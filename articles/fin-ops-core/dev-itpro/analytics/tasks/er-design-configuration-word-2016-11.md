---
title: Riutilizzare le configurazioni ER con i modelli Escel per generare report nel formato Word
description: In questo argomento viene descritto come i formati di report progettati per generare report come cartelle di lavoro di Excel possono essere configurati per generare report come documenti Word.
author: NickSelin
ms.date: 01/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 728984678d78cf626e2b30222f1d1e603e05d117
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755060"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a><span data-ttu-id="db351-103">Riutilizzare le configurazioni ER con i modelli Escel per generare report nel formato Word</span><span class="sxs-lookup"><span data-stu-id="db351-103">Reuse ER configurations with Excel templates to generate reports in Word format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="db351-104">Per generare report come documenti di Microsoft Word, puoi [configurare](../er-design-configuration-word.md) un nuovo [formato](../general-electronic-reporting.md#FormatComponentOutbound) [Creazione di report elettronici (ER)](../general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="db351-104">To generate reports as Microsoft Word documents, you can [configure](../er-design-configuration-word.md) a new [Electronic reporting (ER)](../general-electronic-reporting.md) [format](../general-electronic-reporting.md#FormatComponentOutbound).</span></span> <span data-ttu-id="db351-105">In alternativa, puoi riutilizzare un formato ER originariamente progettato per generare report come cartelle di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="db351-105">Alternatively, you can reuse an ER format that was originally designed to generate reports as Excel workbooks.</span></span> <span data-ttu-id="db351-106">In questo caso, è necessario sostituire il modello Excel con un modello Word.</span><span class="sxs-lookup"><span data-stu-id="db351-106">In this case, you must replace the Excel template with a Word template.</span></span>

<span data-ttu-id="db351-107">Le procedure seguenti mostrano come un utente con il ruolo di amministratore di sistema o il ruolo di sviluppatore per la creazione di report elettronici può configurare un formato ER per generare report come file Word riutilizzando un formato ER progettato per generare report come file Excel.</span><span class="sxs-lookup"><span data-stu-id="db351-107">The following procedures show how a user in either the System administrator role or the Electronic reporting developer role can configure an ER format to generate reports as Word files by reusing an ER format that was designed to generate reports as Excel files.</span></span>

<span data-ttu-id="db351-108">Queste procedure possono essere completate nella società GBSI.</span><span class="sxs-lookup"><span data-stu-id="db351-108">These procedures can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="db351-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="db351-109">Prerequisites</span></span>

