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
ms.openlocfilehash: e2ee153c1dde99810a78ed15c7505fa705088797
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745443"
---
# <a name="today-er-function"></a><span data-ttu-id="c99ca-103">Funzione ER TODAY</span><span class="sxs-lookup"><span data-stu-id="c99ca-103">TODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c99ca-104">La funzione `TODAY` restituisce un valore *Data* che rappresenta la data corrente del server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c99ca-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="c99ca-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c99ca-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="c99ca-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="c99ca-106">Return values</span></span>

<span data-ttu-id="c99ca-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="c99ca-107">*Date*</span></span>

<span data-ttu-id="c99ca-108">Il valore di data risultante.</span><span class="sxs-lookup"><span data-stu-id="c99ca-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="c99ca-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c99ca-109">Example</span></span>

<span data-ttu-id="c99ca-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come stringa **"24-12-2015"**, in base al formato personalizzato specificato.</span><span class="sxs-lookup"><span data-stu-id="c99ca-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c99ca-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c99ca-111">Additional resources</span></span>

[<span data-ttu-id="c99ca-112">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="c99ca-112">Date and time functions</span></span>](er-functions-category-datetime.md)
