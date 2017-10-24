--- 
title: Aggiornare lo stato del processo kanban
description: "Quando un kanban viene svuotato per errore o un kanban ricevuto deve essere svuotato, è necessario aggiornare lo stato del kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3c2b5a5fbfc5bd83cc68ffafaa243dac9244c003
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="update-kanban-status"></a><span data-ttu-id="747d8-103">Aggiornare lo stato del processo kanban</span><span class="sxs-lookup"><span data-stu-id="747d8-103">Update kanban status</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="747d8-104">Quando un kanban viene svuotato per errore o un kanban ricevuto deve essere svuotato, è necessario aggiornare lo stato del kanban.</span><span class="sxs-lookup"><span data-stu-id="747d8-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="747d8-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="747d8-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="747d8-106">Questa procedura è destinata al supervisore.</span><span class="sxs-lookup"><span data-stu-id="747d8-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="747d8-107">Individuare il kanban.</span><span class="sxs-lookup"><span data-stu-id="747d8-107">Find the kanban.</span></span>
1. <span data-ttu-id="747d8-108">Andare a Controllo produzione > Kanban > Kanban.</span><span class="sxs-lookup"><span data-stu-id="747d8-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="747d8-109">Aprire il filtro della colonna Stato unità movimentazione.</span><span class="sxs-lookup"><span data-stu-id="747d8-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="747d8-110">Fare clic su Cancella.</span><span class="sxs-lookup"><span data-stu-id="747d8-110">Click Clear.</span></span>
    * <span data-ttu-id="747d8-111">Vengono reimpostati i filtri.</span><span class="sxs-lookup"><span data-stu-id="747d8-111">This resets the filters.</span></span>  
4. <span data-ttu-id="747d8-112">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="747d8-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="747d8-113">Ad esempio, filtrare il campo Numero carta in base a un valore "000149".</span><span class="sxs-lookup"><span data-stu-id="747d8-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="747d8-114">Modificare da stato svuotato in stato ricevuto</span><span class="sxs-lookup"><span data-stu-id="747d8-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="747d8-115">Fare clic su Ripristina unità movimentazione vuota.</span><span class="sxs-lookup"><span data-stu-id="747d8-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="747d8-116">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="747d8-116">Click OK.</span></span>
    * <span data-ttu-id="747d8-117">Lo stato dell'unità movimentazione è Ricevuto.</span><span class="sxs-lookup"><span data-stu-id="747d8-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="747d8-118">Modificare da stato ricevuto in stato svuotato</span><span class="sxs-lookup"><span data-stu-id="747d8-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="747d8-119">Fare clic su Svuota kanban.</span><span class="sxs-lookup"><span data-stu-id="747d8-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="747d8-120">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="747d8-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="747d8-121">Lo stato dell'unità movimentazione è Svuotato.</span><span class="sxs-lookup"><span data-stu-id="747d8-121">Notice that the Handling unit status is Emptied.</span></span>  