<span data-ttu-id="db351-110">Per completare queste procedure, è innanzitutto necessario seguire i passaggi nella guida attività [Progettare una configurazione per la creazione di report nel formato OPENXML](er-design-reports-openxml-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="db351-110">To complete these procedures, you must first follow the steps in the [Design a configuration for generating reports in OPENXML format](er-design-reports-openxml-2016-11.md) task guide.</span></span>

<span data-ttu-id="db351-111">È inoltre necessario scaricare e salvare i seguenti modelli localmente per il report di esempio:</span><span class="sxs-lookup"><span data-stu-id="db351-111">You must also download and locally save the following templates for the sample report:</span></span>

- [<span data-ttu-id="db351-112">Modello di Report di pagamento (SampleVendPaymDocReport.docx)</span><span class="sxs-lookup"><span data-stu-id="db351-112">Template of Payment Report (SampleVendPaymDocReport.docx)</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)
- [<span data-ttu-id="db351-113">Modello associato di Report di pagamento (SampleVendPaymDocReportBounded.docx)</span><span class="sxs-lookup"><span data-stu-id="db351-113">Bounded Template of Payment Report (SampleVendPaymDocReportBounded.docx)</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)

<span data-ttu-id="db351-114">Queste procedure riguardano una funzionalità aggiunta in Dynamics 365 for Operations versione 1611 (novembre 2016).</span><span class="sxs-lookup"><span data-stu-id="db351-114">These procedures are for a feature that was added in Dynamics 365 for Operations version 1611 (November 2016).</span></span>

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="db351-115">Selezionare la configurazione esistente del report ER</span><span class="sxs-lookup"><span data-stu-id="db351-115">Select the existing ER report configuration</span></span>

1. <span data-ttu-id="db351-116">In Dynamics 365 Finance, passare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="db351-116">In Dynamics 365 Finance, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="db351-117">Assicurarsi che il provider di configurazione **Litware, Inc.** sia selezionato come **attivo**.</span><span class="sxs-lookup"><span data-stu-id="db351-117">Make sure that the **Litware, Inc.** configuration provider is selected as **Active**.</span></span> <span data-ttu-id="db351-118">In caso contrario, segui i passaggi nella guida attività [Creare fornitori di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="db351-118">If it isn't, follow the steps in the [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) task guide.</span></span>
3. <span data-ttu-id="db351-119">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="db351-119">Select **Reporting configurations**.</span></span> <span data-ttu-id="db351-120">Verrà riutilizzata la configurazione ER esistente progettata per generare l'output del report in formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="db351-120">You will reuse the existing ER configuration that was designed to generate the report output in OPENXML format.</span></span>
4. <span data-ttu-id="db351-121">Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, quindi seleziona **Report foglio di lavoro di esempio**.</span><span class="sxs-lookup"><span data-stu-id="db351-121">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and select **Sample worksheet report**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="db351-122">La versione bozza del formato ER selezionato può essere modificata nella scheda dettaglio **Versioni**.</span><span class="sxs-lookup"><span data-stu-id="db351-122">The draft version of the selected ER format can be edited on the **Versions** FastTab.</span></span>

5. <span data-ttu-id="db351-123">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="db351-123">Select **Designer**.</span></span>
6. <span data-ttu-id="db351-124">Nella pagina **Progettazione formati** il titolo dell'elemento di formato radice indica che un modello di Excel è attualmente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="db351-124">On the **Format designer** page, notice that the title of the root format element indicates that an Excel template is currently used.</span></span>

![Selezione della configurazione esistente](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a><span data-ttu-id="db351-126">Rivedere il modello di Word scaricato</span><span class="sxs-lookup"><span data-stu-id="db351-126">Review the downloaded Word template</span></span>

1. <span data-ttu-id="db351-127">Nell'applicazione desktop Word, apri il file del modello **SampleVendPaymDocReport.docx** scaricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="db351-127">In the Word desktop application, open the **SampleVendPaymDocReport.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="db351-128">Verificare che il modello contenga solo il layout di documento che si desidera generare come output ER.</span><span class="sxs-lookup"><span data-stu-id="db351-128">Verify that the template contains only the layout of the document that you want to generate as ER output.</span></span>

![Il layout del modello di Word nell'applicazione desktop](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a><span data-ttu-id="db351-130">Sostituire il modello Excel con il modello Word e aggiungere una parte XML personalizzata</span><span class="sxs-lookup"><span data-stu-id="db351-130">Replace the Excel template with the Word template and add a custom XML part</span></span>

<span data-ttu-id="db351-131">Attualmente, il documento di Excel viene utilizzato come modello per generare l'output nel formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="db351-131">Currently, the Excel document is used as a template to generate the output in OPENXML format.</span></span> <span data-ttu-id="db351-132">Questo modello verrà sostituito con il file modello di Word SampleVendPaymDocReport.docx caricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="db351-132">You will replace this template with the SampleVendPaymDocReport.docx Word template file that you downloaded earlier.</span></span> <span data-ttu-id="db351-133">Il modello di Word verrà inoltre esteso aggiungendo una parte XML personalizzata.</span><span class="sxs-lookup"><span data-stu-id="db351-133">You will also extend the Word template by adding a custom XML part.</span></span>

1. <span data-ttu-id="db351-134">In Finance, nella pagina **Progettazione formati**, nella scheda **Formato** selezionare **Allegati**.</span><span class="sxs-lookup"><span data-stu-id="db351-134">In Finance, on the **Format designer** page, on the **Format** tab, select **Attachments**.</span></span>
2. <span data-ttu-id="db351-135">Nella pagina **Allegati**, selezionare **Elimina** per rimuovere il modello Excel esistente.</span><span class="sxs-lookup"><span data-stu-id="db351-135">On the **Attachments** page, select **Delete** to remove the existing Excel template.</span></span> <span data-ttu-id="db351-136">Selezionare **Sì** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="db351-136">Select **Yes** to confirm the change.</span></span>
3. <span data-ttu-id="db351-137">Seleziona **Nuovo** \> **File**.</span><span class="sxs-lookup"><span data-stu-id="db351-137">Select **New** \> **File**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="db351-138">È necessario selezionare un tipo di documento [configurato](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) nei parametri ER per archiviare i modelli dei formati ER.</span><span class="sxs-lookup"><span data-stu-id="db351-138">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

4. <span data-ttu-id="db351-139">Selezionare **Sfoglia**, quindi individuare e selezionare il file **SampleVendPaymDocReport.docx** scaricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="db351-139">Select **Browse**, and then browse to and select the **SampleVendPaymDocReport.docx** file that you downloaded earlier.</span></span>
5. <span data-ttu-id="db351-140">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="db351-140">Select **OK**.</span></span>
6. <span data-ttu-id="db351-141">Chiudere la pagina **Allegati**.</span><span class="sxs-lookup"><span data-stu-id="db351-141">Close the **Attachments** page.</span></span>
7. <span data-ttu-id="db351-142">Nella pagina **Progettazione formati**, nel campo **Modello**, immetti o seleziona il file **SampleVendPaymDocReport.docx** per utilizzare quel modello di Word invece del modello di Excel utilizzato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="db351-142">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReport.docx** file to use that Word template instead of the Excel template that was previously used.</span></span>
8. <span data-ttu-id="db351-143">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="db351-143">Select **Save**.</span></span>

    <span data-ttu-id="db351-144">Oltre ad archiviare le modifiche apportate alla configurazione, l'azione **Salva** aggiorna anche il modello di Word associato.</span><span class="sxs-lookup"><span data-stu-id="db351-144">In addition to storing configuration changes, the **Save** action updates the attached Word template.</span></span> <span data-ttu-id="db351-145">La struttura gerarchica del formato progettato viene aggiunta al documento Word associato come nuova parte XML personalizzata con il nome **Report**.</span><span class="sxs-lookup"><span data-stu-id="db351-145">The hierarchical structure of the designed format is added to the attached Word document as a new custom XML part that is named **Report**.</span></span> <span data-ttu-id="db351-146">Il modello di Word associato contiene il layout del documento che verrà generato come output ER e la struttura dei dati che ER inserisce nel modello in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="db351-146">The attached Word template contains the layout of the document that will be generated as ER output and the structure of data that ER will enter in that template at runtime.</span></span>

9. <span data-ttu-id="db351-147">Il titolo dell'elemento di formato radice indica che un modello di Word è attualmente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="db351-147">Notice that the title of the root format element indicates that a Word template is currently used.</span></span>

    ![Sostituzione del modello Excel con il modello Word e aggiunta di una parte XML personalizzata](../media/er-design-configuration-word-2016-11-image03.gif)

10. <span data-ttu-id="db351-149">Nella scheda **Formato**, selezionare **Allegati**.</span><span class="sxs-lookup"><span data-stu-id="db351-149">On the **Format** tab, select **Attachments**.</span></span>

<span data-ttu-id="db351-150">È possibile eseguire ora il mapping degli elementi della parte XML personalizzata **Report** ai controlli di contenuto del documento Word.</span><span class="sxs-lookup"><span data-stu-id="db351-150">You can now map the elements of the **Report** custom XML part to the content controls of the Word document.</span></span>

<span data-ttu-id="db351-151">Se hai dimestichezza con il processo di progettazione dei documenti Word in formati che contengono [controli di contenuto](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) mappati agli elementi di [parti XML personalizzate](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), completa tutti i passaggi della procedura successiva per creare il documento.</span><span class="sxs-lookup"><span data-stu-id="db351-151">If you're familiar with the process of designing Word documents as forms that contain [content controls](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) that are mapped to elements of [custom XML parts](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), complete all steps in the next procedure to create the document.</span></span> <span data-ttu-id="db351-152">Per ulteriori informazioni, vedere [Creare moduli che gli utenti completano o stampano in Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span><span class="sxs-lookup"><span data-stu-id="db351-152">For more information, see [Create forms that users complete or print in Words](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span></span> <span data-ttu-id="db351-153">In caso contrario, ignora la procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="db351-153">Otherwise, skip the next procedure.</span></span>

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a><span data-ttu-id="db351-154">Ottenere un documento di Word che abbia una parte XML personalizzata ed eseguire il mapping dei dati</span><span class="sxs-lookup"><span data-stu-id="db351-154">Get a Word document that has a custom XML part and do data mapping</span></span>

1. <span data-ttu-id="db351-155">In Finance, nella pagina **Allegati**, selezionare **Apri** per scaricare il modello selezionato da Finance e archiviarlo localmente come documento Word.</span><span class="sxs-lookup"><span data-stu-id="db351-155">In Finance, on the **Attachments** page, select **Open** to download the selected template from Finance and store it locally as a Word document.</span></span>
3. <span data-ttu-id="db351-156">Nell'applicazione desktop di Word, apri il documento che hai appena scaricato.</span><span class="sxs-lookup"><span data-stu-id="db351-156">In the Word desktop application, open the document that you just downloaded.</span></span>
4. <span data-ttu-id="db351-157">Nella scheda **Sviluppatore**, seleziona **Riquadro di mapping XML**.</span><span class="sxs-lookup"><span data-stu-id="db351-157">On the **Developer** tab, select **XML Mapping Pane**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="db351-158">Se la scheda **Sviluppatore** non viene visualizzata sulla barra multifunzione, personalizzare la barra multifunzione per aggiungerla.</span><span class="sxs-lookup"><span data-stu-id="db351-158">If the **Developer** tab doesn't appear on the ribbon, customize the ribbon to add it.</span></span>

5. <span data-ttu-id="db351-159">Nel riquadro **Mapping XML**, nel campo **Parte XML personalizzata** selezionare la parte XML personalizzata **Report**.</span><span class="sxs-lookup"><span data-stu-id="db351-159">In the **XML Mapping** pane, in the **Custom XML Part** field, select the **Report** custom XML part.</span></span>
6. <span data-ttu-id="db351-160">Eseguire il mapping degli elementi della parte XML personalizzata **Report** selezionata ai controlli di contenuto del documento Word.</span><span class="sxs-lookup"><span data-stu-id="db351-160">Map the elements of the selected **Report** custom XML part and the content controls of the Word document.</span></span>
7. <span data-ttu-id="db351-161">Salvare localmente il documento Word aggiornato come **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="db351-161">Save the updated Word document locally as **SampleVendPaymDocReportBounded.docx**.</span></span>

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="db351-162">Rivedere il modello di Word in cui la parte XML personalizzata è mappata ai controlli del contenuto</span><span class="sxs-lookup"><span data-stu-id="db351-162">Review the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="db351-163">Nell'applicazione desktop Word, aprire il file del modello **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="db351-163">In the Word desktop application, open the **SampleVendPaymDocReportBounded.docx** template file.</span></span>
2. <span data-ttu-id="db351-164">Verificare che il modello contenga il layout di documento che si desidera generare come output ER.</span><span class="sxs-lookup"><span data-stu-id="db351-164">Verify that the template contains the layout of the document that you want to generate as ER output.</span></span> <span data-ttu-id="db351-165">I controlli del contenuto utilizzati come segnaposto per i dati che ER inserirà in questo modello in fase di esecuzione si basano sui mapping configurati tra gli elementi della parte XML personalizzata **Report** e i controlli del contenuto del documento di Word.</span><span class="sxs-lookup"><span data-stu-id="db351-165">The content controls that are used as placeholders for data that ER will enter in this template at runtime are based on the mappings that are configured between elements of the **Report** custom XML part and the content controls of the Word document.</span></span>

![Anteprima del modello di Word nell'applicazione desktop](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="db351-167">Caricare il modello di Word in cui la parte XML personalizzata è mappata ai controlli del contenuto</span><span class="sxs-lookup"><span data-stu-id="db351-167">Upload the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="db351-168">In Finance, nella pagina **Allegati**, selezionare **Elimina** per rimuovere il modello di Word che non ha mapping tra gli elementi della parte XML personalizzata **Report** e i controlli del contenuto.</span><span class="sxs-lookup"><span data-stu-id="db351-168">In Finance, on the **Attachments** page, select **Delete** to remove the Word template that has no mappings between elements of the **Report** custom XML part and content controls.</span></span> <span data-ttu-id="db351-169">Selezionare **Sì** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="db351-169">Select **Yes** to confirm the change.</span></span>
2. <span data-ttu-id="db351-170">Selezionare **Nuovo** \> **File** per aggiungere un nuovo file modello che contiene i mapping tra gli elementi della parte XML personalizzata **Report** e i controlli del contenuto.</span><span class="sxs-lookup"><span data-stu-id="db351-170">Select **New** \> **File** to add a new template file that contains mappings between elements of the **Report** custom XML part and content controls.</span></span>

    > [!NOTE]
    > <span data-ttu-id="db351-171">È necessario selezionare un tipo di documento [configurato](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) nei parametri ER per archiviare i modelli dei formati ER.</span><span class="sxs-lookup"><span data-stu-id="db351-171">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

3. <span data-ttu-id="db351-172">Selezionare **Sfoglia**, quindi individuare e selezionare il file **SampleVendPaymDocReportBounded.docx** che hai scaricato o preparato completando la procedura nella sezione [Ottenere un documento di Word che abbia una parte XML personalizzata ed eseguire il mapping dei dati](#get-word-doc).</span><span class="sxs-lookup"><span data-stu-id="db351-172">Select **Browse**, and then browse to and select the **SampleVendPaymDocReportBounded.docx** file that you downloaded or prepared by completing the procedure in the [Get a Word that has a custom XML part to do data mapping](#get-word-doc) section.</span></span>
4. <span data-ttu-id="db351-173">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="db351-173">Select **OK**.</span></span>
5. <span data-ttu-id="db351-174">Chiudere la pagina **Allegati**.</span><span class="sxs-lookup"><span data-stu-id="db351-174">Close the **Attachments** page.</span></span>
6. <span data-ttu-id="db351-175">Nella pagina **Progettazione formati** nel campo **Modello** selezionare il documento appena scaricato.</span><span class="sxs-lookup"><span data-stu-id="db351-175">On the **Format designer** page, in the **Template** field, select the document that you just downloaded.</span></span>
7. <span data-ttu-id="db351-176">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="db351-176">Select **Save**.</span></span>
8. <span data-ttu-id="db351-177">Chiudere la pagina **Progettazione formati**.</span><span class="sxs-lookup"><span data-stu-id="db351-177">Close the **Format designer** page.</span></span>

## <a name="mark-the-configured-format-as-runnable"></a><span data-ttu-id="db351-178">Contrassegnare il formato configurato come eseguibile</span><span class="sxs-lookup"><span data-stu-id="db351-178">Mark the configured format as runnable</span></span>

<span data-ttu-id="db351-179">Per eseguire la versione bozza del formato modificabile, è necessario renderla [eseguibile](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span><span class="sxs-lookup"><span data-stu-id="db351-179">To run the draft version of the editable format, you must make it [runnable](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span></span>

1. <span data-ttu-id="db351-180">In Finance, nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.</span><span class="sxs-lookup"><span data-stu-id="db351-180">In Finance, on the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
2. <span data-ttu-id="db351-181">Nella finestra di dialogo **Parametri utente**, imposta l'opzione **Esegui impostazioni** su **Sì**, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="db351-181">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
3. <span data-ttu-id="db351-182">Seleziona **Modifica** per rendere la pagina modificabile come richiesto.</span><span class="sxs-lookup"><span data-stu-id="db351-182">Select **Edit** to make the current page editable, as required.</span></span>
4. <span data-ttu-id="db351-183">Per la configurazione **Report foglio di lavoro di esempio** attualmente selezionata, imposta l'opzione **Esegui bozza** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="db351-183">For the currently selected **Sample worksheet report** configuration, set the **Run Draft** option to **Yes**.</span></span>
5. <span data-ttu-id="db351-184">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="db351-184">Select **Save**.</span></span>

## <a name="run-the-format-to-create-output-in-word-format"></a><span data-ttu-id="db351-185">Eseguire il formato per creare l'output in formato Word</span><span class="sxs-lookup"><span data-stu-id="db351-185">Run the format to create output in Word format</span></span>

1. <span data-ttu-id="db351-186">In Finance, andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="db351-186">In Finance, go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="db351-187">In un giornale di registrazione pagamenti immesso in precedenza, selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="db351-187">In a payment journal that you entered earlier, select **Lines**.</span></span>
3. <span data-ttu-id="db351-188">Nella pagina **Pagamenti fornitore**, seleziona tutte le righe nella griglia.</span><span class="sxs-lookup"><span data-stu-id="db351-188">On the **Vendor payments** page, select all rows in the grid.</span></span>
4. <span data-ttu-id="db351-189">Selezionare **Stato del pagamento** \> **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="db351-189">Select **Payment status** \> **None**.</span></span>

    ![Pagamenti per l'elaborazione nella pagina Pagamenti fornitore](../media/er-design-configuration-word-2016-11-image05.png)

5. <span data-ttu-id="db351-191">Nel riquadro azioni, seleziona **Genera pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="db351-191">On the Action Pane, select **Generate payments**.</span></span>
6. <span data-ttu-id="db351-192">Nella finestra di dialogo che viene visualizzata, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="db351-192">In the dialog box that appears, follow these steps:</span></span>

    1. <span data-ttu-id="db351-193">Nel campo **Metodo di pagamento** seleziona **Elettronico**.</span><span class="sxs-lookup"><span data-stu-id="db351-193">In the **Method of payment** field, select **Electronic**.</span></span>
    2. <span data-ttu-id="db351-194">Nel campo **Conto bancario** selezionare **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="db351-194">In the **Bank account** field, select **GBSI OPER**.</span></span>
    3. <span data-ttu-id="db351-195">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="db351-195">Select **OK**.</span></span>

7. <span data-ttu-id="db351-196">Nella finestra di dialogo **Parametri per la creazione di report elettronici** selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="db351-196">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="db351-197">L'output generato viene visualizzato nel formato di Word e contiene i dettagli dei pagamenti elaborati.</span><span class="sxs-lookup"><span data-stu-id="db351-197">The generated output is presented in Word format and contains the details of the processed payments.</span></span> <span data-ttu-id="db351-198">Analizzare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="db351-198">Analyze the generated output.</span></span>

    ![Output generato in formato Word](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a><span data-ttu-id="db351-200">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="db351-200">Additional resources</span></span>

- [<span data-ttu-id="db351-201">Progettare una nuova configurazione ER per generare report in formato Word</span><span class="sxs-lookup"><span data-stu-id="db351-201">Design a new ER configuration to generate reports in Word format</span></span>](../er-design-configuration-word.md)
- [<span data-ttu-id="db351-202">Incorporare immagini e forme nei documenti generati utilizzando ER</span><span class="sxs-lookup"><span data-stu-id="db351-202">Embed images and shapes in documents that you generate by using ER</span></span>](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]