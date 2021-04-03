---
title: Funzione ER FIRSTORNULL
description: In questo argomento illustra l'utilizzo della funzione FIRSTORNULL della creazione di report elettronici (ER)
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 53284333507ef1264d3eb66b0c7141eb69f32392
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564627"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="03f06-103">Funzione ER FIRSTORNULL</span><span class="sxs-lookup"><span data-stu-id="03f06-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03f06-104">La funzione `FIRSTORNULL` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale record non è vuoto.</span><span class="sxs-lookup"><span data-stu-id="03f06-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="03f06-105">Se il record è vuoto, questa funzione restituisce un valore null *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="03f06-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="03f06-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03f06-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="03f06-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="03f06-107">Arguments</span></span>

<span data-ttu-id="03f06-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="03f06-108">`list`: *Record list*</span></span>

<span data-ttu-id="03f06-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="03f06-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="03f06-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="03f06-110">Return values</span></span>

<span data-ttu-id="03f06-111">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="03f06-111">*Container (record)*</span></span>

<span data-ttu-id="03f06-112">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="03f06-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="03f06-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="03f06-113">Example</span></span>

<span data-ttu-id="03f06-114">L'espressione `FIRSTORNULL(SPLIT("",1)).Value` restituisce una stringa vuota ( **""**).</span><span class="sxs-lookup"><span data-stu-id="03f06-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="03f06-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="03f06-115">Additional resources</span></span>

[<span data-ttu-id="03f06-116">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="03f06-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]