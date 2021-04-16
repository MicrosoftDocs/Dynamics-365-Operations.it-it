---
title: Funzione ER NOT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NOT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 7c10ed61b97dcd4d4a66a530bb3d08c539659233
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751717"
---
# <a name="not-er-function"></a><span data-ttu-id="8a175-103">Funzione ER NOT</span><span class="sxs-lookup"><span data-stu-id="8a175-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a175-104">La funzione `NOT` restituisce il valore logico inverso della condizione specificata come valore *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="8a175-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a175-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a175-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="8a175-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8a175-106">Arguments</span></span>

<span data-ttu-id="8a175-107">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="8a175-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="8a175-108">Un'espressione condizionale valida che deve essere invertita.</span><span class="sxs-lookup"><span data-stu-id="8a175-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="8a175-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="8a175-109">Return values</span></span>

<span data-ttu-id="8a175-110">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="8a175-110">*Boolean*</span></span>

<span data-ttu-id="8a175-111">Il valore *Booleano* risultante.</span><span class="sxs-lookup"><span data-stu-id="8a175-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="8a175-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a175-112">Example</span></span>

<span data-ttu-id="8a175-113">`NOT (TRUE)` restituisce **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="8a175-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8a175-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8a175-114">Additional resources</span></span>

[<span data-ttu-id="8a175-115">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="8a175-115">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]