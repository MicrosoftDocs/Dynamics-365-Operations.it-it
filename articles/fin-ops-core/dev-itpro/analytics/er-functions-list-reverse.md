---
title: Funzione ER REVERSE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione REVERSE della creazione di report elettronici (ER).
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
ms.openlocfilehash: 746a736c8797c1c1c5bd71d7d803be4212984595
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755206"
---
# <a name="reverse-er-function"></a><span data-ttu-id="3468c-103">Funzione ER REVERSE</span><span class="sxs-lookup"><span data-stu-id="3468c-103">REVERSE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3468c-104">La funzione `REVERSE` restituisce l'elenco specificato come un valore *Elenco di record* in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="3468c-104">The `REVERSE` function returns the specified list as a *Record list* value in reversed sort order.</span></span>

## <a name="syntax"></a><span data-ttu-id="3468c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3468c-105">Syntax</span></span>

```vb
REVERSE (list)
```

## <a name="arguments"></a><span data-ttu-id="3468c-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3468c-106">Arguments</span></span>

<span data-ttu-id="3468c-107">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="3468c-107">`list`: *Record list*</span></span>

<span data-ttu-id="3468c-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="3468c-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="3468c-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="3468c-109">Return values</span></span>

<span data-ttu-id="3468c-110">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="3468c-110">*Record list*</span></span>

<span data-ttu-id="3468c-111">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="3468c-111">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="3468c-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="3468c-112">Example 1</span></span>

<span data-ttu-id="3468c-113">Se si immette l'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("C|B|A", "|")`, l'espressione `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` restituisce il valore di testo **"C"**.</span><span class="sxs-lookup"><span data-stu-id="3468c-113">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` returns the text value **"C"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="3468c-114">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="3468c-114">Example 2</span></span>

<span data-ttu-id="3468c-115">Se **Vendor** è configurato come origine dati della creazione di report elettronici (ER) che fa riferimento alla tabella VendTable, l'espressione `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` restituisce un elenco di fornitori ordinato per nome in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="3468c-115">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returns a list of vendors that is sorted by name in descending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3468c-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3468c-116">Additional resources</span></span>

[<span data-ttu-id="3468c-117">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="3468c-117">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]