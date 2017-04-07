---
title: Reimposta data mart di reporting finanziario dopo il ripristino del database
description: Viene descritta la procedura per reimpostare la data mart di reporting finanziario dopo il recupero di Microsoft Dynamics 365 per il database delle operazioni.
author: twheeloc
manager: AnnBe
ms.date: 2016-12-08 16 - 20 - 13
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 3967cbb869fbb23d5d7716f619e4c22b4a273921
ms.lasthandoff: 03/29/2017


---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Reimposta data mart di reporting finanziario dopo il ripristino del database

Viene descritta la procedura per reimpostare la data mart di reporting finanziario dopo il recupero di Microsoft Dynamics 365 per il database delle operazioni. 

Esistono vari scenari in cui è possibile aver bisogno di ripristinare il Dynamics 365 per il database delle operazioni da un backup o di copiare il database da un altro ambiente. In questi casi, è inoltre necessario seguire i passaggi appropriati per assicurarsi che il data mart di reporting finanziario utilizzando sia correttamente Dynamics ripristinato 365 per il database delle operazioni. Per eventuali domande in merito la reimpostazione data mart di reporting finanziario per un motivo al recupero di Dynamics 365 per il database delle operazioni, fare riferimento al [per ripetere la data mart] di Management Reporter (https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) per ulteriori informazioni. Si noti che i passaggi del processo è supportata per Dynamics 365 per l'operazione la versione del maggio 2016 configurazione (App 7.0.1265.23014 di configurazione e 7.0.10000.4 di reporting finanziario) e altre nuove versioni. Se si dispone di una versione precedente di Microsoft Dynamics 365 per le operazioni, contattare il proprio un team di supporto di assistenza.

## <a name="export-report-definitions"></a>Esporta le definizioni di report
Innanzitutto, esportare la risoluzione del report disponibili in Progettazione report, utilizzando i seguenti passaggi:

1.  In Progettazione report, andare ** società ** &gt; ** gruppi di blocchi predefiniti **.
2.  Selezionare il gruppo che si e fare clic su ** ** esportazione. ** Nota: ** A Dynamics 365 per le operazioni, un solo gruppo di blocchi predefiniti, è supportata ** ** standard.
3.  Consente di selezionare le definizioni di report da esportare:
    -   Per esportare tutte le definizioni di report e i blocchi predefiniti associati, fare clic su **Seleziona tutto**.
    -   Per esportare specifici report, righe, colonne, alberi o set di dimensioni, fare clic sulla scheda appropriata e selezionare gli elementi da esportare. Per selezionare più elementi in una scheda, tenere premuto CTRL. Quando si selezionano i report da esportare, righe, colonne, alberi e i set di dimensioni associati vengono selezionati.

4.  Fare clic su ** ** esportazione.
5.  Immettere un nome di file e selezionare un percorso protetto in cui si desidera salvare le definizioni di report esportate.
6.  Click **Save**.

