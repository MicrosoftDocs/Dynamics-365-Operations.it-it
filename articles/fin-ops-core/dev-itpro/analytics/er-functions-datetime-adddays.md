---
title: Funzione ER ADDDAYS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ADDDAYS della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c420daa04b8e22504d25d317c75826f1d1914b7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747061"
---
# <a name="adddays-er-function"></a><span data-ttu-id="1a137-103">Funzione ER ADDDAYS</span><span class="sxs-lookup"><span data-stu-id="1a137-103">ADDDAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a137-104">La funzione `ADDDAYS` calcola un valore *DateTime* che è il numero specificato di giorni prima o dopo una data di inizio specificata.</span><span class="sxs-lookup"><span data-stu-id="1a137-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a137-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a137-105">Syntax</span></span>

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="1a137-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1a137-106">Arguments</span></span>

<span data-ttu-id="1a137-107">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="1a137-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="1a137-108">Un valore data/ora che rappresenta la data di inizio.</span><span class="sxs-lookup"><span data-stu-id="1a137-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="1a137-109">`days`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="1a137-109">`days`: *Integer*</span></span>

<span data-ttu-id="1a137-110">Il numero di giorni prima o dopo `datetime`.</span><span class="sxs-lookup"><span data-stu-id="1a137-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="1a137-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="1a137-111">Return values</span></span>

<span data-ttu-id="1a137-112">*Data/Ora*</span><span class="sxs-lookup"><span data-stu-id="1a137-112">*DateTime*</span></span>

<span data-ttu-id="1a137-113">Il valore di data/ora risultante.</span><span class="sxs-lookup"><span data-stu-id="1a137-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1a137-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="1a137-114">Usage notes</span></span>

<span data-ttu-id="1a137-115">Un valore positivo per `days`produce una data futura.</span><span class="sxs-lookup"><span data-stu-id="1a137-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="1a137-116">Un valore negativo restituisce una data trascorsa.</span><span class="sxs-lookup"><span data-stu-id="1a137-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="1a137-117">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="1a137-117">Example 1</span></span>

<span data-ttu-id="1a137-118">`ADDDAYS (NOW(), 7)` restituisce la data e l'ora di sette giorni in futuro.</span><span class="sxs-lookup"><span data-stu-id="1a137-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="1a137-119">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="1a137-119">Example 2</span></span>

<span data-ttu-id="1a137-120">`ADDDAYS (NOW(), -3)` restituisce la data e l'ora di tre giorni in passato.</span><span class="sxs-lookup"><span data-stu-id="1a137-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a137-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1a137-121">Additional resources</span></span>

[<span data-ttu-id="1a137-122">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="1a137-122">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]