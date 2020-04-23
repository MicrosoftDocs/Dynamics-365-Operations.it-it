---
title: Creare una risorsa operativa
description: Una risorsa operativa esegue le attività di un progetto o di un processo di produzione.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e2e59b1e6a83d902df98a0b40ee6c572a6567f05
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212183"
---
# <a name="create-an-operations-resource"></a><span data-ttu-id="2a1a5-103">Creare una risorsa operativa</span><span class="sxs-lookup"><span data-stu-id="2a1a5-103">Create an operations resource</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2a1a5-104">Una risorsa operativa esegue le attività di un progetto o di un processo di produzione.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-104">An operations resource performs the activities of a project or a production process.</span></span> <span data-ttu-id="2a1a5-105">In questa procedura viene illustrato come definire una risorsa operativa.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-105">This procedures shows you how to define an operations resource.</span></span> <span data-ttu-id="2a1a5-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="2a1a5-107">Fare clic su Risorse.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-107">Go to Resources.</span></span>
2. <span data-ttu-id="2a1a5-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-108">Click New.</span></span>
3. <span data-ttu-id="2a1a5-109">Digitare un valore nel campo Risorsa.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-109">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="2a1a5-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-110">In the Description field, type a value.</span></span>

## <a name="define-capacity-and-consumption-parameters"></a><span data-ttu-id="2a1a5-111">Definire i parametri di capacità e consumo.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-111">Define capacity and consumption parameters</span></span>
1. <span data-ttu-id="2a1a5-112">Espandere la sezione Operazione.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-112">Expand the Operation section.</span></span>
2. <span data-ttu-id="2a1a5-113">Immettere un numero nel campo Percentuale scarti.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-113">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="2a1a5-114">Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-114">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="2a1a5-115">Specificare la categoria di costi che determina come rappresentare il costo di attrezzaggio.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-115">Specify the cost category that defines how to account for the cost of setup.</span></span>  
4. <span data-ttu-id="2a1a5-116">Nel campo Categoria tempo di esecuzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-116">In the Run time category field, enter or select a value.</span></span>
    * <span data-ttu-id="2a1a5-117">Specificare la categoria di costi che determina come rappresentare il tempo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-117">Specify the cost category that defines how to account for the cost of run time.</span></span>  
5. <span data-ttu-id="2a1a5-118">Nel campo Categoria quantità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-118">In the Quantity category field, enter or select a value.</span></span>
    * <span data-ttu-id="2a1a5-119">Specificare la categoria di costi che determina come rappresentare il costo delle risorse in base alla quantità di output.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-119">Specify the cost category that defines how to account for the resource cost based on the output quantity.</span></span>  
6. <span data-ttu-id="2a1a5-120">Selezionare un'opzione nel campo Unità di capacità.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-120">In the Capacity unit field, select an option.</span></span>
    * <span data-ttu-id="2a1a5-121">Specificare l'unità in cui esprimere la capacità della risorsa operativa.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-121">Specify the unit in which to express the capacity of the operations resource.</span></span>  
7. <span data-ttu-id="2a1a5-122">Immettere un numero nel campo Capacità.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-122">In the Capacity field, enter a number.</span></span>
8. <span data-ttu-id="2a1a5-123">Immettere un numero nel campo Percentuale efficienza.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-123">In the Efficiency percentage field, enter a number.</span></span>
    * <span data-ttu-id="2a1a5-124">Specificare l'efficienza che ci si attende dalla risorsa operativa.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-124">Specify the efficiency that you expect from the operations resource.</span></span> <span data-ttu-id="2a1a5-125">La percentuale di efficienza consente di rettificare la produttività di una risorsa operativa e influisce sul tempo riservato per la risorsa.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-125">The efficiency percentage adjusts the throughput of the operations resource and affects the time that is reserved for the resource.</span></span>  
9. <span data-ttu-id="2a1a5-126">Nel campo Percentuale programmazione operazioni, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-126">In the Operations scheduling percentage field, enter a number.</span></span>
    * <span data-ttu-id="2a1a5-127">Specificare la percentuale massima di capacità della risorsa operativa che si desidera utilizzare nella programmazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-127">Specify the maximum percentage of capacity of the operations resource that you want to use in operations scheduling.</span></span>  
10. <span data-ttu-id="2a1a5-128">Selezionare Sì nel campo Capacità limitata.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-128">Select Yes in the Finite capacity field.</span></span>
    * <span data-ttu-id="2a1a5-129">Impostare questa opzione su Sì se la risorsa operativa deve essere programmata in base all'effettiva capacità disponibile e se devono essere considerate le prenotazioni esistenti della capacità.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-129">Set this option to Yes if the operations resource should be scheduled based on the actual capacity that is available, and if existing capacity reservations should be considered.</span></span> <span data-ttu-id="2a1a5-130">Se l'opzione è impostata su No, si presuppone che la risorsa operativa abbia una capacità infinita e la risorsa può essere prenotata in eccesso.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-130">If this option is set to No, the operations resource is assumed to have infinite capacity, and the resource might be overbooked.</span></span>  
