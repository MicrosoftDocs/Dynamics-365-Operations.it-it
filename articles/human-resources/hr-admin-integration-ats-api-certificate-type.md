---
title: Tipo di certificato
description: Questo argomento descrive l'entità Tipo di certificato per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 962bccb3aaab16322d072417660ec3aac821183b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467483"
---
# <a name="certificate-type"></a><span data-ttu-id="a0d32-103">Tipo di certificato</span><span class="sxs-lookup"><span data-stu-id="a0d32-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a0d32-104">Questo argomento descrive l'entità Tipo di certificato per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a0d32-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="a0d32-105">Nome fisico: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="a0d32-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="a0d32-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0d32-106">Description</span></span>

<span data-ttu-id="a0d32-107">Questa entità definisce l'elenco dei tipi di certificati professionali impostati in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a0d32-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="a0d32-108">L'entità non è specifica di una persona giuridica (società).</span><span class="sxs-lookup"><span data-stu-id="a0d32-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="a0d32-109">Rappresentazione JSON</span><span class="sxs-lookup"><span data-stu-id="a0d32-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="a0d32-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a0d32-110">Properties</span></span>

| <span data-ttu-id="a0d32-111">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a0d32-111">Property</span></span><br><span data-ttu-id="a0d32-112">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="a0d32-112">**Physical name**</span></span><br><span data-ttu-id="a0d32-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="a0d32-113">**_Type_**</span></span> | <span data-ttu-id="a0d32-114">Utilizza</span><span class="sxs-lookup"><span data-stu-id="a0d32-114">Use</span></span> | <span data-ttu-id="a0d32-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0d32-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a0d32-116">**ID entità tipo certificato**</span><span class="sxs-lookup"><span data-stu-id="a0d32-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="a0d32-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="a0d32-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="a0d32-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a0d32-118">*GUID*</span></span> | <span data-ttu-id="a0d32-119">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0d32-119">Read-only</span></span><br><span data-ttu-id="a0d32-120">Richiesto</span><span class="sxs-lookup"><span data-stu-id="a0d32-120">Required</span></span> 
<span data-ttu-id="a0d32-121">Generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="a0d32-121">System-generated</span></span> | <span data-ttu-id="a0d32-122">Identificatore univoco principale per il tipo di certificato.</span><span class="sxs-lookup"><span data-stu-id="a0d32-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="a0d32-123">**Tipo di certificato**</span><span class="sxs-lookup"><span data-stu-id="a0d32-123">**Certificate Type**</span></span><br><span data-ttu-id="a0d32-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="a0d32-124">mshr_certificatetype</span></span><br><span data-ttu-id="a0d32-125">*String*</span><span class="sxs-lookup"><span data-stu-id="a0d32-125">*String*</span></span> | <span data-ttu-id="a0d32-126">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="a0d32-126">Read/write</span></span><br><span data-ttu-id="a0d32-127">Richiesto</span><span class="sxs-lookup"><span data-stu-id="a0d32-127">Required</span></span> | <span data-ttu-id="a0d32-128">Identificatore univoco leggibile dall'utente per il tipo di certificato.</span><span class="sxs-lookup"><span data-stu-id="a0d32-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="a0d32-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a0d32-129">**Description**</span></span><br><span data-ttu-id="a0d32-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="a0d32-130">mshr_description</span></span><br><span data-ttu-id="a0d32-131">*String*</span><span class="sxs-lookup"><span data-stu-id="a0d32-131">*String*</span></span> | <span data-ttu-id="a0d32-132">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="a0d32-132">Read/write</span></span><br><span data-ttu-id="a0d32-133">Richiesto</span><span class="sxs-lookup"><span data-stu-id="a0d32-133">Required</span></span> | <span data-ttu-id="a0d32-134">Descrizione del tipo di certificato.</span><span class="sxs-lookup"><span data-stu-id="a0d32-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="a0d32-135">**Richiedi rinnovo**</span><span class="sxs-lookup"><span data-stu-id="a0d32-135">**Require Renewal**</span></span><br><span data-ttu-id="a0d32-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="a0d32-136">mshr_requirerenewal</span></span><br><span data-ttu-id="a0d32-137">*set di opzioni mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="a0d32-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="a0d32-138">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="a0d32-138">Read/write</span></span><br><span data-ttu-id="a0d32-139">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="a0d32-139">Optional</span></span> | <span data-ttu-id="a0d32-140">Indica se è necessario il rinnovo del certificato.</span><span class="sxs-lookup"><span data-stu-id="a0d32-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a0d32-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0d32-141">See also</span></span>

[<span data-ttu-id="a0d32-142">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="a0d32-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="a0d32-143">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="a0d32-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]