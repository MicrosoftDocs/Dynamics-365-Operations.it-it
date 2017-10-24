---
title: Contare le scorte magazzino
description: In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione conteggi scorte in modo da conteggiare un articolo specifico in un'ubicazione del magazzino.
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fa72cb0d651f5e60797fa41f6e2b2cf1891730b5
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="ec619-103">Contare le scorte magazzino</span><span class="sxs-lookup"><span data-stu-id="ec619-103">Count inventory in a warehouse</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ec619-104">In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione conteggi scorte in modo da conteggiare un articolo specifico in un'ubicazione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="ec619-104">This procedure walks you through the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="ec619-105">In questa procedura si applica la funzionalità di gestione magazzino di base, disponibile nel modulo Gestione articoli e non la funzionalità di gestione del magazzino disponibile nel modulo Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="ec619-105">The procedure applies to “basic warehousing” functionality, available in the Inventory management module, not to the warehousing functionality that’s available in the Warehouse management module.</span></span> <span data-ttu-id="ec619-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="ec619-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="ec619-107">Se si utilizzano propri dati, assicurarsi di aver configurato prodotti e ubicazioni e aver creato un nome di giornale di registrazione magazzino per il conteggio dei giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ec619-107">If you’re using your own data, make sure that you have products and locations set up, and that you’ve created an inventory journal name for counting journals.</span></span> <span data-ttu-id="ec619-108">Il conteggio delle scorte viene in genere eseguito da un dipendente del reparto magazzino.</span><span class="sxs-lookup"><span data-stu-id="ec619-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="ec619-109">Creare un giornale di registrazione conteggi scorte</span><span class="sxs-lookup"><span data-stu-id="ec619-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="ec619-110">Andare a Gestione inventario > Inserimenti nel giornale di registrazione > Conteggio articoli > Conteggio.</span><span class="sxs-lookup"><span data-stu-id="ec619-110">Go to Inventory management > Journal entries > Item counting > Counting.</span></span>
2. <span data-ttu-id="ec619-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ec619-111">Click New.</span></span>
3. <span data-ttu-id="ec619-112">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec619-112">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ec619-113">Nell'elenco, fare clic sul nome giornale di registrazione conteggio scorte che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ec619-113">In the list, click on the inventory counting journal name you want to use</span></span>
    * <span data-ttu-id="ec619-114">Alcuni campi saranno popolati in base all'impostazione del nome giornale di registrazione conteggio scorte selezionato.</span><span class="sxs-lookup"><span data-stu-id="ec619-114">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
5. <span data-ttu-id="ec619-115">Nel campo Lavoratore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec619-115">In the Worker field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ec619-116">Selezionare dall'elenco il lavoratore desiderato.</span><span class="sxs-lookup"><span data-stu-id="ec619-116">In the list, select the worker you want to use.</span></span>
7. <span data-ttu-id="ec619-117">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="ec619-117">Click Select.</span></span>
8. <span data-ttu-id="ec619-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ec619-118">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="ec619-119">Creare righe di giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="ec619-119">Create journal lines</span></span>
1. <span data-ttu-id="ec619-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ec619-120">Click New.</span></span>
2. <span data-ttu-id="ec619-121">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec619-121">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="ec619-122">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ec619-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ec619-123">Se si utilizza la società di dati dimostrativi USMF, selezionare 'A0001'.</span><span class="sxs-lookup"><span data-stu-id="ec619-123">If you are using demo data company USMF, select 'A0001'.</span></span>  
4. <span data-ttu-id="ec619-124">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec619-124">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ec619-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ec619-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ec619-126">Se si utilizza la società di dati dimostrativi USMF, selezionare il sito '2'.</span><span class="sxs-lookup"><span data-stu-id="ec619-126">If you are using demo data company USMF, select site '2'.</span></span>  
6. <span data-ttu-id="ec619-127">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec619-127">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ec619-128">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ec619-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ec619-129">Se si utilizza la società di dati dimostrativi USMF, selezionare il magazzino '24'.</span><span class="sxs-lookup"><span data-stu-id="ec619-129">If you are using demo data company USMF, select warehouse '24'.</span></span>  
8. <span data-ttu-id="ec619-130">Nel campo Ubicazione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec619-130">In the Location field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="ec619-131">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ec619-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ec619-132">Se si utilizza la società di dati dimostrativi USMF, selezionare l'ubicazione 'BULK-001'.</span><span class="sxs-lookup"><span data-stu-id="ec619-132">If you are using demo data company USMF, select location 'BULK-001'</span></span>  
10. <span data-ttu-id="ec619-133">Nel campo Conteggiato immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ec619-133">In the Counted field, enter a number.</span></span>
    * <span data-ttu-id="ec619-134">Se si immette un numero diverso dal numero indicato nel campo Disponibilità, il campo Quantità viene aggiornato per visualizzare la discrepanza.</span><span class="sxs-lookup"><span data-stu-id="ec619-134">If you enter a counted number that’s different to the number shown in the On-hand field, the Quantity field is updated to show the discrepancy.</span></span>  
11. <span data-ttu-id="ec619-135">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ec619-135">Click Save.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="ec619-136">Registrare il giornale di registrazione conteggi scorte</span><span class="sxs-lookup"><span data-stu-id="ec619-136">Post the inventory counting journal</span></span>
1. <span data-ttu-id="ec619-137">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="ec619-137">Click Post.</span></span>
    * <span data-ttu-id="ec619-138">Durante la registrazione di giornale di registrazione conteggio scorte, se l'importo conteggiato è diverso dall'importo che viene dichiarato nel campo Disponibilità, viene registrata un'entrata o un'uscita dal magazzino, vengono modificati il livello e il valore delle scorte e vengono generate le transazioni contabili.</span><span class="sxs-lookup"><span data-stu-id="ec619-138">When you post an inventory counting journal, if the counted amount differs from amount that’s reported in the On-hand field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
2. <span data-ttu-id="ec619-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ec619-139">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="ec619-140">Visualizza operazioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="ec619-140">View inventory transactions</span></span>
1. <span data-ttu-id="ec619-141">Fare clic su Scorte.</span><span class="sxs-lookup"><span data-stu-id="ec619-141">Click Inventory.</span></span>
2. <span data-ttu-id="ec619-142">Fare clic su Transazioni.</span><span class="sxs-lookup"><span data-stu-id="ec619-142">Click Transactions.</span></span>
    * <span data-ttu-id="ec619-143">È possibile visualizzare tutte le transazioni correlate che verranno create quando si registra il giornale di registrazione conteggi scorte.</span><span class="sxs-lookup"><span data-stu-id="ec619-143">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

