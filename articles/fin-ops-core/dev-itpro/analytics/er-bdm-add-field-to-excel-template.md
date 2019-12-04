---
title: Aggiungere nuovi campi a un modello di documento aziendale in Microsoft Excel
description: In questo argomento vengono fornite informazioni sull'aggiunta di nuovi campi a un modello di documento aziendale in Microsoft Excel utilizzando la funzionalità di gestione dei documenti aziendali.
author: NickSelin
manager: AnnBe
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: d6e0f2c914b8d348ef6eac42557fb46c53df04a9
ms.sourcegitcommit: d16d370dab734e09312cb06711beca9cca52d4c9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "2809522"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a><span data-ttu-id="2a045-103">Aggiungere nuovi campi a un modello di documento aziendale in Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="2a045-103">Add new fields to a business document template in Microsoft Excel</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2a045-104">È possibile aggiungere nuovi campi a un modello utilizzato per generare i documenti aziendali nel formato Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="2a045-104">You can add new fields to a template that is used to generate business documents in Microsoft Excel format.</span></span> <span data-ttu-id="2a045-105">Questi campi possono essere aggiunti come segnaposto che vengono utilizzati per completare i documenti generati con le informazioni richieste dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a045-105">These fields can be added as placeholders that are used to fill generated documents with required information from the application.</span></span> <span data-ttu-id="2a045-106">Per ogni campo aggiunto, è possibile anche specificare un'associazione alle origini dati, per specificare quali dati dell'applicazione verranno inseriti nel campo quando il modello viene utilizzato per generare documenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="2a045-106">For every field that you add, you can also specify a binding to the data sources, to specify what application data will be entered in the field when the template is used to generate business documents.</span></span>

<span data-ttu-id="2a045-107">Per ulteriori informazioni su questa funzionalità, completare l'esempio in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2a045-107">To learn more about this feature, complete the example in this topic.</span></span> <span data-ttu-id="2a045-108">Questo esempio mostra come aggiornare un modello per compilare i campi nei moduli di fattura a testo libero generati.</span><span class="sxs-lookup"><span data-stu-id="2a045-108">This example shows how to update a template to fill in the fields in free text invoice forms that are generated.</span></span>

## <a name="configure-business-document-management-to-edit-templates"></a><span data-ttu-id="2a045-109">Configurare Gestione documenti aziendali per modificare i modelli</span><span class="sxs-lookup"><span data-stu-id="2a045-109">Configure Business document management to edit templates</span></span>

<span data-ttu-id="2a045-110">Poiché la gestione dei documenti aziendali (BDM) si basa sul framework della [panoramica del reporting elettronico (ER)](general-electronic-reporting.md), è necessario configurare i parametri ER e BDM richiesti prima di poter iniziare a lavorare con BDM.</span><span class="sxs-lookup"><span data-stu-id="2a045-110">Because Business document management (BDM) is built on top of the [Electronic reporting (ER) overview](general-electronic-reporting.md) framework, you must configure the required ER and BDM parameters before you can start to work with BDM.</span></span>

1.  <span data-ttu-id="2a045-111">Accedere all'istanza di Microsoft Dynamics 365 Finance come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="2a045-111">Sign in to the instance of Microsoft Dynamics 365 Finance as the system administrator.</span></span>
2.  <span data-ttu-id="2a045-112">Completare i seguenti passaggi dell'esempio nell'argomento [Panoramica di gestione dei documenti aziendali](er-business-document-management.md) :</span><span class="sxs-lookup"><span data-stu-id="2a045-112">Complete the following steps of the example in the [Business document management overview](er-business-document-management.md) topic:</span></span>

    1.  <span data-ttu-id="2a045-113">Configurare i parametri ER.</span><span class="sxs-lookup"><span data-stu-id="2a045-113">Configure ER parameters.</span></span>
    2.  <span data-ttu-id="2a045-114">Attivare il BDM.</span><span class="sxs-lookup"><span data-stu-id="2a045-114">Turn on BDM.</span></span>

