---
title: Modulo Avviso
description: In questo argomento vengono descritti i moduli Avviso e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785354"
---
# <a name="alert-module"></a><span data-ttu-id="f907f-103">Modulo Avviso</span><span class="sxs-lookup"><span data-stu-id="f907f-103">Alert module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="f907f-104">In questo argomento vengono descritti i moduli Avviso e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f907f-104">This topic covers alert modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f907f-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="f907f-105">Overview</span></span>

<span data-ttu-id="f907f-106">Un modulo Avviso è utilizzato per visualizzare messaggi informativi in una pagina.</span><span class="sxs-lookup"><span data-stu-id="f907f-106">An alert module is used to show inline informational messages on a page.</span></span> <span data-ttu-id="f907f-107">I moduli Avviso supportano un messaggio di testo e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="f907f-107">Alert modules support a text message and a link.</span></span> <span data-ttu-id="f907f-108">Possono essere utilizzati per visualizzare promozioni in tutto le pagine di un sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="f907f-108">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="f907f-109">I moduli Avviso sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="f907f-109">Alert modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="examples-of-alert-modules-in-e-commerce"></a><span data-ttu-id="f907f-110">Esempi di moduli Avviso in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="f907f-110">Examples of alert modules in e-Commerce</span></span>

<span data-ttu-id="f907f-111">I moduli Avviso possono essere utilizzati nell'intestazione del sito per indicare promozioni o messaggi a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="f907f-111">Alert modules can be used in the site header to indicate site-wide promotions or messages.</span></span> <span data-ttu-id="f907f-112">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="f907f-112">Here are some examples:</span></span>

<span data-ttu-id="f907f-113">"La vendita annuale termina tra 10 giorni"</span><span class="sxs-lookup"><span data-stu-id="f907f-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="f907f-114">"Grandi risparmi con la vendita di articoli scolastici.</span><span class="sxs-lookup"><span data-stu-id="f907f-114">"Save big with back to school sale.</span></span> <span data-ttu-id="f907f-115">Acquista ora".</span><span class="sxs-lookup"><span data-stu-id="f907f-115">Shop Now."</span></span>

## <a name="alert-module-properties"></a><span data-ttu-id="f907f-116">Proprietà del modulo Avviso</span><span class="sxs-lookup"><span data-stu-id="f907f-116">Alert module properties</span></span>

| <span data-ttu-id="f907f-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="f907f-117">Property name</span></span>  | <span data-ttu-id="f907f-118">Valore</span><span class="sxs-lookup"><span data-stu-id="f907f-118">Value</span></span>                              | <span data-ttu-id="f907f-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f907f-119">Description</span></span> |
|----------------|------------------------------------|-------------|
| <span data-ttu-id="f907f-120">Testo</span><span class="sxs-lookup"><span data-stu-id="f907f-120">Text</span></span>           | <span data-ttu-id="f907f-121">Testo</span><span class="sxs-lookup"><span data-stu-id="f907f-121">Text</span></span>                               | <span data-ttu-id="f907f-122">Il messaggio di testo visualizzato nel modulo Avviso.</span><span class="sxs-lookup"><span data-stu-id="f907f-122">The text message that appears in the alert module.</span></span> |
| <span data-ttu-id="f907f-123">Allineamento testo</span><span class="sxs-lookup"><span data-stu-id="f907f-123">Text alignment</span></span> | <span data-ttu-id="f907f-124">**A destra**, **A sinistra** o **Al centro**</span><span class="sxs-lookup"><span data-stu-id="f907f-124">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="f907f-125">Un valore che definisce il modo in cui il testo è allineato nel modulo Avviso.</span><span class="sxs-lookup"><span data-stu-id="f907f-125">A value that defines how text is aligned in the alert module.</span></span> |
| <span data-ttu-id="f907f-126">Chiudi avviso</span><span class="sxs-lookup"><span data-stu-id="f907f-126">Dismiss alert</span></span>  | <span data-ttu-id="f907f-127">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="f907f-127">**True** or **False**</span></span>              | <span data-ttu-id="f907f-128">Se il valore è impostato su **True**, il cliente può chiudere l'avviso.</span><span class="sxs-lookup"><span data-stu-id="f907f-128">If the value is set to **True**, the customer can dismiss the alert.</span></span> |
| <span data-ttu-id="f907f-129">Collega</span><span class="sxs-lookup"><span data-stu-id="f907f-129">Link</span></span>           | <span data-ttu-id="f907f-130">URL</span><span class="sxs-lookup"><span data-stu-id="f907f-130">URL</span></span>                                | <span data-ttu-id="f907f-131">L'URL di un collegamento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f907f-131">The URL for an optional link.</span></span> |

