---
title: Migliorare le prestazioni delle soluzioni ER aggiungendo origini dati CAMPO CALCOLATO parametrizzate
description: Questo argomento spiega come migliorare le prestazioni delle soluzioni di creazione di report elettronici (ER) aggiungendo origini dati CAMPO CALCOLATO parametrizzato.
author: NickSelin
manager: AnnBe
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c63d64774b5b97a562da20655400078ed47c5675
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569227"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a><span data-ttu-id="98c22-103">Migliorare le prestazioni delle soluzioni ER aggiungendo origini dati CAMPO CALCOLATO parametrizzate</span><span class="sxs-lookup"><span data-stu-id="98c22-103">Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98c22-104">Questo argomento spiega come prendere le [tracce delle prestazioni](trace-execution-er-troubleshoot-perf.md) dei formati della [creazione di report elettronici (ER)](general-electronic-reporting.md) che vengono eseguiti e quindi utilizzare le informazioni di tali tracce per migliorare le prestazioni configurando un'origine dati **Campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="98c22-104">This topic explains how you can take [performance traces](trace-execution-er-troubleshoot-perf.md) of [Electronic reporting (ER)](general-electronic-reporting.md) formats that are run, and then use the information from those traces to help improve performance by configuring a parameterized **Calculated field** data source.</span></span>

<span data-ttu-id="98c22-105">Nell'ambito del processo di pianificazione delle configurazioni ER per la generazione di documenti aziendali, si definisce il metodo utilizzato per recuperare i dati dall'applicazione e immetterli nell'output generato.</span><span class="sxs-lookup"><span data-stu-id="98c22-105">As part of the process of designing ER configurations to generate business documents, you define the method that is used to retrieve data from the application and enter it in the generated output.</span></span> <span data-ttu-id="98c22-106">Progettando un'origine dati ER parametrizzata di tipo **Campo calcolato** è possibile ridurre il numero di chiamate al database e ridurre notevolmente il tempo e il costo coinvolti nella raccolta dei dettagli dell'esecuzione del formato ER.</span><span class="sxs-lookup"><span data-stu-id="98c22-106">By designing a parametrized ER data source of the **Calculated field** type, you can reduce the number of database calls, and significantly reduce the time and cost that are involved in collecting the details of ER format execution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98c22-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="98c22-107">Prerequisites</span></span>

- <span data-ttu-id="98c22-108">Per completare gli esempi in questo argomento, è necessario disporre dell'accesso ai seguenti [ruoli](../sysadmin/tasks/assign-users-security-roles.md):</span><span class="sxs-lookup"><span data-stu-id="98c22-108">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="98c22-109">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="98c22-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="98c22-110">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="98c22-110">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="98c22-111">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="98c22-111">System administrator</span></span>

- <span data-ttu-id="98c22-112">La società deve essere impostata su **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="98c22-112">The company must be set to **DEMF**.</span></span>
- <span data-ttu-id="98c22-113">Seguire i passaggi nell'[Appendice 1](#appendix1) di questo argomento per scaricare i componenti della soluzione Microsoft ER di esempio richiesti per completare gli esempi in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="98c22-113">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the sample Microsoft ER solution that is required to complete the examples in this topic.</span></span>
- <span data-ttu-id="98c22-114">Seguire i passaggi nell'[Appendice 2](#appendix2) di questo argomento per configurare il set minimo di parametri ER necessario per utilizzare il framework ER per migliorare le prestazioni della soluzione Microsoft ER di esempio.</span><span class="sxs-lookup"><span data-stu-id="98c22-114">Follow the steps in [Appendix 2](#appendix2) of this topic to configure the minimal set of ER parameters that is required to use the ER framework to help improve the performance of the sample Microsoft ER solution.</span></span>

## <a name="import-the-sample-er-solution"></a><span data-ttu-id="98c22-115">Importare le soluzione ER di esempio</span><span class="sxs-lookup"><span data-stu-id="98c22-115">Import the sample ER solution</span></span>

<span data-ttu-id="98c22-116">Si supponga di dover progettare una soluzione ER per generare un nuovo report che mostra le transazioni fornitore.</span><span class="sxs-lookup"><span data-stu-id="98c22-116">Imagine that you must design an ER solution to generate a new report that shows vendor transactions.</span></span> <span data-ttu-id="98c22-117">Attualmente, è possibile trovare le transazioni di un fornitore selezionato nella pagina **Transazioni fornitore** (accedere a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori**, selezionare un fornitore e quindi, nel riquadro Azioni, nella scheda **Fornitore** nel gruppo **Transazioni** selezionare **Transazioni**).</span><span class="sxs-lookup"><span data-stu-id="98c22-117">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable** \> **Vendors** \> **All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="98c22-118">Tuttavia, si desidera avere tutte le transazioni fornitore insieme in un documento elettronico in formato XML.</span><span class="sxs-lookup"><span data-stu-id="98c22-118">However, you want to have all vendor transactions together in one electronic document in XML format.</span></span> <span data-ttu-id="98c22-119">Questa soluzione comporterà diverse configurazioni ER contenenti il modello dati, il mapping di modello e i componenti formato necessari.</span><span class="sxs-lookup"><span data-stu-id="98c22-119">This solution will consist of several ER configurations that contain the required data model, model mapping, and format components.</span></span>

