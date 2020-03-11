---
title: Funzione ER ABS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ABS della creazione di report elettronici (ER).
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
ms.openlocfilehash: 214fb2808f024487795f27de45de1d4de8cead2d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041655"
---
# <span data-ttu-id="b7059-103"><a name="ABS">Funzione ER ABS</a></span><span class="sxs-lookup"><span data-stu-id="b7059-103"><a name="ABS">ABS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b7059-104">La funzione `ABS` restituisce il valore assoluto (modulo) del numero specificato come valore *Reale*.</span><span class="sxs-lookup"><span data-stu-id="b7059-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="b7059-105">In altre parole, restituisce il numero senza il segno.</span><span class="sxs-lookup"><span data-stu-id="b7059-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7059-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7059-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="b7059-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b7059-107">Arguments</span></span>

<span data-ttu-id="b7059-108">`number`: *Reale*</span><span class="sxs-lookup"><span data-stu-id="b7059-108">`number`: *Real*</span></span>

<span data-ttu-id="b7059-109">Un valore numerico di cui si desidera il modulo.</span><span class="sxs-lookup"><span data-stu-id="b7059-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="b7059-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="b7059-110">Return values</span></span>

<span data-ttu-id="b7059-111">*Reale*</span><span class="sxs-lookup"><span data-stu-id="b7059-111">*Real*</span></span>

<span data-ttu-id="b7059-112">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="b7059-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="b7059-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7059-113">Example</span></span>

<span data-ttu-id="b7059-114">`ABS (-1)` restituisce **1**.</span><span class="sxs-lookup"><span data-stu-id="b7059-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b7059-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b7059-115">Additional resources</span></span>

[<span data-ttu-id="b7059-116">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="b7059-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)
