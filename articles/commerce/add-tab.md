---
title: Modulo Scheda
description: In questo argomento vengono descritti i moduli Scheda e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 60af9b74f7e647e83229e352a03c09d63d0c7902
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417371"
---
# <a name="tab-module"></a><span data-ttu-id="d8f52-103">Modulo Scheda</span><span class="sxs-lookup"><span data-stu-id="d8f52-103">Tab module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="d8f52-104">In questo argomento vengono descritti i moduli Scheda e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d8f52-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d8f52-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d8f52-105">Overview</span></span>

<span data-ttu-id="d8f52-106">I moduli Scheda sono moduli simili a contenitori utilizzati per organizzare le informazioni in una pagina di sito in schede.</span><span class="sxs-lookup"><span data-stu-id="d8f52-106">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="d8f52-107">Possono essere utilizzati in qualsiasi pagina in cui le informazioni devono essere presentate in schede.</span><span class="sxs-lookup"><span data-stu-id="d8f52-107">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="d8f52-108">In ogni modulo Scheda, è possibile aggiungere uno o più moduli Elemento scheda.</span><span class="sxs-lookup"><span data-stu-id="d8f52-108">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="d8f52-109">Ogni modulo Elemento scheda rappresenta una singola scheda. In ciascun modulo Elemento scheda, è possibile aggiungere uno o più moduli.</span><span class="sxs-lookup"><span data-stu-id="d8f52-109">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="d8f52-110">Non vi sono restrizioni sui tipi di moduli che possono essere aggiunti a un modulo Elemento scheda.</span><span class="sxs-lookup"><span data-stu-id="d8f52-110">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="d8f52-111">L'immagine seguente mostra un esempio di modulo Scheda in una pagina di sito.</span><span class="sxs-lookup"><span data-stu-id="d8f52-111">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="d8f52-112">In questo esempio, è selezionata la scheda **Spedizione**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-112">In this example, the **Shipping** tab selected.</span></span>

