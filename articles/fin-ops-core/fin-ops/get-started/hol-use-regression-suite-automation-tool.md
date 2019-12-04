---
title: Esercitazione sull'utilizzo di Regression Suite Automation Tool
description: In questo argomento viene illustrato come utilizzare lo strumento Regression Suite Automation Tool (RSAT). Vengono descritte varie funzionalità e forniti esempi che utilizzano lo script avanzato.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 654685a382ca5f3f462ad8a9c506b51b52c3758c
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811651"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="79233-104">Esercitazione sull'utilizzo di Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="79233-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="79233-105">Utilizzare gli strumenti del browser Internet per scaricare e salvare questa pagina in formato PDF.</span><span class="sxs-lookup"><span data-stu-id="79233-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="79233-106">Questa esercitazione descrive alcune delle funzionalità avanzate di Regression Suite Automation Tool (RSAT), include un'assegnazione demo e fornisce suggerimenti chiave e la strategia da adottare.</span><span class="sxs-lookup"><span data-stu-id="79233-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="features-of-rsattask-recorder"></a><span data-ttu-id="79233-107">Funzionalità di RSAT/Registrazione attività</span><span class="sxs-lookup"><span data-stu-id="79233-107">Features of RSAT/Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="79233-108">Convalidare un valore di campo</span><span class="sxs-lookup"><span data-stu-id="79233-108">Validate a field value</span></span>

