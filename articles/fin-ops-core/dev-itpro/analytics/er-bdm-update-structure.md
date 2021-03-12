---
title: Aggiornare la struttura di un modello di documento aziendale
description: In questo argomento viene illustrato come aggiornare la struttura di un modello di documento aziendale utilizzando la funzionalità Gestione documenti aziendali.
author: NickSelin
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: cb0188e372b5f6275472cf040d10bb796eed1858
ms.sourcegitcommit: 95d2fc0fa7d17d3a96f7969f12c985b018b4ff94
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "4728091"
---
# <a name="update-the-structure-of-a-business-document-template"></a><span data-ttu-id="1044b-103">Aggiornare la struttura di un modello di documento aziendale</span><span class="sxs-lookup"><span data-stu-id="1044b-103">Update the structure of a business document template</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="1044b-104">Nel riquadro **Struttura del modello** dell'editor di modelli [Gestione documenti aziendali](er-business-document-management.md), è possibile modificare un modello di documento aziendale [aggiungendo nuovi campi](er-bdm-add-field-to-excel-template.md) a un modello in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="1044b-104">In the **Template structure** pane of the [Business document management](er-business-document-management.md) template editor, you can modify a business document template by [adding new fields](er-bdm-add-field-to-excel-template.md) to a template in Microsoft Excel.</span></span> <span data-ttu-id="1044b-105">La struttura del modello viene quindi aggiornata automaticamente in Dynamics 365 Finance, in modo che rifletta le modifiche apportate nel riquadro **Struttura del modello**.</span><span class="sxs-lookup"><span data-stu-id="1044b-105">The structure of the template is then automatically updated in Dynamics 365 Finance, so that it reflects the changes that you made in the **Template structure** pane.</span></span>

<span data-ttu-id="1044b-106">È inoltre possibile modificare un modello utilizzando funzionalità online Office 365.</span><span class="sxs-lookup"><span data-stu-id="1044b-106">You can also modify a template by using Office 365 online functionality.</span></span> <span data-ttu-id="1044b-107">Ad esempio, puoi aggiungere un nuovo elemento con nome, come un'immagine o una forma, al foglio di lavoro modificabile.</span><span class="sxs-lookup"><span data-stu-id="1044b-107">For example, you can add a new named item, such as a picture or shape, to the editable worksheet.</span></span> <span data-ttu-id="1044b-108">In questo caso, la struttura del modello non viene aggiornata automaticamente in Finance e l'elemento aggiunto non viene visualizzato nel riquadro **Struttura del modello**.</span><span class="sxs-lookup"><span data-stu-id="1044b-108">In this case, the structure of the template isn't automatically updated in Finance, and the item that you added doesn't appear in the **Template structure** pane.</span></span> <span data-ttu-id="1044b-109">Aggiorna manualmente la struttura del modello in Finance selezionando **Aggiorna struttura** nella pagina dell'editor del modello.</span><span class="sxs-lookup"><span data-stu-id="1044b-109">Manually update the template structure in Finance by selecting **Update structure** on the template editor page.</span></span>

<span data-ttu-id="1044b-110">Per ulteriori informazioni su questa funzionalità, completare l'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1044b-110">For more information about this feature, complete the following example.</span></span>

## <a name="example-update-the-structure-of-a-business-document-template"></a><span data-ttu-id="1044b-111">Esempio: aggiornare la struttura di un modello di documento aziendale</span><span class="sxs-lookup"><span data-stu-id="1044b-111">Example: Update the structure of a business document template</span></span>

<span data-ttu-id="1044b-112">Questo esempio mostra come un amministratore di sistema può aggiornare la struttura di un modello di documento aziendale in Finance dopo che il modello è stato modificato in Office Online.</span><span class="sxs-lookup"><span data-stu-id="1044b-112">This example shows how a system administrator can update the structure of a business document template in Finance after the template is modified in Office Online.</span></span> <span data-ttu-id="1044b-113">Le sezioni seguenti spiegano i passaggi coinvolti.</span><span class="sxs-lookup"><span data-stu-id="1044b-113">The following sections explain the steps that are involved.</span></span>

