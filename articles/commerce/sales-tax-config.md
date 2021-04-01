---
title: Configurare l'IVA per gli ordini online
description: Questo argomento fornisce una panoramica della selezione della fascia IVA per diversi tipi di ordine online in Dynamics 365 Commerce.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 36dd3e8a3d47f02eed5b9c8bb79d773d98069376
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254843"
---
# <a name="configure-sales-tax-for-online-orders"></a><span data-ttu-id="d57ae-103">Configurare l'IVA per gli ordini online</span><span class="sxs-lookup"><span data-stu-id="d57ae-103">Configure sales tax for online orders</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d57ae-104">Questo argomento fornisce una panoramica della selezione della fascia IVA per diversi tipi di ordine online.</span><span class="sxs-lookup"><span data-stu-id="d57ae-104">This topic provides an overview of sales tax group selection for different online order types.</span></span> 

<span data-ttu-id="d57ae-105">Il canale di e-commerce potrebbe voler supportare opzioni come la consegna o il ritiro per gli ordini online.</span><span class="sxs-lookup"><span data-stu-id="d57ae-105">Your e-commerce channel may want to support options like delivery or pickup for online orders.</span></span> <span data-ttu-id="d57ae-106">L'applicabilità dell'IVA si basa sull'opzione selezionata dagli utenti online.</span><span class="sxs-lookup"><span data-stu-id="d57ae-106">The sales tax applicability is based on the option selected by your online users.</span></span> <span data-ttu-id="d57ae-107">Quando un cliente del sito sceglie di acquistare un articolo online e lo fa spedire a un indirizzo, l'IVA viene determinata in base all'impostazione del gruppo fiscale dell'indirizzo di spedizione del cliente.</span><span class="sxs-lookup"><span data-stu-id="d57ae-107">When a site customer chooses to buy an item online and gets it shipped to an address, the sales tax is determined based on the customer's shipping address tax group setting.</span></span> <span data-ttu-id="d57ae-108">Quando un cliente sceglie di ritirare un articolo acquistato in un negozio, l'IVA viene determinata in base all'impostazione del gruppo fiscale del negozio di ritiro.</span><span class="sxs-lookup"><span data-stu-id="d57ae-108">When a customer opts to pick up a purchased item at a store, the sales tax is determined based on the pickup store's tax group setting.</span></span> 

## <a name="orders-shipped-to-a-customer-address"></a><span data-ttu-id="d57ae-109">Ordini spediti a un indirizzo del cliente</span><span class="sxs-lookup"><span data-stu-id="d57ae-109">Orders shipped to a customer address</span></span> 

<span data-ttu-id="d57ae-110">In generale, le tasse per gli ordini online spediti agli indirizzi dei clienti sono definite dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="d57ae-110">In general, taxes for online orders that ship to customer addresses are defined by the destination.</span></span> <span data-ttu-id="d57ae-111">Ogni fascia IVA ha una configurazione fiscale basata sulla destinazione di vendita al dettaglio in cui l'azienda può definire i dettagli della destinazione come provincia/regione, stato, contea e città in una forma gerarchica.</span><span class="sxs-lookup"><span data-stu-id="d57ae-111">Every sales tax group has a retail destination-based tax configuration in which your business can define destination details such as county/region, state, county, and city in a hierarchical form.</span></span> <span data-ttu-id="d57ae-112">Quando viene effettuato un ordine online, il motore fiscale di Commerce utilizza l'indirizzo di consegna di ogni voce dell'ordine e trova le fasce IVA con criteri fiscali basati sulla destinazione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="d57ae-112">When an online order is placed, the Commerce tax engine uses the delivery address of every line item in the order, and finds sales tax groups with matching destination-based tax criteria.</span></span> <span data-ttu-id="d57ae-113">Ad esempio, per un ordine online con un indirizzo di consegna di una voce a San Francisco, California, il motore fiscale troverà la fascia IVA e il codice IVA per la California, quindi calcolerà di conseguenza l'imposta per ogni articolo di riga.</span><span class="sxs-lookup"><span data-stu-id="d57ae-113">For example, for an online order with a line item delivery address to San Francisco, California, the tax engine will find the sales tax group and sales tax code for California and then calculate tax for each line item accordingly.</span></span>  

## <a name="customer-based-tax-groups"></a><span data-ttu-id="d57ae-114">Gruppi fiscali basati sul cliente</span><span class="sxs-lookup"><span data-stu-id="d57ae-114">Customer-based tax groups</span></span>

<span data-ttu-id="d57ae-115">In Commerce headquarters, ci sono due posizioni in cui sono configurate i gruppi fiscali dei clienti:</span><span class="sxs-lookup"><span data-stu-id="d57ae-115">In Commerce headquarters, there are two places where customer tax groups are configured:</span></span>

- <span data-ttu-id="d57ae-116">**Profilo del cliente**</span><span class="sxs-lookup"><span data-stu-id="d57ae-116">**Customer's profile**</span></span>
- <span data-ttu-id="d57ae-117">**Indirizzo di spedizione del cliente**</span><span class="sxs-lookup"><span data-stu-id="d57ae-117">**Customer's shipping address**</span></span>

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a><span data-ttu-id="d57ae-118">Se il profilo di un cliente ha un gruppo fiscale configurato</span><span class="sxs-lookup"><span data-stu-id="d57ae-118">If a customer's profile has a tax group configured</span></span>

