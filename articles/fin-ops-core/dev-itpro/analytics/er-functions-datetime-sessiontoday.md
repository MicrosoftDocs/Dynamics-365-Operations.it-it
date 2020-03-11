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
ms.openlocfilehash: 483ff46a27068bc2d70c80a848f0329861c914b3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042270"
---
# <span data-ttu-id="5ef20-103"><a name="SESSIONTODAY">Funzione ER SESSIONTODAY</a></span><span class="sxs-lookup"><span data-stu-id="5ef20-103"><a name="SESSIONTODAY">SESSIONTODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ef20-104">La funzione `SESSIONTODAY` restituisce un valore *Data* che rappresenta la data corrente della sessione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5ef20-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ef20-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ef20-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="5ef20-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="5ef20-106">Return values</span></span>

<span data-ttu-id="5ef20-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="5ef20-107">*Date*</span></span>

<span data-ttu-id="5ef20-108">Il valore di data risultante.</span><span class="sxs-lookup"><span data-stu-id="5ef20-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="5ef20-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ef20-109">Example</span></span>

<span data-ttu-id="5ef20-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` restituisce la data della sessione dell'applicazione corrente, il 24 dicembre 2015, come stringa **"24-12-2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.</span><span class="sxs-lookup"><span data-stu-id="5ef20-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ef20-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5ef20-111">Additional resources</span></span>

[<span data-ttu-id="5ef20-112">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="5ef20-112">Date and time functions</span></span>](er-functions-category-datetime.md)
