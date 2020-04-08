---
title: " Creare i colli prodotto per gli ordini fornitore"
description: In questa procedura vengono descritti i passaggi per creare un collo di prodotti e utilizzarlo in un ordine fornitore.
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b0084c6b4acbf14e3afec552575d5be26114237
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141366"
---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="91082-103"> Creare i colli prodotto per gli ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="91082-103">Create product packages for purchase orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91082-104">In questa procedura vengono descritti i passaggi per creare un collo di prodotti e utilizzarlo in un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="91082-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="91082-105">L'ordine fornitore verrà utilizzato per creare un ordine per un set predefinito di prodotti.</span><span class="sxs-lookup"><span data-stu-id="91082-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="91082-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="91082-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="91082-107">Creare un collo di prodotti</span><span class="sxs-lookup"><span data-stu-id="91082-107">Create a product package</span></span>
1. <span data-ttu-id="91082-108">Passare a Retail e Commerce > Gestione inventario > Rifornimento > Colli prodotti.</span><span class="sxs-lookup"><span data-stu-id="91082-108">Go to Retail and Commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="91082-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="91082-109">Click New.</span></span>
3. <span data-ttu-id="91082-110">Nel campo Numero collo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="91082-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="91082-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="91082-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="91082-112">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="91082-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="91082-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="91082-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="91082-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="91082-114">Click Add.</span></span>
8. <span data-ttu-id="91082-115">Nel campo Numero articolo digitare '0160'.</span><span class="sxs-lookup"><span data-stu-id="91082-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="91082-116">Nel campo Dimensione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="91082-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="91082-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="91082-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="91082-118">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="91082-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="91082-119">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="91082-119">Click Add.</span></span>
13. <span data-ttu-id="91082-120">Nel campo Numero articolo digitare '0160'.</span><span class="sxs-lookup"><span data-stu-id="91082-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="91082-121">Nel campo Numero variante fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="91082-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="91082-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="91082-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="91082-123">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="91082-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="91082-124">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="91082-124">Click Add.</span></span>
18. <span data-ttu-id="91082-125">Nel campo Numero articolo digitare '0175'.</span><span class="sxs-lookup"><span data-stu-id="91082-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="91082-126">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="91082-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="91082-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="91082-127">Click Save.</span></span>
21. <span data-ttu-id="91082-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="91082-128">Close the page.</span></span>

## <a name="add-package-to-purchase-order"></a><span data-ttu-id="91082-129">Aggiungere il collo all'ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="91082-129">Add package to purchase order</span></span>
1. <span data-ttu-id="91082-130">Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="91082-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="91082-131">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="91082-131">Click New.</span></span>
3. <span data-ttu-id="91082-132">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="91082-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="91082-133">Nell'elenco, selezionare lo stesso fornitore per cui è stato creato il collo di prodotti in precedenza, se un fornitore è stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="91082-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="91082-134">Attivare/disattivare l'espansione della sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="91082-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="91082-135">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="91082-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="91082-136">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="91082-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="91082-137">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="91082-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="91082-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="91082-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="91082-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="91082-139">Click OK.</span></span>
11. <span data-ttu-id="91082-140">Attivare/disattivare l'espansione della sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="91082-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="91082-141">Fare clic sulla scheda Colli prodotti.</span><span class="sxs-lookup"><span data-stu-id="91082-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="91082-142">Fare clic su Riga ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="91082-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="91082-143">Fare clic su Crea righe da collo.</span><span class="sxs-lookup"><span data-stu-id="91082-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="91082-144">Nell'elenco, individuare e selezionare il collo di prodotti creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="91082-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="91082-145">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="91082-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="91082-146">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="91082-146">Click Create.</span></span>
18. <span data-ttu-id="91082-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="91082-147">Click Save.</span></span>

