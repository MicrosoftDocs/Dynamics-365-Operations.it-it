---
title: Esercitazione sull'utilizzo di Regression Suite Automation Tool
description: In questo argomento viene illustrato come utilizzare lo strumento Regression Suite Automation Tool (RSAT). Vengono descritte varie funzionalità e forniti esempi che utilizzano lo script avanzato.
author: robinarh
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 0c2babc3144cae5c68075bd853a2587505263776
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410152"
---
# <a name="regression-suite-automation-tool-tutorial"></a><span data-ttu-id="726f9-104">Esercitazione Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="726f9-104">Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="726f9-105">Utilizzare gli strumenti del browser Internet per scaricare e salvare questa pagina in formato PDF.</span><span class="sxs-lookup"><span data-stu-id="726f9-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="726f9-106">Questa esercitazione descrive alcune delle funzionalità avanzate di Regression Suite Automation Tool (RSAT), include un'assegnazione demo e fornisce suggerimenti chiave e la strategia da adottare.</span><span class="sxs-lookup"><span data-stu-id="726f9-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span> 

## <a name="notable-features-of-rsat-and-task-recorder"></a><span data-ttu-id="726f9-107">Caratteristiche importanti di RSAT e Registrazione attività</span><span class="sxs-lookup"><span data-stu-id="726f9-107">Notable Features of RSAT and Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="726f9-108">Convalidare un valore di campo</span><span class="sxs-lookup"><span data-stu-id="726f9-108">Validate a field value</span></span>

<span data-ttu-id="726f9-109">RSAT consente di includere passaggi di convalida nel caso di test per convalidare i valori previsti.</span><span class="sxs-lookup"><span data-stu-id="726f9-109">RSAT allows you to include validation steps within your test case to validate expected values.</span></span> <span data-ttu-id="726f9-110">Per informazioni su questa funzione, consultare l'articolo [Convalidare i valori previsti](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span><span class="sxs-lookup"><span data-stu-id="726f9-110">For information about this feature, see the article [Validate expected values](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span></span>

<span data-ttu-id="726f9-111">Nell'esempio seguente viene illustrato come utilizzare questa funzionalità per verificare se le scorte disponibili sono maggiori di 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="726f9-111">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="726f9-112">Nei dati demo della società **USMF**, creare una registrazione attività che includa i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="726f9-112">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="726f9-113">Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="726f9-113">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="726f9-114">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="726f9-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="726f9-115">Ad esempio, filtrare in base al valore **1000** nel campo **Numero articolo**.</span><span class="sxs-lookup"><span data-stu-id="726f9-115">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="726f9-116">Selezionare **Scorte disponibili**.</span><span class="sxs-lookup"><span data-stu-id="726f9-116">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="726f9-117">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="726f9-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="726f9-118">Ad esempio, filtrare in base al valore **1** nel campo **Sito**.</span><span class="sxs-lookup"><span data-stu-id="726f9-118">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="726f9-119">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="726f9-119">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="726f9-120">Verificare che il valore del campo **Totale disponibile** sia **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="726f9-120">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="726f9-121">Salvare la registrazione attività e collegarla al caso di test in Azure Devops.</span><span class="sxs-lookup"><span data-stu-id="726f9-121">Save the task recording and attach it to your test case in Azure Devops.</span></span>
3. <span data-ttu-id="726f9-122">Aggiungere il test case al piano di test e caricare il test case in RSAT.</span><span class="sxs-lookup"><span data-stu-id="726f9-122">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="726f9-123">Apre il file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-123">Open the Excel parameter file.</span></span> <span data-ttu-id="726f9-124">Nella scheda **InventOnhandItem** verrà visualizzata una sezione **Convalida InventOnhandItem** che include un campo **Operatore**.</span><span class="sxs-lookup"><span data-stu-id="726f9-124">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Campo Operatore](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="726f9-126">Per verificare se le scorte disponibili saranno sempre maggiori di 0, modificare il valore del campo **Valore** da **411** a **0** e il valore del campo **Operatore** dal segno uguale (**=**) al segno maggiore di (**\>**).</span><span class="sxs-lookup"><span data-stu-id="726f9-126">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Valori dei campi Valore e Operatore modificati](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="726f9-128">Salvare e chiudere il file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-128">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="726f9-129">Selezionare **Carica** per salvare le modifiche apportate al file di parametri di Excel in Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="726f9-129">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="726f9-130">A questo punto, se il valore del campo **Totale disponibile** per l'articolo specificato nelle scorte è maggiore di 0 (zero), i test avranno esito positivo, indipendentemente dal valore delle scorte disponibili effettivo.</span><span class="sxs-lookup"><span data-stu-id="726f9-130">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="saved-variables-and-chaining-of-test-cases"></a><span data-ttu-id="726f9-131">Variabili salvate e concatenamento di casi di test</span><span class="sxs-lookup"><span data-stu-id="726f9-131">Saved variables and chaining of test cases</span></span>

