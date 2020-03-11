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
ms.openlocfilehash: 86c8a0ae21ffeb6268efbbd198f7c709c2ad54f6
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042115"
---
# <span data-ttu-id="fbca4-103"><a name="FIRSTORNULL">Funzione ER FIRSTORNULL</a></span><span class="sxs-lookup"><span data-stu-id="fbca4-103"><a name="FIRSTORNULL">FIRSTORNULL ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fbca4-104">La funzione `FIRSTORNULL` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale record non è vuoto.</span><span class="sxs-lookup"><span data-stu-id="fbca4-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="fbca4-105">Se il record è vuoto, questa funzione restituisce un valore null *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="fbca4-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="fbca4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbca4-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="fbca4-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fbca4-107">Arguments</span></span>

<span data-ttu-id="fbca4-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="fbca4-108">`list`: *Record list*</span></span>

<span data-ttu-id="fbca4-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="fbca4-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="fbca4-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="fbca4-110">Return values</span></span>

<span data-ttu-id="fbca4-111">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="fbca4-111">*Container (record)*</span></span>

<span data-ttu-id="fbca4-112">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="fbca4-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="fbca4-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbca4-113">Example</span></span>

<span data-ttu-id="fbca4-114">L'espressione `FIRSTORNULL(SPLIT("",1)).Value` restituisce una stringa vuota ( **""**).</span><span class="sxs-lookup"><span data-stu-id="fbca4-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fbca4-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbca4-115">Additional resources</span></span>

[<span data-ttu-id="fbca4-116">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="fbca4-116">List functions</span></span>](er-functions-category-list.md)
