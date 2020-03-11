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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a6134ae7eb1a8044cf906f2a8d02eb153522a6cf
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041931"
---
# <span data-ttu-id="632f0-103"><a name="REVERSE">Funzione ER REVERSE</a></span><span class="sxs-lookup"><span data-stu-id="632f0-103"><a name="REVERSE">REVERSE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="632f0-104">La funzione `REVERSE` restituisce l'elenco specificato come un valore *Elenco di record* in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="632f0-104">The `REVERSE` function returns the specified list as a *Record list* value in reversed sort order.</span></span>

## <a name="syntax"></a><span data-ttu-id="632f0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="632f0-105">Syntax</span></span>

```vb
REVERSE (list)
```

## <a name="arguments"></a><span data-ttu-id="632f0-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="632f0-106">Arguments</span></span>

<span data-ttu-id="632f0-107">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="632f0-107">`list`: *Record list*</span></span>

<span data-ttu-id="632f0-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="632f0-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="632f0-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="632f0-109">Return values</span></span>

<span data-ttu-id="632f0-110">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="632f0-110">*Record list*</span></span>

<span data-ttu-id="632f0-111">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="632f0-111">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="632f0-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="632f0-112">Example 1</span></span>

<span data-ttu-id="632f0-113">Se si immette l'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("C|B|A", "|")`, l'espressione `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` restituisce il valore di testo **"C"**.</span><span class="sxs-lookup"><span data-stu-id="632f0-113">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` returns the text value **"C"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="632f0-114">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="632f0-114">Example 2</span></span>

<span data-ttu-id="632f0-115">Se **Vendor** è configurato come origine dati della creazione di report elettronici (ER) che fa riferimento alla tabella VendTable, l'espressione `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` restituisce un elenco di fornitori ordinato per nome in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="632f0-115">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returns a list of vendors that is sorted by name in descending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="632f0-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="632f0-116">Additional resources</span></span>

[<span data-ttu-id="632f0-117">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="632f0-117">List functions</span></span>](er-functions-category-list.md)
