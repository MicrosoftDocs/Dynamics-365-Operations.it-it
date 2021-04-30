---
title: Dettagli retribuzione per posizioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Dettagli retribuzione per posizioni in Dynamics 365 Human Resources.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f6c4bb0e2f4521e8c870f6c4fb645e2ce506138c
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882012"
---
# <a name="payroll-position"></a><span data-ttu-id="42e40-103">Posizione di retribuzione</span><span class="sxs-lookup"><span data-stu-id="42e40-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="42e40-104">Questo argomento fornisce dettagli e una query di esempio per l'entità Dettagli retribuzione per posizioni in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="42e40-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="42e40-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="42e40-105">Properties</span></span>

| <span data-ttu-id="42e40-106">Proprietà</span><span class="sxs-lookup"><span data-stu-id="42e40-106">Property</span></span><br><span data-ttu-id="42e40-107">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="42e40-107">**Physical name**</span></span><br><span data-ttu-id="42e40-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="42e40-108">**_Type_**</span></span> | <span data-ttu-id="42e40-109">Utilizza</span><span class="sxs-lookup"><span data-stu-id="42e40-109">Use</span></span> | <span data-ttu-id="42e40-110">descrizione</span><span class="sxs-lookup"><span data-stu-id="42e40-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="42e40-111">**Ore regolari annuali**</span><span class="sxs-lookup"><span data-stu-id="42e40-111">**Annual regular hours**</span></span><br><span data-ttu-id="42e40-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="42e40-112">annualregularhours</span></span><br><span data-ttu-id="42e40-113">*Decimali*</span><span class="sxs-lookup"><span data-stu-id="42e40-113">*Decimal*</span></span> | <span data-ttu-id="42e40-114">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="42e40-114">Read-only</span></span><br><span data-ttu-id="42e40-115">Richiesto</span><span class="sxs-lookup"><span data-stu-id="42e40-115">Required</span></span> | <span data-ttu-id="42e40-116">Ore regolari annuali definite per la posizione.</span><span class="sxs-lookup"><span data-stu-id="42e40-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="42e40-117">**ID entità dettagli posizione di retribuzione**</span><span class="sxs-lookup"><span data-stu-id="42e40-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="42e40-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="42e40-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="42e40-119">*GUID*</span><span class="sxs-lookup"><span data-stu-id="42e40-119">*Guid*</span></span> | <span data-ttu-id="42e40-120">Richiesto</span><span class="sxs-lookup"><span data-stu-id="42e40-120">Required</span></span><br><span data-ttu-id="42e40-121">Generato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="42e40-121">System generated.</span></span> | <span data-ttu-id="42e40-122">Un valore GUID generato dal sistema per identificare in modo univoco la posizione.</span><span class="sxs-lookup"><span data-stu-id="42e40-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="42e40-123">**Campo principale**</span><span class="sxs-lookup"><span data-stu-id="42e40-123">**Primary field**</span></span><br><span data-ttu-id="42e40-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="42e40-124">mshr_primaryfield</span></span><br><span data-ttu-id="42e40-125">*String*</span><span class="sxs-lookup"><span data-stu-id="42e40-125">*String*</span></span> | <span data-ttu-id="42e40-126">Richiesto</span><span class="sxs-lookup"><span data-stu-id="42e40-126">Required</span></span><br><span data-ttu-id="42e40-127">Generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="42e40-127">System generated</span></span> |  |
| <span data-ttu-id="42e40-128">**Valore ID mansione posizione**</span><span class="sxs-lookup"><span data-stu-id="42e40-128">**Position job ID value**</span></span><br><span data-ttu-id="42e40-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="42e40-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="42e40-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="42e40-130">*GUID*</span></span> | <span data-ttu-id="42e40-131">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="42e40-131">Read-only</span></span><br><span data-ttu-id="42e40-132">Richiesto</span><span class="sxs-lookup"><span data-stu-id="42e40-132">Required</span></span><br><span data-ttu-id="42e40-133">Chiave esterna:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="42e40-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="42e40-134">L'ID della mansione associata alla posizione.</span><span class="sxs-lookup"><span data-stu-id="42e40-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="42e40-135">**Valore ID piano di retribuzione fissa**</span><span class="sxs-lookup"><span data-stu-id="42e40-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="42e40-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="42e40-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="42e40-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="42e40-137">*GUID*</span></span> | <span data-ttu-id="42e40-138">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="42e40-138">Read-only</span></span><br><span data-ttu-id="42e40-139">Richiesto</span><span class="sxs-lookup"><span data-stu-id="42e40-139">Required</span></span><br><span data-ttu-id="42e40-140">Chiave esterna: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span><span class="sxs-lookup"><span data-stu-id="42e40-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="42e40-141">L'ID del piano di retribuzione fissa associato alla posizione.</span><span class="sxs-lookup"><span data-stu-id="42e40-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="42e40-142">**ID ciclo retributivo**</span><span class="sxs-lookup"><span data-stu-id="42e40-142">**Pay cycle ID**</span></span><br><span data-ttu-id="42e40-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="42e40-143">mshr_primaryfield</span></span><br><span data-ttu-id="42e40-144">*String*</span><span class="sxs-lookup"><span data-stu-id="42e40-144">*String*</span></span> | <span data-ttu-id="42e40-145">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="42e40-145">Read-only</span></span><br><span data-ttu-id="42e40-146">Richiesto</span><span class="sxs-lookup"><span data-stu-id="42e40-146">Required</span></span> | <span data-ttu-id="42e40-147">Il ciclo retributivo definito per la posizione.</span><span class="sxs-lookup"><span data-stu-id="42e40-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="42e40-148">**Pagamento in base alla persona giuridica**</span><span class="sxs-lookup"><span data-stu-id="42e40-148">**Paid by legal entity**</span></span><br><span data-ttu-id="42e40-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="42e40-149">paidbylegalentity</span></span><br><span data-ttu-id="42e40-150">*String*</span><span class="sxs-lookup"><span data-stu-id="42e40-150">*String*</span></span> | <span data-ttu-id="42e40-151">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="42e40-151">Read-only</span></span><br><span data-ttu-id="42e40-152">Richiesto</span><span class="sxs-lookup"><span data-stu-id="42e40-152">Required</span></span> | <span data-ttu-id="42e40-153">La persona giuridica definita nella posizione responsabile dell'emissione del pagamento.</span><span class="sxs-lookup"><span data-stu-id="42e40-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="42e40-154">**ID posizione**</span><span class="sxs-lookup"><span data-stu-id="42e40-154">**Position ID**</span></span><br><span data-ttu-id="42e40-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="42e40-155">mshr_positionid</span></span><br><span data-ttu-id="42e40-156">*String*</span><span class="sxs-lookup"><span data-stu-id="42e40-156">*String*</span></span> | <span data-ttu-id="42e40-157">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="42e40-157">Read-only</span></span><br><span data-ttu-id="42e40-158">Richiesto</span><span class="sxs-lookup"><span data-stu-id="42e40-158">Required</span></span> | <span data-ttu-id="42e40-159">L'ID della posizione.</span><span class="sxs-lookup"><span data-stu-id="42e40-159">The ID of the position.</span></span> |
| <span data-ttu-id="42e40-160">**Data di fine validità**</span><span class="sxs-lookup"><span data-stu-id="42e40-160">**Valid to**</span></span><br><span data-ttu-id="42e40-161">validto</span><span class="sxs-lookup"><span data-stu-id="42e40-161">validto</span></span><br><span data-ttu-id="42e40-162">*Offset data/ora*</span><span class="sxs-lookup"><span data-stu-id="42e40-162">*Date Time Offset*</span></span> | <span data-ttu-id="42e40-163">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="42e40-163">Read-only</span></span><br><span data-ttu-id="42e40-164">Richiesto</span><span class="sxs-lookup"><span data-stu-id="42e40-164">Required</span></span> |<span data-ttu-id="42e40-165">La data di inizio validità dei dettagli della posizione.</span><span class="sxs-lookup"><span data-stu-id="42e40-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="42e40-166">**Data di inizio validità**</span><span class="sxs-lookup"><span data-stu-id="42e40-166">**Valid from**</span></span><br><span data-ttu-id="42e40-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="42e40-167">validfrom</span></span><br><span data-ttu-id="42e40-168">*Offset data/ora*</span><span class="sxs-lookup"><span data-stu-id="42e40-168">*Date Time Offset*</span></span> | <span data-ttu-id="42e40-169">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="42e40-169">Read-only</span></span><br><span data-ttu-id="42e40-170">Richiesto</span><span class="sxs-lookup"><span data-stu-id="42e40-170">Required</span></span> |<span data-ttu-id="42e40-171">La data di fine validità dei dettagli della posizione.</span><span class="sxs-lookup"><span data-stu-id="42e40-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="42e40-172">**Query**</span><span class="sxs-lookup"><span data-stu-id="42e40-172">**Query**</span></span>

<span data-ttu-id="42e40-173">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="42e40-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="42e40-174">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="42e40-174">**Response**</span></span>

```json
{
            "mshr_positionid": "000276",
            "mshr_paycycleid": "w",
            "mshr_annualregularhours": 3000,
            "mshr_paidbylegalentity": "USMF",
            "mshr_validfrom": "2021-03-14T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_primaryfield": "000276 | 3/14/2021",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```
