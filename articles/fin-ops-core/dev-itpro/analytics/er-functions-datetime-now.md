---
title: Funzione ER NOW
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NOW della creazione di report elettronici (ER).
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
ms.openlocfilehash: c93aa2a0e3f6aa07ab9e843d3c5f11c5265e8c40
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746869"
---
# <a name="now-er-function"></a><span data-ttu-id="2c8a0-103">Funzione ER NOW</span><span class="sxs-lookup"><span data-stu-id="2c8a0-103">NOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c8a0-104">La funzione `NOW` restituisce un valore *DateTime* che rappresenta la data e l'ora correnti del server delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2c8a0-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c8a0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c8a0-105">Syntax</span></span>

```vb
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="2c8a0-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="2c8a0-106">Return values</span></span>

<span data-ttu-id="2c8a0-107">*Data/Ora*</span><span class="sxs-lookup"><span data-stu-id="2c8a0-107">*DateTime*</span></span>

<span data-ttu-id="2c8a0-108">Il valore di data/ora risultante.</span><span class="sxs-lookup"><span data-stu-id="2c8a0-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="2c8a0-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c8a0-109">Example</span></span>

<span data-ttu-id="2c8a0-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come **"24-12-2015"**, in base al formato personalizzato specificato.</span><span class="sxs-lookup"><span data-stu-id="2c8a0-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2c8a0-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2c8a0-111">Additional resources</span></span>

[<span data-ttu-id="2c8a0-112">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="2c8a0-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]