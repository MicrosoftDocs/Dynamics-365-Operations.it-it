--- 
title: Rilasciare un ordine di produzione
description: Questa procedura indica come rilasciare un ordine di produzione.
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2ae2d84bd12d338c9bada5518c43178b22112006
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="release-a-production-order"></a><span data-ttu-id="2968f-103">Rilasciare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="2968f-103">Release a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2968f-104">Questa procedura indica come rilasciare un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="2968f-104">This procedure shows how to release a production order.</span></span> <span data-ttu-id="2968f-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="2968f-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2968f-106">Si tratta della quarta procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="2968f-106">This is the fourth procedure out of seven which explains the production order lifecycle.</span></span>

1. <span data-ttu-id="2968f-107">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="2968f-107">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="2968f-108">Nella griglia selezionare un ordine di produzione con lo stato Programmato.</span><span class="sxs-lookup"><span data-stu-id="2968f-108">In the grid, select a production order that has the Scheduled status.</span></span>  
2. <span data-ttu-id="2968f-109">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="2968f-109">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="2968f-110">Fare clic su Rilascia.</span><span class="sxs-lookup"><span data-stu-id="2968f-110">Click Release.</span></span>
    * <span data-ttu-id="2968f-111">In questa pagina, è possibile confermare il rilascio dell'intervallo selezionato di ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="2968f-111">On this page, you can confirm the release of the selected range of production orders.</span></span> <span data-ttu-id="2968f-112">Fare clic su Seleziona se si desidera aggiungere ordini.</span><span class="sxs-lookup"><span data-stu-id="2968f-112">Click Select if you want to add orders.</span></span>  
    * <span data-ttu-id="2968f-113">Il passaggio di rilascio indica quando l'ordine di produzione viene rilasciato allo shop floor di produzione in modo che gli operatori dello shop floor possano indicare lo stato di avanzamento nei processi di produzione.</span><span class="sxs-lookup"><span data-stu-id="2968f-113">The Release step indicates when the production order is released to the production shop floor so that the shop floor operators can report progress on the production jobs.</span></span> <span data-ttu-id="2968f-114">I documenti di produzione che contengono le informazioni rilevanti sull'elaborazione dei processi possono essere emessi.</span><span class="sxs-lookup"><span data-stu-id="2968f-114">Production papers that contain relevant information about processing the jobs can be issued.</span></span> <span data-ttu-id="2968f-115">Il lavoro del magazzino per il prelievo delle materie prime viene generato per gli articoli impostati per il processo di magazzino.</span><span class="sxs-lookup"><span data-stu-id="2968f-115">The warehouse work for raw material picking is generated for the items that are set up for the warehouse process.</span></span>  
4. <span data-ttu-id="2968f-116">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="2968f-116">Click the General tab.</span></span>
    * <span data-ttu-id="2968f-117">Selezionare i report di produzione da stampare.</span><span class="sxs-lookup"><span data-stu-id="2968f-117">Select which production reports should be printed.</span></span> <span data-ttu-id="2968f-118">Il report della scheda processi stampa una pagina per ciascun processo programmato e richiede che l'ordine di produzione venga programmato a livello di processo.</span><span class="sxs-lookup"><span data-stu-id="2968f-118">The Job card report prints a page for each scheduled job and requires the production order to be scheduled at the job level.</span></span> <span data-ttu-id="2968f-119">Il report contiene informazioni sull'ora di inizio e di fine programmata, la quantità da produrre e la risorsa che elabora il processo.</span><span class="sxs-lookup"><span data-stu-id="2968f-119">The report contains information about the scheduled start and end time, the quantity to produce, and which resource processes the job.</span></span> <span data-ttu-id="2968f-120">Il report del processo del ciclo di lavorazione raccoglie le stesse informazioni nella stessa pagina, ma non stampa una pagina per ciascun processo.</span><span class="sxs-lookup"><span data-stu-id="2968f-120">The Route job report collects the same information on the same page, but does not print a page for each job.</span></span> <span data-ttu-id="2968f-121">Nel report Scheda del ciclo di lavorazione vengono visualizzate solo le operazioni ma non i processi.</span><span class="sxs-lookup"><span data-stu-id="2968f-121">The Route card report only shows the operations but not the jobs.</span></span> <span data-ttu-id="2968f-122">Di conseguenza, il report non richiede la programmazione dei processi, ma può essere utilizzato quando gli ordini di produzione vengono programmati a livello di operazione.</span><span class="sxs-lookup"><span data-stu-id="2968f-122">Therefore, this report does not require job scheduling, but can be used when production orders are scheduled at the operation level.</span></span>  
5. <span data-ttu-id="2968f-123">Fare clic sulla casella di controllo Stampa scheda ciclo di lav.</span><span class="sxs-lookup"><span data-stu-id="2968f-123">Click the Print route card checkbox.</span></span>
6. <span data-ttu-id="2968f-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2968f-124">Click OK.</span></span>
7. <span data-ttu-id="2968f-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2968f-125">Close the page.</span></span>

