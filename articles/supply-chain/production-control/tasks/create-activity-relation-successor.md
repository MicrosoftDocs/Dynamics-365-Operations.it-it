---
title: 'Creare relazione attività: attività successiva'
description: Il flusso di attività in un flusso di produzione snella viene documentato tramite relazioni tra le attività.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 261bb1b99045cc78f0e74e1ed2ad7fa133d8ebe6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212344"
---
# <a name="create-activity-relation---successor"></a><span data-ttu-id="45961-103">Creare relazione attività: attività successiva</span><span class="sxs-lookup"><span data-stu-id="45961-103">Create activity relation - Successor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="45961-104">Il flusso di attività in un flusso di produzione snella viene documentato tramite relazioni tra le attività.</span><span class="sxs-lookup"><span data-stu-id="45961-104">The flow of activities in a lean production flow is documented through activity relations.</span></span> <span data-ttu-id="45961-105">Questa registrazione mostra come creare una relazione tra attività.</span><span class="sxs-lookup"><span data-stu-id="45961-105">This recording shows how to create an activity relation.</span></span>

<span data-ttu-id="45961-106">Prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="45961-106">Prerequisites:</span></span>

- <span data-ttu-id="45961-107">Un flusso di produzione e una versione in modalità bozza.</span><span class="sxs-lookup"><span data-stu-id="45961-107">A production flow and version in draft mode.</span></span> 

- <span data-ttu-id="45961-108">Due attività susseguenti nel flusso di produzione vengono create ma non correlate.</span><span class="sxs-lookup"><span data-stu-id="45961-108">Two activities that follow each other in the production flow are created but not related.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="45961-109">Trovare la versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="45961-109">Find the production flow version</span></span> 
1. <span data-ttu-id="45961-110">Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="45961-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="45961-111">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="45961-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="45961-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="45961-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="45961-113">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="45961-113">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="45961-114">Selezionare una versione bozza nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="45961-114">In the list, select a draft version.</span></span>
    * <span data-ttu-id="45961-115">Le relazioni di attività possono essere aggiunte alle versioni bozza o attive di un flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="45961-115">Activity relations can be added to both draft or active versions of a production flow.</span></span>  

## <a name="open-the-activity-overview"></a><span data-ttu-id="45961-116">Aprire la panoramica attività</span><span class="sxs-lookup"><span data-stu-id="45961-116">Open the activity overview</span></span>
1. <span data-ttu-id="45961-117">Fare clic su Attività.</span><span class="sxs-lookup"><span data-stu-id="45961-117">Click Activities.</span></span>
    * <span data-ttu-id="45961-118">Si noti che il modulo mostra tutte le attività del flusso di produzione allocate alla versione dei flussi di produzione in uso.</span><span class="sxs-lookup"><span data-stu-id="45961-118">Note that the form shows all activities of the production flow that are allocated to the Version of the production flows that you are working in.</span></span>  

## <a name="add-a-successor"></a><span data-ttu-id="45961-119">Aggiungere un'attività successiva</span><span class="sxs-lookup"><span data-stu-id="45961-119">Add a Successor</span></span>
1. <span data-ttu-id="45961-120">Fare clic su Aggiungi attività successiva.</span><span class="sxs-lookup"><span data-stu-id="45961-120">Click Add successor.</span></span>
2. <span data-ttu-id="45961-121">Nel campo Attività fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="45961-121">In the Activity field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="45961-122">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="45961-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="45961-123">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="45961-123">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="45961-124">Selezionare la casella di controllo Vincolo.</span><span class="sxs-lookup"><span data-stu-id="45961-124">Select the Constraint check box.</span></span>
6. <span data-ttu-id="45961-125">Nel campo Valore vincolo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="45961-125">In the Constraint value field, enter a number.</span></span>
    * <span data-ttu-id="45961-126">La durata del vincolo è il tempo da programmare tra la fine programmata dell'attività precedente (data e ora di scadenza) e la data di inizio programmata dell'attività successiva.</span><span class="sxs-lookup"><span data-stu-id="45961-126">The constraint time is the time to be scheduled between the scheduled end of the predecessor (due date and time) and the scheduled start of the successor.</span></span>  
7. <span data-ttu-id="45961-127">Digitare un valore nel campo Unità.</span><span class="sxs-lookup"><span data-stu-id="45961-127">In the Units field, type a value.</span></span>
8. <span data-ttu-id="45961-128">Nel campo Rapporto durata ciclo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="45961-128">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="45961-129">Se entrambe le attività vengono eseguite nello stesso tempo di produzione di un'unità, il rapporto durata ciclo deve essere 1.</span><span class="sxs-lookup"><span data-stu-id="45961-129">If both activities run at the same takt, the cycle time ratio should be 1.</span></span> <span data-ttu-id="45961-130">Se l'attività precedente viene eseguita a velocità doppia della successiva, il rapporto deve essere 2.</span><span class="sxs-lookup"><span data-stu-id="45961-130">If the predecessor runs at the double speed of the successor, the ratio should be 2.</span></span>   <span data-ttu-id="45961-131">Il rapporto di durata ciclo viene utilizzato per calcolare le durate ciclo individuali delle attività del flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="45961-131">The cycle time ratios are used to calculate the individual cycle times of the production flow activities.</span></span>  
9. <span data-ttu-id="45961-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="45961-132">Click OK.</span></span>
10. <span data-ttu-id="45961-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="45961-133">Close the page.</span></span>
11. <span data-ttu-id="45961-134">Fare clic sulla scheda GridPanel.</span><span class="sxs-lookup"><span data-stu-id="45961-134">Click the GridPanel tab.</span></span>
12. <span data-ttu-id="45961-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="45961-135">Close the page.</span></span>
13. <span data-ttu-id="45961-136">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="45961-136">Refresh the page.</span></span>

