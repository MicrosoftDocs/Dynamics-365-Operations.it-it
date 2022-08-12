---
title: Automatizzare il test con la creazione di report elettronici
description: In questo articolo viene descritto come utilizzare la funzionalità di base del framework di creazione di report elettronici (ER) per automatizzare i test di alcune funzionalità.
author: NickSelin
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatBaselineTable, ERFormatMappingRunLogTable, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 6254d15d13e40007396c9f2a36a8cd3122dc2609
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "9109342"
---
# <a name="automate-testing-with-electronic-reporting"></a>Automatizzare il test con la creazione di report elettronici

[!include[banner](../includes/banner.md)]

In questo articolo viene descritto come utilizzare il framework di creazione di report elettronici (ER) per automatizzare i test di alcune funzionalità. L'esempio in questo articolo illustra come automatizzare i test dell'elaborazione dei pagamenti fornitore.

L'applicazione utilizza il framework ER per generare file di pagamento e documenti corrispondenti durante l'elaborazione dei pagamenti fornitore. Il framework ER comporta un modello di dati, mapping di modello e componenti di formato che supportano l'elaborazione dei pagamenti per diversi tipi di pagamenti e la generazione di documenti in formati differenti. Questi componenti possono essere scaricati da Microsoft Dynamics Lifecycle Services (LCS) e importati nell'istanza.

È inoltre possibile personalizzare ogni componente di Microsoft e utilizzarlo come base del proprio componente personalizzato. Creando una versione personalizzata, è possibile apportare modifiche che supportano requisiti specifici. Ad esempio, è possibile modificare il modello di dati ER e il modello di mapping ER per accedere a dati dell'applicazione specifici del cliente oppure cambiare un formato ER per modificare il layout di un documento generato.

È possibile utilizzare formati ER personalizzati per elaborare file di pagamento che generano pagamenti fornitore nonché report controllo. Il controllo delle versioni è supportato nei componenti ER. Di conseguenza, Microsoft può fornire versioni aggiornate di soluzioni ER per l'elaborazione dei pagamenti fornitore ed è possibile unire automaticamente la versione aggiornata al proprio componente personalizzato riassegnandola. Tuttavia, è necessario testare la versione riassegnata per assicurarsi che funzioni come previsto.

I modelli di dati ER e i mapping di modello ER sono comuni a numerosi formati ER utilizzati per elaborare differenti tipi di pagamenti e per generare documenti di pagamento specifici del paese o dell'area geografica. Di conseguenza, è particolarmente vantaggioso automatizzare i test di accettazione e integrazione utente di modo che siano eseguiti automaticamente in molteplici società ma prendendo in considerazione il contesto del paese di ogni società di destinazione, utilizzando set di dati diversi e così via.

Per ulteriori informazioni sulla creazione di una versione personalizzata di un formato basato sul formato ricevuto da un provider di configurazione, vedere [ER Aggiornare il formato adottando una nuova versione di base di quel formato](./tasks/er-upgrade-format.md).

## <a name="key-concepts"></a>Concetti chiave

I power user funzionali possono creare test di accettazione e integrazione utente senza dover scrivere codice sorgente.

- Utilizzare la funzionalità di base ER per confrontare i documenti generati alle copie master. Per ulteriori informazioni, vedere [Generare la traccia dei risultati dei report generati e paragonarli ai valori di base](er-trace-reports-compare-baseline.md).
- Utilizzare Registrazione attività per registrare test case e includere la valutazione di base. Per ulteriori informazioni, vedere [Risorse registrazione attività](../user-interface/task-recorder.md).
- Raggruppare test case per gli scenari di test necessari. Per ulteriori informazioni, vedere [Creare e automatizzare i test di accettazione utenti](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md).

    - Utilizzare Modellatore di processi aziendali (BPM) in LCS per creare librerie per test di accettazione utente.
    - Utilizzare librerie di test BPM per creare un piano di test e gruppi di test in Microsoft Azure DevOps Services (Azure DevOps).

