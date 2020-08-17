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
ms.openlocfilehash: b4187dfd704c78d506d7840b04c986687fe807a3
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621015"
---
# <a name="tab-module"></a><span data-ttu-id="80261-103">Modulo Scheda</span><span class="sxs-lookup"><span data-stu-id="80261-103">Tab module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="80261-104">In questo argomento vengono descritti i moduli Scheda e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="80261-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="80261-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="80261-105">Overview</span></span>

<span data-ttu-id="80261-106">I moduli Scheda sono moduli simili a contenitori utilizzati per organizzare le informazioni in una pagina di sito in schede.</span><span class="sxs-lookup"><span data-stu-id="80261-106">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="80261-107">Possono essere utilizzati in qualsiasi pagina in cui le informazioni devono essere presentate in schede.</span><span class="sxs-lookup"><span data-stu-id="80261-107">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="80261-108">In ogni modulo Scheda, è possibile aggiungere uno o più moduli Elemento scheda.</span><span class="sxs-lookup"><span data-stu-id="80261-108">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="80261-109">Ogni modulo Elemento scheda rappresenta una singola scheda. In ciascun modulo Elemento scheda, è possibile aggiungere uno o più moduli.</span><span class="sxs-lookup"><span data-stu-id="80261-109">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="80261-110">Non vi sono restrizioni sui tipi di moduli che possono essere aggiunti a un modulo Elemento scheda.</span><span class="sxs-lookup"><span data-stu-id="80261-110">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="80261-111">L'immagine seguente mostra un esempio di modulo Scheda in una pagina di sito.</span><span class="sxs-lookup"><span data-stu-id="80261-111">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="80261-112">In questo esempio, è selezionata la scheda **Spedizione**.</span><span class="sxs-lookup"><span data-stu-id="80261-112">In this example, the **Shipping** tab selected.</span></span>

![Esempio di modulo Scheda](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="80261-114">Proprietà dei moduli Scheda</span><span class="sxs-lookup"><span data-stu-id="80261-114">Tab module properties</span></span>

| <span data-ttu-id="80261-115">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="80261-115">Property name</span></span> | <span data-ttu-id="80261-116">Valori</span><span class="sxs-lookup"><span data-stu-id="80261-116">Values</span></span> | <span data-ttu-id="80261-117">descrizione</span><span class="sxs-lookup"><span data-stu-id="80261-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="80261-118">Intestazione</span><span class="sxs-lookup"><span data-stu-id="80261-118">Heading</span></span> | <span data-ttu-id="80261-119">Testo</span><span class="sxs-lookup"><span data-stu-id="80261-119">Text</span></span> | <span data-ttu-id="80261-120">Questa proprietà specifica un'intestazione di testo facoltativa per il modulo Scheda.</span><span class="sxs-lookup"><span data-stu-id="80261-120">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="80261-121">Indice scheda attivo</span><span class="sxs-lookup"><span data-stu-id="80261-121">Active Tab Index</span></span> | <span data-ttu-id="80261-122">Numero</span><span class="sxs-lookup"><span data-stu-id="80261-122">Number</span></span> | <span data-ttu-id="80261-123">Questa proprietà specifica la scheda che deve essere attiva per impostazione predefinita quando viene caricata una pagina.</span><span class="sxs-lookup"><span data-stu-id="80261-123">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="80261-124">Se non viene fornito alcun valore, il primo elemento scheda è attivo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="80261-124">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="80261-125">Proprietà dei moduli Elemento scheda</span><span class="sxs-lookup"><span data-stu-id="80261-125">Tab item module properties</span></span>

| <span data-ttu-id="80261-126">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="80261-126">Property name</span></span> | <span data-ttu-id="80261-127">Valori</span><span class="sxs-lookup"><span data-stu-id="80261-127">Values</span></span> | <span data-ttu-id="80261-128">descrizione</span><span class="sxs-lookup"><span data-stu-id="80261-128">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="80261-129">Funzione</span><span class="sxs-lookup"><span data-stu-id="80261-129">Title</span></span> | <span data-ttu-id="80261-130">Testo</span><span class="sxs-lookup"><span data-stu-id="80261-130">Text</span></span> | <span data-ttu-id="80261-131">Questa proprietà specifica il testo del titolo del modulo Elemento scheda.</span><span class="sxs-lookup"><span data-stu-id="80261-131">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="80261-132">Aggiungere un modulo Scheda a una pagina</span><span class="sxs-lookup"><span data-stu-id="80261-132">Add a tab module to a page</span></span>

<span data-ttu-id="80261-133">Per aggiungere un modulo Scheda a una pagina e impostare le proprietà, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="80261-133">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="80261-134">Utilizzare il modello di marketing Fabrikam (o qualsiasi modello che non abbia restrizioni) per creare una nuova pagina denominata **Pagina delle politiche del punto vendita**.</span><span class="sxs-lookup"><span data-stu-id="80261-134">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="80261-135">Nello slot **Principale** della **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="80261-135">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="80261-136">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="80261-136">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="80261-137">Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="80261-137">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="80261-138">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Scheda** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="80261-138">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="80261-139">Nel riquadro delle proprietà del modulo Scheda, selezionare **Intestazione** accanto al simbolo della matita.</span><span class="sxs-lookup"><span data-stu-id="80261-139">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="80261-140">Nella finestra di dialogo **Intestazione**, sotto **Testo intestazione**, immettere il testo dell'intestazione (ad esempio, **Politiche**).</span><span class="sxs-lookup"><span data-stu-id="80261-140">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="80261-141">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="80261-141">Then select **OK**.</span></span>
1. <span data-ttu-id="80261-142">Nello slot **Scheda** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="80261-142">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="80261-143">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Elemento scheda** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="80261-143">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="80261-144">Nel riquadro delle proprietà del modulo Elemento scheda, sotto **Titolo**, immettere il testo del titolo (ad esempio, **Consegna**).</span><span class="sxs-lookup"><span data-stu-id="80261-144">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="80261-145">Nello slot **Elemento scheda** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="80261-145">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="80261-146">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Blocco di testo** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="80261-146">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="80261-147">Nel riquadro delle proprietà del modulo Blocco di testo, sotto **RTF**, immettere un paragrafo di testo.</span><span class="sxs-lookup"><span data-stu-id="80261-147">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="80261-148">Nello slot **Scheda**, aggiungere altri moduli Elemento scheda che hanno titoli.</span><span class="sxs-lookup"><span data-stu-id="80261-148">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="80261-149">In ogni modulo Elemento scheda, aggiungere un modulo Blocco di testo che abbia contenuto.</span><span class="sxs-lookup"><span data-stu-id="80261-149">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="80261-150">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="80261-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="80261-151">La pagina mostrerà un modulo Scheda che contiene moduli Elemento scheda con il contenuto aggiunto.</span><span class="sxs-lookup"><span data-stu-id="80261-151">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="80261-152">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="80261-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="80261-153">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="80261-153">Additional resources</span></span>

[<span data-ttu-id="80261-154">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="80261-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="80261-155">Modulo Contenitore</span><span class="sxs-lookup"><span data-stu-id="80261-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="80261-156">Modulo Accordion</span><span class="sxs-lookup"><span data-stu-id="80261-156">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="80261-157">Modulo Blocco testo</span><span class="sxs-lookup"><span data-stu-id="80261-157">Text block module</span></span>](add-content-rich-block.md)
