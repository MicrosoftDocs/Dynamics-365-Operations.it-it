--- 
title: "Definire le capacità delle risorse"
description: "Capacità risorsa descrive le operazioni che possono effettuare le risorse operative."
author: sorenva
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 99c230c0e6a580f77d863b6f0be298615966c479
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="define-resource-capabilities"></a><span data-ttu-id="332d6-103">Definire le capacità delle risorse</span><span class="sxs-lookup"><span data-stu-id="332d6-103">Define resource capabilities</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="332d6-104">Capacità risorsa descrive le operazioni che possono effettuare le risorse operative.</span><span class="sxs-lookup"><span data-stu-id="332d6-104">Resource capabilities describe what operations resources can do.</span></span> <span data-ttu-id="332d6-105">Durante la programmazione, i requisiti di ogni processo e operazione vengono associati alle capacità delle risorse disponibili.</span><span class="sxs-lookup"><span data-stu-id="332d6-105">During scheduling, the requirements of each job and operation are matched against the capabilities of the available resources.</span></span> <span data-ttu-id="332d6-106">Questa guida attività consentirà di creare una capacità risorsa e di assegnarla a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="332d6-106">This task guide will help you create a resource capability and assign it to a resource.</span></span> <span data-ttu-id="332d6-107">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="332d6-107">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-resource-capability"></a><span data-ttu-id="332d6-108">Consente di creare una capacità risorsa</span><span class="sxs-lookup"><span data-stu-id="332d6-108">Create a resource capability</span></span>
1. <span data-ttu-id="332d6-109">Fare clic su Capacità risorsa.</span><span class="sxs-lookup"><span data-stu-id="332d6-109">Go to Resource capabilities.</span></span>
2. <span data-ttu-id="332d6-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="332d6-110">Click New.</span></span>
3. <span data-ttu-id="332d6-111">Nel campo Capacità, digitare l'ID della capacità della risorsa.</span><span class="sxs-lookup"><span data-stu-id="332d6-111">In the Capability field, type the ID of the resource capability.</span></span>
    * <span data-ttu-id="332d6-112">Per un'operazione specifica, utilizzare l'ID della capacità per specificare le risorse devono avere tale capacità per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="332d6-112">For a given operation, you use the capability ID to specify that resources must have this capability to perform the operation.</span></span>  
4. <span data-ttu-id="332d6-113">Nel campo Descrizione immettere una descrizione della capacità.</span><span class="sxs-lookup"><span data-stu-id="332d6-113">In the Description field, enter a description of the capability.</span></span>

## <a name="assign-capability-to-a-resource"></a><span data-ttu-id="332d6-114">Assegna la capacità a una risorsa</span><span class="sxs-lookup"><span data-stu-id="332d6-114">Assign capability to a resource</span></span>
1. <span data-ttu-id="332d6-115">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="332d6-115">Click Add.</span></span>
2. <span data-ttu-id="332d6-116">Nel campo Risorsa, digitare l'ID della risorsa.</span><span class="sxs-lookup"><span data-stu-id="332d6-116">In the Resource field, type the ID of the resource.</span></span>
    * <span data-ttu-id="332d6-117">Una capacità della risorsa può essere assegnata a una o più risorse.</span><span class="sxs-lookup"><span data-stu-id="332d6-117">A resource capability can be assigned to one or more resources.</span></span>  
3. <span data-ttu-id="332d6-118">Nel campo Scadenza immettere una data.</span><span class="sxs-lookup"><span data-stu-id="332d6-118">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="332d6-119">È possibile utilizzare questo campo per specificare che una risorsa dispone di tale capacità solo per un tempo limitato.</span><span class="sxs-lookup"><span data-stu-id="332d6-119">You can use this field to specify that a resource has the capability for only a limited time.</span></span>  
4. <span data-ttu-id="332d6-120">Nel campo Priorità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="332d6-120">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="332d6-121">Quando si programmano i processi e le operazioni, è possibile specificare se selezionare le risorse in base alla priorità.</span><span class="sxs-lookup"><span data-stu-id="332d6-121">When you schedule jobs and operations, you can specify whether to select resources by priority.</span></span> <span data-ttu-id="332d6-122">In questo caso e se più risorse possono eseguire il processo o l'operazione entro la data richiesta, viene selezionata la risorsa con la priorità più bassa rispetto alla capacità richiesta.</span><span class="sxs-lookup"><span data-stu-id="332d6-122">If you choose to do this, and more than one resource can perform the job or operation by the requested date, the resource that has the lowest priority with respect to the required capability is selected.</span></span>  
5. <span data-ttu-id="332d6-123">Nel campo Livello immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="332d6-123">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="332d6-124">Se si specifica che un processo o un'operazione richiede una capacità specifica, è possibile specificare il livello minimo necessario.</span><span class="sxs-lookup"><span data-stu-id="332d6-124">When you specify that a job or operation requires a particular capability, you can also specify the minimum level that is required.</span></span> <span data-ttu-id="332d6-125">Utilizzare il livello di capacità per distinguere le risorse che possono eseguire lo stesso processo, ma con diverse velocità, forze, dimensioni e così via.</span><span class="sxs-lookup"><span data-stu-id="332d6-125">Use the capability level to differentiate resources that can perform the same job, but at different speeds, strengths, sizes, and so on.</span></span>  