### <a name="prepare-a-business-document-template-for-editing"></a><span data-ttu-id="1044b-114">Prepara un modello di documento aziendale per la modifica</span><span class="sxs-lookup"><span data-stu-id="1044b-114">Prepare a business document template for editing</span></span>

<span data-ttu-id="1044b-115">Completare le seguenti procedure in [Panoramica di gestione dei documenti aziendali](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="1044b-115">Complete the following procedures in [Business document management overview](er-business-document-management.md).</span></span>

1. [<span data-ttu-id="1044b-116">Configurare i parametri ER</span><span class="sxs-lookup"><span data-stu-id="1044b-116">Configure ER parameters</span></span>](er-business-document-management.md#configure-er-parameters)
2. [<span data-ttu-id="1044b-117">Importare soluzioni ER</span><span class="sxs-lookup"><span data-stu-id="1044b-117">Import ER solutions</span></span>](er-business-document-management.md#import-er-solutions)
3. [<span data-ttu-id="1044b-118">Abilitare Gestione documenti aziendali</span><span class="sxs-lookup"><span data-stu-id="1044b-118">Enable Business document management</span></span>](er-business-document-management.md#enable-business-document-management)
4. [<span data-ttu-id="1044b-119">Configurare i parametri</span><span class="sxs-lookup"><span data-stu-id="1044b-119">Configure parameters</span></span>](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a><span data-ttu-id="1044b-120">Modificare un modello di documento aziendale</span><span class="sxs-lookup"><span data-stu-id="1044b-120">Edit a business document template</span></span>

1. <span data-ttu-id="1044b-121">Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.</span><span class="sxs-lookup"><span data-stu-id="1044b-121">In the **Business document management** workspace, select **New document**.</span></span>
2. <span data-ttu-id="1044b-122">Nella pagina **Crea un nuovo modello**, selezionare il modello **Fattura a testo libero (campione ER) (Excel)**.</span><span class="sxs-lookup"><span data-stu-id="1044b-122">On the **Create a new template** page, select the **Free text invoice (ER sample)(Excel)** template.</span></span>
3. <span data-ttu-id="1044b-123">Selezionare **Crea documento**.</span><span class="sxs-lookup"><span data-stu-id="1044b-123">Select **Create document**.</span></span>
4. <span data-ttu-id="1044b-124">Nel campo **Titolo**, immettere **campione FTI Litware**.</span><span class="sxs-lookup"><span data-stu-id="1044b-124">In the **Title** field, enter **FTI sample Litware**.</span></span>
5. <span data-ttu-id="1044b-125">Selezionare **OK** per creare il nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="1044b-125">Select **OK** to create the new template.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1044b-126">Se non hai ancora effettuato l'accesso a Office Online, [verrai reindirizzato alla Office 365 pagina di accesso](er-business-document-management.md#frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="1044b-126">If you haven't yet signed in to Office Online, you're [directed to the Office 365 sign-in page](er-business-document-management.md#frequently-asked-questions).</span></span> <span data-ttu-id="1044b-127">Per tornare al tuo ambiente finanziario, selezionare il pulsante **Indietro** nel browser.</span><span class="sxs-lookup"><span data-stu-id="1044b-127">To return to your Finance environment, select the **Back** button in your browser.</span></span>

    <span data-ttu-id="1044b-128">Il nuovo modello viene aperto per la modifica nel controllo incorporato di Excel Online nella pagina dell'editor del modello.</span><span class="sxs-lookup"><span data-stu-id="1044b-128">The new template is opened for editing in the Excel Online embedded control on the template editor page.</span></span>

<span data-ttu-id="1044b-129">[![Utilizzo dell'area di lavoro di Gestione documenti aziendali per iniziare a modificare un modello di documento aziendale](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span><span class="sxs-lookup"><span data-stu-id="1044b-129">[![Using the Business document management workspace to start to edit a business document template](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span></span>

### <a name="review-the-current-structure-of-the-editable-template"></a><span data-ttu-id="1044b-130">Rivedi la struttura corrente del modello modificabile</span><span class="sxs-lookup"><span data-stu-id="1044b-130">Review the current structure of the editable template</span></span>

1. <span data-ttu-id="1044b-131">In Excel Online, nella barra multifunzione, nella scheda **Visualizza**, nel gruppo **Mostra**, selezionare **Linee della griglia**.</span><span class="sxs-lookup"><span data-stu-id="1044b-131">In Excel Online, on the ribbon, on the **View** tab, in the **Show** group, select **Gridlines**.</span></span>
2. <span data-ttu-id="1044b-132">Nel modello modificabile, seleziona il rettangolo sopra il titolo del modello.</span><span class="sxs-lookup"><span data-stu-id="1044b-132">In the editable template, select the rectangle above the template title.</span></span> <span data-ttu-id="1044b-133">Questo rettangolo è un'immagine denominata **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="1044b-133">This rectangle is a picture that is named **rptHeaderCompLogo**.</span></span>
3. <span data-ttu-id="1044b-134">Se il riquadro **Struttura del modello** è nascosto, selezionare **Mostra struttura**.</span><span class="sxs-lookup"><span data-stu-id="1044b-134">If the **Template structure** pane is hidden, select **Show structure**.</span></span>
4. <span data-ttu-id="1044b-135">Nel riquadro **Struttura del modello**, espandere **Report \> Fattura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="1044b-135">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="1044b-136">Si noti che, nella struttura del modello in Finance, l'elemento **rptHeaderCompLogo** viene presentato come elemento secondario di **Report \> Fattura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="1044b-136">Notice that, in the template structure in Finance, the **rptHeaderCompLogo** item is presented as a child item of **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>

<span data-ttu-id="1044b-137">[![Utilizzo dell'area di lavoro Gestione documenti aziendali per rivedere la struttura corrente di un modello modificabile](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span><span class="sxs-lookup"><span data-stu-id="1044b-137">[![Using the Business document management workspace to review the current structure of an editable template](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a><span data-ttu-id="1044b-138">Aggiornare la struttura di un modello di documento aziendale eliminando un'immagine</span><span class="sxs-lookup"><span data-stu-id="1044b-138">Update the structure of a business document template by deleting a picture</span></span>

1. <span data-ttu-id="1044b-139">In Excel Online, nel modello modificabile, selezionare l'immagine **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="1044b-139">In Excel Online, in the editable template, select the **rptHeaderCompLogo** picture.</span></span>
2. <span data-ttu-id="1044b-140">Segui uno di questi passaggi per eliminare l'immagine selezionata dal modello modificabile:</span><span class="sxs-lookup"><span data-stu-id="1044b-140">Follow one of these steps to delete the selected picture from the editable template:</span></span>

    - <span data-ttu-id="1044b-141">Selezionare il tasto **Elimina** sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="1044b-141">Select the **Delete** key on your keyboard.</span></span>
    - <span data-ttu-id="1044b-142">Selezionare e tenere premuto (o fare clic con il pulsante destro del mouse) sull'immagine, quindi selezionare **Taglia**.</span><span class="sxs-lookup"><span data-stu-id="1044b-142">Select and hold (or right-click) the picture, and then select **Cut**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1044b-143">L'elemento **rptHeaderCompLogo** è attualmente ancora presente nella struttura del modello in Finance, anche se l'immagine non è più inclusa nel modello Excel.</span><span class="sxs-lookup"><span data-stu-id="1044b-143">The **rptHeaderCompLogo** item is currently still present in the template structure in Finance, even though the picture is no longer included in the Excel template.</span></span>

3. <span data-ttu-id="1044b-144">Selezionare **Aggiorna struttura** per sincronizzare la struttura del modello modificabile in Excel e Finance.</span><span class="sxs-lookup"><span data-stu-id="1044b-144">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
4. <span data-ttu-id="1044b-145">Nel riquadro **Struttura del modello**, espandere **Report \> Fattura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="1044b-145">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="1044b-146">Si noti che l'elemento **rptHeaderCompLogo** non è più incluso nella struttura del modello in Finance.</span><span class="sxs-lookup"><span data-stu-id="1044b-146">Notice that the **rptHeaderCompLogo** item is no longer included in the template structure in Finance.</span></span>

<span data-ttu-id="1044b-147">[![Utilizzo dell'area di lavoro di Gestione documenti aziendali per eliminare un'immagine da un modello di documento aziendale](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span><span class="sxs-lookup"><span data-stu-id="1044b-147">[![Using the Business document management workspace to delete a picture from a business document template](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a><span data-ttu-id="1044b-148">Aggiornare la struttura di un modello di documento aziendale aggiungendo un'immagine</span><span class="sxs-lookup"><span data-stu-id="1044b-148">Update the structure of a business document template by adding a picture</span></span>

1. <span data-ttu-id="1044b-149">In Excel Online, nella barra multifunzione, nella scheda **Inserisci**, nel gruppo **Figure**, selezionare **Immagine**.</span><span class="sxs-lookup"><span data-stu-id="1044b-149">In Excel Online, on the ribbon, on the **Insert** tab, in the **Illustrations** group, select **Picture**.</span></span>
2. <span data-ttu-id="1044b-150">Selezionare **Scegli il file**, individuare l'immagine che si desidera aggiungere, selezionarla e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="1044b-150">Select **Choose file**, browse to the image that you want to add, select it, and then select **OK**.</span></span>
3. <span data-ttu-id="1044b-151">Selezionare **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="1044b-151">Select **Insert**.</span></span>
4. <span data-ttu-id="1044b-152">Sposta la nuova immagine finché non si trova nella posizione corretta.</span><span class="sxs-lookup"><span data-stu-id="1044b-152">Move the new picture until it's in the correct place.</span></span> <span data-ttu-id="1044b-153">Per impostazione predefinita, Excel assegna un nome all'immagine.</span><span class="sxs-lookup"><span data-stu-id="1044b-153">By default, Excel names the picture.</span></span> <span data-ttu-id="1044b-154">Ad esempio, potrebbe denominare l'immagine **Immagine 2**.</span><span class="sxs-lookup"><span data-stu-id="1044b-154">For example, it might name the picture **Picture 2**.</span></span>
5. <span data-ttu-id="1044b-155">Selezionare **Aggiorna struttura** per sincronizzare la struttura del modello modificabile in Excel e Finance.</span><span class="sxs-lookup"><span data-stu-id="1044b-155">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
6. <span data-ttu-id="1044b-156">Nel riquadro **Struttura del modello**, espandere **Report \> Fattura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="1044b-156">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
7. <span data-ttu-id="1044b-157">Si noti che la nuova immagine è ora inclusa come un elemento nella struttura del modello in Finance.</span><span class="sxs-lookup"><span data-stu-id="1044b-157">Notice that the new picture is now included as an item in the template structure in Finance.</span></span>

<span data-ttu-id="1044b-158">[![Utilizzo dell'area di lavoro di Gestione documenti aziendali per aggiungere un'immagine a un modello di documento aziendale](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span><span class="sxs-lookup"><span data-stu-id="1044b-158">[![Using the Business document management workspace to add a picture to a business document template](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span></span>

## <a name="related-links"></a><span data-ttu-id="1044b-159">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="1044b-159">Related links</span></span>

[<span data-ttu-id="1044b-160">Panoramica dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="1044b-160">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="1044b-161">Panoramica di gestione dei documenti aziendali</span><span class="sxs-lookup"><span data-stu-id="1044b-161">Business document management overview</span></span>](er-business-document-management.md)