I power user funzionali possono eseguire test di accettazione e integrazione utente.

- Utilizzare lo strumento Regression Suite Automation Tool (RSAT) per eseguire test case del gruppo di test desiderato.
- Notificare i risultati dei test a Azure DevOps e utilizzare questo servizio per analizzarli.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter completare le attività in questo articolo, è necessario soddisfare i seguenti prerequisiti:

- Distribuire una topologia che supporta l'automazione dei test. È necessario avere accesso all'istanza di questa topologia per il ruolo **Amministratore di sistema**. Questa topologia deve contenere i dati dimostrativi che verranno utilizzati in questo esempio. Per ulteriori informazioni, vedere [Distribuire ambienti che supportano la compilazione continua e l'automazione dei test](../perf-test/continuous-build-test-automation.md).
- Per eseguire automaticamente i test di accettazione e integrazione utente, è necessario installare RSAT nella topologia in uso e configurarlo nel modo appropriato. Per informazioni su come installare e configurare RSAT per l'uso con le app per la finanza e le operazioni e Azure DevOps, vedere [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357). Prestare attenzione ai prerequisiti per l'utilizzo dello strumento. Di seguito viene illustrato un esempio delle impostazioni RSAT. Il rettangolo blu racchiude i parametri che specificano l'accesso a Azure DevOps. Il rettangolo verde racchiude i parametri che specificano l'accesso all'istanza.

    ![Impostazioni RSAT.](media/GER-Configure.png "Schermata della finestra di dialogo Impostazioni RSAT")

- Per organizzare i test case nei gruppi e garantire la sequenza di esecuzione corretta, di modo che sia possibile raccogliere i registri delle esecuzioni dei test per ulteriori report e analisi, è necessario avere accesso a Azure DevOps dalla topologia distribuita.
- Per completare l'esempio in questo articolo, ti consigliamo di scaricare [Utilizzo di ER per test RSAT](https://go.microsoft.com/fwlink/?linkid=874684). Questo file zip contiene le seguenti guide attività:

    | Contenuto                                           | Nome e posizione dei file |
    |---------------------------------------------------|------------------------|
    | Registrazione attività di esempio per preparare i dati per i test | Prepare\\Recording.xml |
    | Registrazione attività di esempio per elaborare il pagamento fornitore   | Process\\Recording.xml |

## <a name="prepare-the-accounts-payable-module-to-process-vendor-payments"></a>Preparare il modulo Contabilità fornitori per l'elaborazione di pagamenti fornitore

1. Accedere all'istanza.
2. Scaricare le seguenti configurazioni ER da LCS. Per istruzioni, vedere [ER Importare una configurazione da Lifecycle Services](./tasks/er-import-configuration-lifecycle-services.md)

    - Configurazione del modello ER **Modello di pagamento**
    - Configurazione del mapping di modello ER **Mapping di modello di pagamento 1611**
    - Configurazione del formato ER **BACS (UK)**

    ![Configurazioni per la creazione di report elettronici.](media/GER-Configurations.png "Schermata della pagina Configurazioni in Creazione di report elettronici")

3. Selezionare la società di dati dimostrativi **GBSI**, che presenta un contesto di paese in Gran Bretagna.
4. Configurare i parametri di Contabilità fornitori:

    1. Andare a **Contabilità fornitori \> Impostazione pagamenti \> Metodi di pagamento**.
    2. Selezionare il metodo di pagamento **Elettronico**.
    3. Configurare il metodo di pagamento selezionato di modo che utilizzi il formato ER **BACS (UK)** scaricato in precedenza per l'elaborazione dei pagamenti fornitore:

        1. Nella scheda dettaglio **Formati file**, impostare l'opzione **Formato esportazione elettronica generica** su **Sì**.
        2. Nel campo **Esporta configurazione formato** selezionare **BACS (UK)**.

    ![Pagina Metodi di pagamento.](media/GER-APParameters.png "Schermata della pagina Metodi di pagamento")

    > [!NOTE]
    > Se si dispone della versione derivata di questo formato ER creato per supportare le personalizzazioni, è possibile selezionare questa configurazione nel metodo di pagamento **Elettronico**.

5. Creare un pagamento fornitore di esempio:

    1. Andare a **Contabilità fornitori \> Pagamenti \> Giornale di registrazione pagamenti**.
    2. Verificare di non aver registrato il giornale di registrazione pagamenti.

        ![Pagina Giornale di registrazione pagamenti.](media/GER-APJournal.png "Schermata della pagina Giornale di registrazione pagamenti")

    3. Selezionare **Righe** e immettere una riga con le seguenti informazioni.

        | Campo               | Valore di esempio   |
        |---------------------|-----------------|
        | Nome fornitore         | GB\_SI\_000001  |
        | Dare               | 1,000.00        |
        | Valuta            | GBP             |
        | Tipo di conto di contropartita | Banca            |
        | Conto di contropartita      | GBSI OPER       |
        | Metodo di pagamento   | Elettronico      |

    ![Pagina Pagamenti fornitore.](media/GER-APJournalLines.png "Schermata della pagina Pagamenti fornitore")

## <a name="prepare-the-er-framework-to-test-vendor-payment-processing"></a>Preparare il framework ER per verificare l'elaborazione dei pagamenti fornitore

### <a name="configure-er-parameters"></a>Configurare i parametri ER

1. Accedere a **Amministrazione organizzazione \> Creazione di report elettronici \> Parametri per la creazione di report elettronici**.
2. Nella scheda **Allegati**, nel campo **Base**, selezionare **File** come tipo di documento che il framework Gestione documenti (DM) utilizza per mantenere i documenti correlati alla funzionalità di base come allegati DM.

    ![Pagina Parametri per la creazione di report elettronici.](media/GER-ERParameters.png "Schermata della pagina Parametri per la creazione di report elettronici")

### <a name="generate-baseline-copies-of-vendor-paymentrelated-documents"></a>Generare copie di base dei documenti correlati ai pagamenti fornitore

1. Andare a **Contabilità fornitori \> Pagamenti \> Giornale di registrazione pagamenti**.
2. Selezionare **Righe**.
3. Selezionare **Genera pagamenti**.
4. Selezionare il metodo di pagamento **Elettronico**.
5. Selezionare il conto bancario **GBSI OPER**.
6. Impostare l'opzione **Stampa report controllo** su **Sì**.
7. Scaricare l'output generato come file zip.
8. Aprire il file scaricato.
9. Estrarre i seguenti file dal file scaricato:

    - File di pagamento **File** in formato di testo
    - File di report controllo **ERVendOutPaymControlReport** in formato XLSX

    ![File estratti.](media/GER-APJournalProcessed.png "Schermata dei nomi di file estratti in Esplora risorse")

### <a name="turn-on-the-er-baseline-feature"></a>Attivare la funzionalità di base ER

1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
2. Nel riquadro azioni, nella scheda **Configurazioni**, selezionare **Parametri utente**.
3. Impostare l'opzione **Esegui in modalità di debug** su **Sì**.

Attivando il parametro **Esegui in modalità di debug**, si forza il framework ER per eseguire le seguenti azioni dopo l'esecuzione di qualsiasi formato ER che genera documenti in uscita:

1. Stabilire se una base è stato configurata per qualsiasi componente del formato ER eseguito.
2. Determina se ogni base configurata è applicabile nelle condizioni correnti (codice società della società che ha eseguito l'accesso, nome di file ed estensione del nome di file dell'output generato e così via).
3. Per ciascuna base applicabile, eseguire queste operazioni:

    1. Confrontare l'output generato durante l'esecuzione del formato ER alla base corrispondente.
    2. Archiviare i risultati del confronto nel registro di debug delle configurazioni ER.

### <a name="configure-er-baselines-for-vendor-payment-processing"></a>Configurare le basi ER per l'elaborazione dei pagamenti fornitore

1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
2. Selezionare **Basi**.
3. Selezionare **Nuovo**.
4. Nel campo **Riferimento** selezionare il formato **BACS (UK)**.
5. Selezionare **Allegati**.
6. Aggiungere una nuova base per il file di pagamento fornitore:

    1. Selezionare **Nuovo**.
    2. Nel campo **Tipo**, selezionare il tipo di documento DM **File** configurato nei parametri ER per archiviare gli elementi di base.
    3. Selezionare il file di pagamento **File** salvato localmente in formato di testo.
    4. Nel campo **Descrizione** immettere **File TXT di pagamento**.

7. Aggiungere una nuova base per il report controllo per il pagamento fornitore:

    1. Selezionare **Nuovo**.
    2. Nel campo **Tipo**, selezionare il tipo di documento DM **File** configurato nei parametri ER per archiviare gli elementi di base.
    3. Selezionare il file di report controllo **ERVendOutPaymControlReport** salvato localmente in formato XLSX.
    4. Nel campo **Descrizione** digitare **Report controllo XLSX di pagamento**.

    ![Base per il file di pagamento fornitore e report controllo.](media/GER-BaselineAttachments.png "Schermata della pagina Configurazioni con report controllo XLSX di pagamento selezionato")

8. Chiudere la pagina.
9. Nella scheda dettaglio **Basi**, selezionare **Nuovo** per configurare una base per il file di pagamento:

    1. Denominare la riga **Impostazione base per file di pagamento**.
    2. Nel campo **Nome componente file**, selezionare **file** per applicare questa base all'output in formato ER che genera il file di pagamento in formato di testo BACS (UK).
    3. Nel campo **Società**, selezionare **GBSI** per applicare questa base quando il formato ER **BACS (UK)** viene eseguito nella società GBSI.
    4. Nel campo **Maschera nome file**, immettere **\*.TXT** per applicare questa base solo agli output del componente formato **file** che hanno l'estensione **.txt**.
    5. Nel campo **Base**, selezionare **File TXT di pagamento** di modo che questa base sia utilizzata per il confronto con l'output generato.

10. Selezionare **Nuovo** per configurare una base per il report controllo:

    1. Denominare la riga **Impostazione base per report controllo**.
    2. Nel campo **Nome componente file**, selezionare **ERVendOutPaymControlReport** per applicare questa base all'output in formato ER che genera il report controllo.
    3. Nel campo **Società**, selezionare **GBSI** per applicare questa base quando il formato ER **BACS (UK)** viene eseguito nella società GBSI.
    4. Nel campo **Maschera nome file**, immettere **\*.XLSX** per applicare questa base solo agli output del componente formato **ERVendOutPaymControlReport** che hanno l'estensione **.xslx**.
    5. Nel campo **Base**, selezionare **Report controllo XLSX di pagamento** di modo che questa base sia utilizzata per il confronto con l'output generato.

    ![Scheda dettaglio Basi nella pagina Configurazioni.](media/GER-BaselineRules.png "Schermata della Scheda dettaglio Basi nella pagina Configurazioni")

## <a name="record-tests-to-validate-vendor-payment-processing"></a>Registrare i test per convalidare l'elaborazione dei pagamenti fornitore

Come power user funzionale, è possibile registrare i propri passaggi per testare l'elaborazione dei pagamenti fornitore. Si consiglia di riprodurre (e modificare, come richiesto) la registrazione attività **Prepare\\Recording.xml** scaricata in precedenza. Questa registrazione viene utilizzata per impostare tutti i dati di test sullo stato corretto. Quel passaggio è necessario in quanto i test possono essere eseguiti più volte e ogni test deve utilizzare i dati che hanno lo stesso stato.

### <a name="reset-user-settings"></a>Reimpostare le impostazioni utente

1. Aprire il dashboard predefinito.
2. Selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio).
3. Selezionare **Opzioni utente**.
4. Selezionare **Dati utilizzo**.
5. Selezionare **Reimposta**.
6. Selezionare **Sì** per confermare che si desidera reimpostare i dati di utilizzo.
7. Chiudere la pagina.

