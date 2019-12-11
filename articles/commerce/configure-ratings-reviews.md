---
title: Configurare valutazioni e recensioni
description: In questo argomento viene descritto come configurare il sito di e-Commerce per visualizzare valutazioni e recensioni dei clienti in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0612b32e7751b32ad851f627a53bce2ac491870f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770483"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="409c7-103">Configurare valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="409c7-103">Configure ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="409c7-104">In questo argomento viene descritto come configurare il sito di e-Commerce per visualizzare valutazioni e recensioni dei clienti in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="409c7-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="409c7-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="409c7-105">Overview</span></span>

<span data-ttu-id="409c7-106">Le valutazioni e le recensioni nei siti Web di e-Commerce consentono ai clienti di informarsi sui prodotti prima di deciderne l'acquisto mediante l'opinione di altri clienti riguardo a quei prodotti.</span><span class="sxs-lookup"><span data-stu-id="409c7-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, by showing them what other customers think about those products.</span></span> <span data-ttu-id="409c7-107">Per i siti Web di e-Commerce, valutazioni e recensioni sono anche un meccanismo di raccolta dei riscontri dei clienti sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="409c7-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="409c7-108">Le valutazioni sono visualizzate nelle pagine elenco di prodotti, le pagine elenco di categorie, le pagine dei risultati delle ricerche e altre pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="409c7-108">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> <span data-ttu-id="409c7-109">Gli istogrammi delle valutazioni e le recensioni dei prodotti sono visualizzati nelle pagine dettagli prodotto (PDP).</span><span class="sxs-lookup"><span data-stu-id="409c7-109">Ratings histograms and product reviews are shown on product details pages (PDPs).</span></span> <span data-ttu-id="409c7-110">Un pulsante **Scrivi una recensione** consente ai clienti di inviare valutazioni e recensioni per un prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-110">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="409c7-111">Modulo Valutazioni e recensioni nelle pagine dettagli prodotto</span><span class="sxs-lookup"><span data-stu-id="409c7-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="409c7-112">Tre moduli visualizzano il riepilogo di valutazioni e recensioni nelle pagine dettagli prodotto:</span><span class="sxs-lookup"><span data-stu-id="409c7-112">Three modules show the ratings and reviews summary on PDPs:</span></span>

- <span data-ttu-id="409c7-113">Modulo Scrivere una recensione</span><span class="sxs-lookup"><span data-stu-id="409c7-113">Write review module</span></span>
- <span data-ttu-id="409c7-114">Modulo Elenco recensioni prodotti</span><span class="sxs-lookup"><span data-stu-id="409c7-114">Product reviews list module</span></span>
- <span data-ttu-id="409c7-115">Modulo Istogramma valutazioni</span><span class="sxs-lookup"><span data-stu-id="409c7-115">Ratings histogram module</span></span>
 
