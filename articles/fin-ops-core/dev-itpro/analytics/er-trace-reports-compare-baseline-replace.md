---
title: Miglioramenti nella tracciatura dei risultati dei report ER generati e nella comparazione degli stessi con i valori di base
description: Questo argomento descrive i miglioramenti alla funzionalità di base ER in Microsoft Dynamics 365 for Finance and Operations versione 10.0.3 (giugno 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 1c00a5d9e2804f6ec0f6cb4c544029a1235ee58d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094006"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a>Miglioramenti nella tracciatura dei risultati dei report ER generati e nella comparazione degli stessi con i valori di base

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto il primo set di miglioramenti apportati alle funzionalità di base del framework di report elettronici (ER). Questi miglioramenti sono disponibili in Microsoft Dynamics 365 for Finance and Operations versione 10.0.3 (giugno 2019) e versioni successive.

## <a name="automate-the-setting-of-baseline-rules"></a>Automatizzare l'impostazione delle regole di base

L'argomento [Generare la traccia dei risultati dei report generati e confrontarli con i valori di base](er-trace-reports-compare-baseline.md) descrive il modo in cui configurare il framework ER per raccogliere informazioni sulle esecuzioni del formato ER e valutare i risultati di tali esecuzioni. L'esempio in questo argomento illustra i passaggi che devono essere completati.

Di seguito sono riportati alcuni passaggi:

- Eseguire un formato ER per generare un file in uscita e archiviare il file localmente.
- Aggiungere localmente il file archiviato come allegato della base aggiunta per un formato ER.
- Configurare la regola di base per la base aggiunta. Questa configurazione prevede i passaggi seguenti:

    - Specificare un elemento del formato ER utilizzato per generare un file in uscita.
    - Selezionare l'allegato che fa riferimento al file in uscita generato.

> [!NOTE]
> Questi passaggi devono essere eseguiti manualmente, anche se le nuove funzionalità ER ne consentono l'automatizzazione. Per ulteriori informazioni su questa funzionalità, completare l'esempio riportato di seguito.

## <a name="example-automate-the-setting-of-baseline-rules"></a>Esempio: automatizzare l'impostazione delle regole di base

Per completare i passaggi in questo esempio, completare dapprima i passaggi dell'esempio nell'argomento [Generare la traccia dei risultati dei report generati e confrontarli con i valori di base](er-trace-reports-compare-baseline.md) fino alla sezione "Aggiungere una nuova base per un formato ER progettato".

### <a name="review-added-baseline"></a>Esaminare la base aggiunta

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Selezionare **Basi**.

    > [!NOTE]
    > Il pulsante **Basi** nel riquadro azioni è disponibile solo quando il parametro dell'utente ER **Esegui in modalità di debug** è attivato per la società corrente.

La base è stata aggiunta per il formato **Formato per ottenere basi ER** selezionato, ma non ancora le regole di base per tale base.

![Pagina Base del formato per la creazione di report elettronici, ancora nessuna regola](media/GER-BaselineSample-AddBaseline2.PNG "Schermata della pagina Basi del formato per la creazione di report elettronici")

### <a name="make-a-new-baseline-rule"></a>Creare un nuova regola di base

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella struttura espandere **Modello per ottenere basi ER**.
3. Nella struttura, selezionare **Modello per ottenere basi ER\\Formato per ottenere basi ER**.
4. Nella scheda dettaglio **Versioni** selezionare **Esegui**.
5. Nel campo **Immettere ID**, immettere **1**.
6. Impostare l'opzione **Creare file di base** su **Sì**.
7. Selezionare **OK**.
8. Selezionare **Basi**.

    ![Pagina Basi del formato per la creazione di report elettronici, base selezionata](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Schermata della pagina Basi del formato per la creazione di report elettronici")

    Il file in uscita generato è stato allegato automaticamente alla base del formato ER eseguito. La regola di base è stata aggiunta automaticamente a questa base e contiene il riferimento al file allegato.

9. Nel campo **Nome** immettere **Base 1**.
10. Nel campo **Maschera nome file** digitare **.xml**.
11. Selezionare **Salva**.

### <a name="run-the-format"></a>Eseguire il formato

A questo punto è possibile completare i passaggi rimanenti nell'esempio dell'argomento [Generare la traccia dei risultati dei report generati e confrontarli con i valori di base](er-trace-reports-compare-baseline.md) a partire dalla sezione "Eseguire il formato ER progettato ed esaminare il registro per analizzare i risultati".

> [!NOTE]
> Quando si elimina la regola di base aggiunta automaticamente nella Scheda dettaglio **Basi**, l'allegato a cui si fa riferimento non viene eliminato automaticamente.

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Configurare la base in modo che ignori costantemente le parti variabili dell'output ER

Quando un formato ER è progettato per contenere informazioni che vengono modificate all'esecuzione del formato, il formato deve utilizzare la funzionalità di base ER per confrontare i risultati generati ai valori di base. Ad esempio, le informazioni potrebbero essere la data e l'ora di elaborazione o l'identificatore univoco di un documento generato in formati differenti (identificatore univoco globale \[GUID\] e così via). Le nuove funzionalità ER consentono di configurare la regola di base in modo che ignori gli elementi variabili di un formato ER quando il formato viene eseguito allo scopo di confrontare i valori di base ai risultati dell'esecuzione del formato. Per ulteriori informazioni su questa funzionalità, completare l'esempio riportato di seguito.

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Esempio: configurare la base in modo che ignori le parti variabili dell'output ER

Per completare i passaggi in questo esempio, completare dapprima i passaggi dell'esempio nell'argomento[Generare la traccia dei risultati dei report generati e confrontarli con i valori di base](er-trace-reports-compare-baseline.md).

### <a name="modify-a-configured-er-format"></a>Modificare un formato ER configurato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella struttura espandere **Modello per ottenere basi ER**.
3. Nella struttura, selezionare **Modello per ottenere basi ER\\Formato per ottenere basi ER**.
4. Selezionare **Progettazione**.
5. Nella struttura selezionare **Output\\Documento**.
6. Selezionare **Aggiungi**.
7. Nella finestra di dialogo a discesa, nella struttura selezionare **XLM\\Attributo**.
8. Nel campo **Nome**, immettere **DataOraElaborazione**.
9. Selezionare **OK**.
10. Nella scheda **Mapping**, nella struttura, selezionare **Output\\Documento\\DataOraElaborazione**.
11. Selezionare **Modifica formula**.
12. Nel campo **Formula**, immettere la seguente espressione: **DATETIMEFORMAT(NOW(), "O")**
13. Selezionare **Salva** e quindi selezionare **Test**.
14. Selezionare di nuovo **Test** per testare di nuovo l'espressione configurata.

    ![Pagina Designer formula](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Schermata della pagina Designer formula")

    > [!NOTE]
    > La scheda **Risultato test** indica che l'espressione configurata restituisce un valore di data e ora differente ogni volta che viene richiamata.

15. Chiudere la pagina **Designer formula** quindi selezionare **Salva**.

    ![Pagina Progettazione formati](media/GER-BaselineSample-FormatMappingDesign2.PNG "Schermata della pagina Progettazione formati")

16. Chiudere la pagina **Progettazione formati**.

### <a name="remove-an-existing-baseline-rule"></a>Rimuovere una regola di base esistente

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Selezionare **Basi**.
3. Nell'elenco delle basi, selezionare la base configurata per il formato **Formato per ottenere basi ER**.
4. Nella Scheda dettaglio **Basi**, selezionare **Elimina** per rimuovere la regola di base configurata in precedenza.

![Pagina Base del formato per la creazione di report elettronici, eliminata](media/GER-BaselineSample-AddBaseline3.PNG "Schermata della pagina Basi del formato per la creazione di report elettronici")

### <a name="define-replacements-for-bindings-of-designed-er-format"></a>Definire le sostituzioni per le associazioni del formato ER progettato

1. Nella pagina **Configurazioni**, nella scheda dettaglio **Sostituzioni**, selezionare **Seleziona componenti**.
2. Nella struttura dei componenti del formato, **Output**, espandere **Output\\Documento** e quindi selezionare la casella di controllo per **Output\\Documento\\DataOraElaborazione**.
3. Selezionare **OK**.

![Pagina Base del formato per la creazione di report elettronici, componenti](media/GER-BaselineSample-AddBaseline4.PNG "Schermata della pagina Basi del formato per la creazione di report elettronici")

Il componente del formato ER selezionato è stato aggiunto all'elenco dei componenti nella scheda dettaglio **Sostituzioni**. Quando il formato ER di base viene eseguito in modalità di debug, l'associazione del formato per ogni componente verrà sostituita dall'associazione visualizzata nella colonna **Associazione**. Per modificare l'associazione predefinita per un componente elencata nella scheda dettaglio **Sostituzioni**, selezionare **Modifica**.

### <a name="make-a-new-baseline-rule"></a>Creare un nuova regola di base

Seguire i passaggi nella sezione "Esempio: automatizzare l'impostazione delle regole di base" vista precedentemente in questo argomento. Una notifica informa che il file in uscita è stato generato utilizzando le impostazioni di base e che si è verificata una sostituzione forzata delle associazioni del formato.

![Notifica sulla pagina Configurazioni](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Schermata della notifica nella pagina Configurazioni")

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a>Sopprimere gli avvisi relativi alla sostituzione delle associazioni del formato

Impostando parametri ER specifici, è possibile sopprimere le notifiche che informano della sostituzione delle associazioni del formato. Questa soppressione può essere utile se le associazioni del formato vengono sostituite in una modalità automatica utilizzando Regression Suite Automation Tool. In questo caso, l'avviso può essere considerato un errore del test case in esecuzione.

1. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, selezionare **Parametri utente**.
2. Impostare l'opzione **Sopprimi avvisi di base** su **Sì** e selezionare **OK**.

### <a name="review-the-generated-baseline-file"></a>Esaminare il file di base generato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Selezionare **Basi**.
3. Selezionare **Allegati**.
    > [!NOTE]
    > Il file generato contiene il testo della data e dell'ora di elaborazione (**"#"**) dell'associazione configurata nella regola di base aggiunta e non dell'associazione del formato.
    
4. Chiudere la pagina **Allegati**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Eseguire il formato ER progettato ed esaminare il registro per analizzare i risultati

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella struttura espandere **Modello per ottenere basi ER**.
3. Nella struttura, selezionare **Modello per ottenere basi ER\\Formato per ottenere basi ER**.
4. Nella scheda dettaglio **Versioni** selezionare **Esegui**.
5. Nel campo **Immetti ID**, digitare **1**.
6. Selezionare **OK**.
7. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Registri debug configurazione**.

Il registro di esecuzione contiene informazioni sui risultati del confronto tra il file generato e la base configurata. Il registro indica che il file generato e la base sono uguali, anche se il formato eseguito contiene l'associazione per immettere un valore di data e ora costantemente variabile nel file in uscita.

> [!NOTE]
> Sebbene il file in uscita sia stato generato utilizzando le impostazioni di base che forzano la sostituzione delle associazioni del formato, non vengono restituiti avvisi relativi alla sostituzione.

## <a name="exchange-baseline-settings-between-environments"></a>Scambiare le impostazioni di base tra ambienti

### <a name="export-baseline-settings"></a>Esportare impostazioni di base

Le nuove funzionalità ER consentono di esportare impostazioni di base per il formato ER selezionato dall'ambiente corrente e di archiviarle come file XML. 

Per esportare le impostazioni di base, nella pagina **Basi del formato per la creazione di report elettronici**, selezionare **Esporta**.

### <a name="import-baseline-settings"></a>Importa impostazioni di base

Le impostazioni di base esportate possono essere importate in un ambiente differente. L'ambiente deve essere dapprima importato come formato ER. Successivamente è possibile importare le impostazioni di base.

Per importare le impostazioni di base da un file XML archiviato in locale, nella pagina **Basi del formato per la creazione di report elettronici**, selezionare **Importa** e quindi **Sfoglia** per selezionare il file XML.

![Finestra di dialogo Importa impostazioni di base](media/GER-BaselineSample-ImportBaseline1.PNG "Schermata della finestra di dialogo Importa impostazioni di base")

Per importare le impostazioni di base da un file XML archiviato nel server di Microsoft SharePoint, in base alle impostazioni correnti di Gestione documenti e il tipo di documento selezionato, nella pagina **Basi del formato per la creazione di report elettronici**, selezionare **Importa dall'origine**. Selezionare quindi il tipo di documento e il file XML. Il tipo di documento necessario per accedere alla cartella SharePoint deve essere configurato in anticipo.

![Finestra di dialogo Importa dall'origine](media/GER-BaselineSample-ImportBaseline2.PNG "Schermata della finestra di dialogo Importa dall'origine")

> [!NOTE]
> È possibile utilizzare Registrazione attività per registrare i passaggi per la selezione del tipo di documento richiesto e il nome di file nella finestra dialogo **Importa dall'origine**. In questo modo, è possibile mantenere le impostazioni di base richieste sul server SharePoint e quindi eseguirne l'importazione automaticamente eseguendo una registrazione attività quando si eseguono test automatizzati utilizzando Regression Suite Automation Tool.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Tracciare i risultati del report generato e paragonarli ai valori di base](er-trace-reports-compare-baseline.md)
- [Risorse registrazione attività](../user-interface/task-recorder.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]