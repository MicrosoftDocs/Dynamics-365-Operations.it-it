---
title: Uso di Programma di continuità
description: Questa procedura descrive la vendita di un programma di continuità e l'elaborazione degli ordini cliente correlati.
author: scott-tucker
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 58eca42634ad995f174350bc3a1996ddc4c449b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804091"
---
# <a name="using-continuity-program"></a><span data-ttu-id="c8898-103">Uso di Programma di continuità</span><span class="sxs-lookup"><span data-stu-id="c8898-103">Using continuity program</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8898-104">Questa procedura descrive la vendita di un programma di continuità e l'elaborazione degli ordini cliente correlati.</span><span class="sxs-lookup"><span data-stu-id="c8898-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="c8898-105">Per eseguire questa procedura, l'utente deve essere impostato come utente di servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="c8898-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="c8898-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="c8898-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="c8898-107">Passare a Retail e Commerce > Clienti > Servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="c8898-107">Go to Retail and Commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="c8898-108">Nel campo Cerca testo, digitare 'Karen' quindi premere il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="c8898-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="c8898-109">La finestra di dialogo di ricerca avanzata dovrebbe apparire.</span><span class="sxs-lookup"><span data-stu-id="c8898-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="c8898-110">In caso contrario, fare clic su Cerca a destra del campo.</span><span class="sxs-lookup"><span data-stu-id="c8898-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="c8898-111">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c8898-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c8898-112">Deve essere presente un'unica riga che mostra Karen Berg.</span><span class="sxs-lookup"><span data-stu-id="c8898-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="c8898-113">Selezionare la riga facendo clic su nella colonna di segno di spunta all'estrema sinistra della griglia.</span><span class="sxs-lookup"><span data-stu-id="c8898-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="c8898-114">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="c8898-114">Click Select.</span></span>
5. <span data-ttu-id="c8898-115">Fare clic su Nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="c8898-115">Click New sales order.</span></span>
    * <span data-ttu-id="c8898-116">È consigliabile prendere nota del numero di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="c8898-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="c8898-117">Sarà necessario più avanti in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c8898-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="c8898-118">Nel campo Numero articolo, digitare '88000' quindi premere il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="c8898-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="c8898-119">Si tratta di un articolo continuità nei dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="c8898-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="c8898-120">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="c8898-120">Click Complete.</span></span>
8. <span data-ttu-id="c8898-121">Nel campo Metodo di pagamento, immettere 'Visa'.</span><span class="sxs-lookup"><span data-stu-id="c8898-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="c8898-122">Fare clic su Aggiungi carta di credito.</span><span class="sxs-lookup"><span data-stu-id="c8898-122">Click Add credit card.</span></span>
    * <span data-ttu-id="c8898-123">Immettere le informazioni necessarie su carta di credito in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="c8898-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="c8898-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8898-124">Click OK.</span></span>
11. <span data-ttu-id="c8898-125">Espandere la sezione Pagamento.</span><span class="sxs-lookup"><span data-stu-id="c8898-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="c8898-126">Per inviare un ordine servizio clienti, i pagamenti devono essere immessi per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="c8898-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="c8898-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8898-127">Click OK.</span></span>
13. <span data-ttu-id="c8898-128">Fare clic su Invia.</span><span class="sxs-lookup"><span data-stu-id="c8898-128">Click Submit.</span></span>
    * <span data-ttu-id="c8898-129">È terminata la creazione di un nuovo ordine di continuità.</span><span class="sxs-lookup"><span data-stu-id="c8898-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="c8898-130">A questo punto, eseguirete due processi batch utilizzati per elaborare gli ordini di continuità.</span><span class="sxs-lookup"><span data-stu-id="c8898-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="c8898-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c8898-131">Close the page.</span></span>
15. <span data-ttu-id="c8898-132">Passare a Retail e Commerce > Continuità > Elabora pagamenti di continuità.</span><span class="sxs-lookup"><span data-stu-id="c8898-132">Go to Retail and Commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="c8898-133">Nel campo Articolo di continuità, digitare '88000' quindi premere il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="c8898-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="c8898-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8898-134">Click OK.</span></span>
18. <span data-ttu-id="c8898-135">Passare a Retail e Commerce > Continuità > Crea ordini di continuità figlio.</span><span class="sxs-lookup"><span data-stu-id="c8898-135">Go to Retail and Commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="c8898-136">Questo processo consente di creare nuovi ordini cliente in base alle impostazioni dei programmi di continuità.</span><span class="sxs-lookup"><span data-stu-id="c8898-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="c8898-137">Nel campo Articolo di continuità, digitare '88000' quindi premere il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="c8898-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="c8898-138">Articolo '88000' è un articolo di continuità nei dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="c8898-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="c8898-139">Nel campo Ordine cliente immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c8898-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="c8898-140">Immettere il numero di ordine cliente annotato in precedenza nella procedura.</span><span class="sxs-lookup"><span data-stu-id="c8898-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="c8898-141">Questo terrà il tempo di elaborazione a un minimo per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c8898-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="c8898-142">Il campo Ordine cliente è facoltativo: si potrebbero elaborare tutti gli ordini per qualsiasi dato programma.</span><span class="sxs-lookup"><span data-stu-id="c8898-142">The Sales order field field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="c8898-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8898-143">Click OK.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]