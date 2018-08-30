---
title: Configurare la creazione di report elettronici (ER) per eseguire il pull dei dati in Power BI
description: In questo argomento viene descritto come utilizzare nella configurazione Creazione di report elettronici (ER) per definire il trasferimento di dati dall'istanza di Finance and Operations ai servizi Power BI.
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 9f5a4d0c9fc4c5c9b439b4f184b25085f5d68077
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="configure-electronic-reporting-er-to-pull-data-into-power-bi"></a>Configurare la creazione di report elettronici (ER) per eseguire il pull dei dati in Power BI

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come utilizzare nella configurazione Creazione di report elettronici (ER) per definire il trasferimento di dati dall'istanza di Finance and Operations ai servizi Power BI. Come esempio, in questo argomento vengono utilizzate le transazioni Intrastat come dati aziendali che devono essere trasferiti. La visualizzazione della mappa di Power BI utilizza questi dati transazione Intrastat per presentare una visualizzazione per l'analisi delle attività di importazione o esportazione della società nel report di Power BI.

<a name="overview"></a>Panoramica
--------

Microsoft Power BI è una raccolta di servizi software, app e connettori che lavorano insieme per convertire le origini esterne dei dati in informazioni coerenti, visivamente immersive e interattive. La creazione report elettronici (ER) consente agli utenti di Microsoft Dynamics 365 for Finance and Operations di configurare facilmente le origini dati e disporre il trasferimento dei dati da Finance and Operations a Power BI. I dati vengono trasferiti come file nel formato di foglio di lavoro OpenXML (file di cartella di lavoro di Microsoft Excel). I file trasferiti sono archiviati in un server Microsoft SharePoint configurato per questo scopo. I file archiviati vengono utilizzati in Power BI per creare report contenenti visualizzazioni (tabelle, grafici, mappe e così via). I report di Power BI vengono condivisi con gli utenti di Power BI e vengono utilizzati nei dashboard di Power BI e nelle pagine Finance and Operations. In questo argomento sono spiegate le seguenti attività:

-   Configurare Finance and Operations.
-   Preparare la configurazione del formato ER per ottenere i dati da Finance and Operations.
-   Configurare l'ambiente ER per trasferire i dati a Power BI.
-   Utilizzare i dati trasferiti per creare un report di Power BI.
-   Rendere il report di Power BI accessibile in Finance and Operations.

## <a name="prerequisites"></a>Prerequisiti
Per completare l'esempio riportato in questo argomento, è necessario disporre del seguente accesso:

-   Accesso a Finance and Operations per uno dei seguenti ruoli:
    -   Sviluppatore per la creazione di report elettronici
    -   Consulente funzionale per la creazione di report elettronici
    -   Amministratore di sistema
-   Accesso a SharePoint Server configurato per l'utilizzo con Finance and Operations
-   Accesso al framework Power BI

