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
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2fa0f0f38dcb93aff9b3a1d8130fba0a0c836b3b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981108"
---
# <a name="schedule-a-production-order"></a><span data-ttu-id="3eb42-103">Programmare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="3eb42-103">Schedule a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3eb42-104">Questa procedura indica come programmare un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="3eb42-104">This procedure shows how to schedule a production order.</span></span> <span data-ttu-id="3eb42-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="3eb42-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3eb42-106">Si tratta della terza procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="3eb42-106">This is the third procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="schedule-a-production-order"></a><span data-ttu-id="3eb42-107">Programmare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="3eb42-107">Schedule a production order</span></span>
1. <span data-ttu-id="3eb42-108">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="3eb42-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="3eb42-109">Selezionare un ordine di produzione con stato Stimato.</span><span class="sxs-lookup"><span data-stu-id="3eb42-109">Select a production order that has the Estimated status.</span></span>  
2. <span data-ttu-id="3eb42-110">Nel riquadro azioni fare clic su Programmazione.</span><span class="sxs-lookup"><span data-stu-id="3eb42-110">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="3eb42-111">Fare clic su Programma processi.</span><span class="sxs-lookup"><span data-stu-id="3eb42-111">Click Schedule jobs.</span></span>
    * <span data-ttu-id="3eb42-112">I parametri per la programmazione vengono impostati in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="3eb42-112">The parameters for scheduling are set up on this page.</span></span> <span data-ttu-id="3eb42-113">È possibile impostare i parametri per utenti specifici o per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3eb42-113">You can set up the parameters for specific users or all users.</span></span>  
4. <span data-ttu-id="3eb42-114">Nel campo di direzione di programmazione, selezionare "Avanti da oggi".</span><span class="sxs-lookup"><span data-stu-id="3eb42-114">In the Scheduling direction field, select 'Forward from today'.</span></span>
5. <span data-ttu-id="3eb42-115">Immettere una data nel campo Data di programmazione.</span><span class="sxs-lookup"><span data-stu-id="3eb42-115">In the Scheduling date field, enter a date.</span></span>
6. <span data-ttu-id="3eb42-116">Selezionare o deselezionare la casella di controllo Capacità limitata.</span><span class="sxs-lookup"><span data-stu-id="3eb42-116">Select or clear the Finite capacity check box.</span></span>
7. <span data-ttu-id="3eb42-117">Selezionare o deselezionare la casella di controllo Materiale limitato.</span><span class="sxs-lookup"><span data-stu-id="3eb42-117">Select or clear the Finite material check box.</span></span>
8. <span data-ttu-id="3eb42-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3eb42-118">Click OK.</span></span>

## <a name="view-the-scheduling-results"></a><span data-ttu-id="3eb42-119">Visualizzare i risultati della programmazione</span><span class="sxs-lookup"><span data-stu-id="3eb42-119">View the scheduling results</span></span>
1. <span data-ttu-id="3eb42-120">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="3eb42-120">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="3eb42-121">Fare clic su Tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="3eb42-121">Click All jobs.</span></span>
    * <span data-ttu-id="3eb42-122">In questa pagina vengono visualizzati i processi programmati appena generati.</span><span class="sxs-lookup"><span data-stu-id="3eb42-122">This page displays the scheduled jobs that you have just generated.</span></span>  
3. <span data-ttu-id="3eb42-123">Espandere o comprimere la sezione Programmazione.</span><span class="sxs-lookup"><span data-stu-id="3eb42-123">Expand or collapse the Scheduling section.</span></span>
    * <span data-ttu-id="3eb42-124">Nella scheda dettaglio Programmazione, è possibile visualizzare la data e l'ora programmate.</span><span class="sxs-lookup"><span data-stu-id="3eb42-124">On the Scheduling FastTab, you can view the scheduled date and time.</span></span>  
4. <span data-ttu-id="3eb42-125">Fare clic su Richieste di informazioni.</span><span class="sxs-lookup"><span data-stu-id="3eb42-125">Click Inquiries.</span></span>
5. <span data-ttu-id="3eb42-126">Fare clic su Carico di capacità.</span><span class="sxs-lookup"><span data-stu-id="3eb42-126">Click Capacity load.</span></span>
    * <span data-ttu-id="3eb42-127">Nella pagina Carico di capacità è visualizzata la capacità prenotata tramite la programmazione processi, il numero totale di ore attualmente prenotato per la risorsa e il numero di ore rimanenti e disponibili per la programmazione processi della risorsa.</span><span class="sxs-lookup"><span data-stu-id="3eb42-127">The Capacity load page displays the capacity that is reserved through job scheduling, the total number of hours that are currently reserved on the resource, and the number of hours that remain available for job scheduling on the resource.</span></span>  
6. <span data-ttu-id="3eb42-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3eb42-128">Close the page.</span></span>
7. <span data-ttu-id="3eb42-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3eb42-129">Close the page.</span></span>

