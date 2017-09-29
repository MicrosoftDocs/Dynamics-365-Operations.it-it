--- 
title: " Creare i colli prodotto per gli ordini fornitore"
description: In questa procedura vengono descritti i passaggi per creare un collo di prodotti e utilizzarlo in un ordine fornitore.
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a3be1e7aca7f0382aea55fa8a371c33c8b53df95
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="80675-103"> Creare i colli prodotto per gli ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="80675-103">Create product packages for purchase orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="80675-104">In questa procedura vengono descritti i passaggi per creare un collo di prodotti e utilizzarlo in un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="80675-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="80675-105">L'ordine fornitore verrà utilizzato per creare un ordine per un set predefinito di prodotti.</span><span class="sxs-lookup"><span data-stu-id="80675-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="80675-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="80675-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="80675-107">Creare un collo di prodotti</span><span class="sxs-lookup"><span data-stu-id="80675-107">Create a product package</span></span>
1. <span data-ttu-id="80675-108">Passare a Vendita al dettaglio e commercio > Gestione inventario > Rifornimento > Colli prodotti.</span><span class="sxs-lookup"><span data-stu-id="80675-108">Go to Retail and commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="80675-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="80675-109">Click New.</span></span>
3. <span data-ttu-id="80675-110">Nel campo Numero collo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="80675-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="80675-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="80675-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="80675-112">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="80675-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="80675-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="80675-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="80675-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="80675-114">Click Add.</span></span>
8. <span data-ttu-id="80675-115">Nel campo Numero articolo digitare '0160'.</span><span class="sxs-lookup"><span data-stu-id="80675-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="80675-116">Nel campo Dimensione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="80675-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="80675-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="80675-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="80675-118">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="80675-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="80675-119">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="80675-119">Click Add.</span></span>
13. <span data-ttu-id="80675-120">Nel campo Numero articolo digitare '0160'.</span><span class="sxs-lookup"><span data-stu-id="80675-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="80675-121">Nel campo Numero variante fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="80675-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="80675-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="80675-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="80675-123">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="80675-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="80675-124">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="80675-124">Click Add.</span></span>
18. <span data-ttu-id="80675-125">Nel campo Numero articolo digitare '0175'.</span><span class="sxs-lookup"><span data-stu-id="80675-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="80675-126">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="80675-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="80675-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="80675-127">Click Save.</span></span>
21. <span data-ttu-id="80675-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="80675-128">Close the page.</span></span>

## <a name="add-package-to-puchase-order"></a><span data-ttu-id="80675-129">Aggiungere il collo all'ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="80675-129">Add package to puchase order</span></span>
1. <span data-ttu-id="80675-130">Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="80675-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="80675-131">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="80675-131">Click New.</span></span>
3. <span data-ttu-id="80675-132">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="80675-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="80675-133">Nell'elenco, selezionare lo stesso fornitore per cui è stato creato il collo di prodotti in precedenza, se un fornitore è stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="80675-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="80675-134">Attivare/disattivare l'espansione della sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="80675-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="80675-135">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="80675-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="80675-136">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="80675-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="80675-137">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="80675-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="80675-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="80675-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="80675-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="80675-139">Click OK.</span></span>
11. <span data-ttu-id="80675-140">Attivare/disattivare l'espansione della sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="80675-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="80675-141">Fare clic sulla scheda Colli prodotti.</span><span class="sxs-lookup"><span data-stu-id="80675-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="80675-142">Fare clic su Riga ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="80675-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="80675-143">Fare clic su Crea righe da collo.</span><span class="sxs-lookup"><span data-stu-id="80675-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="80675-144">Nell'elenco, individuare e selezionare il collo di prodotti creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="80675-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="80675-145">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="80675-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="80675-146">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="80675-146">Click Create.</span></span>
18. <span data-ttu-id="80675-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="80675-147">Click Save.</span></span>


