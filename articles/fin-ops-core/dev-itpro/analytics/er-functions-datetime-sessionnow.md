---
title: Funzione ER SESSIONNOW
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SESSIONNOW della creazione di report elettronici (ER).
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
ms.openlocfilehash: 00c41564b18eed477e1cefb0bc3bb2bca3fa6fdd
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745467"
---
# <a name="sessionnow-er-function"></a><span data-ttu-id="2ac4f-103">Funzione ER SESSIONNOW</span><span class="sxs-lookup"><span data-stu-id="2ac4f-103">SESSIONNOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ac4f-104">La funzione `SESSIONNOW` restituisce un valore *DateTime* che rappresenta la data e l'ora correnti della sessione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2ac4f-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="2ac4f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ac4f-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="2ac4f-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="2ac4f-106">Return values</span></span>

<span data-ttu-id="2ac4f-107">*Data/Ora*</span><span class="sxs-lookup"><span data-stu-id="2ac4f-107">*DateTime*</span></span>

<span data-ttu-id="2ac4f-108">Il valore di data/ora risultante.</span><span class="sxs-lookup"><span data-stu-id="2ac4f-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="2ac4f-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ac4f-109">Example</span></span>

<span data-ttu-id="2ac4f-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` restituisce la data/ora della sessione dell'applicazione corrente, il 24 dicembre 2015, come **"24.12.2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.</span><span class="sxs-lookup"><span data-stu-id="2ac4f-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2ac4f-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2ac4f-111">Additional resources</span></span>

[<span data-ttu-id="2ac4f-112">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="2ac4f-112">Date and time functions</span></span>](er-functions-category-datetime.md)
