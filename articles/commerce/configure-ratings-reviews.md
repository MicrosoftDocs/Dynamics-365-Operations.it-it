---
title: Configurare valutazioni e recensioni
description: In questo argomento viene descritto come configurare il sito di e-Commerce per visualizzare valutazioni e recensioni dei clienti in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/17/2020
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
ms.openlocfilehash: edd2082b5d2cafcb955f8e3c7762bcba523ac479
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413358"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="3ecce-103">Configurare valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="3ecce-103">Configure ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3ecce-104">In questo argomento viene descritto come configurare il sito di e-Commerce per visualizzare valutazioni e recensioni dei clienti in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ecce-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3ecce-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="3ecce-105">Overview</span></span>

<span data-ttu-id="3ecce-106">Le valutazioni e le recensioni nei siti Web di e-Commerce consentono ai clienti di informarsi sui prodotti prima di deciderne l'acquisto mediante l'opinione di altri clienti riguardo a quei prodotti.</span><span class="sxs-lookup"><span data-stu-id="3ecce-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision by showing them what other customers think about those products.</span></span> <span data-ttu-id="3ecce-107">Per i siti Web di e-Commerce, valutazioni e recensioni sono anche un meccanismo di raccolta dei riscontri dei clienti sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="3ecce-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="3ecce-108">Configurare un sito per visualizzare valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="3ecce-108">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="3ecce-109">I valori di configurazione per valutazioni e recensioni, ad esempio l'ID tenant, la lunghezza del testo della recensione e la lunghezza del titolo della recensione sono configurati a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="3ecce-109">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="3ecce-110">Per configurare un sito allo scopo di visualizzare valutazioni e recensioni, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="3ecce-110">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="3ecce-111">Andare a **Home \> Siti**.</span><span class="sxs-lookup"><span data-stu-id="3ecce-111">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="3ecce-112">Selezionare il nome del sito.</span><span class="sxs-lookup"><span data-stu-id="3ecce-112">Select the name of your site.</span></span> 
1. <span data-ttu-id="3ecce-113">Andare a **Impostazioni del sito \> Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="3ecce-113">Go to **Site settings \> Extensions**.</span></span> 
1. <span data-ttu-id="3ecce-114">Nel campo **Lunghezza massima testo recensione**, immettere il numero massimo di caratteri per il testo della recensione (ad esempio **1000**).</span><span class="sxs-lookup"><span data-stu-id="3ecce-114">In the **Review text max length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="3ecce-115">Nel campo **Lunghezza massima titolo recensione**, immettere il numero massimo di caratteri per i titoli delle recensioni (ad esempio **55**).</span><span class="sxs-lookup"><span data-stu-id="3ecce-115">In the **Review title max length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="3ecce-116">Selezionare **Salva e pubblica**.</span><span class="sxs-lookup"><span data-stu-id="3ecce-116">Select **Save and Publish**.</span></span> 

<span data-ttu-id="3ecce-117">L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ecce-117">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configurare un sito per visualizzare valutazioni e recensioni](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="3ecce-119">Collegare la valutazione di un prodotto alla sezione Recensioni di una pagina dettagli prodotto</span><span class="sxs-lookup"><span data-stu-id="3ecce-119">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="3ecce-120">Una valutazione di un prodotto viene visualizzata sotto il titolo del prodotto nella parte superiore della pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="3ecce-120">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="3ecce-121">La valutazione di un prodotto può essere configurata di modo che sia collegata alla sezione **Recensioni** della stessa pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="3ecce-121">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="3ecce-122">Per collegare la valutazione di una prodotto alla sezione **Recensioni** della pagina dettagli prodotto, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="3ecce-122">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="3ecce-123">Aprire il modello PDP.</span><span class="sxs-lookup"><span data-stu-id="3ecce-123">Open the PDP template.</span></span> 
1. <span data-ttu-id="3ecce-124">Andare a **Impostazioni modulo contenitore Casella acquisti**.</span><span class="sxs-lookup"><span data-stu-id="3ecce-124">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="3ecce-125">In **Casella acquisti** selezionare **Valutazioni prodotti**, quindi selezionare la casella di controllo **Collega clic a modulo Recensioni completo**.</span><span class="sxs-lookup"><span data-stu-id="3ecce-125">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="3ecce-126">L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ecce-126">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Collegare la valutazione di un prodotto alla sezione Recensioni di una pagina dettagli prodotto](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="3ecce-128">Configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche</span><span class="sxs-lookup"><span data-stu-id="3ecce-128">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="3ecce-129">Per configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="3ecce-129">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="3ecce-130">Andare a **Home \> Siti**.</span><span class="sxs-lookup"><span data-stu-id="3ecce-130">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="3ecce-131">Selezionare il nome del sito.</span><span class="sxs-lookup"><span data-stu-id="3ecce-131">Select the name of your site.</span></span> 
1. <span data-ttu-id="3ecce-132">Andare a **Impostazioni del sito \> Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="3ecce-132">Go to **Site settings \> Extensions**.</span></span>
1. <span data-ttu-id="3ecce-133">Nella scheda **Route**, in **Informativa sulla privacy e politica per valutazioni e recensioni**, selezionare **Aggiungi un collegamento**.</span><span class="sxs-lookup"><span data-stu-id="3ecce-133">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="3ecce-134">Se un collegamento è già stato specificato e si desidera sostituirlo, selezionare il collegamento.</span><span class="sxs-lookup"><span data-stu-id="3ecce-134">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="3ecce-135">Nella finestra di dialogo **Aggiungi un collegamento**, selezionare il collegamento per la pagina dell'informativa sulla privacy e delle politiche, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ecce-135">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="3ecce-136">Selezionare **Salva e pubblica**.</span><span class="sxs-lookup"><span data-stu-id="3ecce-136">Select **Save and Publish**.</span></span> 

<span data-ttu-id="3ecce-137">L'illustrazione seguente mostra questa configurazione in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ecce-137">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configurare il collegamento per la pagina dell'informativa sulla privacy e delle politiche](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a><span data-ttu-id="3ecce-139">Configurare i moduli di valutazione e recensione nelle pagine dei dettagli del prodotto</span><span class="sxs-lookup"><span data-stu-id="3ecce-139">Configure ratings and reviews modules on product details pages</span></span>

<span data-ttu-id="3ecce-140">Per informazioni sulla configurazione dei moduli di valutazione e recensione nelle pagine dei dettagli del prodotto, vedere [Moduli Valutazioni e recensioni](ratings-reviews-modules.md).</span><span class="sxs-lookup"><span data-stu-id="3ecce-140">For information on configuring ratings and reviews modules on product details pages, see [Ratings and reviews modules](ratings-reviews-modules.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3ecce-141">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3ecce-141">Additional resources</span></span>

[<span data-ttu-id="3ecce-142">Panoramica valutazioni e revisioni</span><span class="sxs-lookup"><span data-stu-id="3ecce-142">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="3ecce-143">Consentire utilizzo di valutazioni e sulle revisioni</span><span class="sxs-lookup"><span data-stu-id="3ecce-143">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="3ecce-144">Gestire valutazioni e revisioni</span><span class="sxs-lookup"><span data-stu-id="3ecce-144">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="3ecce-145">Configurare i moduli di valutazione e recensione nelle pagine dei dettagli del prodotto</span><span class="sxs-lookup"><span data-stu-id="3ecce-145">Configure ratings and reviews modules on product details pages</span></span>](ratings-reviews-modules.md)

[<span data-ttu-id="3ecce-146">Sincronizzare valutazioni sul prodotto in Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="3ecce-146">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
