---
title: Dichiarare lo stato di avanzamento di un dispositivo di lavoro mobile
description: Questa procedura consente di iniziare e dichiarare lo stato di avanzamento di un processo di produzione nel modulo di registrazione per il dispositivo di processo.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationTouch, JmgRegistrationTouchUserConfiguration, JmgRegistrationTouchStart, JmgRegistrationTouchReportFeedback, JmgRegistrationTouchAssignedJobs, JmgRegistrationTouchBreak, JmgRegistrationTouchLeave, JmgRegistrationTouchIndirectActivity, JmgDialogForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f5d06b0165a7a3cf7ed9dab46d0bca4d37fdc12
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "330404"
---
# <a name="report-progress-on-a-mobile-job-device"></a><span data-ttu-id="edf1c-103">Dichiarare lo stato di avanzamento di un dispositivo di lavoro mobile</span><span class="sxs-lookup"><span data-stu-id="edf1c-103">Report progress on a mobile job device</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="edf1c-104">Questa procedura consente di iniziare e dichiarare lo stato di avanzamento di un processo di produzione nel modulo di registrazione per il dispositivo di processo.</span><span class="sxs-lookup"><span data-stu-id="edf1c-104">This procedure shows you how to start and report progress on a production job in the job device registration form.</span></span>



<span data-ttu-id="edf1c-105">Per eseguire questa procedura è necessario disporre del ruolo di amministratore di sistema o di operatore macchina associato all'account utente.</span><span class="sxs-lookup"><span data-stu-id="edf1c-105">To be able to run this procedure you must have the System administator or Machine Operator role associated with the user account.</span></span>

1. <span data-ttu-id="edf1c-106">Passare a Controllo produzione > Esecuzione produzione > Dispositivo schede processo.</span><span class="sxs-lookup"><span data-stu-id="edf1c-106">Go to Production control > Manufacturing execution > Job card device.</span></span>
2. <span data-ttu-id="edf1c-107">Nel campo WorkerTextField, immettere il badge di un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="edf1c-107">In the WorkerTextField field, enter the badge of a worker.</span></span> <span data-ttu-id="edf1c-108">Nel tipo di dati dimostrativi USMF digitare '123' per Christina Portra.</span><span class="sxs-lookup"><span data-stu-id="edf1c-108">In the USMF demo data type '123' for Christina Portra..</span></span>
3. <span data-ttu-id="edf1c-109">Fare clic su Accesso.</span><span class="sxs-lookup"><span data-stu-id="edf1c-109">Click Log in.</span></span>
4. <span data-ttu-id="edf1c-110">Fare clic sul pulsante Filtro.</span><span class="sxs-lookup"><span data-stu-id="edf1c-110">Click the Filter button.</span></span>
5. <span data-ttu-id="edf1c-111">Selezionare o deselezionare la casella di controllo Applica filtro configurazione.</span><span class="sxs-lookup"><span data-stu-id="edf1c-111">Check or uncheck the Apply configuration filter check box.</span></span> <span data-ttu-id="edf1c-112">Se si imposta un filtro è possibile utilizzare l'unità di produzione 110 in USMF.</span><span class="sxs-lookup"><span data-stu-id="edf1c-112">If you set a filter you can use production unit 110 in USMF.</span></span>
6. <span data-ttu-id="edf1c-113">Nel campo Unità di produzione, selezionare i processi di produzione del gruppo di risorse con cui il lavoratore può lavorare.</span><span class="sxs-lookup"><span data-stu-id="edf1c-113">In the Production unit field, select the ressource group for which production jobs the worker can work on.</span></span>
7. <span data-ttu-id="edf1c-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="edf1c-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="edf1c-115">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="edf1c-115">Click OK.</span></span>
9. <span data-ttu-id="edf1c-116">Fare clic sul pulsante Inizio processo.</span><span class="sxs-lookup"><span data-stu-id="edf1c-116">Click the Start job button.</span></span>
10. <span data-ttu-id="edf1c-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="edf1c-117">Click OK.</span></span>
11. <span data-ttu-id="edf1c-118">Fare clic sul pulsante Segnala stato.</span><span class="sxs-lookup"><span data-stu-id="edf1c-118">Click the Report progress button.</span></span>
12. <span data-ttu-id="edf1c-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="edf1c-119">Click OK.</span></span>
13. <span data-ttu-id="edf1c-120">Fare clic sul pulsante Processo successivo.</span><span class="sxs-lookup"><span data-stu-id="edf1c-120">Click the Next job button.</span></span>
14. <span data-ttu-id="edf1c-121">Fare clic sul pulsante Assegnato per visualizzare una panoramica di tutti i processi di produzione.</span><span class="sxs-lookup"><span data-stu-id="edf1c-121">Click the Assigned to see an overview of all production jobs button.</span></span>
15. <span data-ttu-id="edf1c-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="edf1c-122">Close the page.</span></span>
16. <span data-ttu-id="edf1c-123">Fare clic sul pulsante Pausa.</span><span class="sxs-lookup"><span data-stu-id="edf1c-123">Click the Break button.</span></span>
17. <span data-ttu-id="edf1c-124">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="edf1c-124">In the list, find and select the desired record.</span></span>
18. <span data-ttu-id="edf1c-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="edf1c-125">Click OK.</span></span>
19. <span data-ttu-id="edf1c-126">Fare clic sul pulsante Uscita.</span><span class="sxs-lookup"><span data-stu-id="edf1c-126">Click the Leaving button.</span></span>
20. <span data-ttu-id="edf1c-127">Selezionare per disconnettersi.</span><span class="sxs-lookup"><span data-stu-id="edf1c-127">Select to log out.</span></span>
21. <span data-ttu-id="edf1c-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="edf1c-128">Click OK.</span></span>
22. <span data-ttu-id="edf1c-129">Nel campo WorkerTextField, eseguire di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="edf1c-129">In the WorkerTextField field, log in again.</span></span> <span data-ttu-id="edf1c-130">È possibile selezionare il lavoratore '123' se si utilizzano i dati dimostrativi di USMF.</span><span class="sxs-lookup"><span data-stu-id="edf1c-130">You can select worker '123' in USMF demo data.</span></span>
23. <span data-ttu-id="edf1c-131">Fare clic su Accesso.</span><span class="sxs-lookup"><span data-stu-id="edf1c-131">Click Log in.</span></span>
24. <span data-ttu-id="edf1c-132">Fare clic su Interrompi pausa.</span><span class="sxs-lookup"><span data-stu-id="edf1c-132">Click Stop break.</span></span>
25. <span data-ttu-id="edf1c-133">Fare clic sul pulsante Attività.</span><span class="sxs-lookup"><span data-stu-id="edf1c-133">Click the Activity button.</span></span>
26. <span data-ttu-id="edf1c-134">Scegliere Annulla.</span><span class="sxs-lookup"><span data-stu-id="edf1c-134">Click Cancel.</span></span>
27. <span data-ttu-id="edf1c-135">Fare clic sul pulsante Uscita.</span><span class="sxs-lookup"><span data-stu-id="edf1c-135">Click the Leaving button.</span></span>
28. <span data-ttu-id="edf1c-136">Selezionare per registrare l'uscita.</span><span class="sxs-lookup"><span data-stu-id="edf1c-136">Select to clock out.</span></span>
29. <span data-ttu-id="edf1c-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="edf1c-137">Click OK.</span></span>
30. <span data-ttu-id="edf1c-138">Selezionare un motivo per cui si esce in anticipo.</span><span class="sxs-lookup"><span data-stu-id="edf1c-138">Select a reason why you are clocking out early.</span></span>