<span data-ttu-id="d57ae-119">Il record del profilo di un cliente in headquarters può avere un gruppo fiscale configurato, tuttavia per gli ordini online il gruppo fiscale configurato nel profilo di un cliente non verrà utilizzato dal motore fiscale.</span><span class="sxs-lookup"><span data-stu-id="d57ae-119">A customer's profile record in headquarters may have a sales tax group configured, however for online orders the sales tax group configured in a customer's profile will not be used by the tax engine.</span></span> 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a><span data-ttu-id="d57ae-120">Se l'indirizzo di spedizione di un cliente ha un gruppo fiscale configurato</span><span class="sxs-lookup"><span data-stu-id="d57ae-120">If a customer's shipping address has a tax group configured</span></span>

<span data-ttu-id="d57ae-121">Se il record dell'indirizzo di spedizione di un cliente ha un gruppo fiscale configurato e un ordine online (o una voce) viene spedito all'indirizzo di spedizione del cliente, il gruppo fiscale configurato nel record dell'indirizzo del cliente verrà utilizzato dal motore fiscale per i calcoli fiscali.</span><span class="sxs-lookup"><span data-stu-id="d57ae-121">If a customer's shipping address record has a tax group configured and an online order (or line item) is shipped to the customer's shipping address, the tax group configured in the customer's address record will be used by the tax engine for tax calculations.</span></span>

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a><span data-ttu-id="d57ae-122">Configurare un gruppo fiscale per un record di indirizzo di spedizione di un cliente</span><span class="sxs-lookup"><span data-stu-id="d57ae-122">Configure a tax group for a customer's shipping address record</span></span>

<span data-ttu-id="d57ae-123">Per configurare un gruppo fiscale per il record dell'indirizzo di spedizione di un cliente in Commerce headquarters seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d57ae-123">To configure a tax group for a customer's shipping address record in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="d57ae-124">Andare a **Tutti i clienti**, quindi selezionare il cliente desiderato.</span><span class="sxs-lookup"><span data-stu-id="d57ae-124">Go to **All customers**, and then select the desired customer.</span></span> 
1. <span data-ttu-id="d57ae-125">Nella Scheda dettaglio **Indirizzi**, selezionare l'indirizzo desiderato, quindi selezionare **Altre opzioni \> Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="d57ae-125">On the **Addresses** FastTab, select the desired address, and then select **More options \> Advanced**.</span></span> 
1. <span data-ttu-id="d57ae-126">Nella scheda **Generale** della pagina **Gestisci indirizzi** impostare il valore dell'IVA secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="d57ae-126">Under the **General** tab on the **Manage addresses** page, set the sales tax value as needed.</span></span>

> [!NOTE]
> <span data-ttu-id="d57ae-127">Il gruppo fiscale viene definito utilizzando l'indirizzo di consegna della riga dell'ordine e le imposte basate sulla destinazione vengono configurate nel gruppo fiscale stesso.</span><span class="sxs-lookup"><span data-stu-id="d57ae-127">The tax group is defined using the delivery address of the order line and the destination-based taxes are configured at the tax group itself.</span></span> <span data-ttu-id="d57ae-128">Per ulteriori informazioni, vedere [Impostare le imposte per i punti vendita online in base alla destinazione](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="d57ae-128">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="order-pickup-in-store"></a><span data-ttu-id="d57ae-129">Ritiro dell'ordine nel punto vendita</span><span class="sxs-lookup"><span data-stu-id="d57ae-129">Order pickup in store</span></span>

<span data-ttu-id="d57ae-130">Per le righe ordine con ritiro nel punto vendita o al piano strada specificato, verrà applicato il gruppo fiscale del punto vendita selezionato.</span><span class="sxs-lookup"><span data-stu-id="d57ae-130">For order lines with pickup in store or curbside pickup specified, the tax group from the selected pickup store will be applied.</span></span> <span data-ttu-id="d57ae-131">Per dettagli su come configurare il gruppo fiscale per un determinato punto vendita, vedere [Impostare altre opzioni fiscali per i punti vendita](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="d57ae-131">For details about how to configure the tax group for a given store, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

> [!NOTE]
> <span data-ttu-id="d57ae-132">Quando una riga ordine viene ritirata presso un negozio, le impostazioni fiscali dell'indirizzo del cliente (se configurate) verranno ignorate dal motore fiscale e verrà applicata la configurazione fiscale del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="d57ae-132">When an order line is picked up at a store, a customer's address tax settings (if set up) will be ignored by the tax engine and the pickup store's tax configuration will be applied.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="d57ae-133">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d57ae-133">Additional resources</span></span>

[<span data-ttu-id="d57ae-134">Panoramica dell'IVA</span><span class="sxs-lookup"><span data-stu-id="d57ae-134">Sales tax overview</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="d57ae-135">Metodi di calcolo IVA nel campo Origine</span><span class="sxs-lookup"><span data-stu-id="d57ae-135">Sales tax calculation methods in the Origin field</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="d57ae-136">Assegnazione e sostituzioni IVA</span><span class="sxs-lookup"><span data-stu-id="d57ae-136">Sales tax assignment and overrides</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="d57ae-137">Opzioni importo totale e intervallo per i codici IVA</span><span class="sxs-lookup"><span data-stu-id="d57ae-137">Whole amount and Interval calculation options for sales tax codes</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="d57ae-138">Calcolo dell'esenzione fiscale</span><span class="sxs-lookup"><span data-stu-id="d57ae-138">Calculation of tax exemption</span></span>](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]