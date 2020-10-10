---
title: Gestione degli errori
description: In questo argomento viene descritta la gestione degli errori in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 72d6c8d750a5a0903017b4c77b3ce5d9521cf99b
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889363"
---
# <a name="fault-management"></a><span data-ttu-id="19685-103">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="19685-103">Fault management</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="19685-104">In Gestione cespiti, è possibile utilizzare Designer errori per impostare sintomi di errore, aree di errore e tipi di errore nei tipi di cespite.</span><span class="sxs-lookup"><span data-stu-id="19685-104">In Asset Management, you can use the fault designer to set up fault symptoms, fault areas, and fault types on asset types.</span></span> <span data-ttu-id="19685-105">In questo modo, è possibile gestire gli errori rilevati nei cespiti.</span><span class="sxs-lookup"><span data-stu-id="19685-105">In this way, you can manage faults that are detected on assets.</span></span> <span data-ttu-id="19685-106">Inoltre, le cause di errore e i suggerimenti per la correzione degli errori possono essere registrati in un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="19685-106">Additionally, fault causes and suggestions for fixing faults can be registered on a work order.</span></span>

<span data-ttu-id="19685-107">Il processo per la registrazione e la gestione degli errori comporta le fasi seguenti.</span><span class="sxs-lookup"><span data-stu-id="19685-107">The process for fault registration and management consists of these steps.</span></span>

1. <span data-ttu-id="19685-108">Creare un elenco di sintomi di errore, aree di errore e tipi di errore che potrebbero verificarsi nei tipi di cespite.</span><span class="sxs-lookup"><span data-stu-id="19685-108">Create a list of fault symptoms, fault areas, and fault types that might occur on your asset types.</span></span>
2. <span data-ttu-id="19685-109">In Designer errori, impostare i sintomi, le aree di errore e i tipi di errore.</span><span class="sxs-lookup"><span data-stu-id="19685-109">In the fault designer, set up symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="19685-110">Di seguito sono riportati alcuni esempi per illustrare la differenza tra i sintomi di errore, le aree di errore e i tipi di errore.</span><span class="sxs-lookup"><span data-stu-id="19685-110">Here are some examples to help you understand the difference between fault symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="19685-111">**Sintomi di errore**</span><span class="sxs-lookup"><span data-stu-id="19685-111">**Fault symptoms:**</span></span>

- <span data-ttu-id="19685-112">Tensioni non bilanciate</span><span class="sxs-lookup"><span data-stu-id="19685-112">Unbalanced voltages</span></span>
- <span data-ttu-id="19685-113">Cortocircuito</span><span class="sxs-lookup"><span data-stu-id="19685-113">Short circuit</span></span>
- <span data-ttu-id="19685-114">Rumore</span><span class="sxs-lookup"><span data-stu-id="19685-114">Noise</span></span>
- <span data-ttu-id="19685-115">Perdita</span><span class="sxs-lookup"><span data-stu-id="19685-115">Leak</span></span>
- <span data-ttu-id="19685-116">Vibrazioni</span><span class="sxs-lookup"><span data-stu-id="19685-116">Vibrations</span></span>

<span data-ttu-id="19685-117">**Aree di errore:**</span><span class="sxs-lookup"><span data-stu-id="19685-117">**Fault areas:**</span></span>

- <span data-ttu-id="19685-118">Elettrico</span><span class="sxs-lookup"><span data-stu-id="19685-118">Electrical</span></span>
- <span data-ttu-id="19685-119">Meccanico</span><span class="sxs-lookup"><span data-stu-id="19685-119">Mechanical</span></span>
- <span data-ttu-id="19685-120">Idraulico</span><span class="sxs-lookup"><span data-stu-id="19685-120">Hydraulic</span></span>
- <span data-ttu-id="19685-121">Pneumatico</span><span class="sxs-lookup"><span data-stu-id="19685-121">Pneumatic</span></span>

<span data-ttu-id="19685-122">**Tipi di errore:**</span><span class="sxs-lookup"><span data-stu-id="19685-122">**Fault types:**</span></span>

- <span data-ttu-id="19685-123">Bobina statore principale difettosa</span><span class="sxs-lookup"><span data-stu-id="19685-123">Faulty main stator winding</span></span>
- <span data-ttu-id="19685-124">Diodo difettoso</span><span class="sxs-lookup"><span data-stu-id="19685-124">Faulty diode</span></span>
- <span data-ttu-id="19685-125">Bobine sporche</span><span class="sxs-lookup"><span data-stu-id="19685-125">Dirty windings</span></span>
- <span data-ttu-id="19685-126">Generatore difettoso</span><span class="sxs-lookup"><span data-stu-id="19685-126">Defective generator</span></span>
- <span data-ttu-id="19685-127">Sensore difettoso</span><span class="sxs-lookup"><span data-stu-id="19685-127">Defective sensor</span></span>

## <a name="create-fault-symptoms"></a><span data-ttu-id="19685-128">Creare un elenco di sintomi di errore</span><span class="sxs-lookup"><span data-stu-id="19685-128">Create fault symptoms</span></span>

