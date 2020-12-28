---
title: Domande frequenti sui suggerimenti sul prodotto
description: In questo argomento vengono fornite informazioni sui processi e sugli strumenti che è possibile utilizzare per risolvere i problemi che riguardano i suggerimenti sul prodotto o i relativi risultati.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Core, Operations
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cf3df2267671b50c20b28dbdb1c6a21696bf2515
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413346"
---
# <a name="product-recommendations-faq"></a><span data-ttu-id="74a9a-103">Domande frequenti sui suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="74a9a-103">Product recommendations FAQ</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="74a9a-104">In questo argomento vengono fornite informazioni sui processi e sugli strumenti che è possibile utilizzare per risolvere i problemi che riguardano i [suggerimenti sul prodotto](product-recommendations.md) o i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="74a9a-104">This topic provides information about processes and tools that you can use to troubleshoot issues that are related to [product recommendations](product-recommendations.md) or their results.</span></span>

## <a name="best-practices"></a><span data-ttu-id="74a9a-105">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="74a9a-105">Best practices</span></span>
<span data-ttu-id="74a9a-106">È molto importante utilizzare il concetto delle rappresentazioni generali prodotto e delle varianti.</span><span class="sxs-lookup"><span data-stu-id="74a9a-106">It's very important to utilize the concept of product masters and variants.</span></span> <span data-ttu-id="74a9a-107">Il raggruppamento di varianti per una rappresentazione generale prodotto padre consente agli algoritmi degli elenchi e al servizio di creare modelli migliori.</span><span class="sxs-lookup"><span data-stu-id="74a9a-107">The sensible grouping of variants to a parent product master helps the list algorithms and service create better models.</span></span> <span data-ttu-id="74a9a-108">Inoltre, il servizio può servire una sola istanza di un prodotto anziché inserire tutte le varianti strettamente correlate in un elenco.</span><span class="sxs-lookup"><span data-stu-id="74a9a-108">Additionally, the service can serve just one instance of a product instead of putting all closely related variants in a list.</span></span> <span data-ttu-id="74a9a-109">Quando tutte le varianti strettamente correlate sono inserite in un elenco, è possibile avere risultati duplicati o errati.</span><span class="sxs-lookup"><span data-stu-id="74a9a-109">When all closely related variants are put in a list, erroneous or duplicate results can occur.</span></span>

## <a name="why-are-products-missing-from-my-recommendation-lists"></a><span data-ttu-id="74a9a-110">Perché i prodotti non sono presenti negli elenchi di suggerimenti?</span><span class="sxs-lookup"><span data-stu-id="74a9a-110">Why are products missing from my recommendation lists?</span></span>

<span data-ttu-id="74a9a-111">In genere, se un articolo non è presente in un elenco di suggerimenti sul prodotto, è possibile che vi sia un problema di configurazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="74a9a-111">Typically, if an item is missing from a product recommendation list, there might be a product configuration issue.</span></span> <span data-ttu-id="74a9a-112">Ad esempio, è possibile che la data di inizio o di fine di un prodotto sia errata, che una dimensione non sia configurata correttamente, che il prodotto non si trovi nell'assortimento di canale appropriato e così via.</span><span class="sxs-lookup"><span data-stu-id="74a9a-112">For example, there might be an incorrect product start date or end date, a dimension might be misconfigured, or the product might not be in the correct channel assortment, etc.</span></span>

<span data-ttu-id="74a9a-113">Se un articolo non è presente in un elenco di suggerimenti basato sull'intelligenza artificiale e sul machine learning, l'articolo potrebbe non soddisfare i criteri dell'elenco di suggerimenti o potrebbe non avere transazioni di acquisto sufficienti per essere visualizzato nell'elenco di suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="74a9a-113">If an item is missing from a recommendation list that is based on artificial intelligence-machine learning (AI-ML), the item might not fit the criteria of the recommendation list, or it might not have enough purchase transactions for the recommendation list to show it.</span></span>