11. <span data-ttu-id="2a1a5-131">Selezionare Sì nel campo Risorsa collo di bottiglia.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-131">Select Yes in the Bottleneck resource field.</span></span>

## <a name="define-working-times"></a><span data-ttu-id="2a1a5-132">Definire gli orari di lavoro</span><span class="sxs-lookup"><span data-stu-id="2a1a5-132">Define working times</span></span>
1. <span data-ttu-id="2a1a5-133">Espandere la sezione Calendari.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-133">Expand the Calendars section.</span></span>
2. <span data-ttu-id="2a1a5-134">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-134">Click Add.</span></span>
3. <span data-ttu-id="2a1a5-135">Nel campo Calendario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-135">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="2a1a5-136">Specificare il calendario dell'orario di lavoro che definisce la capacità (in ore) della risorsa.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-136">Specify the working time calendar that defines the capacity (in hours) of the resource.</span></span>  
4. <span data-ttu-id="2a1a5-137">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="2a1a5-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-138">In the list, click the link in the selected row.</span></span>

## <a name="define-resource-capabilities"></a><span data-ttu-id="2a1a5-139">Definire le capacità delle risorse</span><span class="sxs-lookup"><span data-stu-id="2a1a5-139">Define resource capabilities</span></span>
1. <span data-ttu-id="2a1a5-140">Espandere la sezione Capacità.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-140">Expand the Capabilities section.</span></span>
2. <span data-ttu-id="2a1a5-141">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-141">Click Add.</span></span>
    * <span data-ttu-id="2a1a5-142">Si definisce capacità l'idoneità di una risorsa operativa di eseguire un'attività specifica.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-142">A capability is the ability of an operations resource to perform a particular activity.</span></span> <span data-ttu-id="2a1a5-143">Il motore di programmazione alloca le risorse abbinando i requisiti risorsa di ogni attività alle capacità delle risorse operative disponibili.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-143">The scheduling engine allocates resources by matching the resource requirements of each activity to the capabilities of the available operations resources.</span></span>  
3. <span data-ttu-id="2a1a5-144">Nel campo Capacità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-144">In the Capability field, enter or select a value.</span></span>
4. <span data-ttu-id="2a1a5-145">Nel campo Livello immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-145">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="2a1a5-146">Specificare il livello di competenza in base al quale la risorsa elabora la capacità.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-146">Specify the level of proficiency by which the resource processes the capability.</span></span>  
5. <span data-ttu-id="2a1a5-147">Nel campo Priorità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-147">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="2a1a5-148">Specificare la priorità della risorsa operativa in relazione alla capacità.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-148">Specify the priority of the operations resource with respect to the capability.</span></span> <span data-ttu-id="2a1a5-149">Nella programmazione in base alla priorità, viene selezionata per prima la risorsa operativa con la priorità più alta (valore numerico più basso).</span><span class="sxs-lookup"><span data-stu-id="2a1a5-149">When scheduling by priority, the operations resource with the highest priority (lowest numeric value) is selected first.</span></span>  

## <a name="assign-resource-to-resource-group"></a><span data-ttu-id="2a1a5-150">Assegna risorsa al gruppo di risorse</span><span class="sxs-lookup"><span data-stu-id="2a1a5-150">Assign resource to resource group</span></span>
1. <span data-ttu-id="2a1a5-151">Espandere la sezione Gruppi di risorse.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-151">Expand the Resource groups section.</span></span>
2. <span data-ttu-id="2a1a5-152">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-152">Click Add.</span></span>
    * <span data-ttu-id="2a1a5-153">Il gruppo di risorse definisce il contesto di sito, unità di produzione e magazzino per le risorse operative.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-153">The resource group defines the site, production unit, and warehouse context for operations resources.</span></span> <span data-ttu-id="2a1a5-154">La risorsa operativa può essere programmata solo quando è assegnata a un gruppo di risorse e solo sul sito in cui si trova il gruppo.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-154">The operations resource can only be scheduled when assigned to a resource group, and only on the site where the resource group is located.</span></span>  
3. <span data-ttu-id="2a1a5-155">Nel campo Gruppo di risorse immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-155">In the Resource group field, enter or select a value.</span></span>
4. <span data-ttu-id="2a1a5-156">Nel campo Ubicazione di input immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-156">In the Input location field, enter or select a value.</span></span>
    * <span data-ttu-id="2a1a5-157">Specificare il percorso del magazzino da cui la risorsa operativa sta utilizzando i materiali.</span><span class="sxs-lookup"><span data-stu-id="2a1a5-157">Specify the warehouse location from where the operations resource is consuming materials.</span></span>  

