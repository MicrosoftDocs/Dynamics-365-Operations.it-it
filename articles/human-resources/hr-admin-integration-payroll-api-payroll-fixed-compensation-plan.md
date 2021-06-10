---
title: Piano di retribuzione fissa retribuzioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Piano di retribuzione fissa retribuzioni in Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 227082358c59abddd63f4faa4536a8df270a4d80
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059090"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="8a54c-103">Piano di retribuzione fissa retribuzioni</span><span class="sxs-lookup"><span data-stu-id="8a54c-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8a54c-104">Questo argomento fornisce dettagli e una query di esempio per l'entità Piano di retribuzione fissa retribuzioni in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8a54c-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="8a54c-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8a54c-105">Properties</span></span>

| <span data-ttu-id="8a54c-106">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8a54c-106">Property</span></span><br><span data-ttu-id="8a54c-107">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="8a54c-107">**Physical name**</span></span><br><span data-ttu-id="8a54c-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="8a54c-108">**_Type_**</span></span> | <span data-ttu-id="8a54c-109">Utilizza</span><span class="sxs-lookup"><span data-stu-id="8a54c-109">Use</span></span> | <span data-ttu-id="8a54c-110">descrizione</span><span class="sxs-lookup"><span data-stu-id="8a54c-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="8a54c-111">**ID dipendente**</span><span class="sxs-lookup"><span data-stu-id="8a54c-111">**Employee ID**</span></span><br><span data-ttu-id="8a54c-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="8a54c-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="8a54c-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="8a54c-113">*GUID*</span></span> | <span data-ttu-id="8a54c-114">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a54c-114">Read-only</span></span><br><span data-ttu-id="8a54c-115">Richiesto</span><span class="sxs-lookup"><span data-stu-id="8a54c-115">Required</span></span><br><span data-ttu-id="8a54c-116">Chiave esterna: mshr_Employee_id of mshr_payrollemployeeentity entity</span><span class="sxs-lookup"><span data-stu-id="8a54c-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="8a54c-117">ID dipendente</span><span class="sxs-lookup"><span data-stu-id="8a54c-117">Employee ID</span></span> |
| <span data-ttu-id="8a54c-118">**Retribuzione**</span><span class="sxs-lookup"><span data-stu-id="8a54c-118">**Pay rate**</span></span><br><span data-ttu-id="8a54c-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="8a54c-119">mshr_payrate</span></span><br><span data-ttu-id="8a54c-120">*Decimali*</span><span class="sxs-lookup"><span data-stu-id="8a54c-120">*Decimal*</span></span> | <span data-ttu-id="8a54c-121">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a54c-121">Read-only</span></span><br><span data-ttu-id="8a54c-122">Richiesto</span><span class="sxs-lookup"><span data-stu-id="8a54c-122">Required</span></span> | <span data-ttu-id="8a54c-123">La tariffa retributiva definita nel piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="8a54c-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="8a54c-124">**ID piano**</span><span class="sxs-lookup"><span data-stu-id="8a54c-124">**Plan ID**</span></span><br><span data-ttu-id="8a54c-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="8a54c-125">mshr_planid</span></span><br><span data-ttu-id="8a54c-126">*String*</span><span class="sxs-lookup"><span data-stu-id="8a54c-126">*String*</span></span> | <span data-ttu-id="8a54c-127">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a54c-127">Read-only</span></span><br><span data-ttu-id="8a54c-128">Richiesto</span><span class="sxs-lookup"><span data-stu-id="8a54c-128">Required</span></span> |<span data-ttu-id="8a54c-129">Specifica il piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="8a54c-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="8a54c-130">**Data di inizio validità**</span><span class="sxs-lookup"><span data-stu-id="8a54c-130">**Valid from**</span></span><br><span data-ttu-id="8a54c-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="8a54c-131">mshr_validfrom</span></span><br><span data-ttu-id="8a54c-132">*Offset data/ora*</span><span class="sxs-lookup"><span data-stu-id="8a54c-132">*Date Time Offset*</span></span> |  <span data-ttu-id="8a54c-133">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a54c-133">Read-only</span></span><br><span data-ttu-id="8a54c-134">Richiesto</span><span class="sxs-lookup"><span data-stu-id="8a54c-134">Required</span></span> |<span data-ttu-id="8a54c-135">La data di inizio validità della retribuzione fissa del dipendente.</span><span class="sxs-lookup"><span data-stu-id="8a54c-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="8a54c-136">**Entità piano di retribuzione fissa retribuzioni**</span><span class="sxs-lookup"><span data-stu-id="8a54c-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="8a54c-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="8a54c-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="8a54c-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="8a54c-138">*GUID*</span></span> | <span data-ttu-id="8a54c-139">Richiesto</span><span class="sxs-lookup"><span data-stu-id="8a54c-139">Required</span></span><br><span data-ttu-id="8a54c-140">Generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="8a54c-140">Sytem generated</span></span> | <span data-ttu-id="8a54c-141">Un valore GUID generato dal sistema per identificare in modo univoco il piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="8a54c-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="8a54c-142">**Frequenza retribuzione**</span><span class="sxs-lookup"><span data-stu-id="8a54c-142">**Pay frequency**</span></span><br><span data-ttu-id="8a54c-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="8a54c-143">mshr_payfrequency</span></span><br><span data-ttu-id="8a54c-144">*String*</span><span class="sxs-lookup"><span data-stu-id="8a54c-144">*String*</span></span> | <span data-ttu-id="8a54c-145">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a54c-145">Read-only</span></span><br><span data-ttu-id="8a54c-146">Richiesto</span><span class="sxs-lookup"><span data-stu-id="8a54c-146">Required</span></span> |<span data-ttu-id="8a54c-147">La frequenza alla quale verrà retribuito il dipendente.</span><span class="sxs-lookup"><span data-stu-id="8a54c-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="8a54c-148">**Data di fine validità**</span><span class="sxs-lookup"><span data-stu-id="8a54c-148">**Valid to**</span></span><br><span data-ttu-id="8a54c-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="8a54c-149">mshr_validto</span></span><br><span data-ttu-id="8a54c-150">*Offset data/ora*</span><span class="sxs-lookup"><span data-stu-id="8a54c-150">*Date Time Offset*</span></span> | <span data-ttu-id="8a54c-151">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a54c-151">Read-only</span></span> <br><span data-ttu-id="8a54c-152">Richiesto</span><span class="sxs-lookup"><span data-stu-id="8a54c-152">Required</span></span> | <span data-ttu-id="8a54c-153">La data di fine validità della retribuzione fissa del dipendente.</span><span class="sxs-lookup"><span data-stu-id="8a54c-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="8a54c-154">**ID posizione**</span><span class="sxs-lookup"><span data-stu-id="8a54c-154">**Position ID**</span></span><br><span data-ttu-id="8a54c-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="8a54c-155">mshr_positionid</span></span><br><span data-ttu-id="8a54c-156">*String*</span><span class="sxs-lookup"><span data-stu-id="8a54c-156">*String*</span></span> | <span data-ttu-id="8a54c-157">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a54c-157">Read-only</span></span> <br><span data-ttu-id="8a54c-158">Richiesto</span><span class="sxs-lookup"><span data-stu-id="8a54c-158">Required</span></span> | <span data-ttu-id="8a54c-159">ID posizione associato al dipendente e l'iscrizione al piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="8a54c-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="8a54c-160">**Valuta**</span><span class="sxs-lookup"><span data-stu-id="8a54c-160">**Currency**</span></span><br><span data-ttu-id="8a54c-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="8a54c-161">mshr_currency</span></span><br><span data-ttu-id="8a54c-162">*String*</span><span class="sxs-lookup"><span data-stu-id="8a54c-162">*String*</span></span> | <span data-ttu-id="8a54c-163">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a54c-163">Read-only</span></span> <br><span data-ttu-id="8a54c-164">Richiesto</span><span class="sxs-lookup"><span data-stu-id="8a54c-164">Required</span></span> |<span data-ttu-id="8a54c-165">La valuta definita per il piano di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="8a54c-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="8a54c-166">**Numero dipendente**</span><span class="sxs-lookup"><span data-stu-id="8a54c-166">**Personnel number**</span></span><br><span data-ttu-id="8a54c-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="8a54c-167">mshr_personnelnumber</span></span><br><span data-ttu-id="8a54c-168">*String*</span><span class="sxs-lookup"><span data-stu-id="8a54c-168">*String*</span></span> | <span data-ttu-id="8a54c-169">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="8a54c-169">Read-only</span></span><br><span data-ttu-id="8a54c-170">Richiesto</span><span class="sxs-lookup"><span data-stu-id="8a54c-170">Required</span></span> |<span data-ttu-id="8a54c-171">Il numero personale univoco del dipendente.</span><span class="sxs-lookup"><span data-stu-id="8a54c-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="8a54c-172">**Query**</span><span class="sxs-lookup"><span data-stu-id="8a54c-172">**Query**</span></span>

<span data-ttu-id="8a54c-173">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="8a54c-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="8a54c-174">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="8a54c-174">**Response**</span></span>

```json
{
            "mshr_planid": "GradeC",
            "mshr_personnelnumber": "000041",
            "mshr_payrate": 75200,
            "mshr_positionid": "000276",
            "mshr_validfrom": "2011-04-05T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_payfrequency": "Annual",
            "mshr_currency": "USD",
            "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
            "_mshr_fk_payroll_id_value": null
}
```
