---
title: Correggere le informazioni di tracciabilità di magazzino
description: In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione trasferimenti scorte per correggere le informazioni di tracciabilità inventario.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a8a488d4c30923445b3ebc2626a79b8fa45012c7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431416"
---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="fb112-103">Correggere le informazioni di tracciabilità di magazzino</span><span class="sxs-lookup"><span data-stu-id="fb112-103">Correct inventory tracking information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fb112-104">In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione trasferimenti scorte per correggere le informazioni di tracciabilità inventario.</span><span class="sxs-lookup"><span data-stu-id="fb112-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="fb112-105">In questo esempio, si aggiornano le informazioni di un articolo controllato da batch modificando un batch registrato in modo non corretto con un altro batch.</span><span class="sxs-lookup"><span data-stu-id="fb112-105">In this example, we'll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="fb112-106">È possibile eseguire questa procedura nella società di dati dimostrativi USPI oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="fb112-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="fb112-107">Se si utilizzano propri dati, è necessario disporre di un articolo che supporta i batch e che non è controllato da ubicazione.</span><span class="sxs-lookup"><span data-stu-id="fb112-107">If you use your own data, you need to have an item that's batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="fb112-108">È inoltre necessario disporre di un nome del giornale di registrazione magazzino configurato per i trasferimenti scorte.</span><span class="sxs-lookup"><span data-stu-id="fb112-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="fb112-109">Queste attività verranno in genere svolte da un dipendente del magazzino.</span><span class="sxs-lookup"><span data-stu-id="fb112-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="fb112-110">Creare un giornale di registrazione trasferimento scorte</span><span class="sxs-lookup"><span data-stu-id="fb112-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="fb112-111">Passare a Trasferimenti.</span><span class="sxs-lookup"><span data-stu-id="fb112-111">Go to Transfer.</span></span>
2. <span data-ttu-id="fb112-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fb112-112">Click New.</span></span>
3. <span data-ttu-id="fb112-113">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb112-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="fb112-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fb112-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="fb112-115">Creare righe di giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="fb112-115">Create journal lines</span></span>
1. <span data-ttu-id="fb112-116">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fb112-116">Click New.</span></span>
2. <span data-ttu-id="fb112-117">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb112-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="fb112-118">Se si utilizza USPI, selezionare l'articolo M5003.</span><span class="sxs-lookup"><span data-stu-id="fb112-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="fb112-119">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="fb112-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="fb112-120">Fare clic sulla scheda Dimensioni inventariali.</span><span class="sxs-lookup"><span data-stu-id="fb112-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="fb112-121">Nel campo Numero batch immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb112-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="fb112-122">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb112-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="fb112-123">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb112-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="fb112-124">Nel campo Numero batch immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb112-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="fb112-125">Registra il giornale</span><span class="sxs-lookup"><span data-stu-id="fb112-125">Post the journal</span></span>
1. <span data-ttu-id="fb112-126">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="fb112-126">Click Post.</span></span>
2. <span data-ttu-id="fb112-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fb112-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="fb112-128">Controllare le informazioni di traccia</span><span class="sxs-lookup"><span data-stu-id="fb112-128">Check tracing information</span></span>
1. <span data-ttu-id="fb112-129">Fare clic su Scorte.</span><span class="sxs-lookup"><span data-stu-id="fb112-129">Click Inventory.</span></span>
2. <span data-ttu-id="fb112-130">Fare clic su Traccia.</span><span class="sxs-lookup"><span data-stu-id="fb112-130">Click Trace.</span></span>
3. <span data-ttu-id="fb112-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fb112-131">Click OK.</span></span>
    * <span data-ttu-id="fb112-132">Con queste informazioni di traccia è possibile tracciare a ritroso da quale batch è iniziata la correzione dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="fb112-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="fb112-133">È inoltre possibile utilizzare la pagina Tracciabilità articolo per visualizzare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="fb112-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="fb112-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fb112-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="fb112-135">Controllare le transazioni di inventario</span><span class="sxs-lookup"><span data-stu-id="fb112-135">Check inventory transactions</span></span>
1. <span data-ttu-id="fb112-136">Fare clic su Scorte.</span><span class="sxs-lookup"><span data-stu-id="fb112-136">Click Inventory.</span></span>
2. <span data-ttu-id="fb112-137">Fare clic su Transazioni.</span><span class="sxs-lookup"><span data-stu-id="fb112-137">Click Transactions.</span></span>
    * <span data-ttu-id="fb112-138">È possibile visualizzare le transazioni create quando è stato registrato il giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fb112-138">Here you can see the transactions that were created when you posted your journal.</span></span>   

