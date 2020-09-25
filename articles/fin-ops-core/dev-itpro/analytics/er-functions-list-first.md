---
title: Funzione ER FIRST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FIRST della creazione di report elettronici (ER).
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
ms.openlocfilehash: 3ed0e0aaf29e2a67a4842d71121f1adc24f524f7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745227"
---
# <a name="first-er-function"></a><span data-ttu-id="c9431-103">Funzione ER FIRST</span><span class="sxs-lookup"><span data-stu-id="c9431-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c9431-104">La funzione `FIRST` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale elenco non è vuoto.</span><span class="sxs-lookup"><span data-stu-id="c9431-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="c9431-105">Se l'elenco è vuoto, questa funzione genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c9431-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="c9431-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9431-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="c9431-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c9431-107">Arguments</span></span>

<span data-ttu-id="c9431-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="c9431-108">`list`: *Record list*</span></span>

<span data-ttu-id="c9431-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="c9431-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c9431-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="c9431-110">Return values</span></span>

<span data-ttu-id="c9431-111">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="c9431-111">*Container (record)*</span></span>

<span data-ttu-id="c9431-112">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="c9431-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="c9431-113">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="c9431-113">Example 1</span></span>

<span data-ttu-id="c9431-114">L'espressione `FIRST(SPLIT("ABC",1)).Value` restituisce il valore del testo **"A"**.</span><span class="sxs-lookup"><span data-stu-id="c9431-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c9431-115">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="c9431-115">Example 2</span></span>

<span data-ttu-id="c9431-116">L'espressione `FIRST(SPLIT("",1)).Value` genera un'eccezione in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="c9431-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c9431-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c9431-117">Additional resources</span></span>

[<span data-ttu-id="c9431-118">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="c9431-118">List functions</span></span>](er-functions-category-list.md)
