---
title: Rettifiche prezzi e sconti
description: Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Vendita al dettaglio e commercio in Microsoft Dynamics 365 for Retail.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 2168d6e1c994c106ea47b8ddfa8f07867b885d45
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---

# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="944e0-103">Rettifiche prezzi e sconti</span><span class="sxs-lookup"><span data-stu-id="944e0-103">Price adjustments and discounts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="944e0-104">Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Vendita al dettaglio e commercio in Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="944e0-104">This article provides information about price adjustments and discounts in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="944e0-105">In Dynamics 365 for Retail, è possibile apportare rettifiche prezzo a prodotti e è inoltre possibile impostare gli sconti applicabili a una voce o a una transazione nel POS, in un ordine cliente del call center, o in un ordine online.</span><span class="sxs-lookup"><span data-stu-id="944e0-105">In Dynamics 365 for Retail, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="944e0-106">Sia le rettifiche prezzo che gli sconti sono collegati a gruppi di prezzi.</span><span class="sxs-lookup"><span data-stu-id="944e0-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="944e0-107">Per entrambe le rettifiche prezzo e sconti, è possibile specificare una singola data di inizio e la data di fine o un periodo di riproduzione, un codice di sconto e alcuni attributi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="944e0-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> <span data-ttu-id="944e0-108">Le rettifiche prezzo e gli sconti possono essere applicati ai prodotti, alle varianti o alle categorie.</span><span class="sxs-lookup"><span data-stu-id="944e0-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="944e0-109">Se più di uno sconto viene applicato a un prodotto, un cliente può ricevere uno degli sconti o uno sconto combinato, a seconda della configurazione dello sconto.</span><span class="sxs-lookup"><span data-stu-id="944e0-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="944e0-110">In Dynamics 365 for Retail viene automaticamente applicato lo sconto o la combinazione di sconti che forniscono il migliore prezzo al cliente.</span><span class="sxs-lookup"><span data-stu-id="944e0-110">Dynamics 365 for Retail automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="944e0-111">Quando si imposta una rettifica di prezzo o uno sconto, assicurarsi di confermare che i gruppi di prezzi vengono assegnati ai canali, ai cataloghi, le affiliazioni, o i programmi corretti di fedeltà che si desidera lo sconto da applicare.</span><span class="sxs-lookup"><span data-stu-id="944e0-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="944e0-112">Inoltre, se si desidera generare automaticamente l'ID dello sconto, è possibile impostare le sequenze numeriche nel modulo **Parametri vendita al dettaglio** prima di definire un nuovo sconto o una rettifica prezzo o sconto.</span><span class="sxs-lookup"><span data-stu-id="944e0-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Retail parameters** page before you define a new price adjustment or discount.</span></span> <span data-ttu-id="944e0-113">**Nota:** è possibile eliminare una rettifica prezzo o uno sconto.</span><span class="sxs-lookup"><span data-stu-id="944e0-113">**Note:** You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="944e0-114">Tuttavia, le informazioni statistiche vengono perse.</span><span class="sxs-lookup"><span data-stu-id="944e0-114">However, statistical information will be lost.</span></span>

### <a name="types-of-discounts"></a><span data-ttu-id="944e0-115">Tipi di sconti</span><span class="sxs-lookup"><span data-stu-id="944e0-115">Types of discounts</span></span>

<span data-ttu-id="944e0-116">Sono ora disponibili quattro tipi di sconti vendita al dettaglio:</span><span class="sxs-lookup"><span data-stu-id="944e0-116">There are four types of retail discounts:</span></span>

-   <span data-ttu-id="944e0-117">**Sconto semplice**: una singola percentuale o importo.</span><span class="sxs-lookup"><span data-stu-id="944e0-117">**Simple discount** – A single percentage or amount.</span></span>
-   <span data-ttu-id="944e0-118">**Sconto la quantità** Uno sconto applicato quando due o più prodotti vengono acquistati.</span><span class="sxs-lookup"><span data-stu-id="944e0-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
-   <span data-ttu-id="944e0-119">**Sconto gamma** - Viene applicato uno sconto quando si acquista una combinazione specifica di prodotti.</span><span class="sxs-lookup"><span data-stu-id="944e0-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
-   <span data-ttu-id="944e0-120">**Sconto della soglia** - Uno sconto applicato quando il totale della transazione è più della quantità specificata.</span><span class="sxs-lookup"><span data-stu-id="944e0-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>

<span data-ttu-id="944e0-121">Sia le rettifiche prezzo che gli sconti sono collegati a gruppi di prezzi.</span><span class="sxs-lookup"><span data-stu-id="944e0-121">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="944e0-122">I gruppi di prezzi possono quindi essere associati ai canali, i cataloghi, le affiliazioni e piani di fedeltà.</span><span class="sxs-lookup"><span data-stu-id="944e0-122">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>




