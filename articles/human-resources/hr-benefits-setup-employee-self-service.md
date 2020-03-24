---
title: Configurare il dipendente self-service
description: In Microsoft Dynamics 365 Human Resources, è possibile configurare riquadri per la navigazione di livello superiore in Dipendente self-service.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 17918fc7b894929c92c54b59b7440ab8aef980bd
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092662"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="e1e5e-103">Configurare il dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="e1e5e-103">Configure employee self service</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="e1e5e-104">In Microsoft Dynamics 365 Human Resources, è possibile configurare riquadri per la navigazione di livello superiore in Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="e1e5e-105">I riquadri Piano benefit indirizzano gli utenti ai piani di benefit ai quali hanno diritto a iscriversi.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-105">Benefit plan tiles direct users to benefit plans that they are eligible to enroll in.</span></span>

## <a name="set-up-a-role-center-tile"></a><span data-ttu-id="e1e5e-106">Impostare un riquadro Centro gestione ruolo</span><span class="sxs-lookup"><span data-stu-id="e1e5e-106">Set up a role center tile</span></span>

1. <span data-ttu-id="e1e5e-107">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri di Dipendente self-service**.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="e1e5e-108">Selezionare la scheda **Impostazione riquadro Centro gestione ruoli**, quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-108">Select the **Role center tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="e1e5e-109">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="e1e5e-110">Campo</span><span class="sxs-lookup"><span data-stu-id="e1e5e-110">Field</span></span> | <span data-ttu-id="e1e5e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1e5e-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="e1e5e-112">ID riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-112">Tile ID</span></span> | <span data-ttu-id="e1e5e-113">L'identificatore univoco per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="e1e5e-114">Testo etichetta riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-114">Tile label text</span></span> | <span data-ttu-id="e1e5e-115">Il testo che verrà visualizzato per il riquadro Self service.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="e1e5e-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1e5e-116">Description</span></span> | <span data-ttu-id="e1e5e-117">Una descrizione del riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-117">A description of the tile.</span></span> |
   | <span data-ttu-id="e1e5e-118">Indirizzo Internet</span><span class="sxs-lookup"><span data-stu-id="e1e5e-118">Internet address</span></span> | <span data-ttu-id="e1e5e-119">Immettere l'URL alla pagina Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="e1e5e-120">Dimensioni riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-120">Tile size</span></span> | <span data-ttu-id="e1e5e-121">La dimensione del riquadro: Piccolo, Medio o Grande.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="e1e5e-122">Destinatario</span><span class="sxs-lookup"><span data-stu-id="e1e5e-122">Target</span></span> | <span data-ttu-id="e1e5e-123">Specifica se la pagina deve essere aperta in una nuova finestra o nella finestra corrente.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="e1e5e-124">Immagine di sfondo riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-124">Tile background image</span></span> | <span data-ttu-id="e1e5e-125">L'URL dell'immagine da utilizzare per il riquadro (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="e1e5e-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="e1e5e-126">Avvio</span><span class="sxs-lookup"><span data-stu-id="e1e5e-126">Start</span></span> | <span data-ttu-id="e1e5e-127">La data e l'ora di inizio della disponibilità del riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="e1e5e-128">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="e1e5e-128">End</span></span> | <span data-ttu-id="e1e5e-129">La data e l'ora di fine della disponibilità del riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="e1e5e-130">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-130">Select **Save**.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="e1e5e-131">Impostare un riquadro Piani di benefit</span><span class="sxs-lookup"><span data-stu-id="e1e5e-131">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="e1e5e-132">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri di Dipendente self-service**.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="e1e5e-133">Selezionare la scheda **Impostazione riquadro Piani di benefit**, quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-133">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="e1e5e-134">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="e1e5e-135">Campo</span><span class="sxs-lookup"><span data-stu-id="e1e5e-135">Field</span></span> | <span data-ttu-id="e1e5e-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1e5e-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="e1e5e-137">ID riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-137">Tile ID</span></span> | <span data-ttu-id="e1e5e-138">L'identificatore univoco per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="e1e5e-139">Testo etichetta riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-139">Tile label text</span></span> | <span data-ttu-id="e1e5e-140">Il testo che verrà visualizzato per il riquadro Self service.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-140">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="e1e5e-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1e5e-141">Description</span></span> | <span data-ttu-id="e1e5e-142">Una descrizione del riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-142">A description of the tile.</span></span> |
   | <span data-ttu-id="e1e5e-143">Indirizzo Internet</span><span class="sxs-lookup"><span data-stu-id="e1e5e-143">Internet address</span></span> | <span data-ttu-id="e1e5e-144">Immettere l'URL alla pagina Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="e1e5e-145">Dimensioni riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-145">Tile size</span></span> | <span data-ttu-id="e1e5e-146">La dimensione del riquadro: Piccolo, Medio o Grande.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="e1e5e-147">Destinatario</span><span class="sxs-lookup"><span data-stu-id="e1e5e-147">Target</span></span> | <span data-ttu-id="e1e5e-148">Specifica se la pagina deve essere aperta in una nuova finestra o nella finestra corrente.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="e1e5e-149">Immagine di sfondo riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-149">Tile background image</span></span> | <span data-ttu-id="e1e5e-150">L'URL dell'immagine da utilizzare per il riquadro (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="e1e5e-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="e1e5e-151">Avvio</span><span class="sxs-lookup"><span data-stu-id="e1e5e-151">Start</span></span> | <span data-ttu-id="e1e5e-152">La data e l'ora di inizio della disponibilità del riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="e1e5e-153">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="e1e5e-153">End</span></span> | <span data-ttu-id="e1e5e-154">La data e l'ora di fine della disponibilità del riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="e1e5e-155">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-155">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="e1e5e-156">Impostare un riquadro Piano di credito flessibile</span><span class="sxs-lookup"><span data-stu-id="e1e5e-156">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="e1e5e-157">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri di Dipendente self-service**.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-157">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="e1e5e-158">Selezionare la scheda **Impostazione riquadro Piano di credito flessibile**, quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-158">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="e1e5e-159">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e1e5e-159">Specify values for the following fields:</span></span>

   | <span data-ttu-id="e1e5e-160">Campo</span><span class="sxs-lookup"><span data-stu-id="e1e5e-160">Field</span></span> | <span data-ttu-id="e1e5e-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1e5e-161">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="e1e5e-162">ID riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-162">Tile ID</span></span> | <span data-ttu-id="e1e5e-163">L'identificatore univoco per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-163">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="e1e5e-164">Testo etichetta riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-164">Tile label text</span></span> | <span data-ttu-id="e1e5e-165">Il testo che verrà visualizzato per il riquadro Self service.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-165">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="e1e5e-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1e5e-166">Description</span></span> | <span data-ttu-id="e1e5e-167">Una descrizione del riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-167">A description of the tile.</span></span> |
   | <span data-ttu-id="e1e5e-168">Indirizzo Internet</span><span class="sxs-lookup"><span data-stu-id="e1e5e-168">Internet address</span></span> | <span data-ttu-id="e1e5e-169">Immettere l'URL alla pagina Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-169">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="e1e5e-170">Dimensioni riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-170">Tile size</span></span> | <span data-ttu-id="e1e5e-171">La dimensione del riquadro: Piccolo, Medio o Grande.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-171">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="e1e5e-172">Destinatario</span><span class="sxs-lookup"><span data-stu-id="e1e5e-172">Target</span></span> | <span data-ttu-id="e1e5e-173">Specifica se la pagina deve essere aperta in una nuova finestra o nella finestra corrente.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-173">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="e1e5e-174">Immagine di sfondo riquadro</span><span class="sxs-lookup"><span data-stu-id="e1e5e-174">Tile background image</span></span> | <span data-ttu-id="e1e5e-175">L'URL dell'immagine da utilizzare per il riquadro (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="e1e5e-175">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="e1e5e-176">Avvio</span><span class="sxs-lookup"><span data-stu-id="e1e5e-176">Start</span></span> | <span data-ttu-id="e1e5e-177">La data e l'ora di inizio della disponibilità del riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-177">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="e1e5e-178">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="e1e5e-178">End</span></span> | <span data-ttu-id="e1e5e-179">La data e l'ora di fine della disponibilità del riquadro.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-179">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="e1e5e-180">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e1e5e-180">Select **Save**.</span></span>
