---
title: Modulo blocco di testo
description: In questo argomento vengono descritti i moduli blocco di testo e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025599"
---
# <a name="text-block-module"></a><span data-ttu-id="bbcc1-103">Modulo blocco di testo</span><span class="sxs-lookup"><span data-stu-id="bbcc1-103">Text block module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="bbcc1-104">In questo argomento vengono descritti i moduli blocco di testo e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bbcc1-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="bbcc1-105">Overview</span></span>

<span data-ttu-id="bbcc1-106">Un modulo blocco di testo è un modulo utilizzato per aggiungere contenuto testuale.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="bbcc1-107">Questo contenuto può essere informativo o promozionale.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="bbcc1-108">I moduli blocco di testo sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="bbcc1-109">Sono moduli autonomi che non dipendono dal contesto della pagina o da qualsiasi altro modulo.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="bbcc1-110">Esempi di moduli blocco di testo in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="bbcc1-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="bbcc1-111">I moduli blocco di testo possono essere utilizzati nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="bbcc1-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="bbcc1-112">Per visualizzare caratteristiche dei prodotti in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="bbcc1-113">Per scopi informativi in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-113">For informational purposes on any page.</span></span> <span data-ttu-id="bbcc1-114">Ad esempio, possono spiegare i vantaggi dei programmi fedeltà, descrivere le condizioni di spedizione e reso, rispondere alle domande frequenti oppure fornire contenuto "chi siamo".</span><span class="sxs-lookup"><span data-stu-id="bbcc1-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="bbcc1-115">Per aggiungere messaggi personalizzati in una pagina dettagli prodotto</span><span class="sxs-lookup"><span data-stu-id="bbcc1-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="bbcc1-116">(ad esempio, "Spedizione gratuita per ordini superiori a 50 €").</span><span class="sxs-lookup"><span data-stu-id="bbcc1-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="bbcc1-117">Per le dichiarazioni di non responsabilità e le informazioni di contatto nelle pagine dettagli prodotto, carrello, checkout e altre pagine (ad esempio "Spedizioni e resi sono soggetti alle politiche del punto vendita").</span><span class="sxs-lookup"><span data-stu-id="bbcc1-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="text-block-module-properties"></a><span data-ttu-id="bbcc1-118">Proprietà dei moduli blocco di testo</span><span class="sxs-lookup"><span data-stu-id="bbcc1-118">Text block module properties</span></span>

| <span data-ttu-id="bbcc1-119">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="bbcc1-119">Property name</span></span>     | <span data-ttu-id="bbcc1-120">Value</span><span class="sxs-lookup"><span data-stu-id="bbcc1-120">Value</span></span>                                            | <span data-ttu-id="bbcc1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbcc1-121">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="bbcc1-122">RTF</span><span class="sxs-lookup"><span data-stu-id="bbcc1-122">Rich text</span></span>         | <span data-ttu-id="bbcc1-123">RTF</span><span class="sxs-lookup"><span data-stu-id="bbcc1-123">Rich text</span></span>                                        | <span data-ttu-id="bbcc1-124">Testo di paragrafo.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-124">Paragraph text.</span></span> <span data-ttu-id="bbcc1-125">Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-125">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="bbcc1-126">Nome classe personalizzato</span><span class="sxs-lookup"><span data-stu-id="bbcc1-126">Custom class name</span></span> | <span data-ttu-id="bbcc1-127">Il nome di una classe Cascading Style Sheets (CSS)</span><span class="sxs-lookup"><span data-stu-id="bbcc1-127">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="bbcc1-128">Il nome di una classe CSS personalizzata fornita da uno sviluppatore per formattare questo modulo.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-128">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="bbcc1-129">Il nome della classe deve essere definito nel pacchetto di temi.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-129">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="bbcc1-130">Dimensione carattere</span><span class="sxs-lookup"><span data-stu-id="bbcc1-130">Font size</span></span>         | <span data-ttu-id="bbcc1-131">**Piccolo**, **Medio**, **Grande** o **Grandissimo**</span><span class="sxs-lookup"><span data-stu-id="bbcc1-131">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="bbcc1-132">La dimensione del carattere del contenuto.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-132">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="bbcc1-133">Aggiungere un modulo blocco di testo a una pagina</span><span class="sxs-lookup"><span data-stu-id="bbcc1-133">Add a text block module to a page</span></span>

<span data-ttu-id="bbcc1-134">Per aggiungere un modulo blocco di testo a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-134">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="bbcc1-135">Creare un modello di pagina denominato **Modello contenuto**.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-135">Create a page template that is named **Content template**.</span></span> 
1. <span data-ttu-id="bbcc1-136">Nello slot **Corpo**, aggiungi un modulo **Pagina predefinita**.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-136">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="bbcc1-137">Completare la modifica del modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-137">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="bbcc1-138">Utilizzare il modello di contenuto appena creato per creare una pagina denominata **Pagina contenuto**.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-138">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="bbcc1-139">Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-139">In the **Main** slot of the new page, add a container module.</span></span>
1. <span data-ttu-id="bbcc1-140">Nel riquadro delle proprietà del modulo contenitore, impostare la proprietà **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-140">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="bbcc1-141">Aggiungere un modulo blocco di testo al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-141">Add a text block module to the container module.</span></span> 
1. <span data-ttu-id="bbcc1-142">Nel riquadro delle proprietà del modulo blocco di testo, aggiungere testo al campo **RTF**.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-142">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="bbcc1-143">Completare la modifica della pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="bbcc1-143">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bbcc1-144">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="bbcc1-144">Additional resources</span></span>

[<span data-ttu-id="bbcc1-145">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="bbcc1-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bbcc1-146">Modulo banner promozionale</span><span class="sxs-lookup"><span data-stu-id="bbcc1-146">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="bbcc1-147">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="bbcc1-147">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="bbcc1-148">modulo blocco di contenuto</span><span class="sxs-lookup"><span data-stu-id="bbcc1-148">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="bbcc1-149">Modulo lettore video</span><span class="sxs-lookup"><span data-stu-id="bbcc1-149">Video player module</span></span>](add-video-player.md)