Il file possono essere copiate o caricare in un percorso protetto, in cui verrà inclusa in un ambiente diverso in un altro momento. Le informazioni sull'utilizzo di un conto di archiviazione di Microsoft Azure sono disponibili in [trasferire dati con] l'utilità riga di comando di AzCopy (https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). ** Nota: ** Microsoft non fornisce un conto di archiviazione come parte del Dynamics 365 per il contratto delle operazioni. È necessario richiedere un conto di archiviazione o impostare un conto di archiviazione da una sottoscrizione azzurrata separata. ** Importante: ** Tenere presente il comportamento di unità di D sulle macchine virtuali azzurrate. Non gestire i gruppi esportati di blocchi predefiniti definitivamente in questo campo. Per ulteriori informazioni sulle unità temporanee, vedere [capendo l'unità temporanea sulle macchine virtuali] di Windows Azure (https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Consente di interrompere i servizi
Utilizzare il desktop remoto a cui connettersi tutti i computer nell'ambiente e interrompere i seguenti servizi di Windows utilizzando services.msc:

-   Servizio di rilascio di World Wide Web (in tutti i computer AOS)
-   Microsoft Dynamics 365 per l'utilizzo di gestione in lotti di operazioni (in computer AOS non privati solo)
-   Servizio del processo di Management Reporter 2012 (BI in computer solo)

I servizi che avranno connessioni aperte in Dynamics 365 per il database delle operazioni.

## <a name="reset"></a>Reimpostazione
#### <a name="locate-the-latest-dataupgradezip-package"></a>Individuare l'ultimo pacchetto di DataUpgrade.zip

Individuare l'ultimo pacchetto di DataUpgrade.zip utilizzando le direzioni disponibili in [dallo script di DataUpgrade.zip (]. \ \ migrazione- aggiornamento upgrade-data-to-latest-update.md). Le istruzioni riportate di seguito viene descritto come individuare la versione corretta dei colli di aggiornamento dei dati per l'ambiente.

#### <a name="execute-scripts-against-dynamics-365-for-operations-database"></a>Eseguire gli script con Dynamics 365 per il database delle operazioni

Eseguire gli script con Dynamics 365 per il database di operazioni (non in base al database di report finanziari).

-   Script\\ConfigureAxReportingIntegration.sql di DataUpgrade.zip\\AosService\\
-   Script\\GrantAzViewChangeTracking.sql di DataUpgrade.zip\\AosService\\

Questi script è possibile assicurarsi che gli utenti, ruoli e della modifica che abbia rispettato le impostazioni siano corretti.

#### <a name="execute-powershell-command-to-reset-database"></a>Eseguire il comando di PowerShell per ripristinare il database

Eseguire il comando riportato di seguito, direttamente nel computer AOS, reimpostare l'integrazione tra Dynamics 365 per le operazioni e i report finanziari:

1.  Intervalli aperte PowerShell come amministratore.
2.  Eseguire: F:
3.  Eseguire: F CD:\\MRApplicationService\\MRInstallDirectory
4.  Eseguire: Inclusione-modulo. MRDeploy server\\\\MRDeploy.psd1\\
5.  Eseguire: Reimposta - DatamartIntegration - ragiona ELSE - ReasonDetail "&lt;contemporanea il motivo per reimpostare"
    -   Verrà richiesto di immettere "in" S per confermare.

Descrizione dei parametri:

-   I valori validi per - Motivo è: ASSISTENZA, BADDATA, ELSE.
-   - Il parametro di ReasonDetail a testo libero.
-   Il motivo e il reasonDetail verranno registrati nella telemetria/monitoraggio dell'ambiente.

## <a name="start-services"></a>Avvia i servizi
Utilizzare services.msc per riavviare i servizi che è stata interrotta in precedenza:

-   Servizio di rilascio di World Wide Web (in tutti i computer AOS)
-   Microsoft Dynamics 365 per l'utilizzo di gestione in lotti di operazioni (in computer AOS non privati solo)
-   Servizio del processo di Management Reporter 2012 (BI in computer solo)

## <a name="import-report-definitions"></a>Importare le definizioni di report
Importare le risoluzione del report da Progettazione report, utilizzando il file creato durante l'esportazione:

1.  In Progettazione report, andare ** società ** &gt; ** gruppi di blocchi predefiniti **.
2.  Selezionare il gruppo che si e fare clic su ** ** esportazione. ** Nota: ** A Dynamics 365 per le operazioni, un solo gruppo di blocchi predefiniti, è supportata ** ** standard.
3.  Selezionare ** standard ** il blocco predefinito e fare clic su ** ** importazione.
4.  Selezionare il file che contiene le definizioni di report esportate e fare clic su ** aprire **.
5.  Nella finestra di dialogo Importa, selezionare le definizioni di report da importare:
    -   Per importare tutte le definizioni di report e i blocchi predefiniti di supporto, fare clic su **Seleziona tutto**.
    -   Per importare specifici report, righe, colonne, alberi o set di dimensioni, selezionare i report, le righe, le colonne, gli alberi o i set di dimensioni da importare.

6.  Click **Import**.



