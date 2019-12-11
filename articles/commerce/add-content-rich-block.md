---
title: Modulo Blocco ricco di contenuti
description: In questo argomento vengono descritti i moduli Blocco ricco di contenuti e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785423"
---
# <a name="content-rich-block-module"></a><span data-ttu-id="bec05-103">Modulo Blocco ricco di contenuti</span><span class="sxs-lookup"><span data-stu-id="bec05-103">Content rich block module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="bec05-104">In questo argomento vengono descritti i moduli Blocco ricco di contenuti e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bec05-104">This topic covers content rich block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bec05-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="bec05-105">Overview</span></span>

<span data-ttu-id="bec05-106">Un modulo Blocco ricco di contenuti è un contenitore speciale in cui è possibile inserire uno o più elementi blocco ricco di contenuti.</span><span class="sxs-lookup"><span data-stu-id="bec05-106">A content rich block module is a special container that one or more content rich block items can be put inside.</span></span> <span data-ttu-id="bec05-107">I moduli Blocco ricco di contenuti sono utilizzati per contenuto testuale in una pagina.</span><span class="sxs-lookup"><span data-stu-id="bec05-107">Content rich block modules are used for textual content on a page.</span></span> <span data-ttu-id="bec05-108">Questo contenuto può essere informativo o promozionale.</span><span class="sxs-lookup"><span data-stu-id="bec05-108">This content can be either informational or promotional.</span></span>

<span data-ttu-id="bec05-109">I moduli Blocco ricco di contenuti sono basati sui dati del sistema di gestione dei contenuti (CMS) e possono essere utilizzati in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="bec05-109">Content rich block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="bec05-110">Sono moduli autonomi che non dipendono dal contesto della pagina o da qualsiasi altro modulo.</span><span class="sxs-lookup"><span data-stu-id="bec05-110">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a><span data-ttu-id="bec05-111">Esempi di moduli Blocco ricco di contenuti in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="bec05-111">Examples of content rich block modules in e-Commerce</span></span>

<span data-ttu-id="bec05-112">I moduli Blocco ricco di contenuti possono essere utilizzati nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="bec05-112">Content rich block modules can be used in the following ways:</span></span>

* <span data-ttu-id="bec05-113">Per visualizzare caratteristiche dei prodotti in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="bec05-113">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="bec05-114">Per scopi informativi in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="bec05-114">For informational purposes on any page.</span></span> <span data-ttu-id="bec05-115">Ad esempio, possono spiegare i vantaggi dei programmi fedeltà, descrivere le condizioni di spedizione e reso, rispondere alle domande frequenti oppure fornire contenuto "chi siamo".</span><span class="sxs-lookup"><span data-stu-id="bec05-115">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="bec05-116">Per aggiungere messaggi personalizzati in una pagina dettagli prodotto</span><span class="sxs-lookup"><span data-stu-id="bec05-116">To add custom messages on a product details page.</span></span> <span data-ttu-id="bec05-117">(ad esempio, "Spedizione gratuita per ordini superiori a 50 €").</span><span class="sxs-lookup"><span data-stu-id="bec05-117">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="bec05-118">Per le dichiarazioni di non responsabilità e le informazioni di contatto nelle pagine dettagli prodotto, carrello, checkout e altre pagine (ad esempio "Spedizioni e resi sono soggetti alle politiche del punto vendita").</span><span class="sxs-lookup"><span data-stu-id="bec05-118">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="content-rich-block-module-properties"></a><span data-ttu-id="bec05-119">Proprietà del modulo Blocco ricco di contenuti</span><span class="sxs-lookup"><span data-stu-id="bec05-119">Content rich block module properties</span></span>

