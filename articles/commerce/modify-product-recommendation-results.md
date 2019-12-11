---
title: Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML
description: In questo argomento viene descritto come gestire i risultati dei suggerimenti sul prodotto basati su AI-ML (intelligenza artificiale-machine learning) all'azienda.
author: bebeale
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
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 669b056c38614c8ac9be2d7b244a0ab0c73bc9f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770072"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="40d44-103">Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML</span><span class="sxs-lookup"><span data-stu-id="40d44-103">Manage AI-ML-based product recommendation results</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="40d44-104">In questo argomento viene descritto come gestire i risultati dei suggerimenti sul prodotto basati su AI-ML (intelligenza artificiale-machine learning) all'azienda.</span><span class="sxs-lookup"><span data-stu-id="40d44-104">This topic explains how to tailor product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="40d44-105">Dopo l'abilitazione delle raccomandazioni sul prodotto, le impostazioni predefinite diventano effettive. Questi parametri possono rivelarsi utili per numerose esigenze.</span><span class="sxs-lookup"><span data-stu-id="40d44-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="40d44-106">Si consiglia di spendere un po' di tempo per determinare se i risultati corrispondono all'andamento di vendita dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="40d44-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="40d44-107">Suggeriamo di valutare i risultati per alcuni giorni prima di modificare i parametri come necessario e di eseguire di nuovo dei test.</span><span class="sxs-lookup"><span data-stu-id="40d44-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="40d44-108">Informazioni sui parametri degli elenchi di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="40d44-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="40d44-109">Prima di modificare i parametri, è necessario comprendere come questi influiscono sui risultati.</span><span class="sxs-lookup"><span data-stu-id="40d44-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="40d44-110">Elenco di prodotti Di tendenza</span><span class="sxs-lookup"><span data-stu-id="40d44-110">Trending product list</span></span>

<span data-ttu-id="40d44-111">L'elenco di prodotti **Di tendenza** include due parametri che possono essere modificati: ![esempio di parametri predefiniti dell'elenco Di tendenza](./media/exampletrendingparameters.png)</span><span class="sxs-lookup"><span data-stu-id="40d44-111">The **Trending** product list has two parameters that can be changed: ![Example Trending list default parameters](./media/exampletrendingparameters.png)</span></span>
1. <span data-ttu-id="40d44-112">**Includi nuovi prodotti degli ultimi X giorni** - I prodotti che sono stati aggiunti entro il numero di giorni specificato prima della data corrente possono essere utilizzati per selezionare candidati prodotto.</span><span class="sxs-lookup"><span data-stu-id="40d44-112">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="40d44-113">Il valore predefinito nell'immagine suggerisce che i prodotti aggiunti fino a 180 giorni prima della data corrente possono essere utilizzati nell'elenco di prodotti Di tendenza.</span><span class="sxs-lookup"><span data-stu-id="40d44-113">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="40d44-114">**Includi vendite degli ultimi X giorni** - Le transazioni di vendita verificatesi entro il numero di giorni specificato prima della data corrente possono essere utilizzati per ordinare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="40d44-114">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="40d44-115">Il valore predefinito di cui sopra suggerisce che tutti gli acquisti di un prodotto effettuati negli ultimi 30 giorni sono utilizzati per determinare la posizione del prodotto nell'elenco di prodotti Di tendenza.</span><span class="sxs-lookup"><span data-stu-id="40d44-115">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="40d44-116">Elenco di prodotti Più venduti</span><span class="sxs-lookup"><span data-stu-id="40d44-116">Best selling product list</span></span>

<span data-ttu-id="40d44-117">A seconda dell'attività commerciale, l'elenco Più venduti può avere risultati differenti rispetto all'elenco Di tendenza, anche se entrambi utilizzano dati transazione per ordinare prodotti.</span><span class="sxs-lookup"><span data-stu-id="40d44-117">Depending on your business, Best selling can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="40d44-118">Poiché l'elenco Più venduti non ha alcun limite basato sulla data di assortimento, questo elenco può ancora evidenziare prodotti più vecchi molto popolari che potrebbero essere stati rimossi dall'elenco Di tendenza.</span><span class="sxs-lookup"><span data-stu-id="40d44-118">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="40d44-119">L'elenco di prodotti **Più venduti** include un parametro che può essere modificato:</span><span class="sxs-lookup"><span data-stu-id="40d44-119">The **Best selling** product list has one parameter that can be changed:</span></span>