<span data-ttu-id="19685-129">Seguire questa procedura per creare un elenco di sintomi utilizzabile in Designer errori.</span><span class="sxs-lookup"><span data-stu-id="19685-129">Follow these steps to create a list of symptoms that can be used in the fault designer.</span></span>

1. <span data-ttu-id="19685-130">Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Sintomi di errore**.</span><span class="sxs-lookup"><span data-stu-id="19685-130">Select **Asset management** \> **Setup** \> **Fault** \> **Fault symptoms**.</span></span>
2. <span data-ttu-id="19685-131">Selezionare **Nuovo** per creare un record.</span><span class="sxs-lookup"><span data-stu-id="19685-131">Select **New** to create a record.</span></span>
3. <span data-ttu-id="19685-132">Nel campo **Sintomo errore**, immettere un nome per il sintomo di errore.</span><span class="sxs-lookup"><span data-stu-id="19685-132">In the **Fault symptom** field, enter a name for the fault symptom.</span></span>
4. <span data-ttu-id="19685-133">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="19685-133">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="19685-134">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="19685-134">Select **Save**.</span></span>

## <a name="create-fault-areas"></a><span data-ttu-id="19685-135">Creare un elenco di aree di errore</span><span class="sxs-lookup"><span data-stu-id="19685-135">Create fault areas</span></span>

<span data-ttu-id="19685-136">Seguire questa procedura per creare un elenco di aree utilizzabile in Designer errori.</span><span class="sxs-lookup"><span data-stu-id="19685-136">Follow these steps to create a list of areas or locations that can be used in the fault designer.</span></span>

1. <span data-ttu-id="19685-137">Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Aree di errore**.</span><span class="sxs-lookup"><span data-stu-id="19685-137">Select **Asset management** \> **Setup** \> **Fault** \> **Fault areas**.</span></span>
2. <span data-ttu-id="19685-138">Selezionare **Nuovo** per creare un record.</span><span class="sxs-lookup"><span data-stu-id="19685-138">Select **New** to create a record.</span></span>
3. <span data-ttu-id="19685-139">Nel campo **Area di errore**, immettere un nome per l'area di errore.</span><span class="sxs-lookup"><span data-stu-id="19685-139">In the **Fault area** field, enter a name for the fault area.</span></span>
4. <span data-ttu-id="19685-140">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="19685-140">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="19685-141">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="19685-141">Select **Save**.</span></span>

## <a name="create-fault-types"></a><span data-ttu-id="19685-142">Creare un elenco di tipi di errore</span><span class="sxs-lookup"><span data-stu-id="19685-142">Create fault types</span></span>

<span data-ttu-id="19685-143">Seguire questa procedura per creare un elenco di tipi di errore che possono essere utilizzati in Designer errori.</span><span class="sxs-lookup"><span data-stu-id="19685-143">Follow these steps to create a list of fault types that can be used in the fault designer.</span></span>

1. <span data-ttu-id="19685-144">Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Tipi di errore**.</span><span class="sxs-lookup"><span data-stu-id="19685-144">Select **Asset management** \> **Setup** \> **Fault** \> **Fault types**.</span></span>
2. <span data-ttu-id="19685-145">Selezionare **Nuovo** per creare un record.</span><span class="sxs-lookup"><span data-stu-id="19685-145">Select **New** to create a record.</span></span>
3. <span data-ttu-id="19685-146">Nel campo **Tipo di errore** immettere un nome per il tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="19685-146">In the **Fault type** field, enter a name for the fault type.</span></span>
4. <span data-ttu-id="19685-147">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="19685-147">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="19685-148">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="19685-148">Select **Save**.</span></span>

## <a name="set-up-the-fault-designer"></a><span data-ttu-id="19685-149">Impostare Designer errori</span><span class="sxs-lookup"><span data-stu-id="19685-149">Set up the fault designer</span></span>

<span data-ttu-id="19685-150">In Designer errori, è possibile impostare i dati dell'errore nei tipi di cespite.</span><span class="sxs-lookup"><span data-stu-id="19685-150">In the fault designer, you set up fault data on asset types.</span></span>

