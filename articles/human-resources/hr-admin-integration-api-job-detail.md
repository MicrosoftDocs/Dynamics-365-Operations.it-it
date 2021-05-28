---
title: API Dettagli posizione lavorativa
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Dettagli posizione lavorativa in Dynamics 365 Human Resources.
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
ms.openlocfilehash: c92b0636fbd68c6ee7eded90a8cb5bcd0cda7ca3
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018364"
---
# <a name="job-detail-api"></a><span data-ttu-id="7cc89-103">API Dettagli posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="7cc89-103">Job detail API</span></span>

<span data-ttu-id="7cc89-104">Questo argomento fornisce dettagli e una query di esempio per l'entità Dettagli posizione lavorativa in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7cc89-104">This topic provides details and an example query for the Job detail entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="7cc89-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7cc89-105">Properties</span></span>

| <span data-ttu-id="7cc89-106">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7cc89-106">Property</span></span><br><span data-ttu-id="7cc89-107">**Nome fisico**</span><span class="sxs-lookup"><span data-stu-id="7cc89-107">**Physical name**</span></span><br><span data-ttu-id="7cc89-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="7cc89-108">**_Type_**</span></span> | <span data-ttu-id="7cc89-109">Utilizza</span><span class="sxs-lookup"><span data-stu-id="7cc89-109">Use</span></span> | <span data-ttu-id="7cc89-110">descrizione</span><span class="sxs-lookup"><span data-stu-id="7cc89-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7cc89-111">**ID lavoro**</span><span class="sxs-lookup"><span data-stu-id="7cc89-111">**Job ID**</span></span><br><span data-ttu-id="7cc89-112">mshr_jobid</span><span class="sxs-lookup"><span data-stu-id="7cc89-112">mshr_jobid</span></span><br><span data-ttu-id="7cc89-113">*String*</span><span class="sxs-lookup"><span data-stu-id="7cc89-113">*String*</span></span> | <span data-ttu-id="7cc89-114">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="7cc89-114">Read-only</span></span><br><span data-ttu-id="7cc89-115">Richiesto</span><span class="sxs-lookup"><span data-stu-id="7cc89-115">Required</span></span> | <span data-ttu-id="7cc89-116">ID univoco per una mansione.</span><span class="sxs-lookup"><span data-stu-id="7cc89-116">Unique ID for a job.</span></span> |
| <span data-ttu-id="7cc89-117">**Soglia bassa prezzo di mercato**</span><span class="sxs-lookup"><span data-stu-id="7cc89-117">**Market price low threshold**</span></span><br><span data-ttu-id="7cc89-118">mshr_marketpricelowthreshold</span><span class="sxs-lookup"><span data-stu-id="7cc89-118">mshr_marketpricelowthreshold</span></span><br><span data-ttu-id="7cc89-119">*Decimali*</span><span class="sxs-lookup"><span data-stu-id="7cc89-119">*Decimal*</span></span> | | <span data-ttu-id="7cc89-120">Un valore GUID generato dal sistema per identificare in modo univoco la posizione.</span><span class="sxs-lookup"><span data-stu-id="7cc89-120">A system-generated GUID value to uniquely identify the position.</span></span>  |