<span data-ttu-id="2a045-115">È ora possibile iniziare a utilizzare BDM per modificare i modelli di documenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="2a045-115">You can now start to use BDM to edit business document templates.</span></span>

## <a name="import-er-solutions-that-contain-a-template"></a><span data-ttu-id="2a045-116">Importare le soluzioni ER che contengono un modello</span><span class="sxs-lookup"><span data-stu-id="2a045-116">Import ER solutions that contain a template</span></span>

<span data-ttu-id="2a045-117">L'esempio in questa procedura utilizza la soluzione ER pubblicata ufficialmente.</span><span class="sxs-lookup"><span data-stu-id="2a045-117">The example in this procedure uses the officially published ER solution.</span></span> <span data-ttu-id="2a045-118">È necessario importare le configurazioni ER di questa soluzione nell'istanza corrente di Finance.</span><span class="sxs-lookup"><span data-stu-id="2a045-118">You must import the ER configurations of this solution into your current instance of Finance.</span></span>

<span data-ttu-id="2a045-119">La configurazione del formato ER con **fattura a testo libero (Excel)** di questa soluzione contiene il modello di documento aziendale in formato Excel che può essere modificato utilizzando il BDM.</span><span class="sxs-lookup"><span data-stu-id="2a045-119">The **Free text invoice (Excel)** ER format configuration of this solution contains the business document template in Excel format that can be edited by using BDM.</span></span> <span data-ttu-id="2a045-120">Importare l'ultima versione della configurazione del formato ER da Microsoft Dynamics Lifecycle Service (LCS).</span><span class="sxs-lookup"><span data-stu-id="2a045-120">Import the latest version of this ER format configuration from Microsoft Dynamics Lifecycle Service (LCS).</span></span> <span data-ttu-id="2a045-121">Il corrispondente modello di dati ER e le configurazioni di mapping di modello ER verranno importati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2a045-121">The corresponding ER data model and ER model mapping configurations will be imported automatically.</span></span>

