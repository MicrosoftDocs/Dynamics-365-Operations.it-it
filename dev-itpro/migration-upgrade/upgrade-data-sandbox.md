---
title: Aggiornamento dei dati in un ambiente sandbox
description: In questo argomento viene descritto come eseguire un aggiornamento dei dati da AX 2012 a Dynamics 365 for Finance and Operations in un ambiente sandbox.
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 7140bf740f37a5eb970a5103750a7095d12a33cc
ms.contentlocale: it-it
ms.lasthandoff: 06/15/2017

---

# <a name="data-upgrade-in-a-sandbox-environment"></a>Aggiornamento dei dati in un ambiente sandbox

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

L'output di questa attività è un database aggiornato che è possibile utilizzare in un ambiente sandbox. Un ambiente sandbox è un ambiente in cui gli utenti aziendali e i membri dei team funzionali possono convalidare il funzionamento delle applicazioni. Questa funzionalità include le personalizzazioni e i dati riportati da Microsoft Dynamics AX 2012.

Si consiglia di eseguire il processo di aggiornamento dei dati in un ambiente di sviluppo per eseguirlo in un ambiente sandbox condiviso, poiché questo approccio aiuta a ridurre il tempo complessivo necessario per il corretto aggiornamento dei dati. Per ulteriori informazioni, vedere [Aggiornamento dei dati in un ambiente di sviluppo](prepare-data-upgrade.md).

## <a name="overview-of-the-sandbox-data-upgrade-process"></a>Panoramica del processo di aggiornamento dei dati sandbox

Prima di iniziare ad aggiornare i dati in un ambiente sandbox, si sarà già eseguito l'aggiornamento di dati in un ambiente di sviluppo, come spiegato in [Aggiornamento dei dati in un ambiente di sviluppo](prepare-data-upgrade.md). I due processi sono molto simili. La differenza principale è che un ambiente sandbox utilizza il database SQL di Microsoft Azure per l'archiviazione dei dati, mentre un ambiente di sviluppo utilizza Microsoft SQL Server. La differenza tecnica nel livello di database richiede che la procedura di aggiornamento dei dati venga leggermente modificata in un ambiente sandbox, poiché un backup dall'istanza del database AX 2012 non può essere semplicemente ripristinato nel database SQL.

![Processo di aggiornamento dei dati sandbox](./media/data-upgrade-sandbox.png)

Di seguito vengono riportati i passaggi di alto livello del processo di aggiornamento.

1. Creare una copia del database AX 2012. Si consiglia di utilizzare una copia, poiché è necessario eliminare alcuni oggetti nella copia che verrà esportata.
2. Esportare il database copiato in un file bacpac utilizzando uno strumento libero di SQL Server denominato SQLPackage.exe. Questo strumento fornisce un tipo speciale di backup del database che può essere importato nel database SQL.
3. Caricare il file bacpac in Archiviazione di Azure.
4. Scaricare il file bacpac nel computer server oggetti applicativi (AOS) nell'ambiente sandbox, quindi importarlo utilizzando SQLPackage.exe. È necessario quindi eseguire uno script rispetto al database importato per reimpostare gli utenti del database SQL.
5. Eseguire il pacchetto MajorVersionDataUpgrade.zip per eseguire l'aggiornamento dei dati rispetto al database importato.

## <a name="create-a-copy-of-the-ax-2012-database"></a>Creare una copia del database AX 2012

È necessario creare una copia del database AX 2012 in fase di aggiornamento, poiché è necessario eliminare alcuni oggetti dal database. Questi oggetti includono tutti gli utenti di autenticazione di Microsoft Windows. Queste modifiche rendono il database modificato inutilizzabile per AX 2012. Durante questo passaggio, si creerà una copia del database e si cancelleranno questi oggetti.

Questo passaggio deve essere eseguito dall'amministratore del database (DBA) o da una persona che abbia una conoscenza e un'esperienza simili.

Per creare una copia del database, eseguire il backup del database originale e ripristinarlo con un nuovo nome. Assicurarsi di avere spazio sufficiente per entrambi i database. È possibile creare la copia in un server diverso. La versione dell'istanza di SQL Server che esegue il database non è importante.

Di seguito è riportato un esempio del codice che crea una copia del database. È necessario modificare questo esempio in base ai nomi database specifici.

    BACKUP DATABASE [AxDB] TO  DISK = N'D:\Backups\axdb_copyForUpgrade.bak' WITH NOFORMAT, NOINIT,  
    NAME = N'AxDB_copyForUpgrade-Full Database Backup', SKIP, NOREWIND, NOUNLOAD, COMPRESSION,  STATS = 10
    GO

    RESTORE DATABASE [AxDB_copyForUpgrade] FROM  DISK = N'D:\Backups\axdb_copyForUpgrade.bak'   WITH  FILE = 1,  
    MOVE N'AXDBBuild_Data' TO N'F:\MSSQL_DATA\AxDB_copyForUpgrade.mdf',  
    MOVE N'AXDBBuild_Log' TO N'G:\MSSQL_LOGS\AxDB_CopyForUpgrade.ldf',  
    NOUNLOAD,  STATS = 5

Dopo aver creato la copia, eseguire i seguente script Transact-SQL (T-SQL) sulla copia.
TODO 

### <a name="export-the-copied-database-to-a-bacpac-file"></a>Esportare il database copiato in un file bacpac

Esportare il database copiato in un file bacpac utilizzando lo strumento SQLPackage.exe. Questo passaggio deve essere eseguito dall'amministratore del database o da un membro del team che abbia una conoscenza equivalente.

