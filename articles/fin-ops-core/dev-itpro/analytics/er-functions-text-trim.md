---
title: Funzione ER TRIM
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TRIM della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: c95663f1aacaf93c1c4bfc8d36d9515f495bf61e
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040827"
---
# <span data-ttu-id="3abe8-103"><a name="TRIM">Funzione ER TRIM</a></span><span class="sxs-lookup"><span data-stu-id="3abe8-103"><a name="TRIM">TRIM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3abe8-104">La funzione `TRIM` restituisce la stringa di testo specificata come un valore *Stringa* dopo il troncamento degli spazi iniziali e finali e la rimozione di più spazi tra le parole.</span><span class="sxs-lookup"><span data-stu-id="3abe8-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="3abe8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3abe8-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="3abe8-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3abe8-106">Arguments</span></span>

<span data-ttu-id="3abe8-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="3abe8-107">`text`: *String*</span></span>

<span data-ttu-id="3abe8-108">Il percorso valido di un'origine dati del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="3abe8-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="3abe8-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="3abe8-109">Return values</span></span>

<span data-ttu-id="3abe8-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="3abe8-110">*String*</span></span>

<span data-ttu-id="3abe8-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="3abe8-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="3abe8-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="3abe8-112">Example</span></span>

<span data-ttu-id="3abe8-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` restituisce **"Sample text"**.</span><span class="sxs-lookup"><span data-stu-id="3abe8-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3abe8-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3abe8-114">Additional resources</span></span>

[<span data-ttu-id="3abe8-115">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="3abe8-115">Text functions</span></span>](er-functions-category-text.md)
