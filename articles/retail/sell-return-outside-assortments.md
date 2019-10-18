---
title: Vendere e restituire prodotti che non fanno parte dell'assortimento di un punto vendita
description: Con Dynamics 365 Retail è possibile vendere e restituire i prodotti fuori dagli assortimenti.
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ae6bac983ddb4d4a217fe83c8f68c5a87ccd6a47
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024939"
---
# <a name="sell-and-return-products-that-arent-part-of-a-stores-assortment"></a><span data-ttu-id="b4610-103">Vendere e restituire prodotti che non fanno parte dell'assortimento di un punto vendita</span><span class="sxs-lookup"><span data-stu-id="b4610-103">Sell and return products that aren't part of a store's assortment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b4610-104">Uno scenario comune per il rivenditore è la vendita di prodotti ai clienti o l'accettazione di resi dai clienti anche se non hanno i prodotti specifici nel punto vendita (in altre parole i prodotti non sono un assortimento del punto vendita).</span><span class="sxs-lookup"><span data-stu-id="b4610-104">A common scenario for any retailer is to sell products to their customers or accept returns from their customers even if they don't carry the specific products in their store (in other words, the products are not assorted to the store).</span></span>

<span data-ttu-id="b4610-105">Di seguito sono riportati alcuni scenari comuni:</span><span class="sxs-lookup"><span data-stu-id="b4610-105">Here are some typical scenarios:</span></span>

+ <span data-ttu-id="b4610-106">Un rivenditore conserva tutti i propri prodotti in un punto vendita specifico.</span><span class="sxs-lookup"><span data-stu-id="b4610-106">A retailer doesn't carry all its products in a specific store.</span></span> <span data-ttu-id="b4610-107">I prodotti rimanenti sono conservati in magazzino.</span><span class="sxs-lookup"><span data-stu-id="b4610-107">The remaining products are stored in the warehouse.</span></span> <span data-ttu-id="b4610-108">L'associato del punto vendita può assistere il cliente nella ricerca dei prodotti nel magazzino, aggiungerli al carrello e completare la transazione selezionando un metodo di consegna, ad esempio la spedizione dal magazzino a un indirizzo, o lasciare che il cliente prelevi il prodotto dal punto vendita corrente o da un altro punto vendita.</span><span class="sxs-lookup"><span data-stu-id="b4610-108">The store associate can assist the customer by searching or browsing for the products in the warehouse, add them to the cart, and complete the checkout by selecting a delivery method, such as shipping to an address from the warehouse or letting the customer pick up the product from the current store or from another store.</span></span>
+ <span data-ttu-id="b4610-109">Un rivenditore non dispone di prodotti specifici presso il punto vendita o non li ha in scorta presso il punto vendita visitato dal cliente, ma i prodotti sono disponibili in altri punti vendita.</span><span class="sxs-lookup"><span data-stu-id="b4610-109">A retailer doesn't carry specific products in the store or doesn't have them in stock at the store the customer visited, but the products are available in other stores.</span></span> <span data-ttu-id="b4610-110">L'associato del punto vendita può assistere il cliente nella ricerca dei prodotti nell'altro punto vendita, aggiungerli al carrello e completare la transazione selezionando un metodo di consegna.</span><span class="sxs-lookup"><span data-stu-id="b4610-110">The store associate can assist the customer by searching or browsing the products in the other store, add them to the cart, and complete the checkout by selecting a delivery method.</span></span>
+ <span data-ttu-id="b4610-111">Un rivenditore possiede numerosi punti vendita vicino o in una città o area specifica e non vuole costringere i clienti a restituire i prodotti allo stesso punto vendita in cui li hanno acquistati.</span><span class="sxs-lookup"><span data-stu-id="b4610-111">A retailer has many stores in and around a specific city or zip code and doesn't want to force the customers to return products to the same store they were purchased in.</span></span> <span data-ttu-id="b4610-112">I clienti possono invece restituire i prodotti in qualsiasi punto vendita.</span><span class="sxs-lookup"><span data-stu-id="b4610-112">Instead, customers can return products to any store.</span></span>

<span data-ttu-id="b4610-113">Questi scenari comuni sono disponibili per i rivenditori che utilizzano Retail.</span><span class="sxs-lookup"><span data-stu-id="b4610-113">Those common scenarios are available for retailers using Retail.</span></span> <span data-ttu-id="b4610-114">Con Retail è possibile:</span><span class="sxs-lookup"><span data-stu-id="b4610-114">With Retail, you can:</span></span>

+ <span data-ttu-id="b4610-115">Cercare dei prodotti presso altri punti vendita.</span><span class="sxs-lookup"><span data-stu-id="b4610-115">Search or browse products at other stores.</span></span>
+ <span data-ttu-id="b4610-116">Cercare tutti i prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="b4610-116">Search or browse all released products.</span></span>
+ <span data-ttu-id="b4610-117">Creare transazioni cash-and-carry o ordini di cliente.</span><span class="sxs-lookup"><span data-stu-id="b4610-117">Create cash-and-carry transactions or customer orders.</span></span>
+ <span data-ttu-id="b4610-118">Selezionare le opzioni di consegna per gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="b4610-118">Select delivery options for customer orders.</span></span>
+ <span data-ttu-id="b4610-119">Prelevare i prodotti presso il punto vendita corrente o presso un altro punto vendita.</span><span class="sxs-lookup"><span data-stu-id="b4610-119">Pick up products at the current store or another store.</span></span>
+ <span data-ttu-id="b4610-120">Annullare un ordine presso il punto vendita corrente o presso un altro punto vendita.</span><span class="sxs-lookup"><span data-stu-id="b4610-120">Cancel an order at the current store or another store.</span></span>
+ <span data-ttu-id="b4610-121">Restituire un ordine con o senza ricevuta presso il punto vendita corrente o presso un altro punto vendita.</span><span class="sxs-lookup"><span data-stu-id="b4610-121">Return an order with or without the receipt at the current store or another store.</span></span>
