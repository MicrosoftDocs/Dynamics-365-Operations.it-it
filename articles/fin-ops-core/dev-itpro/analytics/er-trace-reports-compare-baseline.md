---
title: Tenere traccia dei risultati dei report generati e confrontarli con i valori di base
description: In questo argomento viene descritto come confrontare i risultati dei report ER generati ai valori di report di base.
author: NickSelin
manager: AnnBe
ms.date: 06/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 3141e285f694f8778c7ac886d3f7e289fd76c648
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568927"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Tenere traccia dei risultati dei report generati e confrontarli con i valori di base

[!include[banner](../includes/banner.md)]

È possibile generare la traccia dei risultati dei formati ER che generano documenti elettronici in uscita. Quando si attiva la generazione della traccia (utilizzando il parametro dell'utente ER **Esegui in modalità di debug**), viene generato un nuovo record di traccia nel registro di esecuzione di formati ER ogni volta che viene eseguito un report ER. I dettagli seguenti vengono archiviati in ogni traccia generata:

- Tutti gli avvisi generati dalle regole di convalida
- Tutti gli errori generati dalle regole di convalida
- Tutti i file generati archiviati come allegati del record di traccia

È possibile archiviare i singoli file di applicazione di base per qualsiasi formato di ER. I file vengono considerati file di base quando descrivono i risultati previsti di report che vengono eseguiti. Se un file di base è disponibile per un formato ER che viene eseguito quando la generazione della traccia è attivata, la traccia archivia, oltre ai dettagli menzionati in precedenza, il risultato del confronto tra il documento elettronico generato e il file di base. Con un semplice clic è inoltre possibile ottenere il documento elettronico generato e il relativo file di base in un unico file con estensione zip. È quindi possibile effettuare il confronto dettagliato utilizzando uno strumento esterno come WinDiff.

È possibile valutare la traccia per analizzare se i documenti elettronici generati includono il contenuto previsto. È possibile effettuare questa valutazione in un ambiente di test di accettazione utente (UAT) quando viene modificata la base di codice, ad esempio quando è stata effettuata la migrazione a una nuova istanza dell'applicazione, sono stati installati gli hotfix o sono state distribuite modifiche al codice. In questo modo, è possibile assicurarsi che la valutazione non influisca sull'esecuzione dei report di ER utilizzati. Per molti report di ER, la valutazione può essere effettuata in modalità automatica.

Per ulteriori informazioni su questa funzionalità, riprodurre le guide attività **ER Generare report e confrontare i risultati (Parte 1)** e **ER Generare report e confrontare i risultati (Parte 2)**, che fanno parte del processo aziendale **7.5.4.3 Eseguire test di soluzioni/servizi IT (10679)** e che possono essere scaricate dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Queste guide attività illustrano in dettaglio il processo di configurazione del framework di ER per utilizzare file di base per valutare documenti elettronici generati.

## <a name="example-trace-generated-report-results-and-compare-them-with-baseline-values"></a>Esempio: generare la traccia dei risultati dei report generati e confrontarli con i valori di base

Questa procedura descrive il modo in cui configurare il framework ER per raccogliere informazioni sulle esecuzioni del formato ER e valutare i risultati di tali esecuzioni. Nell'ambito di tale valutazione, i documenti generati vengono confrontati ai file di base. In questo esempio verranno create le configurazioni ER necessarie per la società di esempio Litware, Inc. Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici. Tali passaggi possono essere completati utilizzando qualsiasi set di dati.

Per completare i passaggi in questo esempio, è necessario dapprima completare i passaggi in [Creare fornitori di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, verificare che il provider di configurazione per la società di esempio Litware, Inc. sia elencato e contrassegnato come **Attivo**. Se il provider di configurazione non è visualizzato, seguire i passaggi dell'argomento [Creare fornitori di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-document-management-parameters"></a>Configurare i parametri di gestione documenti

1. Passare a **Amministrazione organizzazione** \> **Gestione documenti** \> **Tipi di documento** e creare un nuovo tipo di documento per archiviare i file di base.
2. Nel campo **Classe**, immettere **Allega file**.
3. Nel campo **Gruppo**, immettere **File**.

![Pagina Tipi di documento](media/GER-BaselineSample-SetupDocumentType.PNG "Schermata della pagina Tipi di documento")

> [!NOTE]
> Un nuovo tipo di documento con lo stesso nome deve essere configurato per ogni set di dati in cui si prevede di utilizzare la funzionalità di base ER.

### <a name="configure-er-parameters-to-start-to-use-the-baseline-feature"></a>Configurare parametri ER per iniziare a utilizzare la funzionalità di base

1. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Collegamenti correlati**, selezionare **Parametri per la creazione di report elettronici**.

    ![Area di lavoro Creazione di report elettronici](media/GER-BaselineSample-ERWorkspace.PNG "Schermata dell'area di lavoro Creazione di report elettronici")

2. Nella scheda **Allegati**, nel campo **Base**, immettere o selezionare il tipo di documento appena creato.

    ![Scheda Allegati della pagina Parametri per la creazione di report elettronici](media/GER-BaselineSample-ERParameters.PNG "Schermata della pagina Parametri per la creazione di report elettronici")

3. Selezionare **Salva** e quindi chiudere la pagina **Parametri per la creazione di report elettronici**.

### <a name="add-a-new-er-model-configuration"></a>Aggiungere una nuova configurazione del modello ER

1. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.
2. Nel riquadro azioni, selezionare **Crea configurazione**.
3. Nella finestra di dialogo a discesa, nel campo **Nome**, immettere **Modello per ottenere basi ER**.
4. Selezionare **Crea configurazione** per confermare la creazione di una nuova voce del modello di dati ER.

![Finestra di dialogo a discesa Crea configurazione](media/GER-BaselineSample-ModelAdd.PNG "Schermata della finestra di dialogo a discesa Crea configurazione")

### <a name="design-a-data-model"></a>Progettare un modello di dati

1. Nella pagina **Configurazioni**, nel riquadro azioni, selezionare **Progettazione**.
2. Selezionare **Nuovo**.
3. Nella finestra di dialogo a discesa, nel campo **Nome**, immettere **Radice**.
4. Selezionare **Aggiungi**.
5. Selezionare **Riferimento radice**.
6. Selezionare **OK** e quindi **Salva**.
7. Chiudere la pagina **Progettazione modello**.
8. Selezionare **Cambia stato**.
9. Selezionare **Completa** e quindi **OK**.

![Pagina Configurazioni](media/GER-BaselineSample-ModelComplete.PNG "Schermata della pagina Configurazioni")

### <a name="add-a-new-er-format-configuration"></a>Aggiungere una nuova configurazione di formato ER

1. Nella pagina **Configurazioni**, nel riquadro azioni, selezionare **Crea configurazione**.
2. Nella finestra di dialogo a discesa, nel gruppo di campi **Nuovo**, selezionare l'opzione **Formato basato sul modello di dati Modello per ottenere basi ER**.
3. Nel campo **Nome**, immettere **Formato per ottenere basi ER**.
4. Selezionare **Crea configurazione** per confermare la creazione di una nuova voce del formato ER.

![Finestra di dialogo a discesa Crea configurazione](media/GER-BaselineSample-FormatAdd.PNG "Schermata della finestra di dialogo a discesa Crea configurazione")

### <a name="design-a-format"></a>Progettare un formato

Per questo esempio, si creerà un formato ER semplice per generare documenti XML.

1. Nella pagina **Configurazioni**, nel riquadro azioni, selezionare **Progettazione**.
2. Selezionare **Aggiungi radice**.
2. Nella finestra di dialogo a discesa, effettuare le seguenti operazioni:

    1. Nella struttura selezionare **Comune\\File**.
    2. Nel campo **Nome** immettere **Output**.
    3. Selezionare **OK**.

3. Selezionare **Aggiungi**.
4. Nella finestra di dialogo a discesa, effettuare le seguenti operazioni:

    1. Nella struttura selezionare **XML\\Elemento**.
    2. Nel campo **Nome** immettere **Documento**.
    3. Selezionare **OK**.

5. Nella struttura selezionare **Output\\Documento**.
6. Selezionare **Aggiungi**.
7. Nella finestra di dialogo a discesa, effettuare le seguenti operazioni:

    1. Nella struttura selezionare **XML\\Attributo**.
    2. Nel campo **Nome** immettere **ID**.
    3. Selezionare **OK**.

    ![Pagina Progettazione formati](media/GER-BaselineSample-FormatLayoutDesign.PNG "Schermata della pagina Progettazione formati")

8. Nella scheda **Mapping**, selezionare **Elimina**.
9. Selezionare **Aggiungi radice**.
10. Nella finestra di dialogo a discesa, nella struttura, selezionare **Generale\\Parametro di input utente** e quindi eseguire quanto segue:

    1. Nel campo **Nome** immettere **ID**.
    2. Nel campo **Etichetta**, immettere **Immetti ID**.
    3. Selezionare **OK**.

11. Nella struttura selezionare **Output\\Documento\\Id**.
12. Selezionare **Associa** e quindi **Salva**.

![Pagina Progettazione formati](media/GER-BaselineSample-FormatMappingDesign.PNG "Schermata della pagina Progettazione formati")

In base alla struttura progettata, il formato configurato genererà un file XML. Questo XML contiene l'elemento **Radice** con l'attributo **ID** impostato sul valore che l'utente immette nella finestra di dialogo Runtime ER.

### <a name="generate-a-new-baseline-file-for-a-designed-er-format"></a>Generare un nuovo file di base per un formato ER progettato

1. Nella pagina **Configurazioni**, nella scheda dettaglio **Versioni**, selezionare **Esegui**.
2. Nel campo **Immetti ID**, immettere **1**.
3. Selezionare **OK**.

    ![Finestra di dialogo Parametri per la creazione di report elettronici](media/GER-BaselineSample-FormatRunToMakeBaselineFile1.PNG "Schermata della finestra di dialogo Parametri per la creazione di report elettronici")

4. Salvare una copia locale del file **out.Admin.xml** generato, di modo che sia possibile utilizzarla successivamente come base per questo formato ER.

    ![Notifica sul file generato nella pagina Configurazioni](media/GER-BaselineSample-FormatRunToMakeBaselineFile2.PNG "Schermata della notifica sul file generato nella pagina Configurazioni")

### <a name="configure-er-parameters-to-use-the-baseline-feature"></a>Configurare parametri ER per utilizzare la funzionalità di base

1. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, selezionare **Parametri utente**.
2. Impostare l'opzione **Esegui in modalità di debug** su **Sì**.
3. Selezionare **OK**.

![Finestra di dialogo Parametri dell'utente](media/GER-BaselineSample-ERUserParameters.PNG "Schermata della finestra di dialogo Parametri dell'utente")

### <a name="add-a-new-baseline-for-designed-er-format"></a>Aggiungere una nuova base per il formato ER progettato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nel riquadro azioni selezionare **Basi**.

    ![Pulsante Basi nella pagina Configurazioni](media/GER-BaselineSample-OpenBaselinePage.PNG "Schermata del pulsante Basi nella pagina Configurazioni")

3. Nel Riquadro azioni selezionare **Nuovo**.
4. Selezionare il formato ER **Formato per ottenere basi ER** progettato in precedenza.
5. Selezionare **Salva**.

![Pagina Base del formato per la creazione di report elettronici](media/GER-BaselineSample-AddBaseline.PNG "Schermata della pagina Basi del formato per la creazione di report elettronici")

La base viene aggiunta per il formato **Formato per ottenere basi ER**.

### <a name="configure-a-baseline-rule-for-the-added-baseline"></a>Configurare una regola di base per la base aggiunta

1. Nella pagina **Base del formato per la creazione di report elettronici**, nel riquadro azioni, selezionare il pulsante **Allegati** (il simbolo di graffetta).
2. Nel riquadro azioni selezionare **Nuovo** \> **File**. Nei parametri ER, il tipo di documento **File** deve essere già stato selezionato come tipo di documento utilizzato per archiviare file di base.
3. Selezionare **Sfoglia** e selezionare il file **out.Admin.xml** generato quando si è eseguito il formato ER configurato in precedenza.

    ![Pagina Allegati](media/GER-BaselineSample-UploadBaselineFile.PNG "Schermata della pagina Allegati")

4. Chiudere la pagina **Allegati**.
5. Nella scheda dettaglio **Basi**, selezionare **Nuovo**.
6. Nel campo **Nome** immettere **Base 1**.
7. Nel campo **Nome componente file**, immettere o selezionare **Output**. Questo valore indica che la base configurata verrà confrontata a un file generato utilizzando l'elemento **Output** del formato.
8. Nel campo **Maschera nome file** immettere **\*.xml**.

    > [!NOTE]
    > È possibile definire la maschera del nome di file. Quando la maschera del nome di file viene definita, il record di base verrà utilizzato per valutare l'output generato solo se il nome del file di output generato è conforme a quella maschera.

9. Se la base configurata deve essere utilizzata solo quando il formato ER **Formato per ottenere basi ER** viene eseguito dagli utenti che hanno eseguito l'accesso a specifiche società, selezionare quelle società nel campo **Società**.
10. Nel campo **Base**, immettere o selezionare l'allegato **out.Admin**.
11. Selezionare **Salva**.

![Pagina Base del formato per la creazione di report elettronici](media/GER-BaselineSample-SetupBaselineLine.PNG "Schermata della pagina Basi del formato per la creazione di report elettronici")

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Eseguire il formato ER progettato ed esaminare il registro per analizzare i risultati

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella struttura espandere **Modello per ottenere basi ER**, quindi selezionare **Modello per ottenere basi ER\\Formato per ottenere basi ER**.
3. Nella scheda dettaglio **Versioni** selezionare **Esegui**.
4. Nel campo **Immetti ID**, immettere **1**.
5. Selezionare **OK**.
6. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Registri debug configurazione**.

    ![Pagina Voci di registro report elettronici](media/GER-BaselineSample-ReviewBaselineComparison1.PNG "Schermata della pagina Voci di registro report elettronici")

    > [!NOTE]
    > Il registro di esecuzione contiene informazioni sui risultati del confronto tra il file generato e la base configurata. In questo esempio, il registro indica che il file generato e la base sono uguali.

7. Selezionare **Elimina tutto**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Eseguire il formato ER progettato ed esaminare il registro per analizzare i risultati

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella struttura espandere **Modello per ottenere basi ER**, quindi selezionare **Modello per ottenere basi ER\\Formato per ottenere basi ER**.
3. Nella scheda dettaglio **Versioni** selezionare **Esegui**.
4. Nel campo **Immetti ID**, immettere **2**.
5. Selezionare **OK**.
6. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Registri debug configurazione**.

    ![Pagina Voci di registro report elettronici](media/GER-BaselineSample-ReviewBaselineComparison2.PNG "Schermata della pagina Voci di registro report elettronici")

    > [!NOTE]
    > Il registro di esecuzione contiene informazioni sui risultati del confronto tra il file generato e la base configurata. In questo esempio, il registro indica che il file generato e la base differiscono.

7. Selezionare **Confronta**.

> [!NOTE]
> Il file generato e il file di base sono in formato compresso. È possibile utilizzare strumenti di confronto esterni come WinDiff per comparare i file ed esaminare le differenze.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Configurare il framework di report elettronici](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]