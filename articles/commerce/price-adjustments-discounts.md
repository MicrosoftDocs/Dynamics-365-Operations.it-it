---
title: Rettifiche prezzi e sconti
description: Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Dynamics 365 Commerce.
author: scott-tucker
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 0c2adaa5cd935d5b593bfbb3215d3466fcafab7b
ms.sourcegitcommit: 1d74636bf9db5fb33e998322899504b709b4f89f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "4584317"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="cf2b1-103">Rettifiche prezzi e sconti</span><span class="sxs-lookup"><span data-stu-id="cf2b1-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cf2b1-104">Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-104">This article provides information about price adjustments and discounts in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="cf2b1-105">In Commerce, è possibile apportare rettifiche prezzo a prodotti e è inoltre possibile impostare gli sconti applicabili a una voce o a una transazione nel POS, in un ordine cliente del call center, o in un ordine online.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-105">In Commerce, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="cf2b1-106">Sia le rettifiche prezzo che gli sconti sono collegati a gruppi di prezzi.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="cf2b1-107">Per entrambe le rettifiche prezzo e sconti, è possibile specificare una singola data di inizio e la data di fine o un periodo di riproduzione, un codice di sconto e alcuni attributi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> 

<span data-ttu-id="cf2b1-108">Le rettifiche prezzo e gli sconti possono essere applicati ai prodotti, alle varianti o alle categorie.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="cf2b1-109">Se più di uno sconto viene applicato a un prodotto, un cliente può ricevere uno degli sconti o uno sconto combinato, a seconda della configurazione dello sconto.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="cf2b1-110">In Commerce viene automaticamente applicato lo sconto o la combinazione di sconti che forniscono il migliore prezzo al cliente.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-110">Commerce automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="cf2b1-111">Quando si imposta una rettifica di prezzo o uno sconto, assicurarsi di confermare che i gruppi di prezzi vengono assegnati ai canali, ai cataloghi, le affiliazioni, o i programmi corretti di fedeltà che si desidera lo sconto da applicare.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="cf2b1-112">Inoltre, se si desidera generare automaticamente l'ID dello sconto, è possibile impostare le sequenze numeriche nel modulo **Parametri di commercio** prima di definire un nuovo sconto o una rettifica prezzo o sconto.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Commerce parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="cf2b1-113">È possibile eliminare una rettifica prezzo o uno sconto.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="cf2b1-114">Tuttavia, le informazioni statistiche vengono perse.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="cf2b1-115">Tipi di sconti</span><span class="sxs-lookup"><span data-stu-id="cf2b1-115">Types of discounts</span></span>

<span data-ttu-id="cf2b1-116">Sono ora disponibili molti tipi di sconti:</span><span class="sxs-lookup"><span data-stu-id="cf2b1-116">There are many types of discounts:</span></span>

- <span data-ttu-id="cf2b1-117">**Sconto semplice**: una singola percentuale o importo.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="cf2b1-118">**Sconto la quantità** Uno sconto applicato quando due o più prodotti vengono acquistati.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="cf2b1-119">**Sconto gamma** - Viene applicato uno sconto quando si acquista una combinazione specifica di prodotti.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="cf2b1-120">**Sconto della soglia** - Uno sconto applicato quando il totale della transazione è più della quantità specificata.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>
- <span data-ttu-id="cf2b1-121">**Sconti basati sui metodi di pagamento** - Uno sconto che viene applicato quando il totale della transazione è superiore a un importo specificato e per il pagamento viene utilizzato un tipo di pagamento specifico (ad esempio, contanti, carta di credito o di debito).</span><span class="sxs-lookup"><span data-stu-id="cf2b1-121">**Tender-based discount** – A discount that is applied when the transaction total is more than a specified amount and a specific payment type (for example, cash, credit, or debit card) is used for payment.</span></span>
- <span data-ttu-id="cf2b1-122">**Sconto sulla spedizione** - Uno sconto che viene applicato quando il totale della transazione è superiore a un importo specificato e una modalità di consegna specifica (ad esempio, spedizione in due giorni o spedizione notturna) viene utilizzata per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-122">**Shipping discount** – A discount that is applied when the transaction total is more than a specified amount and a specific mode of delivery (for example, two day shipping or overnight shipping) is used on the order.</span></span>

<span data-ttu-id="cf2b1-123">Sia le rettifiche prezzo che gli sconti sono collegati a gruppi di prezzi.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-123">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="cf2b1-124">I gruppi di prezzi possono quindi essere associati ai canali, i cataloghi, le affiliazioni e piani di fedeltà.</span><span class="sxs-lookup"><span data-stu-id="cf2b1-124">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>
