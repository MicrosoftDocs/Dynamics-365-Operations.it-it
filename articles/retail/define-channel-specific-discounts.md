---
title: Definire gli sconti specifici del canale
description: "I rivenditori fissano spesso sconti diversi in canali diversi. In questo argomento vengono esaminati i concetti che è necessario conoscere per creare uno sconto per un canale specifico."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 34039b298e8994e50a7c06ef034698e8c1264389
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="define-channel-specific-discounts"></a><span data-ttu-id="c3bd3-104">Definire gli sconti specifici del canale</span><span class="sxs-lookup"><span data-stu-id="c3bd3-104">Define channel-specific discounts</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="c3bd3-105">I rivenditori fissano spesso sconti diversi in canali diversi.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-105">Retailers often set different discounts in different channels.</span></span> <span data-ttu-id="c3bd3-106">In questo argomento vengono esaminati i concetti che è necessario conoscere per creare uno sconto per un canale specifico.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-106">This topic reviews the concepts you need to know to create a discount for a specific channel.</span></span> 

<a name="channel-specific-discounts"></a><span data-ttu-id="c3bd3-107">Sconti specifici del canale</span><span class="sxs-lookup"><span data-stu-id="c3bd3-107">Channel-specific discounts</span></span>
--------------------------

<span data-ttu-id="c3bd3-108">I rivenditori offrono spesso sconti diversi in canali diversi.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-108">Retailers often offer different discounts in different channels.</span></span> <span data-ttu-id="c3bd3-109">Questa strategia può servire per andare incontro alle condizioni di mercato locali o per gestire i rivenditori concorrenti.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-109">This is may be done to address local market conditions or to deal with competing retailers.</span></span>

<span data-ttu-id="c3bd3-110">Microsoft Dynamics 365 for Retail utilizza i gruppi di prezzi per definire gli sconti specifici del canale.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-110">Microsoft Dynamics 365 for Retail uses price groups to define channel-specific discounts.</span></span> <span data-ttu-id="c3bd3-111">I gruppi di prezzi possono essere assegnati a una o più delle entità seguenti: canali, cataloghi, affiliazioni e programmi fedeltà.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-111">Price groups can be assigned to one or more of the following entities: channels, catalogs, affiliations, and loyalty programs.</span></span> <span data-ttu-id="c3bd3-112">In questo articolo vengono illustrati i canali, ma gli stessi concetti si applicano per gli sconti di catalogo, gli sconti di affiliazioni e gli sconti fedeltà.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-112">This article discusses channels, but the same concepts apply to catalog discounts, affiliations discounts, and loyalty discounts.</span></span>

## <a name="price-groups"></a><span data-ttu-id="c3bd3-113">Gruppi prezzi</span><span class="sxs-lookup"><span data-stu-id="c3bd3-113">Price groups</span></span>

<span data-ttu-id="c3bd3-114">[![Gruppi prezzi](./media/price-groups-1024x608.png)](./media/price-groups.png)</span><span class="sxs-lookup"><span data-stu-id="c3bd3-114">[![Price groups](./media/price-groups-1024x608.png)](./media/price-groups.png)</span></span>

<span data-ttu-id="c3bd3-115">Il diagramma precedente illustra la relazione tra le entità che possono essere presenti in una transazione (canale, catalogo, affiliazione, cliente, carta fedeltà) e i vari tipi di sconto che possono essere configurati.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-115">The diagram above illustrates the relationship between entities that may be on a transaction (channel, catalog, affiliation, customer, loyalty card) and the various discount types that can be configured.</span></span> <span data-ttu-id="c3bd3-116">Tutte le transazioni si verificano in un canale, pertanto il canale è sicuramente presente in una transazione.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-116">All transactions occur in a channel, so the channel is guaranteed to be present on a transaction.</span></span> <span data-ttu-id="c3bd3-117">Le entità rimanenti sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-117">The remaining entities are optional.</span></span> <span data-ttu-id="c3bd3-118">In ogni pagina anagrafica è presente un collegamento a una pagina correlata dei gruppi di prezzi in cui è possibile visualizzare e aggiungere i gruppi di prezzi in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-118">On each master data pages there is a link to a related price groups page where you can view and add price groups as needed.</span></span> <span data-ttu-id="c3bd3-119">Un gruppo di prezzi viene utilizzato per collegare quattro diversi tipi di entità agli sconti, le rettifiche prezzo e gli accordi commerciali.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-119">A price group is used to relate four different types of entities to discounts, price adjustments, and trade agreements.</span></span> <span data-ttu-id="c3bd3-120">È consigliabile progettare una strategia sui nomi da assegnare ai gruppi di prezzi per tenerli organizzati.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-120">We recommend that you plan a strategy for how you will name your price groups to keep them organized.</span></span> <span data-ttu-id="c3bd3-121">Un'opzione consiste nell'utilizzare un prefisso o un suffisso numerico o letterale per distinguere i diversi tipi.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-121">One option would be to use a letter or number prefix or suffix to distinguish between the different types.</span></span> <span data-ttu-id="c3bd3-122">Ad esempio, 1-xxxxx per gruppi di prezzi del canale e 2-xxxxx per gruppi di prezzi del catalogo.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-122">For example, 1-xxxxx for channel price groups and 2-xxxxx for catalog price groups.</span></span> <span data-ttu-id="c3bd3-123">Sono disponibili quattro pagine di richiesta che si concentrano in ciascuna delle entità al dettaglio che possono essere associate.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-123">There are four inquiry pages that focus on each of the retail entities that can have discounts associated to them.</span></span>