1. <span data-ttu-id="19685-151">Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Designer errori**.</span><span class="sxs-lookup"><span data-stu-id="19685-151">Select **Asset management** \> **Setup** \> **Fault** \> **Fault designer**.</span></span>
2. <span data-ttu-id="19685-152">Nel riquadro sinistro, selezionare il tipo di cespite per il quale impostare un record di errore.</span><span class="sxs-lookup"><span data-stu-id="19685-152">In the left pane, select the type of asset to set up a fault record for.</span></span>
3. <span data-ttu-id="19685-153">Nella Scheda dettaglio **Sintomo errore**, selezionare **Aggiungi riga** e nel campo **Sintomo errore**, selezionare un sintomo di errore.</span><span class="sxs-lookup"><span data-stu-id="19685-153">On the **Fault symptom** FastTab, select **Add line**, and then, in the **Fault symptom** field, select a fault symptom.</span></span>
4. <span data-ttu-id="19685-154">Nella Scheda dettaglio **Area di errore**, selezionare **Aggiungi riga** e nel campo **Area di errore**, selezionare un'area di errore.</span><span class="sxs-lookup"><span data-stu-id="19685-154">On the **Fault area** FastTab, select **Add line**, and then, in the **Fault area** field select a fault area.</span></span>
5. <span data-ttu-id="19685-155">Nella Scheda dettaglio **Tipo di errore**, selezionare **Aggiungi riga** e nel campo **Tipo di errore**, selezionare un tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="19685-155">On the **Fault type** FastTab, select **Add line**, and then, in the **Fault type** field, select a fault type.</span></span>
6. <span data-ttu-id="19685-156">Per creare rapidamente le combinazioni di tutti i sintomi, le aree e i tipi di errore esistenti per il tipo di cespite selezionato, selezionare **Crea combinazioni di errore**.</span><span class="sxs-lookup"><span data-stu-id="19685-156">To quickly create combinations of all existing fault symptoms, areas, and types for the selected asset type, select **Create fault combinations**.</span></span> <span data-ttu-id="19685-157">Questa funzione è utile se sono stati aggiunti molti sintomi, aree e tipi di errore.</span><span class="sxs-lookup"><span data-stu-id="19685-157">This function is useful if you've added many fault symptoms, areas, and types.</span></span> <span data-ttu-id="19685-158">È più semplice eliminare le righe di qualsiasi combinazione che non sono pertinenti al tipo di cespite che creare nuove righe manualmente.</span><span class="sxs-lookup"><span data-stu-id="19685-158">It's easier to delete the lines for any combinations that aren't relevant to the asset type than to create new lines manually.</span></span>

    > [!NOTE]
    > <span data-ttu-id="19685-159">Per copiare la configurazione di sintomi, aree e tipi di errore di un tipo di cespite nel tipo di cespite selezionato, selezionare **Copia da tipo di cespite**.</span><span class="sxs-lookup"><span data-stu-id="19685-159">To copy the setup of fault symptoms, areas, and types from one asset type to the selected asset type, select **Copy from asset type**.</span></span>

7. <span data-ttu-id="19685-160">Selezionare **Salva** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="19685-160">Select **Save** to save your changes.</span></span>

![Pagina Designer errori](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a><span data-ttu-id="19685-162">Creare un elenco di cause di errore</span><span class="sxs-lookup"><span data-stu-id="19685-162">Create fault causes</span></span>

<span data-ttu-id="19685-163">Attenersi alla procedura seguente per creare un elenco di cause di errore note che possono essere aggiunte a un ordine di lavoro o a una richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="19685-163">Follow these steps to create a list of known fault causes that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="19685-164">Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Cause errore**.</span><span class="sxs-lookup"><span data-stu-id="19685-164">Select **Asset management** \> **Setup** \> **Fault** \> **Fault causes**.</span></span>
2. <span data-ttu-id="19685-165">Selezionare **Nuovo** per creare un record.</span><span class="sxs-lookup"><span data-stu-id="19685-165">Select **New** to create a record.</span></span>
3. <span data-ttu-id="19685-166">Nel campo **Causa errore** immettere un nome per la causa dell'errore.</span><span class="sxs-lookup"><span data-stu-id="19685-166">In the **Fault cause** field, enter a name for the fault cause.</span></span>
4. <span data-ttu-id="19685-167">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="19685-167">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="19685-168">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="19685-168">Select **Save**.</span></span>

## <a name="create-fault-remedies"></a><span data-ttu-id="19685-169">Creare un elenco di rimedi agli errori</span><span class="sxs-lookup"><span data-stu-id="19685-169">Create fault remedies</span></span>

<span data-ttu-id="19685-170">Attenersi alla procedura seguente per creare un elenco di suggerimenti per correggere gli errori che possono essere aggiunti a un ordine di lavoro o a una richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="19685-170">Follow these steps to create a list of suggestions for remedy and repair that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="19685-171">Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Rimedi a errori**.</span><span class="sxs-lookup"><span data-stu-id="19685-171">Select **Asset management** \> **Setup** \> **Fault** \> **Fault remedies**.</span></span>
2. <span data-ttu-id="19685-172">Selezionare **Nuovo** per creare un record.</span><span class="sxs-lookup"><span data-stu-id="19685-172">Select **New** to create a record.</span></span>
3. <span data-ttu-id="19685-173">Nel campo **Rimedio a errore**, immettere un nome per il rimedio all'errore.</span><span class="sxs-lookup"><span data-stu-id="19685-173">In the **Fault remedy** field, enter a name for the fault remedy.</span></span>
4. <span data-ttu-id="19685-174">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="19685-174">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="19685-175">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="19685-175">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="19685-176">È possibile modificare i nomi di sintomi, aree, tipi, cause e rimedi come necessario.</span><span class="sxs-lookup"><span data-stu-id="19685-176">You can change the names of your fault symptoms, areas, types, causes, and remedies as you require.</span></span> <span data-ttu-id="19685-177">Le modifiche ai nomi vengono automaticamente implementate nelle registrazioni di errore correlate.</span><span class="sxs-lookup"><span data-stu-id="19685-177">The name changes are automatically reflected in the related fault registrations.</span></span>
