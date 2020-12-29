---
title: Funzione ER LISTOFFIRSTITEM
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LISTOFFIRSTITEM della creazione di report elettronici (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ea81bce8cd6b922f3ef1d53ec0c4b2574780377
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686490"
---
# <a name="listoffirstitem-er-function"></a><span data-ttu-id="9f6b4-103">Funzione ER LISTOFFIRSTITEM</span><span class="sxs-lookup"><span data-stu-id="9f6b4-103">LISTOFFIRSTITEM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f6b4-104">La funzione `LISTOFFIRSTITEM` restituisce un valore *Elenco di record* costituito solo dal primo record dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="9f6b4-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f6b4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f6b4-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="9f6b4-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9f6b4-106">Arguments</span></span>

<span data-ttu-id="9f6b4-107">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="9f6b4-107">`list`: *Record list*</span></span>

<span data-ttu-id="9f6b4-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="9f6b4-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="9f6b4-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="9f6b4-109">Return values</span></span>

<span data-ttu-id="9f6b4-110">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="9f6b4-110">*Record list*</span></span>

<span data-ttu-id="9f6b4-111">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="9f6b4-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="9f6b4-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f6b4-112">Example</span></span>

<span data-ttu-id="9f6b4-113">L'espressione `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` restituisce il valore del testo **"A"**.</span><span class="sxs-lookup"><span data-stu-id="9f6b4-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f6b4-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9f6b4-114">Additional resources</span></span>

[<span data-ttu-id="9f6b4-115">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="9f6b4-115">List functions</span></span>](er-functions-category-list.md)