<span data-ttu-id="98c22-120">Il primo passaggio consiste nell'importare la soluzione ER di esempio per generare un report delle transazioni del fornitore.</span><span class="sxs-lookup"><span data-stu-id="98c22-120">The first step is to import the sample ER solution to generate a vendor transactions report.</span></span>

1. <span data-ttu-id="98c22-121">Accedere all'istanza di Microsoft Dynamics 365 Finance di cui è stato eseguito il provisioning per la società.</span><span class="sxs-lookup"><span data-stu-id="98c22-121">Sign in to the instance of Microsoft Dynamics 365 Finance that is provisioned for your company.</span></span>
2. <span data-ttu-id="98c22-122">In questo argomento si creeranno e modificheranno configurazioni per la società di esempio **Litware, Inc**.</span><span class="sxs-lookup"><span data-stu-id="98c22-122">In this topic, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="98c22-123">Verificare che questo provider di configurazioni sia stato aggiunto all'istanza di Finance e sia selezionato come attivo.</span><span class="sxs-lookup"><span data-stu-id="98c22-123">Make sure that this configuration provider has been added to your Finance instance and is marked as active.</span></span> <span data-ttu-id="98c22-124">Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="98c22-124">For more information, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="98c22-125">Nell'area di lavoro **Creazione di report elettronici**, selezionare il riquadro **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="98c22-125">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="98c22-126">Nella pagina **Configurazioni**, importare le configurazioni ER scaricate come prerequisito in Finance, nel seguente ordine: modello dati, mapping di modello, formato.</span><span class="sxs-lookup"><span data-stu-id="98c22-126">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into Finance, in the following order: data model, model mapping, format.</span></span> <span data-ttu-id="98c22-127">Per ogni configurazione, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="98c22-127">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="98c22-128">Nella riquadro Azioni, selezionare **Scambia** \> **Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="98c22-128">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
    2. <span data-ttu-id="98c22-129">Selezionare **Sfoglia** e selezionare il file appropriato per la configurazione ER in formato XML.</span><span class="sxs-lookup"><span data-stu-id="98c22-129">Select **Browse**, and select the appropriate file for the ER configuration in XML format.</span></span>
    3. <span data-ttu-id="98c22-130">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c22-130">Select **OK**.</span></span>