![Esempio di modulo Scheda](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="d8f52-114">Proprietà dei moduli Scheda</span><span class="sxs-lookup"><span data-stu-id="d8f52-114">Tab module properties</span></span>

| <span data-ttu-id="d8f52-115">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="d8f52-115">Property name</span></span> | <span data-ttu-id="d8f52-116">Valori</span><span class="sxs-lookup"><span data-stu-id="d8f52-116">Values</span></span> | <span data-ttu-id="d8f52-117">descrizione</span><span class="sxs-lookup"><span data-stu-id="d8f52-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="d8f52-118">Intestazione</span><span class="sxs-lookup"><span data-stu-id="d8f52-118">Heading</span></span> | <span data-ttu-id="d8f52-119">Testo</span><span class="sxs-lookup"><span data-stu-id="d8f52-119">Text</span></span> | <span data-ttu-id="d8f52-120">Questa proprietà specifica un'intestazione di testo facoltativa per il modulo Scheda.</span><span class="sxs-lookup"><span data-stu-id="d8f52-120">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="d8f52-121">Indice scheda attivo</span><span class="sxs-lookup"><span data-stu-id="d8f52-121">Active Tab Index</span></span> | <span data-ttu-id="d8f52-122">Numero</span><span class="sxs-lookup"><span data-stu-id="d8f52-122">Number</span></span> | <span data-ttu-id="d8f52-123">Questa proprietà specifica la scheda che deve essere attiva per impostazione predefinita quando viene caricata una pagina.</span><span class="sxs-lookup"><span data-stu-id="d8f52-123">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="d8f52-124">Se non viene fornito alcun valore, il primo elemento scheda è attivo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d8f52-124">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="d8f52-125">Proprietà dei moduli Elemento scheda</span><span class="sxs-lookup"><span data-stu-id="d8f52-125">Tab item module properties</span></span>

| <span data-ttu-id="d8f52-126">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="d8f52-126">Property name</span></span> | <span data-ttu-id="d8f52-127">Valori</span><span class="sxs-lookup"><span data-stu-id="d8f52-127">Values</span></span> | <span data-ttu-id="d8f52-128">descrizione</span><span class="sxs-lookup"><span data-stu-id="d8f52-128">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="d8f52-129">Funzione</span><span class="sxs-lookup"><span data-stu-id="d8f52-129">Title</span></span> | <span data-ttu-id="d8f52-130">Testo</span><span class="sxs-lookup"><span data-stu-id="d8f52-130">Text</span></span> | <span data-ttu-id="d8f52-131">Questa proprietà specifica il testo del titolo del modulo Elemento scheda.</span><span class="sxs-lookup"><span data-stu-id="d8f52-131">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="d8f52-132">Aggiungere un modulo Scheda a una pagina</span><span class="sxs-lookup"><span data-stu-id="d8f52-132">Add a tab module to a page</span></span>

<span data-ttu-id="d8f52-133">Per aggiungere un modulo Scheda a una pagina e impostare le proprietà, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="d8f52-133">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="d8f52-134">Utilizzare il modello di marketing Fabrikam (o qualsiasi modello che non abbia restrizioni) per creare una nuova pagina denominata **Pagina delle politiche del punto vendita**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-134">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="d8f52-135">Nello slot **Principale** della **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-135">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d8f52-136">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-136">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d8f52-137">Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-137">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d8f52-138">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Scheda** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-138">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d8f52-139">Nel riquadro delle proprietà del modulo Scheda, selezionare **Intestazione** accanto al simbolo della matita.</span><span class="sxs-lookup"><span data-stu-id="d8f52-139">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="d8f52-140">Nella finestra di dialogo **Intestazione**, sotto **Testo intestazione**, immettere il testo dell'intestazione (ad esempio, **Politiche**).</span><span class="sxs-lookup"><span data-stu-id="d8f52-140">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="d8f52-141">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-141">Then select **OK**.</span></span>
1. <span data-ttu-id="d8f52-142">Nello slot **Scheda** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-142">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d8f52-143">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Elemento scheda** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-143">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d8f52-144">Nel riquadro delle proprietà del modulo Elemento scheda, sotto **Titolo**, immettere il testo del titolo (ad esempio, **Consegna**).</span><span class="sxs-lookup"><span data-stu-id="d8f52-144">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="d8f52-145">Nello slot **Elemento scheda** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-145">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d8f52-146">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Blocco di testo** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8f52-146">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d8f52-147">Nel riquadro delle proprietà del modulo Blocco di testo, sotto **RTF**, immettere un paragrafo di testo.</span><span class="sxs-lookup"><span data-stu-id="d8f52-147">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="d8f52-148">Nello slot **Scheda**, aggiungere altri moduli Elemento scheda che hanno titoli.</span><span class="sxs-lookup"><span data-stu-id="d8f52-148">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="d8f52-149">In ogni modulo Elemento scheda, aggiungere un modulo Blocco di testo che abbia contenuto.</span><span class="sxs-lookup"><span data-stu-id="d8f52-149">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="d8f52-150">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="d8f52-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="d8f52-151">La pagina mostrerà un modulo Scheda che contiene moduli Elemento scheda con il contenuto aggiunto.</span><span class="sxs-lookup"><span data-stu-id="d8f52-151">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="d8f52-152">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="d8f52-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d8f52-153">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d8f52-153">Additional resources</span></span>

[<span data-ttu-id="d8f52-154">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="d8f52-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d8f52-155">Modulo Contenitore</span><span class="sxs-lookup"><span data-stu-id="d8f52-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="d8f52-156">Modulo Accordion</span><span class="sxs-lookup"><span data-stu-id="d8f52-156">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="d8f52-157">Modulo Blocco testo</span><span class="sxs-lookup"><span data-stu-id="d8f52-157">Text block module</span></span>](add-content-rich-block.md)
