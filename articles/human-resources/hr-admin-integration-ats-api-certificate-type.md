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
ms.openlocfilehash: 1d2d53a628ef43d50bd83fd6b62807f44eddd653
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125715"
---
# <a name="certificate-type"></a><span data-ttu-id="b99d9-103">Tipo di certificato</span><span class="sxs-lookup"><span data-stu-id="b99d9-103">Certificate type</span></span>

<span data-ttu-id="b99d9-104">Questo argomento descrive l'entità Tipo di certificato per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b99d9-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="b99d9-105">Nome fisico: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="b99d9-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="b99d9-106">descrizione</span><span class="sxs-lookup"><span data-stu-id="b99d9-106">Description</span></span>

<span data-ttu-id="b99d9-107">Questa entità definisce l'elenco dei tipi di certificati professionali impostati in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b99d9-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="b99d9-108">L'entità non è specifica di una persona giuridica (società).</span><span class="sxs-lookup"><span data-stu-id="b99d9-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="b99d9-109">Rappresentazione JSON</span><span class="sxs-lookup"><span data-stu-id="b99d9-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="b99d9-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b99d9-110">Properties</span></span>

| <span data-ttu-id="b99d9-111">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b99d9-111">Property</span></span><br><span data-ttu-id="b99d9-112">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="b99d9-112">**Physical name**</span></span><br><span data-ttu-id="b99d9-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="b99d9-113">**_Type_**</span></span> | <span data-ttu-id="b99d9-114">Utilizza</span><span class="sxs-lookup"><span data-stu-id="b99d9-114">Use</span></span> | <span data-ttu-id="b99d9-115">descrizione</span><span class="sxs-lookup"><span data-stu-id="b99d9-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b99d9-116">**ID entità tipo certificato**</span><span class="sxs-lookup"><span data-stu-id="b99d9-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="b99d9-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="b99d9-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="b99d9-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b99d9-118">*GUID*</span></span> | <span data-ttu-id="b99d9-119">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="b99d9-119">Read-only</span></span><br><span data-ttu-id="b99d9-120">Richiesto</span><span class="sxs-lookup"><span data-stu-id="b99d9-120">Required</span></span> 
<span data-ttu-id="b99d9-121">Generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="b99d9-121">System-generated</span></span> | <span data-ttu-id="b99d9-122">Identificatore univoco principale per il tipo di certificato.</span><span class="sxs-lookup"><span data-stu-id="b99d9-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="b99d9-123">**Tipo di certificato**</span><span class="sxs-lookup"><span data-stu-id="b99d9-123">**Certificate Type**</span></span><br><span data-ttu-id="b99d9-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="b99d9-124">mshr_certificatetype</span></span><br><span data-ttu-id="b99d9-125">*String*</span><span class="sxs-lookup"><span data-stu-id="b99d9-125">*String*</span></span> | <span data-ttu-id="b99d9-126">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="b99d9-126">Read/write</span></span><br><span data-ttu-id="b99d9-127">Richiesto</span><span class="sxs-lookup"><span data-stu-id="b99d9-127">Required</span></span> | <span data-ttu-id="b99d9-128">Identificatore univoco leggibile dall'utente per il tipo di certificato.</span><span class="sxs-lookup"><span data-stu-id="b99d9-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="b99d9-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b99d9-129">**Description**</span></span><br><span data-ttu-id="b99d9-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="b99d9-130">mshr_description</span></span><br><span data-ttu-id="b99d9-131">*String*</span><span class="sxs-lookup"><span data-stu-id="b99d9-131">*String*</span></span> | <span data-ttu-id="b99d9-132">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="b99d9-132">Read/write</span></span><br><span data-ttu-id="b99d9-133">Richiesto</span><span class="sxs-lookup"><span data-stu-id="b99d9-133">Required</span></span> | <span data-ttu-id="b99d9-134">Descrizione del tipo di certificato.</span><span class="sxs-lookup"><span data-stu-id="b99d9-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="b99d9-135">**Richiedi rinnovo**</span><span class="sxs-lookup"><span data-stu-id="b99d9-135">**Require Renewal**</span></span><br><span data-ttu-id="b99d9-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="b99d9-136">mshr_requirerenewal</span></span><br><span data-ttu-id="b99d9-137">*set di opzioni mshr_noyes*</span><span class="sxs-lookup"><span data-stu-id="b99d9-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="b99d9-138">Lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="b99d9-138">Read/write</span></span><br><span data-ttu-id="b99d9-139">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="b99d9-139">Optional</span></span> | <span data-ttu-id="b99d9-140">Indica se è necessario il rinnovo del certificato.</span><span class="sxs-lookup"><span data-stu-id="b99d9-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b99d9-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b99d9-141">See also</span></span>

[<span data-ttu-id="b99d9-142">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="b99d9-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="b99d9-143">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="b99d9-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

