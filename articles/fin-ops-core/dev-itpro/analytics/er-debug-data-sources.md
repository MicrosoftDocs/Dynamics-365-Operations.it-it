---
title: Eseguire il debug delle origini dati di un formato ER eseguito per analizzare il flusso e la trasformazione dei dati
description: Questo argomento spiega come eseguire il debug delle origini dati di un formato ER eseguito per comprendere meglio il flusso e la trasformazione dei dati configurati.
author: NickSelin
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 5b51c4beac0ddf1e2b53fe300e10c0f608e5d1e1
ms.sourcegitcommit: 153bb33722c02501bf7bcfd56ac887602d5dfbd3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "3318668"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a><span data-ttu-id="98de8-103">Eseguire il debug delle origini dati di un formato ER eseguito per analizzare il flusso e la trasformazione dei dati</span><span class="sxs-lookup"><span data-stu-id="98de8-103">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

<span data-ttu-id="98de8-104">Quando si [configura](tasks/er-format-configuration-2016-11.md) una soluzione ER per generare documenti in uscita, si definiscono i metodi utilizzati per acquisire dati dall'applicazione e immetterli nell'output generato.</span><span class="sxs-lookup"><span data-stu-id="98de8-104">When you [configure](tasks/er-format-configuration-2016-11.md) an Electronic reporting (ER) solution to generate outbound documents, you define the methods that are used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="98de8-105">Per rendere più efficiente il supporto del ciclo di vita della soluzione ER, la soluzione dovrebbe essere costituita da un [modello di dati](general-electronic-reporting.md#DataModelComponent) ER e dai relativi componenti di [mapping](general-electronic-reporting.md#ModelMappingComponent), nonché da un [formato](general-electronic-reporting.md#FormatComponentOutbound) ER e dai relativi componenti di mapping, in modo tale che il mapping di modello sia specifico dell'applicazione, mentre gli altri componenti rimangano indipendenti dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98de8-105">To make the life cycle support of the ER solution more efficient, your solution should consist of an ER [data model](general-electronic-reporting.md#DataModelComponent) and its [mapping](general-electronic-reporting.md#ModelMappingComponent) components, and also an ER [format](general-electronic-reporting.md#FormatComponentOutbound) and its mapping components, so that the model mapping is application-specific, whereas other components remain application-agnostic.</span></span> <span data-ttu-id="98de8-106">Diversi componenti ER potrebbero pertanto [influire](general-electronic-reporting.md#FormatComponentOutbound) sul processo di immissione dei dati nell'output generato.</span><span class="sxs-lookup"><span data-stu-id="98de8-106">Therefore, several ER components might [affect](general-electronic-reporting.md#FormatComponentOutbound) the process of entering data in the generated output.</span></span>

<span data-ttu-id="98de8-107">In alcuni casi, i dati dell'output generato hanno un aspetto diverso dagli stessi dati nel database dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98de8-107">Sometimes, the data of the generated output looks different than the same data in the application database.</span></span> <span data-ttu-id="98de8-108">In questi casi, sarà necessario determinare quale componente ER è responsabile della trasformazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="98de8-108">In these cases, you will want to determine which ER component is responsible for the data transformation.</span></span> <span data-ttu-id="98de8-109">La funzionalità di debugger dell'origine dati ER riduce significativamente i tempi e i costi correlati a questa analisi.</span><span class="sxs-lookup"><span data-stu-id="98de8-109">The ER data source debugger feature significantly reduces the time and cost that are involved in this investigation.</span></span> <span data-ttu-id="98de8-110">È possibile interrompere l'esecuzione di un formato ER e aprire l'interfaccia del debugger dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="98de8-110">You can interrupt the execution of an ER format and open the data source debugger interface.</span></span> <span data-ttu-id="98de8-111">È dunque possibile spostarsi sulle origini dati disponibili e selezionare una singola origine di dati per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="98de8-111">There, you can browse the available data sources and select an individual data source for execution.</span></span> <span data-ttu-id="98de8-112">Questa esecuzione manuale simula l'esecuzione dell'origine dati durante l'esecuzione reale di un formato ER.</span><span class="sxs-lookup"><span data-stu-id="98de8-112">This manual execution simulates the execution of the data source during the real run of an ER format.</span></span> <span data-ttu-id="98de8-113">Il risultato è presentato in una pagina in cui è possibile analizzare i dati ricevuti.</span><span class="sxs-lookup"><span data-stu-id="98de8-113">The result is presented on a page where you can analyze the data that is received.</span></span>

<span data-ttu-id="98de8-114">Per attivare la funzionalità di debug dell'origine dati, impostare l'opzione **Abilita debug dei dati all'esecuzione del formato** su **Sì** nei parametri utente ER.</span><span class="sxs-lookup"><span data-stu-id="98de8-114">To turn on the data source debugging feature, set the **Enable data debugging at format run** option to **Yes** in the ER user parameters.</span></span> <span data-ttu-id="98de8-115">È quindi possibile avviare il debug dell'origine dati mentre si esegue un formato ER per generare documenti in uscita.</span><span class="sxs-lookup"><span data-stu-id="98de8-115">You can then start data source debugging while you run an ER format to generate outbound documents.</span></span> <span data-ttu-id="98de8-116">Puoi anche usare l'opzione **Avvia debug** per avviare il debug dell'origine dati per un formato ER configurato nella [progettazione dell'operazione ER](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span><span class="sxs-lookup"><span data-stu-id="98de8-116">You can also use the **Start debugging** option to initiate data source debugging for an ER format that is configured in the [ER Operation designer](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span></span>

<span data-ttu-id="98de8-117">Questo argomento fornisce linee guida per l'avvio del debug dell'origine dati per i formati ER eseguiti.</span><span class="sxs-lookup"><span data-stu-id="98de8-117">This topic provides guidelines for initiating data source debugging for executed ER formats.</span></span> <span data-ttu-id="98de8-118">Spiega come le informazioni possono aiutarti a comprendere il flusso e le trasformazioni dei dati.</span><span class="sxs-lookup"><span data-stu-id="98de8-118">It explains how the information can help you understand the data flow and data transformations.</span></span> <span data-ttu-id="98de8-119">Gli esempi in questo argomento utilizzano il processo aziendale per l'elaborazione dei pagamenti del fornitore.</span><span class="sxs-lookup"><span data-stu-id="98de8-119">The examples in this topic use the business process for vendor payments processing.</span></span>

## <a name="limitations"></a><span data-ttu-id="98de8-120">Limiti</span><span class="sxs-lookup"><span data-stu-id="98de8-120">Limitations</span></span>

<span data-ttu-id="98de8-121">Il debugger dell'origine dati può essere utilizzato per accedere ai dati delle origini dati utilizzati nei formati ER eseguiti per generare documenti in uscita.</span><span class="sxs-lookup"><span data-stu-id="98de8-121">The data source debugger can be used to access the data of data sources that are used in ER formats that are run to generate outbound documents.</span></span> <span data-ttu-id="98de8-122">Non può essere utilizzato per eseguire il debug di origini dati di formati ER progettati per analizzare documenti in entrata.</span><span class="sxs-lookup"><span data-stu-id="98de8-122">It can't be used to debug data sources of ER formats that are designed to parse inbound documents.</span></span>

<span data-ttu-id="98de8-123">Le seguenti impostazioni dei formati ER non sono attualmente accessibili per il debug dell'origine dati:</span><span class="sxs-lookup"><span data-stu-id="98de8-123">The following settings of ER formats aren't currently accessible for data source debugging:</span></span>

- <span data-ttu-id="98de8-124">Trasformazioni di formato</span><span class="sxs-lookup"><span data-stu-id="98de8-124">Format transformations</span></span>
- <span data-ttu-id="98de8-125">Regole di convalida mapping e formato</span><span class="sxs-lookup"><span data-stu-id="98de8-125">Format and mapping validation rules</span></span>
- <span data-ttu-id="98de8-126">Espressioni di abilitazione</span><span class="sxs-lookup"><span data-stu-id="98de8-126">Enabling expressions</span></span>
- <span data-ttu-id="98de8-127">Dettagli sulla raccolta dei dati in memoria</span><span class="sxs-lookup"><span data-stu-id="98de8-127">Details of in-memory data collection</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98de8-128">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="98de8-128">Prerequisites</span></span>

- <span data-ttu-id="98de8-129">Per completare gli esempi in questo argomento, è necessario disporre dell'accesso ai seguenti [ruoli](../sysadmin/tasks/assign-users-security-roles.md):</span><span class="sxs-lookup"><span data-stu-id="98de8-129">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="98de8-130">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="98de8-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="98de8-131">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="98de8-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="98de8-132">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="98de8-132">System administrator</span></span>

- <span data-ttu-id="98de8-133">La società deve essere impostata su **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="98de8-133">The company must be set to **DEMF**.</span></span>

- <span data-ttu-id="98de8-134">Seguire i passaggi nell'[Appendice 1](#appendix1) di questo argomento per scaricare i componenti della soluzione Microsoft ER richiesti per elaborare i pagamenti del fornitore.</span><span class="sxs-lookup"><span data-stu-id="98de8-134">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the Microsoft ER solution that are required to process vendor payments.</span></span>
- <span data-ttu-id="98de8-135">Seguire i passaggi nell'[Appendice 2](#appendix2) di questo argomento per preparare la contabilità fornitori per l'elaborazione dei pagamenti dei fornitori utilizzando la soluzione ER che verrà scaricata.</span><span class="sxs-lookup"><span data-stu-id="98de8-135">Follow the steps in [Appendix 2](#appendix2) of this topic to prepare Accounts payable for vendor payment processing by using the ER solution that you will download.</span></span>

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a><span data-ttu-id="98de8-136">Elaborare un pagamento fornitore per ottenere un file di pagamento</span><span class="sxs-lookup"><span data-stu-id="98de8-136">Process a vendor payment to get a payment file</span></span>

1. <span data-ttu-id="98de8-137">Seguire i passaggi nell'[Appendice 3](#appendix3) di questo argomento per elaborare i pagamenti fornitore.</span><span class="sxs-lookup"><span data-stu-id="98de8-137">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>

    ![Elaborazione pagamento fornitore in corso](./media/er-data-debugger-process-payment.png)

2. <span data-ttu-id="98de8-139">Scaricare e salvare il file con estensione zip nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="98de8-139">Download and save the zip file to your local computer.</span></span>
3. <span data-ttu-id="98de8-140">Estrarre il file di pagamento **ISO20022 Credit transfer.xml** dal file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="98de8-140">Extract the **ISO20022 Credit transfer.xml** payment file from the zip file.</span></span>
4. <span data-ttu-id="98de8-141">Aprire il file di pagamento estratto utilizzando il visualizzatore di file XML.</span><span class="sxs-lookup"><span data-stu-id="98de8-141">Open the extracted payment file by using the XML file viewer.</span></span>

    <span data-ttu-id="98de8-142">Nel file di pagamento il codice IBAN (International Bank Account Number) del conto bancario del fornitore non contiene spazi.</span><span class="sxs-lookup"><span data-stu-id="98de8-142">In the payment file, the International Bank Account Number (IBAN) code of the vendor bank account contains no spaces.</span></span> <span data-ttu-id="98de8-143">Differisce pertanto dal valore [immesso](#enteredIBANcode) sulla pagina **Conti bancari**.</span><span class="sxs-lookup"><span data-stu-id="98de8-143">Therefore, it differs from the value that was [entered](#enteredIBANcode) on the **Bank accounts** page.</span></span>

    ![Codice IBAN senza spazi](./media/er-data-debugger-payment-file.png)

    <span data-ttu-id="98de8-145">È possibile utilizzare il debugger dell'origine dati ER per sapere quale componente della soluzione ER viene utilizzato per troncare gli spazi nel codice IBAN.</span><span class="sxs-lookup"><span data-stu-id="98de8-145">You can use the ER data source debugger to learn which component of the ER solution is used to truncate spaces in the IBAN code.</span></span>

## <a name="turn-on-data-source-debugging"></a><span data-ttu-id="98de8-146">Attivare il debug dell'origine dati</span><span class="sxs-lookup"><span data-stu-id="98de8-146">Turn on data source debugging</span></span>

1. <span data-ttu-id="98de8-147">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="98de8-147">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="98de8-148">Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.</span><span class="sxs-lookup"><span data-stu-id="98de8-148">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="98de8-149">Impostare l'opzione **Abilita debug dei dati all'esecuzione del formato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="98de8-149">Set the **Enable data debugging at format run** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98de8-150">Questo parametro è specifico dell'utente e dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="98de8-150">This parameter is user-specific and company-specific.</span></span>

    ![Finestra di dialogo Parametri dell'utente](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a><span data-ttu-id="98de8-152">Elaborare un pagamento fornitore per il debug</span><span class="sxs-lookup"><span data-stu-id="98de8-152">Process a vendor payment for debugging</span></span>

1. <span data-ttu-id="98de8-153">Seguire i passaggi nell'[Appendice 3](#appendix3) di questo argomento per elaborare i pagamenti fornitore.</span><span class="sxs-lookup"><span data-stu-id="98de8-153">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>
2. <span data-ttu-id="98de8-154">Nella finestra di messaggio selezionare **Sì** per confermare che si desidera interrompere l'elaborazione dei pagamenti del fornitore e avviare invece il debug dell'origine dati nella pagina **Debug origini dati**.</span><span class="sxs-lookup"><span data-stu-id="98de8-154">In the message box, select **Yes** to confirm that you want to interrupt vendor payment processing and instead start data source debugging on the **Debug Datasources** page.</span></span>

    ![Finestra di messaggio di conferma](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a><span data-ttu-id="98de8-156">Eseguire il debug delle origini dati utilizzate durante l'elaborazione dei pagamenti</span><span class="sxs-lookup"><span data-stu-id="98de8-156">Debug data sources that are used in payment processing</span></span>

### <a name="debug-the-model-mapping"></a><span data-ttu-id="98de8-157">Debug del mapping di modello</span><span class="sxs-lookup"><span data-stu-id="98de8-157">Debug the model mapping</span></span>

1. <span data-ttu-id="98de8-158">Nella pagina **Debug origini dati** nel riquadro azioni selezionare **Mapping modello** per avviare il debug da questo componente ER.</span><span class="sxs-lookup"><span data-stu-id="98de8-158">On the **Debug Datasources** page, on the Action Pane, select **Model mapping** to start to debug from this ER component.</span></span>
2. <span data-ttu-id="98de8-159">Nel riquadro dell'origine dati a sinistra selezionare l'origine dati **\$notSentTransactions**, quindi selezionare **Leggi tutti i record**.</span><span class="sxs-lookup"><span data-stu-id="98de8-159">In the data source pane on the left, select the **\$notSentTransactions** data source, and then select **Read all records**.</span></span>

    <span data-ttu-id="98de8-160">Puoi selezionare **Leggi 1 record**, **Leggi 10 record**, **Leggi 100 record** o **Leggi tutti i record** per forzare il numero appropriato di record da leggere dall'origine dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="98de8-160">You can select **Read 1 record**, **Read 10 records**, **Read 100 records**, or **Read all records** to force the appropriate number of records to be read from the selected data source.</span></span> <span data-ttu-id="98de8-161">In questo modo, è possibile simulare l'accesso all'origine dati dal formato ER in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="98de8-161">In this way, you can simulate access to the data source from the running ER format.</span></span>

3. <span data-ttu-id="98de8-162">Nel riquadro dei dati a destra selezionare **Espandi tutto**.</span><span class="sxs-lookup"><span data-stu-id="98de8-162">In the data pane on the right, select **Expand all**.</span></span>

    <span data-ttu-id="98de8-163">L'origine dati selezionata del tipo **Elenco di record** contiene un singolo record.</span><span class="sxs-lookup"><span data-stu-id="98de8-163">You can see that the selected data source of the **Record list** type contains a single record.</span></span>

4. <span data-ttu-id="98de8-164">Espandere l'origine dati **\$notSentTransactions** e selezionare metodo **vendBankAccountInTransactionCompany()** annidato.</span><span class="sxs-lookup"><span data-stu-id="98de8-164">Expand the **\$notSentTransactions** data source, and select the nested **vendBankAccountInTransactionCompany()** method.</span></span>
5. <span data-ttu-id="98de8-165">Espandere il metodo **vendBankAccountInTransactionCompany()** e selezionare il campo **IBAN** annidato.</span><span class="sxs-lookup"><span data-stu-id="98de8-165">Expand the **vendBankAccountInTransactionCompany()** method, and select the nested **IBAN** field.</span></span>
6. <span data-ttu-id="98de8-166">Selezionare **Ottieni valore**.</span><span class="sxs-lookup"><span data-stu-id="98de8-166">Select **Get value**.</span></span>

    <span data-ttu-id="98de8-167">Puoi selezionare **Ottieni valore** per forzare la lettura del valore di un campo selezionato dell'origine dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="98de8-167">You can select **Get value** to force the value of a selected field of the selected data source to be read.</span></span> <span data-ttu-id="98de8-168">In questo modo, è possibile simulare l'accesso a questo campo dal formato ER in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="98de8-168">In this way, you can simulate access to this field from the running ER format.</span></span>

7. <span data-ttu-id="98de8-169">Selezionare **Espandi tutto**.</span><span class="sxs-lookup"><span data-stu-id="98de8-169">Select **Expand all**.</span></span>

    ![Valore del campo IBAN nel mapping di modello](./media/er-data-debugger-debugging-model-mapping.png)

    <span data-ttu-id="98de8-171">Il mapping di modello non è responsabile per gli spazi troncati, perché il codice IBAN restituito per il conto bancario fornitore include spazi.</span><span class="sxs-lookup"><span data-stu-id="98de8-171">As you can see, the model mapping isn't responsible for the truncated spaces, because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="98de8-172">È pertanto necessario continuare il debug dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="98de8-172">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format-mapping"></a><span data-ttu-id="98de8-173">Eseguire il debug del mapping di formato</span><span class="sxs-lookup"><span data-stu-id="98de8-173">Debug the format mapping</span></span>

1. <span data-ttu-id="98de8-174">Nella pagina **Debug origini dati** nel riquadro azioni selezionare **Mapping formato** per continuare il debug da questo componente ER.</span><span class="sxs-lookup"><span data-stu-id="98de8-174">On the **Debug Datasources** page, on the Action Pane, select **Format mapping** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="98de8-175">Selezionare l'origine dati **\$PaymentByDebtor**, quindi selezionare **Leggi tutti i record**.</span><span class="sxs-lookup"><span data-stu-id="98de8-175">Select the **\$PaymentByDebtor** data source, and then select **Read all records**.</span></span>
3. <span data-ttu-id="98de8-176">Espandere **\$PaymentByDebtor**.</span><span class="sxs-lookup"><span data-stu-id="98de8-176">Expand **\$PaymentByDebtor**.</span></span>
4. <span data-ttu-id="98de8-177">Espandere **\$PaymentByDebtor.Lines**, quindi selezionare **Leggi tutti i record**.</span><span class="sxs-lookup"><span data-stu-id="98de8-177">Expand **\$PaymentByDebtor.Lines**, and then select **Read all records**.</span></span>
5. <span data-ttu-id="98de8-178">Espandere **\$PaymentByDebtor.Lines.CreditorAccount**.</span><span class="sxs-lookup"><span data-stu-id="98de8-178">Expand **\$PaymentByDebtor.Lines.CreditorAccount**.</span></span>
6. <span data-ttu-id="98de8-179">Espandere **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, quindi selezionare **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span><span class="sxs-lookup"><span data-stu-id="98de8-179">Expand **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, and then select **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span></span>
7. <span data-ttu-id="98de8-180">Selezionare **Ottieni valore**.</span><span class="sxs-lookup"><span data-stu-id="98de8-180">Select **Get value**.</span></span>
8. <span data-ttu-id="98de8-181">Selezionare **Espandi tutto**.</span><span class="sxs-lookup"><span data-stu-id="98de8-181">Select **Expand all**.</span></span>

    ![Valore del campo IBAN nel mapping di formato](./media/er-data-debugger-debugging-format-mapping.png)

    <span data-ttu-id="98de8-183">Le origini dati del mapping di formato non sono responsabili per gli spazi troncati, perché il codice IBAN restituito per il conto bancario fornitore include spazi.</span><span class="sxs-lookup"><span data-stu-id="98de8-183">As you can see, the data sources of the format mapping aren't responsible for the truncated spaces, because the IBAN code that they return for the vendor bank account includes spaces.</span></span> <span data-ttu-id="98de8-184">È pertanto necessario continuare il debug dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="98de8-184">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format"></a><span data-ttu-id="98de8-185">Eseguire il debug del formato</span><span class="sxs-lookup"><span data-stu-id="98de8-185">Debug the format</span></span>

1. <span data-ttu-id="98de8-186">Nella pagina **Debug origini dati** nel riquadro azioni selezionare **Formato** per continuare il debug da questo componente ER.</span><span class="sxs-lookup"><span data-stu-id="98de8-186">On the **Debug Datasources** page, on the Action Pane, select **Format** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="98de8-187">Espandere gli elementi di formato per selezionare **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, quindi selezionare **Leggi tutti i record**.</span><span class="sxs-lookup"><span data-stu-id="98de8-187">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, and then select **Read all records**.</span></span>
3. <span data-ttu-id="98de8-188">Espandere gli elementi di formato per selezionare **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, quindi selezionare **Leggi tutti i record**.</span><span class="sxs-lookup"><span data-stu-id="98de8-188">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, and then select **Read all records**.</span></span>
4. <span data-ttu-id="98de8-189">Espandere gli elementi di formato per selezionare **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, quindi selezionare **Ottieni valore**.</span><span class="sxs-lookup"><span data-stu-id="98de8-189">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, and then select **Get value**.</span></span>
5. <span data-ttu-id="98de8-190">Selezionare **Espandi tutto**.</span><span class="sxs-lookup"><span data-stu-id="98de8-190">Select **Expand all**.</span></span>

    ![Valore del campo IBAN nel formato](./media/er-data-debugger-debugging-format.png)

   <span data-ttu-id="98de8-192">L'associazione del formato non è responsabile per gli spazi troncati, perché il codice IBAN restituito per il conto bancario fornitore include spazi.</span><span class="sxs-lookup"><span data-stu-id="98de8-192">As you can see, the format binding isn't responsible for the truncated spaces because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="98de8-193">Quindi, l'elemento **BankIBAN** viene configurato per utilizzare una trasformazione di formato che tronca gli spazi.</span><span class="sxs-lookup"><span data-stu-id="98de8-193">Therefore, the **BankIBAN** element is configured to use a format transformation that truncates spaces.</span></span>

6. <span data-ttu-id="98de8-194">Chiudere il debugger dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="98de8-194">Close the data source debugger.</span></span>

### <a name="review-the-format-transformations"></a><span data-ttu-id="98de8-195">Esaminare le trasformazioni di formato</span><span class="sxs-lookup"><span data-stu-id="98de8-195">Review the format transformations</span></span>

1. <span data-ttu-id="98de8-196">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="98de8-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="98de8-197">Nella pagina **Configurazioni** selezionare **Modello di pagamento** \> **Bonifico ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="98de8-197">On the **Configurations** page, select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="98de8-198">Selezionare **Progettazione**, quindi espandere gli elementi per selezionare **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span><span class="sxs-lookup"><span data-stu-id="98de8-198">Select **Designer**, and then expand the elements to select **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span></span>

    ![Elemento BankIBAN nella pagina Progettazione formati](./media/er-data-debugger-referred-transformation.png)

    <span data-ttu-id="98de8-200">L'elemento **BankIBAN** è configurato per utilizzare la trasformazione per **non rimuovere gli elementi alfanumerici**.</span><span class="sxs-lookup"><span data-stu-id="98de8-200">As you can see, the **BankIBAN** element is configured to use the **remove not alphanumeric** transformation.</span></span>

4. <span data-ttu-id="98de8-201">Selezionare la scheda **Trasformazioni**.</span><span class="sxs-lookup"><span data-stu-id="98de8-201">Select the **Transformations** tab.</span></span>

    ![Scheda Trasformazioni per l'elemento BankIBAN](./media/er-data-debugger-transformation.png)

    <span data-ttu-id="98de8-203">La trasformazione per **non rimuovere gli elementi alfanumerici** è configurata per utilizzare un'espressione che tronca gli spazi dalla stringa di testo specificata.</span><span class="sxs-lookup"><span data-stu-id="98de8-203">As you can see, the **remove not alphanumeric** transformation is configured to use an expression that truncates spaces from the text string that is provided.</span></span>

## <a name="start-to-debug-in-the-operation-designer"></a><span data-ttu-id="98de8-204">Avviare il debug nella progettazione dell'operazione</span><span class="sxs-lookup"><span data-stu-id="98de8-204">Start to debug in the Operation designer</span></span>

<span data-ttu-id="98de8-205">Quando si configura una versione bozza del formato ER che può essere eseguita direttamente dalla progettazione dell'operazione, è possibile accedere al debugger dell'origine dati selezionando **Avvia debug** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="98de8-205">When you configure a draft version of the ER format that can be run directly from the Operation designer, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Pulsante Avvia debug nella pagina Progettazione formati](./media/er-data-debugger-run-from-designer.png)

<span data-ttu-id="98de8-207">Il mapping di formato e i componenti di formato del formato ER in fase di modifica sono disponibili per il debug.</span><span class="sxs-lookup"><span data-stu-id="98de8-207">The format mapping and format components of the ER format that is being edited are available for debugging.</span></span>

## <a name="start-to-debug-in-the-model-mapping-designer"></a><span data-ttu-id="98de8-208">Avviare il debug in Progettazione mapping modello</span><span class="sxs-lookup"><span data-stu-id="98de8-208">Start to debug in the Model mapping designer</span></span>

<span data-ttu-id="98de8-209">Quando si configura un mapping di modello ER che può essere eseguito dalla pagina **Mapping modello**, è possibile accedere al debugger dell'origine dati selezionando **Avvia debug** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="98de8-209">When you configure an ER model mapping that can be run from the **Model mapping** page, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Pulsante Avvia debug nella pagina Progettazione mapping modello](./media/er-data-debugger-run-from-designer-mapping.png)

<span data-ttu-id="98de8-211">Il componente di mapping del modello ER in fase di modifica è disponibile per il debug.</span><span class="sxs-lookup"><span data-stu-id="98de8-211">The model mapping component of the ER mapping that is being edited is available for debugging.</span></span>

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a><span data-ttu-id="98de8-212">Appendice 1. Ottenere una soluzione ER</span><span class="sxs-lookup"><span data-stu-id="98de8-212">Appendix 1: Get an ER solution</span></span>

### <a name="download-an-er-solution"></a><span data-ttu-id="98de8-213">Download di una soluzione ER</span><span class="sxs-lookup"><span data-stu-id="98de8-213">Download an ER solution</span></span>

<span data-ttu-id="98de8-214">Se si desidera utilizzare una soluzione ER per generare un file di pagamento elettronico per un pagamento fornitore elaborato, è possibile [scaricare](download-electronic-reporting-configuration-lcs.md) il formato di pagamento ER **Bonifico ISO20022** disponibile nella raccolta Risorse condivise in Microsoft Dynamics Lifecycle Services (LCS) o nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="98de8-214">If you want to use an ER solution to generate an electronic payment file for a vendor payment that is processed, you can [download](download-electronic-reporting-configuration-lcs.md) the **ISO20022 Credit transfer** ER payment format that is available from the Shared asset library in Microsoft Dynamics Lifecycle Services (LCS) or from the Global repository.</span></span>

![Importazione del formato di pagamento ER nella pagina Archivio di configurazioni](./media/er-data-debugger-import-from-repo.png)

<span data-ttu-id="98de8-216">Oltre al formato ER selezionato, le seguenti [configurazioni](general-electronic-reporting.md#Configuration) devono essere importate automaticamente nell'istanza di Microsoft Dynamics 365 Finance come parte della soluzione ER **Bonifico ISO20022**:</span><span class="sxs-lookup"><span data-stu-id="98de8-216">In addition to the selected ER format, the following [configurations](general-electronic-reporting.md#Configuration) must be automatically imported into your Microsoft Dynamics 365 Finance instance as part of the **ISO20022 Credit transfer** ER solution:</span></span>

- <span data-ttu-id="98de8-217">**Modello di pagamento** - [Configurazione del modello dati ER](general-electronic-reporting.md#DataModelComponent)</span><span class="sxs-lookup"><span data-stu-id="98de8-217">**Payment model** [ER data model configuration](general-electronic-reporting.md#DataModelComponent)</span></span>
- <span data-ttu-id="98de8-218">**Bonifico ISO20022** - [Configurazione di formato ER](general-electronic-reporting.md#FormatComponentOutbound)</span><span class="sxs-lookup"><span data-stu-id="98de8-218">**ISO20022 Credit transfer** [ER format configuration](general-electronic-reporting.md#FormatComponentOutbound)</span></span>
- <span data-ttu-id="98de8-219">**Mapping di modello di pagamento 1611** - [Configurazione del mapping di modello ER](general-electronic-reporting.md#ModelMappingComponent)</span><span class="sxs-lookup"><span data-stu-id="98de8-219">**Payment model mapping 1611** [ER model mapping configuration](general-electronic-reporting.md#ModelMappingComponent)</span></span>
- <span data-ttu-id="98de8-220">**Mapping di modello di pagamento alla destinazione ISO20022** - Configurazione del mapping di modello ER</span><span class="sxs-lookup"><span data-stu-id="98de8-220">**Payment model mapping to destination ISO20022** ER model mapping configuration</span></span>

<span data-ttu-id="98de8-221">È possibile trovare queste configurazioni nella pagina **Configurazioni** del framework ER (**Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**).</span><span class="sxs-lookup"><span data-stu-id="98de8-221">You can find these configurations on the **Configurations** page of the ER framework (**Organization administration** \> **Electronic reporting** \> **Configurations**).</span></span>

![Configurazioni importate nella pagina Configurazioni](./media/er-data-debugger-configurations.png)

<span data-ttu-id="98de8-223">Se una delle configurazioni precedentemente elencate non è presente nella struttura delle configurazioni, è necessario scaricarla manualmente dalla libreria di risorse condivise LCS nello stesso modo in cui è stato scaricato il formato di pagamento ER **Bonifico ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="98de8-223">If any of the previously listed configurations are missing in the configuration tree, you must manually download them from the LCS Shared asset library in the same way that you downloaded the **ISO20022 Credit transfer** ER payment format.</span></span>

### <a name="analyze-the-downloaded-er-solution"></a><span data-ttu-id="98de8-224">Analizzare la soluzione ER scaricata</span><span class="sxs-lookup"><span data-stu-id="98de8-224">Analyze the downloaded ER solution</span></span>

#### <a name="review-the-model-mapping"></a><span data-ttu-id="98de8-225">Esaminare il mapping di modello</span><span class="sxs-lookup"><span data-stu-id="98de8-225">Review the model mapping</span></span>

1. <span data-ttu-id="98de8-226">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="98de8-226">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="98de8-227">Selezionare **Modello di pagamento** \> **Mapping di modello di pagamento 1611**.</span><span class="sxs-lookup"><span data-stu-id="98de8-227">Select **Payment model** \> **Payment model mapping 1611**.</span></span>
3. <span data-ttu-id="98de8-228">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="98de8-228">Select **Designer**.</span></span>
4. <span data-ttu-id="98de8-229">Selezionare il record di mapping **Mapping modello di pagamento bonifico ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="98de8-229">Select the **Payment model mapping ISO20022 CT** mapping record.</span></span>
5. <span data-ttu-id="98de8-230">Selezionare **Progettazione**, quindi rivedere il mapping di modello aperto.</span><span class="sxs-lookup"><span data-stu-id="98de8-230">Select **Designer**, and then review the model mapping that is opened.</span></span>

    <span data-ttu-id="98de8-231">Il campo **Pagamenti** del modello di dati è associato all'origine dati **\$notSentTransactions** che restituisce l'elenco delle righe di pagamento fornitore in fase di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="98de8-231">Notice that the **Payments** field of the data model is bound to the **\$notSentTransactions** data source that returns the list of vendor payment lines that are being processed.</span></span>

    ![Campo Pagamenti nella pagina Progettazione mapping modello](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a><span data-ttu-id="98de8-233">Esaminare il mapping di formato</span><span class="sxs-lookup"><span data-stu-id="98de8-233">Review the format mapping</span></span>

1. <span data-ttu-id="98de8-234">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="98de8-234">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="98de8-235">Selezionare **Modello di pagamento** \> **Bonifico ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="98de8-235">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="98de8-236">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="98de8-236">Select **Designer**.</span></span>
4. <span data-ttu-id="98de8-237">Nella scheda **Mapping**, verificare il mapping di formato aperto.</span><span class="sxs-lookup"><span data-stu-id="98de8-237">On the **Mapping** tab, review the format mapping that is opened.</span></span>

    <span data-ttu-id="98de8-238">L'elemento **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** del file **ISO20022CTReports** \> **XMLHeader** è associato all'origine dati **\$PaymentByDebtor** configurata per raggruppare i record dl campo **Pagamenti** del modello dati.</span><span class="sxs-lookup"><span data-stu-id="98de8-238">Notice that the **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** element of the **ISO20022CTReports** \> **XMLHeader** file is bound to the **\$PaymentByDebtor** data source that is configured to group records of the data model's **Payments** field.</span></span>

    ![Elemento PmtInf nella pagina Progettazione formati](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a><span data-ttu-id="98de8-240">Esaminare il formato</span><span class="sxs-lookup"><span data-stu-id="98de8-240">Review the format</span></span>

1. <span data-ttu-id="98de8-241">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="98de8-241">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="98de8-242">Selezionare **Modello di pagamento** \> **Bonifico ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="98de8-242">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="98de8-243">Selezionare **Progettazione**, quindi rivedere il formato aperto.</span><span class="sxs-lookup"><span data-stu-id="98de8-243">Select **Designer**, and then review the format that is opened.</span></span>

    <span data-ttu-id="98de8-244">L'elemento di formato in **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** è configurato per l'immissione del codice IBAN del conto fornitore nel file di pagamento.</span><span class="sxs-lookup"><span data-stu-id="98de8-244">Notice that the format element under **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** is configured to enter the IBAN code of the vendor account in the payment file.</span></span>

    ![Elemento BankIBAN nella pagina Progettazione formati](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a><span data-ttu-id="98de8-246">Appendice 2. Configurare la contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="98de8-246">Appendix 2: Configure Accounts payable</span></span>

### <a name="modify-a-vendor-property"></a><span data-ttu-id="98de8-247">Modificare una proprietà fornitore</span><span class="sxs-lookup"><span data-stu-id="98de8-247">Modify a vendor property</span></span>

1. <span data-ttu-id="98de8-248">Andare a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="98de8-248">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="98de8-249">Selezionare **DE-01002** e quindi, nel riquadro azioni, scheda **Fornitore**, gruppo **Impostazione** selezionare **Conti bancari**.</span><span class="sxs-lookup"><span data-stu-id="98de8-249">Select vendor **DE-01002**, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="98de8-250">Nella Scheda dettaglio **Identificazione**, nel campo **IBAN** <a name="enteredIBANcode"></a>immettere **GB33 BUKB 2020 1555 5555 55**.</span><span class="sxs-lookup"><span data-stu-id="98de8-250">On the **Identification** FastTab, in the **IBAN** field, <a name="enteredIBANcode"></a>enter **GB33 BUKB 2020 1555 5555 55**.</span></span>
4. <span data-ttu-id="98de8-251">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="98de8-251">Select **Save**.</span></span>

![Campo IBAN impostato nella pagina Conti bancari fornitore](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a><span data-ttu-id="98de8-253">Impostare un metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="98de8-253">Set up a method of payment</span></span>

1. <span data-ttu-id="98de8-254">Andare a **Contabilità fornitori** \> **Impostazione pagamenti** \> **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="98de8-254">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="98de8-255">Selezionare il metodo di pagamento **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="98de8-255">Select the **SEPA CT** payment method.</span></span>
3. <span data-ttu-id="98de8-256">Nella Scheda dettaglio **Formati file** nella sezione **Formati file** impostare l'opzione **Formato esportazione elettronica generica** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="98de8-256">On the **File formats** FastTab, in the **File formats** section, set the **Generic electronic Export format** option to **Yes**.</span></span>
4. <span data-ttu-id="98de8-257">Nel campo **Esporta configurazione formato** selezionare il formato ER **Bonifico ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="98de8-257">In the **Export format configuration** field, select the **ISO20022 Credit transfer** ER format.</span></span>
5. <span data-ttu-id="98de8-258">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="98de8-258">Select **Save**.</span></span>

![Impostazioni Formati file per la pagina Metodi di pagamento](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a><span data-ttu-id="98de8-260">Aggiungere un pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="98de8-260">Add a vendor payment</span></span>

1. <span data-ttu-id="98de8-261">Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.</span><span class="sxs-lookup"><span data-stu-id="98de8-261">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="98de8-262">Aggiungere un nuovo giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="98de8-262">Add a new payment journal.</span></span>
3. <span data-ttu-id="98de8-263">Selezionare **Righe** e aggiungere una nuova riga di pagamento.</span><span class="sxs-lookup"><span data-stu-id="98de8-263">Select **Lines**, and add a new payment line.</span></span>
4. <span data-ttu-id="98de8-264">Nel campo **Conto** selezionare il fornitore **DE-01002**.</span><span class="sxs-lookup"><span data-stu-id="98de8-264">In the **Account** field, select vendor **DE-01002**.</span></span>
5. <span data-ttu-id="98de8-265">Nel campo **Dare** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="98de8-265">In the **Debit** field, enter a value.</span></span>
6. <span data-ttu-id="98de8-266">Nel campo **Metodo di pagamento** selezionare **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="98de8-266">In the **Method of payment** field, select **SEPA CT**.</span></span>
7. <span data-ttu-id="98de8-267">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="98de8-267">Select **Save**.</span></span>

![Pagamento del fornitore aggiunto nella pagina Pagamenti fornitore](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a><span data-ttu-id="98de8-269">Appendice 3. Elaborare un pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="98de8-269">Appendix 3: Process a vendor payment</span></span>

1. <span data-ttu-id="98de8-270">Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.</span><span class="sxs-lookup"><span data-stu-id="98de8-270">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="98de8-271">Nella pagina **Giornale di registrazione pagamenti fornitore** selezionare il giornale di registrazione pagamenti creato in precedenza, quindi selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="98de8-271">On the **Vendor payment journal** page, select the payment journal that you previously created, and then select **Lines**.</span></span>
3. <span data-ttu-id="98de8-272">Selezionare la riga di pagamento, quindi selezionare **Stato pagamento** \> **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="98de8-272">Select the payment line, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="98de8-273">Selezionare **Genera pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="98de8-273">Select **Generate payments**.</span></span>
5. <span data-ttu-id="98de8-274">Nel campo **Metodo di pagamento** selezionare **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="98de8-274">In the **Method of payment** field, select **SEPA CT**.</span></span>
6. <span data-ttu-id="98de8-275">Nel campo **Conto bancario** selezionare **DEMF OPER**.</span><span class="sxs-lookup"><span data-stu-id="98de8-275">In the **Bank account** field, select **DEMF OPER**.</span></span>
7. <span data-ttu-id="98de8-276">Nella finestra di dialogo **Genera pagamenti** selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="98de8-276">In the **Generate payments** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="98de8-277">Nella finestra di dialogo **Parametri per la creazione di report elettronici** selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="98de8-277">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
