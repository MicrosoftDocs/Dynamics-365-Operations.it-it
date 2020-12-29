---
title: Funzione ER REVERSE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione REVERSE della creazione di report elettronici (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 895d5f13f065b2188f245d081fa69e7e63555dde
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686442"
---
# <a name="reverse-er-function"></a><span data-ttu-id="bdc61-103">Funzione ER REVERSE</span><span class="sxs-lookup"><span data-stu-id="bdc61-103">REVERSE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bdc61-104">La funzione `REVERSE` restituisce l'elenco specificato come un valore *Elenco di record* in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="bdc61-104">The `REVERSE` function returns the specified list as a *Record list* value in reversed sort order.</span></span>

## <a name="syntax"></a><span data-ttu-id="bdc61-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdc61-105">Syntax</span></span>

```vb
REVERSE (list)
```

## <a name="arguments"></a><span data-ttu-id="bdc61-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="bdc61-106">Arguments</span></span>

<span data-ttu-id="bdc61-107">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="bdc61-107">`list`: *Record list*</span></span>

<span data-ttu-id="bdc61-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="bdc61-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="bdc61-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="bdc61-109">Return values</span></span>

<span data-ttu-id="bdc61-110">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="bdc61-110">*Record list*</span></span>

<span data-ttu-id="bdc61-111">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="bdc61-111">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="bdc61-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="bdc61-112">Example 1</span></span>

<span data-ttu-id="bdc61-113">Se si immette l'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("C|B|A", "|")`, l'espressione `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` restituisce il valore di testo **"C"**.</span><span class="sxs-lookup"><span data-stu-id="bdc61-113">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` returns the text value **"C"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="bdc61-114">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="bdc61-114">Example 2</span></span>

<span data-ttu-id="bdc61-115">Se **Vendor** è configurato come origine dati della creazione di report elettronici (ER) che fa riferimento alla tabella VendTable, l'espressione `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` restituisce un elenco di fornitori ordinato per nome in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="bdc61-115">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returns a list of vendors that is sorted by name in descending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bdc61-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="bdc61-116">Additional resources</span></span>

[<span data-ttu-id="bdc61-117">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="bdc61-117">List functions</span></span>](er-functions-category-list.md)
