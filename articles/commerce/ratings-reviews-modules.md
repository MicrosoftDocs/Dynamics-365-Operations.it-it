---
title: Moduli Valutazioni e recensioni
description: Questo argomento tratta i moduli di valutazione e recensione utilizzati nelle pagine dei dettagli del prodotto in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
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
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: b17e986c2e30134c334cd547a85a1dd682172a0e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979805"
---
# <a name="ratings-and-reviews-modules"></a><span data-ttu-id="e918a-103">Moduli Valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="e918a-103">Ratings and reviews modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e918a-104">Questo argomento tratta i moduli di valutazione e recensione utilizzati nelle pagine dei dettagli del prodotto in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e918a-104">This topic covers ratings and reviews modules used on product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e918a-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e918a-105">Overview</span></span>

<span data-ttu-id="e918a-106">Le valutazioni e le recensioni nei siti Web di e-Commerce consentono ai clienti di informarsi sui prodotti prima di deciderne l'acquisto e costituiscono anche un meccanismo di raccolta dell'opinione dei clienti riguardo ai prodotti.</span><span class="sxs-lookup"><span data-stu-id="e918a-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, and are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="e918a-107">Le valutazioni sono visualizzate nelle pagine elenco di prodotti, le pagine elenco di categorie, le pagine dei risultati delle ricerche e altre pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="e918a-107">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> 

<span data-ttu-id="e918a-108">Gli istogrammi delle valutazioni e le recensioni dei prodotti sono visualizzati nelle pagine dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="e918a-108">Ratings histograms and product reviews are shown on PDPs.</span></span> <span data-ttu-id="e918a-109">Un pulsante **Scrivi una recensione** consente ai clienti di inviare valutazioni e recensioni per un prodotto.</span><span class="sxs-lookup"><span data-stu-id="e918a-109">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span> <span data-ttu-id="e918a-110">Le funzionalità di queste pagine dettagli prodotto sono controllate dai moduli di valutazione e recensione.</span><span class="sxs-lookup"><span data-stu-id="e918a-110">These PDP features are controlled by ratings and review modules.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="e918a-111">Modulo Valutazioni e recensioni nelle pagine dettagli prodotto</span><span class="sxs-lookup"><span data-stu-id="e918a-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="e918a-112">Tre moduli visualizzano il riepilogo di valutazioni e recensioni nelle pagine dettagli prodotto:</span><span class="sxs-lookup"><span data-stu-id="e918a-112">Three modules show the ratings and reviews summary on PDPs:</span></span>
- <span data-ttu-id="e918a-113">Modulo Scrivere una recensione</span><span class="sxs-lookup"><span data-stu-id="e918a-113">Write review module</span></span>
- <span data-ttu-id="e918a-114">Modulo Elenco recensioni prodotti</span><span class="sxs-lookup"><span data-stu-id="e918a-114">Product reviews list module</span></span>
- <span data-ttu-id="e918a-115">Modulo Istogramma valutazioni</span><span class="sxs-lookup"><span data-stu-id="e918a-115">Ratings histogram module</span></span>
 
