---
title: Funzione ER UPPER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione UPPER della creazione di report elettronici (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3e594138ef8e28f1b3aaf333026fa8f9e55cca0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688343"
---
# <a name="upper-er-function"></a><span data-ttu-id="11cb0-103">Funzione ER UPPER</span><span class="sxs-lookup"><span data-stu-id="11cb0-103">UPPER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11cb0-104">La funzione `UPPER` restituisce la stringa di testo specificata come valore *Stringa* dopo che è stata convertita in lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="11cb0-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="11cb0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11cb0-105">Syntax</span></span>

```vb
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="11cb0-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="11cb0-106">Arguments</span></span>

<span data-ttu-id="11cb0-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="11cb0-107">`text`: *String*</span></span>

<span data-ttu-id="11cb0-108">Il percorso valido di un'origine dati del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="11cb0-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="11cb0-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="11cb0-109">Return values</span></span>

<span data-ttu-id="11cb0-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="11cb0-110">*String*</span></span>

<span data-ttu-id="11cb0-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="11cb0-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="11cb0-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="11cb0-112">Example</span></span>

<span data-ttu-id="11cb0-113">`UPPER ("Sample")` restituisce **"SAMPLE"**.</span><span class="sxs-lookup"><span data-stu-id="11cb0-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11cb0-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="11cb0-114">Additional resources</span></span>

[<span data-ttu-id="11cb0-115">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="11cb0-115">Text functions</span></span>](er-functions-category-text.md)
