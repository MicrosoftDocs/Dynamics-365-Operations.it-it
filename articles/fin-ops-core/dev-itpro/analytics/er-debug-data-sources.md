---
title: Eseguire il debug delle origini dati di un formato ER eseguito per analizzare il flusso e la trasformazione dei dati
description: Questo argomento spiega come eseguire il debug delle origini dati di un formato ER eseguito per comprendere meglio il flusso e la trasformazione dei dati configurati.
author: NickSelin
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 86551cfeda1e4204c91b0534cda563012191e25c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348118"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a>Eseguire il debug delle origini dati di un formato ER eseguito per analizzare il flusso e la trasformazione dei dati

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Quando si [configura](tasks/er-format-configuration-2016-11.md) una soluzione ER per generare documenti in uscita, si definiscono i metodi utilizzati per acquisire dati dall'applicazione e immetterli nell'output generato. Per rendere più efficiente il supporto del ciclo di vita della soluzione ER, la soluzione dovrebbe essere costituita da un [modello di dati](general-electronic-reporting.md#DataModelComponent) ER e dai relativi componenti di [mapping](general-electronic-reporting.md#ModelMappingComponent), nonché da un [formato](general-electronic-reporting.md#FormatComponentOutbound) ER e dai relativi componenti di mapping, in modo tale che il mapping di modello sia specifico dell'applicazione, mentre gli altri componenti rimangano indipendenti dall'applicazione. Diversi componenti ER potrebbero pertanto [influire](general-electronic-reporting.md#FormatComponentOutbound) sul processo di immissione dei dati nell'output generato.

In alcuni casi, i dati dell'output generato hanno un aspetto diverso dagli stessi dati nel database dell'applicazione. In questi casi, sarà necessario determinare quale componente ER è responsabile della trasformazione dei dati. La funzionalità di debugger dell'origine dati ER riduce significativamente i tempi e i costi correlati a questa analisi. È possibile interrompere l'esecuzione di un formato ER e aprire l'interfaccia del debugger dell'origine dati. È dunque possibile spostarsi sulle origini dati disponibili e selezionare una singola origine di dati per l'esecuzione. Questa esecuzione manuale simula l'esecuzione dell'origine dati durante l'esecuzione reale di un formato ER. Il risultato è presentato in una pagina in cui è possibile analizzare i dati ricevuti.

Per attivare la funzionalità di debug dell'origine dati, impostare l'opzione **Abilita debug dei dati all'esecuzione del formato** su **Sì** nei parametri utente ER. È quindi possibile avviare il debug dell'origine dati mentre si esegue un formato ER per generare documenti in uscita. Puoi anche usare l'opzione **Avvia debug** per avviare il debug dell'origine dati per un formato ER configurato nella [progettazione dell'operazione ER](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).

Questo argomento fornisce linee guida per l'avvio del debug dell'origine dati per i formati ER eseguiti. Spiega come le informazioni possono aiutarti a comprendere il flusso e le trasformazioni dei dati. Gli esempi in questo argomento utilizzano il processo aziendale per l'elaborazione dei pagamenti del fornitore.

## <a name="limitations"></a>Limiti

Il debugger dell'origine dati può essere utilizzato per accedere ai dati delle origini dati utilizzati nei formati ER eseguiti per generare documenti in uscita. Non può essere utilizzato per eseguire il debug di origini dati di formati ER progettati per analizzare documenti in entrata.

Le seguenti impostazioni dei formati ER non sono attualmente accessibili per il debug dell'origine dati:

- Trasformazioni di formato
- Regole di convalida mapping e formato
- Espressioni di abilitazione
- Dettagli sulla raccolta dei dati in memoria

## <a name="prerequisites"></a>Prerequisiti

- Per completare gli esempi in questo argomento, è necessario disporre dell'accesso ai seguenti [ruoli](../sysadmin/tasks/assign-users-security-roles.md):

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

- La società deve essere impostata su **DEMF**.

- Seguire i passaggi nell'[Appendice 1](#appendix1) di questo argomento per scaricare i componenti della soluzione Microsoft ER richiesti per elaborare i pagamenti del fornitore.
- Seguire i passaggi nell'[Appendice 2](#appendix2) di questo argomento per preparare la contabilità fornitori per l'elaborazione dei pagamenti dei fornitori utilizzando la soluzione ER che verrà scaricata.

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a>Elaborare un pagamento fornitore per ottenere un file di pagamento

1. Seguire i passaggi nell'[Appendice 3](#appendix3) di questo argomento per elaborare i pagamenti fornitore.

    ![Elaborazione pagamento fornitore in corso.](./media/er-data-debugger-process-payment.png)

2. Scaricare e salvare il file con estensione zip nel computer locale.
3. Estrarre il file di pagamento **ISO20022 Credit transfer.xml** dal file con estensione zip.
4. Aprire il file di pagamento estratto utilizzando il visualizzatore di file XML.

    Nel file di pagamento il codice IBAN (International Bank Account Number) del conto bancario del fornitore non contiene spazi. Differisce pertanto dal valore [immesso](#enteredIBANcode) sulla pagina **Conti bancari**.

    ![Codice IBAN senza spazi.](./media/er-data-debugger-payment-file.png)

    È possibile utilizzare il debugger dell'origine dati ER per sapere quale componente della soluzione ER viene utilizzato per troncare gli spazi nel codice IBAN.

## <a name="turn-on-data-source-debugging"></a>Attivare il debug dell'origine dati

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Impostare l'opzione **Abilita debug dei dati all'esecuzione del formato** su **Sì**.

    > [!NOTE]
    > Questo parametro è specifico dell'utente e dell'azienda.

    ![Finestra di dialogo Parametri dell'utente.](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a>Elaborare un pagamento fornitore per il debug

1. Seguire i passaggi nell'[Appendice 3](#appendix3) di questo argomento per elaborare i pagamenti fornitore.
2. Nella finestra di messaggio selezionare **Sì** per confermare che si desidera interrompere l'elaborazione dei pagamenti del fornitore e avviare invece il debug dell'origine dati nella pagina **Debug origini dati**.

    ![Finestra di messaggio di conferma.](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a>Eseguire il debug delle origini dati utilizzate durante l'elaborazione dei pagamenti

### <a name="debug-the-model-mapping"></a>Debug del mapping di modello

1. Nella pagina **Debug origini dati** nel riquadro azioni selezionare **Mapping modello** per avviare il debug da questo componente ER.
2. Nel riquadro dell'origine dati a sinistra selezionare l'origine dati **\$notSentTransactions**, quindi selezionare **Leggi tutti i record**.

    Puoi selezionare **Leggi 1 record**, **Leggi 10 record**, **Leggi 100 record** o **Leggi tutti i record** per forzare il numero appropriato di record da leggere dall'origine dati selezionata. In questo modo, è possibile simulare l'accesso all'origine dati dal formato ER in esecuzione.

3. Nel riquadro dei dati a destra selezionare **Espandi tutto**.

    L'origine dati selezionata del tipo **Elenco di record** contiene un singolo record.

4. Espandere l'origine dati **\$notSentTransactions** e selezionare metodo **vendBankAccountInTransactionCompany()** annidato.
5. Espandere il metodo **vendBankAccountInTransactionCompany()** e selezionare il campo **IBAN** annidato.
6. Selezionare **Ottieni valore**.

    Puoi selezionare **Ottieni valore** per forzare la lettura del valore di un campo selezionato dell'origine dati selezionata. In questo modo, è possibile simulare l'accesso a questo campo dal formato ER in esecuzione.

7. Selezionare **Espandi tutto**.

    ![Valore del campo IBAN nel mapping di modello.](./media/er-data-debugger-debugging-model-mapping.png)

    Il mapping di modello non è responsabile per gli spazi troncati, perché il codice IBAN restituito per il conto bancario fornitore include spazi. È pertanto necessario continuare il debug dell'origine dati.

### <a name="debug-the-format-mapping"></a>Eseguire il debug del mapping di formato

1. Nella pagina **Debug origini dati** nel riquadro azioni selezionare **Mapping formato** per continuare il debug da questo componente ER.
2. Selezionare l'origine dati **\$PaymentByDebtor**, quindi selezionare **Leggi tutti i record**.
3. Espandere **\$PaymentByDebtor**.
4. Espandere **\$PaymentByDebtor.Lines**, quindi selezionare **Leggi tutti i record**.
5. Espandere **\$PaymentByDebtor.Lines.CreditorAccount**.
6. Espandere **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, quindi selezionare **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.
7. Selezionare **Ottieni valore**.
8. Selezionare **Espandi tutto**.

    ![Valore del campo IBAN nel mapping di formato.](./media/er-data-debugger-debugging-format-mapping.png)

    Le origini dati del mapping di formato non sono responsabili per gli spazi troncati, perché il codice IBAN restituito per il conto bancario fornitore include spazi. È pertanto necessario continuare il debug dell'origine dati.

### <a name="debug-the-format"></a>Eseguire il debug del formato

1. Nella pagina **Debug origini dati** nel riquadro azioni selezionare **Formato** per continuare il debug da questo componente ER.
2. Espandere gli elementi di formato per selezionare **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, quindi selezionare **Leggi tutti i record**.
3. Espandere gli elementi di formato per selezionare **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, quindi selezionare **Leggi tutti i record**.
4. Espandere gli elementi di formato per selezionare **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, quindi selezionare **Ottieni valore**.
5. Selezionare **Espandi tutto**.

    ![Valore del campo IBAN nel formato.](./media/er-data-debugger-debugging-format.png)

   L'associazione del formato non è responsabile per gli spazi troncati, perché il codice IBAN restituito per il conto bancario fornitore include spazi. Quindi, l'elemento **BankIBAN** viene configurato per utilizzare una trasformazione di formato che tronca gli spazi.

6. Chiudere il debugger dell'origine dati.

### <a name="review-the-format-transformations"></a>Esaminare le trasformazioni di formato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni** selezionare **Modello di pagamento** \> **Bonifico ISO20022**.
3. Selezionare **Progettazione**, quindi espandere gli elementi per selezionare **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.

    ![Elemento BankIBAN nella pagina Progettazione formati.](./media/er-data-debugger-referred-transformation.png)

    L'elemento **BankIBAN** è configurato per utilizzare la trasformazione per **non rimuovere gli elementi alfanumerici**.

4. Selezionare la scheda **Trasformazioni**.

    ![Scheda Trasformazioni per l'elemento BankIBAN.](./media/er-data-debugger-transformation.png)

    La trasformazione per **non rimuovere gli elementi alfanumerici** è configurata per utilizzare un'espressione che tronca gli spazi dalla stringa di testo specificata.

## <a name="start-to-debug-in-the-operation-designer"></a>Avviare il debug nella progettazione dell'operazione

Quando si configura una versione bozza del formato ER che può essere eseguita direttamente dalla progettazione dell'operazione, è possibile accedere al debugger dell'origine dati selezionando **Avvia debug** nel riquadro azioni.

![Pulsante Avvia debug nella pagina Progettazione formati.](./media/er-data-debugger-run-from-designer.png)

Il mapping di formato e i componenti di formato del formato ER in fase di modifica sono disponibili per il debug.

## <a name="start-to-debug-in-the-model-mapping-designer"></a>Avviare il debug in Progettazione mapping modello

Quando si configura un mapping di modello ER che può essere eseguito dalla pagina **Mapping modello**, è possibile accedere al debugger dell'origine dati selezionando **Avvia debug** nel riquadro azioni.

![Pulsante Avvia debug nella pagina Progettazione mapping modello.](./media/er-data-debugger-run-from-designer-mapping.png)

Il componente di mapping del modello ER in fase di modifica è disponibile per il debug.

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a>Appendice 1. Ottenere una soluzione ER

### <a name="download-an-er-solution"></a>Download di una soluzione ER

Se si desidera utilizzare una soluzione ER per generare un file di pagamento elettronico per un pagamento fornitore elaborato, è possibile [scaricare](download-electronic-reporting-configuration-lcs.md) il formato di pagamento ER **Bonifico ISO20022** disponibile nella raccolta Risorse condivise in Microsoft Dynamics Lifecycle Services (LCS) o nel repository globale.

![Importazione del formato di pagamento ER nella pagina Archivio di configurazioni.](./media/er-data-debugger-import-from-repo.png)

Oltre al formato ER selezionato, le seguenti [configurazioni](general-electronic-reporting.md#Configuration) devono essere importate automaticamente nell'istanza di Microsoft Dynamics 365 Finance come parte della soluzione ER **Bonifico ISO20022**:

- **Modello di pagamento** - [Configurazione del modello dati ER](general-electronic-reporting.md#DataModelComponent)
- **Bonifico ISO20022** - [Configurazione di formato ER](general-electronic-reporting.md#FormatComponentOutbound)
- **Mapping di modello di pagamento 1611** - [Configurazione del mapping di modello ER](general-electronic-reporting.md#ModelMappingComponent)
- **Mapping di modello di pagamento alla destinazione ISO20022** - Configurazione del mapping di modello ER

È possibile trovare queste configurazioni nella pagina **Configurazioni** del framework ER (**Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**).

![Configurazioni importate nella pagina Configurazioni.](./media/er-data-debugger-configurations.png)

Se una delle configurazioni precedentemente elencate non è presente nella struttura delle configurazioni, è necessario scaricarla manualmente dalla libreria di risorse condivise LCS nello stesso modo in cui è stato scaricato il formato di pagamento ER **Bonifico ISO20022**.

### <a name="analyze-the-downloaded-er-solution"></a>Analizzare la soluzione ER scaricata

#### <a name="review-the-model-mapping"></a>Esaminare il mapping di modello

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Selezionare **Modello di pagamento** \> **Mapping di modello di pagamento 1611**.
3. Selezionare **Progettazione**.
4. Selezionare il record di mapping **Mapping modello di pagamento bonifico ISO20022**.
5. Selezionare **Progettazione**, quindi rivedere il mapping di modello aperto.

    Il campo **Pagamenti** del modello di dati è associato all'origine dati **\$notSentTransactions** che restituisce l'elenco delle righe di pagamento fornitore in fase di elaborazione.

    ![Campo Pagamenti nella pagina Progettazione mapping modello.](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a>Esaminare il mapping di formato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Selezionare **Modello di pagamento** \> **Bonifico ISO20022**.
3. Selezionare **Progettazione**.
4. Nella scheda **Mapping**, verificare il mapping di formato aperto.

    L'elemento **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** del file **ISO20022CTReports** \> **XMLHeader** è associato all'origine dati **\$PaymentByDebtor** configurata per raggruppare i record dl campo **Pagamenti** del modello dati.

    ![Elemento PmtInf nella pagina Progettazione formati.](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a>Esaminare il formato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Selezionare **Modello di pagamento** \> **Bonifico ISO20022**.
3. Selezionare **Progettazione**, quindi rivedere il formato aperto.

    L'elemento di formato in **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** è configurato per l'immissione del codice IBAN del conto fornitore nel file di pagamento.

    ![Elemento BankIBAN nella pagina Progettazione formati.](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a>Appendice 2. Configurare la contabilità fornitori

### <a name="modify-a-vendor-property"></a>Modificare una proprietà fornitore

1. Andare a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori**.
2. Selezionare **DE-01002** e quindi, nel riquadro azioni, scheda **Fornitore**, gruppo **Impostazione** selezionare **Conti bancari**.
3. Nella Scheda dettaglio **Identificazione**, nel campo **IBAN** <a name="enteredIBANcode"></a>immettere **GB33 BUKB 2020 1555 5555 55**.
4. Selezionare **Salva**.

![Campo IBAN impostato nella pagina Conti bancari fornitore.](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a>Impostare un metodo di pagamento

1. Andare a **Contabilità fornitori** \> **Impostazione pagamenti** \> **Metodi di pagamento**.
2. Selezionare il metodo di pagamento **SEPA CT**.
3. Nella Scheda dettaglio **Formati file** nella sezione **Formati file** impostare l'opzione **Formato esportazione elettronica generica** su **Sì**.
4. Nel campo **Esporta configurazione formato** selezionare il formato ER **Bonifico ISO20022**.
5. Selezionare **Salva**.

![Impostazioni Formati file per la pagina Metodi di pagamento.](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a>Aggiungere un pagamento fornitore

1. Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.
2. Aggiungere un nuovo giornale di registrazione pagamenti.
3. Selezionare **Righe** e aggiungere una nuova riga di pagamento.
4. Nel campo **Conto** selezionare il fornitore **DE-01002**.
5. Nel campo **Dare** immettere un valore.
6. Nel campo **Metodo di pagamento** selezionare **SEPA CT**.
7. Selezionare **Salva**.

![Pagamento del fornitore aggiunto nella pagina Pagamenti fornitore.](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a>Appendice 3. Elaborare un pagamento fornitore

1. Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.
2. Nella pagina **Giornale di registrazione pagamenti fornitore** selezionare il giornale di registrazione pagamenti creato in precedenza, quindi selezionare **Righe**.
3. Selezionare la riga di pagamento, quindi selezionare **Stato pagamento** \> **Nessuno**.
4. Selezionare **Genera pagamenti**.
5. Nel campo **Metodo di pagamento** selezionare **SEPA CT**.
6. Nel campo **Conto bancario** selezionare **DEMF OPER**.
7. Nella finestra di dialogo **Genera pagamenti** selezionare **OK**.
8. Nella finestra di dialogo **Parametri per la creazione di report elettronici** selezionare **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]