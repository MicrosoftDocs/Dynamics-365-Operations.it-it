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
ms.openlocfilehash: d3a45d802ab6b574338a09e77d432357cb9df507
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465920"
---
# <a name="screening-types"></a><span data-ttu-id="e7e60-103">Tipi di screening</span><span class="sxs-lookup"><span data-stu-id="e7e60-103">Screening types</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e7e60-104">Questo argomento descrive l'entità Tipi di screening per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e7e60-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="e7e60-105">Nome fisico: mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="e7e60-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="e7e60-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7e60-106">Description</span></span>

<span data-ttu-id="e7e60-107">Questa entità descrive i tipi di screening impostati dall'azienda per i processi preliminari all'impiego e di screening dei dipendenti in corso.</span><span class="sxs-lookup"><span data-stu-id="e7e60-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="e7e60-108">Rappresentazione JSON</span><span class="sxs-lookup"><span data-stu-id="e7e60-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="e7e60-109">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e7e60-109">Properties</span></span>

| <span data-ttu-id="e7e60-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e7e60-110">Property</span></span><br><span data-ttu-id="e7e60-111">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="e7e60-111">**Physical name**</span></span><br><span data-ttu-id="e7e60-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="e7e60-112">**_Type_**</span></span> | <span data-ttu-id="e7e60-113">Utilizza</span><span class="sxs-lookup"><span data-stu-id="e7e60-113">Use</span></span> | <span data-ttu-id="e7e60-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7e60-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e7e60-115">**ID entità tipo di screening**</span><span class="sxs-lookup"><span data-stu-id="e7e60-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="e7e60-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="e7e60-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="e7e60-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="e7e60-117">*GUID*</span></span> | <span data-ttu-id="e7e60-118">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e7e60-118">Read-only</span></span><br><span data-ttu-id="e7e60-119">Richiesto</span><span class="sxs-lookup"><span data-stu-id="e7e60-119">Required</span></span><br><span data-ttu-id="e7e60-120">Generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="e7e60-120">System-generated</span></span> | <span data-ttu-id="e7e60-121">Identificatore primario univoco per il record del tipo di screening.</span><span class="sxs-lookup"><span data-stu-id="e7e60-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="e7e60-122">**ID tipo di screening**</span><span class="sxs-lookup"><span data-stu-id="e7e60-122">**Screening Type ID**</span></span><br><span data-ttu-id="e7e60-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="e7e60-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="e7e60-124">*String*</span><span class="sxs-lookup"><span data-stu-id="e7e60-124">*String*</span></span> | <span data-ttu-id="e7e60-125">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="e7e60-125">Read/write</span></span><br><span data-ttu-id="e7e60-126">Richiesto</span><span class="sxs-lookup"><span data-stu-id="e7e60-126">Required</span></span> | <span data-ttu-id="e7e60-127">Identificatore univoco definito dall'utente per il tipo di screening.</span><span class="sxs-lookup"><span data-stu-id="e7e60-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="e7e60-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e7e60-128">**Description**</span></span><br><span data-ttu-id="e7e60-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="e7e60-129">mshr_description</span></span><br><span data-ttu-id="e7e60-130">*String*</span><span class="sxs-lookup"><span data-stu-id="e7e60-130">*String*</span></span> | <span data-ttu-id="e7e60-131">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="e7e60-131">Read/write</span></span><br><span data-ttu-id="e7e60-132">Richiesto</span><span class="sxs-lookup"><span data-stu-id="e7e60-132">Required</span></span> | <span data-ttu-id="e7e60-133">Descrizione del tipo di screening.</span><span class="sxs-lookup"><span data-stu-id="e7e60-133">The description of the screening type.</span></span> |
| <span data-ttu-id="e7e60-134">**Unità frequenza**</span><span class="sxs-lookup"><span data-stu-id="e7e60-134">**Frequency Unit**</span></span><br><span data-ttu-id="e7e60-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="e7e60-135">mshr_frequencyunit</span></span><br><span data-ttu-id="e7e60-136">*set di opzioni mshr_hcmfrequencyunit*</span><span class="sxs-lookup"><span data-stu-id="e7e60-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="e7e60-137">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="e7e60-137">Read/write</span></span><br><span data-ttu-id="e7e60-138">Richiesto</span><span class="sxs-lookup"><span data-stu-id="e7e60-138">Required</span></span> | <span data-ttu-id="e7e60-139">Descrive la frequenza con cui lo screening deve essere completato per la persona assegnata.</span><span class="sxs-lookup"><span data-stu-id="e7e60-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="e7e60-140">**Genera da**</span><span class="sxs-lookup"><span data-stu-id="e7e60-140">**Generate From**</span></span><br><span data-ttu-id="e7e60-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="e7e60-141">mshr_generatefrom</span></span><br><span data-ttu-id="e7e60-142">*set di opzioni mshr_hcmfrequencygeneratefrom*</span><span class="sxs-lookup"><span data-stu-id="e7e60-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="e7e60-143">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="e7e60-143">Read-write</span></span><br><span data-ttu-id="e7e60-144">Richiesto</span><span class="sxs-lookup"><span data-stu-id="e7e60-144">Required</span></span> | <span data-ttu-id="e7e60-145">Se il valore Frequenza è un valore diverso da "Solo una volta", il valore GenerateFrom determina la data a partire dalla quale calcolare il successivo evento di screening.</span><span class="sxs-lookup"><span data-stu-id="e7e60-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="e7e60-146">**Intervallo di frequenza**</span><span class="sxs-lookup"><span data-stu-id="e7e60-146">**Frequency Interval**</span></span><br><span data-ttu-id="e7e60-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="e7e60-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="e7e60-148">*Integer*</span><span class="sxs-lookup"><span data-stu-id="e7e60-148">*Integer*</span></span> | <span data-ttu-id="e7e60-149">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="e7e60-149">Read-write</span></span><br><span data-ttu-id="e7e60-150">Richiesto</span><span class="sxs-lookup"><span data-stu-id="e7e60-150">Required</span></span> | <span data-ttu-id="e7e60-151">Se il valore Frequenza è un valore diverso da "Solo una volta", è necessario definire un intervallo per le unità di tempo tra ogni evento di screening.</span><span class="sxs-lookup"><span data-stu-id="e7e60-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e7e60-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7e60-152">See also</span></span>

[<span data-ttu-id="e7e60-153">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="e7e60-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="e7e60-154">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="e7e60-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]