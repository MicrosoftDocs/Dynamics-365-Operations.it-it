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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3547eeea3c6fef5cca0699002cc0c35cffd940b3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688045"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="532cc-103">Funzione ER FIRSTORNULL</span><span class="sxs-lookup"><span data-stu-id="532cc-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="532cc-104">La funzione `FIRSTORNULL` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale record non è vuoto.</span><span class="sxs-lookup"><span data-stu-id="532cc-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="532cc-105">Se il record è vuoto, questa funzione restituisce un valore null *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="532cc-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="532cc-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="532cc-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="532cc-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="532cc-107">Arguments</span></span>

<span data-ttu-id="532cc-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="532cc-108">`list`: *Record list*</span></span>

<span data-ttu-id="532cc-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="532cc-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="532cc-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="532cc-110">Return values</span></span>

<span data-ttu-id="532cc-111">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="532cc-111">*Container (record)*</span></span>

<span data-ttu-id="532cc-112">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="532cc-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="532cc-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="532cc-113">Example</span></span>

<span data-ttu-id="532cc-114">L'espressione `FIRSTORNULL(SPLIT("",1)).Value` restituisce una stringa vuota ( **""**).</span><span class="sxs-lookup"><span data-stu-id="532cc-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="532cc-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="532cc-115">Additional resources</span></span>

[<span data-ttu-id="532cc-116">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="532cc-116">List functions</span></span>](er-functions-category-list.md)
