---
title: Funzione ER NULLDATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NULLDATE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: edf43cc19636f51387504a7d9da73d757d96e558
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744289"
---
# <a name="nulldate-er-function"></a><span data-ttu-id="a8f04-103">Funzione ER NULLDATE</span><span class="sxs-lookup"><span data-stu-id="a8f04-103">NULLDATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8f04-104">La funzione `NULLDATE` restituisce un valore *Data* che rappresenta la data **null** (1 gennaio 1900).</span><span class="sxs-lookup"><span data-stu-id="a8f04-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="a8f04-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8f04-105">Syntax</span></span>

```vb
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="a8f04-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="a8f04-106">Return values</span></span>

<span data-ttu-id="a8f04-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="a8f04-107">*Date*</span></span>

<span data-ttu-id="a8f04-108">Il valore di data risultante.</span><span class="sxs-lookup"><span data-stu-id="a8f04-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="a8f04-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="a8f04-109">Example 1</span></span>

<span data-ttu-id="a8f04-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` restituisce la data **null**, 1 gennaio 1900, come **"1900-01-01"**, basata sul formato personalizzato specificato.</span><span class="sxs-lookup"><span data-stu-id="a8f04-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="a8f04-111">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="a8f04-111">Example 2</span></span>

<span data-ttu-id="a8f04-112">L'espressione `IF( Invoice.DocumentDate = NULLDATE(), true, false)` restituisce **True** quando il valore del campo **DocumentDate** equivale alla data **null**.</span><span class="sxs-lookup"><span data-stu-id="a8f04-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="a8f04-113">In questo esempio, **Invoice** è l'origine dati della creazione di report elettronici (ER) del tipo **Finance and Operations/Tabella** e fa riferimento alla tabella CustInvoiceJour.</span><span class="sxs-lookup"><span data-stu-id="a8f04-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a8f04-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a8f04-114">Additional resources</span></span>

[<span data-ttu-id="a8f04-115">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="a8f04-115">Date and time functions</span></span>](er-functions-category-datetime.md)