<span data-ttu-id="726f9-132">Una delle funzionalità importanti di RSAT è il concatenamento dei test case, ovvero la capacità di un test di passare variabili ad altri test.</span><span class="sxs-lookup"><span data-stu-id="726f9-132">One of the key features of RSAT is the chaining of test cases, that is, the ability of a test to pass variables to other tests.</span></span> <span data-ttu-id="726f9-133">Per ulteriori informazioni, consultare l'articolo [Copiare le variabili in casi di test concatenati](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="726f9-133">For more information, see the article [Copy variables to chain test cases](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="726f9-134">Test case derivato</span><span class="sxs-lookup"><span data-stu-id="726f9-134">Derived test case</span></span>

<span data-ttu-id="726f9-135">RSAT consente di utilizzare la stessa registrazione di attività con più casi di test, permettendo l'esecuzione di un'attività con diverse configurazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="726f9-135">RSAT lets you use the same task recording with multiple test cases, enabling a task to run with different data configurations.</span></span> <span data-ttu-id="726f9-136">Vedere l'articolo [Casi di test derivati](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="726f9-136">See the article [Derived test cases](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) for more information.</span></span>

### <a name="validate-notifications-and-messages"></a><span data-ttu-id="726f9-137">Convalidare notifiche e messaggi</span><span class="sxs-lookup"><span data-stu-id="726f9-137">Validate notifications and messages</span></span>

<span data-ttu-id="726f9-138">Questa funzionalità può essere utilizzata per convalidare un'azione avvenuta.</span><span class="sxs-lookup"><span data-stu-id="726f9-138">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="726f9-139">Ad esempio, quando un ordine di produzione viene creato, valutato e quindi avviato, l'app visualizza un messaggio "Produzione - Avvio" per notificare all'utente che l'ordine di produzione è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="726f9-139">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Notifica Produzione - Avvio](./media/use_rsa_tool_05.png)

<span data-ttu-id="726f9-141">È possibile convalidare questo messaggio mediante RSAT digitando il testo del messaggio nella scheda **MessageValidation** del file di parametri di Excel per la registrazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="726f9-141">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Scheda Convalida messaggio](./media/use_rsa_tool_06.png)

<span data-ttu-id="726f9-143">Dopo l'esecuzione del test case, il messaggio nel file di parametri di Excel viene confrontato al messaggio visualizzato.</span><span class="sxs-lookup"><span data-stu-id="726f9-143">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="726f9-144">Se i messaggi non corrispondono, il test case non avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="726f9-144">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="726f9-145">È possibile immettere più di un messaggio nella scheda **Convalida messaggio** del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-145">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="726f9-146">I messaggi possono anche essere messaggi di errore o di avviso anziché messaggi informativi.</span><span class="sxs-lookup"><span data-stu-id="726f9-146">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="snapshot"></a><span data-ttu-id="726f9-147">Snapshot</span><span class="sxs-lookup"><span data-stu-id="726f9-147">Snapshot</span></span>

<span data-ttu-id="726f9-148">Questa funzionalità consente di acquisire schermate dei passaggi eseguiti durante la registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="726f9-148">This feature takes screenshots of the steps that were performed during task recording.</span></span> <span data-ttu-id="726f9-149">È utile per scopi di controllo o debug.</span><span class="sxs-lookup"><span data-stu-id="726f9-149">It is useful for auditing or debugging purposes.</span></span>

- <span data-ttu-id="726f9-150">Per utilizzare questa funzionalità, aprire il file **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** nella cartella di installazione di RSAT (ad esempio **C:\\Programmi (x86)\\Regression Suite Automation Tool**) e modificare il valore dell'elemento seguente da **false** a **true**.</span><span class="sxs-lookup"><span data-stu-id="726f9-150">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="726f9-151">Quando si esegue il caso di test, RSAT genera snapshot (immagini) dei passaggi nella cartella di riproduzione dei casi di test nella directory di lavoro.</span><span class="sxs-lookup"><span data-stu-id="726f9-151">When your run the test case, RSAT will generate snapshots (images) of the steps in the playback folder of the test cases in the working diretory.</span></span> <span data-ttu-id="726f9-152">Se si utilizza una versione precedente di RSAT, le immagini vengono salvate in **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, viene creata una cartella separata per ogni caso di test che viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="726f9-152">If you are using an older version of RSAT, the images are saved to **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

## <a name="assignment"></a><span data-ttu-id="726f9-153">Assegnazione</span><span class="sxs-lookup"><span data-stu-id="726f9-153">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="726f9-154">Scenario</span><span class="sxs-lookup"><span data-stu-id="726f9-154">Scenario</span></span>

