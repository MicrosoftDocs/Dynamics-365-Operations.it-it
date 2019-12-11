---
title: Panoramica suggerimenti sul prodotto
description: Questo argomento fornisce informazioni generali sui suggerimenti sul prodotto. I suggerimenti sul prodotto consentono ai clienti di individuare facilmente e rapidamente i prodotti desiderati e persino i prodotti che originariamente non intendevano acquistare.
author: Moonma
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770049"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="65917-104">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="65917-104">Product recommendations overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="65917-105">Microsoft Dynamics 365 Commerce può essere utilizzato per visualizzare suggerimenti sul prodotto nel sito Web di e-Commerce e nel dispositivo POS.</span><span class="sxs-lookup"><span data-stu-id="65917-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="65917-106">I suggerimenti sul prodotto sono articoli a cui un cliente potrebbe essere interessato.</span><span class="sxs-lookup"><span data-stu-id="65917-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="65917-107">I suggerimenti si basano sulle tendenze di acquisto di altri clienti in punti vendita online e fisici.</span><span class="sxs-lookup"><span data-stu-id="65917-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="65917-108">I suggerimenti sul prodotto consentono ai clienti di individuare facilmente e rapidamente i prodotti desiderati durante un'esperienza ottimale.</span><span class="sxs-lookup"><span data-stu-id="65917-108">Product recommendations let customers easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="65917-109">Il cross-selling e l'up-selling possono inoltre essere utilizzati per consentire ai clienti di individuare ulteriori prodotti che originariamente non intendevano acquistare.</span><span class="sxs-lookup"><span data-stu-id="65917-109">Cross-selling and upselling can even be used to help customers find additional products than they didn't originally intend to buy.</span></span> <span data-ttu-id="65917-110">Quando i suggerimenti sono utilizzati per consentire l'individuazione di prodotti, possono creare più opportunità di conversione, aumentare i ricavi da vendite e persino migliorare la soddisfazione e la conservazione dei clienti.</span><span class="sxs-lookup"><span data-stu-id="65917-110">When recommendations are used to help with product discovery, they can create more conversion opportunities, help increase sales revenue, and even help enhance customer satisfaction and retention.</span></span>

<span data-ttu-id="65917-111">In Commerce, i suggerimenti sul prodotto sono generati mediante tecnologie di machine learning del servizio Suggerimenti di Microsoft su vasta scala.</span><span class="sxs-lookup"><span data-stu-id="65917-111">In Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>


## <a name="scenarios"></a><span data-ttu-id="65917-112">Scenari</span><span class="sxs-lookup"><span data-stu-id="65917-112">Scenarios</span></span>

<span data-ttu-id="65917-113">I suggerimenti sul prodotto sono disponibili per i seguenti scenari:</span><span class="sxs-lookup"><span data-stu-id="65917-113">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="65917-114">**In qualsiasi pagina di esplorazione del punto vendita o nella pagina di destinazione di e-Commerce:** se i clienti o gli addetti alle vendite visitano una pagina del punto vendita, il motore dei suggerimenti può suggerire prodotti negli elenchi **Novità**, **Più venduti** e **Di tendenza**.</span><span class="sxs-lookup"><span data-stu-id="65917-114">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="65917-115">**Nella pagina dettagli prodotto:** se i clienti o gli addetti alle vendite visitano una pagina **Dettagli prodotto**, il motore dei suggerimenti suggerisce altri articoli il cui acquisto è probabile.</span><span class="sxs-lookup"><span data-stu-id="65917-115">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="65917-116">Questi articoli sono visualizzati nell'elenco **Alle persone piace anche**.</span><span class="sxs-lookup"><span data-stu-id="65917-116">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="65917-117">**Nella pagina Transazione o checkout:** il motore dei suggerimenti suggerisce articoli in base all'intero elenco di articoli nel carrello.</span><span class="sxs-lookup"><span data-stu-id="65917-117">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="65917-118">Questi articoli sono visualizzati nell'elenco **Spesso acquistati insieme**.</span><span class="sxs-lookup"><span data-stu-id="65917-118">These items appear in the **Frequently bought together** list.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="65917-119">Servizio Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="65917-119">Recommendation service</span></span>

<span data-ttu-id="65917-120">I suggerimenti sul prodotto utilizzano le tecnologie di machine learning del servizio Suggerimenti come segue:</span><span class="sxs-lookup"><span data-stu-id="65917-120">Product recommendations use the Recommendations machine learning technologies in the following way:</span></span>

- <span data-ttu-id="65917-121">I dati nel formato richiesto dal servizio Suggerimenti vengono estratti dal database operativo di Commerce e sono inviati all'Archivio entità.</span><span class="sxs-lookup"><span data-stu-id="65917-121">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to the Entity store.</span></span>
- <span data-ttu-id="65917-122">Il servizio Suggerimenti utilizza i dati per preparare i modelli di suggerimenti per gli elenchi **Alle persone piace anche**, **Spesso acquistati insieme**, **Novità**, **Più venduti** e **Di tendenza**.</span><span class="sxs-lookup"><span data-stu-id="65917-122">The Recommendation service uses the data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="65917-123">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="65917-123">Additional resources</span></span>

[<span data-ttu-id="65917-124">Abilitare suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="65917-124">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="65917-125">Creare elenchi dettagliati di suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="65917-125">Create curated product recommendation lists</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="65917-126">Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML</span><span class="sxs-lookup"><span data-stu-id="65917-126">Manage AI-ML-based product recommendation results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="65917-127">Aggiungere elenchi di suggerimenti sul prodotto alle pagine</span><span class="sxs-lookup"><span data-stu-id="65917-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
