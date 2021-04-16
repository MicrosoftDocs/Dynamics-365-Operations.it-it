---
title: Contenitori di spedizione
description: In questo argomento viene descritto come configurare contenitori di spedizione per il modulo Costo sbarcato.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 2f7e9435aa3d0d06e1cc51457a6343b807d76dc7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833715"
---
# <a name="shipping-container-setup"></a><span data-ttu-id="44475-103">Configurazione dei contenitori di spedizione</span><span class="sxs-lookup"><span data-stu-id="44475-103">Shipping container setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="44475-104">In questo argomento viene descritto come configurare contenitori di spedizione per il modulo **Costo sbarcato**.</span><span class="sxs-lookup"><span data-stu-id="44475-104">This topic describes how to set up shipping containers for the **Landed cost** module.</span></span>

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a><span data-ttu-id="44475-105">Configurare tipi di contenitore di spedizione</span><span class="sxs-lookup"><span data-stu-id="44475-105">Set up shipping container types</span></span>

<span data-ttu-id="44475-106">I tipi di contenitore di spedizione definiscono i tipi di contenitore di spedizione disponibili per l'uso durante la spedizione e i viaggi.</span><span class="sxs-lookup"><span data-stu-id="44475-106">Shipping container types define the types of shipping containers that are available for use during shipping and voyages.</span></span>

<span data-ttu-id="44475-107">Selezionare **Costo sbarcato \> Configurazione contenitori \> Tipi di contenitore di spedizione**</span><span class="sxs-lookup"><span data-stu-id="44475-107">To work with the shipping container types, go to **Landed cost \> Containers setup \> Shipping container types**.</span></span> <span data-ttu-id="44475-108">per visualizzare, aggiungere e rimuovere i record dei tipi di contenitore.</span><span class="sxs-lookup"><span data-stu-id="44475-108">There, you can view, add, and remove records for your container types.</span></span> <span data-ttu-id="44475-109">Nella seguente tabella sono descritti i campi disponibili per ogni record.</span><span class="sxs-lookup"><span data-stu-id="44475-109">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="44475-110">Campo</span><span class="sxs-lookup"><span data-stu-id="44475-110">Field</span></span> | <span data-ttu-id="44475-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44475-111">Description</span></span> |
|---|---|
| <span data-ttu-id="44475-112">Tipo di contenitore di spedizione</span><span class="sxs-lookup"><span data-stu-id="44475-112">Shipping container type</span></span> | <span data-ttu-id="44475-113">Immettere un nome/numero di identificazione univoco per il tipo di contenitore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="44475-113">Enter a unique identification name/number for the shipping container type.</span></span> |
| <span data-ttu-id="44475-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44475-114">Description</span></span> | <span data-ttu-id="44475-115">Immettere una descrizione del tipo di contenitore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="44475-115">Enter a description of the shipping container type.</span></span> |
| <span data-ttu-id="44475-116">Volume</span><span class="sxs-lookup"><span data-stu-id="44475-116">Volume</span></span> | <span data-ttu-id="44475-117">Immettere il volume massimo consentito nei contenitori di spedizione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="44475-117">Enter the maximum volume that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="44475-118">Peso</span><span class="sxs-lookup"><span data-stu-id="44475-118">Weight</span></span> | <span data-ttu-id="44475-119">Immettere il paso massimo consentito nei contenitori di spedizione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="44475-119">Enter the maximum weight that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="44475-120">A rendere</span><span class="sxs-lookup"><span data-stu-id="44475-120">Returnable</span></span> | <span data-ttu-id="44475-121">Specificare se i contenitori di spedizione di questo tipo possono essere restituiti al fornitore dopo essere stati utilizzati in un viaggio.</span><span class="sxs-lookup"><span data-stu-id="44475-121">Specify whether shipping containers of this type can be returned to the vendor after they are used during a voyage.</span></span> <span data-ttu-id="44475-122">Se questa opzione è impostata su *Sì*, è possibile che vengano applicati costi aggiuntivi per la restituzione dei contenitori di questo tipo al porto di origine.</span><span class="sxs-lookup"><span data-stu-id="44475-122">If this option is set to *Yes*, additional costs might apply for the return of shipping containers of this type to the port of origin.</span></span> |

## <a name="set-up-shipping-containers"></a><span data-ttu-id="44475-123">Configurare contenitori di spedizione</span><span class="sxs-lookup"><span data-stu-id="44475-123">Set up shipping containers</span></span>