![Esempio di parametro predefinito dell'elenco Più venduti](./media/examplebestsellingparameters.PNG)
1. <span data-ttu-id="40d44-121">**Includi vendite degli ultimi X giorni** - Le transazioni di vendita verificatesi entro il numero di giorni specificato prima della data corrente possono essere utilizzati per ordinare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="40d44-121">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="40d44-122">Il valore predefinito di cui sopra suggerisce che tutti gli acquisti di un prodotto effettuati negli ultimi 30 giorni sono utilizzati per determinare il posizionamento del prodotto nell'elenco di prodotti Più venduti.</span><span class="sxs-lookup"><span data-stu-id="40d44-122">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="40d44-123">Aggiungere o rimuovere manualmente prodotti negli elenchi di suggerimenti</span><span class="sxs-lookup"><span data-stu-id="40d44-123">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling"></a><span data-ttu-id="40d44-124">Per l'elenco Novità, Di tendenza o Più venduti</span><span class="sxs-lookup"><span data-stu-id="40d44-124">For New, Trending, or Best selling</span></span>

1.  <span data-ttu-id="40d44-125">Andare a **Vendita al dettaglio** > **Suggerimenti sul prodotto** > **Parametri suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="40d44-125">Go to **Retail** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="40d44-126">Nell'elenco dei parametri di vendita al dettaglio condivisi, selezionare **Elenchi di suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="40d44-126">In the list of retail shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="40d44-127">Selezionare l'elenco per il quale si intende aggiungere o rimuovere prodotti.</span><span class="sxs-lookup"><span data-stu-id="40d44-127">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="40d44-128">Per aggiungere prodotti alla tabella, selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="40d44-128">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="40d44-129">Nella colonna Prodotto, cercare un prodotto per **Nome** o **Numero prodotto**.
![Esempio di ricerca di un prodotto nell'elenco di prodotti Novità](./media/examplenewlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="40d44-129">Under the Product column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the New product list](./media/examplenewlistconfiguration1.png)</span></span>
1.  <span data-ttu-id="40d44-130">Sotto la colonna Tipo di riga, selezionare una delle due seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="40d44-130">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="40d44-131">**Includi** - Aggiunge un prodotto all'elenco</span><span class="sxs-lookup"><span data-stu-id="40d44-131">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="40d44-132">**Escludi** - Rimuove un prodotto dall'elenco ![Esempio di inclusione o esclusione di un prodotto dell'elenco di prodotti Novità](./media/examplenewlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="40d44-132">**Exclude** – removes a product from appearing in the list ![Example of Including or Excluding a product from the New product list](./media/examplenewlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="40d44-133">La modifica di **Ordine di visualizzazione** cambierà l'ordine di visualizzazione dei prodotti contrassegnati con **includi** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="40d44-133">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="40d44-134">Se due prodotti hanno lo stesso valore di **ordine di visualizzazione**, l'ordine finale di quei due risultati può differire dal back office.</span><span class="sxs-lookup"><span data-stu-id="40d44-134">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="40d44-135">Per rimuovere prodotti dalla tabella: selezionare la riga da rimuovere e selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="40d44-135">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="40d44-136">Per gli elenchi Alle persone piace anche o Spesso acquistati insieme</span><span class="sxs-lookup"><span data-stu-id="40d44-136">For People also like or Frequently bought together lists</span></span>

<span data-ttu-id="40d44-137">Nel contesto degli elenchi **Alle persone piace anche** o **Spesso acquistati insieme**, il machine learning è utilizzato per analizzare criteri di acquisto dei consumatori allo scopo di consigliare prodotti correlati acquistati spesso insieme a un prodotto iniziale univoco.</span><span class="sxs-lookup"><span data-stu-id="40d44-137">In the context of **Frequently bought together** or **People also like** lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="40d44-138">Un **prodotto iniziale** è il prodotto per il quale si desidera generare i risultati.</span><span class="sxs-lookup"><span data-stu-id="40d44-138">A **seed product** is the product you want to generate results for.</span></span> <span data-ttu-id="40d44-139">Nel contesto della modifica manuale degli elenchi di suggerimenti, si aggiungono o rimuovono risultati per questo prodotto.</span><span class="sxs-lookup"><span data-stu-id="40d44-139">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="40d44-140">Seguire questi passaggi per aggiungere o rimuovere manualmente risultati per un prodotto iniziale:</span><span class="sxs-lookup"><span data-stu-id="40d44-140">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="40d44-141">Selezionare il **Prodotto iniziale**.</span><span class="sxs-lookup"><span data-stu-id="40d44-141">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="40d44-142">Sotto la colonna **Prodotto**, cercare un prodotto per **Nome** o **Numero prodotto**
![Esempio di ricerca di un prodotto nell'elenco Spesso acquistati insieme](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="40d44-142">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="40d44-143">Sotto la colonna **Tipo di riga**, selezionare una delle due seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="40d44-143">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="40d44-144">**Includi** - Aggiunge un prodotto all'elenco</span><span class="sxs-lookup"><span data-stu-id="40d44-144">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="40d44-145">**Escludi** - Rimuove un prodotto dall'elenco</span><span class="sxs-lookup"><span data-stu-id="40d44-145">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="40d44-146">![Esempio di inclusione o esclusione di un prodotto nell'elenco Spesso acquistati insieme](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="40d44-146">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="40d44-147">Per rimuovere prodotti dalla tabella: selezionare la riga da rimuovere e selezionare Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="40d44-147">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="40d44-148">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="40d44-148">Additional resources</span></span>

[<span data-ttu-id="40d44-149">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="40d44-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="40d44-150">Abilitare suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="40d44-150">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="40d44-151">Aggiungere elenchi di suggerimenti sul prodotto alle pagine</span><span class="sxs-lookup"><span data-stu-id="40d44-151">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
