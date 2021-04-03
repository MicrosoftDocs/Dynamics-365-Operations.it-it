---
title: Funzione ER SESSIONTODAY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SESSIONTODAY della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: e6ad28e642fcfae3cfa2692a4e41b99fae7fc9df
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561352"
---
# <a name="sessiontoday-er-function"></a><span data-ttu-id="3dded-103">Funzione ER SESSIONTODAY</span><span class="sxs-lookup"><span data-stu-id="3dded-103">SESSIONTODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3dded-104">La funzione `SESSIONTODAY` restituisce un valore *Data* che rappresenta la data corrente della sessione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3dded-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="3dded-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3dded-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="3dded-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="3dded-106">Return values</span></span>

<span data-ttu-id="3dded-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="3dded-107">*Date*</span></span>

<span data-ttu-id="3dded-108">Il valore di data risultante.</span><span class="sxs-lookup"><span data-stu-id="3dded-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="3dded-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="3dded-109">Example</span></span>

<span data-ttu-id="3dded-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` restituisce la data della sessione dell'applicazione corrente, il 24 dicembre 2015, come stringa **"24-12-2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.</span><span class="sxs-lookup"><span data-stu-id="3dded-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3dded-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3dded-111">Additional resources</span></span>

[<span data-ttu-id="3dded-112">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="3dded-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]