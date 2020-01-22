---
title: Funzione ER ADDDAYS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ADDDAYS della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd1290538c506cd0db6eb21a304ff9812c808f17
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916455"
---
# <span data-ttu-id="451fa-103"><a name="ADDDAYS">Funzione ER ADDDAYS</a></span><span class="sxs-lookup"><span data-stu-id="451fa-103"><a name="ADDDAYS">ADDDAYS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="451fa-104">La funzione `ADDDAYS` calcola un valore *DateTime* che è il numero specificato di giorni prima o dopo una data di inizio specificata.</span><span class="sxs-lookup"><span data-stu-id="451fa-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="451fa-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="451fa-105">Syntax</span></span>

```
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="451fa-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="451fa-106">Arguments</span></span>

<span data-ttu-id="451fa-107">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="451fa-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="451fa-108">Un valore data/ora che rappresenta la data di inizio.</span><span class="sxs-lookup"><span data-stu-id="451fa-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="451fa-109">`days`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="451fa-109">`days`: *Integer*</span></span>

<span data-ttu-id="451fa-110">Il numero di giorni prima o dopo `datetime`.</span><span class="sxs-lookup"><span data-stu-id="451fa-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="451fa-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="451fa-111">Return values</span></span>

<span data-ttu-id="451fa-112">*Data/Ora*</span><span class="sxs-lookup"><span data-stu-id="451fa-112">*DateTime*</span></span>

<span data-ttu-id="451fa-113">Il valore di data/ora risultante.</span><span class="sxs-lookup"><span data-stu-id="451fa-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="451fa-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="451fa-114">Usage notes</span></span>

<span data-ttu-id="451fa-115">Un valore positivo per `days`produce una data futura.</span><span class="sxs-lookup"><span data-stu-id="451fa-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="451fa-116">Un valore negativo restituisce una data trascorsa.</span><span class="sxs-lookup"><span data-stu-id="451fa-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="451fa-117">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="451fa-117">Example 1</span></span>

<span data-ttu-id="451fa-118">`ADDDAYS (NOW(), 7)` restituisce la data e l'ora di sette giorni in futuro.</span><span class="sxs-lookup"><span data-stu-id="451fa-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="451fa-119">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="451fa-119">Example 2</span></span>

<span data-ttu-id="451fa-120">`ADDDAYS (NOW(), -3)` restituisce la data e l'ora di tre giorni in passato.</span><span class="sxs-lookup"><span data-stu-id="451fa-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="451fa-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="451fa-121">Additional resources</span></span>

[<span data-ttu-id="451fa-122">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="451fa-122">Date and time functions</span></span>](er-functions-category-datetime.md)