<span data-ttu-id="44475-124">I record di contenitore di spedizione consentono di identificare ogni contenitore utilizzato durante i viaggi.</span><span class="sxs-lookup"><span data-stu-id="44475-124">You use shipping container records to identify each container that you use during voyages.</span></span> <span data-ttu-id="44475-125">Quando si crea un viaggio, è possibile selezionare uno specifico contenitore nell'elenco di tutti i record di contenitore di spedizione definiti qui.</span><span class="sxs-lookup"><span data-stu-id="44475-125">When you create a voyage, you can select a specific container for it in the list of all the shipping container records that you've defined here.</span></span> <span data-ttu-id="44475-126">Questa funzione è particolarmente utile se l'azienda possiede dei contenitori di spedizione.</span><span class="sxs-lookup"><span data-stu-id="44475-126">This feature is especially useful if your company owns its own shipping containers.</span></span>

<span data-ttu-id="44475-127">Non è necessario immettere i numeri dei contenitori di spedizione che verranno utilizzati una sola volta.</span><span class="sxs-lookup"><span data-stu-id="44475-127">You don't have to enter shipping container numbers for shipping containers that will be used only one time.</span></span> <span data-ttu-id="44475-128">È invece possibile aggiungere i numeri dei contenitori di spedizione quando si crea un viaggio.</span><span class="sxs-lookup"><span data-stu-id="44475-128">Instead, you can add the shipping container number when you create a voyage.</span></span>

<span data-ttu-id="44475-129">I record di contenitore di spedizione sono utilizzati solo in Costo sbarcato.</span><span class="sxs-lookup"><span data-stu-id="44475-129">Shipping container records are used only in Landed cost.</span></span> <span data-ttu-id="44475-130">Non sono disponibili nel modulo **Gestione trasporti** standard.</span><span class="sxs-lookup"><span data-stu-id="44475-130">They aren't available in the standard **Transportation management** module (TMS).</span></span>

