---
title: Panoramica suggerimenti sul prodotto
description: Questo argomento fornisce informazioni generali sui suggerimenti sul prodotto. I suggerimenti sul prodotto consentono ai clienti di individuare facilmente e rapidamente i prodotti desiderati e persino i prodotti che originariamente non intendevano acquistare.
author: Moonma
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5aa7db8e53906f9e1416b912fe2c3b70d5430258
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413329"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="6fd10-104">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="6fd10-104">Product recommendations overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6fd10-105">Microsoft Dynamics 365 Commerce può essere utilizzato per visualizzare suggerimenti sul prodotto nel sito Web di e-Commerce e nel dispositivo POS.</span><span class="sxs-lookup"><span data-stu-id="6fd10-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="6fd10-106">I suggerimenti sul prodotto sono articoli a cui un cliente potrebbe essere interessato.</span><span class="sxs-lookup"><span data-stu-id="6fd10-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="6fd10-107">I suggerimenti si basano sulle tendenze di acquisto di altri clienti in punti vendita online e fisici.</span><span class="sxs-lookup"><span data-stu-id="6fd10-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="6fd10-108">I suggerimenti sul prodotto consentono ai clienti di individuare facilmente e rapidamente i prodotti desiderati durante un'esperienza ottimale.</span><span class="sxs-lookup"><span data-stu-id="6fd10-108">Product recommendations allow customers to easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="6fd10-109">Il cross-selling e l'up-selling possono inoltre essere utilizzati per consentire ai clienti di individuare ulteriori prodotti che originariamente non intendevano acquistare.</span><span class="sxs-lookup"><span data-stu-id="6fd10-109">Cross-selling and upselling can even be used to assist customers find additional products that they didn't originally intend to buy.</span></span> <span data-ttu-id="6fd10-110">Quando i suggerimenti sono utilizzati per aumentare l'individuazione di prodotti, possono creare più opportunità di conversione, aumentare i ricavi da vendite e persino amplificare la soddisfazione e la conservazione dei clienti.</span><span class="sxs-lookup"><span data-stu-id="6fd10-110">When recommendations are used to enhance product discovery, they create more conversion opportunities, help increase sales revenue, and even amplify customer satisfaction and retention.</span></span>

<span data-ttu-id="6fd10-111">In e-Commerce, i suggerimenti sul prodotto sono generati mediante tecnologie di machine learning del servizio Suggerimenti di Microsoft su vasta scala.</span><span class="sxs-lookup"><span data-stu-id="6fd10-111">In e-Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="6fd10-112">Servizio Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="6fd10-112">Recommendation service</span></span>

<span data-ttu-id="6fd10-113">Il servizio di suggerimenti sui prodotti utilizza le tecnologie di intelligenza artificiale e machine learning (AI-ML) nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6fd10-113">The product recommendations service utilizes artificial intelligence and machine learning (AI-ML) technologies in the following way:</span></span>

- <span data-ttu-id="6fd10-114">I dati nel formato richiesto dal servizio Suggerimenti vengono estratti dal database operativo di Commerce e sono inviati a Azure Data Lake Storage o all'Archivio entità.</span><span class="sxs-lookup"><span data-stu-id="6fd10-114">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to Azure Data Lake Storage or Entity store.</span></span>
- <span data-ttu-id="6fd10-115">Il servizio Suggerimenti utilizza i dati memorizzati per preparare i modelli di suggerimenti per gli elenchi **Alle persone piace anche**, **Spesso acquistati insieme**, **Novità**, **Più venduti** e **Di tendenza**.</span><span class="sxs-lookup"><span data-stu-id="6fd10-115">The recommendations service uses the stored data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="scenarios"></a><span data-ttu-id="6fd10-116">Scenari</span><span class="sxs-lookup"><span data-stu-id="6fd10-116">Scenarios</span></span>