### <a name="record-the-steps-to-prepare-data-for-testing"></a>Registrare i passaggi per preparare i dati per i test

1. Selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio).
2. Selezionare **Registrazione attività**.
3. Selezionare **Riproduci registrazione**.
4. Selezionare **Apri dal PC**.
5. Selezionare **Sfoglia** e selezionare il file **Prepare\\Recording.xml** salvato localmente.
6. Selezionare **Avvia**.
7. Continuare a selezionare **Esegui passaggio in sospeso successivo** fino a che tutti i passaggi della registrazione siano stati riprodotti.

Questa registrazione attività esegue le seguenti operazioni:

1. Impostare lo stato della riga di pagamento elaborato su **Nessuno**.

    ![Passaggi 3 e 4 della registrazione attività.](media/GER-Recording1Review1.png "Schermata dei passaggi 3 e 4 della registrazione attività")

2. Attivare il parametro utente ER **Esegui in modalità di debug**.

    ![Passaggi 9 e 10 della registrazione attività.](media/GER-Recording1Review2.png "Schermata dei passaggi 9 e 10 della registrazione attività")

3. Pulire il registro di debug ER contenente i risultati del confronto tra i file generati e le basi.

    ![Passaggi 13 e 15 della registrazione attività.](media/GER-Recording1Review3.png "Schermata dei passaggi 13 e 15 della registrazione attività")

