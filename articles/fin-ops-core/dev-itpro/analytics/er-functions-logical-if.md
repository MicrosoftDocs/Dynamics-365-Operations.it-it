---
title: Funzione ER IF
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione IF della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: b29302ffe534f2439519e57c6a6b8c94c1df8d62
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917145"
---
# <span data-ttu-id="c3764-103"><a name="IF">Funzione ER IF</a></span><span class="sxs-lookup"><span data-stu-id="c3764-103"><a name="IF">IF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3764-104">La funzione `IF` restituisce il primo valore specificato se viene soddisfatta la condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="c3764-104">The `IF` function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="c3764-105">In caso contrario, restituisce il secondo valore specificato.</span><span class="sxs-lookup"><span data-stu-id="c3764-105">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="c3764-106">Il valore restituito può essere un valore di uno qualsiasi dei tipi di dati supportati.</span><span class="sxs-lookup"><span data-stu-id="c3764-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3764-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3764-107">Syntax</span></span>

```
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a><span data-ttu-id="c3764-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c3764-108">Arguments</span></span>

<span data-ttu-id="c3764-109">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="c3764-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="c3764-110">Un'espressione condizionale valida che deve essere testata.</span><span class="sxs-lookup"><span data-stu-id="c3764-110">A valid conditional expression that must be tested.</span></span>

<span data-ttu-id="c3764-111">`first value`: *Qualsiasi tipo di dati supportato*</span><span class="sxs-lookup"><span data-stu-id="c3764-111">`first value`: *Any of the supported data types*</span></span>

<span data-ttu-id="c3764-112">Il risultato che viene restituito se la condizione viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="c3764-112">The result that is returned if the condition is met.</span></span>

<span data-ttu-id="c3764-113">`second value`: *Qualsiasi tipo di dati supportato*</span><span class="sxs-lookup"><span data-stu-id="c3764-113">`second value`: *Any of the supported data types*</span></span>

<span data-ttu-id="c3764-114">Il risultato che viene restituito se la condizione non viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="c3764-114">The result that is returned if the condition isn't met.</span></span>

## <a name="return-values"></a><span data-ttu-id="c3764-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="c3764-115">Return values</span></span>

<span data-ttu-id="c3764-116">*Qualsiasi tipo di dati supportato*</span><span class="sxs-lookup"><span data-stu-id="c3764-116">*Any of the supported data types*</span></span>

<span data-ttu-id="c3764-117">Il valore risultante di uno qualsiasi dei tipi di dati supportati.</span><span class="sxs-lookup"><span data-stu-id="c3764-117">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c3764-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="c3764-118">Usage notes</span></span>

<span data-ttu-id="c3764-119">Gli argomenti `first value` e `second value` devono essere specificati utilizzando lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="c3764-119">The `first value` and `second value` arguments must be specified by using the same data type.</span></span> <span data-ttu-id="c3764-120">In fase di progettazione viene generata un'eccezione se i tipi di dati dei valori configurati non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="c3764-120">An exception is thrown at design time if the data types of the configured values don't match.</span></span>

<span data-ttu-id="c3764-121">Se il primo valore e il secondo valore sono valori del tipo di dati *Contenitore (record)* o *Elenco di record*, il risultato ha solo i campi esistenti in entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="c3764-121">If the first value and the second value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="c3764-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3764-122">Example</span></span>

<span data-ttu-id="c3764-123">`IF (1=2, "condition is met", "condition is not met")` restituisce la stringa **"condition is not met"**.</span><span class="sxs-lookup"><span data-stu-id="c3764-123">`IF (1=2, "condition is met", "condition is not met")` returns the string **"condition is not met"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c3764-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c3764-124">Additional resources</span></span>

[<span data-ttu-id="c3764-125">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="c3764-125">Logical functions</span></span>](er-functions-category-logical.md)
