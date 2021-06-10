---
title: Screening persona
description: Questo argomento descrive l'entità Screening persona per Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9d29b26094e307c3f68d57f297ab3614f3a5ccae
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059282"
---
# <a name="person-screening"></a><span data-ttu-id="b243c-103">Screening persona</span><span class="sxs-lookup"><span data-stu-id="b243c-103">Person screening</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b243c-104">Questo argomento descrive l'entità Screening persona per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b243c-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="b243c-105">Nome fisico: mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="b243c-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="b243c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b243c-106">Description</span></span>

<span data-ttu-id="b243c-107">Questa entità descrive gli screening che un candidato ha superato o deve passare per un impiego.</span><span class="sxs-lookup"><span data-stu-id="b243c-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="b243c-108">Rappresentazione JSON</span><span class="sxs-lookup"><span data-stu-id="b243c-108">JSON representation</span></span>

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a><span data-ttu-id="b243c-109">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b243c-109">Properties</span></span>

| <span data-ttu-id="b243c-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b243c-110">Property</span></span><br><span data-ttu-id="b243c-111">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="b243c-111">**Physical name**</span></span><br><span data-ttu-id="b243c-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="b243c-112">**_Type_**</span></span> | <span data-ttu-id="b243c-113">Utilizza</span><span class="sxs-lookup"><span data-stu-id="b243c-113">Use</span></span> | <span data-ttu-id="b243c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b243c-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b243c-115">**ID entità screening persona**</span><span class="sxs-lookup"><span data-stu-id="b243c-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="b243c-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="b243c-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="b243c-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b243c-117">*GUID*</span></span> | <span data-ttu-id="b243c-118">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="b243c-118">Read-only</span></span><br><span data-ttu-id="b243c-119">Richiesto</span><span class="sxs-lookup"><span data-stu-id="b243c-119">Required</span></span><br><span data-ttu-id="b243c-120">Generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="b243c-120">System-generated</span></span> | <span data-ttu-id="b243c-121">Identificatore primario univoco per il record di screening della persona.</span><span class="sxs-lookup"><span data-stu-id="b243c-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="b243c-122">**Numero parte**</span><span class="sxs-lookup"><span data-stu-id="b243c-122">**Party Number**</span></span><br><span data-ttu-id="b243c-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="b243c-123">mshr_partynumber</span></span><br><span data-ttu-id="b243c-124">*String*</span><span class="sxs-lookup"><span data-stu-id="b243c-124">*String*</span></span> | <span data-ttu-id="b243c-125">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="b243c-125">Read/write</span></span><br><span data-ttu-id="b243c-126">Richiesto</span><span class="sxs-lookup"><span data-stu-id="b243c-126">Required</span></span> | <span data-ttu-id="b243c-127">Il numero della parte (persona) associato al candidato.</span><span class="sxs-lookup"><span data-stu-id="b243c-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="b243c-128">**Valore ID persona**</span><span class="sxs-lookup"><span data-stu-id="b243c-128">**Person ID Value**</span></span><br><span data-ttu-id="b243c-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="b243c-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="b243c-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b243c-130">*GUID*</span></span> | <span data-ttu-id="b243c-131">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="b243c-131">Read-only</span></span><br><span data-ttu-id="b243c-132">Richiesto</span><span class="sxs-lookup"><span data-stu-id="b243c-132">Required</span></span><br><span data-ttu-id="b243c-133">Chiave esterna: mshr_dirpersonentityid di mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="b243c-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="b243c-134">L'identificatore generato dal sistema per il record dell'entità della parte (persona).</span><span class="sxs-lookup"><span data-stu-id="b243c-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="b243c-135">**ID tipo di screening**</span><span class="sxs-lookup"><span data-stu-id="b243c-135">**Screening Type ID**</span></span><br><span data-ttu-id="b243c-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="b243c-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="b243c-137">*String*</span><span class="sxs-lookup"><span data-stu-id="b243c-137">*String*</span></span> | <span data-ttu-id="b243c-138">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="b243c-138">Read/write</span></span><br><span data-ttu-id="b243c-139">Richiesto</span><span class="sxs-lookup"><span data-stu-id="b243c-139">Required</span></span><br><span data-ttu-id="b243c-140">Chiave esterna: ScreeningType</span><span class="sxs-lookup"><span data-stu-id="b243c-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="b243c-141">L'identificatore del tipo di screening definito in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b243c-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="b243c-142">**Valore ID tipo di screening**</span><span class="sxs-lookup"><span data-stu-id="b243c-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="b243c-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="b243c-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="b243c-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b243c-144">*GUID*</span></span> | <span data-ttu-id="b243c-145">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="b243c-145">Read-only</span></span><br><span data-ttu-id="b243c-146">Richiesto</span><span class="sxs-lookup"><span data-stu-id="b243c-146">Required</span></span><br><span data-ttu-id="b243c-147">Chiave esterna: mshr_hcmscreeningtypeentityid di mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="b243c-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="b243c-148">Identificatore generato dal sistema per il record del tipo di screening dell'entità associata.</span><span class="sxs-lookup"><span data-stu-id="b243c-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="b243c-149">**Richiesto entro il**</span><span class="sxs-lookup"><span data-stu-id="b243c-149">**Required By**</span></span><br><span data-ttu-id="b243c-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="b243c-150">mshr_requiredby</span></span><br><span data-ttu-id="b243c-151">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="b243c-151">*Datetime*</span></span> | <span data-ttu-id="b243c-152">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="b243c-152">Read/write</span></span><br><span data-ttu-id="b243c-153">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="b243c-153">Optional</span></span> | <span data-ttu-id="b243c-154">La data entro la quale lo screening deve essere completato.</span><span class="sxs-lookup"><span data-stu-id="b243c-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="b243c-155">**Stato**</span><span class="sxs-lookup"><span data-stu-id="b243c-155">**Status**</span></span><br><span data-ttu-id="b243c-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="b243c-156">mshr_status</span></span><br><span data-ttu-id="b243c-157">*set di opzioni mshr_hcmcompletionstatus*</span><span class="sxs-lookup"><span data-stu-id="b243c-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="b243c-158">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="b243c-158">Read/write</span></span><br><span data-ttu-id="b243c-159">Richiesto</span><span class="sxs-lookup"><span data-stu-id="b243c-159">Required</span></span> | <span data-ttu-id="b243c-160">Fornisce lo stato del candidato per lo screening.</span><span class="sxs-lookup"><span data-stu-id="b243c-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="b243c-161">**Data di completamento**</span><span class="sxs-lookup"><span data-stu-id="b243c-161">**Completed Date**</span></span><br><span data-ttu-id="b243c-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="b243c-162">mshr_completeddate</span></span><br><span data-ttu-id="b243c-163">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="b243c-163">*Datetime*</span></span> | <span data-ttu-id="b243c-164">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="b243c-164">Read/write</span></span><br><span data-ttu-id="b243c-165">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="b243c-165">Optional</span></span> | <span data-ttu-id="b243c-166">Data in cui lo screening è stato completato.</span><span class="sxs-lookup"><span data-stu-id="b243c-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="b243c-167">**Note**</span><span class="sxs-lookup"><span data-stu-id="b243c-167">**Notes**</span></span><br><span data-ttu-id="b243c-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="b243c-168">mshr_note</span></span><br><span data-ttu-id="b243c-169">*String*</span><span class="sxs-lookup"><span data-stu-id="b243c-169">*String*</span></span> | <span data-ttu-id="b243c-170">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="b243c-170">Read/write</span></span><br><span data-ttu-id="b243c-171">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="b243c-171">Optional</span></span> | <span data-ttu-id="b243c-172">Note per l'utilizzo da parte di responsabili delle assunzioni e reclutatori.</span><span class="sxs-lookup"><span data-stu-id="b243c-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b243c-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b243c-173">See also</span></span>

[<span data-ttu-id="b243c-174">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="b243c-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="b243c-175">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="b243c-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]