<span data-ttu-id="6fd10-117">I suggerimenti sul prodotto sono disponibili per i seguenti scenari:</span><span class="sxs-lookup"><span data-stu-id="6fd10-117">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="6fd10-118">**In qualsiasi pagina di esplorazione del punto vendita o nella pagina di destinazione di e-Commerce:** se i clienti o gli addetti alle vendite visitano una pagina del punto vendita, il motore dei suggerimenti può suggerire prodotti negli elenchi **Novità**, **Più venduti** e **Di tendenza**.</span><span class="sxs-lookup"><span data-stu-id="6fd10-118">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="6fd10-119">**Nella pagina dettagli prodotto:** se i clienti o gli addetti alle vendite visitano una pagina **Dettagli prodotto**, il motore dei suggerimenti suggerisce altri articoli il cui acquisto è probabile.</span><span class="sxs-lookup"><span data-stu-id="6fd10-119">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="6fd10-120">Questi articoli sono visualizzati nell'elenco **Alle persone piace anche**.</span><span class="sxs-lookup"><span data-stu-id="6fd10-120">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="6fd10-121">**Nella pagina Transazione o checkout:** il motore dei suggerimenti suggerisce articoli in base all'intero elenco di articoli nel carrello.</span><span class="sxs-lookup"><span data-stu-id="6fd10-121">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="6fd10-122">Questi articoli sono visualizzati nell'elenco **Spesso acquistati insieme**.</span><span class="sxs-lookup"><span data-stu-id="6fd10-122">These items appear in the **Frequently bought together** list.</span></span>
- <span data-ttu-id="6fd10-123">**Suggerimenti personalizzati:** i merchandiser possono offrire ai clienti che hanno effettuato l'accesso un elenco **Selezioni personalizzate**, oltre alle nuove funzionalità che consentono di personalizzare scenari di elenco esistenti in base a quel cliente.</span><span class="sxs-lookup"><span data-stu-id="6fd10-123">**Personalized recommendations:** Merchandizers can provide signed-in customers a personalized **picks for you** list, in addition to new functionality that allows for existing list scenarios to be personalized based on that customer.</span></span> <span data-ttu-id="6fd10-124">Per ulteriori informazioni, vedere [Abilitare i suggerimenti personalizzati.](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="6fd10-124">To learn more, see [Enable personalized recommendations.](personalized-recommendations.md).</span></span>

### <a name="types-of-product-recommendations"></a><span data-ttu-id="6fd10-125">Tipi di suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="6fd10-125">Types of product recommendations</span></span>

