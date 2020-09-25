---
title: Funzione ER EMPTYRECORD
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione EMPTYRECORD della creazione di report elettronici (ER).
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
ms.openlocfilehash: 2e46fcef3d53483b782ac39a0661fc0edc8d861c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743952"
---
# <a name="emptyrecord-er-function"></a><span data-ttu-id="190c0-103">Funzione ER EMPTYRECORD</span><span class="sxs-lookup"><span data-stu-id="190c0-103">EMPTYRECORD ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="190c0-104">La funzione `EMPTYRECORD` restituisce un valore *Contenitore (record)* nullo che ha la stessa struttura dell'elenco di record o del record specificato.</span><span class="sxs-lookup"><span data-stu-id="190c0-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="190c0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="190c0-105">Syntax</span></span>

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="190c0-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="190c0-106">Arguments</span></span>

<span data-ttu-id="190c0-107">`list`: *Elenco di record* o *Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="190c0-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="190c0-108">Il percorso valido di un elemento di un'origine dati del tipo *Elenco di record* o *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="190c0-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="190c0-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="190c0-109">Return values</span></span>

<span data-ttu-id="190c0-110">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="190c0-110">*Container (record)*</span></span>

<span data-ttu-id="190c0-111">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="190c0-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="190c0-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="190c0-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="190c0-113">Un record null è un record in cui il valore di tutti i campi è vuoto.</span><span class="sxs-lookup"><span data-stu-id="190c0-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="190c0-114">Un valore vuoto è **0** (zero) per i numeri, stringa vuota per le stringhe e così via.</span><span class="sxs-lookup"><span data-stu-id="190c0-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="190c0-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="190c0-115">Example</span></span>

<span data-ttu-id="190c0-116">`EMPTYRECORD (SPLIT ("abc", 1))` restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="190c0-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="190c0-117">Per ulteriori informazioni, vedere [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="190c0-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="190c0-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="190c0-118">Additional resources</span></span>

[<span data-ttu-id="190c0-119">Funzioni di record</span><span class="sxs-lookup"><span data-stu-id="190c0-119">Record functions</span></span>](er-functions-category-record.md)
