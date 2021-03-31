---
title: Modulo Accordion
description: In questo argomento vengono descritti i moduli Accordion e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a08441f5dffa9c2c65b304d0265dd107a838a685
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206609"
---
# <a name="accordion-module"></a><span data-ttu-id="56341-103">Modulo Accordion</span><span class="sxs-lookup"><span data-stu-id="56341-103">Accordion module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="56341-104">In questo argomento vengono descritti i moduli Accordion e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="56341-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="56341-105">I moduli Accordion sono moduli simili a contenitori utilizzati per organizzare informazioni o moduli in una pagina fornendo una funzionalità comprimibile di tipo pannello.</span><span class="sxs-lookup"><span data-stu-id="56341-105">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="56341-106">Un modulo Accordion può essere utilizzato in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="56341-106">An accordion module can be used on any page.</span></span>

<span data-ttu-id="56341-107">In ogni modulo Accordion, è possibile aggiungere uno o più moduli Elemento accordion.</span><span class="sxs-lookup"><span data-stu-id="56341-107">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="56341-108">Ogni modulo Elemento accordion rappresenta un pannello comprimibile.</span><span class="sxs-lookup"><span data-stu-id="56341-108">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="56341-109">In ogni modulo Elemento accordion, è possibile aggiungere uno o più moduli.</span><span class="sxs-lookup"><span data-stu-id="56341-109">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="56341-110">Non vi sono restrizioni sui tipi di moduli che possono essere aggiunti a un modulo Elemento accordion.</span><span class="sxs-lookup"><span data-stu-id="56341-110">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="56341-111">L'immagine seguente mostra un esempio di modulo Accordion utilizzato per organizzare le informazioni sulla pagina delle domande frequenti di un punto vendita.</span><span class="sxs-lookup"><span data-stu-id="56341-111">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Esempio di modulo Accordion](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="56341-113">Proprietà del modulo Accordion</span><span class="sxs-lookup"><span data-stu-id="56341-113">Accordion module properties</span></span>

| <span data-ttu-id="56341-114">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="56341-114">Property name</span></span> | <span data-ttu-id="56341-115">Valori</span><span class="sxs-lookup"><span data-stu-id="56341-115">Values</span></span> | <span data-ttu-id="56341-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56341-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="56341-117">Intestazione</span><span class="sxs-lookup"><span data-stu-id="56341-117">Heading</span></span> | <span data-ttu-id="56341-118">Testo</span><span class="sxs-lookup"><span data-stu-id="56341-118">Text</span></span> | <span data-ttu-id="56341-119">Questa proprietà specifica un'intestazione di testo facoltativa per il modulo Accordion.</span><span class="sxs-lookup"><span data-stu-id="56341-119">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="56341-120">Espandi tutto</span><span class="sxs-lookup"><span data-stu-id="56341-120">Expand All</span></span> | <span data-ttu-id="56341-121">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="56341-121">**True** or **False**</span></span> | <span data-ttu-id="56341-122">Se il valore è impostato su **True**, la funzionalità di espansione/compressione è attivata, di modo che tutti gli elementi nel modulo Accordion possano essere espansi e compressi.</span><span class="sxs-lookup"><span data-stu-id="56341-122">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="56341-123">Stile interazione</span><span class="sxs-lookup"><span data-stu-id="56341-123">Interaction Style</span></span> | <span data-ttu-id="56341-124">**Indipendente** o **Espandi un solo elemento**</span><span class="sxs-lookup"><span data-stu-id="56341-124">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="56341-125">Questa proprietà definisce lo stile di interazione per gli elementi accordion.</span><span class="sxs-lookup"><span data-stu-id="56341-125">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="56341-126">Se il valore è impostato su **Indipendente**, ogni elemento accordion può essere espanso o compresso indipendentemente.</span><span class="sxs-lookup"><span data-stu-id="56341-126">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="56341-127">Se il valore è impostato su **Espandi un solo elemento**, è possibile espandere un solo elemento alla volta.</span><span class="sxs-lookup"><span data-stu-id="56341-127">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="56341-128">Man mano che gli oggetti vengono espansi, gli oggetti precedentemente espansi vengono compressi.</span><span class="sxs-lookup"><span data-stu-id="56341-128">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="56341-129">Proprietà del modulo Elemento accordion</span><span class="sxs-lookup"><span data-stu-id="56341-129">Accordion item module properties</span></span>

