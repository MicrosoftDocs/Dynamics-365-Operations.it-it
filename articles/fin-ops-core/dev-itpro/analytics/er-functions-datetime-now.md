---
title: Funzione ER NOW
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NOW della creazione di report elettronici (ER).
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
ms.openlocfilehash: cffb23afa4cb347d2840b099b0b49a71150d87d8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917559"
---
# <span data-ttu-id="79f29-103"><a name="NOW">Funzione ER NOW</a></span><span class="sxs-lookup"><span data-stu-id="79f29-103"><a name="NOW">NOW ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="79f29-104">La funzione `NOW` restituisce un valore *DateTime* che rappresenta la data e l'ora correnti del server delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="79f29-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="79f29-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79f29-105">Syntax</span></span>

```
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="79f29-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="79f29-106">Return values</span></span>

<span data-ttu-id="79f29-107">*Data/Ora*</span><span class="sxs-lookup"><span data-stu-id="79f29-107">*DateTime*</span></span>

<span data-ttu-id="79f29-108">Il valore di data/ora risultante.</span><span class="sxs-lookup"><span data-stu-id="79f29-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="79f29-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="79f29-109">Example</span></span>

<span data-ttu-id="79f29-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come **"24-12-2015"**, in base al formato personalizzato specificato.</span><span class="sxs-lookup"><span data-stu-id="79f29-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="79f29-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="79f29-111">Additional resources</span></span>

[<span data-ttu-id="79f29-112">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="79f29-112">Date and time functions</span></span>](er-functions-category-datetime.md)
