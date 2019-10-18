---
title: Miglioramenti nella tracciatura dei risultati dei report ER generati e nella comparazione degli stessi con i valori di base
description: In questo argomento vengono fornite informazioni sul miglioramento della funzionalità di base ER in Microsoft Dynamics 365 for Finance and Operations versione 10.0.3 (giugno 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: a260be0f8659106907b26bf69bee3b33b09d0c24
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181337"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a><span data-ttu-id="fb600-103">Miglioramenti nella tracciatura dei risultati dei report ER generati e nella comparazione degli stessi con i valori di base</span><span class="sxs-lookup"><span data-stu-id="fb600-103">Improvements in tracing the results of generated ER reports and comparing them with baseline values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="fb600-104">In questo argomento viene descritto il primo set di miglioramenti apportati alle funzionalità di base del framework di report elettronici (ER).</span><span class="sxs-lookup"><span data-stu-id="fb600-104">This topic describes the first set of improvements that have been made to the baseline feature of the Electronic reporting (ER) framework.</span></span> <span data-ttu-id="fb600-105">Questi miglioramenti sono disponibili in Microsoft Dynamics 365 for Finance and Operations versione 10.0.3 (giugno 2019) e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="fb600-105">These improvements are available in Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (June 2019) and later.</span></span>

## <a name="automate-the-setting-of-baseline-rules"></a><span data-ttu-id="fb600-106">Automatizzare l'impostazione delle regole di base</span><span class="sxs-lookup"><span data-stu-id="fb600-106">Automate the setting of baseline rules</span></span>

<span data-ttu-id="fb600-107">L'argomento [Generare la traccia dei risultati dei report generati e confrontarli con i valori di base](er-trace-reports-compare-baseline.md) descrive il modo in cui configurare il framework ER per raccogliere informazioni sulle esecuzioni del formato ER e valutare i risultati di tali esecuzioni.</span><span class="sxs-lookup"><span data-stu-id="fb600-107">The [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic explains how to configure the ER framework to collect information about ER format executions and evaluate the results of those executions.</span></span> <span data-ttu-id="fb600-108">L'esempio in questo argomento illustra i passaggi che devono essere completati.</span><span class="sxs-lookup"><span data-stu-id="fb600-108">The example in this topic shows the steps that must be completed.</span></span>

<span data-ttu-id="fb600-109">Di seguito sono riportati alcuni passaggi:</span><span class="sxs-lookup"><span data-stu-id="fb600-109">Here are some of the steps:</span></span>

- <span data-ttu-id="fb600-110">Eseguire un formato ER per generare un file in uscita e archiviare il file localmente.</span><span class="sxs-lookup"><span data-stu-id="fb600-110">Run an ER format to generate an outbound file, and store the file locally.</span></span>
- <span data-ttu-id="fb600-111">Aggiungere localmente il file archiviato come allegato della base aggiunta per un formato ER.</span><span class="sxs-lookup"><span data-stu-id="fb600-111">Add the locally stored file as an attachment of the baseline that was added for an ER format.</span></span>
- <span data-ttu-id="fb600-112">Configurare la regola di base per la base aggiunta.</span><span class="sxs-lookup"><span data-stu-id="fb600-112">Configure the baseline rule for the added baseline.</span></span> <span data-ttu-id="fb600-113">Questa configurazione prevede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb600-113">This configuration includes the following steps:</span></span>

    - <span data-ttu-id="fb600-114">Specificare un elemento del formato ER utilizzato per generare un file in uscita.</span><span class="sxs-lookup"><span data-stu-id="fb600-114">Specify an ER format element that is used to generate an outbound file.</span></span>
    - <span data-ttu-id="fb600-115">Selezionare l'allegato che fa riferimento al file in uscita generato.</span><span class="sxs-lookup"><span data-stu-id="fb600-115">Select the attachment that refers to the generated outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="fb600-116">Questi passaggi devono essere eseguiti manualmente, anche se le nuove funzionalità ER ne consentono l'automatizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb600-116">These steps must be done manually, even though the new ER capabilities enable them to be automated.</span></span> <span data-ttu-id="fb600-117">Per ulteriori informazioni su questa funzionalità, completare l'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fb600-117">To learn more about this feature, complete the following example.</span></span>

## <a name="example-automate-the-setting-of-baseline-rules"></a><span data-ttu-id="fb600-118">Esempio: automatizzare l'impostazione delle regole di base</span><span class="sxs-lookup"><span data-stu-id="fb600-118">Example: Automate the setting of baseline rules</span></span>

<span data-ttu-id="fb600-119">Per completare i passaggi in questo esempio, completare dapprima i passaggi dell'esempio nell'argomento [Generare la traccia dei risultati dei report generati e confrontarli con i valori di base](er-trace-reports-compare-baseline.md) fino alla sezione "Aggiungere una nuova base per un formato ER progettato".</span><span class="sxs-lookup"><span data-stu-id="fb600-119">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, up through the "Add a new baseline for a designed ER format" section.</span></span>

### <a name="review-added-baseline"></a><span data-ttu-id="fb600-120">Esaminare la base aggiunta</span><span class="sxs-lookup"><span data-stu-id="fb600-120">Review added baseline</span></span>

1. <span data-ttu-id="fb600-121">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="fb600-121">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fb600-122">Selezionare **Basi**.</span><span class="sxs-lookup"><span data-stu-id="fb600-122">Select **Baselines**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fb600-123">Il pulsante **Basi** nel riquadro azioni è disponibile solo quando il parametro dell'utente ER **Esegui in modalità di debug** è attivato per la società corrente.</span><span class="sxs-lookup"><span data-stu-id="fb600-123">The **Baselines** button on the Action Pane is available only when the **Run in debug mode** ER user parameter is turned on for the current company.</span></span>

<span data-ttu-id="fb600-124">La base è stata aggiunta per il formato **Formato per ottenere basi ER** selezionato, ma non ancora le regole di base per tale base.</span><span class="sxs-lookup"><span data-stu-id="fb600-124">The baseline has been added for the selected **Format to learn ER baselines** format, but the baseline rules haven't yet been added for this baseline.</span></span>

<span data-ttu-id="fb600-125">![Pagina Basi del formato per la creazione di report elettronici](media/GER-BaselineSample-AddBaseline2.PNG "Schermata della pagina Basi del formato per la creazione di report elettronici")</span><span class="sxs-lookup"><span data-stu-id="fb600-125">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline2.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="fb600-126">Creare un nuova regola di base</span><span class="sxs-lookup"><span data-stu-id="fb600-126">Make a new baseline rule</span></span>

1. <span data-ttu-id="fb600-127">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="fb600-127">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fb600-128">Nella struttura espandere **Modello per ottenere basi ER**.</span><span class="sxs-lookup"><span data-stu-id="fb600-128">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="fb600-129">Nella struttura, selezionare **Modello per ottenere basi ER\\Formato per ottenere basi ER**.</span><span class="sxs-lookup"><span data-stu-id="fb600-129">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="fb600-130">Nella scheda dettaglio **Versioni** selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="fb600-130">On the **Versions** FastTab, select **Run**.</span></span>
5. <span data-ttu-id="fb600-131">Nel campo **Immettere ID**, immettere **1**.</span><span class="sxs-lookup"><span data-stu-id="fb600-131">In the **Enter Id** field, enter **1**.</span></span>
6. <span data-ttu-id="fb600-132">Impostare l'opzione **Creare file di base** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="fb600-132">Set the **Make baseline files** option to **Yes**.</span></span>
7. <span data-ttu-id="fb600-133">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb600-133">Select **OK**.</span></span>

    <span data-ttu-id="fb600-134">![Pagina Parametri per la creazione di report elettronici](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Schermata della pagina Parametri per la creazione di report elettronici")</span><span class="sxs-lookup"><span data-stu-id="fb600-134">![Electronic report parameters dialog box](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Screenshot of the Electronic report parameters dialog box")</span></span>

8. <span data-ttu-id="fb600-135">Selezionare **Basi**.</span><span class="sxs-lookup"><span data-stu-id="fb600-135">Select **Baselines**.</span></span>

    <span data-ttu-id="fb600-136">![Pagina Basi del formato per la creazione di report elettronici](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Schermata della pagina Basi del formato per la creazione di report elettronici")</span><span class="sxs-lookup"><span data-stu-id="fb600-136">![Electronic reporting format baselines page](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

    <span data-ttu-id="fb600-137">Il file in uscita generato è stato allegato automaticamente alla base del formato ER eseguito.</span><span class="sxs-lookup"><span data-stu-id="fb600-137">The generated outbound file has been automatically attached to the baseline of the executed ER format.</span></span> <span data-ttu-id="fb600-138">La regola di base è stata aggiunta automaticamente a questa base e contiene il riferimento al file allegato.</span><span class="sxs-lookup"><span data-stu-id="fb600-138">The baseline rule has been automatically added to this baseline and also contains the reference to the attached file.</span></span>

9. <span data-ttu-id="fb600-139">Nel campo **Nome** immettere **Base 1**.</span><span class="sxs-lookup"><span data-stu-id="fb600-139">In the **Name** field, enter **Baseline 1**.</span></span>
10. <span data-ttu-id="fb600-140">Nel campo **Maschera nome file** digitare **.xml**.</span><span class="sxs-lookup"><span data-stu-id="fb600-140">In the **File name mask** field, enter **.xml**.</span></span>
11. <span data-ttu-id="fb600-141">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fb600-141">Select **Save**.</span></span>

### <a name="run-the-format"></a><span data-ttu-id="fb600-142">Eseguire il formato</span><span class="sxs-lookup"><span data-stu-id="fb600-142">Run the format</span></span>

<span data-ttu-id="fb600-143">A questo punto è possibile completare i passaggi rimanenti nell'esempio dell'argomento [Generare la traccia dei risultati dei report generati e confrontarli con i valori di base](er-trace-reports-compare-baseline.md) a partire dalla sezione "Eseguire il formato ER progettato ed esaminare il registro per analizzare i risultati".</span><span class="sxs-lookup"><span data-stu-id="fb600-143">You're now ready to complete the remaining steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, starting from the "Run the designed ER format and review the log to analyze the results" section.</span></span>

> [!NOTE]
> <span data-ttu-id="fb600-144">Quando si elimina la regola di base aggiunta automaticamente nella Scheda dettaglio **Basi**, l'allegato a cui si fa riferimento non viene eliminato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fb600-144">When you delete the automatically added baseline rule on the **Baselines** FastTab, the referenced attachment isn't automatically deleted.</span></span>

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="fb600-145">Configurare la base in modo che ignori costantemente le parti variabili dell'output ER</span><span class="sxs-lookup"><span data-stu-id="fb600-145">Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="fb600-146">Quando un formato ER è progettato per contenere informazioni che vengono modificate all'esecuzione del formato, il formato deve utilizzare la funzionalità di base ER per confrontare i risultati generati ai valori di base.</span><span class="sxs-lookup"><span data-stu-id="fb600-146">When an ER format has been designed to contain information that is changed when the format is run, the format must be required to use the ER baseline feature to compare the generated results with baseline values.</span></span> <span data-ttu-id="fb600-147">Ad esempio, le informazioni potrebbero essere la data e l'ora di elaborazione o l'identificatore univoco di un documento generato in formati differenti (identificatore univoco globale \[GUID\] e così via).</span><span class="sxs-lookup"><span data-stu-id="fb600-147">For example, the information might be the processing date and time or the unique identifier of a generated document in different formats (globally unique identifier \[GUID\], and so on).</span></span> <span data-ttu-id="fb600-148">Le nuove funzionalità ER consentono di configurare la regola di base in modo che ignori gli elementi variabili di un formato ER quando il formato viene eseguito allo scopo di confrontare i valori di base ai risultati dell'esecuzione del formato.</span><span class="sxs-lookup"><span data-stu-id="fb600-148">The new ER capabilities let you configure the baseline rule so that it ignores changeable elements of an ER format when the format is run with the purpose of comparing baseline values with the results of the format's execution.</span></span> <span data-ttu-id="fb600-149">Per ulteriori informazioni su questa funzionalità, completare l'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fb600-149">To learn more about this feature, complete the following example.</span></span>

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="fb600-150">Esempio: configurare la base in modo che ignori le parti variabili dell'output ER</span><span class="sxs-lookup"><span data-stu-id="fb600-150">Example: Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="fb600-151">Per completare i passaggi in questo esempio, completare dapprima i passaggi dell'esempio nell'argomento[Generare la traccia dei risultati dei report generati e confrontarli con i valori di base](er-trace-reports-compare-baseline.md).</span><span class="sxs-lookup"><span data-stu-id="fb600-151">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic.</span></span>

### <a name="modify-a-configured-er-format"></a><span data-ttu-id="fb600-152">Modificare un formato ER configurato</span><span class="sxs-lookup"><span data-stu-id="fb600-152">Modify a configured ER format</span></span>

1. <span data-ttu-id="fb600-153">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="fb600-153">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fb600-154">Nella struttura espandere **Modello per ottenere basi ER**.</span><span class="sxs-lookup"><span data-stu-id="fb600-154">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="fb600-155">Nella struttura, selezionare **Modello per ottenere basi ER\\Formato per ottenere basi ER**.</span><span class="sxs-lookup"><span data-stu-id="fb600-155">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="fb600-156">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="fb600-156">Select **Designer**.</span></span>
5. <span data-ttu-id="fb600-157">Nella struttura selezionare **Output\\Documento**.</span><span class="sxs-lookup"><span data-stu-id="fb600-157">In the tree, select **Output\\Document**.</span></span>
6. <span data-ttu-id="fb600-158">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="fb600-158">Select **Add**.</span></span>
7. <span data-ttu-id="fb600-159">Nella finestra di dialogo a discesa, nella struttura selezionare **XLM\\Attributo**.</span><span class="sxs-lookup"><span data-stu-id="fb600-159">In the drop-down dialog box, in the tree, select **XML\\Attribute**.</span></span>
8. <span data-ttu-id="fb600-160">Nel campo **Nome**, immettere **DataOraElaborazione**.</span><span class="sxs-lookup"><span data-stu-id="fb600-160">In the **Name** field, enter **ProcessingDateTime**.</span></span>
9. <span data-ttu-id="fb600-161">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb600-161">Select **OK**.</span></span>
10. <span data-ttu-id="fb600-162">Nella scheda **Mapping**, nella struttura, selezionare **Output\\Documento\\DataOraElaborazione**.</span><span class="sxs-lookup"><span data-stu-id="fb600-162">On the **Mapping** tab, in the tree, select **Output\\Document\\ProcessingDateTime**.</span></span>
11. <span data-ttu-id="fb600-163">Selezionare **Modifica formula**.</span><span class="sxs-lookup"><span data-stu-id="fb600-163">Select **Edit formula**.</span></span>
12. <span data-ttu-id="fb600-164">Nel campo **Formula**, immettere la seguente espressione: **DATETIMEFORMAT(NOW(), "O")**</span><span class="sxs-lookup"><span data-stu-id="fb600-164">In the **Formula** field, enter the following expression: **DATETIMEFORMAT(NOW(), "O")**</span></span>
13. <span data-ttu-id="fb600-165">Selezionare **Salva** e quindi selezionare **Test**.</span><span class="sxs-lookup"><span data-stu-id="fb600-165">Select **Save**, and then select **Test**.</span></span>
14. <span data-ttu-id="fb600-166">Selezionare di nuovo **Test** per testare di nuovo l'espressione configurata.</span><span class="sxs-lookup"><span data-stu-id="fb600-166">Select **Test** again to retest the configured expression.</span></span>

    <span data-ttu-id="fb600-167">![Pagina Designer formula](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Schermata della pagina Designer formula")</span><span class="sxs-lookup"><span data-stu-id="fb600-167">![Formula designer page](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Screenshot of the Formula designer page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="fb600-168">La scheda **Risultato test** indica che l'espressione configurata restituisce un valore di data e ora differente ogni volta che viene richiamata.</span><span class="sxs-lookup"><span data-stu-id="fb600-168">The **Test result** tab shows that the configured expression returns a different date and time value whenever it's called.</span></span>

15. <span data-ttu-id="fb600-169">Chiudere la pagina **Designer formula** quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fb600-169">Close the **Formula designer** page, and then select **Save**.</span></span>

    <span data-ttu-id="fb600-170">![Pagina Progettazione formati](media/GER-BaselineSample-FormatMappingDesign2.PNG "Schermata della pagina Progettazione formati")</span><span class="sxs-lookup"><span data-stu-id="fb600-170">![Format designer page](media/GER-BaselineSample-FormatMappingDesign2.PNG "Screenshot of the Format designer page")</span></span>

16. <span data-ttu-id="fb600-171">Chiudere la pagina **Progettazione formati**.</span><span class="sxs-lookup"><span data-stu-id="fb600-171">Close the **Format designer** page.</span></span>

### <a name="remove-an-existing-baseline-rule"></a><span data-ttu-id="fb600-172">Rimuovere una regola di base esistente</span><span class="sxs-lookup"><span data-stu-id="fb600-172">Remove an existing baseline rule</span></span>

1. <span data-ttu-id="fb600-173">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="fb600-173">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fb600-174">Selezionare **Basi**.</span><span class="sxs-lookup"><span data-stu-id="fb600-174">Select **Baselines**.</span></span>
3. <span data-ttu-id="fb600-175">Nell'elenco delle basi, selezionare la base configurata per il formato **Formato per ottenere basi ER**.</span><span class="sxs-lookup"><span data-stu-id="fb600-175">In the list of baselines, select the baseline that is configured for the **Format to learn ER baselines** format.</span></span>
4. <span data-ttu-id="fb600-176">Nella Scheda dettaglio **Basi**, selezionare **Elimina** per rimuovere la regola di base configurata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="fb600-176">On the **Baselines** FastTab, select **Delete** to remove the baseline rule that you configured earlier.</span></span>

<span data-ttu-id="fb600-177">![Pagina Basi del formato per la creazione di report elettronici](media/GER-BaselineSample-AddBaseline3.PNG "Schermata della pagina Basi del formato per la creazione di report elettronici")</span><span class="sxs-lookup"><span data-stu-id="fb600-177">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline3.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="define-replacements-for-bindings-of-designed-er-format"></a><span data-ttu-id="fb600-178">Definire le sostituzioni per le associazioni del formato ER progettato</span><span class="sxs-lookup"><span data-stu-id="fb600-178">Define replacements for bindings of designed ER format</span></span>

1. <span data-ttu-id="fb600-179">Nella pagina **Configurazioni**, nella scheda dettaglio **Sostituzioni**, selezionare **Seleziona componenti**.</span><span class="sxs-lookup"><span data-stu-id="fb600-179">On the **Configurations** page, on the **Replacements** FastTab, select **Select components**.</span></span>
2. <span data-ttu-id="fb600-180">Nella struttura dei componenti del formato, **Output**, espandere **Output\\Documento** e quindi selezionare la casella di controllo per **Output\\Documento\\DataOraElaborazione**.</span><span class="sxs-lookup"><span data-stu-id="fb600-180">In the format components tree, expand **Output**, expand **Output\\Document**, and then select the check box for **Output\\Document\\ProcessingDateTime**.</span></span>

    <span data-ttu-id="fb600-181">![Finestra di dialogo Seleziona componenti](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Schermata della finestra di dialogo Seleziona componenti")</span><span class="sxs-lookup"><span data-stu-id="fb600-181">![Select Components dialog box](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Screenshot of the Select Components dialog box")</span></span>

3. <span data-ttu-id="fb600-182">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb600-182">Select **OK**.</span></span>

<span data-ttu-id="fb600-183">![Pagina Basi del formato per la creazione di report elettronici](media/GER-BaselineSample-AddBaseline4.PNG "Schermata della pagina Basi del formato per la creazione di report elettronici")</span><span class="sxs-lookup"><span data-stu-id="fb600-183">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline4.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

<span data-ttu-id="fb600-184">Il componente del formato ER selezionato è stato aggiunto all'elenco dei componenti nella scheda dettaglio **Sostituzioni**.</span><span class="sxs-lookup"><span data-stu-id="fb600-184">The selected ER format component has been added to the list of components on the **Replacements** FastTab.</span></span> <span data-ttu-id="fb600-185">Quando il formato ER di base viene eseguito in modalità di debug, l'associazione del formato per ogni componente verrà sostituita dall'associazione visualizzata nella colonna **Associazione**.</span><span class="sxs-lookup"><span data-stu-id="fb600-185">When the base ER format is run in debug mode, the format's binding for each component will be replaced by the binding that is shown in the **Binding** column.</span></span> <span data-ttu-id="fb600-186">Per modificare l'associazione predefinita per un componente elencata nella scheda dettaglio **Sostituzioni**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="fb600-186">To change the default binding for a component that is listed on the **Replacements** FastTab, select **Edit**.</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="fb600-187">Creare un nuova regola di base</span><span class="sxs-lookup"><span data-stu-id="fb600-187">Make a new baseline rule</span></span>

<span data-ttu-id="fb600-188">Seguire i passaggi nella sezione "Esempio: automatizzare l'impostazione delle regole di base" vista precedentemente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="fb600-188">Follow the steps in the "Example: Automate the setting of baseline rules" section earlier in this topic.</span></span> <span data-ttu-id="fb600-189">Una notifica informa che il file in uscita è stato generato utilizzando le impostazioni di base e che si è verificata una sostituzione forzata delle associazioni del formato.</span><span class="sxs-lookup"><span data-stu-id="fb600-189">A notification warns you that the outbound file has been generated by using baseline settings, and that a forced replacement of the format bindings has occurred.</span></span>

<span data-ttu-id="fb600-190">![Notifica nella pagina Configurazioni](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Schermata della notifica nella pagina Configurazioni")</span><span class="sxs-lookup"><span data-stu-id="fb600-190">![Notification on the Configurations page](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Screenshot of the notification on the Configurations page")</span></span>

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a><span data-ttu-id="fb600-191">Sopprimere gli avvisi relativi alla sostituzione delle associazioni del formato</span><span class="sxs-lookup"><span data-stu-id="fb600-191">Suppress warnings about the replacement of format bindings</span></span>

<span data-ttu-id="fb600-192">Impostando parametri ER specifici, è possibile sopprimere le notifiche che informano della sostituzione delle associazioni del formato.</span><span class="sxs-lookup"><span data-stu-id="fb600-192">By setting specific ER parameters, you can suppress notifications that warn about the replacement of format bindings.</span></span> <span data-ttu-id="fb600-193">Questa soppressione può essere utile se le associazioni del formato vengono sostituite in una modalità automatica utilizzando Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="fb600-193">This suppression can be useful when format bindings are replaced in an unattended mode by using the Regression Suite Automation Tool.</span></span> <span data-ttu-id="fb600-194">In questo caso, l'avviso può essere considerato un errore del test case in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fb600-194">In this case, the warning can be considered a failure of the test case that is running.</span></span>

1. <span data-ttu-id="fb600-195">Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, selezionare **Parametri utente**.</span><span class="sxs-lookup"><span data-stu-id="fb600-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
2. <span data-ttu-id="fb600-196">Impostare l'opzione **Sopprimi avvisi di base**su **Sì** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb600-196">Set the **Suppress baseline warnings** option to **Yes**, and then select **OK**.</span></span>

<span data-ttu-id="fb600-197">![Finestra di dialogo Parametri utente](media/GER-BaselineSample-ERUserParameters1.png "Schermata della finestra di dialogo Parametri utente")</span><span class="sxs-lookup"><span data-stu-id="fb600-197">![User parameters dialog box](media/GER-BaselineSample-ERUserParameters1.png "Screenshot of the User parameters dialog box")</span></span>

### <a name="review-the-generated-baseline-file"></a><span data-ttu-id="fb600-198">Esaminare il file di base generato</span><span class="sxs-lookup"><span data-stu-id="fb600-198">Review the generated baseline file</span></span>

1. <span data-ttu-id="fb600-199">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="fb600-199">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fb600-200">Selezionare **Basi**.</span><span class="sxs-lookup"><span data-stu-id="fb600-200">Select **Baselines**.</span></span>
3. <span data-ttu-id="fb600-201">Selezionare **Allegati**.</span><span class="sxs-lookup"><span data-stu-id="fb600-201">Select **Attachments**.</span></span>

    <span data-ttu-id="fb600-202">![Pagina Allegati](media/GER-BaselineSample-AttachedBaselineFile.PNG "Schermata della pagina Allegati").</span><span class="sxs-lookup"><span data-stu-id="fb600-202">![Attachments page](media/GER-BaselineSample-AttachedBaselineFile.PNG "Screenshot of the Attachments page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="fb600-203">Il file generato contiene il testo della data e dell'ora di elaborazione (**"#"**) dell'associazione configurata nella regola di base aggiunta e non dell'associazione del formato.</span><span class="sxs-lookup"><span data-stu-id="fb600-203">The generated file contains the processing date and time text (**"#"**) from the binding that was configured in the added baseline rule, not from the format's binding.</span></span>

4. <span data-ttu-id="fb600-204">Chiudere la pagina **Allegati**.</span><span class="sxs-lookup"><span data-stu-id="fb600-204">Close the **Attachments** page.</span></span>

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a><span data-ttu-id="fb600-205">Eseguire il formato ER progettato ed esaminare il registro per analizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="fb600-205">Run the designed ER format and review the log to analyze the results</span></span>

1. <span data-ttu-id="fb600-206">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="fb600-206">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="fb600-207">Nella struttura espandere **Modello per ottenere basi ER**.</span><span class="sxs-lookup"><span data-stu-id="fb600-207">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="fb600-208">Nella struttura, selezionare **Modello per ottenere basi ER\\Formato per ottenere basi ER**.</span><span class="sxs-lookup"><span data-stu-id="fb600-208">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="fb600-209">Nella scheda dettaglio **Versioni** selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="fb600-209">On the **Versions** FastTab select **Run**.</span></span>
5. <span data-ttu-id="fb600-210">Nel campo **Immetti ID**, digitare **1**.</span><span class="sxs-lookup"><span data-stu-id="fb600-210">In the **Enter Id** field, type **1**.</span></span>
6. <span data-ttu-id="fb600-211">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb600-211">Select **OK**.</span></span>
7. <span data-ttu-id="fb600-212">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Registri debug configurazione**.</span><span class="sxs-lookup"><span data-stu-id="fb600-212">Go to **Organization administration** \> **Electronic reporting** \> **Configuration debug logs**.</span></span>

<span data-ttu-id="fb600-213">Il registro di esecuzione contiene informazioni sui risultati del confronto tra il file generato e la base configurata.</span><span class="sxs-lookup"><span data-stu-id="fb600-213">The execution log contains information about the results of the comparison of the generated file with the configured baseline.</span></span> <span data-ttu-id="fb600-214">Il registro indica che il file generato e la base sono uguali, anche se il formato eseguito contiene l'associazione per immettere un valore di data e ora costantemente variabile nel file in uscita.</span><span class="sxs-lookup"><span data-stu-id="fb600-214">The log indicates that the generated file and the baseline are equal, even though the executed format contains the binding to enter a constantly changing date and time value in the outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="fb600-215">Sebbene il file in uscita sia stato generato utilizzando le impostazioni di base che forzano la sostituzione delle associazioni del formato, non vengono restituiti avvisi relativi alla sostituzione.</span><span class="sxs-lookup"><span data-stu-id="fb600-215">Although the outbound file has been generated by using baseline settings that force the replacement of the format's bindings, you don't receive any warnings about the replacement.</span></span>

## <a name="exchange-baseline-settings-between-environments"></a><span data-ttu-id="fb600-216">Scambiare le impostazioni di base tra ambienti</span><span class="sxs-lookup"><span data-stu-id="fb600-216">Exchange baseline settings between environments</span></span>

### <a name="export-baseline-settings"></a><span data-ttu-id="fb600-217">Esportare impostazioni di base</span><span class="sxs-lookup"><span data-stu-id="fb600-217">Export baseline settings</span></span>

<span data-ttu-id="fb600-218">Le nuove funzionalità ER consentono di esportare impostazioni di base per il formato ER selezionato dall'ambiente corrente e di archiviarle come file XML.</span><span class="sxs-lookup"><span data-stu-id="fb600-218">The new ER capabilities let you export baseline settings for the selected ER format from the current environment and store them as XML files.</span></span> 

<span data-ttu-id="fb600-219">Per esportare le impostazioni di base, nella pagina **Basi del formato per la creazione di report elettronici**, selezionare **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="fb600-219">To export baseline settings, on the **Electronic reporting format baselines** page, select **Export**.</span></span>

### <a name="import-baseline-settings"></a><span data-ttu-id="fb600-220">Importa impostazioni di base</span><span class="sxs-lookup"><span data-stu-id="fb600-220">Import baseline settings</span></span>

<span data-ttu-id="fb600-221">Le impostazioni di base esportate possono essere importate in un ambiente differente.</span><span class="sxs-lookup"><span data-stu-id="fb600-221">Exported baseline settings can be imported into a different environment.</span></span> <span data-ttu-id="fb600-222">L'ambiente deve essere dapprima importato come formato ER.</span><span class="sxs-lookup"><span data-stu-id="fb600-222">The environment must first be imported as an ER format.</span></span> <span data-ttu-id="fb600-223">Successivamente è possibile importare le impostazioni di base.</span><span class="sxs-lookup"><span data-stu-id="fb600-223">You can then import the baseline settings.</span></span>

<span data-ttu-id="fb600-224">Per importare le impostazioni di base da un file XML archiviato in locale, nella pagina **Basi del formato per la creazione di report elettronici**, selezionare **Importa** e quindi **Sfoglia** per selezionare il file XML.</span><span class="sxs-lookup"><span data-stu-id="fb600-224">To import baseline settings from a locally stored XML file, on the **Electronic reporting format baselines** page, select **Import**, and then select **Browse** to select the XML file.</span></span>

<span data-ttu-id="fb600-225">![Finestra di dialogo Importa impostazioni di base](media/GER-BaselineSample-ImportBaseline1.PNG "Schermata della finestra di dialogo Importa impostazioni di base")</span><span class="sxs-lookup"><span data-stu-id="fb600-225">![Import baseline settings dialog box](media/GER-BaselineSample-ImportBaseline1.PNG "Screenshot of the Import baseline settings dialog box")</span></span>

<span data-ttu-id="fb600-226">Per importare le impostazioni di base da un file XML archiviato nel server di Microsoft SharePoint, in base alle impostazioni correnti di Gestione documenti e il tipo di documento selezionato, nella pagina **Basi del formato per la creazione di report elettronici**, selezionare **Importa dall'origine**.</span><span class="sxs-lookup"><span data-stu-id="fb600-226">To import baseline settings from an XML file that is stored on the Microsoft SharePoint Server, based on the current Document management settings and the selected document type, on the **Electronic reporting format baselines** page, select **Import from source**.</span></span> <span data-ttu-id="fb600-227">Selezionare quindi il tipo di documento e il file XML.</span><span class="sxs-lookup"><span data-stu-id="fb600-227">Then select the document type and the XML file.</span></span> <span data-ttu-id="fb600-228">Il tipo di documento necessario per accedere alla cartella SharePoint deve essere configurato in anticipo.</span><span class="sxs-lookup"><span data-stu-id="fb600-228">The required document type to access the SharePoint folder must be configured in advance.</span></span>

<span data-ttu-id="fb600-229">![Finestra di dialogo Importa dall'origine](media/GER-BaselineSample-ImportBaseline2.PNG "Schermata della finestra di dialogo Importa dall'origine")</span><span class="sxs-lookup"><span data-stu-id="fb600-229">![Import from source dialog box](media/GER-BaselineSample-ImportBaseline2.PNG "Screenshot of the Import from source dialog box")</span></span>

> [!NOTE]
> <span data-ttu-id="fb600-230">È possibile utilizzare Registrazione attività per registrare i passaggi per la selezione del tipo di documento richiesto e il nome di file nella finestra dialogo **Importa dall'origine**.</span><span class="sxs-lookup"><span data-stu-id="fb600-230">You can use Task recorder to record the steps for selecting the required document type and the file name in the **Import from source** dialog box.</span></span> <span data-ttu-id="fb600-231">In questo modo, è possibile mantenere le impostazioni di base richieste sul server SharePoint e quindi eseguirne l'importazione automaticamente eseguendo una registrazione attività quando si eseguono test automatizzati utilizzando Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="fb600-231">In this way, you can keep required baseline settings on SharePoint Server and then automatically import them by playing a task recording when you run automated tests by using the Regression Suite Automation Tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb600-232">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb600-232">Additional resources</span></span>

- [<span data-ttu-id="fb600-233">Tenere traccia dei risultati dei report generati e confrontarli con i valori di base</span><span class="sxs-lookup"><span data-stu-id="fb600-233">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="fb600-234">Registrazione attività</span><span class="sxs-lookup"><span data-stu-id="fb600-234">Task recorder</span></span>](../user-interface/task-recorder.md)