<span data-ttu-id="2a045-122">Per ulteriori informazioni su come importare le configurazioni ER, vedere [Gestire il ciclo di vita della configurazione ER](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="2a045-122">For more information about how to import ER configurations, see [Manage the ER configuration lifecycle](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Pagina Raccolta di risorse condivise LCS](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a><span data-ttu-id="2a045-124">Modificare il modello di soluzione ER</span><span class="sxs-lookup"><span data-stu-id="2a045-124">Edit the ER solution template</span></span>

1.  <span data-ttu-id="2a045-125">Accedere come utente con accesso all'area di lavoro di **Gestione documenti aziendali**.</span><span class="sxs-lookup"><span data-stu-id="2a045-125">Sign in as a user who has access to the **Business document management** workspace.</span></span>
2.  <span data-ttu-id="2a045-126">Aprire l'area di lavoro di **Gestione documenti aziendali**.</span><span class="sxs-lookup"><span data-stu-id="2a045-126">Open the **Business document management** workspace.</span></span>

    ![Area di lavoro di Gestione documenti aziendali](./media/BDM-AddFldExcel-Workspace.png)

3.  <span data-ttu-id="2a045-128">Nella griglia, selezionare il modello **Fattura a testo libero (Excel)**.</span><span class="sxs-lookup"><span data-stu-id="2a045-128">In the grid, select the **Free text invoice (Excel)** template.</span></span>
4.  <span data-ttu-id="2a045-129">Nel riquadro a destra, selezionare **Nuovo modello** per creare un nuovo modello basato sul modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="2a045-129">In the right pane, select **New template** to create a new template that is based on the selected template.</span></span>
5.  <span data-ttu-id="2a045-130">Nel campo **Titolo**, immettere **Fattura a testo libero (Excel) Contoso** come titolo del nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="2a045-130">In the **Title** field, enter **Free text invoice (Excel) Contoso** as the title of the new template.</span></span>
6.  <span data-ttu-id="2a045-131">Selezionare **OK** per confermare l'avvio del processo di modifica.</span><span class="sxs-lookup"><span data-stu-id="2a045-131">Select **OK** to confirm the start of the editing process.</span></span>

<span data-ttu-id="2a045-132">Viene visualizzata la pagina dell'editor di modelli BDM.</span><span class="sxs-lookup"><span data-stu-id="2a045-132">The BDM template editor page appears.</span></span> <span data-ttu-id="2a045-133">È possibile utilizzare Microsoft Office 365 per modificare il modello selezionato online nel controllo incorporato.</span><span class="sxs-lookup"><span data-stu-id="2a045-133">You can use Microsoft Office 365 to edit the selected template online in the embedded control.</span></span>

![Pagina dell'editor di modelli BDM](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a><span data-ttu-id="2a045-135">Aggiungere l'etichetta per un nuovo campo al modello</span><span class="sxs-lookup"><span data-stu-id="2a045-135">Add the label for a new field to the template</span></span>

1.  <span data-ttu-id="2a045-136">Nella pagina dell'editor di modelli BDM, sulla barra multifunzione di Excel, nella scheda **Visualizza**, selezionare le caselle di controllo **Intestazioni e Linee della griglia** per il modello di Excel modificabile.</span><span class="sxs-lookup"><span data-stu-id="2a045-136">On the BDM template editor page, on the Excel ribbon, on the **View** tab, select the **Headings and Gridlines** check boxes for the editable Excel template.</span></span>

    ![Caselle di controllo Intestazioni e Linee della griglia selezionate](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  <span data-ttu-id="2a045-138">Selezionare le celle **E8:F8**.</span><span class="sxs-lookup"><span data-stu-id="2a045-138">Select cells **E8:F8**.</span></span>
3.  <span data-ttu-id="2a045-139">Sulla barra multifunzione di Excel, nella scheda **Home**, selezionare **Unisci e centra** per unire le celle selezionata in una nuova cella **E8:F8** unita.</span><span class="sxs-lookup"><span data-stu-id="2a045-139">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **E8:F8** cell.</span></span>
4.  <span data-ttu-id="2a045-140">Nella cella unita **E8:F8**, immettere **URL**.</span><span class="sxs-lookup"><span data-stu-id="2a045-140">In the merged cell **E8:F8**, enter **URL**.</span></span>
5.  <span data-ttu-id="2a045-141">Selezionare la cella unita **E7:F7**, selezionare **Copia formato** e quindi selezionare la cella unita **E8: 8** per formattarla come la cella unita **E7:F7**.</span><span class="sxs-lookup"><span data-stu-id="2a045-141">Select merged cell **E7:F7**, select **Format painter**, and then select merged cell **E8:F8** to format it in the same way as merged cell **E7:F7**.</span></span>

    ![Etichetta del nuovo campo aggiunta al modello](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a><span data-ttu-id="2a045-143">Formattare il modello in modo da riservare spazio per un nuovo campo</span><span class="sxs-lookup"><span data-stu-id="2a045-143">Format the template to reserve space for a new field</span></span>

1.  <span data-ttu-id="2a045-144">Nella pagina dell'editor dei modelli BDM, selezionare la cella unita **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="2a045-144">On the BDM template editor page, select merged cell **G8:H8**.</span></span>
2.  <span data-ttu-id="2a045-145">Sulla barra multifunzione di Excel, nella scheda **Home**, selezionare **Unisci e centra** per unire le celle selezionata in una nuova cella **G8:H8** unita.</span><span class="sxs-lookup"><span data-stu-id="2a045-145">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **G8:H8** cell.</span></span>
3.  <span data-ttu-id="2a045-146">Selezionare la cella unita **G7:H7**, selezionare **Copia formato** e quindi selezionare la cella unita **G8:H8** per formattarla come la cella unita **G7:H7**.</span><span class="sxs-lookup"><span data-stu-id="2a045-146">Select merged cell **G7:H7**, select **Format painter**, and then select merged cell **G8:H8** to format it in the same way as merged cell **G7:H7**.</span></span>

    ![Spazio riservato per il nuovo campo](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  <span data-ttu-id="2a045-148">Nel campo **Nome** selezionare **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="2a045-148">In the **Name** box field, select **CompanyInfo**.</span></span>

    <span data-ttu-id="2a045-149">L'intervallo **CompanyInfo** del modello corrente di Excel contiene tutti i campi utilizzati per completare l'intestazione di un report generato con i dettagli della società corrente come parte venditore.</span><span class="sxs-lookup"><span data-stu-id="2a045-149">The **CompanyInfo** range of the current Excel template holds all the fields that are used to fill the header of a generated report with the details of the current company as a seller party.</span></span>

    ![Intervallo CompanyInfo selezionato](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a><span data-ttu-id="2a045-151">Aggiungere un nuovo campo al modello</span><span class="sxs-lookup"><span data-stu-id="2a045-151">Add a new field to the template</span></span>

1.  <span data-ttu-id="2a045-152">Nella pagina **Editor di modelli BDM**, nel riquadro azioni, selezionare **Mostra formato**.</span><span class="sxs-lookup"><span data-stu-id="2a045-152">On the **BDM template editor** page, on the Action Pane, select **Show format**.</span></span>
2.  <span data-ttu-id="2a045-153">Nel riquadro **Struttura del modello**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2a045-153">In the **Template structure** pane, select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2a045-154">È necessario modificare la sezione del modello che si desidera utilizzare come nuovo campo.</span><span class="sxs-lookup"><span data-stu-id="2a045-154">You must adjust the section of the template that you want to use as a new field.</span></span> <span data-ttu-id="2a045-155">Questa modifica è già stata applicata per formattare la cella unita **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="2a045-155">You already made this adjustment by formatting merged cell **G8:H8**.</span></span>

    ![Aggiunta di un nuovo campo al modello](./media/BDM-AddFldExcel-AddCell.png)

3.  <span data-ttu-id="2a045-157">Selezionare **Excel\Cella** per aggiungere un nuovo campo come cella nel modello.</span><span class="sxs-lookup"><span data-stu-id="2a045-157">Select **Excel\Cell** to add a new field as a cell in the template.</span></span>

    <span data-ttu-id="2a045-158">È possibile selezionare **Excel\Intervallo** per aggiungere un nuovo intervallo al modello.</span><span class="sxs-lookup"><span data-stu-id="2a045-158">You can select **Excel\Range** if you want to add a new range to the template.</span></span> <span data-ttu-id="2a045-159">L'intervallo immesso può contenere più celle.</span><span class="sxs-lookup"><span data-stu-id="2a045-159">The range that is entered can contain multiple cells.</span></span> <span data-ttu-id="2a045-160">È possibile aggiungere le celle anche successivamente.</span><span class="sxs-lookup"><span data-stu-id="2a045-160">You can add these cells later.</span></span>
    
    <span data-ttu-id="2a045-161">Si noti che il componente del modello **CompanyInfo** è selezionato automaticamente nel riquadro **Struttura del modello** perché è il componente principale più adatto nella struttura del modello corrente per il campo da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="2a045-161">Notice that the **CompanyInfo** template component, is automatically selected in the **Template structure** pane, because it's the most suitable parent component in the current template structure for the field that you're adding.</span></span>
    
4.  <span data-ttu-id="2a045-162">Nel campo **Intervallo Excel**, immettere **CompanyURL_Value**.</span><span class="sxs-lookup"><span data-stu-id="2a045-162">In the **Excel range** field, enter **CompanyURL_Value**.</span></span>
5.  <span data-ttu-id="2a045-163">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a045-163">Select **OK**.</span></span>

    ![Il campo CompanyURL_Value aggiunto alla struttura del modello](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  <span data-ttu-id="2a045-165">Nel riquadro **Struttura del modello**, selezionare il pulsante con i puntini di sospensione (...) e scegliere **Mostra associazioni**.</span><span class="sxs-lookup"><span data-stu-id="2a045-165">In the **Template structure** pane, select the ellipsis button (...), and then select **Show bindings**.</span></span>

    ![Mostra associazioni selezionato](./media/BDM-AddFldExcel-ShowBindings.png)

    <span data-ttu-id="2a045-167">Nel riquadro **Struttura del modello** verranno visualizzate le origini dati disponibili nel formato ER sottostante.</span><span class="sxs-lookup"><span data-stu-id="2a045-167">The **Template structure** pane now shows the data sources that are available in the underlying ER format.</span></span>

7.  <span data-ttu-id="2a045-168">Selezionare **CompanyInfo_Value** come campo che si prevede di associare a un'origine dati del formato ER sottostante.</span><span class="sxs-lookup"><span data-stu-id="2a045-168">Select **CompanyInfo_Value** as the field that you plan to bind to a data source of the underlying ER format.</span></span>
8.  <span data-ttu-id="2a045-169">Nella sezione **Origini dati** del riquadro **Struttura del modello**, espandere **Modello \> InvoiceBase \> CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="2a045-169">In the **Data sources** section of the **Template structure** pane, expand **Model \> InvoiceBase \> CompanyInfo**.</span></span>
9.  <span data-ttu-id="2a045-170">In **CompanyInfo**, selezionare la voce **WebsiteURI**.</span><span class="sxs-lookup"><span data-stu-id="2a045-170">Under **CompanyInfo**, select the **WebsiteURI** item.</span></span>

    ![Voce WebsiteURI selezionata](./media/BDM-AddFldExcel-BindURL.png)

10. <span data-ttu-id="2a045-172">Selezionare **Associa**.</span><span class="sxs-lookup"><span data-stu-id="2a045-172">Select **Bind**.</span></span>
11. <span data-ttu-id="2a045-173">Nel riquadro **Struttura del modello** selezionare **Salva**, quindi chiudere la pagina dell'editor di modelli BDM.</span><span class="sxs-lookup"><span data-stu-id="2a045-173">In the **Template structure** pane, select **Save**, and then close the BDM template editor page.</span></span>

<span data-ttu-id="2a045-174">Nell'area di lavoro **Gestione documenti aziendali**, nella scheda **Modello** nel riquadro destro viene visualizzato il modello aggiornato.</span><span class="sxs-lookup"><span data-stu-id="2a045-174">In the **Business document management** workspace, the **Template** tab in the right pane shows the updated template.</span></span> <span data-ttu-id="2a045-175">Nella griglia, notare che il campo **Stato** per il modello modificato è diventato **Bozza** e il campo **Revisione** non è più vuoto.</span><span class="sxs-lookup"><span data-stu-id="2a045-175">In the grid, notice that the **Status** field for the edited template has been changed to **Draft**, and the **Revision** field is no longer blank.</span></span> <span data-ttu-id="2a045-176">Queste modifiche indicano che il processo di modifica del modello è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="2a045-176">These changes indicate that the process of editing this template has been started.</span></span>

![Modello modificato nell'area di lavoro di Gestione documenti aziendali](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a><span data-ttu-id="2a045-178">Esaminare le impostazioni aziendali</span><span class="sxs-lookup"><span data-stu-id="2a045-178">Review company settings</span></span>

1.  <span data-ttu-id="2a045-179">Andare a **Amministrazione organizzazione \> Organizzazioni \> Persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="2a045-179">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>
2.  <span data-ttu-id="2a045-180">Nella Scheda dettaglio **Informazioni sul contatto**, verificare che l'URL della società sia immesso.</span><span class="sxs-lookup"><span data-stu-id="2a045-180">On the **Contact information** FastTab, verify that the company URL is entered.</span></span>

![URL della società immesso nella pagina delle persone giuridiche](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a><span data-ttu-id="2a045-182">Generare documenti aziendali per verificare il modello aggiornato</span><span class="sxs-lookup"><span data-stu-id="2a045-182">Generate business documents to test the updated template</span></span>

1.  <span data-ttu-id="2a045-183">Nell'applicazione, modificare la società in **USMF** e passare **Contabilità clienti \> Fatture \> Tutte le fatture a testo libero**.</span><span class="sxs-lookup"><span data-stu-id="2a045-183">In the application, change the company to **USMF**, and go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2.  <span data-ttu-id="2a045-184">Selezionare la fattura **FTI-00000002** e quindi selezionare **Gestione stampa**.</span><span class="sxs-lookup"><span data-stu-id="2a045-184">Select invoice **FTI-00000002**, and then select **Print management**.</span></span>
3.  <span data-ttu-id="2a045-185">Nel riquadro a sinistra, espandere **Modulo - Contabilità clienti \> Documenti \> Fattura a testo libero**.</span><span class="sxs-lookup"><span data-stu-id="2a045-185">In the left pane, expand **Module - accounts receivable \> Documents \> Free text invoice**.</span></span>
4.  <span data-ttu-id="2a045-186">In **Fattura a testo libero** selezionare il livello **Documento originale** per specificare l'ambito delle fatture per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2a045-186">Under **Free text invoice**, select the **Original document** level to specify the scope of invoices for processing.</span></span>
5.  <span data-ttu-id="2a045-187">Nel riquadro a destra, nel campo **Formato report**, selezionare il modello **Fattura a testo libero (Excel) Contoso** per il livello di documento specificato.</span><span class="sxs-lookup"><span data-stu-id="2a045-187">In the right pane, in the **Report format** field, select the **Free text invoice (Excel) Contoso** template for the specified document level.</span></span>

    ![Modello Fattura a testo libero (Excel) Contoso selezionato](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  <span data-ttu-id="2a045-189">Premere **ESC** per chiudere la pagina corrente.</span><span class="sxs-lookup"><span data-stu-id="2a045-189">Press **Esc** to close the current page.</span></span>
7.  <span data-ttu-id="2a045-190">Selezionare **Stampa \> Selezionato**.</span><span class="sxs-lookup"><span data-stu-id="2a045-190">Select **Print \> Selected**.</span></span>
8.  <span data-ttu-id="2a045-191">Scaricare il documento generato e aprirlo in Excel.</span><span class="sxs-lookup"><span data-stu-id="2a045-191">Download the generated document, and open it in Excel.</span></span>

    ![Fattura a testo libero in Excel](./media/BDM-AddFldExcel-PreviewReport.png)

<span data-ttu-id="2a045-193">Il modello modificato viene utilizzato per generare il report delle fatture a testo libero per l'articolo selezionato.</span><span class="sxs-lookup"><span data-stu-id="2a045-193">The modified template is used to generate the free text invoice report for the selected item.</span></span> <span data-ttu-id="2a045-194">Per analizzare il modo in cui questo report viene modificato in seguito ai cambiamenti al modello, eseguire il report in una sessione dell'applicazione subito dopo aver modificato il modello in un'altra sessione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a045-194">To analyze how this report is affected by changes that you make to the template, run the report in one application session immediately after you change the template in another application session.</span></span>

## <a name="related-links"></a><span data-ttu-id="2a045-195">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="2a045-195">Related links</span></span>

[<span data-ttu-id="2a045-196">Panoramica dello strumento di creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="2a045-196">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="2a045-197">Panoramica di gestione dei documenti aziendali</span><span class="sxs-lookup"><span data-stu-id="2a045-197">Business document management overview</span></span>](er-business-document-management.md)

[<span data-ttu-id="2a045-198">Progettare una configurazione per la creazione di report nel formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="2a045-198">Design a configuration for generating reports in OPENXML format</span></span>](tasks/er-design-reports-openxml-2016-11.md)
