---
title: Creare nuovo ordine di rifornimento spedizione
description: "In questa procedura viene illustrato come creare un ordine di rifornimento spedizione in cui è possibile tracciare la consegna prevista da un fornitore nell'inventario di spedizione."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 6286e8f52b8131a8e4779f1e11d84233b8e0760e
ms.contentlocale: it-it
ms.lasthandoff: 09/12/2017

---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="2791c-103">Creare nuovo ordine di rifornimento spedizione</span><span class="sxs-lookup"><span data-stu-id="2791c-103">Create a consignment replenishment order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2791c-104">In questa procedura viene illustrato come creare un ordine di rifornimento spedizione in cui è possibile tracciare la consegna prevista da un fornitore nell'inventario di spedizione.</span><span class="sxs-lookup"><span data-stu-id="2791c-104">This procedure shows how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="2791c-105">Viene inoltre illustrato come registrare un'entrata prodotti in modo da registrare l'inventario di spedizione come scorte disponibili di proprietà del fornitore.</span><span class="sxs-lookup"><span data-stu-id="2791c-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="2791c-106">Questa procedura viene in genere eseguita da un responsabile approvvigionamenti.</span><span class="sxs-lookup"><span data-stu-id="2791c-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="2791c-107">È possibile utilizzare questa guida nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="2791c-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="2791c-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations, versione 1611.</span><span class="sxs-lookup"><span data-stu-id="2791c-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>




## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="2791c-109">Creare nuovo ordine di rifornimento spedizione</span><span class="sxs-lookup"><span data-stu-id="2791c-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="2791c-110">Andare ad Approvvigionamento > Spedizione > Ordini di rifornimento spedizione.</span><span class="sxs-lookup"><span data-stu-id="2791c-110">Go to Procurement and sourcing > Consignment > Consignment replenishment orders.</span></span>
2. <span data-ttu-id="2791c-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2791c-111">Click New.</span></span>
3. <span data-ttu-id="2791c-112">Nel campo Conto fornitore selezionare il fornitore US-104.</span><span class="sxs-lookup"><span data-stu-id="2791c-112">In the Vendor account field, select vendor US-104.</span></span>
    * <span data-ttu-id="2791c-113">È necessario selezionare un fornitore registrato come proprietario nella pagina Proprietari inventario.</span><span class="sxs-lookup"><span data-stu-id="2791c-113">You must select a vendor that’s registered as an owner in the Inventory owners page.</span></span>  
4. <span data-ttu-id="2791c-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2791c-114">Click OK.</span></span>
5. <span data-ttu-id="2791c-115">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="2791c-115">Click Add line.</span></span>
6. <span data-ttu-id="2791c-116">Nel campo Numero articolo digitare M9211CI.</span><span class="sxs-lookup"><span data-stu-id="2791c-116">In the Item number field, type M9211CI.</span></span>
    * <span data-ttu-id="2791c-117">È necessario selezionare un articolo impostato per l'inventario di spedizione.</span><span class="sxs-lookup"><span data-stu-id="2791c-117">You must select an item that is set up for consignment inventory.</span></span>  
7. <span data-ttu-id="2791c-118">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="2791c-118">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="2791c-119">Nel campo Data di consegna richiesta immettere una data.</span><span class="sxs-lookup"><span data-stu-id="2791c-119">In the Requested delivery date field, enter a date.</span></span>
    * <span data-ttu-id="2791c-120">Le date di richiesta e conferma vengono utilizzate dal motore MRP per l'arrivo previsto delle merci.</span><span class="sxs-lookup"><span data-stu-id="2791c-120">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="2791c-121">Immettere una data nel campo Data di consegna confermata.</span><span class="sxs-lookup"><span data-stu-id="2791c-121">In the Confirmed delivery date field, enter a date.</span></span>
10. <span data-ttu-id="2791c-122">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="2791c-122">Expand the Line details section.</span></span>
11. <span data-ttu-id="2791c-123">Fare clic sulla scheda Dimensioni inventariali.</span><span class="sxs-lookup"><span data-stu-id="2791c-123">Click the Inventory dimensions tab.</span></span>
12. <span data-ttu-id="2791c-124">Per visualizzare il proprietario nel campo del proprietario Dimensioni inventariali, aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="2791c-124">To show the owner in the Inventory dimensions owner field, refresh the page.</span></span>
    * <span data-ttu-id="2791c-125">Il fornitore US-104 è ora elencato come proprietario.</span><span class="sxs-lookup"><span data-stu-id="2791c-125">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="2791c-126">Controllare lo stato delle transazioni di inventario</span><span class="sxs-lookup"><span data-stu-id="2791c-126">Check the inventory transaction status</span></span>
1. <span data-ttu-id="2791c-127">Fare clic su Scorte.</span><span class="sxs-lookup"><span data-stu-id="2791c-127">Click Inventory.</span></span>
2. <span data-ttu-id="2791c-128">Fare clic su Transazioni.</span><span class="sxs-lookup"><span data-stu-id="2791c-128">Click Transactions.</span></span>
3. <span data-ttu-id="2791c-129">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2791c-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2791c-130">Si noti che il campo Entrata è impostato su Ordinato.</span><span class="sxs-lookup"><span data-stu-id="2791c-130">Notice that the Receipt field is set to Ordered.</span></span>  
4. <span data-ttu-id="2791c-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2791c-131">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="2791c-132">Ricevi articoli</span><span class="sxs-lookup"><span data-stu-id="2791c-132">Receive items</span></span>
1. <span data-ttu-id="2791c-133">Fare clic su Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="2791c-133">Click Product receipt.</span></span>
2. <span data-ttu-id="2791c-134">Digitare un valore nel campo Entrata prodotti esterna.</span><span class="sxs-lookup"><span data-stu-id="2791c-134">In the External product receipt field, type a value.</span></span>
3. <span data-ttu-id="2791c-135">Nel campo Quantità, immettere un numero minore del numero riportato lì.</span><span class="sxs-lookup"><span data-stu-id="2791c-135">In the Quantity field, enter a number that’s lower than the number that’s shown there.</span></span>
4. <span data-ttu-id="2791c-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2791c-136">Click OK.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="2791c-137">Controllare le scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="2791c-137">Check the on-hand inventory</span></span>
1. <span data-ttu-id="2791c-138">Fare clic su Scorte.</span><span class="sxs-lookup"><span data-stu-id="2791c-138">Click Inventory.</span></span>
2. <span data-ttu-id="2791c-139">Fare clic su Disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2791c-139">Click On-hand.</span></span>
3. <span data-ttu-id="2791c-140">Fare clic su Panoramica.</span><span class="sxs-lookup"><span data-stu-id="2791c-140">Click Overview.</span></span>
    * <span data-ttu-id="2791c-141">Gli articoli ricevuti come inventario di spedizione di proprietà del fornitore sono scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="2791c-141">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="2791c-142">La quantità rimanente nell'ordine di rifornimento spedizione è indicata nel campo Ordinata in totale.</span><span class="sxs-lookup"><span data-stu-id="2791c-142">The remaining quantity on the consignment replenishment order is shown in the Ordered in total field.</span></span>  
4. <span data-ttu-id="2791c-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2791c-143">Close the page.</span></span>
5. <span data-ttu-id="2791c-144">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="2791c-144">Click Close.</span></span>
