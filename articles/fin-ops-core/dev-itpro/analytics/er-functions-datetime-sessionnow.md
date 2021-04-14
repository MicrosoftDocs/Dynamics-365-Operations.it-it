---
title: Funzione ER SESSIONNOW
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SESSIONNOW della creazione di report elettronici (ER).
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
ms.openlocfilehash: 47b88a1ca0ea9fd09c2a82963901d9ace78891bb
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746796"
---
# <a name="sessionnow-er-function"></a><span data-ttu-id="f8691-103">Funzione ER SESSIONNOW</span><span class="sxs-lookup"><span data-stu-id="f8691-103">SESSIONNOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8691-104">La funzione `SESSIONNOW` restituisce un valore *DateTime* che rappresenta la data e l'ora correnti della sessione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f8691-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="f8691-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8691-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="f8691-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="f8691-106">Return values</span></span>

<span data-ttu-id="f8691-107">*Data/Ora*</span><span class="sxs-lookup"><span data-stu-id="f8691-107">*DateTime*</span></span>

<span data-ttu-id="f8691-108">Il valore di data/ora risultante.</span><span class="sxs-lookup"><span data-stu-id="f8691-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="f8691-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8691-109">Example</span></span>

<span data-ttu-id="f8691-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` restituisce la data/ora della sessione dell'applicazione corrente, il 24 dicembre 2015, come **"24.12.2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.</span><span class="sxs-lookup"><span data-stu-id="f8691-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f8691-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f8691-111">Additional resources</span></span>

[<span data-ttu-id="f8691-112">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="f8691-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]