-   <span data-ttu-id="c3bd3-124">**Gruppi di prezzi canale di vendita al dettaglio**- In questa pagina viene visualizzato un elenco dei canali e degli sconti collegati e per ogni gruppo prezzi.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-124">**Retail channel price groups** - This page shows a list of channels and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="c3bd3-125">**Gruppi prezzi catalogo**- In questa pagina viene visualizzato un elenco dei cataloghi e degli sconti collegati e per ogni gruppo prezzi.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-125">**Catalog price groups** - This page shows a list of catalogs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="c3bd3-126">**Gruppi di prezzi programma fedeltà**- In questa pagina viene visualizzato un elenco dei programma fedeltà e degli sconti collegati e per ogni gruppo prezzi.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-126">**Loyalty price groups** - This page shows a list of loyalty programs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="c3bd3-127">**Gruppi di prezzi rapporti**- In questa pagina viene visualizzato un elenco dei rapporti e degli sconti collegati e per ogni gruppo prezzi.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-127">**Affiliation price groups** - This page shows a list of affiliations and discounts linked together for each price group.</span></span>

## <a name="example-channel-discount-set-up"></a><span data-ttu-id="c3bd3-128">Impostazione di esempio di sconto di canale</span><span class="sxs-lookup"><span data-stu-id="c3bd3-128">Example channel discount set up</span></span>
<span data-ttu-id="c3bd3-129">Nel seguente esempio sono illustrate le attività in questione nell'impostazione dello sconto di canale.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-129">The following example illustrates the tasks involved in setting up a channel discount.</span></span>

1.  <span data-ttu-id="c3bd3-130">Per questo esempio, si ha un canale **Houston** e si crea un nuovo sconto denominato **Di nuovo a scuola.**</span><span class="sxs-lookup"><span data-stu-id="c3bd3-130">For this example, you have a channel called **Houston**, and you're going to create a new discount called **Back-to-School.**</span></span>
2.  <span data-ttu-id="c3bd3-131">Poiché la strategia di sconto e dei prezzi comprende la possibilità degli sconti di canale, creare sempre un gruppo di prezzi specifico del canale quando si crea un canale.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-131">Because the pricing and discount strategy includes the possibility of channel discounts, you always create a channel-specific price group when you create a channel.</span></span>
3.  <span data-ttu-id="c3bd3-132">Si ha il gruppo di prezzi **Houston-PG** ed è assegnato al canale **Houston**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-132">You have the price group **Houston-PG** and it is assigned to the **Houston** channel.</span></span>
4.  <span data-ttu-id="c3bd3-133">Dopo aver creato il nuovo sconto **Di nuovo a scuola**, è necessario fare clic su **Gruppi prezzi** nella parte superiore della pagina **Sconto**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-133">After you create the new **Back-to-School** discount, you need to click **Price groups** on the top of the **Discount** page.</span></span> <span data-ttu-id="c3bd3-134">Si apre la pagina **Gruppi di prezzo scontati**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-134">The **Discount price groups** page will open.</span></span> <span data-ttu-id="c3bd3-135">Dopodiché, fare clic su **Nuovo** e selezionare il gruppo di prezzi **Houston-PG**.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-135">Next, click **New** and select the **Houston-PG** price group.</span></span>
5.  <span data-ttu-id="c3bd3-136">Ora è possibile attivare lo sconto e spingerlo nel canale.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-136">Now you can enable the discount and push it to the channel.</span></span>



<a name="see-also"></a><span data-ttu-id="c3bd3-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3bd3-137">See also</span></span>
--------

[<span data-ttu-id="c3bd3-138">Rettifiche prezzi e sconti</span><span class="sxs-lookup"><span data-stu-id="c3bd3-138">Price adjustments and discounts</span></span>](price-adjustments-discounts.md)