### <a name="record-the-steps-to-test-vendor-payment-processing"></a>Registrare i passaggi per testare l'elaborazione dei pagamenti fornitore

Si consiglia di riprodurre (e modificare, come richiesto) la registrazione attività **Process\\Recording.xml** scaricata in precedenza. Questa registrazione viene utilizzata per elaborare i pagamenti fornitore e convalidare i risultati del confronto tra i documenti generati e le basi corrispondenti.

1. Selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio).
2. Selezionare **Registrazione attività**.
3. Selezionare **Riproduci registrazione**.
4. Selezionare **Apri dal PC**.
5. Selezionare **Sfoglia** e selezionare il file **Process\\Recording.xml** salvato localmente.
6. Selezionare **Avvia**.
7. Continuare a selezionare **Esegui passaggio in sospeso successivo** fino a che tutti i passaggi della registrazione siano stati riprodotti.

Questa registrazione attività esegue le seguenti operazioni:

1. Avviare l'elaborazione dei pagamenti fornitore.
2. Selezionare i parametri di runtime corretti e attivare la generazione di un report controllo.

    ![Passaggi 3 e 8 della registrazione attività.](media/GER-Recording2Review1.png "Schermata dei passaggi 3 e 8 della registrazione attività")

3. Accedere al registro di debug ER per registrare i risultati del confronto tra gli output generati e le basi corrispondenti.

    Nel registro di debug ER, i risultati del confronto sono visualizzati nel campo **Testo generato**. I campi **Componente formato** e **Percorso formato che ha generato la voce di registro** fanno riferimento al componente di file per il quale l'output generato è stato confrontato alla base.

    ![Voci nella pagina Voci di registro report elettronici.](media/GER-ERDebugLog.png "Schermata delle voci nella pagina Voci di registro report elettronici")

