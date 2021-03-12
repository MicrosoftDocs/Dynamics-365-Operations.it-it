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
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 296b3fb03b20dee5b6024c182df7feb3ce280913
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964672"
---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="4e952-103"> Creare i colli prodotto per gli ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="4e952-103">Create product packages for purchase orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4e952-104">In questa procedura vengono descritti i passaggi per creare un collo di prodotti e utilizzarlo in un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="4e952-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="4e952-105">L'ordine fornitore verrà utilizzato per creare un ordine per un set predefinito di prodotti.</span><span class="sxs-lookup"><span data-stu-id="4e952-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="4e952-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="4e952-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="4e952-107">Creare un collo di prodotti</span><span class="sxs-lookup"><span data-stu-id="4e952-107">Create a product package</span></span>
1. <span data-ttu-id="4e952-108">Passare a Retail e Commerce > Gestione inventario > Rifornimento > Colli prodotti.</span><span class="sxs-lookup"><span data-stu-id="4e952-108">Go to Retail and Commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="4e952-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4e952-109">Click New.</span></span>
3. <span data-ttu-id="4e952-110">Nel campo Numero collo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4e952-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="4e952-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4e952-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4e952-112">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4e952-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="4e952-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4e952-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="4e952-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4e952-114">Click Add.</span></span>
8. <span data-ttu-id="4e952-115">Nel campo Numero articolo digitare '0160'.</span><span class="sxs-lookup"><span data-stu-id="4e952-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="4e952-116">Nel campo Dimensione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4e952-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="4e952-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4e952-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="4e952-118">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4e952-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="4e952-119">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4e952-119">Click Add.</span></span>
13. <span data-ttu-id="4e952-120">Nel campo Numero articolo digitare '0160'.</span><span class="sxs-lookup"><span data-stu-id="4e952-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="4e952-121">Nel campo Numero variante fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4e952-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="4e952-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4e952-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="4e952-123">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4e952-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="4e952-124">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4e952-124">Click Add.</span></span>
18. <span data-ttu-id="4e952-125">Nel campo Numero articolo digitare '0175'.</span><span class="sxs-lookup"><span data-stu-id="4e952-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="4e952-126">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4e952-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="4e952-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4e952-127">Click Save.</span></span>
21. <span data-ttu-id="4e952-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4e952-128">Close the page.</span></span>

## <a name="add-package-to-purchase-order"></a><span data-ttu-id="4e952-129">Aggiungere il collo all'ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="4e952-129">Add package to purchase order</span></span>
1. <span data-ttu-id="4e952-130">Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="4e952-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="4e952-131">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4e952-131">Click New.</span></span>
3. <span data-ttu-id="4e952-132">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4e952-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="4e952-133">Nell'elenco, selezionare lo stesso fornitore per cui è stato creato il collo di prodotti in precedenza, se un fornitore è stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="4e952-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="4e952-134">Attivare/disattivare l'espansione della sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="4e952-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="4e952-135">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4e952-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="4e952-136">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4e952-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="4e952-137">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4e952-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="4e952-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4e952-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="4e952-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4e952-139">Click OK.</span></span>
11. <span data-ttu-id="4e952-140">Attivare/disattivare l'espansione della sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="4e952-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="4e952-141">Fare clic sulla scheda Colli prodotti.</span><span class="sxs-lookup"><span data-stu-id="4e952-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="4e952-142">Fare clic su Riga ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="4e952-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="4e952-143">Fare clic su Crea righe da collo.</span><span class="sxs-lookup"><span data-stu-id="4e952-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="4e952-144">Nell'elenco, individuare e selezionare il collo di prodotti creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="4e952-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="4e952-145">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4e952-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="4e952-146">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="4e952-146">Click Create.</span></span>
18. <span data-ttu-id="4e952-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4e952-147">Click Save.</span></span>