1. <span data-ttu-id="726f9-155">Il responsabile della progettazione dei prodotti crea un nuovo prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="726f9-155">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="726f9-156">Il responsabile produzione inizia un ordine di produzione per portare il livello scorte a due pezzi.</span><span class="sxs-lookup"><span data-stu-id="726f9-156">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="726f9-157">La produzione inizia e termina l'ordine di produzione e verifica che la quantità disponibile sia due pezzi.</span><span class="sxs-lookup"><span data-stu-id="726f9-157">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="726f9-158">Il team delle vendite riceve un ordine per quattro pezzi del nuovo prodotto.</span><span class="sxs-lookup"><span data-stu-id="726f9-158">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="726f9-159">Di conseguenza, il team delle vendite aggiorna i fabbisogni netti tramite il piano dinamico.</span><span class="sxs-lookup"><span data-stu-id="726f9-159">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="726f9-160">Poiché non è disponibile ulteriore capacità, i criteri di ordine predefiniti sono impostati su "acquista anziché produrre".</span><span class="sxs-lookup"><span data-stu-id="726f9-160">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="726f9-161">Di conseguenza, viene creato un ordine fornitore pianificato.</span><span class="sxs-lookup"><span data-stu-id="726f9-161">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="726f9-162">L'acquirente aggiunge un fornitore, stabilizza l'ordine fornitore pianificato e conferma l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="726f9-162">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="726f9-163">Quando le merci acquistate arrivano presso il punto vendita, l'operatore cerca l'ordine fornitore correlato e riceve le merci.</span><span class="sxs-lookup"><span data-stu-id="726f9-163">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="726f9-164">Poiché l'ordine è ora completato, le merci possono essere prelevate e imballate a fronte dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="726f9-164">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="726f9-165">L'ufficio contabilità registra la fattura di acquisto e quella di vendita.</span><span class="sxs-lookup"><span data-stu-id="726f9-165">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="726f9-166">Nella figura seguente è illustrato il flusso di questo scenario.</span><span class="sxs-lookup"><span data-stu-id="726f9-166">The following illustration shows the flow for this scenario.</span></span>

![Flusso dello scenario demo](./media/use_rsa_tool_14.png)

<span data-ttu-id="726f9-168">La seguente illustrazione mostra la gerarchia dei processi aziendali per questo scenario in Modellatore di processi aziendali LCS.</span><span class="sxs-lookup"><span data-stu-id="726f9-168">The following illustration shows the business processes hierarchy for this scenario in the LCS Business Process Modeler.</span></span>