È molto importante che si installi la versione più recente di SQL Server Management Studio prima di iniziare questo passaggio. Sebbene SQLPackage sia presente nelle versioni precedenti di Management Studio, non verrà eseguito correttamente per questo passaggio a meno che prima non si installi la versione più recente.

Questo passaggio è importante perché l'esportazione dovrà essere eseguita di nuovo durante il periodo di inattività prima del passaggio alla fase operativa. Di seguito sono riportati alcuni suggerimenti.

- Il processo bacpac è molto impegnativo a livello di I/O e di CPU. Eseguire quindi l'esportazione in un computer molto potente.
- SQLPackage deve essere eseguito localmente nel computer che ospita il database. Non eseguire SQLPackage in un computer portatile locale connesso al computer del database perché il processo fa un uso intensivo anche della rete.

Successivamente aprire una finestra **Prompt dei comandi** come amministratore ed eseguire i comandi seguenti.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:export /ssn:localhost /sdn:<database to export> /tf:D:\Exportedbacpac\my.bacpac /p:CommandTimeout=1200 /p:VerifyFullTextDocumentTypesSupported=false

Ecco una descrizione dei parametri:

- **ssn** (nome server di origine) - Il nome del server SQL da cui esportare. Per il nostro processo, questo parametro deve essere sempre impostato su **localhost**.
- **sdn** (nome del database di origine) - Il nome del database da esportare.
- **tf** (file di destinazione) - Il percorso e il nome del file in cui esportare. La cartella deve essere già presente, ma il file verrà creato dal processo.
- **/p:CommandTimeout** - Il valore di timeout per query. Questo parametro consente l'esportazione di tabelle di dimensioni più grandi senza il rischio di raggiungere il timeout.

### <a name="upload-the-bacpac-file-to-azure-storage"></a>Caricare il file bacpac in Archiviazione di Azure

Caricare il file bacpac in Archiviazione di Azure. Vedere TODO in UsingStorageExplorer.docx

### <a name="import-the-bacpac-file-into-sql-database"></a>Importare il file bacpac in database SQL

Durante questo passaggio, si importa il file bacpac esportato nell'istanza del database SQL utilizzato dall'ambiente sandbox. È innanzitutto necessario installare la versione più recente di Management Studio nel computer AOS sandbox. Si importa quindi il file utilizzando lo strumento SQLPackage.exe.

Queste attività devono essere eseguite direttamente nel computer AOS nell'ambiente sandbox, perché vi sono regole del firewall che limitano l'accesso all'istanza del database SQL. Invece, se si utilizza il computer AOS è possibile accedere.

Come per il passaggio dell'esportazione, è necessario dotarsi della versione più recente di Management Studio prima di iniziare l'importazione. Questo passaggio non funziona con una versione meno recente.

Per motivi di prestazioni, è consigliabile memorizzare il file bacpac nell'unità D del computer AOS. Nelle macchine virtuali (VM) di Azure l'unità D è un disco fisico che in genere ha prestazioni superiori rispetto agli altri dischi disponibili.

Aprire una finestra **Prompt dei comandi** come amministratore ed eseguire i comandi seguenti.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:import /sf:D:\Exportedbacpac\my.bacpac /tsn:<azure sql database server name>.database.windows.net /tu:sqladmin /tp:<password from LCS> /tdn:<New database name> /p:CommandTimeout=1200 /p:DatabaseEdition=Premium /p:DatabaseServiceObjective=P1

Ecco una descrizione dei parametri:

- **tsn** (nome del server di destinazione) - Il nome del server SQL Azure in cui importare. Il nome è disponibile in LCS. Aggiungervi il suffisso **.database.windows.net**.
- **tdn** (nome del database di destinazione) - Il nome del database in cui importare. Il database non deve necessariamente essere già presente. Sarà creato dal processo di importazione.
- **sf** (file di origine) - Il percorso e il nome del file da cui importare.
- **tp** (password di destinazione) - La password SQL dall'istanza del database SQL di destinazione.
- **tu** (utente di destinazione) - Il nome utente SQL per l'istanza del database SQL di destinazione. Si consiglia di utilizzare **sqladmin**. È possibile recuperare la password per questo utente dal progetto LCS.
- **/p:CommandTimeout** - Il valore di timeout per query. Questo parametro consente l'esportazione di tabelle di dimensioni più grandi senza il rischio di raggiungere il timeout.
- **/p:DatabaseServiceObjective** - Il livello del servizio del database che viene creato. È possibile controllare il valore per il database esistente utilizzando Management Studio. Fare clic con il pulsante destro del mouse sul database, quindi selezionare **Proprietà**.

Dopo aver eseguito i comandi, si riceverà l'avviso seguente. È possibile ignorarlo tranquillamente.

![Errore sandbox](./media/sandbox-2.png)
 
### <a name="run-the-majorversiondataupgradezip-package"></a>Eseguire il pacchetto MajorVersionDataUpgrade.zip

Eseguire il pacchetto distribuibile dell'aggiornamento dei dati come descritto in [Aggiornare i dati in ambienti di sviluppo, demo o sandbox](upgrade-data-to-latest-update.md).

### <a name="upgrade-a-copy-of-the-database-in-a-development-environment"></a>Aggiornare una copia del database in un ambiente di sviluppo

È utile aggiornare lo stesso database in un ambiente di sviluppo. Se si dispone di una copia del database disponibile per gli ambienti di sviluppo, sarà molto più semplice controllare i bug rilevati nell'ambiente sandbox aggiornato.

