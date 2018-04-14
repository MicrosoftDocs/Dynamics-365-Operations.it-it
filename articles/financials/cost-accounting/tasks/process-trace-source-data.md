--- 
title: Elaborare e tenere traccia dei dati di origine
description: Tutte le elaborazione dei dati vengono eseguite da processi.
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 57884660fb9459c8cd918e5d1ba4df14efcf6db3
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="process-and-trace-source-data"></a><span data-ttu-id="8dd80-103">Elaborare e tenere traccia dei dati di origine</span><span class="sxs-lookup"><span data-stu-id="8dd80-103">Process and trace source data</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8dd80-104">Tutte le elaborazione dei dati vengono eseguite da processi.</span><span class="sxs-lookup"><span data-stu-id="8dd80-104">All data processing is run by jobs.</span></span> <span data-ttu-id="8dd80-105">Per ogni processo e provider di dati, viene creato un giornale di registrazione per documentare che il processo è stato eseguito e che le voci sono state elaborate nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="8dd80-105">For each job and data provider, a journal is created to document that the process has been run, and that the entries were processed in the current job.</span></span> <span data-ttu-id="8dd80-106">Utilizzare questa procedura per impostare un'origine dati e per tenere traccia di una voce di costo specifica.</span><span class="sxs-lookup"><span data-stu-id="8dd80-106">Use this procedure to set up a data source and then  trace the origin of a specific cost entry.</span></span> <span data-ttu-id="8dd80-107">Questa registrazione utilizza i dati dimostrativi della società USP2.</span><span class="sxs-lookup"><span data-stu-id="8dd80-107">This recording uses the USP2 demo data company USP2.</span></span> <span data-ttu-id="8dd80-108">Prima di completare questa attività, verificare di aver eseguito le guide attività "Creare un movimento CoGe di contabilità industriale", "Definire unità di controllo costi" e "Gestire l'origine dati per il movimento CoGe di contabilità industriale".</span><span class="sxs-lookup"><span data-stu-id="8dd80-108">Before you complete this task, make sure that you play the following task guides: "Create a cost accounting ledger," "Define cost control units," and "Manage data source for the cost accounting ledger."</span></span>

1. <span data-ttu-id="8dd80-109">Andare a Contabilità industriale > Impostazione contabilità generale > Movimenti CoGe di contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="8dd80-109">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="8dd80-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8dd80-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8dd80-111">Selezionare il movimento CoGe della contabilità industriale creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8dd80-111">Select the cost accounting ledger that you created earlier.</span></span>  
3. <span data-ttu-id="8dd80-112">Fare clic su Versioni effettive.</span><span class="sxs-lookup"><span data-stu-id="8dd80-112">Click Actual versions.</span></span>
4. <span data-ttu-id="8dd80-113">Fare clic su Elaborazione dati di origine nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="8dd80-113">On the Action Pane, click Source data processing.</span></span>
5. <span data-ttu-id="8dd80-114">Fare clic su Giornali di registrazione trasferimenti voci di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="8dd80-114">Click General ledger entry transfer journals.</span></span>
6. <span data-ttu-id="8dd80-115">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8dd80-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="8dd80-116">Fare clic su Inserimenti nel giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8dd80-116">Click Journal entries.</span></span>
8. <span data-ttu-id="8dd80-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8dd80-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="8dd80-118">Fare clic su Voci di costo.</span><span class="sxs-lookup"><span data-stu-id="8dd80-118">Click Cost entries.</span></span>
10. <span data-ttu-id="8dd80-119">Fare clic su Voce di origine.</span><span class="sxs-lookup"><span data-stu-id="8dd80-119">Click Source entry.</span></span>
11. <span data-ttu-id="8dd80-120">Fare clic su Elaborazione dati di origine nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="8dd80-120">On the Action Pane, click Source data processing.</span></span>
12. <span data-ttu-id="8dd80-121">Fare clic su Contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="8dd80-121">Click General ledger.</span></span>
13. <span data-ttu-id="8dd80-122">Nel campo Periodo di calendario fiscale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8dd80-122">In the Fiscal calendar period field, enter or select a value.</span></span>
    * <span data-ttu-id="8dd80-123">Per questo esempio, selezionare il periodo 9 dell'anno fiscale 2017.</span><span class="sxs-lookup"><span data-stu-id="8dd80-123">For this example, select Fiscal 2017 Period 9.</span></span>  
14. <span data-ttu-id="8dd80-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8dd80-124">Click OK.</span></span>


