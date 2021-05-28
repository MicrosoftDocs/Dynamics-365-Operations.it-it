---
title: Dettagli retribuzione per posizioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Dettagli retribuzione per posizioni in Dynamics 365 Human Resources.
author: jcart
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
ms.openlocfilehash: 7b23ac5d11b18c77109be21afe1570755dccba20
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019324"
---
# <a name="payroll-position"></a><span data-ttu-id="760dd-103">Posizione di retribuzione</span><span class="sxs-lookup"><span data-stu-id="760dd-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="760dd-104">Questo argomento fornisce dettagli e una query di esempio per l'entità Dettagli retribuzione per posizioni in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="760dd-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="760dd-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="760dd-105">Properties</span></span>

| <span data-ttu-id="760dd-106">Proprietà</span><span class="sxs-lookup"><span data-stu-id="760dd-106">Property</span></span><br><span data-ttu-id="760dd-107">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="760dd-107">**Physical name**</span></span><br><span data-ttu-id="760dd-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="760dd-108">**_Type_**</span></span> | <span data-ttu-id="760dd-109">Utilizza</span><span class="sxs-lookup"><span data-stu-id="760dd-109">Use</span></span> | <span data-ttu-id="760dd-110">descrizione</span><span class="sxs-lookup"><span data-stu-id="760dd-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="760dd-111">**Ore regolari annuali**</span><span class="sxs-lookup"><span data-stu-id="760dd-111">**Annual regular hours**</span></span><br><span data-ttu-id="760dd-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="760dd-112">annualregularhours</span></span><br><span data-ttu-id="760dd-113">*Decimali*</span><span class="sxs-lookup"><span data-stu-id="760dd-113">*Decimal*</span></span> | <span data-ttu-id="760dd-114">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="760dd-114">Read-only</span></span><br><span data-ttu-id="760dd-115">Richiesto</span><span class="sxs-lookup"><span data-stu-id="760dd-115">Required</span></span> | <span data-ttu-id="760dd-116">Ore regolari annuali definite per la posizione.</span><span class="sxs-lookup"><span data-stu-id="760dd-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="760dd-117">**ID entità dettagli posizione di retribuzione**</span><span class="sxs-lookup"><span data-stu-id="760dd-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="760dd-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="760dd-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="760dd-119">*GUID*</span><span class="sxs-lookup"><span data-stu-id="760dd-119">*Guid*</span></span> | <span data-ttu-id="760dd-120">Richiesto</span><span class="sxs-lookup"><span data-stu-id="760dd-120">Required</span></span><br><span data-ttu-id="760dd-121">Generato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="760dd-121">System generated.</span></span> | <span data-ttu-id="760dd-122">Un valore GUID generato dal sistema per identificare in modo univoco la posizione.</span><span class="sxs-lookup"><span data-stu-id="760dd-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="760dd-123">**Campo principale**</span><span class="sxs-lookup"><span data-stu-id="760dd-123">**Primary field**</span></span><br><span data-ttu-id="760dd-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="760dd-124">mshr_primaryfield</span></span><br><span data-ttu-id="760dd-125">*String*</span><span class="sxs-lookup"><span data-stu-id="760dd-125">*String*</span></span> | <span data-ttu-id="760dd-126">Richiesto</span><span class="sxs-lookup"><span data-stu-id="760dd-126">Required</span></span><br><span data-ttu-id="760dd-127">Generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="760dd-127">System generated</span></span> |  |
| <span data-ttu-id="760dd-128">**Valore ID mansione posizione**</span><span class="sxs-lookup"><span data-stu-id="760dd-128">**Position job ID value**</span></span><br><span data-ttu-id="760dd-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="760dd-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="760dd-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="760dd-130">*GUID*</span></span> | <span data-ttu-id="760dd-131">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="760dd-131">Read-only</span></span><br><span data-ttu-id="760dd-132">Richiesto</span><span class="sxs-lookup"><span data-stu-id="760dd-132">Required</span></span><br><span data-ttu-id="760dd-133">Chiave esterna:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="760dd-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="760dd-134">L'ID della mansione associata alla posizione.</span><span class="sxs-lookup"><span data-stu-id="760dd-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="760dd-135">**Valore ID piano di retribuzione fissa**</span><span class="sxs-lookup"><span data-stu-id="760dd-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="760dd-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="760dd-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="760dd-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="760dd-137">*GUID*</span></span> | <span data-ttu-id="760dd-138">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="760dd-138">Read-only</span></span><br><span data-ttu-id="760dd-139">Richiesto</span><span class="sxs-lookup"><span data-stu-id="760dd-139">Required</span></span><br><span data-ttu-id="760dd-140">Chiave esterna: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span><span class="sxs-lookup"><span data-stu-id="760dd-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="760dd-141">L'ID del piano di retribuzione fissa associato alla posizione.</span><span class="sxs-lookup"><span data-stu-id="760dd-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="760dd-142">**ID ciclo retributivo**</span><span class="sxs-lookup"><span data-stu-id="760dd-142">**Pay cycle ID**</span></span><br><span data-ttu-id="760dd-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="760dd-143">mshr_primaryfield</span></span><br><span data-ttu-id="760dd-144">*String*</span><span class="sxs-lookup"><span data-stu-id="760dd-144">*String*</span></span> | <span data-ttu-id="760dd-145">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="760dd-145">Read-only</span></span><br><span data-ttu-id="760dd-146">Richiesto</span><span class="sxs-lookup"><span data-stu-id="760dd-146">Required</span></span> | <span data-ttu-id="760dd-147">Il ciclo retributivo definito per la posizione.</span><span class="sxs-lookup"><span data-stu-id="760dd-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="760dd-148">**Pagamento in base alla persona giuridica**</span><span class="sxs-lookup"><span data-stu-id="760dd-148">**Paid by legal entity**</span></span><br><span data-ttu-id="760dd-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="760dd-149">paidbylegalentity</span></span><br><span data-ttu-id="760dd-150">*String*</span><span class="sxs-lookup"><span data-stu-id="760dd-150">*String*</span></span> | <span data-ttu-id="760dd-151">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="760dd-151">Read-only</span></span><br><span data-ttu-id="760dd-152">Richiesto</span><span class="sxs-lookup"><span data-stu-id="760dd-152">Required</span></span> | <span data-ttu-id="760dd-153">La persona giuridica definita nella posizione responsabile dell'emissione del pagamento.</span><span class="sxs-lookup"><span data-stu-id="760dd-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="760dd-154">**ID posizione**</span><span class="sxs-lookup"><span data-stu-id="760dd-154">**Position ID**</span></span><br><span data-ttu-id="760dd-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="760dd-155">mshr_positionid</span></span><br><span data-ttu-id="760dd-156">*String*</span><span class="sxs-lookup"><span data-stu-id="760dd-156">*String*</span></span> | <span data-ttu-id="760dd-157">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="760dd-157">Read-only</span></span><br><span data-ttu-id="760dd-158">Richiesto</span><span class="sxs-lookup"><span data-stu-id="760dd-158">Required</span></span> | <span data-ttu-id="760dd-159">L'ID della posizione.</span><span class="sxs-lookup"><span data-stu-id="760dd-159">The ID of the position.</span></span> |
| <span data-ttu-id="760dd-160">**Data di fine validità**</span><span class="sxs-lookup"><span data-stu-id="760dd-160">**Valid to**</span></span><br><span data-ttu-id="760dd-161">validto</span><span class="sxs-lookup"><span data-stu-id="760dd-161">validto</span></span><br><span data-ttu-id="760dd-162">*Offset data/ora*</span><span class="sxs-lookup"><span data-stu-id="760dd-162">*Date Time Offset*</span></span> | <span data-ttu-id="760dd-163">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="760dd-163">Read-only</span></span><br><span data-ttu-id="760dd-164">Richiesto</span><span class="sxs-lookup"><span data-stu-id="760dd-164">Required</span></span> |<span data-ttu-id="760dd-165">La data di inizio validità dei dettagli della posizione.</span><span class="sxs-lookup"><span data-stu-id="760dd-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="760dd-166">**Data di inizio validità**</span><span class="sxs-lookup"><span data-stu-id="760dd-166">**Valid from**</span></span><br><span data-ttu-id="760dd-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="760dd-167">validfrom</span></span><br><span data-ttu-id="760dd-168">*Offset data/ora*</span><span class="sxs-lookup"><span data-stu-id="760dd-168">*Date Time Offset*</span></span> | <span data-ttu-id="760dd-169">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="760dd-169">Read-only</span></span><br><span data-ttu-id="760dd-170">Richiesto</span><span class="sxs-lookup"><span data-stu-id="760dd-170">Required</span></span> |<span data-ttu-id="760dd-171">La data di fine validità dei dettagli della posizione.</span><span class="sxs-lookup"><span data-stu-id="760dd-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="760dd-172">**Query**</span><span class="sxs-lookup"><span data-stu-id="760dd-172">**Query**</span></span>

<span data-ttu-id="760dd-173">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="760dd-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="760dd-174">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="760dd-174">**Response**</span></span>

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