<span data-ttu-id="44475-131">Selezionare **Costo sbarcato \> Configurazione contenitori \> Contenitori di spedizione**</span><span class="sxs-lookup"><span data-stu-id="44475-131">To work with shipping containers, go to **Landed cost \> Containers setup \> Shipping containers**.</span></span> <span data-ttu-id="44475-132">per visualizzare, aggiungere e rimuovere i record dei contenitori di spedizione.</span><span class="sxs-lookup"><span data-stu-id="44475-132">There, you can view, add, and remove records your shipping containers.</span></span> <span data-ttu-id="44475-133">Nella seguente tabella sono descritti i campi disponibili per ogni record.</span><span class="sxs-lookup"><span data-stu-id="44475-133">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="44475-134">Campo</span><span class="sxs-lookup"><span data-stu-id="44475-134">Field</span></span> | <span data-ttu-id="44475-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44475-135">Description</span></span> |
|---|---|
| <span data-ttu-id="44475-136">Contenitore di spedizione</span><span class="sxs-lookup"><span data-stu-id="44475-136">Shipping container</span></span> | <span data-ttu-id="44475-137">Immettere un nome/numero di identificazione univoco per il contenitore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="44475-137">Enter a unique identification name/number for the shipping container.</span></span> |
| <span data-ttu-id="44475-138">Tipo di contenitore di spedizione</span><span class="sxs-lookup"><span data-stu-id="44475-138">Shipping container type</span></span> | <span data-ttu-id="44475-139">Selezionare il tipo di contenitore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="44475-139">Select the type of shipping container.</span></span> <span data-ttu-id="44475-140">Per ulteriori informazioni, vedere la sezione [Configurare tipi di contenitori di spedizione](#shipping-container-types) descritta precedentemente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="44475-140">For more information, see the [Set up shipping container types](#shipping-container-types) section earlier in this topic.</span></span> |

> [!NOTE]
> - <span data-ttu-id="44475-141">La configurazione dei contenitori di spedizione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="44475-141">The shipping container setup is optional.</span></span> <span data-ttu-id="44475-142">In genere, la si utilizza solo se l'azienda possiede dei contenitori di spedizione o se riutilizza spesso gli stessi contenitori di spedizione.</span><span class="sxs-lookup"><span data-stu-id="44475-142">Typically, you will use it only if your company owns its own shipping containers or often reuses the same shipping containers.</span></span>
> - <span data-ttu-id="44475-143">Non vengono calcolate cifre di controllo per i numeri dei contenitori di spedizione.</span><span class="sxs-lookup"><span data-stu-id="44475-143">No check digits are calculated for shipping container numbers.</span></span>

## <a name="set-up-unit-types"></a><a name="unit-types"></a><span data-ttu-id="44475-144">Configurare tipi di unità</span><span class="sxs-lookup"><span data-stu-id="44475-144">Set up unit types</span></span>

<span data-ttu-id="44475-145">I tipi di unità stabiliscono raggruppamenti e metodi di identificazione aggiuntivi per i contenitori di spedizione.</span><span class="sxs-lookup"><span data-stu-id="44475-145">Unit types establish additional groupings and identification methods for shipping containers.</span></span> <span data-ttu-id="44475-146">Il tipo di unità viene generalmente utilizzato per identificare il tipo di contenitore in cui vengono imballate le merci, come pallet o fusti.</span><span class="sxs-lookup"><span data-stu-id="44475-146">The unit type is typically used to identify the type of container that goods are packaged in, such as pallets or drums.</span></span> <span data-ttu-id="44475-147">È possibile selezionare un tipo di unità quando si configura un contenitore nella pagina **Tutti i contenitori di spedizione**.</span><span class="sxs-lookup"><span data-stu-id="44475-147">You can select a unit type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="44475-148">I tipi di unità sono utilizzati solo in Costo sbarcato.</span><span class="sxs-lookup"><span data-stu-id="44475-148">Unit types are used only in Landed cost.</span></span> <span data-ttu-id="44475-149">Non sono disponibili nel modulo Gestione trasporti.</span><span class="sxs-lookup"><span data-stu-id="44475-149">They aren't available in TMS.</span></span>

<span data-ttu-id="44475-150">Selezionare **Costo sbarcato \> Configurazione contenitori \> Tipi di unità**</span><span class="sxs-lookup"><span data-stu-id="44475-150">To work with unit types, go to **Landed cost \> Containers setup \> Unit types**.</span></span> <span data-ttu-id="44475-151">per visualizzare, aggiungere e rimuovere i record dei tipi di unità.</span><span class="sxs-lookup"><span data-stu-id="44475-151">There, you can view, add, and remove records for your unit types.</span></span> <span data-ttu-id="44475-152">Nella seguente tabella sono descritti i campi disponibili per ogni record.</span><span class="sxs-lookup"><span data-stu-id="44475-152">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="44475-153">Campo</span><span class="sxs-lookup"><span data-stu-id="44475-153">Field</span></span> | <span data-ttu-id="44475-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44475-154">Description</span></span> |
|---|---|
| <span data-ttu-id="44475-155">Tipo di unità</span><span class="sxs-lookup"><span data-stu-id="44475-155">Unit type</span></span> | <span data-ttu-id="44475-156">Immettere un nome/numero di identificazione univoco per il tipo di unità.</span><span class="sxs-lookup"><span data-stu-id="44475-156">Enter a unique identification name/number for the unit type.</span></span> |
| <span data-ttu-id="44475-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44475-157">Description</span></span> | <span data-ttu-id="44475-158">Immettere una descrizione del tipo di unità.</span><span class="sxs-lookup"><span data-stu-id="44475-158">Enter a description of the unit type.</span></span> |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a><span data-ttu-id="44475-159">Configurare tipi di refrigerazione</span><span class="sxs-lookup"><span data-stu-id="44475-159">Set up refrigeration types</span></span>

<span data-ttu-id="44475-160">I tipi di refrigerazione stabiliscono raggruppamenti e metodi di identificazione aggiuntivi per i contenitori di spedizione (solitamente contenitori refrigerati).</span><span class="sxs-lookup"><span data-stu-id="44475-160">Refrigeration types establish additional groupings and identification methods for shipping containers (usually refrigerated containers).</span></span> <span data-ttu-id="44475-161">È possibile selezionare un tipo di refrigerazione quando si configura un contenitore nella pagina **Tutti i contenitori di spedizione**.</span><span class="sxs-lookup"><span data-stu-id="44475-161">You can select a refrigeration type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="44475-162">Selezionare **Costo sbarcato \> Configurazione contenitori \> Tipi di refrigerazione**</span><span class="sxs-lookup"><span data-stu-id="44475-162">To work with refrigeration types, go to **Landed cost \> Containers setup \> Refrigeration types**.</span></span> <span data-ttu-id="44475-163">per visualizzare, aggiungere e rimuovere i record dei tipi di refrigerazione.</span><span class="sxs-lookup"><span data-stu-id="44475-163">There, you can view, add, and remove records for your refrigeration types.</span></span> <span data-ttu-id="44475-164">Nella seguente tabella sono descritti i campi disponibili per ogni record.</span><span class="sxs-lookup"><span data-stu-id="44475-164">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="44475-165">Campo</span><span class="sxs-lookup"><span data-stu-id="44475-165">Field</span></span> | <span data-ttu-id="44475-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44475-166">Description</span></span> |
|---|---|
| <span data-ttu-id="44475-167">Tipo di refrigerazione</span><span class="sxs-lookup"><span data-stu-id="44475-167">Refrigeration type</span></span> | <span data-ttu-id="44475-168">Immettere un nome/numero di identificazione univoco per il tipo di refrigerazione.</span><span class="sxs-lookup"><span data-stu-id="44475-168">Enter a unique identification name/number for the refrigeration type.</span></span> |
| <span data-ttu-id="44475-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44475-169">Description</span></span> | <span data-ttu-id="44475-170">Immettere una descrizione del tipo di refrigerazioneE.</span><span class="sxs-lookup"><span data-stu-id="44475-170">Enter a description of the refrigeration type.</span></span> |