![Processi aziendali per lo scenario demo](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="726f9-170">Strategia - Suggerimenti chiave</span><span class="sxs-lookup"><span data-stu-id="726f9-170">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="726f9-171">Dati</span><span class="sxs-lookup"><span data-stu-id="726f9-171">Data</span></span>

- <span data-ttu-id="726f9-172">Assicurarsi di disporre di volumi di dati rappresentativi (una copia dei dati della configurazione prodotto/Golden oltre ai dati migrati).</span><span class="sxs-lookup"><span data-stu-id="726f9-172">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="726f9-173">Quando si generano nuovi dati tramite Registrazione attività, creare nomi di test che non saranno in conflitto con i nomi esistenti (ad esempio, utilizzare un prefisso come **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="726f9-173">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="726f9-174">Utilizzare il ripristino temporizzato di Azure per eseguire di nuovo i test in ambienti non di livello 1.</span><span class="sxs-lookup"><span data-stu-id="726f9-174">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="726f9-175">Sebbene sia possibile utilizzare le funzioni **RANDOM** e **NOW** di Excel per generare una combinazione univoca, questa operazione risulta parecchio complessa.</span><span class="sxs-lookup"><span data-stu-id="726f9-175">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="726f9-176">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="726f9-176">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="726f9-177">Registrazione attività</span><span class="sxs-lookup"><span data-stu-id="726f9-177">Task recorder</span></span>

- <span data-ttu-id="726f9-178">Definire gli scenari prima di iniziare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="726f9-178">Define scenarios before you start recording.</span></span> <span data-ttu-id="726f9-179">Un progetto ben gestito comporta scenari di test predefiniti.</span><span class="sxs-lookup"><span data-stu-id="726f9-179">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="726f9-180">Per generare un test case, prendere in considerazione la prevedibilità del risultato di questi scenari di test.</span><span class="sxs-lookup"><span data-stu-id="726f9-180">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="726f9-181">Dividere le registrazioni se vengono eseguite da ruoli differenti oppure in caso di tempo di attesa o di evento esterno prima del passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="726f9-181">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="726f9-182">Non selezionare i valori negli elenchi.</span><span class="sxs-lookup"><span data-stu-id="726f9-182">Avoid selecting values in lists.</span></span> <span data-ttu-id="726f9-183">Utilizzare invece formati di testo, ad esempio **FIFO**, **AudioRM** e **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="726f9-183">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="726f9-184">Quando si esegue la selezione in un elenco, viene registrata la posizione del valore nell'elenco e non il valore stesso.</span><span class="sxs-lookup"><span data-stu-id="726f9-184">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="726f9-185">Se si aggiungono degli elementi a tale elenco, la posizione del valore può cambiare.</span><span class="sxs-lookup"><span data-stu-id="726f9-185">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="726f9-186">Di conseguenza, la registrazione utilizzerà un parametro differente e ciò potrebbe influenzare il resto dello scenario.</span><span class="sxs-lookup"><span data-stu-id="726f9-186">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="726f9-187">Prendere in considerazione il comportamento multiutente.</span><span class="sxs-lookup"><span data-stu-id="726f9-187">Think about multi-user behavior.</span></span> <span data-ttu-id="726f9-188">Ad esempio, non presupporre che l'ordine cliente appena creato verrà sempre selezionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="726f9-188">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="726f9-189">Invece, utilizzare sempre il filtro per trovare l'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="726f9-189">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="726f9-190">Utilizzare la funzione Copia di Registrazione attività per salvare il nome di un prodotto appena creato di modo che possa essere utilizzato in test case concatenati.</span><span class="sxs-lookup"><span data-stu-id="726f9-190">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="726f9-191">Utilizzare la funzione Convalida di Registrazione attività per impostare checkpoint con cui verificare la corretta esecuzione dei passaggi.</span><span class="sxs-lookup"><span data-stu-id="726f9-191">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="726f9-192">RSAT</span><span class="sxs-lookup"><span data-stu-id="726f9-192">RSAT</span></span>

- <span data-ttu-id="726f9-193">Per eseguire il test in un'altra società, è possibile modificare la società nella scheda **Generale** del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-193">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="726f9-194">Assicurarsi che le impostazioni e i dati siano disponibili nella nuova società selezionata.</span><span class="sxs-lookup"><span data-stu-id="726f9-194">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="726f9-195">È possibile modificare l'utente dei test nella scheda **Generale** del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-195">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="726f9-196">Specificare l'ID di posta elettronica dell'utente che esegue il test case.</span><span class="sxs-lookup"><span data-stu-id="726f9-196">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="726f9-197">In questo modo, il test case può essere eseguito utilizzando le autorizzazioni di sicurezza dell'utente specificato.</span><span class="sxs-lookup"><span data-stu-id="726f9-197">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="726f9-198">Per ritardare l'esecuzione del test, è possibile definire una pausa nella scheda **Generale** del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-198">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="726f9-199">Questa pausa può essere utilizzata in un processo batch (ad esempio se un flusso di lavoro deve essere eseguito per poter eseguire il passaggio successivo).</span><span class="sxs-lookup"><span data-stu-id="726f9-199">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="726f9-200">Script avanzato</span><span class="sxs-lookup"><span data-stu-id="726f9-200">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="726f9-201">CLI</span><span class="sxs-lookup"><span data-stu-id="726f9-201">CLI</span></span>

<span data-ttu-id="726f9-202">RSAT può essere chiamato da una finestra **Prompt dei comandi** o **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="726f9-202">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="726f9-203">Verificare che la variabile di ambiente **TestRoot** sia impostata sul percorso di installazione di RSAT.</span><span class="sxs-lookup"><span data-stu-id="726f9-203">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="726f9-204">(in Microsoft Windows, aprire **Pannello di controllo**, selezionare **Sistema e sicurezza \> Sistema \> Impostazioni di sistema avanzate** e quindi **Variabili di ambiente**).</span><span class="sxs-lookup"><span data-stu-id="726f9-204">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="726f9-205">Aprire una finestra **Prompt dei comandi** o **PowerShell** come amministratore.</span><span class="sxs-lookup"><span data-stu-id="726f9-205">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="726f9-206">Passare alla directory di installazione RSAT.</span><span class="sxs-lookup"><span data-stu-id="726f9-206">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="726f9-207">Elencare tutti i comandi.</span><span class="sxs-lookup"><span data-stu-id="726f9-207">List all commands.</span></span>

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a><span data-ttu-id="726f9-208">?</span><span class="sxs-lookup"><span data-stu-id="726f9-208">?</span></span> 
<span data-ttu-id="726f9-209">Mostra le informazioni di aiuto su tutti i comandi disponibili e i relativi parametri.</span><span class="sxs-lookup"><span data-stu-id="726f9-209">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a><span data-ttu-id="726f9-210">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="726f9-210">Optional parameters</span></span>

**``command``**


<span data-ttu-id="726f9-211">Dove ``[command]`` è uno dei comandi specificati di seguito.</span><span class="sxs-lookup"><span data-stu-id="726f9-211">Where ``[command]`` is one of the commands specified below.</span></span>


#### <a name="about"></a><span data-ttu-id="726f9-212">informazioni su</span><span class="sxs-lookup"><span data-stu-id="726f9-212">about</span></span>
<span data-ttu-id="726f9-213">Visualizza la versione corrente.</span><span class="sxs-lookup"><span data-stu-id="726f9-213">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="726f9-214">cls</span><span class="sxs-lookup"><span data-stu-id="726f9-214">cls</span></span>
<span data-ttu-id="726f9-215">Cancella il contenuto dello schermo.</span><span class="sxs-lookup"><span data-stu-id="726f9-215">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a><span data-ttu-id="726f9-216">scarica</span><span class="sxs-lookup"><span data-stu-id="726f9-216">download</span></span>
<span data-ttu-id="726f9-217">Scarica gli allegati per il test case specificato nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="726f9-217">Downloads attachments for the specified test case to the output directory.</span></span> <span data-ttu-id="726f9-218">È possibile usare il comando ``list`` per ottenere tutti i test case disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-218">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="726f9-219">Utilizzare qualsiasi valore della prima colonna come parametro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="726f9-219">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-220">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-220">Required parameters</span></span>
<span data-ttu-id="726f9-221">**``test_case_id``** Rappresenta l'ID del test case.</span><span class="sxs-lookup"><span data-stu-id="726f9-221">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="726f9-222">**``output_dir``** Rappresenta la directory di output.</span><span class="sxs-lookup"><span data-stu-id="726f9-222">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="726f9-223">È necessario che la directory sia già presente.</span><span class="sxs-lookup"><span data-stu-id="726f9-223">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="726f9-224">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-224">Examples</span></span>

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a><span data-ttu-id="726f9-225">modifica</span><span class="sxs-lookup"><span data-stu-id="726f9-225">edit</span></span>
<span data-ttu-id="726f9-226">Permette di aprire il file dei parametri nel programma Excel e di modificarlo.</span><span class="sxs-lookup"><span data-stu-id="726f9-226">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-227">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-227">Required parameters</span></span>
<span data-ttu-id="726f9-228">**``excel_file``** Deve contenere un percorso completo di un file Excel esistente.</span><span class="sxs-lookup"><span data-stu-id="726f9-228">**``excel_file``** Must contain a full path to an existing Excel file.</span></span>

##### <a name="examples"></a><span data-ttu-id="726f9-229">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-229">Examples</span></span>
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a><span data-ttu-id="726f9-230">generate</span><span class="sxs-lookup"><span data-stu-id="726f9-230">generate</span></span>
<span data-ttu-id="726f9-231">Genera i file di esecuzione del test e dei parametri per il test case specificato nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="726f9-231">Generates test execution and parameter files for the specified test case in the output directory.</span></span>
<span data-ttu-id="726f9-232">È possibile usare il comando ``list`` per ottenere tutti i test case disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-232">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="726f9-233">Utilizzare qualsiasi valore della prima colonna come parametro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="726f9-233">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-234">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-234">Required parameters</span></span>
<span data-ttu-id="726f9-235">**``test_case_id``** Rappresenta l'ID del test case.</span><span class="sxs-lookup"><span data-stu-id="726f9-235">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="726f9-236">**``output_dir``** Rappresenta la directory di output.</span><span class="sxs-lookup"><span data-stu-id="726f9-236">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="726f9-237">È necessario che la directory sia già presente.</span><span class="sxs-lookup"><span data-stu-id="726f9-237">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="726f9-238">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-238">Examples</span></span>
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a><span data-ttu-id="726f9-239">generatederived</span><span class="sxs-lookup"><span data-stu-id="726f9-239">generatederived</span></span>
<span data-ttu-id="726f9-240">Genera un nuovo test case, derivato dal test case fornito.</span><span class="sxs-lookup"><span data-stu-id="726f9-240">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="726f9-241">È possibile usare il comando ``list`` per ottenere tutti i test case disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-241">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="726f9-242">Utilizzare qualsiasi valore della prima colonna come parametro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="726f9-242">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-243">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-243">Required parameters</span></span>
<span data-ttu-id="726f9-244">**``parent_test_case_id``** Rappresenta l'ID del test case padre.</span><span class="sxs-lookup"><span data-stu-id="726f9-244">**``parent_test_case_id``** Represents the parent test case ID.</span></span>  
<span data-ttu-id="726f9-245">**``test_plan_id``** Rappresenta l'ID del piano di test.</span><span class="sxs-lookup"><span data-stu-id="726f9-245">**``test_plan_id``** Represents the test plan ID.</span></span>  
<span data-ttu-id="726f9-246">**``test_suite_id``** Rappresenta l'ID della suite di test.</span><span class="sxs-lookup"><span data-stu-id="726f9-246">**``test_suite_id``** Represents the test suite ID.</span></span>

##### <a name="examples"></a><span data-ttu-id="726f9-247">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-247">Examples</span></span>
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a><span data-ttu-id="726f9-248">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="726f9-248">generatetestonly</span></span>
<span data-ttu-id="726f9-249">Genera solo il file di esecuzione del test per il test case specificato nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="726f9-249">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="726f9-250">È possibile usare il comando ``list`` per ottenere tutti i test case disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-250">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="726f9-251">Utilizzare qualsiasi valore della prima colonna come parametro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="726f9-251">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-252">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-252">Required parameters</span></span>
<span data-ttu-id="726f9-253">**``test_case_id``** Rappresenta l'ID del test case.</span><span class="sxs-lookup"><span data-stu-id="726f9-253">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="726f9-254">**``output_dir``** Rappresenta la directory di output.</span><span class="sxs-lookup"><span data-stu-id="726f9-254">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="726f9-255">È necessario che la directory sia già presente.</span><span class="sxs-lookup"><span data-stu-id="726f9-255">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="726f9-256">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-256">Examples</span></span>
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a><span data-ttu-id="726f9-257">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="726f9-257">generatetestsuite</span></span>
<span data-ttu-id="726f9-258">Genera tutti i test case per la suite specificata nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="726f9-258">Generates all test cases for the specified suite in the output directory.</span></span>
<span data-ttu-id="726f9-259">È possibile usare il comando ``listtestsuitenames`` per ottenere tutte le suite di test disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-259">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="726f9-260">Utilizzare qualsiasi valore della colonna come parametro **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="726f9-260">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-261">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-261">Required parameters</span></span>
<span data-ttu-id="726f9-262">**``test_suite_name``** Rappresenta il nome della suite di test.</span><span class="sxs-lookup"><span data-stu-id="726f9-262">**``test_suite_name``** Represents the test suite name.</span></span>  
<span data-ttu-id="726f9-263">**``output_dir``** Rappresenta la directory di output.</span><span class="sxs-lookup"><span data-stu-id="726f9-263">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="726f9-264">È necessario che la directory sia già presente.</span><span class="sxs-lookup"><span data-stu-id="726f9-264">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="726f9-265">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-265">Examples</span></span>
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a><span data-ttu-id="726f9-266">guida</span><span class="sxs-lookup"><span data-stu-id="726f9-266">help</span></span>
<span data-ttu-id="726f9-267">Identico a [?](#section)</span><span class="sxs-lookup"><span data-stu-id="726f9-267">Identical to the [?](#section)</span></span> <span data-ttu-id="726f9-268">comando</span><span class="sxs-lookup"><span data-stu-id="726f9-268">command</span></span>


#### <a name="list"></a><span data-ttu-id="726f9-269">elenco</span><span class="sxs-lookup"><span data-stu-id="726f9-269">list</span></span>
<span data-ttu-id="726f9-270">Elenca tutti i test case disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-270">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a><span data-ttu-id="726f9-271">listtestplans</span><span class="sxs-lookup"><span data-stu-id="726f9-271">listtestplans</span></span>
<span data-ttu-id="726f9-272">Elenca tutti i piani di test disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-272">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a><span data-ttu-id="726f9-273">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="726f9-273">listtestsuite</span></span>
<span data-ttu-id="726f9-274">Elenca i test case per la suite di test specificata.</span><span class="sxs-lookup"><span data-stu-id="726f9-274">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="726f9-275">È possibile usare il comando ``listtestsuitenames`` per ottenere tutte le suite di test disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-275">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="726f9-276">Utilizzare qualsiasi valore della prima colonna come parametro **suite_name**.</span><span class="sxs-lookup"><span data-stu-id="726f9-276">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-277">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-277">Required parameters</span></span>
<span data-ttu-id="726f9-278">**``suite_name``** Nome della suite desiderata.</span><span class="sxs-lookup"><span data-stu-id="726f9-278">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="726f9-279">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-279">Examples</span></span>
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a><span data-ttu-id="726f9-280">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="726f9-280">listtestsuitenames</span></span>
<span data-ttu-id="726f9-281">Elenca tutte le suite di test disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-281">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a><span data-ttu-id="726f9-282">playback</span><span class="sxs-lookup"><span data-stu-id="726f9-282">playback</span></span>
<span data-ttu-id="726f9-283">Riproduce un test case utilizzando un file Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-283">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-284">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-284">Required parameters</span></span>
<span data-ttu-id="726f9-285">**``excel_file``** Percorso completo del file di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-285">**``excel_file``** A full path to the Excel file.</span></span> <span data-ttu-id="726f9-286">Il file deve essere già presente.</span><span class="sxs-lookup"><span data-stu-id="726f9-286">File must exist.</span></span> 

##### <a name="examples"></a><span data-ttu-id="726f9-287">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-287">Examples</span></span>
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a><span data-ttu-id="726f9-288">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="726f9-288">playbackbyid</span></span>
<span data-ttu-id="726f9-289">Riproduce più test case contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="726f9-289">Plays back multiple test cases at once.</span></span>
<span data-ttu-id="726f9-290">È possibile usare il comando ``list`` per ottenere tutti i test case disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-290">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="726f9-291">Utilizzare qualsiasi valore della prima colonna come parametro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="726f9-291">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-292">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-292">Required parameters</span></span>
<span data-ttu-id="726f9-293">**``test_case_id1``** ID del test case esistente.</span><span class="sxs-lookup"><span data-stu-id="726f9-293">**``test_case_id1``** ID of exisiting test case.</span></span>  
<span data-ttu-id="726f9-294">**``test_case_id2``** ID del test case esistente.</span><span class="sxs-lookup"><span data-stu-id="726f9-294">**``test_case_id2``** ID of exisiting test case.</span></span>  
<span data-ttu-id="726f9-295">**``test_case_idN``** ID del test case esistente.</span><span class="sxs-lookup"><span data-stu-id="726f9-295">**``test_case_idN``** ID of exisiting test case.</span></span>  

##### <a name="examples"></a><span data-ttu-id="726f9-296">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-296">Examples</span></span>
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a><span data-ttu-id="726f9-297">playbackmany</span><span class="sxs-lookup"><span data-stu-id="726f9-297">playbackmany</span></span>
<span data-ttu-id="726f9-298">Riproduce molti test case contemporaneamente, utilizzando i file di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-298">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-299">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-299">Required parameters</span></span>
<span data-ttu-id="726f9-300">**``excel_file1``** Percorso completo del file di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-300">**``excel_file1``** Full path to the Excel file.</span></span> <span data-ttu-id="726f9-301">Il file deve essere già presente.</span><span class="sxs-lookup"><span data-stu-id="726f9-301">File must exist.</span></span>  
<span data-ttu-id="726f9-302">**``excel_file2``** Percorso completo del file di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-302">**``excel_file2``** Full path to the Excel file.</span></span> <span data-ttu-id="726f9-303">Il file deve essere già presente.</span><span class="sxs-lookup"><span data-stu-id="726f9-303">File must exist.</span></span>  
<span data-ttu-id="726f9-304">**``excel_fileN``** Percorso completo del file di Excel.</span><span class="sxs-lookup"><span data-stu-id="726f9-304">**``excel_fileN``** Full path to the Excel file.</span></span> <span data-ttu-id="726f9-305">Il file deve essere già presente.</span><span class="sxs-lookup"><span data-stu-id="726f9-305">File must exist.</span></span>  

##### <a name="examples"></a><span data-ttu-id="726f9-306">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-306">Examples</span></span>
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a><span data-ttu-id="726f9-307">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="726f9-307">playbacksuite</span></span>
<span data-ttu-id="726f9-308">Riproduce tutti i test case dalla suite di test specificata.</span><span class="sxs-lookup"><span data-stu-id="726f9-308">Plays back all test cases from the specified test suite.</span></span> <span data-ttu-id="726f9-309">È possibile usare il comando ``listtestsuitenames`` per ottenere tutte le suite di test disponibili.</span><span class="sxs-lookup"><span data-stu-id="726f9-309">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="726f9-310">Utilizzare qualsiasi valore della prima colonna come parametro **suite_name**.</span><span class="sxs-lookup"><span data-stu-id="726f9-310">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-311">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-311">Required parameters</span></span>
<span data-ttu-id="726f9-312">**``suite_name``** Nome della suite desiderata.</span><span class="sxs-lookup"><span data-stu-id="726f9-312">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="726f9-313">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-313">Examples</span></span>
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a><span data-ttu-id="726f9-314">quit</span><span class="sxs-lookup"><span data-stu-id="726f9-314">quit</span></span>
<span data-ttu-id="726f9-315">Chiude l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="726f9-315">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a><span data-ttu-id="726f9-316">upload</span><span class="sxs-lookup"><span data-stu-id="726f9-316">upload</span></span>
<span data-ttu-id="726f9-317">Carica tutti i file appartenenti alla suite di test o ai test case specificati.</span><span class="sxs-lookup"><span data-stu-id="726f9-317">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a><span data-ttu-id="726f9-318">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-318">Required parameters</span></span>
<span data-ttu-id="726f9-319">**``suite_name``** Tutti i file appartenenti alla suite di test verranno caricati.</span><span class="sxs-lookup"><span data-stu-id="726f9-319">**``suite_name``** All files belonging to the specified test suite will be uploaded.</span></span>
<span data-ttu-id="726f9-320">**``testcase_id``** Tutti i file appartenenti ai test case verranno caricati.</span><span class="sxs-lookup"><span data-stu-id="726f9-320">**``testcase_id``** All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="726f9-321">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-321">Examples</span></span>
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a><span data-ttu-id="726f9-322">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="726f9-322">uploadrecording</span></span>
<span data-ttu-id="726f9-323">Carica solo il file di registrazione appartenente ai test case specificati.</span><span class="sxs-lookup"><span data-stu-id="726f9-323">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a><span data-ttu-id="726f9-324">Parametri obbligatori</span><span class="sxs-lookup"><span data-stu-id="726f9-324">Required parameters</span></span>
<span data-ttu-id="726f9-325">**``testcase_id``** Il file di registrazione appartenente ai test case specificati verrà caricato.</span><span class="sxs-lookup"><span data-stu-id="726f9-325">**``testcase_id``** Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="726f9-326">Esempi</span><span class="sxs-lookup"><span data-stu-id="726f9-326">Examples</span></span>
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a><span data-ttu-id="726f9-327">usage</span><span class="sxs-lookup"><span data-stu-id="726f9-327">usage</span></span>
<span data-ttu-id="726f9-328">Mostra due modi per invocare questa applicazione: uno che utilizza un file di impostazioni predefinito, un altro che fornisce un file di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="726f9-328">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a><span data-ttu-id="726f9-329">Esempi di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="726f9-329">Windows PowerShell examples</span></span>

[!IMPORTANT] <span data-ttu-id="726f9-330">Gli script di esempio seguenti sono forniti COSÌ COME SONO a scopo illustrativo e non sono supportati da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="726f9-330">The example scripts below are provided AS IS for illustration purposes and are not supported by Microsoft.</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="726f9-331">Eseguire un test case in un ciclo</span><span class="sxs-lookup"><span data-stu-id="726f9-331">Run a test case in a loop</span></span>

<span data-ttu-id="726f9-332">Si ha uno script di test che crea un nuovo cliente.</span><span class="sxs-lookup"><span data-stu-id="726f9-332">You have a test script that creates a new customer.</span></span> <span data-ttu-id="726f9-333">Tramite lo script, questo test case può essere eseguito in un ciclo randomizzando i seguenti dati prima dell'esecuzione di ogni iterazione:</span><span class="sxs-lookup"><span data-stu-id="726f9-333">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="726f9-334">ID cliente</span><span class="sxs-lookup"><span data-stu-id="726f9-334">Customer ID</span></span>
- <span data-ttu-id="726f9-335">Nome cliente</span><span class="sxs-lookup"><span data-stu-id="726f9-335">Customer name</span></span>
- <span data-ttu-id="726f9-336">Indirizzo cliente</span><span class="sxs-lookup"><span data-stu-id="726f9-336">Customer address</span></span>

<span data-ttu-id="726f9-337">L'ID cliente sarà in formato *ATCUS\<number\>*, dove \<number\> è un valore compreso tra **000000001** e **999999999**.</span><span class="sxs-lookup"><span data-stu-id="726f9-337">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="726f9-338">Nel seguente esempio viene utilizzato un parametro **start** per definire il primo numero utilizzato.</span><span class="sxs-lookup"><span data-stu-id="726f9-338">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="726f9-339">Un secondo parametro, **nr**, viene utilizzato per definire il numero di clienti che devono essere creati.</span><span class="sxs-lookup"><span data-stu-id="726f9-339">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="726f9-340">Per ogni iterazione, i parametri nel file di parametri di Excel vengono modificati utilizzando una funzione UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="726f9-340">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="726f9-341">La riga di comando di RSAT viene quindi richiamata in una funzione RunTestCase.</span><span class="sxs-lookup"><span data-stu-id="726f9-341">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="726f9-342">Aprire Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in modalità amministratore e incollare il seguente codice nella finestra denominata **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="726f9-342">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="726f9-343">Eseguire uno script che dipende dai dati in Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="726f9-343">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="726f9-344">Nell'esempio seguente viene utilizzata una chiamata Open Data Protocol (OData) per individuare lo stato di un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="726f9-344">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="726f9-345">Se lo stato non è **fatturato**, è ad esempio possibile chiamare un test case RSAT che registra la fattura.</span><span class="sxs-lookup"><span data-stu-id="726f9-345">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

```xpp
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```
