---
title: Reimpostare il data mart dei report finanziari dopo il ripristino di un database
description: In questo argomento viene descritto come reimpostare il data mart dei report finanziari dopo il ripristino di un database di Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6e3f78fb2f6528449d2a411225cd0e14ca33443e
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Reimpostare il data mart dei report finanziari dopo il ripristino di un database

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come reimpostare il data mart dei report finanziari dopo il ripristino di un database di Microsoft Dynamics 365 for Finance and Operations.

Se si ripristina il database di Finance and Operations da un backup o si copia il database da un altro ambiente, è necessario completare i passaggi in questo argomento per assicurarsi che il data mart dei report finanziari stia utilizzando correttamente il database di Finance and Operations ripristinato. 
> [!Note] 
> I passaggi di questo processo sono supportati per la versione di maggio 2016 di Dynamics 365 for Operation (build di app 7.0.1265.23014 e build di report finanziari 7.0.10000.4) e versioni successive. Se si dispone di una versione precedente di Finance and Operations, contattare il team del supporto per assistenza.

## <a name="export-report-definitions"></a>Esportare definizioni di report
Innanzitutto, esportare le progettazioni di report disponibili in Progettazione report, utilizzando i seguenti passaggi:

1.  In Progettazione report, passare a **Società** &gt; **Gruppi di blocchi predefiniti**.
2.  Selezionare il gruppo di blocchi predefiniti da esportare, quindi fare clic su **Esporta**. 

    > [!Note] 
    > Per Finance and Operations, è supportato un solo gruppo di blocchi predefiniti, **Predefinito**.
    
3.  Selezionare le definizioni di report da esportare:
    -   Per esportare tutte le definizioni di report e i blocchi predefiniti associati, fare clic su **Seleziona tutto**.
    -   Per esportare specifici report, righe, colonne, alberi o set di dimensioni, fare clic sulla scheda appropriata e selezionare gli elementi da esportare. Per selezionare più elementi in una scheda, tenere premuto CTRL. Quando si selezionano i report da esportare, vengono selezionate le righe, le colonne, gli alberi e i set di dimensioni associati.

4.  Fare clic su **Esporta**.
5.  Immettere un nome di file e selezionare un percorso protetto in cui si desidera salvare le definizioni di report esportate.
6.  Fare clic su **Salva**.

Il file può essere copiato o caricato in un percorso protetto, in modo da consentirne l'importazione in un ambiente diverso in un secondo momento. Le informazioni sull'utilizzo di un account di archiviazione di Microsoft Azure sono disponibili in [Trasferire dati con l'utilità riga di comando di AzCopy](/azure/storage/storage-use-azcopy). 
> [!NOTE]
> Microsoft non fornisce un account di archiviazione incluso nel contratto Finance and Operations. È necessario richiedere un account di archiviazione o impostarne uno da una sottoscrizione Azure separata. 
> [!WARNING]
> Tenere presente il comportamento dell'unità D sulle macchine virtuali Azure. Non conservare i gruppi di blocchi predefiniti esportati in questa posizione in modo permanente. Per ulteriori informazioni sulle unità temporanee, vedere [Informazioni sull'unità temporanea sulle macchine virtuali Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Interrompere i servizi
Utilizzare Desktop remoto per collegarsi a tutti i computer nell'ambiente e interrompere i seguenti servizi Windows utilizzando services.msc:

-   Servizio di pubblicazione World Wide Web (in tutti i computer AOS)
-   Servizio di gestione dei batch di Microsoft Dynamics 365 for Finance and Operations (solo in computer AOS non privati)
-   Servizio dei processi dello strumento di creazione report di gestione 2012 (solo in computer BI)

Questi servizi avranno connessioni aperte al database di Finance and Operations.

## <a name="reset"></a>Reimpostazione
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a>Individuare e scaricare il pacchetto MinorVersionDataUpgrade.zip più recente

Individuare il pacchetto MinorVersionDataUpgrade.zip più recente utilizzando le istruzioni disponibili in [Scaricare il pacchetto distribuibile di aggiornamento dei dati più recente](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). Le istruzioni illustrano come individuare e scaricare la versione corretta del pacchetto di aggiornamento dei dati. Un aggiornamento non è necessario per scaricare il pacchetto MinorVersionDataUpgrade.zip. È sufficiente completare i passaggi nella sezione "Scaricare il pacchetto distribuibile di aggiornamento dei dati più recente" senza eseguire le altre operazioni dell'articolo per recuperare una copia del pacchetto MinorVersionDataUpgrade.zip.

### <a name="execute-scripts-against-finance-and-operations-database"></a>Eseguire gli script sul database di Finance and Operations

Eseguire i seguenti script sul database di Finance and Operations (non sul database dei report finanziari).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Questi script garantiscono che gli utenti, i ruoli e le impostazioni di rilevamento delle modifiche siano corretti.

### <a name="execute-powershell-command-to-reset-database"></a>Eseguire il comando PowerShell per reimpostare il database

Nel computer AOS, eseguire i comandi seguenti in PowerShell come amministratore per reimpostare l'integrazione tra Finance and Operations e i report finanziari:

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> Dopo l'esecuzione dei comandi, Verrà richiesto di immettere "Y" per confermare.

Descrizione dei parametri:

-   I valori validi per -Reason sono: SERVICING, BADDATA, OTHER.
-   Il parametro -ReasonDetail è a testo libero.
-   Il motivo e il parametro reasonDetail verranno registrati in telemetria/monitoraggio dell'ambiente.

## <a name="start-services"></a>Avviare i servizi
Utilizzare services.msc per riavviare i servizi interrotti in precedenza:

-   Servizio di pubblicazione World Wide Web (in tutti i computer AOS)
-   Servizio di gestione dei batch di Microsoft Dynamics 365 for Finance and Operations (solo in computer AOS non privati)
-   Servizio dei processi dello strumento di creazione report di gestione 2012 (solo in computer BI)

## <a name="import-report-definitions"></a>Importare definizioni di report
Importare le progettazioni di report da Progettazione report, utilizzando il file creato durante l'esportazione:

1.  In Progettazione report, passare a **Società** &gt; **Gruppi di blocchi predefiniti**.
2.  Selezionare il gruppo di blocchi predefiniti da esportare, quindi fare clic su **Esporta**. 

    > [!NOTE]
    > Per Finance and Operations, è supportato un solo gruppo di blocchi predefiniti, **Predefinito**.
    
3.  Selezionare il blocco predefinito **Predefinito** e fare clic su **Importa**.
4.  Selezionare il file contenente le definizioni di report esportate e fare clic su **Apri**.
5.  Nella finestra di dialogo Importa, selezionare le definizioni di report da importare:
    -   Per importare tutte le definizioni di report e i blocchi predefiniti di supporto, fare clic su **Seleziona tutto**.
    -   Per importare specifici report, righe, colonne, alberi o set di dimensioni, selezionare i report, le righe, le colonne, gli alberi o i set di dimensioni da importare.

6.  Fare clic su **Importa**.





