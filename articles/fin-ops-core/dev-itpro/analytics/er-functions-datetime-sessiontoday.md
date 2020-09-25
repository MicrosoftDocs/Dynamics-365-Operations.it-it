---
title: Funzione ER SESSIONTODAY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SESSIONTODAY della creazione di report elettronici (ER).
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
ms.openlocfilehash: 2aa3d5e34e6dcd9b5d4a3fe3f21d7e3285adbcad
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745419"
---
# <a name="sessiontoday-er-function"></a><span data-ttu-id="a5e60-103">Funzione ER SESSIONTODAY</span><span class="sxs-lookup"><span data-stu-id="a5e60-103">SESSIONTODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5e60-104">La funzione `SESSIONTODAY` restituisce un valore *Data* che rappresenta la data corrente della sessione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a5e60-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5e60-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5e60-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="a5e60-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="a5e60-106">Return values</span></span>

<span data-ttu-id="a5e60-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="a5e60-107">*Date*</span></span>

<span data-ttu-id="a5e60-108">Il valore di data risultante.</span><span class="sxs-lookup"><span data-stu-id="a5e60-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="a5e60-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5e60-109">Example</span></span>

<span data-ttu-id="a5e60-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` restituisce la data della sessione dell'applicazione corrente, il 24 dicembre 2015, come stringa **"24-12-2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.</span><span class="sxs-lookup"><span data-stu-id="a5e60-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5e60-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a5e60-111">Additional resources</span></span>

[<span data-ttu-id="a5e60-112">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="a5e60-112">Date and time functions</span></span>](er-functions-category-datetime.md)
