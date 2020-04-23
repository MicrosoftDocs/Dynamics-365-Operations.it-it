---
title: Creare una programmazione per un sito
description: Questa procedura mostra come programmare gli ordini di produzione non ancora iniziati per un sito.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bc2dc4a03f9d937339ec2470f6a065f77c7036a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209630"
---
# <a name="create-a-schedule-for-a-site"></a><span data-ttu-id="9b4d9-103">Creare una programmazione per un sito</span><span class="sxs-lookup"><span data-stu-id="9b4d9-103">Create a schedule for a site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9b4d9-104">Questa procedura mostra come programmare gli ordini di produzione non ancora iniziati per un sito.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-104">This procedure shows how to schedule production orders that are not yet started for a site.</span></span>  <span data-ttu-id="9b4d9-105">Per completare questa procedura viene utilizzata la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-105">The demo data company USMF is used to complete this procedure.</span></span>


## <a name="identify-production-orders-that-are-not-started"></a><span data-ttu-id="9b4d9-106">Individuare gli ordini di produzione non ancora avviati</span><span class="sxs-lookup"><span data-stu-id="9b4d9-106">Identify production orders that are not started</span></span>
1. <span data-ttu-id="9b4d9-107">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-107">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="9b4d9-108">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="9b4d9-109">Ad esempio, applicare un filtro nel campo Sito con un valore "1".</span><span class="sxs-lookup"><span data-stu-id="9b4d9-109">For example, filter on the Site field with a value of '1'.</span></span>
    * <span data-ttu-id="9b4d9-110">1 rappresenta un sito in USMF.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-110">1 represents a site in USMF.</span></span> <span data-ttu-id="9b4d9-111">Se non si utilizza USMF, selezionare un sito della propria società.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-111">If you are not using USMF, select a site from your own company.</span></span>  
3. <span data-ttu-id="9b4d9-112">Aprire il filtro della colonna Stato.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-112">Open the Status column filter.</span></span>
4. <span data-ttu-id="9b4d9-113">Applicare un filtro nel campo "Stato", con un valore di "Programmato", utilizzando l'operatore "è esattamente".</span><span class="sxs-lookup"><span data-stu-id="9b4d9-113">Apply a filter on the "Status" field, with a value of "Scheduled", using the "is exactly" filter operator.</span></span>

## <a name="create-a-schedule"></a><span data-ttu-id="9b4d9-114">Creare una programmazione</span><span class="sxs-lookup"><span data-stu-id="9b4d9-114">Create a schedule</span></span>
1. <span data-ttu-id="9b4d9-115">Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-115">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="9b4d9-116">Nel riquadro azioni fare clic su Programmazione.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-116">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="9b4d9-117">Fare clic su Programma processi.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-117">Click Schedule jobs.</span></span>
4. <span data-ttu-id="9b4d9-118">Nel campo di direzione di programmazione, selezionare "Indietro da data di consegna".</span><span class="sxs-lookup"><span data-stu-id="9b4d9-118">In the Scheduling direction field, select 'Backward from delivery date'.</span></span>
5. <span data-ttu-id="9b4d9-119">Selezionare No nel campo Capacità limitata.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-119">Select No in the Finite capacity field.</span></span>
6. <span data-ttu-id="9b4d9-120">Selezionare No nel campo Materiale limitato.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-120">Select No in the Finite material field.</span></span>
7. <span data-ttu-id="9b4d9-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-121">Click OK.</span></span>
    * <span data-ttu-id="9b4d9-122">Questa operazione potrebbe richiedere tempo.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-122">This may take a while.</span></span>  

## <a name="view-the-result-of-scheduled-production-orders"></a><span data-ttu-id="9b4d9-123">Visualizzare il risultato degli ordini di produzione programmati</span><span class="sxs-lookup"><span data-stu-id="9b4d9-123">View the result of scheduled production orders</span></span>
1. <span data-ttu-id="9b4d9-124">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-124">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9b4d9-125">È possibile contrassegnare qualsiasi riga.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-125">You can mark any row.</span></span>  
2. <span data-ttu-id="9b4d9-126">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-126">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="9b4d9-127">Fare clic su Tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-127">Click All jobs.</span></span>
    * <span data-ttu-id="9b4d9-128">In questa pagina è possibile visualizzare l'elenco dei processi.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-128">On this page, you can see the list of jobs.</span></span> <span data-ttu-id="9b4d9-129">Nella scheda di programmazione è possibile visualizzare la data di inizio e di fine di un processo.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-129">On the Scheduling tab, you can see the Start date and End date for a job.</span></span>  
4. <span data-ttu-id="9b4d9-130">Fare clic su Materiali.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-130">Click Materials.</span></span>
    * <span data-ttu-id="9b4d9-131">In questa pagina è possibile visualizzare il consumo stimato dei materiali per le operazioni presenti nell'ordine di produzione e le scorte correnti disponibili.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-131">On this page, you can see the estimated material consumption for the operations on the production order and the current available inventory.</span></span>  

