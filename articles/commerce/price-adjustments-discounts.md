---
title: Rettifiche prezzi e sconti
description: Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Dynamics 365 Commerce.
author: scott-tucker
ms.date: 06/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 44c03ae0a04d648e788a72d8f6dcc3671c5736c7
ms.sourcegitcommit: 7c9d6be464db058511df9cb6ba162d21dc0554e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "6240944"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="9c7ee-103">Rettifiche prezzi e sconti</span><span class="sxs-lookup"><span data-stu-id="9c7ee-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9c7ee-104">Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-104">This article provides information about price adjustments and discounts in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9c7ee-105">In Commerce, è possibile apportare rettifiche prezzo a prodotti e è inoltre possibile impostare gli sconti applicabili a una voce o a una transazione nel POS, in un ordine cliente del call center, o in un ordine online.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-105">In Commerce, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="9c7ee-106">Sia le rettifiche prezzo che gli sconti sono collegati a gruppi di prezzi.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="9c7ee-107">Per entrambe le rettifiche prezzo e sconti, è possibile specificare una singola data di inizio e la data di fine o un periodo di riproduzione, un codice di sconto e alcuni attributi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> 

<span data-ttu-id="9c7ee-108">Le rettifiche prezzo e gli sconti possono essere applicati ai prodotti, alle varianti o alle categorie.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="9c7ee-109">Se più di uno sconto viene applicato a un prodotto, un cliente può ricevere uno degli sconti o uno sconto combinato, a seconda della configurazione dello sconto.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="9c7ee-110">In Commerce viene automaticamente applicato lo sconto o la combinazione di sconti che forniscono il migliore prezzo al cliente.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-110">Commerce automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="9c7ee-111">Quando si imposta una rettifica di prezzo o uno sconto, assicurarsi di confermare che i gruppi di prezzi vengono assegnati ai canali, ai cataloghi, le affiliazioni, o i programmi corretti di fedeltà che si desidera lo sconto da applicare.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="9c7ee-112">Inoltre, se si desidera generare automaticamente l'ID dello sconto, è possibile impostare le sequenze numeriche nel modulo **Parametri di commercio** prima di definire un nuovo sconto o una rettifica prezzo o sconto.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Commerce parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="9c7ee-113">È possibile eliminare una rettifica prezzo o uno sconto.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="9c7ee-114">Tuttavia, le informazioni statistiche vengono perse.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="9c7ee-115">Tipi di sconti</span><span class="sxs-lookup"><span data-stu-id="9c7ee-115">Types of discounts</span></span>

<span data-ttu-id="9c7ee-116">Sono ora disponibili molti tipi di sconti:</span><span class="sxs-lookup"><span data-stu-id="9c7ee-116">There are many types of discounts:</span></span>

- <span data-ttu-id="9c7ee-117">**Sconto semplice**: una singola percentuale o importo.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="9c7ee-118">**Sconto la quantità** Uno sconto applicato quando due o più prodotti vengono acquistati.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="9c7ee-119">**Sconto gamma** - Viene applicato uno sconto quando si acquista una combinazione specifica di prodotti.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="9c7ee-120">**Sconto della soglia** - Uno sconto applicato quando il totale della transazione è più della quantità specificata.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>
- <span data-ttu-id="9c7ee-121">**Sconti basati sui metodi di pagamento** - Uno sconto che viene applicato quando il totale della transazione è superiore a un importo specificato e per il pagamento viene utilizzato un tipo di pagamento specifico (ad esempio, contanti, carta di credito o di debito).</span><span class="sxs-lookup"><span data-stu-id="9c7ee-121">**Tender-based discount** – A discount that is applied when the transaction total is more than a specified amount and a specific payment type (for example, cash, credit, or debit card) is used for payment.</span></span>
- <span data-ttu-id="9c7ee-122">**Sconto sulla spedizione** - Uno sconto che viene applicato quando il totale della transazione è superiore a un importo specificato e una modalità di consegna specifica (ad esempio, spedizione in due giorni o spedizione notturna) viene utilizzata per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-122">**Shipping discount** – A discount that is applied when the transaction total is more than a specified amount and a specific mode of delivery (for example, two day shipping or overnight shipping) is used on the order.</span></span>

<span data-ttu-id="9c7ee-123">Sia le rettifiche prezzo che gli sconti sono collegati a gruppi di prezzi.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-123">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="9c7ee-124">I gruppi di prezzi possono quindi essere associati ai canali, i cataloghi, le affiliazioni e piani di fedeltà.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-124">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>

> [!NOTE]
> <span data-ttu-id="9c7ee-125">Lo sconto gamma e lo sconto di soglia hanno proprietà denominate rispettivamente "Conteggio prodotti non scontati" e "Conteggio prodotti non scontati verso la soglia".</span><span class="sxs-lookup"><span data-stu-id="9c7ee-125">The mix and match discount and the threshold discount have properties named "Count non-discountable products" and "Count non-discountable products towards threshold", respectively.</span></span> <span data-ttu-id="9c7ee-126">Se queste proprietà sono abilitate, un articolo che non è idoneo per alcuno sconto può comunque contribuire a qualificare una transazione per lo sconto, ma l'articolo non idoneo non riceverà lo sconto.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-126">If these properties are enabled, an item that is not eligible for any discount can still help qualify a transaction for the discount, but the ineligible item will not get the discount.</span></span> 
> 
> <span data-ttu-id="9c7ee-127">Ad esempio, se si crea uno sconto di gamma con due righe, A e B, in cui un cliente dovrebbe ottenere uno sconto del 10% su entrambi gli articoli, ma l'articolo A ha la configurazione "Impedisci tutti gli sconti" selezionata, in genere ciò impedirà all'articolo A di essere incluso nello sconto.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-127">For example, if you create a mix and match discount with two lines, A and B, where a customer should get 10% off on both items, but item A has the configuration "Prevent all discounts" checked, then this would typically stop item A from being included in the discount.</span></span> <span data-ttu-id="9c7ee-128">Tuttavia, se la proprietà "Conteggio prodotti non scontati" è abilitata, l'articolo A può essere utilizzato per l'idoneità per lo sconto di gamma, ma lo sconto del 10% verrà applicato solo all'articolo B. Una logica simile si applica allo sconto di soglia.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-128">However, if the "Count non-discountable products" property is enabled, then item A can be used to qualify for the mix and match discount, but the 10% discount will only be applied to item B. Similar logic applies to the threshold discount.</span></span> 
>
> <span data-ttu-id="9c7ee-129">Tuttavia, la proprietà "Conteggio prodotti non scontati verso la soglia" ha una funzionalità aggiuntiva rispetto alla proprietà "Conteggio prodotti non scontati" degli sconti di gamma.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-129">However, the property "Count non-discountable products towards threshold" has an additional capability when compared to the "Count non-discountable products" property of the mix and match discounts.</span></span> <span data-ttu-id="9c7ee-130">Se lo sconto di soglia è abilitato e c'è un articolo che ha uno sconto esistente che impedirebbe all'articolo di ottenere altri sconti, il prezzo pagato per questo articolo sarà idoneo per il raggiungimento della soglia, ma questo articolo non riceverà l'ulteriore sconto.</span><span class="sxs-lookup"><span data-stu-id="9c7ee-130">If the threshold discount is enabled, and if there is an item that has an existing discount which would prevent the item from any other discounts, then  the price paid for this item would qualify towards meeting the threshold, but this item will not get the additional discount.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
