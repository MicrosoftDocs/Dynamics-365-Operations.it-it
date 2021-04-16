---
title: Regolare i risultati dei suggerimenti sul prodotto basati su AI-ML
description: In questo argomento viene descritto come gestire i risultati dei suggerimenti sul prodotto basati su AI-ML (intelligenza artificiale-machine learning) all'azienda.
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: dfe04881e71558ed326025d8f2545c3c611df3aa
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796972"
---
# <a name="adjust-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="0ed31-103">Regolare i risultati dei suggerimenti sul prodotto basati su AI-ML</span><span class="sxs-lookup"><span data-stu-id="0ed31-103">Adjust AI-ML-based product recommendation results</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0ed31-104">In questo argomento viene descritto come regolare i risultati dei suggerimenti sul prodotto basati su AI-ML (intelligenza artificiale-machine learning) all'azienda.</span><span class="sxs-lookup"><span data-stu-id="0ed31-104">This topic explains how to adjust product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="0ed31-105">Dopo l'abilitazione delle raccomandazioni sul prodotto, le impostazioni predefinite diventano effettive. Questi parametri possono rivelarsi utili per numerose esigenze.</span><span class="sxs-lookup"><span data-stu-id="0ed31-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="0ed31-106">Si consiglia di spendere un po' di tempo per determinare se i risultati corrispondono all'andamento di vendita dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="0ed31-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="0ed31-107">Suggeriamo di valutare i risultati per alcuni giorni prima di modificare i parametri come necessario e di eseguire di nuovo dei test.</span><span class="sxs-lookup"><span data-stu-id="0ed31-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="0ed31-108">Informazioni sui parametri degli elenchi di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="0ed31-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="0ed31-109">Prima di modificare i parametri, è necessario comprendere come questi influiscono sui risultati.</span><span class="sxs-lookup"><span data-stu-id="0ed31-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="0ed31-110">Elenco di prodotti "Di tendenza"</span><span class="sxs-lookup"><span data-stu-id="0ed31-110">"Trending" product list</span></span>

<span data-ttu-id="0ed31-111">L'elenco di prodotti "Di tendenza" include due parametri che possono essere modificati:</span><span class="sxs-lookup"><span data-stu-id="0ed31-111">The "Trending" product list has two parameters that can be changed:</span></span>

