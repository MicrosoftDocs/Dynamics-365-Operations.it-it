---
title: Impostare la dichiarazione elettronica per immettere potenza dati BI da Dynamics 365 per le operazioni
description: "In questo argomento viene descritto come utilizzare nella configurazione Creazione di report elettronici (ER) per definire il trasferimento di dati dall&quot;istanza di Microsoft Dynamics 365 for Operations ai servizi Power BI. Come esempio, in questo argomento vengono utilizzate le transazioni Intrastat come dati aziendali che devono essere trasferiti. La visualizzazione della mappa di Power BI utilizza questi dati transazione Intrastat per presentare una visualizzazione per l&quot;analisi delle attività di importazione o esportazione della società nel report di Power BI."
author: kfend
manager: AnnBe
ms.date: 2016-10-31 13 - 22 - 29
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ed0192c44b6d7e88120c64e539ebb0ac3b379831
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-electronic-reporting-to-provide-power-bi-with-data-from-dynamics-365-for-operations"></a>Impostare la dichiarazione elettronica per immettere potenza dati BI da Dynamics 365 per le operazioni

In questo argomento viene descritto come utilizzare nella configurazione Creazione di report elettronici (ER) per definire il trasferimento di dati dall'istanza di Microsoft Dynamics 365 for Operations ai servizi Power BI. Come esempio, in questo argomento vengono utilizzate le transazioni Intrastat come dati aziendali che devono essere trasferiti. La visualizzazione della mappa di Power BI utilizza questi dati transazione Intrastat per presentare una visualizzazione per l'analisi delle attività di importazione o esportazione della società nel report di Power BI.

<a name="overview"></a>Panoramica
--------

Microsoft Power BI è una raccolta di servizi software, app e connettori che lavorano insieme per convertire le origini esterne dei dati in informazioni coerenti, visivamente immersive e interattive. La creazione report elettronici (ER) consente agli utenti di Microsoft Dynamics 365 for Operations di configurare facilmente le origini dati e disporre il trasferimento dei dati da Dynamics 365 for Operations a Power BI. I dati vengono trasferiti come file nel formato di foglio di lavoro OpenXML (file di cartella di lavoro di Microsoft Excel). I file trasferiti sono archiviati in un server Microsoft SharePoint configurato per questo scopo. I file archiviati vengono utilizzati in Power BI per creare report contenenti visualizzazioni (tabelle, grafici, mappe e così via). I report di Power BI vengono condivisi con gli utenti di Power BI e vengono utilizzati nei dashboard di Power BI e nelle pagine Dynamics 365 for Operations. In questo argomento sono spiegate le seguenti attività:

-   Configurare Dynamics 365 for Operations.
-   Preparare la configurazione del formato ER per ottenere i dati da Dynamics 365 for Operations.
-   Configurare l'ambiente ER per trasferire i dati a Power BI.
-   Utilizzare i dati trasferiti per creare un report di Power BI.
-   Rendere il report di Power BI accessibile in Dynamics 365 for Operations.

## <a name="prerequisites"></a>Prerequisiti
Per completare l'esempio riportato in questo argomento, è necessario disporre del seguente accesso:

-   Accesso a Dynamics 365 for Operations per uno dei seguenti ruoli:
    -   Sviluppatore per la creazione di report elettronici
    -   Consulente funzionale per la creazione di report elettronici
    -   Amministratore di sistema
-   Accesso a SharePoint Server configurato per l'utilizzo con Dynamics 365 for Operations
-   Accesso al framework Power BI

