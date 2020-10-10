---
title: Abilitare gli elementi consigliati "acquista prodotti simili"
description: Questo argomento descrive come abilitare i consigli sui prodotti "acquista prodotti simili" in Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: da957850072e233a41a042d5857f81ddbf178f7a
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818376"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="9850f-103">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="9850f-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9850f-104">Questo argomento descrive come abilitare i consigli sui prodotti "acquista prodotti simili" in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9850f-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9850f-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9850f-105">Overview</span></span>

<span data-ttu-id="9850f-106">La funzionalità relativa ai consigli "acquista prodotti simili" in Dynamics 365 Commerce utilizza la potenza dell'intelligenza artificiale e dell'apprendimento automatico (IA-ML) per fornire ai clienti consigli per prodotti visivamente simili.</span><span class="sxs-lookup"><span data-stu-id="9850f-106">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="9850f-107">Rendendo disponibili i consigli "acquista prodotti simili" per tutti i canali di vendita al dettaglio in Commerce, i rivenditori possono aumentare la soddisfazione dei clienti aiutandoli a trovare facilmente ciò che desiderano.</span><span class="sxs-lookup"><span data-stu-id="9850f-107">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="9850f-108">La funzionalità per i consigli "acquista prodotti simili" utilizza immagini di prodotti di varianti del prodotto iniziale per trovare e consigliare prodotti visivamente simili nel catalogo prodotti di un rivenditore.</span><span class="sxs-lookup"><span data-stu-id="9850f-108">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="9850f-109">I consigli "acquista prodotti simili" sono disponibili sia nelle esperienze POS che e-commerce.</span><span class="sxs-lookup"><span data-stu-id="9850f-109">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="9850f-110">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="9850f-110">Example scenarios</span></span>

- <span data-ttu-id="9850f-111">Un cliente visualizza un maglione a righe nere e riceve un consiglio per un maglione rosso simile.</span><span class="sxs-lookup"><span data-stu-id="9850f-111">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="9850f-112">Il cliente seleziona il prodotto consigliato invece del prodotto visualizzato originariamente e quindi riceve consigli per prodotti simili in rosso.</span><span class="sxs-lookup"><span data-stu-id="9850f-112">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="9850f-113">Un cliente utilizza i consigli "acquista prodotti simili" per scoprire orecchini corrispondenti a un anello che il cliente è interessato ad acquistare.</span><span class="sxs-lookup"><span data-stu-id="9850f-113">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="9850f-114">Abilitare i consigli "acquista look simili" in Commerce headquarters</span><span class="sxs-lookup"><span data-stu-id="9850f-114">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="9850f-115">I consigli relativi ai prodotti sono supportati solo per gli utenti Commerce che hanno eseguito la migrazione del loro archivio ad Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="9850f-115">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="9850f-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9850f-116">Prerequisites</span></span>

<span data-ttu-id="9850f-117">Prima che i rivenditori possano iniziare a mostrare ai clienti consigli di "acquista prodotti simili", esistono due passaggi prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="9850f-117">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="9850f-118">[Abilitare suggerimenti sul prodotto](enable-product-recommendations.md) in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="9850f-118">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="9850f-119">Verificare che il server multimediale supporti le chiamate HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9850f-119">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="9850f-120">Affinché il motore dei consigli possa accedere alle immagini dei prodotti, i rivenditori devono generare gli URL dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="9850f-120">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="9850f-121">Per generare gli URL dei prodotti in Commerce Headquarters, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="9850f-121">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="9850f-122">Andare a **Immagini del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="9850f-122">Go to **Product images**.</span></span>
1. <span data-ttu-id="9850f-123">Nel riquadro azioni selezionare **Definisci modello media**.</span><span class="sxs-lookup"><span data-stu-id="9850f-123">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="9850f-124">Nel riquadro delle proprietà **Definisci modello media**, in **URL multimediali**, selezionare **Genera URL**.</span><span class="sxs-lookup"><span data-stu-id="9850f-124">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="9850f-125">Quando si abilita la funzionalità di consiglio "acquista prodotti simili", inizia il processo di generazione degli elenchi di consigli sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="9850f-125">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="9850f-126">Potrebbe essere necessario fino a un giorno prima che questi elenchi siano disponibili e visibili online e nei terminali POS.</span><span class="sxs-lookup"><span data-stu-id="9850f-126">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="9850f-127">Per abilitare la funzione di consigli "acquista prodotti simili" in Commerce headquarters, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="9850f-127">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="9850f-128">Andare a **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="9850f-128">Go to **Feature management**.</span></span>
1. <span data-ttu-id="9850f-129">Nell'elenco delle funzioni disponibili, cercare e selezionare **Acquista prodotti simili**.</span><span class="sxs-lookup"><span data-stu-id="9850f-129">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="9850f-130">Nel riquadro di destra, selezionare **Abilita** per attivare il servizio.</span><span class="sxs-lookup"><span data-stu-id="9850f-130">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="9850f-131">La figura seguente mostra la funzione **Acquista prodotti simili** nella pagina **Gestione funzionalità** in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="9850f-131">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![La funzione Acquista prodotti simili nella pagina Gestione funzionalità in Commerce headquarters](./media/enableshopsimilarlooks.png)

