---
title: Creare un prodotto finito (solo febbraio 2016)
description: Questa attività consente di creare un prodotto finito.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44f9693e04160ffe9307de5e454d8269ca883679
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "339029"
---
# <a name="create-a-finished-product-february-2016-only"></a><span data-ttu-id="578f0-103">Creare un prodotto finito (solo febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="578f0-103">Create a finished product (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="578f0-104">Questa attività consente di creare un prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="578f0-104">This task focuses on creating a finished product.</span></span> <span data-ttu-id="578f0-105">Corrisponde alla prima attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="578f0-105">It is the first task in the BOM calculation series.</span></span> <span data-ttu-id="578f0-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="578f0-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="578f0-107">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="578f0-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="578f0-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="578f0-108">Click New.</span></span>
3. <span data-ttu-id="578f0-109">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="578f0-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="578f0-110">Per la dimostrazione, digitare BOM_1.</span><span class="sxs-lookup"><span data-stu-id="578f0-110">For the demonstration, type BOM_1.</span></span>  
4. <span data-ttu-id="578f0-111">Nel campo Gruppo modello articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="578f0-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="578f0-112">Selezionare STD.</span><span class="sxs-lookup"><span data-stu-id="578f0-112">Select STD.</span></span> <span data-ttu-id="578f0-113">STD sta per costo standard ed è il modello più utilizzato quando si lavora con i calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="578f0-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="578f0-114">Nel campo Gruppo di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="578f0-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="578f0-115">Selezionare, ad esempio Audio.</span><span class="sxs-lookup"><span data-stu-id="578f0-115">For example, select Audio.</span></span> <span data-ttu-id="578f0-116">Ciò non ha effetto sui calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="578f0-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="578f0-117">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="578f0-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="578f0-118">Selezionare SiteWH.</span><span class="sxs-lookup"><span data-stu-id="578f0-118">Select SiteWH.</span></span> <span data-ttu-id="578f0-119">Solo sito e magazzino verranno utilizzati per la dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="578f0-119">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="578f0-120">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="578f0-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="578f0-121">Le dimensioni di tracciabilità non verranno utilizzate in questo esempio, selezionare Nessuno.</span><span class="sxs-lookup"><span data-stu-id="578f0-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="578f0-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="578f0-122">Click OK.</span></span>
9. <span data-ttu-id="578f0-123">Nel riquadro azioni, fare clic su Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="578f0-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="578f0-124">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="578f0-124">Click Default order settings.</span></span>
11. <span data-ttu-id="578f0-125">Nel campo Tipo di ordine predefinito selezionare 'Production'.</span><span class="sxs-lookup"><span data-stu-id="578f0-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="578f0-126">Poiché si sta producendo un prodotto finito, selezionare Produzione.</span><span class="sxs-lookup"><span data-stu-id="578f0-126">Because this is a finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="578f0-127">Nel campo Sito acquisto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="578f0-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="578f0-128">Per la dimostrazione, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="578f0-128">For the demonstration, select Site 1.</span></span>  
13. <span data-ttu-id="578f0-129">Nel campo Sito magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="578f0-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="578f0-130">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="578f0-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="578f0-131">Nel campo Sito vendite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="578f0-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="578f0-132">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="578f0-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="578f0-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="578f0-133">Close the page.</span></span>

