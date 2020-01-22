---
title: Funzione ER CHAR
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CHAR della creazione di report elettronici (ER).
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
ms.openlocfilehash: d42afcf97690351763138fd9e16265aa104a6bc4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915742"
---
# <span data-ttu-id="fbdaf-103"><a name="CHAR">Funzione ER CHAR</a></span><span class="sxs-lookup"><span data-stu-id="fbdaf-103"><a name="CHAR">CHAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fbdaf-104">La funzione `CHAR` restituisce un valore *Stringa* che presenta un singolo carattere a cui si fa riferimento mediante il numero Unicode specificato.</span><span class="sxs-lookup"><span data-stu-id="fbdaf-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="fbdaf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbdaf-105">Syntax</span></span>

```
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="fbdaf-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fbdaf-106">Arguments</span></span>

<span data-ttu-id="fbdaf-107">`number`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="fbdaf-107">`number`: *Integer*</span></span>

<span data-ttu-id="fbdaf-108">Un numero che corrisponde a un singolo carattere previsto.</span><span class="sxs-lookup"><span data-stu-id="fbdaf-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="fbdaf-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="fbdaf-109">Return values</span></span>

<span data-ttu-id="fbdaf-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="fbdaf-110">*String*</span></span>

<span data-ttu-id="fbdaf-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="fbdaf-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fbdaf-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="fbdaf-112">Usage notes</span></span>

<span data-ttu-id="fbdaf-113">La stringa restituita dalla funzione dipende dalla codifica selezionata nell'elemento del formato **FILE** padre.</span><span class="sxs-lookup"><span data-stu-id="fbdaf-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="fbdaf-114">Per un elenco delle codifiche supportate, vedere [Classe di codifica](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="fbdaf-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="fbdaf-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbdaf-115">Example</span></span>

<span data-ttu-id="fbdaf-116">`CHAR (255)` restituisce **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="fbdaf-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fbdaf-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fbdaf-117">Additional resources</span></span>

[<span data-ttu-id="fbdaf-118">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="fbdaf-118">Text functions</span></span>](er-functions-category-text.md)
