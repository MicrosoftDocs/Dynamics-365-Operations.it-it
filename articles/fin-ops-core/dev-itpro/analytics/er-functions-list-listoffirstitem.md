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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d985ef5015bc104a83260b64418821cc715e8cb
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917260"
---
# <span data-ttu-id="ec0cf-103"><a name="LISTOFFIRSTITEM">Funzione ER LISTOFFIRSTITEM</a></span><span class="sxs-lookup"><span data-stu-id="ec0cf-103"><a name="LISTOFFIRSTITEM">LISTOFFIRSTITEM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec0cf-104">La funzione `LISTOFFIRSTITEM` restituisce un valore *Elenco di record* costituito solo dal primo record dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="ec0cf-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="ec0cf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec0cf-105">Syntax</span></span>

```
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="ec0cf-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ec0cf-106">Arguments</span></span>

<span data-ttu-id="ec0cf-107">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="ec0cf-107">`list`: *Record list*</span></span>

<span data-ttu-id="ec0cf-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="ec0cf-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ec0cf-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="ec0cf-109">Return values</span></span>

<span data-ttu-id="ec0cf-110">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="ec0cf-110">*Record list*</span></span>

<span data-ttu-id="ec0cf-111">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="ec0cf-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="ec0cf-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="ec0cf-112">Example</span></span>

<span data-ttu-id="ec0cf-113">L'espressione `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` restituisce il valore del testo **"A"**.</span><span class="sxs-lookup"><span data-stu-id="ec0cf-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ec0cf-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ec0cf-114">Additional resources</span></span>

[<span data-ttu-id="ec0cf-115">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="ec0cf-115">List functions</span></span>](er-functions-category-list.md)
