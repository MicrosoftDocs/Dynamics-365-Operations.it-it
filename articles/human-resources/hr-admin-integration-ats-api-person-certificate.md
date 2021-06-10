---
title: Certificato della persona
description: Questo argomento descrive l'entità Certificato della persona per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 5cdd742d6d36ccd7136f95e416507ed6e5e5a75a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055198"
---
# <a name="person-certificate"></a><span data-ttu-id="4dc03-103">Certificato della persona</span><span class="sxs-lookup"><span data-stu-id="4dc03-103">Person certificate</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4dc03-104">Questo argomento descrive l'entità Certificato della persona per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4dc03-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="4dc03-105">Nome fisico: mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="4dc03-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="4dc03-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4dc03-106">Description</span></span>

<span data-ttu-id="4dc03-107">Questa entità descrive i certificati professionali di un candidato.</span><span class="sxs-lookup"><span data-stu-id="4dc03-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="4dc03-108">Rappresentazione JSON</span><span class="sxs-lookup"><span data-stu-id="4dc03-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="4dc03-109">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4dc03-109">Properties</span></span>

| <span data-ttu-id="4dc03-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4dc03-110">Property</span></span><br><span data-ttu-id="4dc03-111">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="4dc03-111">**Physical name**</span></span><br><span data-ttu-id="4dc03-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="4dc03-112">**_Type_**</span></span> | <span data-ttu-id="4dc03-113">Utilizza</span><span class="sxs-lookup"><span data-stu-id="4dc03-113">Use</span></span> | <span data-ttu-id="4dc03-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4dc03-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4dc03-115">**ID entità certificato persona**</span><span class="sxs-lookup"><span data-stu-id="4dc03-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="4dc03-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="4dc03-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="4dc03-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4dc03-117">*GUID*</span></span> | <span data-ttu-id="4dc03-118">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4dc03-118">Read-only</span></span><br><span data-ttu-id="4dc03-119">Richiesto</span><span class="sxs-lookup"><span data-stu-id="4dc03-119">Required</span></span> | <span data-ttu-id="4dc03-120">Identificatore univoco generato dal sistema per il record dell'entità del certificato della persona.</span><span class="sxs-lookup"><span data-stu-id="4dc03-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="4dc03-121">**Numero parte**</span><span class="sxs-lookup"><span data-stu-id="4dc03-121">**Party Number**</span></span><br><span data-ttu-id="4dc03-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="4dc03-122">mshr_partynumber</span></span><br><span data-ttu-id="4dc03-123">*String*</span><span class="sxs-lookup"><span data-stu-id="4dc03-123">*String*</span></span> | <span data-ttu-id="4dc03-124">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="4dc03-124">Read/write</span></span><br><span data-ttu-id="4dc03-125">Richiesto</span><span class="sxs-lookup"><span data-stu-id="4dc03-125">Required</span></span> | <span data-ttu-id="4dc03-126">L'ID della parte (persona) associata al candidato.</span><span class="sxs-lookup"><span data-stu-id="4dc03-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="4dc03-127">**Valore ID persona**</span><span class="sxs-lookup"><span data-stu-id="4dc03-127">**Person ID Value**</span></span><br><span data-ttu-id="4dc03-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="4dc03-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="4dc03-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4dc03-129">*GUID*</span></span> | <span data-ttu-id="4dc03-130">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4dc03-130">Read-only</span></span><br><span data-ttu-id="4dc03-131">Richiesto</span><span class="sxs-lookup"><span data-stu-id="4dc03-131">Required</span></span><br><span data-ttu-id="4dc03-132">Chiave esterna: mshr_dirpersonentityid di mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="4dc03-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="4dc03-133">L'identificatore generato dal sistema per il record dell'entità della parte (persona).</span><span class="sxs-lookup"><span data-stu-id="4dc03-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="4dc03-134">**ID tipo di certificato**</span><span class="sxs-lookup"><span data-stu-id="4dc03-134">**Certificate Type ID**</span></span><br><span data-ttu-id="4dc03-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="4dc03-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="4dc03-136">*String*</span><span class="sxs-lookup"><span data-stu-id="4dc03-136">*String*</span></span> | <span data-ttu-id="4dc03-137">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="4dc03-137">Read/write</span></span><br><span data-ttu-id="4dc03-138">Richiesto</span><span class="sxs-lookup"><span data-stu-id="4dc03-138">Required</span></span> |  <span data-ttu-id="4dc03-139">L'identificatore del tipo di certificato definito in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4dc03-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="4dc03-140">**Valore ID tipo di certificato**</span><span class="sxs-lookup"><span data-stu-id="4dc03-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="4dc03-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="4dc03-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="4dc03-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4dc03-142">*GUID*</span></span> | <span data-ttu-id="4dc03-143">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4dc03-143">Read-only</span></span><br><span data-ttu-id="4dc03-144">Richiesto</span><span class="sxs-lookup"><span data-stu-id="4dc03-144">Required</span></span><br><span data-ttu-id="4dc03-145">Chiave esterna: mshr_hcmcertificatetypeentityid di mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="4dc03-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="4dc03-146">Identificatore univoco generato dal sistema del tipo di certificato dell'entità associata.</span><span class="sxs-lookup"><span data-stu-id="4dc03-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="4dc03-147">**Data di inizio**</span><span class="sxs-lookup"><span data-stu-id="4dc03-147">**Start Date**</span></span><br><span data-ttu-id="4dc03-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="4dc03-148">mshr_startdate</span></span><br><span data-ttu-id="4dc03-149">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="4dc03-149">*Datetime*</span></span> | <span data-ttu-id="4dc03-150">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="4dc03-150">Read/write</span></span><br><span data-ttu-id="4dc03-151">Richiesto</span><span class="sxs-lookup"><span data-stu-id="4dc03-151">Required</span></span> | <span data-ttu-id="4dc03-152">La data in cui è stato rilasciato il certificato.</span><span class="sxs-lookup"><span data-stu-id="4dc03-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="4dc03-153">**Data di fine**</span><span class="sxs-lookup"><span data-stu-id="4dc03-153">**End Date**</span></span><br><span data-ttu-id="4dc03-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="4dc03-154">mshr_enddate</span></span><br><span data-ttu-id="4dc03-155">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="4dc03-155">*Datetime*</span></span> | <span data-ttu-id="4dc03-156">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="4dc03-156">Read/write</span></span><br><span data-ttu-id="4dc03-157">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="4dc03-157">Optional</span></span> | <span data-ttu-id="4dc03-158">La data in cui scadrà il certificato.</span><span class="sxs-lookup"><span data-stu-id="4dc03-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="4dc03-159">**Note**</span><span class="sxs-lookup"><span data-stu-id="4dc03-159">**Notes**</span></span><br><span data-ttu-id="4dc03-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="4dc03-160">mshr_notes</span></span><br><span data-ttu-id="4dc03-161">*String*</span><span class="sxs-lookup"><span data-stu-id="4dc03-161">*String*</span></span> | <span data-ttu-id="4dc03-162">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="4dc03-162">Read/write</span></span><br><span data-ttu-id="4dc03-163">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="4dc03-163">Optional</span></span> | <span data-ttu-id="4dc03-164">Note per l'utilizzo da parte di responsabili delle assunzioni e reclutatori.</span><span class="sxs-lookup"><span data-stu-id="4dc03-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="4dc03-165">**Campo principale**</span><span class="sxs-lookup"><span data-stu-id="4dc03-165">**Primary Field**</span></span><br><span data-ttu-id="4dc03-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="4dc03-166">mshr_primaryfield</span></span><br><span data-ttu-id="4dc03-167">*String*</span><span class="sxs-lookup"><span data-stu-id="4dc03-167">*String*</span></span> | <span data-ttu-id="4dc03-168">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4dc03-168">Read-only</span></span><br><span data-ttu-id="4dc03-169">Richiesto</span><span class="sxs-lookup"><span data-stu-id="4dc03-169">Required</span></span> |  <span data-ttu-id="4dc03-170">Campo da utilizzare come un identificatore principale del record dell'entità.</span><span class="sxs-lookup"><span data-stu-id="4dc03-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="4dc03-171">Combinazione di numero di parte, ID tipo di certificato e data di inizio.</span><span class="sxs-lookup"><span data-stu-id="4dc03-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4dc03-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dc03-172">See also</span></span>

[<span data-ttu-id="4dc03-173">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="4dc03-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="4dc03-174">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="4dc03-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]