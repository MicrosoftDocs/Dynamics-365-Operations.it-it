---
title: Funzione ER TODAY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TODAY della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 94ef15d1971287e8bf13944bc8f693b567950031
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411439"
---
# <a name=""></a><span data-ttu-id="52201-103"><a name="TODAY">Funzione ER TODAY</a></span><span class="sxs-lookup"><span data-stu-id="52201-103"><a name="TODAY">TODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52201-104">La funzione `TODAY` restituisce un valore *Data* che rappresenta la data corrente del server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="52201-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="52201-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52201-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="52201-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="52201-106">Return values</span></span>

<span data-ttu-id="52201-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="52201-107">*Date*</span></span>

<span data-ttu-id="52201-108">Il valore di data risultante.</span><span class="sxs-lookup"><span data-stu-id="52201-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="52201-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="52201-109">Example</span></span>

<span data-ttu-id="52201-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come stringa **"24-12-2015"**, in base al formato personalizzato specificato.</span><span class="sxs-lookup"><span data-stu-id="52201-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52201-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="52201-111">Additional resources</span></span>

[<span data-ttu-id="52201-112">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="52201-112">Date and time functions</span></span>](er-functions-category-datetime.md)
