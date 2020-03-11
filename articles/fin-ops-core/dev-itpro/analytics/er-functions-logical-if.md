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
ms.openlocfilehash: 198210f15e75de761dbb03e5087ba7c77a95721a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041747"
---
# <span data-ttu-id="7ba1e-103"><a name="IF">Funzione ER IF</a></span><span class="sxs-lookup"><span data-stu-id="7ba1e-103"><a name="IF">IF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ba1e-104">La funzione `IF` restituisce il primo valore specificato se viene soddisfatta la condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-104">The `IF` function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="7ba1e-105">In caso contrario, restituisce il secondo valore specificato.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-105">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="7ba1e-106">Il valore restituito può essere un valore di uno qualsiasi dei tipi di dati supportati.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ba1e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ba1e-107">Syntax</span></span>

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a><span data-ttu-id="7ba1e-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7ba1e-108">Arguments</span></span>

<span data-ttu-id="7ba1e-109">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="7ba1e-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="7ba1e-110">Un'espressione condizionale valida che deve essere testata.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-110">A valid conditional expression that must be tested.</span></span>

<span data-ttu-id="7ba1e-111">`first value`: *Qualsiasi tipo di dati supportato*</span><span class="sxs-lookup"><span data-stu-id="7ba1e-111">`first value`: *Any of the supported data types*</span></span>

<span data-ttu-id="7ba1e-112">Il risultato che viene restituito se la condizione viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-112">The result that is returned if the condition is met.</span></span>

<span data-ttu-id="7ba1e-113">`second value`: *Qualsiasi tipo di dati supportato*</span><span class="sxs-lookup"><span data-stu-id="7ba1e-113">`second value`: *Any of the supported data types*</span></span>

<span data-ttu-id="7ba1e-114">Il risultato che viene restituito se la condizione non viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-114">The result that is returned if the condition isn't met.</span></span>

## <a name="return-values"></a><span data-ttu-id="7ba1e-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="7ba1e-115">Return values</span></span>

<span data-ttu-id="7ba1e-116">*Qualsiasi tipo di dati supportato*</span><span class="sxs-lookup"><span data-stu-id="7ba1e-116">*Any of the supported data types*</span></span>

<span data-ttu-id="7ba1e-117">Il valore risultante di uno qualsiasi dei tipi di dati supportati.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-117">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7ba1e-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="7ba1e-118">Usage notes</span></span>

<span data-ttu-id="7ba1e-119">Gli argomenti `first value` e `second value` devono essere specificati utilizzando lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-119">The `first value` and `second value` arguments must be specified by using the same data type.</span></span> <span data-ttu-id="7ba1e-120">In fase di progettazione viene generata un'eccezione se i tipi di dati dei valori configurati non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-120">An exception is thrown at design time if the data types of the configured values don't match.</span></span>

<span data-ttu-id="7ba1e-121">Se il primo valore e il secondo valore sono valori del tipo di dati *Contenitore (record)* o *Elenco di record*, il risultato ha solo i campi esistenti in entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-121">If the first value and the second value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="7ba1e-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ba1e-122">Example</span></span>

<span data-ttu-id="7ba1e-123">`IF (1=2, "condition is met", "condition is not met")` restituisce la stringa **"condition is not met"**.</span><span class="sxs-lookup"><span data-stu-id="7ba1e-123">`IF (1=2, "condition is met", "condition is not met")` returns the string **"condition is not met"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ba1e-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7ba1e-124">Additional resources</span></span>

[<span data-ttu-id="7ba1e-125">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="7ba1e-125">Logical functions</span></span>](er-functions-category-logical.md)
