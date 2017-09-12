--- 
title: Gestire un ciclo di lavorazione per un modello di prodotto
description: L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.
author: BibiSp
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 3f6bacc54664c32a7d42f2befc51c420e29ada56
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="maintain-a-route-for-a-product-model"></a><span data-ttu-id="e02af-103">Gestire un ciclo di lavorazione per un modello di prodotto</span><span class="sxs-lookup"><span data-stu-id="e02af-103">Maintain a route for a product model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e02af-104">L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.</span><span class="sxs-lookup"><span data-stu-id="e02af-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="e02af-105">Questa procedura utilizza il modello High end speaker della società di dati dimostrativi USMF per eseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="e02af-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="e02af-106">Aggiungere un'operazione del ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="e02af-106">Add a route operation</span></span>
1. <span data-ttu-id="e02af-107">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="e02af-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="e02af-108">Fare clic su Modelli di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="e02af-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="e02af-109">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="e02af-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e02af-110">Selezionare il modello High end speaker per questo esercizio.</span><span class="sxs-lookup"><span data-stu-id="e02af-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="e02af-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e02af-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e02af-112">Espandere la sezione Operazioni ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="e02af-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="e02af-113">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="e02af-113">Click Add.</span></span>
7. <span data-ttu-id="e02af-114">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e02af-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="e02af-115">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="e02af-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="e02af-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="e02af-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="e02af-117">Immettere i dettagli operazione ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="e02af-117">Enter route operation details</span></span>
1. <span data-ttu-id="e02af-118">Fare clic su Dettagli operazione ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="e02af-118">Click Route operation details.</span></span>
2. <span data-ttu-id="e02af-119">Nel campo Operazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e02af-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="e02af-120">Nel campo Oper.</span><span class="sxs-lookup"><span data-stu-id="e02af-120">In the Oper.</span></span> <span data-ttu-id="e02af-121">N.</span><span class="sxs-lookup"><span data-stu-id="e02af-121">No.</span></span> <span data-ttu-id="e02af-122">immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e02af-122">field, enter a number.</span></span>
    * <span data-ttu-id="e02af-123">I numeri di operazione determinano la sequenza del ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="e02af-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="e02af-124">Ogni proprietà di un'operazione del ciclo di lavorazione può ottenere un valore statico o essere sottoposta al mapping a un attributo.</span><span class="sxs-lookup"><span data-stu-id="e02af-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="e02af-125">Il mapping a un attributo determinerà l'impostazione del valore come parte di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e02af-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="e02af-126">Nel campo Gruppo di cicli di lavorazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e02af-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="e02af-127">Il gruppo di cicli di lavorazione determina il comportamento essenziale di costi, consumo e impostazione.</span><span class="sxs-lookup"><span data-stu-id="e02af-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="e02af-128">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e02af-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="e02af-129">Fare clic sulla scheda Tempi.</span><span class="sxs-lookup"><span data-stu-id="e02af-129">Click the Times tab.</span></span>
7. <span data-ttu-id="e02af-130">Nel campo Qtà lavorazione</span><span class="sxs-lookup"><span data-stu-id="e02af-130">In the Process qty.</span></span> <span data-ttu-id="e02af-131">immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e02af-131">field, enter a number.</span></span>
    * <span data-ttu-id="e02af-132">Determinare quante elaborazioni verranno eseguite durante un'operazione.</span><span class="sxs-lookup"><span data-stu-id="e02af-132">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="e02af-133">Nel campo Ore/Ora immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e02af-133">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="e02af-134">Inserire il rapporto durata.</span><span class="sxs-lookup"><span data-stu-id="e02af-134">Enter the time ratio.</span></span>  
9. <span data-ttu-id="e02af-135">Selezionare la casella di controllo Imposta.</span><span class="sxs-lookup"><span data-stu-id="e02af-135">Select the Set check box.</span></span>
10. <span data-ttu-id="e02af-136">Nel campo Tempo di esecuzione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e02af-136">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="e02af-137">Determinare l'ora di elaborazione per la quantità specificata.</span><span class="sxs-lookup"><span data-stu-id="e02af-137">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="e02af-138">Fare clic sulla scheda Requisiti risorsa.</span><span class="sxs-lookup"><span data-stu-id="e02af-138">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="e02af-139">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="e02af-139">Click Add.</span></span>
13. <span data-ttu-id="e02af-140">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e02af-140">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="e02af-141">Nel campo Tipo di requisito selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="e02af-141">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="e02af-142">Decidere se si desidera specificare risorse o funzionalità specifiche di cui si deve disporre.</span><span class="sxs-lookup"><span data-stu-id="e02af-142">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="e02af-143">Nel campo Requisito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e02af-143">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="e02af-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e02af-144">Click OK.</span></span>