| <span data-ttu-id="bec05-120">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="bec05-120">Property name</span></span>     | <span data-ttu-id="bec05-121">Valore</span><span class="sxs-lookup"><span data-stu-id="bec05-121">Value</span></span>                                 | <span data-ttu-id="bec05-122">Proprietà</span><span class="sxs-lookup"><span data-stu-id="bec05-122">Property</span></span> |
|-------------------|---------------------------------------|----------|
| <span data-ttu-id="bec05-123">Numero di colonne</span><span class="sxs-lookup"><span data-stu-id="bec05-123">Number of columns</span></span> | <span data-ttu-id="bec05-124">Un numero da **1** a **4**</span><span class="sxs-lookup"><span data-stu-id="bec05-124">A number from **1** through **4**</span></span>     | <span data-ttu-id="bec05-125">Il numero di colonne nel blocco ricco di contenuti.</span><span class="sxs-lookup"><span data-stu-id="bec05-125">The number of columns in the content rich block.</span></span> <span data-ttu-id="bec05-126">È possibile avere fino a quattro colonne.</span><span class="sxs-lookup"><span data-stu-id="bec05-126">There can be up to four columns.</span></span> |
| <span data-ttu-id="bec05-127">Larghezza</span><span class="sxs-lookup"><span data-stu-id="bec05-127">Width</span></span>             | <span data-ttu-id="bec05-128">**Riempi contenitore** o **Riempi schermo**</span><span class="sxs-lookup"><span data-stu-id="bec05-128">**Fill container** or **Fill screen**</span></span> | <span data-ttu-id="bec05-129">Se il valore è **Riempi contenitore**, gli elementi nel contenitore sono limitati alla larghezza del contenitore.</span><span class="sxs-lookup"><span data-stu-id="bec05-129">If the value is set to **Fill container**, the items inside the container are restricted to the width of the container.</span></span> <span data-ttu-id="bec05-130">Se il valore impostato è **Riempi schermo**, gli elementi non sono limitati alla larghezza del contenitore ma possono essere visualizzati in modalità a schermo intero.</span><span class="sxs-lookup"><span data-stu-id="bec05-130">If the value is set to **Fill screen**, the items aren't restricted to the container width but can go into full-screen mode.</span></span> <span data-ttu-id="bec05-131">È possibile modificare il valore per ottenere il layout desiderato.</span><span class="sxs-lookup"><span data-stu-id="bec05-131">You can change the value to achieve the desired layout.</span></span> |

## <a name="content-rich-block-item-module-properties"></a><span data-ttu-id="bec05-132">Proprietà del modulo Elemento blocco ricco di contenuti</span><span class="sxs-lookup"><span data-stu-id="bec05-132">Content rich block item module properties</span></span>

| <span data-ttu-id="bec05-133">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="bec05-133">Property name</span></span> | <span data-ttu-id="bec05-134">Valore</span><span class="sxs-lookup"><span data-stu-id="bec05-134">Value</span></span>          | <span data-ttu-id="bec05-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bec05-135">Description</span></span> |
|---------------|----------------|-------------|
| <span data-ttu-id="bec05-136">Paragrafo</span><span class="sxs-lookup"><span data-stu-id="bec05-136">Paragraph</span></span>     | <span data-ttu-id="bec05-137">Testo di paragrafo</span><span class="sxs-lookup"><span data-stu-id="bec05-137">Paragraph text</span></span> | <span data-ttu-id="bec05-138">Il testo che accompagna ogni elemento blocco ricco di contenuti.</span><span class="sxs-lookup"><span data-stu-id="bec05-138">The text that accompanies each content rich block item.</span></span> <span data-ttu-id="bec05-139">Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo.</span><span class="sxs-lookup"><span data-stu-id="bec05-139">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |

## <a name="add-a-content-rich-block-module-to-a-page"></a><span data-ttu-id="bec05-140">Aggiungere un modulo Blocco ricco di contenuti a una pagina</span><span class="sxs-lookup"><span data-stu-id="bec05-140">Add a content rich block module to a page</span></span>

