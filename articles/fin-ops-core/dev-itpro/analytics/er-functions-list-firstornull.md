---
title: Funzione ER FIRSTORNULL
description: In questo argomento illustra l'utilizzo della funzione FIRSTORNULL della creazione di report elettronici (ER)
author: NickSelin
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
ms.openlocfilehash: 1ccc094fc468470ffc857c729b6d8402796785d7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753218"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="2efb3-103">Funzione ER FIRSTORNULL</span><span class="sxs-lookup"><span data-stu-id="2efb3-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2efb3-104">La funzione `FIRSTORNULL` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale record non è vuoto.</span><span class="sxs-lookup"><span data-stu-id="2efb3-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="2efb3-105">Se il record è vuoto, questa funzione restituisce un valore null *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="2efb3-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="2efb3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2efb3-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="2efb3-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2efb3-107">Arguments</span></span>

<span data-ttu-id="2efb3-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="2efb3-108">`list`: *Record list*</span></span>

<span data-ttu-id="2efb3-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="2efb3-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="2efb3-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="2efb3-110">Return values</span></span>

<span data-ttu-id="2efb3-111">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="2efb3-111">*Container (record)*</span></span>

<span data-ttu-id="2efb3-112">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="2efb3-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="2efb3-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="2efb3-113">Example</span></span>

<span data-ttu-id="2efb3-114">L'espressione `FIRSTORNULL(SPLIT("",1)).Value` restituisce una stringa vuota ( **""**).</span><span class="sxs-lookup"><span data-stu-id="2efb3-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2efb3-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2efb3-115">Additional resources</span></span>

[<span data-ttu-id="2efb3-116">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="2efb3-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]