<span data-ttu-id="e918a-116">Nella figura seguente sono illustrati i moduli Valutazioni e recensioni in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="e918a-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Moduli Valutazioni e recensioni in una pagina dettagli prodotto](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="e918a-118">Per informazioni su come ottimizzare i modelli e i layout di pagine dettagli prodotto in modo da condividere le configurazioni per moduli Valutazioni e recensioni tra molteplici pagine dettagli prodotto nel sito di e-Commerce, vedere [Panoramica modelli e layout](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e918a-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="e918a-119">Nella figura seguente viene illustrato come la finestra di dialogo **Aggiungi modulo** presenta i moduli Valutazioni e recensioni in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e918a-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>
<span data-ttu-id="e918a-120">![Finestra di dialogo Aggiungi modulo](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span><span class="sxs-lookup"><span data-stu-id="e918a-120">![Add module dialog box](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span></span>

### <a name="write-review-module"></a><span data-ttu-id="e918a-121">Modulo Scrivere una recensione</span><span class="sxs-lookup"><span data-stu-id="e918a-121">Write review module</span></span>

<span data-ttu-id="e918a-122">Il modulo Scrivere una recensione include un pulsante **Scrivi una recensione** che consente agli utenti di accedere, assegnare una valutazione e scrivere la recensione di un prodotto.</span><span class="sxs-lookup"><span data-stu-id="e918a-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="e918a-123">Questo modulo consente inoltre agli utenti di modificare una valutazione o una recensione creata precedentemente.</span><span class="sxs-lookup"><span data-stu-id="e918a-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="e918a-124">Questo modulo viene in genere visualizzato sopra i moduli Istogramma valutazioni ed Elenco recensioni prodotti in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="e918a-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>
<span data-ttu-id="e918a-125">Nella seguente figura è illustrata la finestra di dialogo **Scrivi una recensione** che viene visualizzata quando un cliente seleziona **Scrivi una recensione**.</span><span class="sxs-lookup"><span data-stu-id="e918a-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="e918a-126">Il cliente può utilizzare questa finestra di dialogo per inviare una valutazione e una recensione.</span><span class="sxs-lookup"><span data-stu-id="e918a-126">The customer can use this dialog box to submit a rating and a review.</span></span>
<span data-ttu-id="e918a-127">![Finestra di dialogo Scrivi una recensione](media/rnr-eCommerce-write-review-module.png) Nella tabella seguente viene illustrata la proprietà del modulo Scrivere una recensione che deve essere configurata nello strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="e918a-127">![Write a review dialog box](media/rnr-eCommerce-write-review-module.png) The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>
| <span data-ttu-id="e918a-128">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="e918a-128">Property name</span></span> | <span data-ttu-id="e918a-129">Valore</span><span class="sxs-lookup"><span data-stu-id="e918a-129">Value</span></span>        | <span data-ttu-id="e918a-130">Descrizione della proprietà</span><span class="sxs-lookup"><span data-stu-id="e918a-130">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="e918a-131">Nome</span><span class="sxs-lookup"><span data-stu-id="e918a-131">Name</span></span>          | <span data-ttu-id="e918a-132">Scrivi recensione</span><span class="sxs-lookup"><span data-stu-id="e918a-132">Write review</span></span> | <span data-ttu-id="e918a-133">Il nome del modulo Scrivere una recensione.</span><span class="sxs-lookup"><span data-stu-id="e918a-133">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="e918a-134">Modulo Istogramma valutazioni</span><span class="sxs-lookup"><span data-stu-id="e918a-134">Ratings histogram module</span></span>

<span data-ttu-id="e918a-135">Il modulo Istogramma valutazioni visualizza un istogramma delle valutazioni.</span><span class="sxs-lookup"><span data-stu-id="e918a-135">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="e918a-136">Questo modulo viene visualizzato in genere tra i moduli Scrivere una recensione e il modulo Elenco recensioni prodotto in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="e918a-136">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>
<span data-ttu-id="e918a-137">Il modulo Istogramma valutazioni non richiede alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="e918a-137">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="e918a-138">È sufficiente aggiungere il modulo nel modello di pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="e918a-138">You just have to add the module in the PDP template.</span></span> <span data-ttu-id="e918a-139">Nelle figure seguenti è illustrato un modello di pagina dettagli prodotto in Dynamics 365 Commerce quando i moduli Valutazioni e recensioni sono configurati per la visualizzazione nelle pagine dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="e918a-139">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>
<span data-ttu-id="e918a-140">![Modello di pagina dettagli prodotto quando valutazioni e recensioni sono configurate per la visualizzazione nelle pagine dettagli prodotto](media/rnr-eCommerce-pdp-reviews-modules.png)</span><span class="sxs-lookup"><span data-stu-id="e918a-140">![PDP template when ratings and reviews are configured for display on PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span></span>

### <a name="product-reviews-list-module"></a><span data-ttu-id="e918a-141">Modulo Elenco recensioni prodotti</span><span class="sxs-lookup"><span data-stu-id="e918a-141">Product reviews list module</span></span>

<span data-ttu-id="e918a-142">Il modulo Elenco recensioni prodotti visualizza un elenco di recensioni di prodotti con opzioni di ordinamento, filtro e paginazione.</span><span class="sxs-lookup"><span data-stu-id="e918a-142">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="e918a-143">Questo modulo è in genere visualizzato dopo il modulo Istogramma valutazioni in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="e918a-143">This module typically appears after the ratings histogram module on a PDP.</span></span>
<span data-ttu-id="e918a-144">Nella tabella seguente sono illustrate le proprietà del modulo Elenco recensioni prodotti che devono essere configurate nello strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="e918a-144">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="e918a-145">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="e918a-145">Property name</span></span>              | <span data-ttu-id="e918a-146">Valore</span><span class="sxs-lookup"><span data-stu-id="e918a-146">Value</span></span> | <span data-ttu-id="e918a-147">Descrizione della proprietà</span><span class="sxs-lookup"><span data-stu-id="e918a-147">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="e918a-148">Recensioni visualizzate in ogni pagina</span><span class="sxs-lookup"><span data-stu-id="e918a-148">Reviews shown on each page</span></span> | <span data-ttu-id="e918a-149">10</span><span class="sxs-lookup"><span data-stu-id="e918a-149">10</span></span>    | <span data-ttu-id="e918a-150">Il numero di recensioni che devono essere visualizzate contemporaneamente in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="e918a-150">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="e918a-151">Sono inclusi i pulsanti **Avanti** e **Indietro** di modo che gli utenti possano passare da una pagina all'altra delle recensioni.</span><span class="sxs-lookup"><span data-stu-id="e918a-151">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="e918a-152">Istogramma delle valutazioni - Visualizzazione di riepilogo</span><span class="sxs-lookup"><span data-stu-id="e918a-152">Ratings histogram – Summary view</span></span>

<span data-ttu-id="e918a-153">Il modulo Elenco recensioni prodotti include uno slot in cui è possibile aggiungere un modulo Istogramma valutazioni.</span><span class="sxs-lookup"><span data-stu-id="e918a-153">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="e918a-154">Nella figura seguente viene illustrato come è possibile aggiungere un modulo Istogramma valutazioni nel modulo Elenco recensioni prodotti in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e918a-154">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Aggiungere un modulo Istogramma valutazioni in un modulo Elenco recensioni prodotti](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a><span data-ttu-id="e918a-156">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e918a-156">Additional resources</span></span>

[<span data-ttu-id="e918a-157">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="e918a-157">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e918a-158">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="e918a-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="e918a-159">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="e918a-159">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="e918a-160">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="e918a-160">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="e918a-161">Modulo conferma ordine</span><span class="sxs-lookup"><span data-stu-id="e918a-161">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="e918a-162">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="e918a-162">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="e918a-163">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="e918a-163">Footer module</span></span>](author-footer-module.md)