| <span data-ttu-id="56341-130">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="56341-130">Property name</span></span> | <span data-ttu-id="56341-131">Valori</span><span class="sxs-lookup"><span data-stu-id="56341-131">Values</span></span> | <span data-ttu-id="56341-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56341-132">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="56341-133">Funzione</span><span class="sxs-lookup"><span data-stu-id="56341-133">Title</span></span> | <span data-ttu-id="56341-134">Testo</span><span class="sxs-lookup"><span data-stu-id="56341-134">Text</span></span> | <span data-ttu-id="56341-135">Questa proprietà specifica il testo del titolo del modulo Elemento accordion.</span><span class="sxs-lookup"><span data-stu-id="56341-135">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="56341-136">Selezionando l'area del titolo, gli utenti possono espandere o comprimere la sezione.</span><span class="sxs-lookup"><span data-stu-id="56341-136">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="56341-137">Espandi per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="56341-137">Expand by default</span></span> | <span data-ttu-id="56341-138">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="56341-138">**True** or **False**</span></span> | <span data-ttu-id="56341-139">Se il valore è impostato su **True**, l'elemento accordion viene espanso per impostazione predefinita quando viene caricata la pagina.</span><span class="sxs-lookup"><span data-stu-id="56341-139">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="56341-140">Aggiungere un modulo Accordion a una pagina Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="56341-140">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="56341-141">Per aggiungere un modulo Accordion a una pagina Domande frequenti e impostarne le proprietà in Creazione di siti Web, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="56341-141">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="56341-142">Andare a **Pagine** e utilizzare il modello di marketing Fabrikam (o qualsiasi modello che non abbia restrizioni) per creare una nuova pagina denominata **Domande frequenti punto vendita**.</span><span class="sxs-lookup"><span data-stu-id="56341-142">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="56341-143">Nello slot **Principale** della **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="56341-143">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="56341-144">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="56341-144">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="56341-145">Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="56341-145">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="56341-146">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Accordion** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="56341-146">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="56341-147">Nel riquadro delle proprietà del modulo Accordion, selezionare **Intestazione** accanto al simbolo della matita.</span><span class="sxs-lookup"><span data-stu-id="56341-147">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="56341-148">Nella finestra di dialogo **Intestazione**, sotto **Testo intestazione**, immettere **Domande frequenti**.</span><span class="sxs-lookup"><span data-stu-id="56341-148">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="56341-149">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="56341-149">Then select **OK**.</span></span>
1. <span data-ttu-id="56341-150">Nel riquadro delle proprietà del modulo Accordion, selezionare la casella di controllo **Mostra espandi tutto**, quindi nel campo **Stile interazione**, selezionare **Indipendente**.</span><span class="sxs-lookup"><span data-stu-id="56341-150">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="56341-151">Nello slot **Accordion** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="56341-151">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="56341-152">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Elemento accordion** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="56341-152">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="56341-153">Nel riquadro delle proprietà del modulo Elemento accordion, sotto **Titolo**, immettere il testo del titolo (ad esempio, **Come si effettua un reso?**).</span><span class="sxs-lookup"><span data-stu-id="56341-153">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="56341-154">Nello slot **Elemento accordion** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="56341-154">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="56341-155">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Blocco di testo** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="56341-155">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="56341-156">Nel riquadro delle proprietà del modulo Blocco di testo, immettere un paragrafo di testo (ad esempio, **I resi devono essere effettuati tramite il call center contattando 1-800-FABRIKAM. I prodotti devono essere restituiti entro 30 giorni dalla ricezione.**).</span><span class="sxs-lookup"><span data-stu-id="56341-156">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="56341-157">Nello slot **Accordion**, aggiungere altri modulo Elemento accordion.</span><span class="sxs-lookup"><span data-stu-id="56341-157">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="56341-158">In ogni modulo Elemento accordion, aggiungere un modulo Blocco di testo che abbia contenuto.</span><span class="sxs-lookup"><span data-stu-id="56341-158">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="56341-159">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="56341-159">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="56341-160">La pagina mostrerà un modulo Accordion con il contenuto aggiunto.</span><span class="sxs-lookup"><span data-stu-id="56341-160">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="56341-161">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="56341-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56341-162">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="56341-162">Additional resources</span></span>

[<span data-ttu-id="56341-163">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="56341-163">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="56341-164">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="56341-164">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="56341-165">Modulo scheda</span><span class="sxs-lookup"><span data-stu-id="56341-165">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="56341-166">Modulo blocco testo</span><span class="sxs-lookup"><span data-stu-id="56341-166">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]