---
title: Funzione ER FIRSTORNULL
description: In questo argomento illustra l'utilizzo della funzione FIRSTORNULL della creazione di report elettronici (ER)
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: e360812c5b0dbfb8df4ab279bf3e0050acebbb25
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745202"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="fc09c-103">Funzione ER FIRSTORNULL</span><span class="sxs-lookup"><span data-stu-id="fc09c-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fc09c-104">La funzione `FIRSTORNULL` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale record non è vuoto.</span><span class="sxs-lookup"><span data-stu-id="fc09c-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="fc09c-105">Se il record è vuoto, questa funzione restituisce un valore null *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="fc09c-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc09c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc09c-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="fc09c-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fc09c-107">Arguments</span></span>

<span data-ttu-id="fc09c-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="fc09c-108">`list`: *Record list*</span></span>

<span data-ttu-id="fc09c-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="fc09c-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="fc09c-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="fc09c-110">Return values</span></span>

<span data-ttu-id="fc09c-111">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="fc09c-111">*Container (record)*</span></span>

<span data-ttu-id="fc09c-112">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="fc09c-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="fc09c-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc09c-113">Example</span></span>

<span data-ttu-id="fc09c-114">L'espressione `FIRSTORNULL(SPLIT("",1)).Value` restituisce una stringa vuota ( **""**).</span><span class="sxs-lookup"><span data-stu-id="fc09c-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fc09c-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fc09c-115">Additional resources</span></span>

[<span data-ttu-id="fc09c-116">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="fc09c-116">List functions</span></span>](er-functions-category-list.md)
