---
title: Funzione ER DAYS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DAYS della creazione di report elettronici (ER).
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
ms.openlocfilehash: 310359a29a506d69d1f34aaa710a82b0f2ea528e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746893"
---
# <a name="days-er-function"></a><span data-ttu-id="8ba7b-103">Funzione ER DAYS</span><span class="sxs-lookup"><span data-stu-id="8ba7b-103">DAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ba7b-104">La funzione `DAYS` restituisce un valore *Intero* che è la rappresentazione del numero di giorni tra una data specificata e una seconda data specificata.</span><span class="sxs-lookup"><span data-stu-id="8ba7b-104">The `DAYS` function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="8ba7b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ba7b-105">Syntax</span></span>

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a><span data-ttu-id="8ba7b-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8ba7b-106">Arguments</span></span>

<span data-ttu-id="8ba7b-107">`date 1`: *Data*</span><span class="sxs-lookup"><span data-stu-id="8ba7b-107">`date 1`: *Date*</span></span>

<span data-ttu-id="8ba7b-108">Un valore di data che rappresenta la data di inizio per il calcolo del numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="8ba7b-108">A date value that represents the start date for the calculation of the number of days.</span></span>

<span data-ttu-id="8ba7b-109">`date 2`: *Data*</span><span class="sxs-lookup"><span data-stu-id="8ba7b-109">`date 2`: *Date*</span></span>

<span data-ttu-id="8ba7b-110">Un valore di data che rappresenta la data di fine per il calcolo del numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="8ba7b-110">A date value that represents the end date for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="8ba7b-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="8ba7b-111">Return values</span></span>

<span data-ttu-id="8ba7b-112">*Intero*</span><span class="sxs-lookup"><span data-stu-id="8ba7b-112">*Integer*</span></span>

<span data-ttu-id="8ba7b-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="8ba7b-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8ba7b-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="8ba7b-114">Usage notes</span></span>

<span data-ttu-id="8ba7b-115">La funzione `DAYS` restituisce un valore positivo quando la prima data è successiva alla seconda data, restituisce **0** (zero) quando la prima data corrisponde alla seconda data o restituisce un valore negativo quando la prima data è antecedente alla seconda data.</span><span class="sxs-lookup"><span data-stu-id="8ba7b-115">The `DAYS` function returns a positive value when the first date is later than the second date, it returns **0** (zero) when the first date equals the second date, and it returns a negative value when the first date is earlier than the second date.</span></span>

## <a name="example"></a><span data-ttu-id="8ba7b-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ba7b-116">Example</span></span>

<span data-ttu-id="8ba7b-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` restituisce **-1**.</span><span class="sxs-lookup"><span data-stu-id="8ba7b-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returns **-1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8ba7b-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8ba7b-118">Additional resources</span></span>

[<span data-ttu-id="8ba7b-119">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="8ba7b-119">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]