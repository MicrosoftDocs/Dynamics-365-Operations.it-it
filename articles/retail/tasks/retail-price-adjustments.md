--- 
title: " Rettifiche prezzi di vendita al dettaglio"
description: In questa procedura vengono descritti i passaggi per creare una rettifica prezzo di vendita al dettaglio.
author: josaw1
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: edfb9a1515f0af7d3272ea3fbb362bd0e6b0f129
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="retail-price-adjustments"></a><span data-ttu-id="25769-103"> Rettifiche prezzi di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="25769-103">Retail price adjustments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="25769-104">In questa procedura vengono descritti i passaggi per creare una rettifica prezzo di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="25769-104">This procedure will walk through creating a retail price adjustment.</span></span> <span data-ttu-id="25769-105">Con una rettifica prezzo di vendita al dettaglio si può impostare direttamente il prezzo di vendita di un articolo o modificare il prezzo di vendita di base o il prezzo di vendita dell'accordo commerciale.</span><span class="sxs-lookup"><span data-stu-id="25769-105">A retail price adjustment can set an item's sale price directly, or modify its base sale price or trade agreement sale price.</span></span> <span data-ttu-id="25769-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="25769-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="25769-107">Fare clic su Gestione prezzi e sconti.</span><span class="sxs-lookup"><span data-stu-id="25769-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="25769-108">Fare clic sulla scheda Rettifiche prezzi.</span><span class="sxs-lookup"><span data-stu-id="25769-108">Click the Price adjustments tab.</span></span>
3. <span data-ttu-id="25769-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="25769-109">Click New.</span></span>
    * <span data-ttu-id="25769-110">A questo punto è possibile creare tutte le regole di sconto e di prezzo più utilizzate, incluse le regole di sconti vendita al dettaglio, rettifiche di prezzo, giornali di registrazione accordi commerciali e prezzi di categoria.</span><span class="sxs-lookup"><span data-stu-id="25769-110">From here you can create all of the most commonly used price and discount rules, including retail discounts, price adjustments, trade agreement journals, and category pricing rules.</span></span>  
4. <span data-ttu-id="25769-111">Fare clic su Rettifica prezzo.</span><span class="sxs-lookup"><span data-stu-id="25769-111">Click Price adjustment.</span></span>
5. <span data-ttu-id="25769-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="25769-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="25769-113">Espandere la sezione Righe.</span><span class="sxs-lookup"><span data-stu-id="25769-113">Expand the Lines section.</span></span>
7. <span data-ttu-id="25769-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="25769-114">Click Add.</span></span>
    * <span data-ttu-id="25769-115">Per questo esempio, immettere '81126' nel campo Prodotto.</span><span class="sxs-lookup"><span data-stu-id="25769-115">For this example, enter '81126' in the Product field.</span></span>    <span data-ttu-id="25769-116">Poi, nel campo Percentuale sconto, immettere '10,0'.</span><span class="sxs-lookup"><span data-stu-id="25769-116">Then, enter '10.0' in the Discount percentage field.</span></span>  
    * <span data-ttu-id="25769-117">Una rettifica prezzo di tipo di percentuale sconto riduce il prezzo di vendita di base o il prezzo di vendita dell'accordo commerciale.</span><span class="sxs-lookup"><span data-stu-id="25769-117">A discount percentage type price adjustment will reduce a base sales price or trade agreement sales price.</span></span>  
8. <span data-ttu-id="25769-118">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="25769-118">Click Add.</span></span>
    * <span data-ttu-id="25769-119">Per questo esempio, immettere '81125' nel campo Prodotto.</span><span class="sxs-lookup"><span data-stu-id="25769-119">For this example, enter '81125' in the Product field.</span></span>    <span data-ttu-id="25769-120">Quindi, selezionare 'Importo sconto di cassa' nel campo Metodo di sconto.</span><span class="sxs-lookup"><span data-stu-id="25769-120">Then, select 'Cash discount amount' in the Discount method field.</span></span>    <span data-ttu-id="25769-121">Infine, impostare '5,0' nel campo Importo sconto di cassa.</span><span class="sxs-lookup"><span data-stu-id="25769-121">Finally, enter '5.0' in the Cash discount amount field.</span></span>  
    * <span data-ttu-id="25769-122">Il tipo di sconto Importo sconto di cassa è un importo detratto dal prezzo di base o dal prezzo dell'accordo commerciale.</span><span class="sxs-lookup"><span data-stu-id="25769-122">A Cash discount amount discount type is an amount taken off from a base price or a trade agreement price.</span></span>  
9. <span data-ttu-id="25769-123">Fare clic su Gruppi di prezzi.</span><span class="sxs-lookup"><span data-stu-id="25769-123">Click Price groups.</span></span>
    * <span data-ttu-id="25769-124">Selezionare 'RP-Houston' nel campo Gruppo di prezzi.</span><span class="sxs-lookup"><span data-stu-id="25769-124">Select 'RP-Houston' in the Price group field.</span></span>  
    * <span data-ttu-id="25769-125">In tal modo la rettifica prezzo viene associata al punto vendita Houston.</span><span class="sxs-lookup"><span data-stu-id="25769-125">This will associate the Price adjustment to the Houston store.</span></span>  
10. <span data-ttu-id="25769-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="25769-126">Click Save.</span></span>
11. <span data-ttu-id="25769-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25769-127">Close the page.</span></span>
12. <span data-ttu-id="25769-128">Nel campo Stato, selezionare 'Abilitato'.</span><span class="sxs-lookup"><span data-stu-id="25769-128">In the Status field, select 'Enabled'.</span></span>
13. <span data-ttu-id="25769-129">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="25769-129">Click Save.</span></span>
14. <span data-ttu-id="25769-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25769-130">Close the page.</span></span>
15. <span data-ttu-id="25769-131">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="25769-131">Refresh the page.</span></span>


