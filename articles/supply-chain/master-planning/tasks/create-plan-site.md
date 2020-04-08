---
title: Creare un piano per un sito
description: Il pianificatore di produzione calcola i fabbisogni di capacità e materiali per la produzione di un articolo specifico.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13238818de10596de34eaf9d8cd7d55562a307eb
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150311"
---
# <a name="create-a-plan-for-a-site"></a><span data-ttu-id="4eb5b-103">Creare un piano per un sito</span><span class="sxs-lookup"><span data-stu-id="4eb5b-103">Create a plan for a site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4eb5b-104">Il pianificatore di produzione calcola i fabbisogni di capacità e materiali per la produzione di un articolo specifico.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-104">The production planner calculates the material and capacity requirements for the production of a specific item.</span></span> <span data-ttu-id="4eb5b-105">Una volta creati i suggerimenti di approvvigionamento, trova gli ordini presso il sito per il quale effettua la pianificazione e consolida gli ordini, a partire da quelli urgenti.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-105">After the sourcing suggestions are created, he finds the orders at the site for which he is planning and firms the orders, starting from the urgent ones.</span></span> <span data-ttu-id="4eb5b-106">Gli ordini più urgenti sono quelli che devono essere consolidati alla data corrente.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-106">The most urgent orders are the ones that need to be firmed on the current date.</span></span> <span data-ttu-id="4eb5b-107">Utilizzare la società di dati dimostrativi USMF per eseguire queste attività.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-107">Use the demo data company USMF to perform these tasks.</span></span>


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a><span data-ttu-id="4eb5b-108">Creare un piano di capacità e materiali per un articolo</span><span class="sxs-lookup"><span data-stu-id="4eb5b-108">Create a materials and capacity plan for an item</span></span>
1. <span data-ttu-id="4eb5b-109">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-109">Click Master planning.</span></span>
    * <span data-ttu-id="4eb5b-110">È necessario passare al dashboard predefinito.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-110">You need to navigate to the default Dashboard.</span></span>  
2. <span data-ttu-id="4eb5b-111">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-111">Click Run.</span></span>
3. <span data-ttu-id="4eb5b-112">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-112">Expand the Records to include section.</span></span>
4. <span data-ttu-id="4eb5b-113">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-113">Click Filter.</span></span>
5. <span data-ttu-id="4eb5b-114">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-114">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="4eb5b-115">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-115">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="4eb5b-116">Esempio: D0001</span><span class="sxs-lookup"><span data-stu-id="4eb5b-116">Example: D0001</span></span>  
7. <span data-ttu-id="4eb5b-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-117">Click OK.</span></span>
8. <span data-ttu-id="4eb5b-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-118">Click OK.</span></span>
    * <span data-ttu-id="4eb5b-119">Il processo può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-119">This may take a few minutes.</span></span>  
9. <span data-ttu-id="4eb5b-120">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-120">Refresh the page.</span></span>

## <a name="identify-the-urgent-planned-orders-for-the-item"></a><span data-ttu-id="4eb5b-121">Identificare gli ordini urgenti pianificati per l'articolo</span><span class="sxs-lookup"><span data-stu-id="4eb5b-121">Identify the urgent planned orders for the item</span></span>
1. <span data-ttu-id="4eb5b-122">Aprire il filtro dalla colonna Numero articolo.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-122">Open Item number column filter.</span></span>
2. <span data-ttu-id="4eb5b-123">Applicare un filtro sul campo "Numero articolo" con un valore pari a "D0001" tramite l'operatore di filtro "inizia con".</span><span class="sxs-lookup"><span data-stu-id="4eb5b-123">Apply a filter on the "Item number" field, with a value of "D0001", using the "begins with" filter operator.</span></span>
3. <span data-ttu-id="4eb5b-124">Aprire il filtro della colonna Data ordine.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-124">Open Order date column filter.</span></span>
4. <span data-ttu-id="4eb5b-125">Applicare un filtro nel campo "Data ordine", con un valore di data corrente, utilizzando l'operatore "è esattamente".</span><span class="sxs-lookup"><span data-stu-id="4eb5b-125">Apply a filter on the "Order date" field, with a value of current date, using the "is exactly" filter operator.</span></span>

## <a name="firm-all-the-urgent-orders-for-the-item"></a><span data-ttu-id="4eb5b-126">Stabilizzare tutti gli ordini urgenti per l'articolo</span><span class="sxs-lookup"><span data-stu-id="4eb5b-126">Firm all the urgent orders for the item</span></span>
1. <span data-ttu-id="4eb5b-127">Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-127">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="4eb5b-128">Fare clic su Stabilizza.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-128">Click Firm.</span></span>
3. <span data-ttu-id="4eb5b-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4eb5b-129">Click OK.</span></span>