<span data-ttu-id="bec05-141">Per aggiungere un modulo Blocco ricco di contenuti a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="bec05-141">To add a content rich block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="bec05-142">Creare un modello di pagina denominato **Modello contenuto**.</span><span class="sxs-lookup"><span data-stu-id="bec05-142">Create a page template that is named **Content template**.</span></span>
1. <span data-ttu-id="bec05-143">Nello slot **Principale** della pagina predefinita, aggiungere un modulo Blocco ricco di contenuti.</span><span class="sxs-lookup"><span data-stu-id="bec05-143">In the **Main** slot of the default page, add a content rich block module.</span></span>
1. <span data-ttu-id="bec05-144">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="bec05-144">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="bec05-145">Utilizzare il modello di contenuto appena creato per creare una pagina denominata **Pagina contenuto**.</span><span class="sxs-lookup"><span data-stu-id="bec05-145">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="bec05-146">Nello slot **Principale** della nuova pagina, aggiungere un modulo Blocco ricco di contenuti.</span><span class="sxs-lookup"><span data-stu-id="bec05-146">In the **Main** slot of the new page, add a content rich block module.</span></span>
1. <span data-ttu-id="bec05-147">Nelle proprietà del modulo Blocco ricco di contenuti, impostare il numero di colonne su **2**.</span><span class="sxs-lookup"><span data-stu-id="bec05-147">In the properties of the content rich block module, set number of columns to **2**.</span></span>
1. <span data-ttu-id="bec05-148">Nel modulo Blocco ricco di contenuti, selezionare **Aggiungi un modulo** e aggiungere un elemento blocco ricco di contenuti (ad esempio **item1**).</span><span class="sxs-lookup"><span data-stu-id="bec05-148">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item1**).</span></span>
1. <span data-ttu-id="bec05-149">Nel nuovo elemento blocco ricco di contenuti, aggiungere il testo di paragrafo.</span><span class="sxs-lookup"><span data-stu-id="bec05-149">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="bec05-150">Nel modulo Blocco ricco di contenuti, selezionare **Aggiungi un modulo** e aggiungere un elemento blocco ricco di contenuti (ad esempio **item2**).</span><span class="sxs-lookup"><span data-stu-id="bec05-150">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item2**).</span></span>
1. <span data-ttu-id="bec05-151">Nel nuovo elemento blocco ricco di contenuti, aggiungere il testo di paragrafo.</span><span class="sxs-lookup"><span data-stu-id="bec05-151">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="bec05-152">Salvare la pagina e visualizzare un'anteprima delle modifiche</span><span class="sxs-lookup"><span data-stu-id="bec05-152">Save the page, and preview the changes.</span></span> <span data-ttu-id="bec05-153">Dovrebbero essere visualizzati due blocchi ricchi di contenuti in una visualizzazione a due colonne.</span><span class="sxs-lookup"><span data-stu-id="bec05-153">You should see two rich text blocks in a two-column view.</span></span>
1. <span data-ttu-id="bec05-154">Archiviare la pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="bec05-154">Check in the page, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="bec05-155">Se si aggiunge un terzo elemento blocco ricco di contenuti, verrà impilato sotto i due elementi aggiunti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bec05-155">If you add a third content rich block item, it will be stacked below the two items that you previously added.</span></span> <span data-ttu-id="bec05-156">Modificando il numero di colonne ed elementi nel contenitore, è possibile ottenere differenti layout per contenuto testuale.</span><span class="sxs-lookup"><span data-stu-id="bec05-156">By changing the number of columns and items in the container, you can achieve different layouts for textual content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bec05-157">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="bec05-157">Additional resources</span></span>

[<span data-ttu-id="bec05-158">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="bec05-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bec05-159">Modulo Avviso</span><span class="sxs-lookup"><span data-stu-id="bec05-159">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="bec05-160">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="bec05-160">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="bec05-161">Modulo Posizionamento contenuti</span><span class="sxs-lookup"><span data-stu-id="bec05-161">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="bec05-162">Modulo Funzionalità</span><span class="sxs-lookup"><span data-stu-id="bec05-162">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="bec05-163">Modulo Hero</span><span class="sxs-lookup"><span data-stu-id="bec05-163">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="bec05-164">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="bec05-164">Video player module</span></span>](add-video-player.md)

