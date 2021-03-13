---
title: Certificato della persona
description: Questo argomento descrive l'entità Certificato della persona per Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fa4582dc00341a647f1ea43ed16d9dce8bfcf688
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125355"
---
# <a name="person-certificate"></a><span data-ttu-id="a3181-103">Certificato della persona</span><span class="sxs-lookup"><span data-stu-id="a3181-103">Person certificate</span></span>

<span data-ttu-id="a3181-104">Questo argomento descrive l'entità Certificato della persona per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a3181-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="a3181-105">Nome fisico: mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="a3181-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="a3181-106">descrizione</span><span class="sxs-lookup"><span data-stu-id="a3181-106">Description</span></span>

<span data-ttu-id="a3181-107">Questa entità descrive i certificati professionali di un candidato.</span><span class="sxs-lookup"><span data-stu-id="a3181-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="a3181-108">Rappresentazione JSON</span><span class="sxs-lookup"><span data-stu-id="a3181-108">JSON representation</span></span>

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="a3181-109">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a3181-109">Properties</span></span>

| <span data-ttu-id="a3181-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a3181-110">Property</span></span><br><span data-ttu-id="a3181-111">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="a3181-111">**Physical name**</span></span><br><span data-ttu-id="a3181-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="a3181-112">**_Type_**</span></span> | <span data-ttu-id="a3181-113">Utilizza</span><span class="sxs-lookup"><span data-stu-id="a3181-113">Use</span></span> | <span data-ttu-id="a3181-114">descrizione</span><span class="sxs-lookup"><span data-stu-id="a3181-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a3181-115">**ID entità certificato persona**</span><span class="sxs-lookup"><span data-stu-id="a3181-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="a3181-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="a3181-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="a3181-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a3181-117">*GUID*</span></span> | <span data-ttu-id="a3181-118">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a3181-118">Read-only</span></span><br><span data-ttu-id="a3181-119">Richiesto</span><span class="sxs-lookup"><span data-stu-id="a3181-119">Required</span></span> | <span data-ttu-id="a3181-120">Identificatore univoco generato dal sistema per il record dell'entità del certificato della persona.</span><span class="sxs-lookup"><span data-stu-id="a3181-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="a3181-121">**Numero parte**</span><span class="sxs-lookup"><span data-stu-id="a3181-121">**Party Number**</span></span><br><span data-ttu-id="a3181-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="a3181-122">mshr_partynumber</span></span><br><span data-ttu-id="a3181-123">*String*</span><span class="sxs-lookup"><span data-stu-id="a3181-123">*String*</span></span> | <span data-ttu-id="a3181-124">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="a3181-124">Read/write</span></span><br><span data-ttu-id="a3181-125">Richiesto</span><span class="sxs-lookup"><span data-stu-id="a3181-125">Required</span></span> | <span data-ttu-id="a3181-126">L'ID della parte (persona) associata al candidato.</span><span class="sxs-lookup"><span data-stu-id="a3181-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="a3181-127">**Valore ID persona**</span><span class="sxs-lookup"><span data-stu-id="a3181-127">**Person ID Value**</span></span><br><span data-ttu-id="a3181-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="a3181-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="a3181-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a3181-129">*GUID*</span></span> | <span data-ttu-id="a3181-130">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a3181-130">Read-only</span></span><br><span data-ttu-id="a3181-131">Richiesto</span><span class="sxs-lookup"><span data-stu-id="a3181-131">Required</span></span><br><span data-ttu-id="a3181-132">Chiave esterna: mshr_dirpersonentityid di mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="a3181-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="a3181-133">L'identificatore generato dal sistema per il record dell'entità della parte (persona).</span><span class="sxs-lookup"><span data-stu-id="a3181-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="a3181-134">**ID tipo di certificato**</span><span class="sxs-lookup"><span data-stu-id="a3181-134">**Certificate Type ID**</span></span><br><span data-ttu-id="a3181-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="a3181-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="a3181-136">*String*</span><span class="sxs-lookup"><span data-stu-id="a3181-136">*String*</span></span> | <span data-ttu-id="a3181-137">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="a3181-137">Read/write</span></span><br><span data-ttu-id="a3181-138">Richiesto</span><span class="sxs-lookup"><span data-stu-id="a3181-138">Required</span></span> |  <span data-ttu-id="a3181-139">L'identificatore del tipo di certificato definito in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a3181-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="a3181-140">**Valore ID tipo di certificato**</span><span class="sxs-lookup"><span data-stu-id="a3181-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="a3181-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="a3181-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="a3181-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a3181-142">*GUID*</span></span> | <span data-ttu-id="a3181-143">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a3181-143">Read-only</span></span><br><span data-ttu-id="a3181-144">Richiesto</span><span class="sxs-lookup"><span data-stu-id="a3181-144">Required</span></span><br><span data-ttu-id="a3181-145">Chiave esterna: mshr_hcmcertificatetypeentityid di mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="a3181-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="a3181-146">Identificatore univoco generato dal sistema del tipo di certificato dell'entità associata.</span><span class="sxs-lookup"><span data-stu-id="a3181-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="a3181-147">**Data di inizio**</span><span class="sxs-lookup"><span data-stu-id="a3181-147">**Start Date**</span></span><br><span data-ttu-id="a3181-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="a3181-148">mshr_startdate</span></span><br><span data-ttu-id="a3181-149">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="a3181-149">*Datetime*</span></span> | <span data-ttu-id="a3181-150">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="a3181-150">Read/write</span></span><br><span data-ttu-id="a3181-151">Richiesto</span><span class="sxs-lookup"><span data-stu-id="a3181-151">Required</span></span> | <span data-ttu-id="a3181-152">La data in cui è stato rilasciato il certificato.</span><span class="sxs-lookup"><span data-stu-id="a3181-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="a3181-153">**Data di fine**</span><span class="sxs-lookup"><span data-stu-id="a3181-153">**End Date**</span></span><br><span data-ttu-id="a3181-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="a3181-154">mshr_enddate</span></span><br><span data-ttu-id="a3181-155">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="a3181-155">*Datetime*</span></span> | <span data-ttu-id="a3181-156">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="a3181-156">Read/write</span></span><br><span data-ttu-id="a3181-157">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="a3181-157">Optional</span></span> | <span data-ttu-id="a3181-158">La data in cui scadrà il certificato.</span><span class="sxs-lookup"><span data-stu-id="a3181-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="a3181-159">**Note**</span><span class="sxs-lookup"><span data-stu-id="a3181-159">**Notes**</span></span><br><span data-ttu-id="a3181-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="a3181-160">mshr_notes</span></span><br><span data-ttu-id="a3181-161">*String*</span><span class="sxs-lookup"><span data-stu-id="a3181-161">*String*</span></span> | <span data-ttu-id="a3181-162">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="a3181-162">Read/write</span></span><br><span data-ttu-id="a3181-163">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="a3181-163">Optional</span></span> | <span data-ttu-id="a3181-164">Note per l'utilizzo da parte di responsabili delle assunzioni e reclutatori.</span><span class="sxs-lookup"><span data-stu-id="a3181-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="a3181-165">**Campo principale**</span><span class="sxs-lookup"><span data-stu-id="a3181-165">**Primary Field**</span></span><br><span data-ttu-id="a3181-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="a3181-166">mshr_primaryfield</span></span><br><span data-ttu-id="a3181-167">*String*</span><span class="sxs-lookup"><span data-stu-id="a3181-167">*String*</span></span> | <span data-ttu-id="a3181-168">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a3181-168">Read-only</span></span><br><span data-ttu-id="a3181-169">Richiesto</span><span class="sxs-lookup"><span data-stu-id="a3181-169">Required</span></span> |  <span data-ttu-id="a3181-170">Campo da utilizzare come un identificatore principale del record dell'entità.</span><span class="sxs-lookup"><span data-stu-id="a3181-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="a3181-171">Combinazione di numero di parte, ID tipo di certificato e data di inizio.</span><span class="sxs-lookup"><span data-stu-id="a3181-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a3181-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3181-172">See also</span></span>

[<span data-ttu-id="a3181-173">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="a3181-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="a3181-174">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="a3181-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

