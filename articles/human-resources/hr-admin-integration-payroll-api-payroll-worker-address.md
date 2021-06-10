---
title: Indirizzo lavoratore retribuzioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Indirizzo lavoratore retribuzioni in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 3407128b0172f0e253d51bcfa23a894f981e21e2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052291"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="1f8d8-103">Indirizzo lavoratore retribuzioni</span><span class="sxs-lookup"><span data-stu-id="1f8d8-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1f8d8-104">Questo argomento fornisce dettagli e una query di esempio per l'entità Indirizzo lavoratore retribuzioni in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="1f8d8-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1f8d8-105">Properties</span></span>

| <span data-ttu-id="1f8d8-106">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1f8d8-106">Property</span></span><br><span data-ttu-id="1f8d8-107">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-107">**Physical name**</span></span><br><span data-ttu-id="1f8d8-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-108">**_Type_**</span></span> | <span data-ttu-id="1f8d8-109">Utilizza</span><span class="sxs-lookup"><span data-stu-id="1f8d8-109">Use</span></span> | <span data-ttu-id="1f8d8-110">descrizione</span><span class="sxs-lookup"><span data-stu-id="1f8d8-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1f8d8-111">**Città**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-111">**City**</span></span><br><span data-ttu-id="1f8d8-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="1f8d8-112">mshr_city</span></span><br><span data-ttu-id="1f8d8-113">*String*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-113">*String*</span></span> | <span data-ttu-id="1f8d8-114">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-114">Read-only</span></span><br><span data-ttu-id="1f8d8-115">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-115">Required</span></span> | <span data-ttu-id="1f8d8-116">La città definita per l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="1f8d8-117">**Numero dipendente**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-117">**Personnel number**</span></span><br><span data-ttu-id="1f8d8-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="1f8d8-118">mshr_personnelnumber</span></span><br><span data-ttu-id="1f8d8-119">*String*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-119">*String*</span></span> | <span data-ttu-id="1f8d8-120">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-120">Read-only</span></span><br><span data-ttu-id="1f8d8-121">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-121">Required</span></span> | <span data-ttu-id="1f8d8-122">Il numero personale univoco del dipendente.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="1f8d8-123">**Paese**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-123">**Country region**</span></span><br><span data-ttu-id="1f8d8-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="1f8d8-124">mshr_countryregionid</span></span><br><span data-ttu-id="1f8d8-125">*String*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-125">*String*</span></span> | <span data-ttu-id="1f8d8-126">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-126">Read-only</span></span><br><span data-ttu-id="1f8d8-127">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-127">Required</span></span> | <span data-ttu-id="1f8d8-128">Il paese definito per l'indirizzo</span><span class="sxs-lookup"><span data-stu-id="1f8d8-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="1f8d8-129">**Data di inizio validità**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-129">**Valid from**</span></span><br><span data-ttu-id="1f8d8-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="1f8d8-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="1f8d8-131">*Offset data/ora*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-131">*Date Time Offset*</span></span> | <span data-ttu-id="1f8d8-132">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-132">Read-only</span></span> <br><span data-ttu-id="1f8d8-133">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-133">Required</span></span> | <span data-ttu-id="1f8d8-134">La data di inizio validità dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="1f8d8-135">**Indirizzo lavoro**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-135">**Worked in address**</span></span><br><span data-ttu-id="1f8d8-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="1f8d8-137">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-137">Read-only</span></span><br><span data-ttu-id="1f8d8-138">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-138">Required</span></span> | <span data-ttu-id="1f8d8-139">Indica se l'indirizzo è dove lavora il dipendente.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="1f8d8-140">**Regione**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-140">**County**</span></span><br><span data-ttu-id="1f8d8-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="1f8d8-141">mshr_county</span></span><br><span data-ttu-id="1f8d8-142">*String*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-142">*String*</span></span> | <span data-ttu-id="1f8d8-143">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-143">Read-only</span></span><br><span data-ttu-id="1f8d8-144">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-144">Required</span></span> | <span data-ttu-id="1f8d8-145">La regione definita per l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="1f8d8-146">**ID Indirizzo lavoratore retribuzioni**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="1f8d8-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="1f8d8-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="1f8d8-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-148">*GUID*</span></span> | <span data-ttu-id="1f8d8-149">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-149">Required</span></span><br><span data-ttu-id="1f8d8-150">Generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="1f8d8-150">System generated</span></span> | <span data-ttu-id="1f8d8-151">Un valore GUID generato dal sistema per identificare in modo univoco l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="1f8d8-152">**Campo principale**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-152">**Primary field**</span></span><br><span data-ttu-id="1f8d8-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="1f8d8-153">mshr_primaryfield</span></span><br><span data-ttu-id="1f8d8-154">*String*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-154">*String*</span></span> | <span data-ttu-id="1f8d8-155">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-155">Read-only</span></span><br><span data-ttu-id="1f8d8-156">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-156">Required</span></span> |  |
| <span data-ttu-id="1f8d8-157">**Via**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-157">**Street**</span></span><br><span data-ttu-id="1f8d8-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="1f8d8-158">mshr_street</span></span><br><span data-ttu-id="1f8d8-159">*String*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-159">*String*</span></span> | <span data-ttu-id="1f8d8-160">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-160">Read-only</span></span><br><span data-ttu-id="1f8d8-161">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-161">Required</span></span> | <span data-ttu-id="1f8d8-162">La via definita per l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-162">The street defined for the address.</span></span> |
| <span data-ttu-id="1f8d8-163">**Data di fine validità**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-163">**Valid to**</span></span><br><span data-ttu-id="1f8d8-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="1f8d8-165">*Offset data/ora*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-165">*Date Time Offset*</span></span> | <span data-ttu-id="1f8d8-166">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-166">Read-only</span></span> <br><span data-ttu-id="1f8d8-167">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-167">Required</span></span> | <span data-ttu-id="1f8d8-168">La data di fine validità dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="1f8d8-169">**ID ubicazione**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-169">**Location ID**</span></span><br><span data-ttu-id="1f8d8-170">mshr_locationidbr>*String*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="1f8d8-171">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-171">Read-only</span></span> <br><span data-ttu-id="1f8d8-172">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-172">Required</span></span> | <span data-ttu-id="1f8d8-173">L'ID dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-173">The ID for the address.</span></span>  |
| <span data-ttu-id="1f8d8-174">**CAP**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-174">**Postal code**</span></span><br><span data-ttu-id="1f8d8-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="1f8d8-175">mshr_zipcode</span></span><br><span data-ttu-id="1f8d8-176">*String*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-176">*String*</span></span> | <span data-ttu-id="1f8d8-177">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-177">Read-only</span></span> <br><span data-ttu-id="1f8d8-178">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-178">Required</span></span> |<span data-ttu-id="1f8d8-179">Il numero di identificazione definito per il dipendente.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="1f8d8-180">**Indirizzo domicilio**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-180">**Lived in address**</span></span><br><span data-ttu-id="1f8d8-181">mshr_islivedinaddressbr>*String*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="1f8d8-182">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-182">Read-only</span></span><br><span data-ttu-id="1f8d8-183">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-183">Required</span></span> | <span data-ttu-id="1f8d8-184">Indica se l'indirizzo è dove vive il dipendente.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="1f8d8-185">**Stato/regione**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-185">**State**</span></span><br><span data-ttu-id="1f8d8-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="1f8d8-186">mshr_state</span></span><br><span data-ttu-id="1f8d8-187">*String*</span><span class="sxs-lookup"><span data-stu-id="1f8d8-187">*String*</span></span> | <span data-ttu-id="1f8d8-188">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1f8d8-188">Read-only</span></span><br><span data-ttu-id="1f8d8-189">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1f8d8-189">Required</span></span> | <span data-ttu-id="1f8d8-190">Lo stato definito per l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1f8d8-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="1f8d8-191">Query di esempio</span><span class="sxs-lookup"><span data-stu-id="1f8d8-191">Example query</span></span>

<span data-ttu-id="1f8d8-192">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="1f8d8-193">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="1f8d8-193">**Response**</span></span>

```json
{
            "mshr_personnelnumber": "000041",
            "mshr_locationid": "000000538",
            "mshr_islivedinaddress": 200000001,
            "mshr_isworkedinaddress": 200000000,
            "mshr_countryregionid": "USA",
            "mshr_zipcode": "99025",
            "mshr_street": "6543 Cypress Ave",
            "mshr_city": "Tacoma",
            "mshr_state": "WA",
            "mshr_county": "KING",
            "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
            "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
            "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
            "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```
