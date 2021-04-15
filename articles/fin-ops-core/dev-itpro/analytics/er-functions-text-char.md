---
title: Funzione ER CHAR
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CHAR della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: a621328817171be7df0622507c84f5c6f6fe90a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746437"
---
# <a name="char-er-function"></a><span data-ttu-id="df2ae-103">Funzione ER CHAR</span><span class="sxs-lookup"><span data-stu-id="df2ae-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="df2ae-104">La funzione `CHAR` restituisce un valore *Stringa* che presenta un singolo carattere a cui si fa riferimento mediante il numero Unicode specificato.</span><span class="sxs-lookup"><span data-stu-id="df2ae-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="df2ae-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df2ae-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="df2ae-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="df2ae-106">Arguments</span></span>

<span data-ttu-id="df2ae-107">`number`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="df2ae-107">`number`: *Integer*</span></span>

<span data-ttu-id="df2ae-108">Un numero che corrisponde a un singolo carattere previsto.</span><span class="sxs-lookup"><span data-stu-id="df2ae-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="df2ae-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="df2ae-109">Return values</span></span>

<span data-ttu-id="df2ae-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="df2ae-110">*String*</span></span>

<span data-ttu-id="df2ae-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="df2ae-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="df2ae-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="df2ae-112">Usage notes</span></span>

<span data-ttu-id="df2ae-113">La stringa restituita dalla funzione dipende dalla codifica selezionata nell'elemento del formato **FILE** padre.</span><span class="sxs-lookup"><span data-stu-id="df2ae-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="df2ae-114">Per un elenco delle codifiche supportate, vedere [Classe di codifica](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="df2ae-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="df2ae-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="df2ae-115">Example</span></span>

<span data-ttu-id="df2ae-116">`CHAR (255)` restituisce **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="df2ae-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df2ae-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="df2ae-117">Additional resources</span></span>

[<span data-ttu-id="df2ae-118">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="df2ae-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]