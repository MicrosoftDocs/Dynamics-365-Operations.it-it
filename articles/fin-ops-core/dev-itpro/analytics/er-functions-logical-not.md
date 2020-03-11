---
title: Funzione ER NOT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NOT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: a518f255a4488c5ed6e007b1787e678fd88aff36
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041724"
---
# <span data-ttu-id="c8dae-103"><a name="NOT">Funzione ER NOT</a></span><span class="sxs-lookup"><span data-stu-id="c8dae-103"><a name="NOT">NOT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8dae-104">La funzione `NOT` restituisce il valore logico inverso della condizione specificata come valore *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="c8dae-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8dae-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8dae-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="c8dae-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c8dae-106">Arguments</span></span>

<span data-ttu-id="c8dae-107">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="c8dae-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="c8dae-108">Un'espressione condizionale valida che deve essere invertita.</span><span class="sxs-lookup"><span data-stu-id="c8dae-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="c8dae-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="c8dae-109">Return values</span></span>

<span data-ttu-id="c8dae-110">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="c8dae-110">*Boolean*</span></span>

<span data-ttu-id="c8dae-111">Il valore *Booleano* risultante.</span><span class="sxs-lookup"><span data-stu-id="c8dae-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="c8dae-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8dae-112">Example</span></span>

<span data-ttu-id="c8dae-113">`NOT (TRUE)` restituisce **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="c8dae-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8dae-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c8dae-114">Additional resources</span></span>

[<span data-ttu-id="c8dae-115">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="c8dae-115">Logical functions</span></span>](er-functions-category-logical.md)
