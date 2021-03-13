---
title: Tipi di screening
description: Questo argomento descrive l'entità Tipi di screening per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 227c15acb44e020ea9858961e45c11ad07e18a74
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126172"
---
# <a name="screening-types"></a><span data-ttu-id="1b9e5-103">Tipi di screening</span><span class="sxs-lookup"><span data-stu-id="1b9e5-103">Screening types</span></span>

<span data-ttu-id="1b9e5-104">Questo argomento descrive l'entità Tipi di screening per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1b9e5-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="1b9e5-105">Nome fisico: mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="1b9e5-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="1b9e5-106">descrizione</span><span class="sxs-lookup"><span data-stu-id="1b9e5-106">Description</span></span>

<span data-ttu-id="1b9e5-107">Questa entità descrive i tipi di screening impostati dall'azienda per i processi preliminari all'impiego e di screening dei dipendenti in corso.</span><span class="sxs-lookup"><span data-stu-id="1b9e5-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="1b9e5-108">Rappresentazione JSON</span><span class="sxs-lookup"><span data-stu-id="1b9e5-108">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="1b9e5-109">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1b9e5-109">Properties</span></span>

| <span data-ttu-id="1b9e5-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1b9e5-110">Property</span></span><br><span data-ttu-id="1b9e5-111">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="1b9e5-111">**Physical name**</span></span><br><span data-ttu-id="1b9e5-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="1b9e5-112">**_Type_**</span></span> | <span data-ttu-id="1b9e5-113">Utilizza</span><span class="sxs-lookup"><span data-stu-id="1b9e5-113">Use</span></span> | <span data-ttu-id="1b9e5-114">descrizione</span><span class="sxs-lookup"><span data-stu-id="1b9e5-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1b9e5-115">**ID entità tipo di screening**</span><span class="sxs-lookup"><span data-stu-id="1b9e5-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="1b9e5-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="1b9e5-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="1b9e5-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1b9e5-117">*GUID*</span></span> | <span data-ttu-id="1b9e5-118">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1b9e5-118">Read-only</span></span><br><span data-ttu-id="1b9e5-119">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1b9e5-119">Required</span></span><br><span data-ttu-id="1b9e5-120">Generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="1b9e5-120">System-generated</span></span> | <span data-ttu-id="1b9e5-121">Identificatore primario univoco per il record del tipo di screening.</span><span class="sxs-lookup"><span data-stu-id="1b9e5-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="1b9e5-122">**ID tipo di screening**</span><span class="sxs-lookup"><span data-stu-id="1b9e5-122">**Screening Type ID**</span></span><br><span data-ttu-id="1b9e5-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="1b9e5-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="1b9e5-124">*String*</span><span class="sxs-lookup"><span data-stu-id="1b9e5-124">*String*</span></span> | <span data-ttu-id="1b9e5-125">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="1b9e5-125">Read/write</span></span><br><span data-ttu-id="1b9e5-126">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1b9e5-126">Required</span></span> | <span data-ttu-id="1b9e5-127">Identificatore univoco definito dall'utente per il tipo di screening.</span><span class="sxs-lookup"><span data-stu-id="1b9e5-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="1b9e5-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1b9e5-128">**Description**</span></span><br><span data-ttu-id="1b9e5-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="1b9e5-129">mshr_description</span></span><br><span data-ttu-id="1b9e5-130">*String*</span><span class="sxs-lookup"><span data-stu-id="1b9e5-130">*String*</span></span> | <span data-ttu-id="1b9e5-131">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="1b9e5-131">Read/write</span></span><br><span data-ttu-id="1b9e5-132">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1b9e5-132">Required</span></span> | <span data-ttu-id="1b9e5-133">Descrizione del tipo di screening.</span><span class="sxs-lookup"><span data-stu-id="1b9e5-133">The description of the screening type.</span></span> |
| <span data-ttu-id="1b9e5-134">**Unità frequenza**</span><span class="sxs-lookup"><span data-stu-id="1b9e5-134">**Frequency Unit**</span></span><br><span data-ttu-id="1b9e5-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="1b9e5-135">mshr_frequencyunit</span></span><br><span data-ttu-id="1b9e5-136">*set di opzioni mshr_hcmfrequencyunit*</span><span class="sxs-lookup"><span data-stu-id="1b9e5-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="1b9e5-137">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="1b9e5-137">Read/write</span></span><br><span data-ttu-id="1b9e5-138">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1b9e5-138">Required</span></span> | <span data-ttu-id="1b9e5-139">Descrive la frequenza con cui lo screening deve essere completato per la persona assegnata.</span><span class="sxs-lookup"><span data-stu-id="1b9e5-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="1b9e5-140">**Genera da**</span><span class="sxs-lookup"><span data-stu-id="1b9e5-140">**Generate From**</span></span><br><span data-ttu-id="1b9e5-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="1b9e5-141">mshr_generatefrom</span></span><br><span data-ttu-id="1b9e5-142">*set di opzioni mshr_hcmfrequencygeneratefrom*</span><span class="sxs-lookup"><span data-stu-id="1b9e5-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="1b9e5-143">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="1b9e5-143">Read-write</span></span><br><span data-ttu-id="1b9e5-144">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1b9e5-144">Required</span></span> | <span data-ttu-id="1b9e5-145">Se il valore Frequenza è un valore diverso da "Solo una volta", il valore GenerateFrom determina la data a partire dalla quale calcolare il successivo evento di screening.</span><span class="sxs-lookup"><span data-stu-id="1b9e5-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="1b9e5-146">**Intervallo di frequenza**</span><span class="sxs-lookup"><span data-stu-id="1b9e5-146">**Frequency Interval**</span></span><br><span data-ttu-id="1b9e5-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="1b9e5-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="1b9e5-148">*Integer*</span><span class="sxs-lookup"><span data-stu-id="1b9e5-148">*Integer*</span></span> | <span data-ttu-id="1b9e5-149">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="1b9e5-149">Read-write</span></span><br><span data-ttu-id="1b9e5-150">Richiesto</span><span class="sxs-lookup"><span data-stu-id="1b9e5-150">Required</span></span> | <span data-ttu-id="1b9e5-151">Se il valore Frequenza è un valore diverso da "Solo una volta", è necessario definire un intervallo per le unità di tempo tra ogni evento di screening.</span><span class="sxs-lookup"><span data-stu-id="1b9e5-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1b9e5-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b9e5-152">See also</span></span>

[<span data-ttu-id="1b9e5-153">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="1b9e5-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="1b9e5-154">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="1b9e5-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