## <a name="configure-document-management-parameters"></a>Configurare i parametri di gestione documenti
1.  Nella pagina **Parametri di gestione documenti** configurare l'accesso a SharePoint Server che verrà utilizzato nella società a cui è stato eseguito l'accesso (la società DEMF in questo esempio).
2.  Verificare la connessione a SharePoint Server per assicurarsi di disporre dell'accesso. [pagina di parametri di gestione documenti![(]. /media/ger-power-bi-sharepoint-server-setting-1024x369.png)](. /media/ger-power-bi-sharepoint-server-setting.png)
3.  Aprire il sito di SharePoint configurato. Creare una nuova cartella in cui ER memorizza i file di Excel con i dati aziendali richiesti dai report di Power BI come origine dei set di dati di Power BI.
4.  In Dynamics 365 for Operations, nella pagina **Tipi di documento**, creare un nuovo tipo di documento che verrà utilizzato per accedere alla cartella di SharePoint appena creata. Immettere **File** nel campo **Gruppo** e **SharePoint** nel campo **Posizione** e immettere il percorso della cartella di SharePoint. [tipi di documento pagina![(]. /media/ger-power-bi-sharepoint-document-type-1024x485.png)](. /media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>Configurare i parametri ER
1.  Nell'area di lavoro **Creazione di report elettronici**, fare clic sul collegamento **Parametri per la creazione di report elettronici**.
2.  Nella scheda **Allegati**, selezionare il tipo di documento **File** per tutti i campi.
3.  Nell'area di lavoro **Creazione di report elettronici**, rendere attivo il provider richiesto facendo clic su **Imposta come attivo**. Per ulteriori informazioni, consultare la guida attività **Selezionare il provider di servizi con ER**.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>Utilizzare un modello dati ER come origine dati
È necessario disporre di un modello dati ER come origine dei dati aziendali che verranno utilizzati nei report di Power BI. Questo modello dati viene caricato dall'archivio delle configurazioni ER. Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](download-electronic-reporting-configuration-lcs.md) o riprodurre la guida attività **Importare con ER una configurazione da Lifecyle Services**. Selezionare **Intrastat **come modello dati che verrà caricato dall'archivio delle configurazioni ER selezionato. In questo esempio, la versione 1 del modello utilizzata.) È quindi possibile accedere ** Intrastat ** alla configurazione di modelli di ER ** configurazioni ** nella pagina. [pagina di![configurazioni (]. /media/ger-power-bi-data-model-1024x371.png)](. /media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Progettare una configurazione di formato ER
È necessario creare una nuova configurazione di formato ER che utilizza il modello dati **Intrastat** come origine dei dati aziendali. Questa configurazione di formato deve generare i risultati di output come documenti elettronici nel formato OpenXML (file di Excel). Per ulteriori informazioni, riprodurre la guida attività **Creare con ER una configurazione per report in OPENXML**. Assegnare alla nuova configurazione il nome **Attività di esportazione/importazione**, come illustrato nella figura seguente. Utilizzare il file Excel [Data ER - Dettagli di esportazione e importazione](https://go.microsoft.com/fwlink/?linkid=845208) come modello quando si progetta il formato ER. Per informazioni su come importare un modello di formato, giochi la Guida di attività.) [] configurazione dell'importazione o esportazione![(media ger-power-bi-format-configuration.png/)](media ger-power-bi-format-configuration.png/) per modificare ** attività esportazione/importazione ** formato della configurazione, effettuare le seguenti operazioni.

1.  Fare clic su **Progettazione**.
2.  Nella scheda **Formato**, assegnare all'elemento di file per questo formato il nome **File di output di Excel**. [articolo del file di output![ excel (]. /media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](. /media/ger-power-bi-format-configuration-file-element-name.png)
3.  Nella scheda **Mapping**, specificare il nome del file di Excel che verrà generato ogni volta che il formato viene eseguito. Configurare l'espressione correlata per restituire il valore **Dettagli di esportazione e importazione** (l'estensione del nome file xlsx verrà aggiunta automaticamente). [![Format designer](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)
4.  Aggiungere un nuovo articolo di origine dati per questo formato. Questa enumerazione sarà necessaria per un'altra associazione di dati.
    1.  Nominano l'origine dati ** enum\_di tipo **.
    2.  Selezionare **Enumerazione modello dati** come tipo di origine dati.
    3.  Fare riferimento all'enumerazione del modello dati **Direzione**.

    [enum\_di direzione![(]. /media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](. /media/ger-power-bi-format-configuration-mapping-added-enum.png)
5.  Completare l'associazione degli elementi del modello dati **Intrastat** agli elementi del formato progettato, come illustrato nella figura seguente. [![che completa l'associazione (]. /media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](. /media/ger-power-bi-format-configuration-mapping-details.png)

Una volta eseguito, il formato ER genera il risultato di output nel formato di Excel. Invia i dettagli delle transazioni Intrastat al risultato di output e le separa come transazioni che descrivono le attività di importazione o attività di esportazione. Fare clic su ** esecuzione ** per verificare il nuovo formato di ER a elenco di transazioni Intrastat ** Intrastat ** nella pagina (** imposta ** &gt; ** dichiarazioni ** &gt; ** commercio estero ** &gt; ** Intrastat **). [pagina![Intrastat (]. /media/ger-power-bi-format-test-run-transactions-1024x322.png)](. /media/ger-power-bi-format-test-run-transactions.png) Il seguente risultato di output viene generato. Il file è denominato **Dettagli di esportazione e importazione.xlsx**, come specificato nelle impostazioni di formato. [importazione![ e esportazione details.xlsx (]. /media/ger-power-bi-format-test-run-output-1024x472.png)](. /media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>Configurare la destinazione ER
È necessario configurare il framework ER per inviare il risultato di output della nuova configurazione di formato ER in modo speciale.

-   Il risultato di output deve essere inviato alla cartella del SharePoint Server selezionato.
-   Ciascuna esecuzione della configurazione di formato deve creare una nuova versione dello stesso file di Excel.

** Reporting elettronica ** nella pagina (** Amministrazione organizzazione ** &gt; ** reporting **) elettronica, fare clic su destinazione ** elettronica di reporting ** l'articolo e aggiungere una nuova destinazione. Nel campo **Riferimento**, selezionare la configurazione di formato **Attività di esportazione/importazione** creata in precedenza. Seguire questi passaggi per aggiungere un nuovo record di destinazione file per il riferimento.

1.  Nel campo **Nome** immettere il titolo della destinazione file.
2.  Nel campo **Nome file**, selezionare il nome **File di output di Excel** per il componente del formato di file di Excel.

Fare clic sul pulsante **Impostazioni** per il nuovo record di destinazione. Quindi, nella finestra di dialogo **Impostazioni di destinazione**, effettuare le seguenti operazioni.

1.  Nella scheda **Power BI**, impostare l'opzione **Abilitato** su **Sì**.
2.  Nel campo **SharePoint**, selezionare il tipo di documento **Condiviso** creato in precedenza.

## <a name="schedule-execution-of-the-configured-er-format"></a>Programmare l'esecuzione del formato ER configurato
In ** configurazioni ** pagina (** Amministrazione organizzazione ** &gt; ** reporting elettronica ** &gt; ** configurazioni **), nella struttura di configurazioni, selezionare ** attività esportazione/importazione ** la configurazione creata in precedenza. Modificare lo stato della versione 1.1 da **Bozza** in **Completato** per rendere questo formato disponibile per l'utilizzo. [pagina di![configurazioni (]. /media/ger-power-bi-format-configuration-complete-1024x401.png)](. /media/ger-power-bi-format-configuration-complete.png) Selezionare la versione completata ** attività esportazione/importazione ** di configurazione quindi su ** ** esecuzione. Si noti che la destinazione configurata viene applicata al risultato di output generato in formato di Excel. Impostare l'opzione **Elaborazione batch** su **Sì** per eseguire il report in modalità automatica. Fare clic su **Ricorrenza** per programmare la ricorrenza richiesta per l'esecuzione del batch. La ricorrenza definisce la frequenza di trasferimento dei dati aggiornati da Dynamics 365 for Operations a Power BI. [finestra di dialogo elettronica dei parametri del report![(]. /media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](. /media/ger-power-bi-format-configuration-run-to-schedule.png) Dopo che ha configurato, è possibile trovare il processo di esecuzione del report di ER ** processi batch ** nella pagina (** processi batch Informazioni di Amministrazione &gt; sistema &gt; **). [pagina di processi batch![(]. /media/ger-power-bi-format-configuration-running-job-1024x410.png)](. /media/ger-power-bi-format-configuration-running-job.png) Quando il processo viene eseguito per la prima volta, la destinazione crea un nuovo file di Excel con il nome della cartella selezionata di SharePoint. A ogni esecuzione successiva del processo, la destinazione crea una nuova versione del file di Excel. [nuova versione![il file di Excel (]. /media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](. /media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Creare un set di dati di Power BI mediante il risultato di output del formato ER
Accedere a Power BI e aprire un gruppo esistente di Power BI (area di lavoro) o creare un nuovo gruppo. Fare clic su ** aggiungere ** in ** file ** ** importare o si ottengono i dati ** nell'area, o fare clic sul segno più (**+**) accanto a ** gruppi di dati ** nel riquadro sinistro. [![per la creazione di un set di dati (]. /media/ger-power-bi-add-dataset-1024x524.png)](. /media/ger-power-bi-add-dataset.png) Selezionare ** siti SharePoint Team ** l'opzione quindi immettere il percorso di SharePoint Server in uso ** (https://ax7partner.spoppe.com** nel proprio esempio). Andare alla cartella **/Shared Documents/GER data/PowerBI** e selezionare il file di Excel creato come origine dati per il nuovo set di dati di Power BI. [![che seleziona il file di Excel (]. /media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](. Fare clic su di /media/ger-power-bi-add-dataset-select-excel-file.png) ** collegare ** quindi su ** ** importazione. Un nuovo set di dati viene creato in base al file di Excel selezionato. Il set di dati può anche essere aggiunto automaticamente al dashboard appena creato. [set di dati![nel dashboard (]. /media/ger-power-bi-added-dataset-1024x489.png)](. /media/ger-power-bi-added-dataset.png) Configurare la programmazione dei a questo set di dati forzino un aggiornamento periodico. Gli aggiornamenti periodici abilitano l'utilizzo di nuovi dati aziendali che provengono da Dynamics 365 for Operations mediante l'esecuzione periodica del report ER tra le nuove versioni del file di Excel create nel SharePoint Server.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Creare un report di Power BI mediante il nuovo set di dati
Per creare un nuovo report di Power BI, fare clic sul set di dati di Power BI **Dettagli di esportazione e importazione** creato. Quindi, configurare la visualizzazione. Ad esempio, selezionare la visualizzazione **Mappa compilata** e configurarla nel seguente modo:

-   Assegnare il campo del set di dati **CountryOrigin** al campo **Posizione** della visualizzazione della mappa.
-   Assegnare il campo del set di dati **Importo** al campo **Saturazione colore** della visualizzazione della mappa.
-   Aggiungere i campi del set di dati **Attività** e **Anno** alla raccolta di campi **Filtri** della visualizzazione della mappa.

Salvare il report di Power BI come **Report dettagli di esportazione e importazione**. [importazione![ e report con i dettagli di esportazione (]. /media/ger-power-bi-added-report-1024x498.png)](. Nota di /media/ger-power-bi-added-report.png) che la mappa vengono visualizzati i paesi inclusi nel file di Excel (Austria e Svizzera in questo esempio). Questi paesi sono a colori per mostrare la proporzione di importi fatturati per ciascuno di essi. Aggiornare l'elenco delle transazioni Intrastat. La transazione di esportazione che proviene dall'Italia viene aggiunta. [elenco di transazioni Intrastat![(]. /media/ger-power-bi-new-run-new-transaction-1024x321.png)](. Aspettare di /media/ger-power-bi-new-run-new-transaction.png) programmata l'esecuzione successiva del report di ER e aggiornare il successivo del set di dati di Power BI. Quindi esaminare il report di Power BI (selezionare per visualizzare solo le transazioni di importazione). La mappa aggiornata ora visualizza Italia. [mappa aggiornamento![(]. /media/ger-power-bi-new-run-new-map-1024x511.png)](. /media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-dynamics-365-for-operations"></a>Accedere al report di Power BI in Dynamics 365 for Operations
Impostare l'integrazione tra Dynamics 365 for Operations e Power BI. Per ulteriori informazioni, vedere [Configurazione dell'integrazione di Power BI per le aree di lavoro](configure-power-bi-integration.md). ** Reporting elettronica ** nella pagina di area di lavoro che supporti alimentano BI l'integrazione (** Amministrazione organizzazione ** &gt; ** aree di lavoro ** &gt; ** area di lavoro elettronica di reporting **), fare clic su ** opzioni ** &gt; ** l'apertura del catalogo ** del report. Selezionare il report di Power BI **Dettagli di esportazione e importazione** creato, per visualizzare il report come elemento di azione nella pagina selezionata. Fare clic sull'elemento di azione per aprire la pagina Dynamics 365 for Operations che indica il report progettato in Power BI. [importazione![ e report con i dettagli di esportazione (]. /media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](. /media/ger-power-bi-review-bi-report-in-ax-form.png)

<a name="see-also"></a>Vedere anche
--------

[Destinazione report elettronici](electronic-reporting-destinations.md)

[Panoramica sui report elettronici](general-electronic-reporting.md)


