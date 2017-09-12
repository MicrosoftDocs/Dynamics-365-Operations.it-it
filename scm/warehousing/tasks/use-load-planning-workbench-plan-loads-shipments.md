--- 
title: Pianificare i carichi e le spedizioni utilizzando il workbench di pianificazione del carico
description: Questa procedura illustra come utilizzare il workbench di pianificazione del carico per creare un carico per un ordine cliente.
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f840a4c15305af5f55451ae7f1cec2da25e685a4
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="b5121-103">Pianificare i carichi e le spedizioni utilizzando il workbench di pianificazione del carico</span><span class="sxs-lookup"><span data-stu-id="b5121-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b5121-104">Questa procedura illustra come utilizzare il workbench di pianificazione del carico per creare un carico per un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b5121-104">This procedure shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="b5121-105">Come prerequisito, è necessario creare prima l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b5121-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="b5121-106">Questa procedura è parte delle attività giornaliere per il coordinatore dei trasporti.</span><span class="sxs-lookup"><span data-stu-id="b5121-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="b5121-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="b5121-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="b5121-108">Crea un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="b5121-108">Create a sales order</span></span>
1. <span data-ttu-id="b5121-109">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="b5121-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="b5121-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b5121-110">Click New.</span></span>
3. <span data-ttu-id="b5121-111">Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b5121-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b5121-112">Selezionare il conto US-004.</span><span class="sxs-lookup"><span data-stu-id="b5121-112">Select account US-004.</span></span>
5. <span data-ttu-id="b5121-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b5121-113">Click OK.</span></span>
6. <span data-ttu-id="b5121-114">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b5121-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="b5121-115">Selezionare l'articolo A0001.</span><span class="sxs-lookup"><span data-stu-id="b5121-115">Select item A0001.</span></span>
    * <span data-ttu-id="b5121-116">A0001 è abilitato per la gestione trasporto.</span><span class="sxs-lookup"><span data-stu-id="b5121-116">A0001 is enabled for transportation management.</span></span>  
8. <span data-ttu-id="b5121-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b5121-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="b5121-118">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b5121-118">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="b5121-119">Nel campo Magazzino digitare "24".</span><span class="sxs-lookup"><span data-stu-id="b5121-119">In the Warehouse field, type '24'.</span></span>
    * <span data-ttu-id="b5121-120">In questo esempio selezionare il magazzino 24.</span><span class="sxs-lookup"><span data-stu-id="b5121-120">In this example select warehouse 24.</span></span> <span data-ttu-id="b5121-121">Tale magazzino è abilitato per la gestione trasporto e la gestione avanzata del magazzino.</span><span class="sxs-lookup"><span data-stu-id="b5121-121">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="b5121-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b5121-122">Click Save.</span></span>
12. <span data-ttu-id="b5121-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b5121-123">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="b5121-124">Creare un nuovo carico</span><span class="sxs-lookup"><span data-stu-id="b5121-124">Create a new load</span></span>
1. <span data-ttu-id="b5121-125">Andare a Gestione trasporto > Pianificazione > Workbench pianificazione carico.</span><span class="sxs-lookup"><span data-stu-id="b5121-125">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="b5121-126">Fare clic sulla scheda Righe di vendita.</span><span class="sxs-lookup"><span data-stu-id="b5121-126">Click the Sales lines tab.</span></span>
    * <span data-ttu-id="b5121-127">Verrà creato il carico per l'ordine cliente creato.</span><span class="sxs-lookup"><span data-stu-id="b5121-127">Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="b5121-128">I carichi possono essere creati in base all'offerta e alla domanda da ordini fornitore, ordini di trasferimento e ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="b5121-128">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="b5121-129">Nel riquadro azioni fare clic su Domanda e offerta.</span><span class="sxs-lookup"><span data-stu-id="b5121-129">On the Action Pane, click Supply and demand.</span></span>
4. <span data-ttu-id="b5121-130">Fare clic su Al nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="b5121-130">Click To new load.</span></span>
5. <span data-ttu-id="b5121-131">Nel campo ID modello carico fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b5121-131">In the Load template ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b5121-132">Il modello di carico definisce le misure massime per il peso e il volume dell'intero carico.</span><span class="sxs-lookup"><span data-stu-id="b5121-132">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="b5121-133">Ad esempio, il modello di carico può rappresentare la dimensione di un container o di un camion.</span><span class="sxs-lookup"><span data-stu-id="b5121-133">For example, the load template might represent the size of a container or truck.</span></span>  
6. <span data-ttu-id="b5121-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b5121-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="b5121-135">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b5121-135">Click OK.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="b5121-136">Assegnare una tariffa e un percorso al carico</span><span class="sxs-lookup"><span data-stu-id="b5121-136">Rate and route the load</span></span>
1. <span data-ttu-id="b5121-137">Fare clic su Valutazione e distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b5121-137">Click Rating and routing.</span></span>
2. <span data-ttu-id="b5121-138">Fare clic su Tariffa workbench ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="b5121-138">Click Rate route workbench.</span></span>
3. <span data-ttu-id="b5121-139">Fare clic su Strumento tariffe.</span><span class="sxs-lookup"><span data-stu-id="b5121-139">Click Rate shop.</span></span>
4. <span data-ttu-id="b5121-140">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="b5121-140">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="b5121-141">Fare clic su Assegna.</span><span class="sxs-lookup"><span data-stu-id="b5121-141">Click Assign.</span></span>
6. <span data-ttu-id="b5121-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b5121-142">Close the page.</span></span>
7. <span data-ttu-id="b5121-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b5121-143">Close the page.</span></span>

