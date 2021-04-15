---
title: Configurare il dipendente self-service
description: In Microsoft Dynamics 365 Human Resources, è possibile configurare riquadri per la navigazione di livello superiore in Dipendente self-service.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3e763a09e0a0f13eb7222a6ffbcb31b6230b83f4
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797937"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="7ed55-103">Configurare il dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="7ed55-103">Configure employee self service</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7ed55-104">In Microsoft Dynamics 365 Human Resources, è possibile configurare riquadri per la navigazione di livello superiore in Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="7ed55-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="7ed55-105">I riquadri Piano benefit indirizzano gli utenti ai piani di benefit per i quali sono idonei.</span><span class="sxs-lookup"><span data-stu-id="7ed55-105">Benefit plan tiles direct users to benefit plans that they're eligible for.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="7ed55-106">Impostare un riquadro Piani di benefit</span><span class="sxs-lookup"><span data-stu-id="7ed55-106">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="7ed55-107">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri di Dipendente self-service**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="7ed55-108">Selezionare la scheda **Impostazione riquadro Piani di benefit**, quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-108">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="7ed55-109">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="7ed55-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="7ed55-110">Campo</span><span class="sxs-lookup"><span data-stu-id="7ed55-110">Field</span></span> | <span data-ttu-id="7ed55-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ed55-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="7ed55-112">**ID riquadro**</span><span class="sxs-lookup"><span data-stu-id="7ed55-112">**Tile ID**</span></span> | <span data-ttu-id="7ed55-113">L'identificatore univoco per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="7ed55-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="7ed55-114">**Testo etichetta riquadro**</span><span class="sxs-lookup"><span data-stu-id="7ed55-114">**Tile label text**</span></span> | <span data-ttu-id="7ed55-115">Il testo che verrà visualizzato per il riquadro Self service.</span><span class="sxs-lookup"><span data-stu-id="7ed55-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="7ed55-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7ed55-116">**Description**</span></span> | <span data-ttu-id="7ed55-117">Una descrizione del riquadro.</span><span class="sxs-lookup"><span data-stu-id="7ed55-117">A description of the tile.</span></span> |
   | <span data-ttu-id="7ed55-118">**Indirizzo Internet**</span><span class="sxs-lookup"><span data-stu-id="7ed55-118">**Internet address**</span></span> | <span data-ttu-id="7ed55-119">Immettere l'URL alla pagina Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="7ed55-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="7ed55-120">**Dimensioni riquadro**</span><span class="sxs-lookup"><span data-stu-id="7ed55-120">**Tile size**</span></span> | <span data-ttu-id="7ed55-121">La dimensione del riquadro: Piccolo, Medio o Grande.</span><span class="sxs-lookup"><span data-stu-id="7ed55-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="7ed55-122">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="7ed55-122">**Target**</span></span> | <span data-ttu-id="7ed55-123">Specifica se la pagina deve essere aperta in una nuova finestra o nella finestra corrente.</span><span class="sxs-lookup"><span data-stu-id="7ed55-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="7ed55-124">**Immagine di sfondo riquadro**</span><span class="sxs-lookup"><span data-stu-id="7ed55-124">**Tile background image**</span></span> | <span data-ttu-id="7ed55-125">L'URL dell'immagine da utilizzare per il riquadro (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="7ed55-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="7ed55-126">**Avvio**</span><span class="sxs-lookup"><span data-stu-id="7ed55-126">**Start**</span></span> | <span data-ttu-id="7ed55-127">La data e l'ora di inizio della disponibilità del riquadro.</span><span class="sxs-lookup"><span data-stu-id="7ed55-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="7ed55-128">**Fine periodo**</span><span class="sxs-lookup"><span data-stu-id="7ed55-128">**End**</span></span> | <span data-ttu-id="7ed55-129">La data e l'ora di fine della disponibilità del riquadro.</span><span class="sxs-lookup"><span data-stu-id="7ed55-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="7ed55-130">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-130">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="7ed55-131">Impostare un riquadro Piano di credito flessibile</span><span class="sxs-lookup"><span data-stu-id="7ed55-131">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="7ed55-132">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri di Dipendente self-service**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="7ed55-133">Selezionare la scheda **Impostazione riquadro Piano di credito flessibile**, quindi selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-133">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="7ed55-134">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="7ed55-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="7ed55-135">Campo</span><span class="sxs-lookup"><span data-stu-id="7ed55-135">Field</span></span> | <span data-ttu-id="7ed55-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ed55-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="7ed55-137">**ID riquadro**</span><span class="sxs-lookup"><span data-stu-id="7ed55-137">**Tile ID**</span></span> | <span data-ttu-id="7ed55-138">L'identificatore univoco per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="7ed55-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="7ed55-139">**Testo etichetta riquadro**</span><span class="sxs-lookup"><span data-stu-id="7ed55-139">**Tile label text**</span></span> | <span data-ttu-id="7ed55-140">Il testo che verrà visualizzato per il riquadro Self service.</span><span class="sxs-lookup"><span data-stu-id="7ed55-140">The text that will appear for the tile on Self service.</span></span> |
   | <span data-ttu-id="7ed55-141">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7ed55-141">**Description**</span></span> | <span data-ttu-id="7ed55-142">Una descrizione del riquadro.</span><span class="sxs-lookup"><span data-stu-id="7ed55-142">A description of the tile.</span></span> |
   | <span data-ttu-id="7ed55-143">**Indirizzo Internet**</span><span class="sxs-lookup"><span data-stu-id="7ed55-143">**Internet address**</span></span> | <span data-ttu-id="7ed55-144">Immettere l'URL alla pagina Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="7ed55-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="7ed55-145">**Dimensioni riquadro**</span><span class="sxs-lookup"><span data-stu-id="7ed55-145">**Tile size**</span></span> | <span data-ttu-id="7ed55-146">La dimensione del riquadro: Piccolo, Medio o Grande.</span><span class="sxs-lookup"><span data-stu-id="7ed55-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="7ed55-147">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="7ed55-147">**Target**</span></span> | <span data-ttu-id="7ed55-148">Specifica se la pagina deve essere aperta in una nuova finestra o nella finestra corrente.</span><span class="sxs-lookup"><span data-stu-id="7ed55-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="7ed55-149">**Immagine di sfondo riquadro**</span><span class="sxs-lookup"><span data-stu-id="7ed55-149">**Tile background image**</span></span> | <span data-ttu-id="7ed55-150">L'URL dell'immagine da utilizzare per il riquadro (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="7ed55-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="7ed55-151">**Avvio**</span><span class="sxs-lookup"><span data-stu-id="7ed55-151">**Start**</span></span> | <span data-ttu-id="7ed55-152">La data e l'ora di inizio della disponibilità del riquadro.</span><span class="sxs-lookup"><span data-stu-id="7ed55-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="7ed55-153">**Fine periodo**</span><span class="sxs-lookup"><span data-stu-id="7ed55-153">**End**</span></span> | <span data-ttu-id="7ed55-154">La data e l'ora di fine della disponibilità del riquadro.</span><span class="sxs-lookup"><span data-stu-id="7ed55-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="7ed55-155">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7ed55-155">Select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]