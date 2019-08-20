---
title: Trasferire l'inventario fisico all'interno del magazzino
description: In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione trasferimento scorte in modo da registrare lo spostamento di un articolo da un'ubicazione di un magazzino a un'altra.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7344bfa3be0d7345d3ac68202c7bc26bcac8ebb9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845259"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="7c4b1-103">Trasferire l'inventario fisico all'interno del magazzino</span><span class="sxs-lookup"><span data-stu-id="7c4b1-103">Transfer physical inventory within the warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7c4b1-104">In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione trasferimento scorte in modo da registrare lo spostamento di un articolo da un'ubicazione di un magazzino a un'altra.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="7c4b1-105">È necessario disporre di un nome del giornale di registrazione magazzino configurato per i trasferimenti scorte prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="7c4b1-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF utilizzando i valori di esempio visualizzati o è possibile utilizzare propri dati se prodotti e ubicazioni sono stati configurati.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="7c4b1-107">Queste attività verranno in genere svolte da un dipendente del magazzino.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="7c4b1-108">Creare un giornale di registrazione trasferimento scorte</span><span class="sxs-lookup"><span data-stu-id="7c4b1-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="7c4b1-109">Passare a Trasferimenti.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-109">Go to Transfer.</span></span>
2. <span data-ttu-id="7c4b1-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-110">Click New.</span></span>
3. <span data-ttu-id="7c4b1-111">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-111">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="7c4b1-112">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-112">Click OK.</span></span>
    * <span data-ttu-id="7c4b1-113">È presente l'opzione per specificare le dimensioni 'Da' e 'A' per ogni riga del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="7c4b1-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="7c4b1-114">che sono per questo tipo di giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-114">These are essential for this journal type.</span></span> <span data-ttu-id="7c4b1-115">È possibile trasferire gli articoli nelle ubicazioni utilizzando regole diverse.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="7c4b1-116">In questo esempio verrà trasferito un articolo all'interno dello stesso magazzino, da un'ubicazione controllata da targa a un'ubicazione non controllata da targa.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-116">In this example we’ll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="7c4b1-117">Creare righe di giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="7c4b1-117">Create journal lines</span></span>
1. <span data-ttu-id="7c4b1-118">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-118">Click New.</span></span>
2. <span data-ttu-id="7c4b1-119">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="7c4b1-120">Se si utilizza USMF, è possibile selezionare 'A0001'.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="7c4b1-121">Nel campo Dal sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-121">In the From site field, enter or select a value.</span></span>
    * <span data-ttu-id="7c4b1-122">Se si utilizza USMF, è possibile selezionare '2'.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="7c4b1-123">Nel campo Al sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-123">In the To site field, enter or select a value.</span></span>
    * <span data-ttu-id="7c4b1-124">Se si utilizza USMF, è possibile selezionare '2'.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="7c4b1-125">Nel campo Magazzino origine immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-125">In the From warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="7c4b1-126">Se si utilizza USMF, è possibile selezionare '24'.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="7c4b1-127">Nel campo Magazzino destinazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-127">In the To warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="7c4b1-128">Se si utilizza USMF, è possibile selezionare '24'.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="7c4b1-129">Nel campo Ubicazione origine immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-129">In the From location field, enter or select a value.</span></span>
    * <span data-ttu-id="7c4b1-130">Se si utilizza USMF, è possibile selezionare 'FL-001'.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="7c4b1-131">Nel campo Ubicazione destinazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-131">In the To location field, enter or select a value.</span></span>
    * <span data-ttu-id="7c4b1-132">Se si utilizza USMF, è possibile selezionare 'BULK-001'.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="7c4b1-133">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-133">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="7c4b1-134">Fare clic sulla scheda Dimensioni inventariali.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-134">Click the Inventory dimensions tab.</span></span>
11. <span data-ttu-id="7c4b1-135">Nel campo Targa immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-135">In the License plate field, enter or select a value.</span></span>
    * <span data-ttu-id="7c4b1-136">Se si utilizza USMF, è possibile selezionare '24'.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="7c4b1-137">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-137">Click Save.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="7c4b1-138">Registrare il giornale di registrazione trasferimento scorte</span><span class="sxs-lookup"><span data-stu-id="7c4b1-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="7c4b1-139">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-139">Click Post.</span></span>
2. <span data-ttu-id="7c4b1-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-140">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="7c4b1-141">Visualizza operazioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="7c4b1-141">View inventory transactions</span></span>
1. <span data-ttu-id="7c4b1-142">Fare clic su Scorte.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-142">Click Inventory.</span></span>
2. <span data-ttu-id="7c4b1-143">Fare clic su Transazioni.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-143">Click Transactions.</span></span>
    * <span data-ttu-id="7c4b1-144">È possibile visualizzare le transazioni create quando è stato registrato il giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="7c4b1-144">Here you can see the transactions that were created when you posted your journal.</span></span>  

