---
title: API Dettagli posizione lavorativa
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Dettagli posizione lavorativa in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 562b9f505311b6cfe505a76fc5c0a384eb641936
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054766"
---
# <a name="job-detail-api"></a><span data-ttu-id="f5fff-103">API Dettagli posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="f5fff-103">Job detail API</span></span>

<span data-ttu-id="f5fff-104">Questo argomento fornisce dettagli e una query di esempio per l'entità Dettagli posizione lavorativa in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f5fff-104">This topic provides details and an example query for the Job detail entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="f5fff-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f5fff-105">Properties</span></span>

| <span data-ttu-id="f5fff-106">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f5fff-106">Property</span></span><br><span data-ttu-id="f5fff-107">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="f5fff-107">**Physical name**</span></span><br><span data-ttu-id="f5fff-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="f5fff-108">**_Type_**</span></span> | <span data-ttu-id="f5fff-109">Utilizza</span><span class="sxs-lookup"><span data-stu-id="f5fff-109">Use</span></span> | <span data-ttu-id="f5fff-110">descrizione</span><span class="sxs-lookup"><span data-stu-id="f5fff-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f5fff-111">**ID lavoro**</span><span class="sxs-lookup"><span data-stu-id="f5fff-111">**Job ID**</span></span><br><span data-ttu-id="f5fff-112">mshr_jobid</span><span class="sxs-lookup"><span data-stu-id="f5fff-112">mshr_jobid</span></span><br><span data-ttu-id="f5fff-113">*String*</span><span class="sxs-lookup"><span data-stu-id="f5fff-113">*String*</span></span> | <span data-ttu-id="f5fff-114">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="f5fff-114">Read-only</span></span><br><span data-ttu-id="f5fff-115">Richiesto</span><span class="sxs-lookup"><span data-stu-id="f5fff-115">Required</span></span> | <span data-ttu-id="f5fff-116">ID univoco per una mansione.</span><span class="sxs-lookup"><span data-stu-id="f5fff-116">Unique ID for a job.</span></span> |
| <span data-ttu-id="f5fff-117">**Soglia bassa prezzo di mercato**</span><span class="sxs-lookup"><span data-stu-id="f5fff-117">**Market price low threshold**</span></span><br><span data-ttu-id="f5fff-118">mshr_marketpricelowthreshold</span><span class="sxs-lookup"><span data-stu-id="f5fff-118">mshr_marketpricelowthreshold</span></span><br><span data-ttu-id="f5fff-119">*Decimali*</span><span class="sxs-lookup"><span data-stu-id="f5fff-119">*Decimal*</span></span> | | <span data-ttu-id="f5fff-120">Un valore GUID generato dal sistema per identificare in modo univoco la posizione.</span><span class="sxs-lookup"><span data-stu-id="f5fff-120">A system-generated GUID value to uniquely identify the position.</span></span>  |
