---
title: Livello di valutazione
description: Questo argomento descrive l'entità Livello di valutazione per Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eac80599de07a045aa233f1cdfd16fe0db8733a2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800335"
---
# <a name="rating-level"></a><span data-ttu-id="784e7-103">Livello di valutazione</span><span class="sxs-lookup"><span data-stu-id="784e7-103">Rating level</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="784e7-104">Questo argomento descrive l'entità Livello di valutazione per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="784e7-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="784e7-105">Nome fisico: mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="784e7-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="784e7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="784e7-106">Description</span></span>

<span data-ttu-id="784e7-107">Questa entità fornisce i livelli di valutazione disponibili per le competenze.</span><span class="sxs-lookup"><span data-stu-id="784e7-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="784e7-108">I livelli di valutazione si applicano a tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="784e7-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="784e7-109">Rappresentazione JSON</span><span class="sxs-lookup"><span data-stu-id="784e7-109">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="784e7-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="784e7-110">Properties</span></span>

| <span data-ttu-id="784e7-111">Proprietà</span><span class="sxs-lookup"><span data-stu-id="784e7-111">Property</span></span><br><span data-ttu-id="784e7-112">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="784e7-112">**Physical name**</span></span><br><span data-ttu-id="784e7-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="784e7-113">**_Type_**</span></span> | <span data-ttu-id="784e7-114">Utilizza</span><span class="sxs-lookup"><span data-stu-id="784e7-114">Use</span></span> | <span data-ttu-id="784e7-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="784e7-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="784e7-116">**ID entità livello di valutazione**</span><span class="sxs-lookup"><span data-stu-id="784e7-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="784e7-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="784e7-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="784e7-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="784e7-118">*GUID*</span></span> | <span data-ttu-id="784e7-119">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="784e7-119">Read-only</span></span><br><span data-ttu-id="784e7-120">Richiesto</span><span class="sxs-lookup"><span data-stu-id="784e7-120">Required</span></span><br><span data-ttu-id="784e7-121">Generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="784e7-121">System-generated</span></span> | <span data-ttu-id="784e7-122">L'identificatore univoco generato dal sistema per il livello.</span><span class="sxs-lookup"><span data-stu-id="784e7-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="784e7-123">**ID livello valutazione**</span><span class="sxs-lookup"><span data-stu-id="784e7-123">**Rating Level ID**</span></span><br><span data-ttu-id="784e7-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="784e7-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="784e7-125">*String*</span><span class="sxs-lookup"><span data-stu-id="784e7-125">*String*</span></span> | <span data-ttu-id="784e7-126">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="784e7-126">Read/write</span></span><br><span data-ttu-id="784e7-127">Richiesto</span><span class="sxs-lookup"><span data-stu-id="784e7-127">Required</span></span> | <span data-ttu-id="784e7-128">Identificatore univoco leggibile dall'utente per il livello.</span><span class="sxs-lookup"><span data-stu-id="784e7-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="784e7-129">**ID modello di valutazione**</span><span class="sxs-lookup"><span data-stu-id="784e7-129">**Rating Model ID**</span></span><br><span data-ttu-id="784e7-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="784e7-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="784e7-131">*String*</span><span class="sxs-lookup"><span data-stu-id="784e7-131">*String*</span></span> | <span data-ttu-id="784e7-132">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="784e7-132">Read/write</span></span><br><span data-ttu-id="784e7-133">Richiesto</span><span class="sxs-lookup"><span data-stu-id="784e7-133">Required</span></span> | <span data-ttu-id="784e7-134">Il modello di valutazione a cui appartiene il livello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="784e7-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="784e7-135">**ID entità modello di valutazione**</span><span class="sxs-lookup"><span data-stu-id="784e7-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="784e7-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="784e7-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="784e7-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="784e7-137">*GUID*</span></span> | <span data-ttu-id="784e7-138">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="784e7-138">Read-only</span></span><br><span data-ttu-id="784e7-139">Richiesto</span><span class="sxs-lookup"><span data-stu-id="784e7-139">Required</span></span><br><span data-ttu-id="784e7-140">Chiave esterna: mshr_hcmratingmodelentityid di mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="784e7-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="784e7-141">L'identificatore generato dal sistema per il modello di valutazione a cui appartiene il livello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="784e7-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="784e7-142">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="784e7-142">**Description**</span></span><br><span data-ttu-id="784e7-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="784e7-143">mshr_description</span></span><br><span data-ttu-id="784e7-144">*String*</span><span class="sxs-lookup"><span data-stu-id="784e7-144">*String*</span></span> | <span data-ttu-id="784e7-145">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="784e7-145">Read/write</span></span><br><span data-ttu-id="784e7-146">Richiesto</span><span class="sxs-lookup"><span data-stu-id="784e7-146">Required</span></span> | <span data-ttu-id="784e7-147">La descrizione del livello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="784e7-147">The description of the rating level.</span></span> |
| <span data-ttu-id="784e7-148">**Fattore**</span><span class="sxs-lookup"><span data-stu-id="784e7-148">**Factor**</span></span><br><span data-ttu-id="784e7-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="784e7-149">mshr_factor</span></span><br><span data-ttu-id="784e7-150">*Integer*</span><span class="sxs-lookup"><span data-stu-id="784e7-150">*Integer*</span></span> | <span data-ttu-id="784e7-151">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="784e7-151">Read/write</span></span><br><span data-ttu-id="784e7-152">Richiesto</span><span class="sxs-lookup"><span data-stu-id="784e7-152">Required</span></span> | <span data-ttu-id="784e7-153">Il fattore per il livello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="784e7-153">The factor for the rating level.</span></span> <span data-ttu-id="784e7-154">Quando si confrontano gli articoli con un numero di livelli di valutazione diversi, il fattore viene utilizzato per normalizzare i punteggi.</span><span class="sxs-lookup"><span data-stu-id="784e7-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="784e7-155">Il valore deve essere un numero intero compreso tra 0 e 9.</span><span class="sxs-lookup"><span data-stu-id="784e7-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="784e7-156">**Nota**</span><span class="sxs-lookup"><span data-stu-id="784e7-156">**Note**</span></span><br><span data-ttu-id="784e7-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="784e7-157">mshr_note</span></span><br><span data-ttu-id="784e7-158">*String*</span><span class="sxs-lookup"><span data-stu-id="784e7-158">*String*</span></span> | <span data-ttu-id="784e7-159">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="784e7-159">Read/write</span></span><br><span data-ttu-id="784e7-160">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="784e7-160">Optional</span></span> | <span data-ttu-id="784e7-161">Eventuali note associate al livello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="784e7-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="784e7-162">**Campo principale**</span><span class="sxs-lookup"><span data-stu-id="784e7-162">**Primary Field**</span></span><br><span data-ttu-id="784e7-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="784e7-163">mshr_primaryfield</span></span><br><span data-ttu-id="784e7-164">*String*</span><span class="sxs-lookup"><span data-stu-id="784e7-164">*String*</span></span> | <span data-ttu-id="784e7-165">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="784e7-165">Read-only</span></span><br><span data-ttu-id="784e7-166">Richiesto</span><span class="sxs-lookup"><span data-stu-id="784e7-166">Required</span></span> | <span data-ttu-id="784e7-167">Campo da utilizzare come un identificatore principale del record dell'entità.</span><span class="sxs-lookup"><span data-stu-id="784e7-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="784e7-168">Combinazione di ID livello di valutazione e ID modello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="784e7-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="784e7-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="784e7-169">See also</span></span>

[<span data-ttu-id="784e7-170">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="784e7-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="784e7-171">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="784e7-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]