--- 
title: "Aggiungere un'attività precedente a un'attività del flusso di produzione"
description: "In una versione del flusso di produzione, tutte le attività devono essere in sequenza."
author: cvocph
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: bab99189fdd1980600612aaca9c6eb70cd976e2d
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a><span data-ttu-id="5af21-103">Aggiungere un'attività precedente a un'attività del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="5af21-103">Add a predecessor to a production flow activity</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5af21-104">In una versione del flusso di produzione, tutte le attività devono essere in sequenza.</span><span class="sxs-lookup"><span data-stu-id="5af21-104">In a production flow version, all activities must be sequenced.</span></span> <span data-ttu-id="5af21-105">Un'attività può avere una o più attività precedenti o successive.</span><span class="sxs-lookup"><span data-stu-id="5af21-105">An activity can have one or multiple predecessors or successors.</span></span> 

<span data-ttu-id="5af21-106">In questa procedura viene illustrato come associare un'attività precedente a un'attività.</span><span class="sxs-lookup"><span data-stu-id="5af21-106">This procedure shows how to associate a predecessor to an activity.</span></span> 

<span data-ttu-id="5af21-107">Per eseguire questa attività, è necessario disporre di un flusso di produzione con la versione bozza con almeno due attività che possono essere connesse.</span><span class="sxs-lookup"><span data-stu-id="5af21-107">To perform this task, you need a production flow that has the Draft version with at least two activities that can be connected.</span></span> 

<span data-ttu-id="5af21-108">Per ulteriori informazioni, leggere il white paper sui flussi di produzione e le attività nel lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="5af21-108">To learn more, read the white paper "Production flows and activities in lean manufacturing."</span></span>


## <a name="find-the-production-flow-and-version"></a><span data-ttu-id="5af21-109">Trovare il flusso e la versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="5af21-109">Find the production flow and version</span></span>
1. <span data-ttu-id="5af21-110">Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="5af21-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="5af21-111">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5af21-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5af21-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5af21-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="5af21-113">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5af21-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="5af21-114">Fare clic su Attività.</span><span class="sxs-lookup"><span data-stu-id="5af21-114">Click Activities.</span></span>

## <a name="select-an-activity-and-add-a-predecessor"></a><span data-ttu-id="5af21-115">Selezionare un'attività e aggiungere un'attività precedente</span><span class="sxs-lookup"><span data-stu-id="5af21-115">Select an activity and add a predecessor</span></span>
1. <span data-ttu-id="5af21-116">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5af21-116">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="5af21-117">Fare clic su Aggiungi attività precedente.</span><span class="sxs-lookup"><span data-stu-id="5af21-117">Click Add predecessor.</span></span>
3. <span data-ttu-id="5af21-118">Nel campo Attività immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5af21-118">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="5af21-119">Nel campo Rapporto durata ciclo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5af21-119">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="5af21-120">Il rapporto di durata ciclo predefinito di una relazione tra attività è 1.</span><span class="sxs-lookup"><span data-stu-id="5af21-120">The default cycle time ratio of an activity relation is 1.</span></span> <span data-ttu-id="5af21-121">Ciò presuppone che entrambe le attività vengano eseguite allo stesso ritmo o tempo di produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="5af21-121">This assumes that both activities run at the same pace or takt time.</span></span> <span data-ttu-id="5af21-122">Se l'attività precedente viene eseguita a ritmo più alto (tempo inferiore di produzione di un'unità), il rapporto deve essere inferiore a 1, se l'attività precedente viene eseguita a ritmo più lento (tempo superiore di produzione di un'unità) il rapporto durata ciclo è maggiore di 1.</span><span class="sxs-lookup"><span data-stu-id="5af21-122">If the predecessor runs at a higher pace (lower takt time), the ratio should be lower than 1, if the predecessor runs at a slower pace (higher takt time) the cycle time ratio is greater than 1.</span></span>  
5. <span data-ttu-id="5af21-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5af21-123">Click OK.</span></span>


