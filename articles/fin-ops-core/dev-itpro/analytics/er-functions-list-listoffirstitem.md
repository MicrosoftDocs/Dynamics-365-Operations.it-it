---
title: Funzione ER LISTOFFIRSTITEM
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LISTOFFIRSTITEM della creazione di report elettronici (ER).
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
ms.openlocfilehash: 8cd48732280c9af0b89129a32b42285207f97fb7
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041977"
---
# <span data-ttu-id="4b849-103"><a name="LISTOFFIRSTITEM">Funzione ER LISTOFFIRSTITEM</a></span><span class="sxs-lookup"><span data-stu-id="4b849-103"><a name="LISTOFFIRSTITEM">LISTOFFIRSTITEM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b849-104">La funzione `LISTOFFIRSTITEM` restituisce un valore *Elenco di record* costituito solo dal primo record dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="4b849-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b849-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b849-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="4b849-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4b849-106">Arguments</span></span>

<span data-ttu-id="4b849-107">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="4b849-107">`list`: *Record list*</span></span>

<span data-ttu-id="4b849-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="4b849-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="4b849-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="4b849-109">Return values</span></span>

<span data-ttu-id="4b849-110">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="4b849-110">*Record list*</span></span>

<span data-ttu-id="4b849-111">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="4b849-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="4b849-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b849-112">Example</span></span>

<span data-ttu-id="4b849-113">L'espressione `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` restituisce il valore del testo **"A"**.</span><span class="sxs-lookup"><span data-stu-id="4b849-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b849-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4b849-114">Additional resources</span></span>

[<span data-ttu-id="4b849-115">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="4b849-115">List functions</span></span>](er-functions-category-list.md)
