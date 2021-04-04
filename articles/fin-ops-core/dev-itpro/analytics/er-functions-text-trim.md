---
title: Funzione ER TRIM
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TRIM della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: b671ef72a3558c17fb16db939770394b225656da
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560038"
---
# <a name="trim-er-function"></a><span data-ttu-id="8fa83-103">Funzione ER TRIM</span><span class="sxs-lookup"><span data-stu-id="8fa83-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8fa83-104">La funzione `TRIM` restituisce la stringa di testo specificata come un valore *Stringa* dopo il troncamento degli spazi iniziali e finali e la rimozione di più spazi tra le parole.</span><span class="sxs-lookup"><span data-stu-id="8fa83-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="8fa83-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fa83-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="8fa83-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8fa83-106">Arguments</span></span>

<span data-ttu-id="8fa83-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="8fa83-107">`text`: *String*</span></span>

<span data-ttu-id="8fa83-108">Il percorso valido di un'origine dati del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="8fa83-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="8fa83-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="8fa83-109">Return values</span></span>

<span data-ttu-id="8fa83-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="8fa83-110">*String*</span></span>

<span data-ttu-id="8fa83-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="8fa83-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="8fa83-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8fa83-112">Example</span></span>

<span data-ttu-id="8fa83-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` restituisce **"Sample text"**.</span><span class="sxs-lookup"><span data-stu-id="8fa83-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8fa83-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8fa83-114">Additional resources</span></span>

[<span data-ttu-id="8fa83-115">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="8fa83-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]