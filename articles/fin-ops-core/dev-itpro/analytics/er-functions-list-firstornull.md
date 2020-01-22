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
ms.openlocfilehash: 075b2e064641061adf5404591a784311b6d28697
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917329"
---
# <span data-ttu-id="3cb24-103"><a name="FIRSTORNULL">Funzione ER FIRSTORNULL</a></span><span class="sxs-lookup"><span data-stu-id="3cb24-103"><a name="FIRSTORNULL">FIRSTORNULL ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3cb24-104">La funzione `FIRSTORNULL` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale record non è vuoto.</span><span class="sxs-lookup"><span data-stu-id="3cb24-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="3cb24-105">Se il record è vuoto, questa funzione restituisce un valore null *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="3cb24-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="3cb24-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3cb24-106">Syntax</span></span>

```
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="3cb24-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3cb24-107">Arguments</span></span>

<span data-ttu-id="3cb24-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="3cb24-108">`list`: *Record list*</span></span>

<span data-ttu-id="3cb24-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="3cb24-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="3cb24-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="3cb24-110">Return values</span></span>

<span data-ttu-id="3cb24-111">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="3cb24-111">*Container (record)*</span></span>

<span data-ttu-id="3cb24-112">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="3cb24-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="3cb24-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="3cb24-113">Example</span></span>

<span data-ttu-id="3cb24-114">L'espressione `FIRSTORNULL(SPLIT("",1)).Value` restituisce una stringa vuota ( **""**).</span><span class="sxs-lookup"><span data-stu-id="3cb24-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3cb24-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3cb24-115">Additional resources</span></span>

[<span data-ttu-id="3cb24-116">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="3cb24-116">List functions</span></span>](er-functions-category-list.md)
