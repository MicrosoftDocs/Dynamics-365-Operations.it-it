---
title: Prodotti resi e di vendita non inclusi in un assortimento
description: "Con 365 Dynamics for Retail è possibile vendere e restituire i prodotti fuori dagli assortimenti."
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 418ee6136a5a02d343828d8eb33b1e37325e2918
ms.contentlocale: it-it
ms.lasthandoff: 01/19/2018

---

# <a name="sell-and-return-products-outside-of-an-assortment"></a><span data-ttu-id="4e228-103">Prodotti resi e di vendita non inclusi in un assortimento</span><span class="sxs-lookup"><span data-stu-id="4e228-103">Sell and return products outside of an assortment</span></span>
<span data-ttu-id="4e228-104">Uno scenario comune per il rivenditore è la vendita di prodotti ai clienti o l'accettazione di resi dai clienti anche se non hanno i prodotti specifici nel punto vendita (in altre parole i prodotti non sono un assortimento del punto vendita).</span><span class="sxs-lookup"><span data-stu-id="4e228-104">A common scenario for any retailer is to sell products to their customers or accept returns from their customers even if they don’t carry the specific products in their store (in other words, the products are not assorted to the store).</span></span>
<span data-ttu-id="4e228-105">Di seguito sono riportati alcuni scenari comuni:</span><span class="sxs-lookup"><span data-stu-id="4e228-105">Here are some typical scenarios:</span></span>

+ <span data-ttu-id="4e228-106">Un rivenditore conserva tutti i propri prodotti in un punto vendita specifico.</span><span class="sxs-lookup"><span data-stu-id="4e228-106">A retailer doesn’t carry all its products in a specific store.</span></span> <span data-ttu-id="4e228-107">I prodotti rimanenti sono conservati in magazzino.</span><span class="sxs-lookup"><span data-stu-id="4e228-107">The remaining products are stored in the warehouse.</span></span> <span data-ttu-id="4e228-108">L'associato del punto vendita può assistere il cliente nella ricerca dei prodotti nel magazzino, aggiungerli al carrello e completare la transazione selezionando un metodo di consegna, ad esempio la spedizione dal magazzino a un indirizzo, o lasciare che il cliente prelevi il prodotto dal punto vendita corrente o da un altro punto vendita.</span><span class="sxs-lookup"><span data-stu-id="4e228-108">The store associate can assist the customer by searching or browsing for the products in the warehouse, add them to the cart, and complete the checkout by selecting a delivery method, such as shipping to an address from the warehouse or letting the customer pick up the product from the current store or from another store.</span></span>
+ <span data-ttu-id="4e228-109">Un rivenditore non dispone di prodotti specifici presso il punto vendita o non li ha in scorta presso il punto vendita visitato dal cliente, ma i prodotti sono disponibili in altri punti vendita.</span><span class="sxs-lookup"><span data-stu-id="4e228-109">A retailer doesn’t carry specific products in the store or doesn’t have them in stock at the store the customer visited, but the products are available in other stores.</span></span> <span data-ttu-id="4e228-110">L'associato del punto vendita può assistere il cliente nella ricerca dei prodotti nell'altro punto vendita, aggiungerli al carrello e completare la transazione selezionando un metodo di consegna.</span><span class="sxs-lookup"><span data-stu-id="4e228-110">The store associate can assist the customer by searching or browsing the products in the other store, add them to the cart, and complete the checkout by selecting a delivery method.</span></span>
+ <span data-ttu-id="4e228-111">Un rivenditore possiede numerosi punti vendita vicino o in una città o area specifica e non vuole costringere i clienti a restituire i prodotti allo stesso punto vendita in cui li hanno acquistati.</span><span class="sxs-lookup"><span data-stu-id="4e228-111">A retailer has many stores in and around a specific city or zip code and doesn’t want to force the customers to return products to the same store they were purchased in.</span></span> <span data-ttu-id="4e228-112">I clienti possono invece restituire i prodotti in qualsiasi punto vendita.</span><span class="sxs-lookup"><span data-stu-id="4e228-112">Instead, customers can return products to any store.</span></span>


<span data-ttu-id="4e228-113">Questi scenari comuni sono disponibili per i rivenditori che utilizzano Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="4e228-113">Those common scenarios are available for retailers using Dynamics 365 for Retail.</span></span> <span data-ttu-id="4e228-114">Con Retail è possibile:</span><span class="sxs-lookup"><span data-stu-id="4e228-114">With Retail, you can:</span></span>
+ <span data-ttu-id="4e228-115">Cercare dei prodotti presso altri punti vendita.</span><span class="sxs-lookup"><span data-stu-id="4e228-115">Search or browse products at other stores.</span></span>
+ <span data-ttu-id="4e228-116">Cercare tutti i prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="4e228-116">Search or browse all released products.</span></span>
+ <span data-ttu-id="4e228-117">Creare transazioni cash-and-carry o ordini di cliente.</span><span class="sxs-lookup"><span data-stu-id="4e228-117">Create cash-and-carry transactions or customer orders.</span></span>
+ <span data-ttu-id="4e228-118">Selezionare le opzioni di consegna per gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="4e228-118">Select delivery options for customer orders.</span></span>
+ <span data-ttu-id="4e228-119">Prelevare i prodotti presso il punto vendita corrente o presso un altro punto vendita.</span><span class="sxs-lookup"><span data-stu-id="4e228-119">Pick up products at the current store or another store.</span></span>
+ <span data-ttu-id="4e228-120">Annullare un ordine presso il punto vendita corrente o presso un altro punto vendita.</span><span class="sxs-lookup"><span data-stu-id="4e228-120">Cancel an order at the current store or another store.</span></span>
+ <span data-ttu-id="4e228-121">Restituire un ordine con o senza ricevuta presso il punto vendita corrente o presso un altro punto vendita.</span><span class="sxs-lookup"><span data-stu-id="4e228-121">Return an order with or without the receipt at the current store or another store.</span></span>

