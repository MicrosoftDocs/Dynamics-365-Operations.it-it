---
title: " Rettifiche prezzi di vendita al dettaglio"
description: In questa procedura vengono descritti i passaggi per creare una rettifica prezzo di commercio.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailDiscountPriceGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83498fa0a0432cb182106d6d273cb6117ed0b094
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413491"
---
# <a name="retail-price-adjustments"></a><span data-ttu-id="2ee30-103"> Rettifiche prezzi di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="2ee30-103">Retail price adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ee30-104">In questa procedura vengono descritti i passaggi per creare una rettifica prezzo di commercio.</span><span class="sxs-lookup"><span data-stu-id="2ee30-104">This procedure will walk through creating a commerce price adjustment.</span></span> <span data-ttu-id="2ee30-105">Con una rettifica prezzo si può impostare direttamente il prezzo di vendita di un articolo o modificare il prezzo di vendita di base o il prezzo di vendita dell'accordo commerciale.</span><span class="sxs-lookup"><span data-stu-id="2ee30-105">A price adjustment can set an item's sale price directly, or modify its base sale price or trade agreement sale price.</span></span> <span data-ttu-id="2ee30-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="2ee30-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="2ee30-107">Fare clic su Gestione prezzi e sconti.</span><span class="sxs-lookup"><span data-stu-id="2ee30-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="2ee30-108">Fare clic sulla scheda Rettifiche prezzi.</span><span class="sxs-lookup"><span data-stu-id="2ee30-108">Click the Price adjustments tab.</span></span>
3. <span data-ttu-id="2ee30-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2ee30-109">Click New.</span></span>
    * <span data-ttu-id="2ee30-110">A questo punto è possibile creare tutte le regole di sconto e di prezzo più utilizzate, incluse le regole di sconti, rettifiche di prezzo, giornali di registrazione accordi commerciali e prezzi di categoria.</span><span class="sxs-lookup"><span data-stu-id="2ee30-110">From here you can create all of the most commonly used price and discount rules, including discounts, price adjustments, trade agreement journals, and category pricing rules.</span></span>  
4. <span data-ttu-id="2ee30-111">Fare clic su Rettifica prezzo.</span><span class="sxs-lookup"><span data-stu-id="2ee30-111">Click Price adjustment.</span></span>
5. <span data-ttu-id="2ee30-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2ee30-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="2ee30-113">Espandere la sezione Righe.</span><span class="sxs-lookup"><span data-stu-id="2ee30-113">Expand the Lines section.</span></span>
7. <span data-ttu-id="2ee30-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="2ee30-114">Click Add.</span></span>
    * <span data-ttu-id="2ee30-115">Per questo esempio, immettere '81126' nel campo Prodotto.</span><span class="sxs-lookup"><span data-stu-id="2ee30-115">For this example, enter '81126' in the Product field.</span></span> <span data-ttu-id="2ee30-116">Poi, nel campo Percentuale sconto, immettere '10,0'.</span><span class="sxs-lookup"><span data-stu-id="2ee30-116">Then, enter '10.0' in the Discount percentage field.</span></span>  
    * <span data-ttu-id="2ee30-117">Una rettifica prezzo di tipo di percentuale sconto riduce il prezzo di vendita di base o il prezzo di vendita dell'accordo commerciale.</span><span class="sxs-lookup"><span data-stu-id="2ee30-117">A discount percentage type price adjustment will reduce a base sales price or trade agreement sales price.</span></span>  
8. <span data-ttu-id="2ee30-118">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="2ee30-118">Click Add.</span></span>
    * <span data-ttu-id="2ee30-119">Per questo esempio, immettere '81125' nel campo Prodotto.</span><span class="sxs-lookup"><span data-stu-id="2ee30-119">For this example, enter '81125' in the Product field.</span></span> <span data-ttu-id="2ee30-120">Quindi, selezionare 'Importo sconto di cassa' nel campo Metodo di sconto.</span><span class="sxs-lookup"><span data-stu-id="2ee30-120">Then, select 'Cash discount amount' in the Discount method field.</span></span>    <span data-ttu-id="2ee30-121">Infine, impostare '5,0' nel campo Importo sconto di cassa.</span><span class="sxs-lookup"><span data-stu-id="2ee30-121">Finally, enter '5.0' in the Cash discount amount field.</span></span>  
    * <span data-ttu-id="2ee30-122">Il tipo di sconto Importo sconto di cassa è un importo detratto dal prezzo di base o dal prezzo dell'accordo commerciale.</span><span class="sxs-lookup"><span data-stu-id="2ee30-122">A Cash discount amount discount type is an amount taken off from a base price or a trade agreement price.</span></span>  
9. <span data-ttu-id="2ee30-123">Fare clic su Gruppi di prezzi.</span><span class="sxs-lookup"><span data-stu-id="2ee30-123">Click Price groups.</span></span>
    * <span data-ttu-id="2ee30-124">Selezionare 'RP-Houston' nel campo Gruppo di prezzi.</span><span class="sxs-lookup"><span data-stu-id="2ee30-124">Select 'RP-Houston' in the Price group field.</span></span>  
    * <span data-ttu-id="2ee30-125">In tal modo la rettifica prezzo viene associata al punto vendita Houston.</span><span class="sxs-lookup"><span data-stu-id="2ee30-125">This will associate the Price adjustment to the Houston store.</span></span>  
10. <span data-ttu-id="2ee30-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2ee30-126">Click Save.</span></span>
11. <span data-ttu-id="2ee30-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2ee30-127">Close the page.</span></span>
12. <span data-ttu-id="2ee30-128">Nel campo Stato, selezionare 'Abilitato'.</span><span class="sxs-lookup"><span data-stu-id="2ee30-128">In the Status field, select 'Enabled'.</span></span>
13. <span data-ttu-id="2ee30-129">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2ee30-129">Click Save.</span></span>
14. <span data-ttu-id="2ee30-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2ee30-130">Close the page.</span></span>
15. <span data-ttu-id="2ee30-131">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="2ee30-131">Refresh the page.</span></span>