<span data-ttu-id="409c7-116">Nella figura seguente sono illustrati i moduli Valutazioni e recensioni in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Moduli Valutazioni e recensioni in una pagina dettagli prodotto](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="409c7-118">Per informazioni su come ottimizzare i modelli e i layout di pagine dettagli prodotto in modo da condividere le configurazioni per moduli Valutazioni e recensioni tra molteplici pagine dettagli prodotto nel sito di e-Commerce, vedere [Panoramica modelli e layout](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="409c7-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="409c7-119">Nella figura seguente viene illustrato come la finestra di dialogo **Aggiungi modulo** presenta i moduli Valutazioni e recensioni in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="409c7-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>

![Finestra di dialogo Aggiungi modulo](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a><span data-ttu-id="409c7-121">Modulo Scrivere una recensione</span><span class="sxs-lookup"><span data-stu-id="409c7-121">Write review module</span></span>

<span data-ttu-id="409c7-122">Il modulo Scrivere una recensione include un pulsante **Scrivi una recensione** che consente agli utenti di accedere, assegnare una valutazione e scrivere la recensione di un prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="409c7-123">Questo modulo consente inoltre agli utenti di modificare una valutazione o una recensione creata precedentemente.</span><span class="sxs-lookup"><span data-stu-id="409c7-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="409c7-124">Questo modulo viene in genere visualizzato sopra i moduli Istogramma valutazioni ed Elenco recensioni prodotti in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>

<span data-ttu-id="409c7-125">Nella seguente figura è illustrata la finestra di dialogo **Scrivi una recensione** che viene visualizzata quando un cliente seleziona **Scrivi una recensione**.</span><span class="sxs-lookup"><span data-stu-id="409c7-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="409c7-126">Il cliente può utilizzare questa finestra di dialogo per inviare una valutazione e una recensione.</span><span class="sxs-lookup"><span data-stu-id="409c7-126">The customer can use this dialog box to submit a rating and a review.</span></span>

![Finestra di dialogo Scrivi una recensione](media/rnr-eCommerce-write-review-module.png)

<span data-ttu-id="409c7-128">Nella tabella seguente viene illustrata la proprietà del modulo Scrivere una recensione che deve essere configurata nello strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="409c7-128">The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>

| <span data-ttu-id="409c7-129">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="409c7-129">Property name</span></span> | <span data-ttu-id="409c7-130">Valore</span><span class="sxs-lookup"><span data-stu-id="409c7-130">Value</span></span>        | <span data-ttu-id="409c7-131">Descrizione della proprietà</span><span class="sxs-lookup"><span data-stu-id="409c7-131">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="409c7-132">Nome</span><span class="sxs-lookup"><span data-stu-id="409c7-132">Name</span></span>          | <span data-ttu-id="409c7-133">Scrivi recensione</span><span class="sxs-lookup"><span data-stu-id="409c7-133">Write review</span></span> | <span data-ttu-id="409c7-134">Il nome del modulo Scrivere una recensione.</span><span class="sxs-lookup"><span data-stu-id="409c7-134">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="409c7-135">Modulo Istogramma valutazioni</span><span class="sxs-lookup"><span data-stu-id="409c7-135">Ratings histogram module</span></span>

<span data-ttu-id="409c7-136">Il modulo Istogramma valutazioni visualizza un istogramma delle valutazioni.</span><span class="sxs-lookup"><span data-stu-id="409c7-136">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="409c7-137">Questo modulo viene visualizzato in genere tra i moduli Scrivere una recensione e il modulo Elenco recensioni prodotto in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-137">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>

<span data-ttu-id="409c7-138">Il modulo Istogramma valutazioni non richiede alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="409c7-138">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="409c7-139">È sufficiente aggiungere il modulo nel modello di pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-139">You just have to add the module in the PDP template.</span></span> 

<span data-ttu-id="409c7-140">Nelle figure seguenti è illustrato un modello di pagina dettagli prodotto in Dynamics 365 Commerce quando i moduli Valutazioni e recensioni sono configurati per la visualizzazione nelle pagine dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-140">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>

![Modello di pagina dettagli prodotto quando valutazioni e recensioni sono configurate per la visualizzazione nelle pagine dettagli prodotto](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a><span data-ttu-id="409c7-142">Modulo Elenco recensioni prodotti</span><span class="sxs-lookup"><span data-stu-id="409c7-142">Product reviews list module</span></span>

<span data-ttu-id="409c7-143">Il modulo Elenco recensioni prodotti visualizza un elenco di recensioni di prodotti con opzioni di ordinamento, filtro e paginazione.</span><span class="sxs-lookup"><span data-stu-id="409c7-143">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="409c7-144">Questo modulo è in genere visualizzato dopo il modulo Istogramma valutazioni in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-144">This module typically appears after the ratings histogram module on a PDP.</span></span>

<span data-ttu-id="409c7-145">Nella tabella seguente sono illustrate le proprietà del modulo Elenco recensioni prodotti che devono essere configurate nello strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="409c7-145">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="409c7-146">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="409c7-146">Property name</span></span>              | <span data-ttu-id="409c7-147">Valore</span><span class="sxs-lookup"><span data-stu-id="409c7-147">Value</span></span> | <span data-ttu-id="409c7-148">Descrizione della proprietà</span><span class="sxs-lookup"><span data-stu-id="409c7-148">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="409c7-149">Recensioni visualizzate in ogni pagina</span><span class="sxs-lookup"><span data-stu-id="409c7-149">Reviews shown on each page</span></span> | <span data-ttu-id="409c7-150">10</span><span class="sxs-lookup"><span data-stu-id="409c7-150">10</span></span>    | <span data-ttu-id="409c7-151">Il numero di recensioni che devono essere visualizzate contemporaneamente in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-151">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="409c7-152">Sono inclusi i pulsanti **Avanti** e**Indietro** di modo che gli utenti possano passare da una pagina all'altra delle recensioni.</span><span class="sxs-lookup"><span data-stu-id="409c7-152">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="409c7-153">Istogramma delle valutazioni - Visualizzazione di riepilogo</span><span class="sxs-lookup"><span data-stu-id="409c7-153">Ratings histogram – Summary view</span></span>

<span data-ttu-id="409c7-154">Il modulo Elenco recensioni prodotti include uno slot in cui è possibile aggiungere un modulo Istogramma valutazioni.</span><span class="sxs-lookup"><span data-stu-id="409c7-154">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="409c7-155">Nella figura seguente viene illustrato come è possibile aggiungere un modulo Istogramma valutazioni nel modulo Elenco recensioni prodotti in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="409c7-155">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Aggiungere un modulo Istogramma valutazioni in un modulo Elenco recensioni prodotti](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="409c7-157">Configurare un sito per visualizzare valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="409c7-157">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="409c7-158">I valori di configurazione per valutazioni e recensioni, ad esempio l'ID tenant, la lunghezza del testo della recensione e la lunghezza del titolo della recensione sono configurati a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="409c7-158">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="409c7-159">Per configurare un sito allo scopo di visualizzare valutazioni e recensioni, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="409c7-159">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="409c7-160">Andare a **Home \> Siti**.</span><span class="sxs-lookup"><span data-stu-id="409c7-160">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="409c7-161">Selezionare il nome del sito.</span><span class="sxs-lookup"><span data-stu-id="409c7-161">Select the name of your site.</span></span> 
1. <span data-ttu-id="409c7-162">Andare a **Gestione sito \> Estendibilità**.</span><span class="sxs-lookup"><span data-stu-id="409c7-162">Go to **Site management \> Extensibility**.</span></span> 
1. <span data-ttu-id="409c7-163">Nel campo **Lunghezza massima testo recensione**, immettere il numero massimo di caratteri per il testo della recensione (ad esempio **1000**).</span><span class="sxs-lookup"><span data-stu-id="409c7-163">In the **Review Text Max Length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="409c7-164">Nel campo **Lunghezza massima titolo recensione**, immettere il numero massimo di caratteri per i titoli delle recensioni (ad esempio **55**).</span><span class="sxs-lookup"><span data-stu-id="409c7-164">In the **Review Title Max Length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="409c7-165">Selezionare **Salva e pubblica**.</span><span class="sxs-lookup"><span data-stu-id="409c7-165">Select **Save and Publish**.</span></span> 

<span data-ttu-id="409c7-166">L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="409c7-166">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configurare un sito per visualizzare valutazioni e recensioni](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="409c7-168">Collegare la valutazione di un prodotto alla sezione Recensioni di una pagina dettagli prodotto</span><span class="sxs-lookup"><span data-stu-id="409c7-168">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="409c7-169">Una valutazione di un prodotto viene visualizzata sotto il titolo del prodotto nella parte superiore della pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-169">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="409c7-170">La valutazione di un prodotto può essere configurata di modo che sia collegata alla sezione **Recensioni** della stessa pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="409c7-170">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="409c7-171">Per collegare la valutazione di una prodotto alla sezione **Recensioni** della pagina dettagli prodotto, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="409c7-171">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="409c7-172">Aprire il modello PDP.</span><span class="sxs-lookup"><span data-stu-id="409c7-172">Open the PDP template.</span></span> 
1. <span data-ttu-id="409c7-173">Andare a **Impostazioni modulo contenitore Casella acquisti**.</span><span class="sxs-lookup"><span data-stu-id="409c7-173">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="409c7-174">In **Casella acquisti**selezionare **Valutazioni prodotti**, quindi selezionare la casella di controllo **Collega clic a modulo Recensioni completo**.</span><span class="sxs-lookup"><span data-stu-id="409c7-174">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="409c7-175">L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="409c7-175">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Collegare la valutazione di un prodotto alla sezione Recensioni di una pagina dettagli prodotto](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="409c7-177">Configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche</span><span class="sxs-lookup"><span data-stu-id="409c7-177">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="409c7-178">Per configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="409c7-178">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="409c7-179">Andare a **Home \> Siti**.</span><span class="sxs-lookup"><span data-stu-id="409c7-179">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="409c7-180">Selezionare il nome del sito.</span><span class="sxs-lookup"><span data-stu-id="409c7-180">Select the name of your site.</span></span> 
1. <span data-ttu-id="409c7-181">Andare a **Gestione sito \> Estendibilità**.</span><span class="sxs-lookup"><span data-stu-id="409c7-181">Go to **Site management \> Extensibility**</span></span>
1. <span data-ttu-id="409c7-182">Nella scheda **Route**, in **Informativa sulla privacy e politica per valutazioni e recensioni**, selezionare **Aggiungi un collegamento**.</span><span class="sxs-lookup"><span data-stu-id="409c7-182">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="409c7-183">Se un collegamento è già stato specificato e si desidera sostituirlo, selezionare il collegamento.</span><span class="sxs-lookup"><span data-stu-id="409c7-183">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="409c7-184">Nella finestra di dialogo **Aggiungi un collegamento**, selezionare il collegamento per la pagina dell'informativa sulla privacy e delle politiche, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="409c7-184">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="409c7-185">Selezionare **Salva e pubblica**.</span><span class="sxs-lookup"><span data-stu-id="409c7-185">Select **Save and Publish**.</span></span> 

<span data-ttu-id="409c7-186">L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="409c7-186">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a><span data-ttu-id="409c7-188">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="409c7-188">Additional resources</span></span>

[<span data-ttu-id="409c7-189">Panoramica valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="409c7-189">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="409c7-190">Consentire l'utilizzo di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="409c7-190">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="409c7-191">Gestire valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="409c7-191">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="409c7-192">Sincronizzare valutazioni sul prodotto in Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="409c7-192">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