<span data-ttu-id="79233-109">Per informazioni su questa funzionalità, vedere [Creare una nuova registrazione attività che dispone di una funzione Convalida](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span><span class="sxs-lookup"><span data-stu-id="79233-109">For information about this feature, see the [Create a new task recording that has a Validate function](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span></span>

### <a name="saved-variable"></a><span data-ttu-id="79233-110">Variabile salvata</span><span class="sxs-lookup"><span data-stu-id="79233-110">Saved variable</span></span>

<span data-ttu-id="79233-111">Per informazioni su queste funzionalità, vedere [Modificare una registrazione attività esistente per creare una variabile salvata](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span><span class="sxs-lookup"><span data-stu-id="79233-111">For information about this feature, see the [Modify an existing task recording to create a saved variable](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="79233-112">Test case derivato</span><span class="sxs-lookup"><span data-stu-id="79233-112">Derived test case</span></span>

1. <span data-ttu-id="79233-113">Aprire Regression Suite Automation Tool (RSAT) e selezionare entrambi i test case creati in [Esercitazione sull'impostazione e l'installazione di Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="79233-113">Open Regression suite automation tool (RSAT), and select both the test cases that you created in [Set up and install Regression suite automation tool tutorial](./hol-set-up-regression-suite-automation-tool.md).</span></span>
2. <span data-ttu-id="79233-114">Selezionare **Nuovo \> Crea test case derivato**.</span><span class="sxs-lookup"><span data-stu-id="79233-114">Select **New \> Create derived test case**.</span></span>

    ![Comando Crea test case derivato nel menu Nuovo](./media/use_rsa_tool_01.png)

3. <span data-ttu-id="79233-116">Viene visualizzato un messaggio indicante che un test case derivato verrà creato per ogni test case selezionato nel gruppo di test corrente e che ogni test case derivato disporrà di una propria copia del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="79233-116">You receive a message that states that a derived test case will be created for each selected test case in the current test suite, and that each derived test case will have its own copy of the Excel parameter file.</span></span> <span data-ttu-id="79233-117">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="79233-117">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79233-118">Quando si esegue un test case derivato, questo utilizza la registrazione attività del relativo test case padre e la propria copia del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="79233-118">When you run a derived test case, it uses the task recording of its parent test case and its own copy of the Excel parameter file.</span></span> <span data-ttu-id="79233-119">In questo modo, è possibile eseguire lo stesso test con parametri differenti, senza dover avere più di una registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="79233-119">In this way, you can run the same test with different parameters, without having to maintain more than one task recording.</span></span> <span data-ttu-id="79233-120">Un test case derivato non deve far parte dello stesso gruppo di test come test case padre.</span><span class="sxs-lookup"><span data-stu-id="79233-120">A derived test case doesn't have to be part of the same test suite as its parent test case.</span></span>

    ![Finestra di messaggio](./media/use_rsa_tool_02.png)

    <span data-ttu-id="79233-122">Vengono creati due ulteriori test case derivati e la relativa casella di controllo **Derivato?** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="79233-122">Two additional derived test cases are created, and the **Derived?** check box is selected for them.</span></span>

    ![Test case derivati creati](./media/use_rsa_tool_03.png)

    <span data-ttu-id="79233-124">Un test case derivato viene automaticamente creato in Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="79233-124">A derived test case is automatically created in Azure DevOps.</span></span> <span data-ttu-id="79233-125">È un elemento secondario del test case **Creare un nuovo prodotto** e viene contrassegnato con una parola chiave speciale: **RSAT: DerivedTestSteps**.</span><span class="sxs-lookup"><span data-stu-id="79233-125">It's a child item of the **Create a new product** test case and is tagged with a special keyword: **RSAT:DerivedTestSteps**.</span></span> <span data-ttu-id="79233-126">Questi test case vengono inoltre aggiunti automaticamente al piano di test in Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="79233-126">These test cases are also automatically added to the test plan in Azure DevOps.</span></span>

    ![Parola chiave RSAT:DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > <span data-ttu-id="79233-128">Se, per un qualsiasi motivo, i test case derivati creati non sono nell'ordine corretto, accedere a Azure DevOps e riordinare i test case nel gruppo di test, di modo che RSAT possa eseguirli nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="79233-128">If, for any reason, the derived test cases that are created aren't in the correct order, go to Azure DevOps, and reorder the test cases in the test suite, so that RSAT can run them in the correct order.</span></span>

4. <span data-ttu-id="79233-129">Selezionare i test case derivati, quindi selezionare **Modifica** per aprire i file di parametri di Excel corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="79233-129">Select the derived test cases, and then select **Edit** to open the corresponding Excel parameter files.</span></span>
5. <span data-ttu-id="79233-130">Modificare questi file di parametri di Excel esattamente come i file padre.</span><span class="sxs-lookup"><span data-stu-id="79233-130">Edit these Excel parameter files in the same way that you edited the parent files.</span></span> <span data-ttu-id="79233-131">In altre parole, assicurarsi che l'ID prodotto sia impostato di modo che venga generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="79233-131">In other words, make sure that the product ID is set so that it's automatically generated.</span></span> <span data-ttu-id="79233-132">Verificare inoltre che la variabile salvata venga copiata nei campi appropriati.</span><span class="sxs-lookup"><span data-stu-id="79233-132">Also make sure that the saved variable is copied to the relevant fields.</span></span>
6. <span data-ttu-id="79233-133">Nella scheda **Generale** di entrambi i file di parametri di Excel, impostare il valore del campo **Società** su **USSI**, di modo che i test case derivati siano eseguiti per una persona giuridica differente rispetto al test case padre.</span><span class="sxs-lookup"><span data-stu-id="79233-133">On the **General** tab of both Excel parameter files, update the value of the **Company** field to **USSI**, so that the derived test cases will be run against a different legal entity than the parent test case.</span></span> <span data-ttu-id="79233-134">Per eseguire i test case per un utente specifico (o per il ruolo associato a un utente specifico), è possibile aggiornare il valore del campo **Verifica utente**.</span><span class="sxs-lookup"><span data-stu-id="79233-134">To run the test cases against a specific user (or the role that is associated with a specific user), you can update the value of the **Test User** field.</span></span>
7. <span data-ttu-id="79233-135">Selezionare **Esegui** e verificare che il prodotto venga creato nelle persone giuridiche USMF e USSI.</span><span class="sxs-lookup"><span data-stu-id="79233-135">Select **Run**, and validate that the product is created in both the USMF legal entity and the USSI legal entity.</span></span>

### <a name="validate-notifications"></a><span data-ttu-id="79233-136">Convalidare le notifiche</span><span class="sxs-lookup"><span data-stu-id="79233-136">Validate notifications</span></span>

<span data-ttu-id="79233-137">Questa funzionalità può essere utilizzata per convalidare un'azione avvenuta.</span><span class="sxs-lookup"><span data-stu-id="79233-137">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="79233-138">Ad esempio, quando un ordine di produzione viene creato, valutato e quindi avviato, l'app visualizza un messaggio "Produzione - Avvio" per notificare all'utente che l'ordine di produzione è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="79233-138">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Notifica Produzione - Avvio](./media/use_rsa_tool_05.png)

<span data-ttu-id="79233-140">È possibile convalidare questo messaggio mediante RSAT digitando il testo del messaggio nella scheda **MessageValidation** del file di parametri di Excel per la registrazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="79233-140">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Scheda Convalida messaggio](./media/use_rsa_tool_06.png)

<span data-ttu-id="79233-142">Dopo l'esecuzione del test case, il messaggio nel file di parametri di Excel viene confrontato al messaggio visualizzato.</span><span class="sxs-lookup"><span data-stu-id="79233-142">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="79233-143">Se i messaggi non corrispondono, il test case non avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="79233-143">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="79233-144">È possibile immettere più di un messaggio nella scheda **Convalida messaggio** del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="79233-144">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="79233-145">I messaggi possono anche essere messaggi di errore o di avviso anziché messaggi informativi.</span><span class="sxs-lookup"><span data-stu-id="79233-145">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="validate-values-by-using-operators"></a><span data-ttu-id="79233-146">Convalidare i valori utilizzando operatori</span><span class="sxs-lookup"><span data-stu-id="79233-146">Validate values by using operators</span></span>

<span data-ttu-id="79233-147">Nelle versioni precedenti di RSAT, è possibile convalidare i valori solo se un valore di controllo è uguale a un valore previsto.</span><span class="sxs-lookup"><span data-stu-id="79233-147">In previous versions of RSAT, you could validate values only if a control value equaled an expected value.</span></span> <span data-ttu-id="79233-148">La nuova funzionalità consente di verificare se una variabile non è uguale a, è minore di o è maggiore di un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="79233-148">The new feature lets you validate that a variable isn't equal to, is less than, or is more than a specified value.</span></span>

- <span data-ttu-id="79233-149">Per utilizzare questa funzionalità, aprire il file **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** nella cartella di installazione di RSAT (ad esempio **C:\\Programmi (x86)\\Regression Suite Automation Tool**) e modificare il valore dell'elemento seguente da **false** a **true**.</span><span class="sxs-lookup"><span data-stu-id="79233-149">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    <span data-ttu-id="79233-150">Nel file di parametri di Excel, viene visualizzato un nuovo campo **Operatore**.</span><span class="sxs-lookup"><span data-stu-id="79233-150">In the Excel parameter file, a new **Operator** field appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79233-151">Se si utilizza una versione precedente di RSAT, è necessario generare nuovi file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="79233-151">If you've been using an older version of RSAT, you must generate new Excel parameter files.</span></span>

    ![Campo Operatore](./media/use_rsa_tool_07.png)

<span data-ttu-id="79233-153">Nell'esempio seguente viene illustrato come utilizzare questa funzionalità per verificare se le scorte disponibili sono maggiori di 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="79233-153">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="79233-154">Nei dati demo della società **USMF**, creare una registrazione attività che includa i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="79233-154">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="79233-155">Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="79233-155">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="79233-156">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="79233-156">Use the Quick Filter to find records.</span></span> <span data-ttu-id="79233-157">Ad esempio, filtrare in base al valore **1000** nel campo **Numero articolo**.</span><span class="sxs-lookup"><span data-stu-id="79233-157">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="79233-158">Selezionare **Scorte disponibili**.</span><span class="sxs-lookup"><span data-stu-id="79233-158">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="79233-159">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="79233-159">Use the Quick Filter to find records.</span></span> <span data-ttu-id="79233-160">Ad esempio, filtrare in base al valore **1** nel campo **Sito**.</span><span class="sxs-lookup"><span data-stu-id="79233-160">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="79233-161">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="79233-161">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="79233-162">Verificare che il valore del campo **Totale disponibile** sia **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="79233-162">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="79233-163">Salvare la registrazione attività nella libreria BPM in LCS e sincronizzarla con Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="79233-163">Save the task recording to the BPM library in LCS, and sync it to Azure DevOps.</span></span>
3. <span data-ttu-id="79233-164">Aggiungere il test case al piano di test e caricare il test case in RSAT.</span><span class="sxs-lookup"><span data-stu-id="79233-164">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="79233-165">Apre il file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="79233-165">Open the Excel parameter file.</span></span> <span data-ttu-id="79233-166">Nella scheda **InventOnhandItem** verrà visualizzata una sezione **Convalida InventOnhandItem** che include un campo **Operatore**.</span><span class="sxs-lookup"><span data-stu-id="79233-166">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Campo Operatore](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="79233-168">Per verificare se le scorte disponibili saranno sempre maggiori di 0, modificare il valore del campo **Valore** da **411** a **0** e il valore del campo **Operatore** dal segno uguale (**=**) al segno maggiore di (**\>**).</span><span class="sxs-lookup"><span data-stu-id="79233-168">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Valori dei campi Valore e Operatore modificati](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="79233-170">Salvare e chiudere il file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="79233-170">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="79233-171">Selezionare **Carica** per salvare le modifiche apportate al file di parametri di Excel in Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="79233-171">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="79233-172">A questo punto, se il valore del campo **Totale disponibile** per l'articolo specificato nelle scorte è maggiore di 0 (zero), i test avranno esito positivo, indipendentemente dal valore delle scorte disponibili effettivo.</span><span class="sxs-lookup"><span data-stu-id="79233-172">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="generator-logs"></a><span data-ttu-id="79233-173">Registri di generatori</span><span class="sxs-lookup"><span data-stu-id="79233-173">Generator logs</span></span>

<span data-ttu-id="79233-174">Questa funzionalità crea una cartella contenente i registri dei test case eseguiti.</span><span class="sxs-lookup"><span data-stu-id="79233-174">This feature creates a folder that contains the logs of the test cases that have been run.</span></span>

- <span data-ttu-id="79233-175">Per utilizzare questa funzionalità, aprire il file **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** nella cartella di installazione di RSAT (ad esempio **C:\\Programmi (x86)\\Regression Suite Automation Tool**) e modificare il valore dell'elemento seguente da **false** a **true**.</span><span class="sxs-lookup"><span data-stu-id="79233-175">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```
    <add key="LogGeneration" value="false" />
    ```

<span data-ttu-id="79233-176">Dopo l'esecuzione dei test case, è possibile trovare i file di registro in **C:\\Utenti\\\<Nome utente\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span><span class="sxs-lookup"><span data-stu-id="79233-176">After the test cases are run, you can find the log files under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span></span>

![Cartella GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> <span data-ttu-id="79233-178">Se dei test case erano presenti prima di modificare il valore nel file .config, i registri non verranno generati per quei test case fino a che non si generano nuovi file di esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="79233-178">If there were existing test cases before you changed the value in the .config file, logs won't be generated for those test cases until you generate new test execution files.</span></span>
> 
> ![Comando Genera solo file di esecuzione test nel menu Nuovo](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a><span data-ttu-id="79233-180">Snapshot</span><span class="sxs-lookup"><span data-stu-id="79233-180">Snapshot</span></span>

<span data-ttu-id="79233-181">Questa funzionalità consente di acquisire schermate dei passaggi eseguiti durante la registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="79233-181">This feature takes screenshots of the steps that were performed during task recording.</span></span>

- <span data-ttu-id="79233-182">Per utilizzare questa funzionalità, aprire il file **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** nella cartella di installazione di RSAT (ad esempio **C:\\Programmi (x86)\\Regression Suite Automation Tool**) e modificare il valore dell'elemento seguente da **false** a **true**.</span><span class="sxs-lookup"><span data-stu-id="79233-182">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="79233-183">In **C:\\Utenti\\\<Nome utente\>\\AppData\\Roaming\\regressionTool\\playback** viene creata una cartella distinta per ogni test case eseguito.</span><span class="sxs-lookup"><span data-stu-id="79233-183">Under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

![Cartella degli snapshot per un test case](./media/use_rsa_tool_12.png)

<span data-ttu-id="79233-185">In ognuna di queste cartelle, è possibile trovare gli snapshot dei passaggi eseguiti durante l'esecuzione di test case.</span><span class="sxs-lookup"><span data-stu-id="79233-185">In each of these folders, you can find snapshots of the steps that were performed while the test cases were run.</span></span>

![File di snapshot](./media/use_rsa_tool_13.png)

## <a name="assignment"></a><span data-ttu-id="79233-187">Assegnazione</span><span class="sxs-lookup"><span data-stu-id="79233-187">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="79233-188">Scenario</span><span class="sxs-lookup"><span data-stu-id="79233-188">Scenario</span></span>

1. <span data-ttu-id="79233-189">Il responsabile della progettazione dei prodotti crea un nuovo prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="79233-189">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="79233-190">Il responsabile produzione inizia un ordine di produzione per portare il livello scorte a due pezzi.</span><span class="sxs-lookup"><span data-stu-id="79233-190">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="79233-191">La produzione inizia e termina l'ordine di produzione e verifica che la quantità disponibile sia due pezzi.</span><span class="sxs-lookup"><span data-stu-id="79233-191">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="79233-192">Il team delle vendite riceve un ordine per quattro pezzi del nuovo prodotto.</span><span class="sxs-lookup"><span data-stu-id="79233-192">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="79233-193">Di conseguenza, il team delle vendite aggiorna i fabbisogni netti tramite il piano dinamico.</span><span class="sxs-lookup"><span data-stu-id="79233-193">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="79233-194">Poiché non è disponibile ulteriore capacità, i criteri di ordine predefiniti sono impostati su "acquista anziché produrre".</span><span class="sxs-lookup"><span data-stu-id="79233-194">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="79233-195">Di conseguenza, viene creato un ordine fornitore pianificato.</span><span class="sxs-lookup"><span data-stu-id="79233-195">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="79233-196">L'acquirente aggiunge un fornitore, stabilizza l'ordine fornitore pianificato e conferma l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="79233-196">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="79233-197">Quando le merci acquistate arrivano presso il punto vendita, l'operatore cerca l'ordine fornitore correlato e riceve le merci.</span><span class="sxs-lookup"><span data-stu-id="79233-197">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="79233-198">Poiché l'ordine è ora completato, le merci possono essere prelevate e imballate a fronte dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="79233-198">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="79233-199">L'ufficio contabilità registra la fattura di acquisto e quella di vendita.</span><span class="sxs-lookup"><span data-stu-id="79233-199">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="79233-200">Nella figura seguente è illustrato il flusso di questo scenario.</span><span class="sxs-lookup"><span data-stu-id="79233-200">The following illustration shows the flow for this scenario.</span></span>

![Flusso dello scenario demo](./media/use_rsa_tool_14.png)

<span data-ttu-id="79233-202">Nella figura seguente sono illustrati i processi aziendali di questo scenario in RSAT.</span><span class="sxs-lookup"><span data-stu-id="79233-202">The following illustration shows the business processes for this scenario in RSAT.</span></span>

![Processi aziendali per lo scenario demo](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="79233-204">Strategia - Suggerimenti chiave</span><span class="sxs-lookup"><span data-stu-id="79233-204">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="79233-205">Dati</span><span class="sxs-lookup"><span data-stu-id="79233-205">Data</span></span>

- <span data-ttu-id="79233-206">Assicurarsi di disporre di volumi di dati rappresentativi (una copia dei dati della configurazione prodotto/Golden oltre ai dati migrati).</span><span class="sxs-lookup"><span data-stu-id="79233-206">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="79233-207">Quando si generano nuovi dati tramite Registrazione attività, creare nomi di test che non saranno in conflitto con i nomi esistenti (ad esempio, utilizzare un prefisso come **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="79233-207">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="79233-208">Utilizzare il ripristino temporizzato di Azure per eseguire di nuovo i test in ambienti non di livello 1.</span><span class="sxs-lookup"><span data-stu-id="79233-208">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="79233-209">Sebbene sia possibile utilizzare le funzioni **RANDOM** e **NOW** di Excel per generare una combinazione univoca, questa operazione risulta parecchio complessa.</span><span class="sxs-lookup"><span data-stu-id="79233-209">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="79233-210">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="79233-210">Here is an example.</span></span>

    ```
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="79233-211">Registrazione attività</span><span class="sxs-lookup"><span data-stu-id="79233-211">Task recorder</span></span>

- <span data-ttu-id="79233-212">Definire gli scenari prima di iniziare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="79233-212">Define scenarios before you start recording.</span></span> <span data-ttu-id="79233-213">Un progetto ben gestito comporta scenari di test predefiniti.</span><span class="sxs-lookup"><span data-stu-id="79233-213">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="79233-214">Per generare un test case, prendere in considerazione la prevedibilità del risultato di questi scenari di test.</span><span class="sxs-lookup"><span data-stu-id="79233-214">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="79233-215">Dividere le registrazioni se vengono eseguite da ruoli differenti oppure in caso di tempo di attesa o di evento esterno prima del passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="79233-215">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="79233-216">Non selezionare i valori negli elenchi.</span><span class="sxs-lookup"><span data-stu-id="79233-216">Avoid selecting values in lists.</span></span> <span data-ttu-id="79233-217">Utilizzare invece formati di testo, ad esempio **FIFO**, **AudioRM** e **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="79233-217">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="79233-218">Quando si esegue la selezione in un elenco, viene registrata la posizione del valore nell'elenco e non il valore stesso.</span><span class="sxs-lookup"><span data-stu-id="79233-218">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="79233-219">Se si aggiungono degli elementi a tale elenco, la posizione del valore può cambiare.</span><span class="sxs-lookup"><span data-stu-id="79233-219">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="79233-220">Di conseguenza, la registrazione utilizzerà un parametro differente e ciò potrebbe influenzare il resto dello scenario.</span><span class="sxs-lookup"><span data-stu-id="79233-220">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="79233-221">Prendere in considerazione il comportamento multiutente.</span><span class="sxs-lookup"><span data-stu-id="79233-221">Think about multi-user behavior.</span></span> <span data-ttu-id="79233-222">Ad esempio, non presupporre che l'ordine cliente appena creato verrà sempre selezionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="79233-222">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="79233-223">Invece, utilizzare sempre il filtro per trovare l'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="79233-223">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="79233-224">Utilizzare la funzione Copia di Registrazione attività per salvare il nome di un prodotto appena creato di modo che possa essere utilizzato in test case concatenati.</span><span class="sxs-lookup"><span data-stu-id="79233-224">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="79233-225">Utilizzare la funzione Convalida di Registrazione attività per impostare checkpoint con cui verificare la corretta esecuzione dei passaggi.</span><span class="sxs-lookup"><span data-stu-id="79233-225">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="79233-226">RSAT</span><span class="sxs-lookup"><span data-stu-id="79233-226">RSAT</span></span>

- <span data-ttu-id="79233-227">Per eseguire il test in un'altra società, è possibile modificare la società nella scheda **Generale** del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="79233-227">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="79233-228">Assicurarsi che le impostazioni e i dati siano disponibili nella nuova società selezionata.</span><span class="sxs-lookup"><span data-stu-id="79233-228">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="79233-229">È possibile modificare l'utente dei test nella scheda **Generale** del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="79233-229">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="79233-230">Specificare l'ID di posta elettronica dell'utente che esegue il test case.</span><span class="sxs-lookup"><span data-stu-id="79233-230">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="79233-231">In questo modo, il test case può essere eseguito utilizzando le autorizzazioni di sicurezza dell'utente specificato.</span><span class="sxs-lookup"><span data-stu-id="79233-231">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="79233-232">Per ritardare l'esecuzione del test, è possibile definire una pausa nella scheda **Generale** del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="79233-232">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="79233-233">Questa pausa può essere utilizzata in un processo batch (ad esempio se un flusso di lavoro deve essere eseguito per poter eseguire il passaggio successivo).</span><span class="sxs-lookup"><span data-stu-id="79233-233">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="79233-234">Script avanzato</span><span class="sxs-lookup"><span data-stu-id="79233-234">Advanced scripting</span></span>

### <a name="command-line"></a><span data-ttu-id="79233-235">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="79233-235">Command line</span></span>

<span data-ttu-id="79233-236">RSAT può essere chiamato da una finestra **Prompt dei comandi**.</span><span class="sxs-lookup"><span data-stu-id="79233-236">RSAT can be called from a **Command Prompt** window.</span></span>

> [!NOTE]
> <span data-ttu-id="79233-237">Verificare che la variabile di ambiente **TestRoot** sia impostata sul percorso di installazione di RSAT.</span><span class="sxs-lookup"><span data-stu-id="79233-237">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="79233-238">(in Microsoft Windows, aprire **Pannello di controllo**, selezionare **Sistema e sicurezza \> Sistema \> Impostazioni di sistema avanzate** e quindi **Variabili di ambiente**).</span><span class="sxs-lookup"><span data-stu-id="79233-238">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="79233-239">Aprire una finestra **Prompt dei comandi** come amministratore.</span><span class="sxs-lookup"><span data-stu-id="79233-239">Open a **Command Prompt** window as an admin.</span></span>
2. <span data-ttu-id="79233-240">Eseguire lo strumento dalla directory di installazione.</span><span class="sxs-lookup"><span data-stu-id="79233-240">Run the tool from the installation directory.</span></span>

    ```
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="79233-241">Elencare tutti i comandi.</span><span class="sxs-lookup"><span data-stu-id="79233-241">List all commands.</span></span>

    ```
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a><span data-ttu-id="79233-242">Esempi di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79233-242">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="79233-243">Eseguire un test case in un ciclo</span><span class="sxs-lookup"><span data-stu-id="79233-243">Run a test case in a loop</span></span>

<span data-ttu-id="79233-244">Si ha uno script di test che crea un nuovo cliente.</span><span class="sxs-lookup"><span data-stu-id="79233-244">You have a test script that creates a new customer.</span></span> <span data-ttu-id="79233-245">Tramite lo script, questo test case può essere eseguito in un ciclo randomizzando i seguenti dati prima dell'esecuzione di ogni iterazione:</span><span class="sxs-lookup"><span data-stu-id="79233-245">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="79233-246">ID cliente</span><span class="sxs-lookup"><span data-stu-id="79233-246">Customer ID</span></span>
- <span data-ttu-id="79233-247">Nome cliente</span><span class="sxs-lookup"><span data-stu-id="79233-247">Customer name</span></span>
- <span data-ttu-id="79233-248">Indirizzo cliente</span><span class="sxs-lookup"><span data-stu-id="79233-248">Customer address</span></span>

<span data-ttu-id="79233-249">L'ID cliente sarà in formato *ATCUS\<numero\>*, dove \<numero\> è un valore compreso tra **000000001** e **999999999**.</span><span class="sxs-lookup"><span data-stu-id="79233-249">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="79233-250">Nel seguente esempio viene utilizzato un parametro **start** per definire il primo numero utilizzato.</span><span class="sxs-lookup"><span data-stu-id="79233-250">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="79233-251">Un secondo parametro, **nr**, viene utilizzato per definire il numero di clienti che devono essere creati.</span><span class="sxs-lookup"><span data-stu-id="79233-251">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="79233-252">Per ogni iterazione, i parametri nel file di parametri di Excel vengono modificati utilizzando una funzione UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="79233-252">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="79233-253">La riga di comando di RSAT viene quindi richiamata in una funzione RunTestCase.</span><span class="sxs-lookup"><span data-stu-id="79233-253">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="79233-254">Aprire Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in modalità amministratore e incollare il seguente codice nella finestra denominata **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="79233-254">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

```
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
$excelFilename = "full path to excel file parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="79233-255">Eseguire uno script che dipende dai dati in Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="79233-255">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="79233-256">Nell'esempio seguente viene utilizzata una chiamata Open Data Protocol (OData) per individuare lo stato di un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="79233-256">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="79233-257">Se lo stato non è **fatturato**, è ad esempio possibile chiamare un test case RSAT che registra la fattura.</span><span class="sxs-lookup"><span data-stu-id="79233-257">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

```
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