![Configurazioni importate nella pagina Configurazioni](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a><span data-ttu-id="98c22-132">Esaminare le soluzione ER di esempio</span><span class="sxs-lookup"><span data-stu-id="98c22-132">Review the sample ER solution</span></span>

### <a name="review-the-model-mapping"></a><span data-ttu-id="98c22-133">Esaminare il mapping di modello</span><span class="sxs-lookup"><span data-stu-id="98c22-133">Review the model mapping</span></span>

1. <span data-ttu-id="98c22-134">Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di miglioramento delle prestazioni**, quindi selezionare **Mapping miglioramento delle prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-134">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="98c22-135">Nel riquadro azioni selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="98c22-135">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="98c22-136">Selezionare **Progettazione** nel riquadro azioni della pagina **Modello per mapping origine dati**.</span><span class="sxs-lookup"><span data-stu-id="98c22-136">On the **Model to datasource mapping** page, on the Action Pane, select **Designer**.</span></span>

    <span data-ttu-id="98c22-137">Questo mapping di modello ER esegue le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98c22-137">This ER model mapping is designed to perform the following actions:</span></span>

    - <span data-ttu-id="98c22-138">Recupera l'elenco delle transazioni del fornitore archiviate nella tabella VendTrans (origine dati **Transazioni**).</span><span class="sxs-lookup"><span data-stu-id="98c22-138">Fetch the list of vendor transactions that are stored in the VendTrans table (**Trans** data source).</span></span>
    - <span data-ttu-id="98c22-139">Per ogni transazione, recuperare, dalla tabella VendTable, il record di un fornitore per il quale è stata registrata la transazione (origine dati **\#Vend**).</span><span class="sxs-lookup"><span data-stu-id="98c22-139">For every transaction, fetch, from the VendTable table, the record of a vendor that the transaction has been posted for (**\#Vend** data source).</span></span>

    > [!NOTE]
    > <span data-ttu-id="98c22-140">L'origine dati **\#Vend** è configurata per recuperare il record del fornitore corrispondente utilizzando la relazione molti-a-uno esistente **\@.'\>Relations'.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="98c22-140">The **\#Vend** data source is configured to fetch the corresponding vendor record by using the existing many-to-one relation **\@.'\>Relations'.VendTable\_AccountNum**.</span></span>

    <span data-ttu-id="98c22-141">Il mapping di modello in questa configurazione implementa il modello di dati di base per qualsiasi formato ER creato per questo modello ed eseguito in Finance.</span><span class="sxs-lookup"><span data-stu-id="98c22-141">The model mapping in this configuration implements the base data model for any ER formats that are created for this model and run in Finance.</span></span> <span data-ttu-id="98c22-142">Di conseguenza, il contenuto dell'origine dati **Transazioni** viene esposto per i formati ER, ad esempio origini dati **modello**.</span><span class="sxs-lookup"><span data-stu-id="98c22-142">Therefore, the content of the **Trans** data source is exposed for ER formats such as abstract **model** data sources.</span></span>

    ![Origine dati transazioni nella pagina di progettazione del mapping del modello](media/er-calculated-field-ds-performance-mapping-1.png)

4. <span data-ttu-id="98c22-144">Chiudere la pagina **Progettazione mapping modello**.</span><span class="sxs-lookup"><span data-stu-id="98c22-144">Close the **Model mapping designer** page.</span></span>
5. <span data-ttu-id="98c22-145">Chiudere la pagina **Modello per mapping origine dati**.</span><span class="sxs-lookup"><span data-stu-id="98c22-145">Close the **Model to datasource mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="98c22-146">Esaminare il formato</span><span class="sxs-lookup"><span data-stu-id="98c22-146">Review format</span></span>

1. <span data-ttu-id="98c22-147">Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di miglioramento delle prestazioni**, quindi selezionare **Formato miglioramento delle prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-147">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement format**.</span></span>
2. <span data-ttu-id="98c22-148">Nel riquadro azioni selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="98c22-148">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="98c22-149">Nella pagina **Progettazione formati** nella scheda **Mapping** selezionare **Espandi/Comprimi**.</span><span class="sxs-lookup"><span data-stu-id="98c22-149">On the **Format designer** page, on the **Mapping** tab, select **Expand/Collapse**.</span></span>
4. <span data-ttu-id="98c22-150">Espandere gli elementi **Modello**, **Dati** e **Transazione**.</span><span class="sxs-lookup"><span data-stu-id="98c22-150">Expand the **Model**, **Data,** and **Transaction** items.</span></span>

    <span data-ttu-id="98c22-151">Questo formato ER è progettato per generare un report sulle transazioni del fornitore in formato XML.</span><span class="sxs-lookup"><span data-stu-id="98c22-151">This ER format is designed to generate a vendor transactions report in XML format.</span></span>

    ![Formattare le origini dati e le associazioni configurate degli elementi di formato nella pagina Progettazione formati](media/er-calculated-field-ds-performance-format.png)

5. <span data-ttu-id="98c22-153">Chiudere la pagina **Progettazione formati**.</span><span class="sxs-lookup"><span data-stu-id="98c22-153">Close the **Format designer** page.</span></span>

## <a name="run-the-sample-er-solution-to-trace-execution"></a><span data-ttu-id="98c22-154">Eseguire la soluzione ER di esempio per generare la traccia dell'esecuzione</span><span class="sxs-lookup"><span data-stu-id="98c22-154">Run the sample ER solution to trace execution</span></span>

<span data-ttu-id="98c22-155">Immaginiamo di aver completato la progettazione della prima versione della soluzione ER.</span><span class="sxs-lookup"><span data-stu-id="98c22-155">Imagine that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="98c22-156">Ora si desidera testare la soluzione nell'istanza di Finance e analizzare le prestazioni di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="98c22-156">You now want to test the solution in your Finance instance and analyze the execution performance.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="98c22-157">Attivare la traccia delle prestazioni ER</span><span class="sxs-lookup"><span data-stu-id="98c22-157">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="98c22-158">Selezionare la società **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="98c22-158">Select the **DEMF** company.</span></span>
2. <span data-ttu-id="98c22-159">Seguire i passaggi in [Attivare la traccia delle prestazioni ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) per generare una traccia delle prestazioni durante l'esecuzione di un formato ER.</span><span class="sxs-lookup"><span data-stu-id="98c22-159">Follow the steps in [Turn on the ER performance trace](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) to generate a performance trace while an ER format is run.</span></span>

    ![Finestra di dialogo Parametri dell'utente](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a><span data-ttu-id="98c22-161">Eseguire il formato ER</span><span class="sxs-lookup"><span data-stu-id="98c22-161">Run the ER format</span></span>

1. <span data-ttu-id="98c22-162">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-162">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="98c22-163">Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Formato miglioramento delle prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-163">On the **Configurations** page, in the configuration tree, select **Performance improvement format**.</span></span>
3. <span data-ttu-id="98c22-164">Nel Riquadro azioni selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="98c22-164">On the Action Pane, select **Run**.</span></span>

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a><span data-ttu-id="98c22-165">Utilizzare la traccia delle prestazioni per analizzare le prestazioni del mapping di modello</span><span class="sxs-lookup"><span data-stu-id="98c22-165">Use the performance trace to analyze model mapping performance</span></span>

1. <span data-ttu-id="98c22-166">Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping miglioramento delle prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-166">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="98c22-167">Nel riquadro azioni selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="98c22-167">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="98c22-168">Selezionare **Progettazione** nel riquadro azioni della pagina **Mapping di modello**.</span><span class="sxs-lookup"><span data-stu-id="98c22-168">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="98c22-169">Nella pagina **Progettazione mapping modello**, nel riquadro azioni, selezionare **Traccia delle prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-169">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="98c22-170">Selezionare la traccia più recente generata, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c22-170">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="98c22-171">Le nuove informazioni sono ora disponibili per alcuni elementi dell'origine dati del mapping di modello corrente:</span><span class="sxs-lookup"><span data-stu-id="98c22-171">New information is now available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="98c22-172">Il tempo effettivo impiegato per acquisire dati utilizzando l'origine dati</span><span class="sxs-lookup"><span data-stu-id="98c22-172">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="98c22-173">Lo stesso tempo espresso come percentuale del tempo totale impiegato per l'esecuzione dell'intero mapping di modello</span><span class="sxs-lookup"><span data-stu-id="98c22-173">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

![Dettagli sul tempo di esecuzione nella pagina Progettazione mapping di modello](./media/er-calculated-field-ds-performance-mapping-2.png)

<span data-ttu-id="98c22-175">La griglia **Statistiche delle prestazioni** mostra che l'origine dati **Transazioni** chiama la tabella VendTrans una volta.</span><span class="sxs-lookup"><span data-stu-id="98c22-175">The **Performance statistics** grid shows that the **Trans** data source calls the VendTrans table one time.</span></span> <span data-ttu-id="98c22-176">Il valore **\[265\]\[Q:265\]** dell'origine dati **Transazioni** indica che 265 transazioni del fornitore sono state recuperate dalla tabella dell'applicazione e restituite al modello di dati.</span><span class="sxs-lookup"><span data-stu-id="98c22-176">The value **\[265\]\[Q:265\]** of the **Trans** data source indicates that 265 vendor transactions have been fetched from the application table and returned to the data model.</span></span>

<span data-ttu-id="98c22-177">La griglia **Statistiche delle prestazioni** mostra anche che il mapping di modello corrente duplica le richieste del database mentre l'origine dati **\#Vend** viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="98c22-177">The **Performance statistics** grid also shows that the current model mapping duplicates database requests while the **\#Vend** data source is run.</span></span> <span data-ttu-id="98c22-178">Questa duplicazione di verifica per i seguenti motivi:</span><span class="sxs-lookup"><span data-stu-id="98c22-178">This duplication occurs for the following reasons:</span></span>

- <span data-ttu-id="98c22-179">La tabella del fornitore viene richiamata due volte per ciascuna delle 265 transazioni fornitore iterate, per un totale di 530 chiamate:</span><span class="sxs-lookup"><span data-stu-id="98c22-179">The vendor table is called two times for each of the 265 iterated vendor transactions, for a total of 530 calls:</span></span>

    - <span data-ttu-id="98c22-180">Viene effettuata una chiamata per inserire il numero di conto del fornitore.</span><span class="sxs-lookup"><span data-stu-id="98c22-180">One call is made to enter the vendor account number.</span></span>
    - <span data-ttu-id="98c22-181">Viene effettuata una chiamata per inserire il nome del fornitore.</span><span class="sxs-lookup"><span data-stu-id="98c22-181">One call is made to enter the vendor name.</span></span>

- <span data-ttu-id="98c22-182">La tabella del fornitore viene richiamata per ciascuna transazione fornitore iterata, anche se le transazioni recuperate sono state registrate solo per cinque fornitori.</span><span class="sxs-lookup"><span data-stu-id="98c22-182">The vendor table is called for each iterated vendor transaction, even though the fetched transactions have been posted for only five vendors.</span></span> <span data-ttu-id="98c22-183">Delle 530 chiamate, 525 sono duplicate.</span><span class="sxs-lookup"><span data-stu-id="98c22-183">Of the 530 calls, 525 are duplicates.</span></span> <span data-ttu-id="98c22-184">La figura seguente mostra il messaggio ricevuto sulle chiamate duplicate (richieste di database).</span><span class="sxs-lookup"><span data-stu-id="98c22-184">The following illustration shows the message that you receive about duplicate calls (database requests).</span></span>

![Messaggio sulle richieste di database duplicate nella pagina Progettazione mapping modello](./media/er-calculated-field-ds-performance-mapping-2a.png)

<span data-ttu-id="98c22-186">Del tempo totale di esecuzione del mapping di modello (circa otto secondi), notare che più dell'80 percento (circa sei secondi) è stato impiegato per recuperare i valori dalla tabella dell'applicazione VendTable.</span><span class="sxs-lookup"><span data-stu-id="98c22-186">Of the total model mapping execution time (approximately eight seconds), notice that more than 80 percent (approximately six seconds) has been spent retrieving values from the VendTable application table.</span></span> <span data-ttu-id="98c22-187">Questa percentuale è troppo grande per due attributi di cinque fornitori, rispetto al volume di informazioni dalla tabella dell'applicazione VendTrans.</span><span class="sxs-lookup"><span data-stu-id="98c22-187">That percentage is too large for two attributes of five vendors, compared with the volume of information from the VendTrans application table.</span></span>

<span data-ttu-id="98c22-188">Per ridurre il numero di chiamate effettuate per ottenere i dettagli del fornitore per ogni transazione e migliorare le prestazioni del mapping di modello, è possibile utilizzare la memorizzazione nella cache per l'origine dati **\#Vend**.</span><span class="sxs-lookup"><span data-stu-id="98c22-188">To reduce the number of calls that are made to get the vendor details for every transaction, and to improve the performance of the model mapping, you can use caching for the **\#Vend** data source.</span></span>

> [!NOTE]
> <span data-ttu-id="98c22-189">L'origine dati **Transazioni\\\#Vend** verrà memorizzata nella cache nell'ambito della transazione corrente dell'origine dati **Transazioni** in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="98c22-189">The **Trans\\\#Vend** data source will be cached in the scope of the current transaction of the **Trans** data source at runtime.</span></span>

<span data-ttu-id="98c22-190">Memorizzando nella cache l'origine dati **\#Vend** si riduce il numero di chiamate duplicate da 525 a 260, ma non si elimina completamente la duplicazione.</span><span class="sxs-lookup"><span data-stu-id="98c22-190">By caching the **\#Vend** data source, you reduce the number of duplicated calls from 525 to 260, but you don't completely eliminate the duplication.</span></span> <span data-ttu-id="98c22-191">Per eliminare completamente la duplicazione, è possibile configurare una nuova origine dati parametrizzata di tipo **Campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="98c22-191">To completely eliminate duplication, you can configure a new parameterized data source of the **Calculated field** type.</span></span>

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="98c22-192">Migliorare il mapping di modello basato sulle informazioni della traccia dell'esecuzione</span><span class="sxs-lookup"><span data-stu-id="98c22-192">Improve the model mapping based on information from the execution trace</span></span>

### <a name="change-the-logic-of-the-model-mapping"></a><span data-ttu-id="98c22-193">Modificare la logica del mapping di modello</span><span class="sxs-lookup"><span data-stu-id="98c22-193">Change the logic of the model mapping</span></span>

<span data-ttu-id="98c22-194">Attenersi alla seguente procedura per utilizzare la memorizzazione nella cache e un'origine dati di tipo **Campo calcolato** per evitare chiamate duplicate al database.</span><span class="sxs-lookup"><span data-stu-id="98c22-194">Follow these steps to use caching and a data source of the **Calculated field** type, to help prevent duplicate calls to the database.</span></span>

1. <span data-ttu-id="98c22-195">Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping miglioramento delle prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-195">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="98c22-196">Nel riquadro azioni selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="98c22-196">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="98c22-197">Selezionare **Progettazione** nel riquadro azioni della pagina **Mapping di modello**.</span><span class="sxs-lookup"><span data-stu-id="98c22-197">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="98c22-198">Nella pagina **Progettazione mapping di modello**, seguire questi passaggi per aggiungere un'origine dati di tipo **Record di tabella** per accedere ai record nella tabella dell'applicazione VendTable:</span><span class="sxs-lookup"><span data-stu-id="98c22-198">On the **Model mapping designer** page, follow these steps to add a data source of the **Table records** type to access records in the VendTable application table:</span></span>

    1. <span data-ttu-id="98c22-199">Nel riquadro **Tipi di origine dati**, espandere **Dynamics 365 for Operations** e selezionare **Record di tabella**.</span><span class="sxs-lookup"><span data-stu-id="98c22-199">In the **Data source types** pane, expand **Dynamics 365 for Operations**, and select **Table records**.</span></span>
    2. <span data-ttu-id="98c22-200">Selezionare **Aggiungi radice**.</span><span class="sxs-lookup"><span data-stu-id="98c22-200">Select **Add root**.</span></span>
    3. <span data-ttu-id="98c22-201">Nella finestra di dialogo, nel campo **Nome**, immettere **Vend**.</span><span class="sxs-lookup"><span data-stu-id="98c22-201">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    4. <span data-ttu-id="98c22-202">Nel campo **Tabella**, immettere **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="98c22-202">In the **Table** field, enter **VendTable**.</span></span>
    5. <span data-ttu-id="98c22-203">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c22-203">Select **OK**.</span></span>

5. <span data-ttu-id="98c22-204">È possibile parametrizzare le chiamate alle origini dati di tipo **Campo calcolato** solo se tali origini dati risiedono in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="98c22-204">You can parameterize calls to data sources of the **Calculated field** type only if those data sources reside in a container.</span></span> <span data-ttu-id="98c22-205">Pertanto, attenersi alla seguente procedura per aggiungere un'origine dati di tipo **Contenitore vuoto** per contenere una nuova origine dati parametrizzata di tipo **Campo calcolato**:</span><span class="sxs-lookup"><span data-stu-id="98c22-205">Therefore, follow these steps to add a data source of the **Empty container** type to hold a new parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="98c22-206">Nel riquadro **Tipi di origine dati**, espandere **Generale** e selezionare **Contenitore vuoto**.</span><span class="sxs-lookup"><span data-stu-id="98c22-206">In the **Data source types** pane, expand **General**, and select **Empty container**.</span></span>
    2. <span data-ttu-id="98c22-207">Selezionare **Aggiungi radice**.</span><span class="sxs-lookup"><span data-stu-id="98c22-207">Select **Add root**.</span></span>
    3. <span data-ttu-id="98c22-208">Nella finestra di dialogo, nel campo **Nome**, immettere **Casella**.</span><span class="sxs-lookup"><span data-stu-id="98c22-208">In the dialog box, in the **Name** field, enter **Box**.</span></span>
    3. <span data-ttu-id="98c22-209">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c22-209">Select **OK**.</span></span>

    ![Origine dati casella nella pagina di progettazione del mapping del modello](./media/er-calculated-field-ds-performance-mapping-3.png)

6. <span data-ttu-id="98c22-211">Attenersi alla seguente procedura per aggiungere un'origine dati parametrizzata di tipo **Campo calcolato**:</span><span class="sxs-lookup"><span data-stu-id="98c22-211">Follow these steps to add a parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="98c22-212">Selezionare **Casella** nel riquadro **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="98c22-212">In the **Data sources** pane, select **Box**.</span></span>
    2. <span data-ttu-id="98c22-213">Nel riquadro **Tipi di origine dati**, espandere **Funzioni** e selezionare **Campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="98c22-213">In the **Data source types** pane, expand **Functions**, and select **Calculated field**.</span></span>
    3. <span data-ttu-id="98c22-214">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="98c22-214">Select **Add**.</span></span>
    4. <span data-ttu-id="98c22-215">Nella finestra di dialogo, nel campo **Nome**, immettere **Vend**.</span><span class="sxs-lookup"><span data-stu-id="98c22-215">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    5. <span data-ttu-id="98c22-216">Selezionare **Modifica formula**.</span><span class="sxs-lookup"><span data-stu-id="98c22-216">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="98c22-217">Nella pagina **Designer formula** selezionare **Parametri** per specificare i parametri che devono essere forniti quando viene chiamata questa origine dati.</span><span class="sxs-lookup"><span data-stu-id="98c22-217">On the **Formula designer** page, select **Parameters** to specify the parameters that must be provided when this data source is called.</span></span>
    7. <span data-ttu-id="98c22-218">Nella finestra di dialogo **Parametri** selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="98c22-218">In the **Parameters** dialog box, select **New**.</span></span>
    8. <span data-ttu-id="98c22-219">Nel campo **Nome**, immettere **parmVendAccNumber**.</span><span class="sxs-lookup"><span data-stu-id="98c22-219">In the **Name** field, enter **parmVendAccNumber**.</span></span>
    9. <span data-ttu-id="98c22-220">Nel campo **Tipo** selezionare **Stringa**.</span><span class="sxs-lookup"><span data-stu-id="98c22-220">In the **Type** field, select **String**.</span></span>
    10. <span data-ttu-id="98c22-221">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c22-221">Select **OK**.</span></span>
    11. <span data-ttu-id="98c22-222">Nel campo **Formula** immettere **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span><span class="sxs-lookup"><span data-stu-id="98c22-222">In the **Formula** field, enter **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span></span>
    12. <span data-ttu-id="98c22-223">Selezionare **Salva** e chiudere la pagina **Designer formula**.</span><span class="sxs-lookup"><span data-stu-id="98c22-223">Select **Save**, and close the **Formula designer** page.</span></span>
    13. <span data-ttu-id="98c22-224">Selezionare **OK** per aggiungere la nuova origine dati.</span><span class="sxs-lookup"><span data-stu-id="98c22-224">Select **OK** to add the new data source.</span></span>

7. <span data-ttu-id="98c22-225">Seguire questi passaggi per contrassegnare l'origine dati aggiunta come memorizzata nella cache durante l'esecuzione:</span><span class="sxs-lookup"><span data-stu-id="98c22-225">Follow these steps to mark the added data source as cached during the execution:</span></span>

    1. <span data-ttu-id="98c22-226">Nel riquadro **Origini dati** selezionare **Casella\\Vend**.</span><span class="sxs-lookup"><span data-stu-id="98c22-226">In the **Data sources** pane, select **Box\\Vend**.</span></span>
    2. <span data-ttu-id="98c22-227">Selezionare **Cache**.</span><span class="sxs-lookup"><span data-stu-id="98c22-227">Select **Cache**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98c22-228">L'origine dati **Casella\\Vend** verrà memorizzata nella cache nell'ambito di tutte le transazioni fornitore dell'origine dati **Transazioni** in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="98c22-228">The **Box\\Vend** data source will be cached in the scope of all vendor transactions of the **Trans** data source at runtime.</span></span>

8. <span data-ttu-id="98c22-229">Seguire questi passaggi per aggiornare l'origine dati **Transazioni\\\#Vend** nidificata in modo che utilizzi l'origine dati **Casella\\Vend**:</span><span class="sxs-lookup"><span data-stu-id="98c22-229">Follow these steps to update the nested **Trans\\\#Vend** data source so that it uses the **Box\\Vend** data source:</span></span>

    1. <span data-ttu-id="98c22-230">Nel riquadro **Origini dati**, espandere **Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-230">In the **Data sources** pane, expand **Trans**.</span></span>
    2. <span data-ttu-id="98c22-231">Selezionare l'origine dati **Trans\\\#Vend** e selezionare **Modifica** \> **Modifica formula**.</span><span class="sxs-lookup"><span data-stu-id="98c22-231">Select the **Trans\\\#Vend** data source, and then select **Edit** \> **Edit formula**.</span></span>
    3. <span data-ttu-id="98c22-232">Nella pagina **Designer formula** nel campo **Formula** inserire **Box.Vend(\@.AccountNum)**.</span><span class="sxs-lookup"><span data-stu-id="98c22-232">On the **Formula designer** page, in the **Formula** field, enter **Box.Vend(\@.AccountNum)**.</span></span>
    4. <span data-ttu-id="98c22-233">Selezionare **Salva** quindi chiudere la pagina **Designer formula**.</span><span class="sxs-lookup"><span data-stu-id="98c22-233">Select **Save**, and then close the **Formula designer** page.</span></span>
    5. <span data-ttu-id="98c22-234">Selezionare **OK** per completare le modifiche all'origine dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="98c22-234">Select **OK** to complete your changes to the selected data source.</span></span>

9. <span data-ttu-id="98c22-235">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="98c22-235">Select **Save**.</span></span>

    ![Origine dati Vend nella pagina di progettazione del mapping del modello](./media/er-calculated-field-ds-performance-mapping-4.png)

10. <span data-ttu-id="98c22-237">Chiudere la pagina **Progettazione mapping modello**.</span><span class="sxs-lookup"><span data-stu-id="98c22-237">Close the **Model mapping designer** page.</span></span>
11. <span data-ttu-id="98c22-238">Chiudere la pagina **Mapping modello**.</span><span class="sxs-lookup"><span data-stu-id="98c22-238">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="98c22-239">Completare la versione modificata del mapping di modello ER</span><span class="sxs-lookup"><span data-stu-id="98c22-239">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="98c22-240">Nella pagina **Configurazioni**, nella Scheda dettaglio **Versioni**, selezionare la versione **1.2** della configurazione **Mapping miglioramento delle prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-240">On the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance improvement mapping** configuration.</span></span>
2. <span data-ttu-id="98c22-241">Selezionare **Cambia stato** \> **Completa** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c22-241">Select **Change status** \> **Complete**, and then select **OK**.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="98c22-242">Eseguire la soluzione ER modificata per generare la traccia dell'esecuzione</span><span class="sxs-lookup"><span data-stu-id="98c22-242">Run the modified ER solution to trace execution</span></span>

<span data-ttu-id="98c22-243">Ripetere i passaggi nella sezione [Eseguire il formato ER](#run-format) vista in precedenza in questo argomento per generare una nuova traccia delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="98c22-243">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a><span data-ttu-id="98c22-244">Utilizzare la traccia delle prestazioni per analizzare le modifiche al mapping di modello</span><span class="sxs-lookup"><span data-stu-id="98c22-244">Use the performance trace to analyze adjustments to the model mapping</span></span> 

1. <span data-ttu-id="98c22-245">Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping miglioramento delle prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-245">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="98c22-246">Nel riquadro azioni selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="98c22-246">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="98c22-247">Selezionare **Progettazione** nel riquadro azioni della pagina **Mapping di modello**.</span><span class="sxs-lookup"><span data-stu-id="98c22-247">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="98c22-248">Nella pagina **Progettazione mapping modello**, nel riquadro azioni, selezionare **Traccia delle prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="98c22-248">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="98c22-249">Selezionare la traccia più recente generata, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c22-249">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="98c22-250">Si noti che le rettifiche apportate al mapping di modello hanno eliminato le query duplicate al database.</span><span class="sxs-lookup"><span data-stu-id="98c22-250">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="98c22-251">Anche il numero di chiamate alle tabelle di database e alle origini dati per questo mapping di modello sono state ridotti.</span><span class="sxs-lookup"><span data-stu-id="98c22-251">The number of calls to database tables and data sources for this model mapping has also been reduced.</span></span>

![Informazioni di traccia nella pagina di progettazione del mapping del modello 1](./media/er-calculated-field-ds-performance-mapping-5.png)

<span data-ttu-id="98c22-253">Il tempo di esecuzione totale è stato ridotto di circa 20 volte (da circa 8 secondi a circa 400 millisecondi).</span><span class="sxs-lookup"><span data-stu-id="98c22-253">The total execution time has been reduced about 20 times (from about 8 seconds to about 400 milliseconds).</span></span> <span data-ttu-id="98c22-254">Di conseguenza, le prestazioni dell'intera soluzione ER sono state migliorate.</span><span class="sxs-lookup"><span data-stu-id="98c22-254">Therefore, the performance of the whole ER solution has been improved.</span></span>

![Informazioni di traccia nella pagina di progettazione del mapping del modello 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a><span data-ttu-id="98c22-256">Appendice 1: scaricare i componenti della soluzione Microsoft ER di esempio</span><span class="sxs-lookup"><span data-stu-id="98c22-256">Appendix 1: Download the components of the sample Microsoft ER solution</span></span>

<span data-ttu-id="98c22-257">È necessario scaricare e archiviare localmente i file seguenti.</span><span class="sxs-lookup"><span data-stu-id="98c22-257">You must download the following files and store them locally.</span></span>

| <span data-ttu-id="98c22-258">File</span><span class="sxs-lookup"><span data-stu-id="98c22-258">File</span></span>                                        | <span data-ttu-id="98c22-259">Contenuto</span><span class="sxs-lookup"><span data-stu-id="98c22-259">Content</span></span> |
|---------------------------------------------|---------|
| <span data-ttu-id="98c22-260">Performance improvement model.version.1</span><span class="sxs-lookup"><span data-stu-id="98c22-260">Performance improvement model.version.1</span></span>     | [<span data-ttu-id="98c22-261">Configurazione del modello di dati ER di esempio</span><span class="sxs-lookup"><span data-stu-id="98c22-261">Sample ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="98c22-262">Performance improvement mapping.version.1.1</span><span class="sxs-lookup"><span data-stu-id="98c22-262">Performance improvement mapping.version.1.1</span></span> | [<span data-ttu-id="98c22-263">Configurazione del mapping di modello ER di esempio</span><span class="sxs-lookup"><span data-stu-id="98c22-263">Sample ER model mapping configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="98c22-264">Performance improvement format.version.1.1</span><span class="sxs-lookup"><span data-stu-id="98c22-264">Performance improvement format.version.1.1</span></span>  | [<span data-ttu-id="98c22-265">Configurazione di formato ER di esempio</span><span class="sxs-lookup"><span data-stu-id="98c22-265">Sample ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a><span data-ttu-id="98c22-266">Appendice 2: configurare il framework ER</span><span class="sxs-lookup"><span data-stu-id="98c22-266">Appendix 2: Configure the ER framework</span></span>

<span data-ttu-id="98c22-267">Prima di poter iniziare a utilizzare il framework ER per migliorare le prestazioni della soluzione Microsoft ER di esempio, è necessario configurare il set minimo di parametri ER.</span><span class="sxs-lookup"><span data-stu-id="98c22-267">Before you can start to use the ER framework to improve the performance of the sample Microsoft ER solution, you must configure the minimal set of ER parameters.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="98c22-268">Configurare i parametri ER</span><span class="sxs-lookup"><span data-stu-id="98c22-268">Configure ER parameters</span></span>

1. <span data-ttu-id="98c22-269">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="98c22-269">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="98c22-270">Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="98c22-270">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="98c22-271">Nella pagina **Parametri per la creazione di report elettronici**, nella scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="98c22-271">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="98c22-272">Nella scheda **Allegati**, imposta i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="98c22-272">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="98c22-273">Nel campo **Configurazioni**, seleziona il tipo **File** per l'azienda **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="98c22-273">In the **Configurations** field, select the **File** type for the **DEMF** company.</span></span>
    - <span data-ttu-id="98c22-274">Nei campi **Archivio processi**, **Temporaneo**, **Base** e **Altri**, seleziona il tipo **File**.</span><span class="sxs-lookup"><span data-stu-id="98c22-274">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="98c22-275">Per ulteriori informazioni sui parametri ER, vedi [Configurare il framework ER](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="98c22-275">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="98c22-276">Attivare un provider di configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="98c22-276">Activate an ER configuration provider</span></span>

<span data-ttu-id="98c22-277">Ogni configurazione ER aggiunta viene contrassegnata come di proprietà di un provider di configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="98c22-277">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="98c22-278">Il provider di configurazione ER che è attivato nell'area di lavoro **Creazione di report elettronici** viene utilizzato per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="98c22-278">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="98c22-279">Pertanto, è necessario attivare un provider di configurazione ER nell'area di lavoro **Creazione di report elettronici** prima di iniziare ad aggiungere o modificare le configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="98c22-279">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="98c22-280">Solo il proprietario di una configurazione ER può modificare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="98c22-280">Only the owner of an ER configuration can edit the configuration.</span></span> <span data-ttu-id="98c22-281">Pertanto, prima di poter modificare una configurazione ER, è necessario attivare il provider di configurazione ER appropriato nell'area di lavoro **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="98c22-281">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="98c22-282">Rivedere l'elenco dei provider di configurazione ER</span><span class="sxs-lookup"><span data-stu-id="98c22-282">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="98c22-283">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="98c22-283">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="98c22-284">Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="98c22-284">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="98c22-285">Nella pagina **Tabella del provider di configurazione**, ogni record del provider ha un nome e un URL univoci.</span><span class="sxs-lookup"><span data-stu-id="98c22-285">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="98c22-286">Rivedi il contenuto della pagina.</span><span class="sxs-lookup"><span data-stu-id="98c22-286">Review the contents of this page.</span></span> <span data-ttu-id="98c22-287">Se un record per **Litware, Inc.** esiste già, andare alla procedura successiva, [Aggiungere un nuovo provider di configurazione ER](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="98c22-287">If a record for **Litware, Inc.** already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="98c22-288">Aggiungere un nuovo provider di configurazione ER</span><span class="sxs-lookup"><span data-stu-id="98c22-288">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="98c22-289">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="98c22-289">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="98c22-290">Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="98c22-290">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="98c22-291">Nella pagina **Provider di configurazione**, seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="98c22-291">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="98c22-292">Nel campo **Nome**, immetti **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="98c22-292">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="98c22-293">Nel campo **Indirizzo Internet** immetti `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="98c22-293">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="98c22-294">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="98c22-294">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="98c22-295">Attivare un provider di configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="98c22-295">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="98c22-296">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="98c22-296">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="98c22-297">Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Litware, Inc.**, quindi seleziona **Imposta attivo**.</span><span class="sxs-lookup"><span data-stu-id="98c22-297">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="98c22-298">Per ulteriori informazioni sui provider di configurazione ER, vedi [Creare provider di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="98c22-298">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98c22-299">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="98c22-299">Additional resources</span></span>

- [<span data-ttu-id="98c22-300">Panoramica sui report elettronici</span><span class="sxs-lookup"><span data-stu-id="98c22-300">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="98c22-301">Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni</span><span class="sxs-lookup"><span data-stu-id="98c22-301">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)
- [<span data-ttu-id="98c22-302">Supporto per le chiamate parametrizzate delle origini dati ER di tipo Campo calcolato</span><span class="sxs-lookup"><span data-stu-id="98c22-302">Support parameterized calls of ER data sources of the Calculated field type</span></span>](er-calculated-field-type.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]