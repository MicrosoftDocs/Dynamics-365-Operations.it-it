---
title: Sopprimere i controlli del contenuto di Word nei report generati
description: In questo argomento viene descritto come configurare un formato di creazione di report elettronici (ER) per generare report come file Microsoft Word in cui i controlli del contenuto sono stati eliminati.
author: NickSelin
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 8c99203110cfdc7f8123c30488611d55f48e8f67
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753603"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a><span data-ttu-id="2d4a9-103">Sopprimere i controlli del contenuto di Word nei report generati</span><span class="sxs-lookup"><span data-stu-id="2d4a9-103">Suppress Word content controls in generated reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2d4a9-104">Per generare report come documenti Microsoft Word, è necessario progettare un modello per i report come documento Word.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-104">To generate reports as Microsoft Word documents, you must design a template for the reports as a Word document.</span></span> <span data-ttu-id="2d4a9-105">Questo modello deve contenere controlli del contenuto di Word come segnaposto per i dati che verranno compilati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-105">This template must contain Word content controls as placeholders for data that will be filled in at runtime.</span></span> <span data-ttu-id="2d4a9-106">Per utilizzare il documento Word creato come modello per i report, è possibile [configurare](er-design-configuration-word.md) una nuova [soluzione](er-quick-start1-new-solution.md) di [Creazione di report elettronici (ER)](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="2d4a9-106">To use the Word document that is created as a template for your reports, you can [configure](er-design-configuration-word.md) a new [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md).</span></span> <span data-ttu-id="2d4a9-107">La soluzione deve includere una [configurazione](general-electronic-reporting.md#Configuration) ER che contiene un componente in [formato](general-electronic-reporting.md#FormatComponentOutbound) ER.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-107">The solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="2d4a9-108">Questo formato ER deve essere configurato per utilizzare il modello progettato per la generazione di report.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-108">This ER format must be configured to use the designed template for report generation.</span></span>

<span data-ttu-id="2d4a9-109">Nella versione 10.0.6 e successive di Dynamics 365 Finance, è possibile configurare formule nel formato ER per sopprimere alcuni controlli del contenuto di Word nei documenti generati.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-109">In version 10.0.6 and later of Dynamics 365 Finance, you can configure formulas in your ER format to suppress some Word content controls in generated documents.</span></span>

<span data-ttu-id="2d4a9-110">I passaggi seguenti spiegano come un utente assegnato al ruolo di amministratore di sistema o di consulente funzionale per la creazione di report elettronici può configurare un formato ER che genera report come file Word e sopprime alcuni dei controlli del contenuto nei report generati che sono stati configurati utilizzando un modello Word.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-110">The following steps explain how a user who is assigned to the System administrator or Electronic reporting functional consultant role can configure an ER format that generates reports as Word files and suppresses some of the content controls in the generated reports that have been configured by using a Word template.</span></span>

<span data-ttu-id="2d4a9-111">Questi passaggi possono essere completati nella società GBSI.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-111">These steps can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d4a9-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2d4a9-112">Prerequisites</span></span>

<span data-ttu-id="2d4a9-113">Per effettuare questi passaggi, è necessario completare quelli nelle seguenti guide attività:</span><span class="sxs-lookup"><span data-stu-id="2d4a9-113">To complete these steps, you must first complete the steps in the following task guides:</span></span>

- [<span data-ttu-id="2d4a9-114">Progettare una configurazione per la creazione di report nel formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="2d4a9-114">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="2d4a9-115">Riutilizzare le configurazioni per la creazione di report elettronici con modelli di Excel per generare report in formato Word</span><span class="sxs-lookup"><span data-stu-id="2d4a9-115">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)

<span data-ttu-id="2d4a9-116">Dopo aver completato i passaggi di queste guide attività, vengono preparati i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="2d4a9-116">When you complete the steps of these task guides, the following items are prepared:</span></span>

- <span data-ttu-id="2d4a9-117">Un formato ER **Report foglio di lavoro di esempio** configurato per generare un documento in formato Word</span><span class="sxs-lookup"><span data-stu-id="2d4a9-117">A **Sample worksheet report** ER format that is configured to generate a document in Word format</span></span>
- <span data-ttu-id="2d4a9-118">Una versione [bozza](general-electronic-reporting.md#component-versioning) del formato ER **Report del foglio di lavoro di esempio** contrassegnato come **Eseguibile**</span><span class="sxs-lookup"><span data-stu-id="2d4a9-118">A [draft](general-electronic-reporting.md#component-versioning) version of the **Sample worksheet report** ER format that is marked as **Runnable**</span></span>
- <span data-ttu-id="2d4a9-119">Un metodo di pagamento **Elettronico** configurato per utilizzare il formato ER **Report del foglio di lavoro di esempio** per l'elaborazione dei pagamenti del fornitore</span><span class="sxs-lookup"><span data-stu-id="2d4a9-119">An **Electronic** method of payments that is configured to use the **Sample worksheet report** ER format for vendor payment processing</span></span>

<span data-ttu-id="2d4a9-120">È inoltre necessario scaricare e salvare il seguente modello per il report di esempio:</span><span class="sxs-lookup"><span data-stu-id="2d4a9-120">You must also download and save the following template for the sample report:</span></span>

- [<span data-ttu-id="2d4a9-121">Modello associato 2 di Report di pagamento (SampleVendPaymDocReportBounded2.docx)</span><span class="sxs-lookup"><span data-stu-id="2d4a9-121">Bounded Template 2 of Payment Report (SampleVendPaymDocReportBounded2.docx)</span></span>](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a><span data-ttu-id="2d4a9-122">Rivedere il modello di Word scaricato</span><span class="sxs-lookup"><span data-stu-id="2d4a9-122">Review the downloaded Word template</span></span>

1. <span data-ttu-id="2d4a9-123">Nell'applicazione desktop Word, aprire il file del modello **SampleVendPaymDocReportBounded2.docx** scaricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-123">In the Word desktop application, open the **SampleVendPaymDocReportBounded2.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="2d4a9-124">Verificare che il file del modello contenga una sezione di riepilogo che mostra gli importi totali dei pagamenti per ogni codice valuta che è stato soddisfatto nei pagamenti elaborati.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-124">Verify that the template file contains a summary section that shows the total payment amounts for every currency code that has been met in the processed payments.</span></span>

    - <span data-ttu-id="2d4a9-125">La sezione di riepilogo risiede in una tabella separata del documento Word.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-125">The summary section resides in a separate table of the Word document.</span></span>
    - <span data-ttu-id="2d4a9-126">La prima riga di questa tabella contiene le intestazioni delle colonne della tabella come intestazione di sezione.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-126">The first row of this table holds the table columns headings as the section header.</span></span>
    - <span data-ttu-id="2d4a9-127">La seconda riga di questa tabella contiene il controllo del contenuto ripetuto come dettagli della sezione.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-127">The second row of this table holds the repeating content control as the section details.</span></span>
    - <span data-ttu-id="2d4a9-128">Questo controllo del contenuto è mappato al campo **SummaryLines** della parte XML personalizzata **Report**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-128">This content control is mapped to the **SummaryLines** field of the **Report** custom XML part.</span></span>
    - <span data-ttu-id="2d4a9-129">In base a questo mapping, il controllo del contenuto è associato all'elemento **SummaryLines** del formato ER modificabile.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-129">Based on this mapping, the content control is associated with the **SummaryLines** element of the editable ER format.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d4a9-130">Il controllo del contenuto ripetuto è contrassegnato con la chiave **SummaryLines** che corrisponde al campo della parte XML personalizzata a cui è stata mappata.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-130">The repeating content control is tagged by the **SummaryLines** key that matches the field of the custom XML part that it has been mapped to.</span></span>

    ![Layout del modello Word](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="2d4a9-132">Selezionare la configurazione esistente del report ER</span><span class="sxs-lookup"><span data-stu-id="2d4a9-132">Select the existing ER report configuration</span></span>

<span data-ttu-id="2d4a9-133">Per i passaggi seguenti, si riutilizzerà la configurazione ER esistente configurata quando sono stati completati i passaggi nelle guide attività menzionate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-133">For the following steps, you will reuse the existing ER configuration that you configured when you completed the steps in the previously mentioned task guides.</span></span>

1. <span data-ttu-id="2d4a9-134">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-134">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="2d4a9-135">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-135">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="2d4a9-136">Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di pagamento**, quindi selezionare **Report foglio di lavoro di esempio**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-136">On the **Configurations** page, in the configuration tree, expand **Payment model**, and select **Sample worksheet report**.</span></span>
4. <span data-ttu-id="2d4a9-137">Selezionare **Designer** per modificare la versione bozza del formato ER selezionato.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-137">Select **Designer** to edit the draft version of the selected ER format.</span></span>

## <a name="replace-the-current-template-with-the-new-template"></a><span data-ttu-id="2d4a9-138">Sostituire il modello corrente con il nuovo modello</span><span class="sxs-lookup"><span data-stu-id="2d4a9-138">Replace the current template with the new template</span></span>

<span data-ttu-id="2d4a9-139">Attualmente, il file SampleVendPaymDocReportBounded.docx viene utilizzato come modello per generare l'output nel formato Word.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-139">Currently, the SampleVendPaymDocReportBounded.docx file is used as a template to generate the output in Word format.</span></span> <span data-ttu-id="2d4a9-140">Nei passaggi seguenti, questo modello di Word verrà sostituito con il nuovo modello di Word, SampleVendPaymDocReportBounded2.docx caricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-140">In the following steps, you will replace this Word template with the new Word template, SampleVendPaymDocReportBounded2.docx, that you downloaded earlier.</span></span>

1. <span data-ttu-id="2d4a9-141">Nella pagina **Progettazione formati**, selezionare **Allegati**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-141">On the **Format designer** page, select **Attachments**.</span></span>
2. <span data-ttu-id="2d4a9-142">Nella pagina **Allegati**, selezionare **Elimina** per rimuovere il modello esistente.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-142">On the **Attachments** page, select **Delete** to remove the existing template.</span></span>
3. <span data-ttu-id="2d4a9-143">Selezionare **Sì** per confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-143">Select **Yes** to confirm the deletion.</span></span>
4. <span data-ttu-id="2d4a9-144">Seleziona **Nuovo** \> **File**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-144">Select **New** \> **File**.</span></span>
5. <span data-ttu-id="2d4a9-145">Selezionare **Sfoglia** e individuare e selezionare il file **SampleVendPaymDocReportBounded2.docx** scaricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-145">Select **Browse**, and browse to and select the **SampleVendPaymDocReportBounded2.docx** file that you downloaded earlier.</span></span>
6. <span data-ttu-id="2d4a9-146">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-146">Select **OK**.</span></span>
7. <span data-ttu-id="2d4a9-147">Chiudere la pagina **Allegati**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-147">Close the **Attachments** page.</span></span>
8. <span data-ttu-id="2d4a9-148">Nella pagina **Progettazione formati** nel campo **Modello**, immettere o selezionare il file **SampleVendPaymDocReportBounded2.docx**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-148">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReportBounded2.docx** file.</span></span>

## <a name="run-the-format-to-create-word-output"></a><span data-ttu-id="2d4a9-149">Eseguire il formato per creare l'output di Word</span><span class="sxs-lookup"><span data-stu-id="2d4a9-149">Run the format to create Word output</span></span>

1. <span data-ttu-id="2d4a9-150">Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-150">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="2d4a9-151">Nella pagina **Pagamenti fornitore**, nella scheda **Elenco**, selezionare tutti i pagamenti.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-151">On the **Vendor payments** page, on the **List** tab, select all the payments.</span></span>
3. <span data-ttu-id="2d4a9-152">Selezionare **Stato del pagamento** \> **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-152">Select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="2d4a9-153">Selezionare **Genera pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-153">Select **Generate payments**.</span></span>
5. <span data-ttu-id="2d4a9-154">Nel campo **Metodo di pagamento** seleziona **Elettronico**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-154">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="2d4a9-155">Nel campo **Conto bancario** selezionare **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-155">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="2d4a9-156">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-156">Select **OK**.</span></span>
8. <span data-ttu-id="2d4a9-157">Nella finestra di dialogo **Parametri per la creazione di report elettronici**, selezionare **OK** e analizzare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-157">In the **Electronic report parameters** dialog box, select **OK**, and analyze the generated output.</span></span>

    ![Pagamenti per l'elaborazione nella pagina Pagamenti fornitore](./media/er-design-configuration-word-suppress-controls-image2.gif)

    <span data-ttu-id="2d4a9-159">L'output viene presentato in formato Word e contiene la sezione di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-159">The output is presented in Word format and contains the summary section.</span></span>

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a><span data-ttu-id="2d4a9-160">Configurare il formato modificabile per sopprimere la sezione di riepilogo</span><span class="sxs-lookup"><span data-stu-id="2d4a9-160">Configure the editable format to suppress the summary section</span></span>

<span data-ttu-id="2d4a9-161">Se si desidera sopprimere la sezione di riepilogo in un documento generato, in base alla richiesta di un utente che esegue questo formato ER, è necessario modificare il formato ER modificabile.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-161">If you want to suppress the summary section in a generated document, based on the request of a user who runs this ER format, you must modify the editable ER format.</span></span>

1. <span data-ttu-id="2d4a9-162">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici** e aprire la versione bozza del formato ER da modificare.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-162">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**, and open the draft version of the ER format for editing.</span></span>
2. <span data-ttu-id="2d4a9-163">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-163">Select **Reporting configurations**.</span></span> 
3. <span data-ttu-id="2d4a9-164">Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di pagamento** \> **Report foglio di lavoro di esempio**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-164">On the **Configurations** page, in the configuration tree, expand **Payment model** \> **Sample worksheet report**.</span></span>
4. <span data-ttu-id="2d4a9-165">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-165">Select **Designer**.</span></span>
5. <span data-ttu-id="2d4a9-166">Nella pagina **Progettazione formati**, espandere **Word** e selezionare **SummaryLines**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-166">On the **Format designer** page, expand **Word**, and select **SummaryLines**.</span></span>
6. <span data-ttu-id="2d4a9-167">Nella scheda **Mapping**, aggiungere una nuova origine dati per chiedere all'utente, in fase di runtime, se la sezione di riepilogo deve essere soppressa:</span><span class="sxs-lookup"><span data-stu-id="2d4a9-167">On the **Mapping** tab, add a new data source to ask the user, at runtime, whether the summary section should be suppressed:</span></span>

    1. <span data-ttu-id="2d4a9-168">Selezionare **Aggiungi radice**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-168">Select **Add root**.</span></span>
    2. <span data-ttu-id="2d4a9-169">Nella finestra di dialogo **Aggiungi origine dati**, selezionare **Generale\Parametro di input utente** per aprire la finestra di dialogo **Proprietà origine dati "Parametro di input utente"**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-169">In the **Add data source** dialog box, select **General\User input parameter** to open the **'User input parameter' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="2d4a9-170">Nel campo **Nome** immettere **uipSuppress**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-170">In the **Name** field, enter **uipSuppress**.</span></span>
    4. <span data-ttu-id="2d4a9-171">Nel campo **Etichetta**, immettere **Sopprimere la sezione di riepilogo**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-171">In the **Label** field, enter **Suppress summary section**.</span></span>
    5. <span data-ttu-id="2d4a9-172">Nel campo **Nome del tipo di dati delle operazioni**, selezionare o immettere **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-172">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="2d4a9-173">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-173">Select **OK**.</span></span>

7. <span data-ttu-id="2d4a9-174">Aggiungere una nuova origine dati di tipo enumerazione applicazione **NoYes**:</span><span class="sxs-lookup"><span data-stu-id="2d4a9-174">Add a new data source of the **NoYes** application enumeration type:</span></span>

    1. <span data-ttu-id="2d4a9-175">Selezionare **Aggiungi radice**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-175">Select **Add root**.</span></span>
    2. <span data-ttu-id="2d4a9-176">Nella finestra di dialogo **Aggiungi origine dati**, selezionare **Dynamics 365 for Operations\Enumerazione** per aprire la finestra di dialogo **Proprietà origine dati "Enumerazione"**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-176">In the **Add data source** dialog box, select **Dynamics 365 for Operations\Enumeration** to open the **'Enumeration' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="2d4a9-177">Nel campo **Nome** immettere **enumNoYes**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-177">In the **Name** field, enter **enumNoYes**.</span></span>
    4. <span data-ttu-id="2d4a9-178">Nel campo **Etichetta**, immettere **Opzioni di soppressione**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-178">In the **Label** field, enter **Suppress options**.</span></span>
    5. <span data-ttu-id="2d4a9-179">Nel campo **Nome del tipo di dati delle operazioni**, selezionare o immettere **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-179">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="2d4a9-180">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-180">Select **OK**.</span></span>

8. <span data-ttu-id="2d4a9-181">Per l'elemento di formato **SummaryLines** selezionato, configurare la formula per specificare quando il controllo del contenuto di Word associato all'elemento di formato selezionato deve essere soppresso:</span><span class="sxs-lookup"><span data-stu-id="2d4a9-181">For the selected **SummaryLines** format element, configure the formula to specify when the Word content control that is associated with the selected format element should be suppressed:</span></span>

    1. <span data-ttu-id="2d4a9-182">Nella scheda **Mapping**, nella sezione **Rimosso**, selezionare **Modifica** per aprire la pagina **[Designer formula](general-electronic-reporting-formula-designer.md)**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-182">On the **Mapping** tab, in the **Removed** section, select **Edit** to open the **[Formula designer](general-electronic-reporting-formula-designer.md)** page.</span></span>
    2. <span data-ttu-id="2d4a9-183">Nel campo **Formula**, immettere la formula `uipSuppress = enumNoYes.Yes`.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-183">In the **Formula** field, enter the formula `uipSuppress = enumNoYes.Yes`.</span></span>
    3. <span data-ttu-id="2d4a9-184">Selezionare **Salva** e chiudere la pagina **Designer formula**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-184">Select **Save**, and close the **Formula designer** page.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2d4a9-185">Questa formula verrà applicata a un documento generato **dopo l'esecuzione di tutti gli altri elementi di formato**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-185">This formula will be applied to a generated document **after all other format elements are run**.</span></span> <span data-ttu-id="2d4a9-186">Per applicare questa formula, un controllo del contenuto di Word contrassegnato come elemento di formato per cui la formula è configurata (**SummaryLines** in questo caso) si trova in un documento generato.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-186">To apply this formula, a Word content control that is tagged as a format element that the formula is configured for (**SummaryLines** in this case) is found in a generated document.</span></span> <span data-ttu-id="2d4a9-187">Quel controllo del contenuto viene quindi completamente rimosso, insieme alla riga nella tabella di Word che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-187">That content control is then completely removed, together with the row in the Word table that holds it.</span></span> <span data-ttu-id="2d4a9-188">La riga dei dettagli della sezione di riepilogo viene rimossa dal documento generato.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-188">The details row of the summary section is removed from the generated document.</span></span>
        >
        > <span data-ttu-id="2d4a9-189">In fase di progettazione, si potrebbe configurare la formula **Rimosso** per un elemento di formato, anche se nessun controllo del contenuto nel modello di Word che si sta utilizzando ha un tag che corrisponde al nome di un elemento di formato per cui la proprietà **Rimosso** è configurata.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-189">At design time, you might configure the **Removed** formula for a format element, even though no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span> <span data-ttu-id="2d4a9-190">Quando si convalida il formato in fase di progettazione, viene visualizzato un [avviso](er-components-inspections.md#i14) su questa incoerenza.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-190">When you validate the format at design time, you receive a [warning](er-components-inspections.md#i14) about this inconsistency.</span></span>
        >
        > <span data-ttu-id="2d4a9-191">In fase di runtime, viene generata un'eccezione se nessun controllo del contenuto nel modello di Word che si sta utilizzando ha un tag che corrisponde al nome di un elemento di formato per cui la proprietà **Rimosso** è configurata.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-191">At runtime, an exception is thrown if no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span>

    4. <span data-ttu-id="2d4a9-192">Nella scheda **Mapping**, nella sezione **Rimosso**, impostare l'opzione **Con padre** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-192">On the **Mapping** tab, in the **Removed** section, set the **With parent** option to **Yes**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2d4a9-193">È necessario impostare questa opzione su **Sì** per rimuovere l'intera tabella di Word come oggetto padre della riga che contiene i dettagli della sezione di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-193">You must set this option to **Yes** to remove the whole Word table as the parent object of the row that holds the summary section details.</span></span> <span data-ttu-id="2d4a9-194">Se si imposta questa opzione su **No**, la riga di intestazione della sezione rimane nel documento generato.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-194">If you set this option to **No**, the section header row remains in the generated document.</span></span>

9. <span data-ttu-id="2d4a9-195">Selezionare **Salva** per salvare le modifiche al formato modificabile.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-195">Select **Save** to save your changes to the editable format.</span></span>

    ![Output generato in formato Word](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a><span data-ttu-id="2d4a9-197">Eseguire il formato modificato per creare l'output di Word</span><span class="sxs-lookup"><span data-stu-id="2d4a9-197">Run the modified format to create Word output</span></span>

1. <span data-ttu-id="2d4a9-198">Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-198">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="2d4a9-199">Selezionare il giornale di registrazione pagamenti creato, quindi selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-199">Select the payment journal that you created, and then select **Lines**.</span></span>
3. <span data-ttu-id="2d4a9-200">Nella pagina **Pagamenti fornitore**, selezionare tutte le righe, quindi selezionare **Stato pagamenti** \> **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-200">On the **Vendor payments** page, select all the rows, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="2d4a9-201">Selezionare **Genera pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-201">Select **Generate payments**.</span></span>
5. <span data-ttu-id="2d4a9-202">Nel campo **Metodo di pagamento** seleziona **Elettronico**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-202">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="2d4a9-203">Nel campo **Conto bancario** selezionare **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-203">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="2d4a9-204">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-204">Select **OK**.</span></span>
8. <span data-ttu-id="2d4a9-205">Nella finestra di dialogo **Parametri per la creazione di report elettronici**, nel campo **Sopprimi sezione di riepilogo**, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-205">In the **Electronic report parameters** dialog box, in the **Suppress summary section** field, select **Yes**.</span></span>
9. <span data-ttu-id="2d4a9-206">Selezionare **OK** e analizzare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-206">Select **OK**, and analyze the generated output.</span></span>

    ![Output generato in formato Word](./media/er-design-configuration-word-suppress-controls-image4.gif)

    <span data-ttu-id="2d4a9-208">Si noti che l'output non contiene la sezione di riepilogo poiché è stata soppressa.</span><span class="sxs-lookup"><span data-stu-id="2d4a9-208">Notice that the output doesn't contain the summary section, because it has been suppressed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2d4a9-209">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2d4a9-209">Additional resources</span></span>

- [<span data-ttu-id="2d4a9-210">Progettare una configurazione per la creazione di report nel formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="2d4a9-210">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="2d4a9-211">Progettare una configurazione per la generazione di report in formato Word</span><span class="sxs-lookup"><span data-stu-id="2d4a9-211">Design a new ER configuration to generate reports in Word format</span></span>](er-design-configuration-word.md)
- [<span data-ttu-id="2d4a9-212">Riutilizzare le configurazioni per la creazione di report elettronici con modelli di Excel per generare report in formato Word</span><span class="sxs-lookup"><span data-stu-id="2d4a9-212">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)
- [<span data-ttu-id="2d4a9-213">Ispezionare il componente ER configurato per evitare problemi di runtime</span><span class="sxs-lookup"><span data-stu-id="2d4a9-213">Inspect the configured ER component to prevent runtime issues</span></span>](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]