## <a name="add-an-alert-module-to-a-page"></a><span data-ttu-id="f907f-132">Aggiungere un modulo Avviso a una pagina</span><span class="sxs-lookup"><span data-stu-id="f907f-132">Add an alert module to a page</span></span> 

<span data-ttu-id="f907f-133">Per aggiungere un modulo Avviso a una pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="f907f-133">To add an alert module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="f907f-134">Creare un modello di pagina denominato **Modello avviso**.</span><span class="sxs-lookup"><span data-stu-id="f907f-134">Create a page template that is named **alert template**.</span></span>
1. <span data-ttu-id="f907f-135">Nello slot **Principale** della pagina predefinita, aggiungere un modulo Avviso.</span><span class="sxs-lookup"><span data-stu-id="f907f-135">In the **Main** slot of the default page, add an alert module.</span></span>
1. <span data-ttu-id="f907f-136">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="f907f-136">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="f907f-137">Utilizzare il modello di avviso appena creato per creare una pagina denominata **Pagina avviso**.</span><span class="sxs-lookup"><span data-stu-id="f907f-137">Use the alert template that you just created to create a page that is named **alert page**.</span></span> 
1. <span data-ttu-id="f907f-138">Nello slot **Principale** della nuova pagina, aggiungere un modulo Avviso.</span><span class="sxs-lookup"><span data-stu-id="f907f-138">In the **Main** slot of the new page, add an alert module.</span></span>
1. <span data-ttu-id="f907f-139">Nelle impostazioni del modulo Avviso, immettere il testo dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="f907f-139">In the settings for the alert module, enter the alert text.</span></span> <span data-ttu-id="f907f-140">È possibile modificare le altre proprietà se si desidera personalizzare ulteriormente il modulo Avviso.</span><span class="sxs-lookup"><span data-stu-id="f907f-140">You can edit the other properties if you want to customize the alert module further.</span></span>
1. <span data-ttu-id="f907f-141">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="f907f-141">Save and preview the page.</span></span> <span data-ttu-id="f907f-142">Nella parte superiore della pagina, dovrebbe essere visualizzato un avviso con il testo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="f907f-142">At the top of the page, you should see an alert that has the text that you added.</span></span>
1. <span data-ttu-id="f907f-143">Archiviare la pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="f907f-143">Check in the page, and publish it.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="f907f-144">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f907f-144">Additional resources</span></span>

[<span data-ttu-id="f907f-145">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="f907f-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f907f-146">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="f907f-146">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="f907f-147">Modulo Blocco ricco di contenuti</span><span class="sxs-lookup"><span data-stu-id="f907f-147">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="f907f-148">Modulo Posizionamento contenuti</span><span class="sxs-lookup"><span data-stu-id="f907f-148">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="f907f-149">Modulo Funzionalità</span><span class="sxs-lookup"><span data-stu-id="f907f-149">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="f907f-150">Modulo Hero</span><span class="sxs-lookup"><span data-stu-id="f907f-150">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="f907f-151">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="f907f-151">Video player module</span></span>](add-video-player.md)
