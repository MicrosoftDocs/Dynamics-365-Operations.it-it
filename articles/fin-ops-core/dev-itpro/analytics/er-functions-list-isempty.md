---
title: Funzione ER ISEMPTY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ISEMPTY della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: b689e6d4bb849f07db5d00cf8a9dc5c16646a927
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563874"
---
# <a name="isempty-er-function"></a><span data-ttu-id="78599-103">Funzione ER ISEMPTY</span><span class="sxs-lookup"><span data-stu-id="78599-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78599-104">La funzione `ISEMPTY` restituisce un valore *Booleano* **TRUE** se l'elenco specificato non contiene record.</span><span class="sxs-lookup"><span data-stu-id="78599-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="78599-105">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="78599-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="78599-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78599-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="78599-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="78599-107">Arguments</span></span>

<span data-ttu-id="78599-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="78599-108">`list`: *Record list*</span></span>

<span data-ttu-id="78599-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="78599-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="78599-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="78599-110">Return values</span></span>

<span data-ttu-id="78599-111">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="78599-111">*Boolean*</span></span>

<span data-ttu-id="78599-112">Il valore *Booleano* risultante.</span><span class="sxs-lookup"><span data-stu-id="78599-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="78599-113">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="78599-113">Example 1</span></span>

<span data-ttu-id="78599-114">Se si immette l'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("A|B|C", "|")`, l'espressione `ISEMPTY(DS)` restituisce **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="78599-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="78599-115">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="78599-115">Example 2</span></span>

<span data-ttu-id="78599-116">L'espressione `ISEMPTY (SPLIT ("",1))` restituisce **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="78599-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78599-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="78599-117">Additional resources</span></span>

[<span data-ttu-id="78599-118">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="78599-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]