## <a name="configure-document-management-parameters"></a>Configurare i parametri di gestione documenti
1.  Nella pagina **Parametri di gestione documenti** configurare l'accesso a SharePoint Server che verrà utilizzato nella società a cui è stato eseguito l'accesso (la società DEMF in questo esempio).
2.  Verificare la connessione a SharePoint Server per assicurarsi di disporre dell'accesso. [![Pagina Parametri di gestione documenti](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)
3.  Aprire il sito di SharePoint configurato. Creare una nuova cartella in cui ER memorizza i file di Excel con i dati aziendali richiesti dai report di Power BI come origine dei set di dati di Power BI.
4.  In Finance and Operations, nella pagina **Tipi di documento**, creare un nuovo tipo di documento che verrà utilizzato per accedere alla cartella di SharePoint appena creata. Immettere **File** nel campo **Gruppo** e **SharePoint** nel campo **Posizione** e immettere il percorso della cartella di SharePoint. [![Pagina Tipi di documento](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>Configurare i parametri ER
1.  Nell'area di lavoro **Creazione di report elettronici**, fare clic sul collegamento **Parametri per la creazione di report elettronici**.
2.  Nella scheda **Allegati**, selezionare il tipo di documento **File** per tutti i campi.
3.  Nell'area di lavoro **Creazione di report elettronici**, rendere attivo il provider richiesto facendo clic su **Imposta come attivo**. Per ulteriori informazioni, consultare la guida attività **Selezionare il provider di servizi con ER**.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>Utilizzare un modello dati ER come origine dati
È necessario disporre di un modello dati ER come origine dei dati aziendali che verranno utilizzati nei report di Power BI. Questo modello dati viene caricato dall'archivio delle configurazioni ER. Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](download-electronic-reporting-configuration-lcs.md) o riprodurre la guida attività **Importare con ER una configurazione da Lifecyle Services**. Selezionare **Intrastat** come modello dati che verrà caricato dall'archivio delle configurazioni ER selezionato. In questo esempio viene utilizzata la versione 1 del modello. È quindi possibile accedere alla configurazione del modello di report elettronico **Intrastat** nella pagina **Configurazioni**. [![Pagina Configurazioni](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Progettare una configurazione di formato ER
È necessario creare una nuova configurazione di formato ER che utilizza il modello dati **Intrastat** come origine dei dati aziendali. Questa configurazione di formato deve generare i risultati di output come documenti elettronici nel formato OpenXML (file di Excel). Per ulteriori informazioni, riprodurre la guida attività **Creare con ER una configurazione per report in OPENXML**. Assegnare alla nuova configurazione il nome **Attività di esportazione/importazione**, come illustrato nella figura seguente. Utilizzare il file Excel [Data ER - Dettagli di esportazione e importazione](https://go.microsoft.com/fwlink/?linkid=845208) come modello quando si progetta il formato ER. Per informazioni su come importare un modello di formato, vedere la guida attività.) [![Configurazione Attività di esportazione/importazione](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png) Per modificare la configurazione del formato **Attività di esportazione/importazione**, seguire questi passaggi.

1.  Fare clic su **Progettazione**.
2.  Nella scheda **Formato**, assegnare all'elemento di file per questo formato il nome **File di output di Excel**. [![Elemento di file di output di Excel](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)
3.  Nella scheda **Mapping**, specificare il nome del file di Excel che verrà generato ogni volta che il formato viene eseguito. Configurare l'espressione correlata per restituire il valore **Dettagli di esportazione e importazione** (l'estensione del nome file xlsx verrà aggiunta automaticamente). [![Progettazione formati](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)
4.  Aggiungere un nuovo articolo di origine dati per questo formato. Questa enumerazione sarà necessaria per un'altra associazione di dati.
    1.  Assegnare un nome all'origine dati **direction\_enum**.
    2.  Selezionare **Enumerazione modello dati** come tipo di origine dati.
    3.  Fare riferimento all'enumerazione del modello dati **Direzione**.

    [![direction\_enum](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)
5.  Completare l'associazione degli elementi del modello dati **Intrastat** agli elementi del formato progettato, come illustrato nella figura seguente. [![Completare l'associazione](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

Una volta eseguito, il formato ER genera il risultato di output nel formato di Excel. Invia i dettagli delle transazioni Intrastat al risultato di output e le separa come transazioni che descrivono le attività di importazione o attività di esportazione. Fare clic su **esegui** per verificare il nuovo formato di report elettronico per l'elenco di transazioni Intrastat nella pagina **Intrastat** (**Imposta** &gt; **Dichiarazioni** &gt; **Commercio estero** &gt; **Intrastat**). [![Pagina Intrastat](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png) Viene generato il seguente risultato di output. Il file è denominato **Dettagli di esportazione e importazione.xlsx**, come specificato nelle impostazioni di formato. [![Import and export details.xlsx](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>Configurare la destinazione ER
È necessario configurare il framework ER per inviare il risultato di output della nuova configurazione di formato ER in modo speciale.

-   Il risultato di output deve essere inviato alla cartella del SharePoint Server selezionato.
-   Ciascuna esecuzione della configurazione di formato deve creare una nuova versione dello stesso file di Excel.

Nella pagina **Creazione di report elettronici** (**Amministrazione organizzazione** &gt; **Creazione di report elettronici**) fare clic su **Destinazione report elettronici** e aggiungere una nuova destinazione. Nel campo **Riferimento**, selezionare la configurazione di formato **Attività di esportazione/importazione** creata in precedenza. Seguire questi passaggi per aggiungere un nuovo record di destinazione file per il riferimento.

1.  Nel campo **Nome** immettere il titolo della destinazione file.
2.  Nel campo **Nome file**, selezionare il nome **File di output di Excel** per il componente del formato di file di Excel.

Fare clic sul pulsante **Impostazioni** per il nuovo record di destinazione. Quindi, nella finestra di dialogo **Impostazioni di destinazione**, effettuare le seguenti operazioni.

1.  Nella scheda **Power BI**, impostare l'opzione **Abilitato** su **Sì**.
2.  Nel campo **SharePoint**, selezionare il tipo di documento **Condiviso** creato in precedenza.

## <a name="schedule-execution-of-the-configured-er-format"></a>Programmare l'esecuzione del formato ER configurato
1. Nella pagina **Configurazioni** (**Amministrazione organizzazione** &gt; **Creazione di report elettronici** &gt; **Configurazioni**), nell'albero delle configurazioni, selezionare la configurazione creata in precedenza **Attività di esportazione/importazione**. 
2. Modificare lo stato della versione 1.1 da **Bozza** in **Completato** per rendere questo formato disponibile per l'utilizzo. [![Pagina Configurazioni](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png) 
3. Selezionare la versione completata della configurazione **Attività di importazione/esportazione** e fare clic su **Esegui**. Si noti che la destinazione configurata viene applicata al risultato di output generato in formato di Excel. 
4. Impostare l'opzione **Elaborazione batch** su **Sì** per eseguire il report in modalità automatica. 
5. Fare clic su **Ricorrenza** per programmare la ricorrenza richiesta per l'esecuzione del batch. La ricorrenza definisce la frequenza di trasferimento dei dati aggiornati da Finance and Operations a Power BI. [![Finestra di dialogo Parametri per la creazione di report elettronici](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png) 
6. Una volta configurato, è possibile trovare il processo di esecuzione del report ER nella pagina **Processi batch** (**Amministrazione di sistema &gt; Informazioni &gt; Processi batch**). [![Pagina Processi batch](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png) 
7. Se il processo viene eseguito per la prima volta, la destinazione crea un nuovo file di Excel con il nome configurato nella cartella selezionata di SharePoint. A ogni esecuzione successiva del processo, la destinazione crea una nuova versione del file di Excel. [![Nuova versione del file di Excel](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Creare un set di dati di Power BI mediante il risultato di output del formato ER
1. Accedere a Power BI e aprire un gruppo esistente di Power BI (area di lavoro) o creare un nuovo gruppo. Fare clic su **Aggiunti** in **File** nella sezione **Importa o connetti a dati** oppure fare clic sul segno più (**+**) accanto a **Set di dati** nel riquadro di sinistra. [![Creazione di un set di dati](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png) 
2. Selezionare l'opzione **SharePoint - Siti del team** quindi immettere il percorso del SharePoint Server in uso (`https://ax7partner.litware.com` in questo esempio). 
3. Passare alla cartella **/Shared Documents/GER data/PowerBI** e selezionare il file di Excel creato come origine dati per il nuovo set di dati di Power BI. [![Selezione del file di Excel](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png) 
4. Fare clic su **Connetti**, quindi su **Importa**. Un nuovo set di dati viene creato in base al file di Excel selezionato. Il set di dati può anche essere aggiunto automaticamente al dashboard appena creato. [![Set di dati nel dashboard](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png) 
5. Configurare la programmazione di aggiornamento per il set di dati in modo da forzare l'aggiornamento periodico. Gli aggiornamenti periodici abilitano l'utilizzo di nuovi dati aziendali che provengono da Finance and Operations mediante l'esecuzione periodica del report ER tra le nuove versioni del file di Excel create nel SharePoint Server.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Creare un report di Power BI mediante il nuovo set di dati
1. Fare clic sul set di dati di Power BI **Dettagli di esportazione e importazione** creato. 
2. Configurare la visualizzazione. Ad esempio, selezionare la visualizzazione **Mappa compilata** e configurarla nel seguente modo:
   -   Assegnare il campo del set di dati **CountryOrigin** al campo **Posizione** della visualizzazione della mappa.
   -   Assegnare il campo del set di dati **Importo** al campo **Saturazione colore** della visualizzazione della mappa.
   -   Aggiungere i campi del set di dati **Attività** e **Anno** alla raccolta di campi **Filtri** della visualizzazione della mappa.

3. Salvare il report di Power BI come **Report dettagli di esportazione e importazione**. [![Report dettagli di esportazione e importazione](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png) Si noti che nella mappa sono visualizzati i paesi inclusi nel file di Excel (Austria e Svizzera in questo esempio). Questi paesi sono a colori per mostrare la proporzione di importi fatturati per ciascuno di essi. 
4. Aggiornare l'elenco delle transazioni Intrastat. La transazione di esportazione che proviene dall'Italia viene aggiunta. [![Elenco di transazioni Intrastat](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png) 
5. Aspettare l'esecuzione programmata successiva del report ER e l'aggiornamento successivo programmato del set di dati di Power BI. Quindi esaminare il report di Power BI (selezionare per visualizzare solo le transazioni di importazione). La mappa aggiornata ora visualizza Italia. [![Mappa aggiornata](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-finance-and-operations"></a>Accedere al report di Power BI in Finance and Operations
Impostare l'integrazione tra Finance and Operations e Power BI. Per ulteriori informazioni, vedere [Configurazione dell'integrazione di Power BI per le aree di lavoro](configure-power-bi-integration.md). 

1. Nella pagina dell'area di lavoro **Creazione di report elettronici** che supporta l'integrazione Power BI (**Amministrazione organizzazione** &gt; **Aree di lavoro** &gt; **Area di lavoro Creazione di report elettronici**) fare clic su **Opzioni** &gt; **Apri catalogo di report**. 
2. Selezionare il report di Power BI **Dettagli di esportazione e importazione** creato, per visualizzare il report come elemento di azione nella pagina selezionata. 
3. Fare clic sull'elemento di azione per aprire la pagina Finance and Operations che indica il report progettato in Power BI. [![Report dettagli di esportazione e importazione](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Destinazioni dei report elettronici](electronic-reporting-destinations.md)

[Panoramica dei report elettronici](general-electronic-reporting.md)




