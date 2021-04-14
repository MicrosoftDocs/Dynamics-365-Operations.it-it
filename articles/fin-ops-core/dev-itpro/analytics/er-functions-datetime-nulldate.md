---
title: Funzione ER NULLDATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NULLDATE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 6ac8da3f18c7793512685d52dd64a9bd55bfb8fc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746845"
---
# <a name="nulldate-er-function"></a><span data-ttu-id="2e523-103">Funzione ER NULLDATE</span><span class="sxs-lookup"><span data-stu-id="2e523-103">NULLDATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e523-104">La funzione `NULLDATE` restituisce un valore *Data* che rappresenta la data **null** (1 gennaio 1900).</span><span class="sxs-lookup"><span data-stu-id="2e523-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="2e523-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e523-105">Syntax</span></span>

```vb
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="2e523-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="2e523-106">Return values</span></span>

<span data-ttu-id="2e523-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="2e523-107">*Date*</span></span>

<span data-ttu-id="2e523-108">Il valore di data risultante.</span><span class="sxs-lookup"><span data-stu-id="2e523-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="2e523-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="2e523-109">Example 1</span></span>

<span data-ttu-id="2e523-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` restituisce la data **null**, 1 gennaio 1900, come **"1900-01-01"**, basata sul formato personalizzato specificato.</span><span class="sxs-lookup"><span data-stu-id="2e523-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="2e523-111">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="2e523-111">Example 2</span></span>

<span data-ttu-id="2e523-112">L'espressione `IF( Invoice.DocumentDate = NULLDATE(), true, false)` restituisce **True** quando il valore del campo **DocumentDate** equivale alla data **null**.</span><span class="sxs-lookup"><span data-stu-id="2e523-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="2e523-113">In questo esempio, **Invoice** è l'origine dati della creazione di report elettronici (ER) del tipo **Finance and Operations/Tabella** e fa riferimento alla tabella CustInvoiceJour.</span><span class="sxs-lookup"><span data-stu-id="2e523-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2e523-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2e523-114">Additional resources</span></span>

[<span data-ttu-id="2e523-115">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="2e523-115">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]