<span data-ttu-id="6fd10-126">La tabella seguente descrive vari tipi di suggerimenti sul prodotto automatizzati disponibili per i rivenditori da implementare nella soluzione Dynamics 365 Commerce tramite il [modulo Raccolta prodotti](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6fd10-126">The following table describes various types of automated product recommendations available for retailers to implement in their Dynamics 365 Commerce solution via the [product collection module](product-collection-module-overview.md).</span></span> <span data-ttu-id="6fd10-127">I rivenditori possono anche mostrare risultati personalizzati per un utente che ha effettuato l'accesso se l'autore del sito sceglie tale opzione.</span><span class="sxs-lookup"><span data-stu-id="6fd10-127">Retailers can also show personalized results for a signed-in user if the site author chooses that option.</span></span>

| <span data-ttu-id="6fd10-128">Modulo Raccolta prodotti</span><span class="sxs-lookup"><span data-stu-id="6fd10-128">Product collection module</span></span>  | <span data-ttu-id="6fd10-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="6fd10-129">Type</span></span> | <span data-ttu-id="6fd10-130">descrizione</span><span class="sxs-lookup"><span data-stu-id="6fd10-130">Description</span></span> |
|----------------------------|------|-------------|
| <span data-ttu-id="6fd10-131">Nuove</span><span class="sxs-lookup"><span data-stu-id="6fd10-131">New</span></span>                        | <span data-ttu-id="6fd10-132">Algoritmico</span><span class="sxs-lookup"><span data-stu-id="6fd10-132">Algorithmic</span></span> | <span data-ttu-id="6fd10-133">Questo modulo mostra un elenco dei prodotti più recenti che sono stati assortiti di recente in canali e cataloghi.</span><span class="sxs-lookup"><span data-stu-id="6fd10-133">This module shows a list of the newest products that have been recently assorted to channels and catalogs.</span></span> |
| <span data-ttu-id="6fd10-134">Più venduti</span><span class="sxs-lookup"><span data-stu-id="6fd10-134">Best selling</span></span>               | <span data-ttu-id="6fd10-135">Algoritmico</span><span class="sxs-lookup"><span data-stu-id="6fd10-135">Algorithmic</span></span> | <span data-ttu-id="6fd10-136">Questo modulo mostra un elenco di prodotti classificati in base al più alto numero di vendite.</span><span class="sxs-lookup"><span data-stu-id="6fd10-136">This module shows a list of products that are ranked by the highest number of sales.</span></span> |
| <span data-ttu-id="6fd10-137">Di tendenza</span><span class="sxs-lookup"><span data-stu-id="6fd10-137">Trending</span></span>                   | <span data-ttu-id="6fd10-138">Algoritmico</span><span class="sxs-lookup"><span data-stu-id="6fd10-138">Algorithmic</span></span> | <span data-ttu-id="6fd10-139">Questo modulo presenta un elenco dei prodotti di maggior successo in un determinato periodo, classificati per numero più alto di vendite.</span><span class="sxs-lookup"><span data-stu-id="6fd10-139">This module shows a list of the highest-performing products for a given period, ranked by highest number of sales.</span></span>  |
| <span data-ttu-id="6fd10-140">Spesso acquistati insieme</span><span class="sxs-lookup"><span data-stu-id="6fd10-140">Frequently bought together</span></span> | <span data-ttu-id="6fd10-141">AI-ML</span><span class="sxs-lookup"><span data-stu-id="6fd10-141">AI-ML</span></span> | <span data-ttu-id="6fd10-142">Questo modulo offre suggerimenti per un elenco di prodotti che vengono comunemente acquistati insieme al contenuto del carrello attuale dei consumatori.</span><span class="sxs-lookup"><span data-stu-id="6fd10-142">This module recommends a list of products that are commonly purchased together with the contents of the consumers current cart.</span></span> |
| <span data-ttu-id="6fd10-143">Alle persone piace anche</span><span class="sxs-lookup"><span data-stu-id="6fd10-143">People also like</span></span>           | <span data-ttu-id="6fd10-144">AI-ML</span><span class="sxs-lookup"><span data-stu-id="6fd10-144">AI-ML</span></span> | <span data-ttu-id="6fd10-145">Questo modulo offre suggerimenti per i prodotti per un determinato prodotto iniziale in base ai modelli di acquisto dei consumatori.</span><span class="sxs-lookup"><span data-stu-id="6fd10-145">This module recommends products for a given seed product based on consumer purchase patterns.</span></span> |
| <span data-ttu-id="6fd10-146">Selezioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="6fd10-146">Picks for you</span></span>              | <span data-ttu-id="6fd10-147">AI-ML</span><span class="sxs-lookup"><span data-stu-id="6fd10-147">AI-ML</span></span> | <span data-ttu-id="6fd10-148">Questo modulo offre suggerimenti per un elenco personalizzato di prodotti basato sui modelli di acquisto dell'utente che ha effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6fd10-148">This module recommends a personalized list of products based on purchase patterns of the signed-in user.</span></span> <span data-ttu-id="6fd10-149">Per un utente guest, questo elenco verrà compresso.</span><span class="sxs-lookup"><span data-stu-id="6fd10-149">For a guest user, this list will be collapsed.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="6fd10-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6fd10-150">Additional resources</span></span>

[<span data-ttu-id="6fd10-151">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6fd10-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="6fd10-152">Abilita suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="6fd10-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="6fd10-153">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="6fd10-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="6fd10-154">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="6fd10-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="6fd10-155">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="6fd10-155">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="6fd10-156">Aggiungere suggerimenti sul prodotto nel POS</span><span class="sxs-lookup"><span data-stu-id="6fd10-156">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="6fd10-157">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="6fd10-157">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="6fd10-158">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="6fd10-158">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="6fd10-159">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="6fd10-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="6fd10-160">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="6fd10-160">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="6fd10-161">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="6fd10-161">Product recommendations FAQ</span></span>](faq-recommendations.md)
