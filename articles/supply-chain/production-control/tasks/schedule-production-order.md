---
title: Programmare un ordine di produzione
description: Questa procedura indica come programmare un ordine di produzione.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b3fe8f6890c7d8ac8835503091642faa773f7f6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431108"
---
# <a name="schedule-a-production-order"></a><span data-ttu-id="8f658-103">Programmare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="8f658-103">Schedule a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8f658-104">Questa procedura indica come programmare un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8f658-104">This procedure shows how to schedule a production order.</span></span> <span data-ttu-id="8f658-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="8f658-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8f658-106">Si tratta della terza procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8f658-106">This is the third procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="schedule-a-production-order"></a><span data-ttu-id="8f658-107">Programmare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="8f658-107">Schedule a production order</span></span>
1. <span data-ttu-id="8f658-108">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="8f658-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="8f658-109">Selezionare un ordine di produzione con stato Stimato.</span><span class="sxs-lookup"><span data-stu-id="8f658-109">Select a production order that has the Estimated status.</span></span>  
2. <span data-ttu-id="8f658-110">Nel riquadro azioni fare clic su Programmazione.</span><span class="sxs-lookup"><span data-stu-id="8f658-110">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="8f658-111">Fare clic su Programma processi.</span><span class="sxs-lookup"><span data-stu-id="8f658-111">Click Schedule jobs.</span></span>
    * <span data-ttu-id="8f658-112">I parametri per la programmazione vengono impostati in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="8f658-112">The parameters for scheduling are set up on this page.</span></span> <span data-ttu-id="8f658-113">È possibile impostare i parametri per utenti specifici o per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8f658-113">You can set up the parameters for specific users or all users.</span></span>  
4. <span data-ttu-id="8f658-114">Nel campo di direzione di programmazione, selezionare "Avanti da oggi".</span><span class="sxs-lookup"><span data-stu-id="8f658-114">In the Scheduling direction field, select 'Forward from today'.</span></span>
5. <span data-ttu-id="8f658-115">Immettere una data nel campo Data di programmazione.</span><span class="sxs-lookup"><span data-stu-id="8f658-115">In the Scheduling date field, enter a date.</span></span>
6. <span data-ttu-id="8f658-116">Selezionare o deselezionare la casella di controllo Capacità limitata.</span><span class="sxs-lookup"><span data-stu-id="8f658-116">Select or clear the Finite capacity check box.</span></span>
7. <span data-ttu-id="8f658-117">Selezionare o deselezionare la casella di controllo Materiale limitato.</span><span class="sxs-lookup"><span data-stu-id="8f658-117">Select or clear the Finite material check box.</span></span>
8. <span data-ttu-id="8f658-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8f658-118">Click OK.</span></span>

## <a name="view-the-scheduling-results"></a><span data-ttu-id="8f658-119">Visualizzare i risultati della programmazione</span><span class="sxs-lookup"><span data-stu-id="8f658-119">View the scheduling results</span></span>
1. <span data-ttu-id="8f658-120">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8f658-120">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8f658-121">Fare clic su Tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="8f658-121">Click All jobs.</span></span>
    * <span data-ttu-id="8f658-122">In questa pagina vengono visualizzati i processi programmati appena generati.</span><span class="sxs-lookup"><span data-stu-id="8f658-122">This page displays the scheduled jobs that you have just generated.</span></span>  
3. <span data-ttu-id="8f658-123">Espandere o comprimere la sezione Programmazione.</span><span class="sxs-lookup"><span data-stu-id="8f658-123">Expand or collapse the Scheduling section.</span></span>
    * <span data-ttu-id="8f658-124">Nella scheda dettaglio Programmazione, è possibile visualizzare la data e l'ora programmate.</span><span class="sxs-lookup"><span data-stu-id="8f658-124">On the Scheduling FastTab, you can view the scheduled date and time.</span></span>  
4. <span data-ttu-id="8f658-125">Fare clic su Richieste di informazioni.</span><span class="sxs-lookup"><span data-stu-id="8f658-125">Click Inquiries.</span></span>
5. <span data-ttu-id="8f658-126">Fare clic su Carico di capacità.</span><span class="sxs-lookup"><span data-stu-id="8f658-126">Click Capacity load.</span></span>
    * <span data-ttu-id="8f658-127">Nella pagina Carico di capacità è visualizzata la capacità prenotata tramite la programmazione processi, il numero totale di ore attualmente prenotato per la risorsa e il numero di ore rimanenti e disponibili per la programmazione processi della risorsa.</span><span class="sxs-lookup"><span data-stu-id="8f658-127">The Capacity load page displays the capacity that is reserved through job scheduling, the total number of hours that are currently reserved on the resource, and the number of hours that remain available for job scheduling on the resource.</span></span>  
6. <span data-ttu-id="8f658-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8f658-128">Close the page.</span></span>
7. <span data-ttu-id="8f658-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8f658-129">Close the page.</span></span>