4. Il confronto tra l'output corrente e la base viene registrato utilizzando l'opzione Registrazione attività **Convalida** e selezionando **Valore corrente**.

    ![Utilizzo dell'opzione Convalida per il confronto con il valore corrente.](media/GER-TRRecordValidation.png "Schermata dell'utilizzo dell'opzione Convalida per il confronto con il valore corrente")

    L'illustrazione seguente mostra i passaggi di convalida registrati nella registrazione attività.

    ![Passaggi 13 e 15 della registrazione attività.](media/GER-Recording2Review2.png "Schermata dei passaggi 13 e 15 della registrazione attività")

## <a name="add-the-recorded-tests-to-azure-devops"></a>Aggiungere i test registrati a Azure DevOps

1. Aprire l'ambiente Azure DevOps.
2. Selezionare il progetto definito nei parametri RSAT durante la [configurazione dello strumento](#prerequisites).
3. Selezionare il piano di test definito nei parametri RSAT durante la [configurazione dello strumento](#prerequisites).
4. Crea un nuovo test case per il piano di test selezionato:

    1. Denominare il test case **Preparare i dati per testare l'elaborazione del pagamento elettronico del fornitore**.
    2. Allegare il file **Recording.xml** dalla cartella **Prepare** scaricata in precedenza.

5. Crea un nuovo test case per il piano di test selezionato:

    1. Denominare il test case **Testare l'elaborazione dei pagamenti fornitore utilizzando il formato ER BACS (UK)**
    2. Allegare il file **Recording.xml** dalla cartella **Process** scaricata in precedenza.

    ![Nuovi test case per il piano di test selezionato.](media/GER-RSAT-DevOps-Tests-Passed.png "Schermata dei nuovi test case per il piano di test selezionato")

> [!NOTE]
> Prestare attenzione all'ordine di esecuzione corretto dei test che vengono aggiunti.

## <a name="prepare-rsat-to-run-the-recorded-tests"></a>Preparare RSAT per eseguire i test registrati

### <a name="load-the-tests-from-azure-devops-to-rsat"></a>Caricare i test da Azure DevOps in RSAT

1. Avviare l'applicazione RSAT locale nella topologia corrente.
2. Selezionare **Carica** per caricare in RSAT i test che si trovano attualmente in Azure DevOps.

    ![Test caricati in RSAT.](media/GER-RSAT-RSAT-Tests-Loaded.png "Schermata dei test caricati in RSAT")

### <a name="create-automation-and-parameters-files"></a>Creare file di automazione e di parametri

1. In RSAT, selezionare i test caricati da Azure DevOps.
2. Selezionare **Nuovo** per creare file di automazione e di parametri RSAT.

    ![File di automazione e di parametri RSAT creati in RSAT.](media/GER-RSAT-RSAT-Tests-Initiated.png "Schermata dei file di automazione e di parametri RSAT creati in RSAT")

### <a name="modify-the-parameters-files"></a>Modificare i file di parametri

1. In RSAT, selezionare il test case **Preparare i dati per testare l'elaborazione del pagamento elettronico del fornitore**.
2. Selezionare **Modifica**.
3. Nella cartella di lavoro Microsoft Excel che viene aperta, nel foglio di lavoro **Generale**, impostare il codice della società su **GBSI**, poiché la società verrà utilizzata per l'esecuzione del test.
4. In RSAT, selezionare il test case **Testare l'elaborazione dei pagamenti fornitore utilizzando il formato ER BACS (UK)**.
5. Selezionare **Modifica**.
6. Nella cartella di lavoro di Excel che viene aperta, nel foglio di lavoro **Generale**, impostare il codice della società su **GBSI**.
7. Nel foglio di lavoro **ERFormatMappingRunLogTable**, notare che le celle A:3 e C:3 contengono il testo dei campi nella tabella del registro di debug ER utilizzati per convalidare i risultati del confronto tra l'output e la base. Questi testi verranno utilizzati per valutare i record del registro di debug ER creati durante l'esecuzione dei test.

    ![Foglio di lavoro ERFormatMappingRunLogTable.](media/GER-RSAT-RSAT-ExcelParameters.png "Schermata del foglio di lavoro ERFormatMappingRunLogTable")

## <a name="run-the-tests-and-analyze-the-results"></a>Eseguire i test e analizzare i risultati

### <a name="run-the-tests-in-rsat"></a>Eseguire i test in RSAT

1. In RSAT, selezionare i test caricati.
2. Selezionare **Esegui**.

Da notare che i test case vengono eseguiti automaticamente nell'applicazione utilizzando un Web browser.

### <a name="analyze-the-results-of-test-execution"></a>Analizzare i risultati dell'esecuzione dei test

I risultati dell'esecuzione dei test sono archiviati in RSAT. Da notare che entrambi i test sono stati superati.

![Test superati in RSAT.](media/GER-RSAT-RSAT-Tests-Passed.png "Schermata dei test superati in RSAT")

Da notare che i risultati dell'esecuzione dei test vengono inviati a Azure DevOps idi modo che sia possibile analizzarli ulteriormente.

![Risultati dell'esecuzione dei test in Azure DevOps.](media/GER-RSAT-DevOps-Tests-Added.png "Schermata dei risultati dell'esecuzione dei test in Azure DevOps")

### <a name="simulate-a-situation-where-tests-fail"></a>Simulare una situazione in cui i test hanno esito negativo

Questo gruppo di test ha esito negativo quando almeno uno degli output generati non corrisponde alla base corrispondente. Per riprodurre questa situazione, è possibile utilizzare la versione derivata del formato **BACS (UK)** che genererà un file di pagamento con un contenuto differente da quello della base corrispondente. Per simulare questa situazione, è possibile utilizzare lo stesso formato **BACS (UK)** ma modificare l'importo del pagamento nella riga di pagamento elaborata.

1. Aprire l'applicazione e andare a **Contabilità fornitori \> Pagamenti \> Giornale di registrazione pagamenti**.
2. Selezionare **Righe**.
3. Selezionare la riga di pagamento e quindi selezionare **Stato pagamenti \> Nessuno**.
4. Nel campo **Dare**, cambiare il valore da **1.000,00** a **2.000,00**.
5. Selezionare **Salva** per salvare le modifiche.

### <a name="run-the-tests-in-rsat"></a>Eseguire i test in RSAT

1. In RSAT, selezionare i test caricati.
2. Selezionare **Esegui**.

Da notare che i test case vengono eseguiti automaticamente nell'applicazione utilizzando un Web browser.

### <a name="analyze-the-results-of-test-execution"></a>Analizzare i risultati dell'esecuzione dei test

I risultati dell'esecuzione dei test sono archiviati in RSAT. Da notare che il secondo test ha avuto esito negativo durante la seconda esecuzione.

![Risultati dei test non superati in RSAT.](media/GER-RSAT-RSAT-Tests-Failed.png "Schermata dei risultati dei test non superati in RSAT")

Da notare che i risultati dell'esecuzione dei test vengono inviati a Azure DevOps idi modo che sia possibile analizzarli ulteriormente.

![Risultati dei test non superati in Azure DevOps.](media/GER-RSAT-DevOps-Tests-Failed.png "Schermata dei risultati dei test non superati in Azure DevOps")

È possibile accedere allo stato di ogni test. È inoltre possibile accedere al registro di esecuzione in modo da analizzare le cause di qualsiasi errore. Nell'illustrazione seguente, il registro di esecuzione mostra che l'errore si è verificato a causa della differenza di contenuto tra il file di pagamento generato e la propria base.

![Registro di esecuzione per l'analisi degli errori in Azure DevOps.](media/GER-RSAT-DevOps-Tests-Failed-Log.png "Schermata del registro di esecuzione per l'analisi degli errori in Azure DevOps")

Di conseguenza, come visto, il funzionamento di qualsiasi formato ER può essere valutato automaticamente utilizzando RSAT come piattaforma di test e mediante i test case basati su Registrazione attività che utilizzano la funzionalità di base ER.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Risorse registrazione attività](../user-interface/task-recorder.md)
- [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)
- [Creare e automatizzare i test di accettazione utenti](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)
- [Distribuire ambienti che supportano la compilazione continua e l'automazione dei test](../perf-test/continuous-build-test-automation.md)
- [Tracciare i risultati del report generato e paragonarli ai valori di base](er-trace-reports-compare-baseline.md)
- [ER Aggiornare il formato adottandone una nuova versione di base](tasks/er-upgrade-format.md)
- [ER importa una configurazione da Lifecycle Services](tasks/er-import-configuration-lifecycle-services.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