![Esempio di parametri predefiniti dell'elenco Di tendenza](./media/exampletrendingparameters.png)

1. <span data-ttu-id="0ed31-113">**Includi nuovi prodotti degli ultimi X giorni** - I prodotti che sono stati aggiunti entro il numero di giorni specificato prima della data corrente possono essere utilizzati per selezionare candidati prodotto.</span><span class="sxs-lookup"><span data-stu-id="0ed31-113">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="0ed31-114">Il valore predefinito nell'immagine suggerisce che i prodotti aggiunti fino a 180 giorni prima della data corrente possono essere utilizzati nell'elenco di prodotti Di tendenza.</span><span class="sxs-lookup"><span data-stu-id="0ed31-114">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="0ed31-115">**Includi vendite degli ultimi X giorni** - Le transazioni di vendita verificatesi entro il numero di giorni specificato prima della data corrente possono essere utilizzati per ordinare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="0ed31-115">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="0ed31-116">Il valore predefinito di cui sopra suggerisce che tutti gli acquisti di un prodotto effettuati negli ultimi 30 giorni sono utilizzati per determinare la posizione del prodotto nell'elenco di prodotti Di tendenza.</span><span class="sxs-lookup"><span data-stu-id="0ed31-116">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="0ed31-117">Elenco di prodotti "Più venduti"</span><span class="sxs-lookup"><span data-stu-id="0ed31-117">"Best selling" product list</span></span>

<span data-ttu-id="0ed31-118">A seconda dell'attività commerciale, l'elenco "Più venduti" può avere risultati differenti rispetto all'elenco Di tendenza, anche se entrambi utilizzano dati transazione per ordinare prodotti.</span><span class="sxs-lookup"><span data-stu-id="0ed31-118">Depending on your business, the "Best selling" list can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="0ed31-119">Poiché l'elenco Più venduti non ha alcun limite basato sulla data di assortimento, questo elenco può ancora evidenziare prodotti più vecchi molto popolari che potrebbero essere stati rimossi dall'elenco Di tendenza.</span><span class="sxs-lookup"><span data-stu-id="0ed31-119">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="0ed31-120">L'elenco di prodotti "Più venduti" include un parametro che può essere modificato:</span><span class="sxs-lookup"><span data-stu-id="0ed31-120">The "Best selling" product list has one parameter that can be changed:</span></span>

![Esempio di parametro predefinito dell'elenco Più venduti](./media/examplebestsellingparameters.PNG)

1. <span data-ttu-id="0ed31-122">**Includi vendite degli ultimi X giorni** - Le transazioni di vendita verificatesi entro il numero di giorni specificato prima della data corrente possono essere utilizzati per ordinare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="0ed31-122">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="0ed31-123">Il valore predefinito di cui sopra suggerisce che tutti gli acquisti di un prodotto effettuati negli ultimi 30 giorni sono utilizzati per determinare il posizionamento del prodotto nell'elenco di prodotti Più venduti.</span><span class="sxs-lookup"><span data-stu-id="0ed31-123">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="0ed31-124">Aggiungere o rimuovere manualmente prodotti negli elenchi di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="0ed31-124">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling-lists"></a><span data-ttu-id="0ed31-125">Per gli elenchi "Novità", "Di tendenza" o "Più venduti"</span><span class="sxs-lookup"><span data-stu-id="0ed31-125">For "New," "Trending," or "Best selling" lists</span></span>

1.  <span data-ttu-id="0ed31-126">Andare a **Retail e Commerce** > **Suggerimenti sul prodotto** > **Parametri suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="0ed31-126">Go to **Retail and Commerce** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="0ed31-127">Nell'elenco dei parametri condivisi, selezionare **Elenchi suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="0ed31-127">In the list of shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="0ed31-128">Selezionare l'elenco per il quale si intende aggiungere o rimuovere prodotti.</span><span class="sxs-lookup"><span data-stu-id="0ed31-128">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="0ed31-129">Per aggiungere prodotti alla tabella, selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="0ed31-129">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="0ed31-130">Sotto la colonna Prodotto, cerca un prodotto per **Nome** o **Numero prodotto**.</span><span class="sxs-lookup"><span data-stu-id="0ed31-130">Under the Product column, search for a product by **Name** or **Product number.**</span></span>

    ![Esempio di ricerca di un prodotto nell'elenco Nuovo prodotto](./media/examplenewlistconfiguration1.png)

1.  <span data-ttu-id="0ed31-132">Sotto la colonna Tipo di riga, selezionare una delle due seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="0ed31-132">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="0ed31-133">**Includi** - Aggiunge un prodotto all'elenco</span><span class="sxs-lookup"><span data-stu-id="0ed31-133">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="0ed31-134">**Escludi** - Rimuove un prodotto dall'elenco</span><span class="sxs-lookup"><span data-stu-id="0ed31-134">**Exclude** – removes a product from appearing in the list</span></span>
    
    ![Esempio di inclusione o esclusione di un prodotto dall'elenco Nuovo prodotto](./media/examplenewlistconfiguration2.png)

1.  <span data-ttu-id="0ed31-136">La modifica di **Ordine di visualizzazione** cambierà l'ordine di visualizzazione dei prodotti contrassegnati con **includi** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0ed31-136">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="0ed31-137">Se due prodotti hanno lo stesso valore di **ordine di visualizzazione**, l'ordine finale di quei due risultati può differire dal back office.</span><span class="sxs-lookup"><span data-stu-id="0ed31-137">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="0ed31-138">Per rimuovere prodotti dalla tabella: selezionare la riga da rimuovere e selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="0ed31-138">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="0ed31-139">Per gli elenchi "Alle persone piace anche" o "Spesso acquistati insieme"</span><span class="sxs-lookup"><span data-stu-id="0ed31-139">For "People also like" or "Frequently bought together" lists</span></span>

<span data-ttu-id="0ed31-140">Nel contesto degli elenchi "Alle persone piace anche" o "Spesso acquistati insieme", il machine learning è utilizzato per analizzare criteri di acquisto dei consumatori allo scopo di consigliare prodotti correlati acquistati spesso insieme a un prodotto iniziale univoco.</span><span class="sxs-lookup"><span data-stu-id="0ed31-140">In the context of "Frequently bought together" or "People also like" lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="0ed31-141">Un *prodotto iniziale* è il prodotto per il quale si desidera generare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0ed31-141">A *seed product* is the product you want to generate results for.</span></span> <span data-ttu-id="0ed31-142">Nel contesto della modifica manuale degli elenchi di suggerimenti, si aggiungono o rimuovono risultati per questo prodotto.</span><span class="sxs-lookup"><span data-stu-id="0ed31-142">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="0ed31-143">Seguire questi passaggi per aggiungere o rimuovere manualmente risultati per un prodotto iniziale:</span><span class="sxs-lookup"><span data-stu-id="0ed31-143">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="0ed31-144">Selezionare il **Prodotto iniziale**.</span><span class="sxs-lookup"><span data-stu-id="0ed31-144">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="0ed31-145">Sotto la colonna **Prodotto**, cercare un prodotto per **Nome** o **Numero prodotto**
![Esempio di ricerca di un prodotto nell'elenco Spesso acquistati insieme](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="0ed31-145">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="0ed31-146">Sotto la colonna **Tipo di riga**, selezionare una delle due seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="0ed31-146">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="0ed31-147">**Includi** - Aggiunge un prodotto all'elenco</span><span class="sxs-lookup"><span data-stu-id="0ed31-147">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="0ed31-148">**Escludi** - Rimuove un prodotto dall'elenco</span><span class="sxs-lookup"><span data-stu-id="0ed31-148">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="0ed31-149">![Esempio di inclusione o esclusione di un prodotto nell'elenco Spesso acquistati insieme](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="0ed31-149">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="0ed31-150">Per rimuovere prodotti dalla tabella: selezionare la riga da rimuovere e selezionare Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="0ed31-150">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="0ed31-151">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0ed31-151">Additional resources</span></span>

[<span data-ttu-id="0ed31-152">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="0ed31-152">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="0ed31-153">Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0ed31-153">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="0ed31-154">Abilita suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="0ed31-154">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="0ed31-155">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="0ed31-155">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="0ed31-156">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="0ed31-156">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="0ed31-157">Abilitare gli elementi consigliati "acquista prodotti simili"</span><span class="sxs-lookup"><span data-stu-id="0ed31-157">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="0ed31-158">Aggiungere suggerimenti sul prodotto nel POS</span><span class="sxs-lookup"><span data-stu-id="0ed31-158">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="0ed31-159">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="0ed31-159">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="0ed31-160">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="0ed31-160">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="0ed31-161">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="0ed31-161">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="0ed31-162">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="0ed31-162">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]