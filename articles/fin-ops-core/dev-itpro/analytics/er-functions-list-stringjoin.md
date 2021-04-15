---
title: Funzione ER STRINGJOIN
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione STRINGJOIN della creazione di report elettronici (ER).
author: NickSelin
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
ms.openlocfilehash: ac21651e0f5b5a1579b9335bb7f3217370c4d5a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745523"
---
# <a name="stringjoin-er-function"></a><span data-ttu-id="22a79-103">Funzione ER STRINGJOIN</span><span class="sxs-lookup"><span data-stu-id="22a79-103">STRINGJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="22a79-104">La funzione `STRINGJOIN` restituisce un valore *Stringa* costituito da valori concatenati del campo specificato dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="22a79-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="22a79-105">I valori possono essere separati dal delimitatore specificato.</span><span class="sxs-lookup"><span data-stu-id="22a79-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="22a79-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22a79-106">Syntax</span></span>

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="22a79-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="22a79-107">Arguments</span></span>

<span data-ttu-id="22a79-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="22a79-108">`list`: *Record list*</span></span>

<span data-ttu-id="22a79-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="22a79-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="22a79-110">`field`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="22a79-110">`field`: *Field*</span></span>

<span data-ttu-id="22a79-111">Il percorso valido di un campo del tipo di dati *Stringa* nell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="22a79-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="22a79-112">`delimiter`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="22a79-112">`delimiter`: *String*</span></span>

<span data-ttu-id="22a79-113">Un delimitatore utilizzato per separare le sottostringhe.</span><span class="sxs-lookup"><span data-stu-id="22a79-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="22a79-114">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="22a79-114">Return values</span></span>

<span data-ttu-id="22a79-115">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="22a79-115">*String*</span></span>

<span data-ttu-id="22a79-116">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="22a79-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="22a79-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="22a79-117">Example</span></span>

<span data-ttu-id="22a79-118">Se si immette `SPLIT("abc" , 1)`come origine dati **DS**, l'espressione `STRINGJOIN (DS, DS.Value, "-")` restituisce **"a-b-c"**.</span><span class="sxs-lookup"><span data-stu-id="22a79-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="22a79-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="22a79-119">Additional resources</span></span>

[<span data-ttu-id="22a79-120">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="22a79-120">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]