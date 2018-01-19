--- 
title: " Utilizzare un programma di continuità"
description: "Questa procedura descrive la vendita di un programma di continuità e l'elaborazione degli ordini cliente correlati."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 4f12dd1b3f4df2a88da781d39df1700c296a02cf
ms.contentlocale: it-it
ms.lasthandoff: 01/19/2018

---
# <a name="use-a-continuity-program"></a><span data-ttu-id="d89db-103"> Utilizzare un programma di continuità</span><span class="sxs-lookup"><span data-stu-id="d89db-103">Use a continuity program</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="d89db-104">Questa procedura descrive la vendita di un programma di continuità e l'elaborazione degli ordini cliente correlati.</span><span class="sxs-lookup"><span data-stu-id="d89db-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="d89db-105">Per eseguire questa procedura, l'utente deve essere impostato come utente di servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="d89db-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="d89db-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="d89db-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="d89db-107">Passare a Vendita al dettaglio e commercio > Clienti > Servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="d89db-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="d89db-108">Nel campo Cerca testo, digitare 'Karen' quindi premere il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="d89db-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="d89db-109">La finestra di dialogo di ricerca avanzata dovrebbe apparire.</span><span class="sxs-lookup"><span data-stu-id="d89db-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="d89db-110">In caso contrario, fare clic su Cerca a destra del campo.</span><span class="sxs-lookup"><span data-stu-id="d89db-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="d89db-111">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d89db-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d89db-112">Deve essere presente un'unica riga che mostra Karen Berg.</span><span class="sxs-lookup"><span data-stu-id="d89db-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="d89db-113">Selezionare la riga facendo clic su nella colonna di segno di spunta all'estrema sinistra della griglia.</span><span class="sxs-lookup"><span data-stu-id="d89db-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="d89db-114">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="d89db-114">Click Select.</span></span>
5. <span data-ttu-id="d89db-115">Fare clic su Nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="d89db-115">Click New sales order.</span></span>
    * <span data-ttu-id="d89db-116">È consigliabile prendere nota del numero di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="d89db-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="d89db-117">Sarà necessario più avanti in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="d89db-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="d89db-118">Nel campo Numero articolo, digitare '88000' quindi premere il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="d89db-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="d89db-119">Si tratta di un articolo continuità nei dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="d89db-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="d89db-120">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="d89db-120">Click Complete.</span></span>
8. <span data-ttu-id="d89db-121">Nel campo Metodo di pagamento, immettere 'Visa'.</span><span class="sxs-lookup"><span data-stu-id="d89db-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="d89db-122">Fare clic su Aggiungi carta di credito.</span><span class="sxs-lookup"><span data-stu-id="d89db-122">Click Add credit card.</span></span>
    * <span data-ttu-id="d89db-123">Immettere le informazioni necessarie su carta di credito in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="d89db-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="d89db-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d89db-124">Click OK.</span></span>
11. <span data-ttu-id="d89db-125">Espandere la sezione Pagamento.</span><span class="sxs-lookup"><span data-stu-id="d89db-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="d89db-126">Per inviare un ordine servizio clienti, i pagamenti devono essere immessi per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="d89db-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="d89db-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d89db-127">Click OK.</span></span>
13. <span data-ttu-id="d89db-128">Fare clic su Invia.</span><span class="sxs-lookup"><span data-stu-id="d89db-128">Click Submit.</span></span>
    * <span data-ttu-id="d89db-129">È terminata la creazione di un nuovo ordine di continuità.</span><span class="sxs-lookup"><span data-stu-id="d89db-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="d89db-130">A questo punto, eseguirete due processi batch utilizzati per elaborare gli ordini di continuità.</span><span class="sxs-lookup"><span data-stu-id="d89db-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="d89db-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d89db-131">Close the page.</span></span>
15. <span data-ttu-id="d89db-132">Passare a Vendita al dettaglio e commercio > Continuità > Elabora pagamenti di continuità.</span><span class="sxs-lookup"><span data-stu-id="d89db-132">Go to Retail and commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="d89db-133">Nel campo Articolo di continuità, digitare '88000' quindi premere il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="d89db-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="d89db-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d89db-134">Click OK.</span></span>
18. <span data-ttu-id="d89db-135">Passare a Vendita al dettaglio e commercio > Continuità > Crea ordini di continuità figlio.</span><span class="sxs-lookup"><span data-stu-id="d89db-135">Go to Retail and commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="d89db-136">Questo processo consente di creare nuovi ordini cliente in base alle impostazioni dei programmi di continuità.</span><span class="sxs-lookup"><span data-stu-id="d89db-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="d89db-137">Nel campo Articolo di continuità, digitare '88000' quindi premere il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="d89db-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="d89db-138">Articolo '88000' è un articolo di continuità nei dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="d89db-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="d89db-139">Nel campo Ordine cliente immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d89db-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="d89db-140">Immettere il numero di ordine cliente annotato in precedenza nella procedura.</span><span class="sxs-lookup"><span data-stu-id="d89db-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="d89db-141">Questo terrà il tempo di elaborazione a un minimo per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="d89db-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="d89db-142">Il campo Ordine cliente è facoltativo: si potrebbero elaborare tutti gli ordini per qualsiasi dato programma.</span><span class="sxs-lookup"><span data-stu-id="d89db-142">The Sales order field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="d89db-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d89db-143">Click OK.</span></span>