<span data-ttu-id="74a9a-114">È consigliabile verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="74a9a-114">We recommend that you check these steps:</span></span>
1. <span data-ttu-id="74a9a-115">**Verificare che i suggerimenti sul prodotto siano stati attivati in HQ.**</span><span class="sxs-lookup"><span data-stu-id="74a9a-115">**Make sure that product recommendations have been enabled in HQ.**</span></span> <span data-ttu-id="74a9a-116">Per ulteriori informazioni su come abilitare questo servizio, vedere [Abilitare suggerimenti sul prodotto](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="74a9a-116">For more information about how to enable this service, see [Enable product recommendations](enable-product-recommendations.md).</span></span>
1. <span data-ttu-id="74a9a-117">**Verificare che le proprietà chiave del prodotto siano state impostate.**</span><span class="sxs-lookup"><span data-stu-id="74a9a-117">**Make sure that key product properties are set.**</span></span> <span data-ttu-id="74a9a-118">Ad esempio, gli assortimenti di prodotti devono essere impostati su **Includi**.</span><span class="sxs-lookup"><span data-stu-id="74a9a-118">For example, product assortments must be set to **Include**.</span></span>
1. <span data-ttu-id="74a9a-119">**Per i prodotti assortiti di recente, esiste la possibilità che il prodotto sia visualizzato nel nuovo elenco solo dopo 3 ore.**</span><span class="sxs-lookup"><span data-stu-id="74a9a-119">**For newly assorted products, it might take up to 3 hours before the product will start appearing in the new list.**</span></span>
1. <span data-ttu-id="74a9a-120">**Se un prodotto non è ancora visualizzato in Di tendenza, Più venduti, Alle persone piace anche o Spesso acquistati insieme, è possibile che il prodotto non abbia transazioni sufficienti.**</span><span class="sxs-lookup"><span data-stu-id="74a9a-120">**If a product is still not appearing in Trending, Best selling, People also like, or Frequently bought together, then that product might not have enough transactions.**</span></span> <span data-ttu-id="74a9a-121">In questo caso, è possibile attendere che si verifichino altre transazioni, aggiornare i parametri degli elenchi di suggerimenti predefiniti o modificare manualmente i risultati degli elenchi di suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="74a9a-121">In this case, you can either wait for more transactions to occur, update the default recommendation list parameters, or use manual intervention to modify the recommendation product list results.</span></span> <span data-ttu-id="74a9a-122">Per ulteriori informazioni sui parametri relativi ai suggerimenti, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="74a9a-122">For more information about recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>
1. <span data-ttu-id="74a9a-123">**Verificare che il prodotto soddisfi i criteri dei suggerimenti per l'elenco.**</span><span class="sxs-lookup"><span data-stu-id="74a9a-123">**Make sure that the product meets the recommendation criteria for the list.**</span></span> <span data-ttu-id="74a9a-124">Per ulteriori informazioni sui parametri relativi ai suggerimenti sul prodotto, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="74a9a-124">For more information about product recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="how-can-i-prevent-poor-recommendation-results-from-being-returned"></a><span data-ttu-id="74a9a-125">Come è possibile evitare di avere risultati dei suggerimenti insoddisfacenti?</span><span class="sxs-lookup"><span data-stu-id="74a9a-125">How can I prevent poor recommendation results from being returned?</span></span>

<span data-ttu-id="74a9a-126">Gli elenchi di suggerimenti richiedono un ampio volume di transazioni per generare risultati.</span><span class="sxs-lookup"><span data-stu-id="74a9a-126">Recommendation lists require a large volume of transactions to produce results.</span></span> <span data-ttu-id="74a9a-127">Di conseguenza, è importante che gli utenti forniscano dati sulle transazioni completi.</span><span class="sxs-lookup"><span data-stu-id="74a9a-127">Therefore, it's important that users provide full historical transaction data.</span></span>

<span data-ttu-id="74a9a-128">Inoltre, i prodotti che non hanno transazioni o un numero elevato di transazioni generalmente non hanno risultati in **Alle persone piace anche** o **Spesso acquistati insieme** e non sono visualizzati negli elenchi di suggerimenti **Più venduti** o **Di tendenza**.</span><span class="sxs-lookup"><span data-stu-id="74a9a-128">Additionally, products that have no transactions or few transactions typically don't have **People also like** or **Frequently bought together** results, and don't appear in **Trending** or **Best selling** recommendation lists.</span></span> <span data-ttu-id="74a9a-129">Questa situazione può verificarsi spesso per prodotti nuovissimi o prodotti vecchi con un numero ridotto di acquisti.</span><span class="sxs-lookup"><span data-stu-id="74a9a-129">This situation can often occur for very new products, or for old products that have a small number of purchases.</span></span> <span data-ttu-id="74a9a-130">Per i nuovi articoli popolari, questo problema verrà risolto facilmente.</span><span class="sxs-lookup"><span data-stu-id="74a9a-130">Popular new items will easily overcome this issue.</span></span>

<span data-ttu-id="74a9a-131">È consigliabile procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="74a9a-131">We recommend that you follow these steps:</span></span>
1. <span data-ttu-id="74a9a-132">**Verificare che il prodotto soddisfi i criteri dei suggerimenti per quell'elenco.**</span><span class="sxs-lookup"><span data-stu-id="74a9a-132">**Make sure that the product meets the recommendation criteria for that list.**</span></span> <span data-ttu-id="74a9a-133">Per ulteriori informazioni sui parametri relativi ai suggerimenti sul prodotto, vedere Modificare i risultati dei suggerimenti sul prodotto basati su AI-ML.</span><span class="sxs-lookup"><span data-stu-id="74a9a-133">For more information about product recommendation parameters, see Modify AI-ML-based product recommendation results.</span></span>
1. <span data-ttu-id="74a9a-134">**Se il prodotto è nuovo, valutare l'opportunità di modificare un elenco di suggerimenti fino a che il prodotto ha più transazioni.**</span><span class="sxs-lookup"><span data-stu-id="74a9a-134">**If the product is new, consider modifying a recommendation list until the product has more transactions.**</span></span> <span data-ttu-id="74a9a-135">Per ulteriori informazioni su come modificare i risultati degli elenchi di suggerimenti, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="74a9a-135">For more information about how to modify recommendation list results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>


- <span data-ttu-id="74a9a-136">**Verificare che il prodotto soddisfi i criteri dei suggerimenti per quell'elenco.**</span><span class="sxs-lookup"><span data-stu-id="74a9a-136">**Make sure that the product meets the recommendation criteria for that list.**</span></span> <span data-ttu-id="74a9a-137">Per ulteriori informazioni sui parametri relativi ai suggerimenti sul prodotto, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="74a9a-137">For more information about product recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>
- <span data-ttu-id="74a9a-138">**Se il prodotto è nuovo, valutare l'opportunità di modificare un elenco di suggerimenti fino a che il prodotto ha più transazioni.**</span><span class="sxs-lookup"><span data-stu-id="74a9a-138">**If the product is new, consider modifying a recommendation list until the product has more transactions**.</span></span> <span data-ttu-id="74a9a-139">Per ulteriori informazioni su come modificare i risultati degli elenchi di suggerimenti, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="74a9a-139">For more information about how to modify recommendation list results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="can-i-remove-a-product-but-still-see-it-in-the-store"></a><span data-ttu-id="74a9a-140">È possibile continuare a visualizzare un prodotto nel punto vendita anche dopo averlo eliminato?</span><span class="sxs-lookup"><span data-stu-id="74a9a-140">Can I remove a product but still see it in the store?</span></span>

<span data-ttu-id="74a9a-141">Se necessario, è possibile rettificare gli elenchi generati mediante algoritmi.</span><span class="sxs-lookup"><span data-stu-id="74a9a-141">You can adjust lists that are algorithmically generated if a business need arises.</span></span> <span data-ttu-id="74a9a-142">Tuttavia, se un prodotto viene rimosso da un elenco di suggerimenti, il prodotto rimarrà individuabile nel punto vendita.</span><span class="sxs-lookup"><span data-stu-id="74a9a-142">However, if a product is removed from a recommendation list, the product will remain discoverable in the store.</span></span> <span data-ttu-id="74a9a-143">Per ulteriori informazioni su come modificare i risultati dei suggerimenti sul prodotto, vedere [Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="74a9a-143">For more information about how to modify product recommendation results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

<span data-ttu-id="74a9a-144">Se un articolo non deve essere individuato nel punto vendita, è necessario impostare **Assortimenti articolo** su **Escludi**.</span><span class="sxs-lookup"><span data-stu-id="74a9a-144">If you must block an item from being discovered in the store, you must change the **Item assortments** value to **Exclude**.</span></span>

## <a name="how-do-i-add-a-list-to-an-e-commerce-page"></a><span data-ttu-id="74a9a-145">Come si aggiunge un elenco a una pagina di e-Commerce?</span><span class="sxs-lookup"><span data-stu-id="74a9a-145">How do I add a list to an e-Commerce page?</span></span>

<span data-ttu-id="74a9a-146">Per informazioni su come aggiungere le pagine di suggerimenti sul prodotto al sito Web di e-Commerce, vedere [Aggiungere elenchi di suggerimenti sul prodotto alle pagine](add-reco-list-to-page.md).</span><span class="sxs-lookup"><span data-stu-id="74a9a-146">For information about how to add product recommendation pages to your e-Commerce website, see [Add product recommendation lists to pages](add-reco-list-to-page.md).</span></span>

## <a name="how-do-i-enable-recommendations-on-pos"></a><span data-ttu-id="74a9a-147">Come si abilitano i suggerimenti nel POS?</span><span class="sxs-lookup"><span data-stu-id="74a9a-147">How do I enable recommendations on POS?</span></span>

<span data-ttu-id="74a9a-148">Dopo avere abilitato i suggerimenti sul prodotto, sarà necessario aggiungere il pannello dei suggerimenti alla schermata POS di controllo.</span><span class="sxs-lookup"><span data-stu-id="74a9a-148">After enabling product recommendations, you will need to add the recommendations panel to the control POS screen.</span></span> <span data-ttu-id="74a9a-149">Per ulteriori informazioni, vedere [Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="74a9a-149">For more information, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="74a9a-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="74a9a-150">Additional resources</span></span>

[<span data-ttu-id="74a9a-151">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="74a9a-151">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="74a9a-152">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="74a9a-152">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="74a9a-153">Abilita suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="74a9a-153">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="74a9a-154">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="74a9a-154">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="74a9a-155">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="74a9a-155">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="74a9a-156">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="74a9a-156">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="74a9a-157">Aggiungere suggerimenti sul prodotto nel POS</span><span class="sxs-lookup"><span data-stu-id="74a9a-157">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="74a9a-158">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="74a9a-158">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="74a9a-159">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="74a9a-159">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="74a9a-160">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="74a9a-160">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="74a9a-161">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="74a9a-161">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)