<span data-ttu-id="9850f-133">Dopo che le attività precedenti sono state completate, i terminali POS vengono automaticamente migliorati con un pannello **Acquista prodotti simili** contestuale.</span><span class="sxs-lookup"><span data-stu-id="9850f-133">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="9850f-134">Selezionando **Ulteriori informazioni**, gli utenti dei terminali POS possono essere indirizzati a una pagina dedicata "acquista prodotti simili" che può essere filtrata ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="9850f-134">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="9850f-135">Se si disabilita la funzione "acquista prodotti simili", nessun altro tipo di consiglio sui prodotti sarà interessato.</span><span class="sxs-lookup"><span data-stu-id="9850f-135">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="9850f-136">Per ulteriori informazioni relative ai suggerimenti sui prodotti, vedere [Panoramica suggerimenti sul prodotto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="9850f-136">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="9850f-137">Aggiungi un pulsante Acquista prodotti simili alle pagine dei dettagli dei prodotti utilizzando la creazione di siti Commerce</span><span class="sxs-lookup"><span data-stu-id="9850f-137">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="9850f-138">Dopo aver abilitato la funzione di consigli "acquista prodotti simili" in Commerce headquarters, un'opzione nel generatore di siti Commerce consente ai rivenditori di aggiungere un pulsante **Acquista prodotti simili** alla casella di acquisto in qualsiasi pagina dei dettagli del prodotto (PDP).</span><span class="sxs-lookup"><span data-stu-id="9850f-138">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="9850f-139">Un cliente che seleziona questo pulsante viene indirizzato a una pagina dedicata "acquista prodotti simili" che restituisce prodotti visivamente simili.</span><span class="sxs-lookup"><span data-stu-id="9850f-139">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="9850f-140">Lì, il cliente può utilizzare i selettori per filtrare ulteriormente i prodotti.</span><span class="sxs-lookup"><span data-stu-id="9850f-140">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="9850f-141">Per aggiungere un pulsante **Acquista prodotti simili** alle pagine dei dettagli dei prodotti utilizzando la creazione di siti Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="9850f-141">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="9850f-142">Aprire una pagina di creazione di siti Web che contiene un modulo Casella acquisti.</span><span class="sxs-lookup"><span data-stu-id="9850f-142">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="9850f-143">Selezionare il modulo Casella acquisti nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="9850f-143">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="9850f-144">Nel riquadro di navigazione a destra, selezionare la casella di controllo **Abilita collegamento acquista prodotti simili**.</span><span class="sxs-lookup"><span data-stu-id="9850f-144">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="9850f-145">Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="9850f-145">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="9850f-146">Dopo la pubblicazione della pagina, la pagina dei dettagli del prodotto includerà un pulsante **Acquista prodotti simili**.</span><span class="sxs-lookup"><span data-stu-id="9850f-146">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="9850f-147">La figura seguente mostra la casella di controllo **Abilita collegamento acquista prodotti simili** e **Acquista prodotti simili** in una pagina dei dettagli del prodotto di esempio in Creazione di siti.</span><span class="sxs-lookup"><span data-stu-id="9850f-147">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![Casella di controllo Abilita collegamento acquista prodotti simili e Acquista prodotti simili in una pagina dei dettagli del prodotto in Creazione di siti](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="9850f-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9850f-149">Additional resources</span></span>

[<span data-ttu-id="9850f-150">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="9850f-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="9850f-151">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9850f-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="9850f-152">Abilita suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="9850f-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="9850f-153">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="9850f-153">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="9850f-154">Aggiungere suggerimenti sul prodotto su POS</span><span class="sxs-lookup"><span data-stu-id="9850f-154">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="9850f-155">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="9850f-155">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="9850f-156">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="9850f-156">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="9850f-157">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="9850f-157">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="9850f-158">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="9850f-158">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="9850f-159">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="9850f-159">Product recommendations FAQ</span></span>](faq-recommendations.md)
