---
title: Funzione ER DATETODATETIME
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DATETODATETIME della creazione di report elettronici (ER).
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
ms.openlocfilehash: bb90c58544eeba804cd39542cc70fab3b840af80
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746965"
---
# <a name="datetodatetime-er-function"></a><span data-ttu-id="36cec-103">Funzione ER DATETODATETIME</span><span class="sxs-lookup"><span data-stu-id="36cec-103">DATETODATETIME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36cec-104">La funzione `DATETODATETIME` restituisce un valore *DateTime* che viene convertito da un determinato valore di data a un valore di data/ora in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="36cec-104">The `DATETODATETIME` function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="36cec-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36cec-105">Syntax</span></span>

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a><span data-ttu-id="36cec-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="36cec-106">Arguments</span></span>

<span data-ttu-id="36cec-107">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="36cec-107">`date`: *Date*</span></span>

<span data-ttu-id="36cec-108">Un valore di data che rappresenta la data da convertire.</span><span class="sxs-lookup"><span data-stu-id="36cec-108">A date value that represents the date to convert.</span></span>

## <a name="return-values"></a><span data-ttu-id="36cec-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="36cec-109">Return values</span></span>

<span data-ttu-id="36cec-110">*Data/Ora*</span><span class="sxs-lookup"><span data-stu-id="36cec-110">*DateTime*</span></span>

<span data-ttu-id="36cec-111">Il valore di data/ora risultante.</span><span class="sxs-lookup"><span data-stu-id="36cec-111">The resulting date/time value.</span></span>

## <a name="example-1"></a><span data-ttu-id="36cec-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="36cec-112">Example 1</span></span>

<span data-ttu-id="36cec-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` restituisce la data della sessione corrente di Microsoft Dynamics 365 Finance, 24 dicembre 2015, come **12/24/2015 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="36cec-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` returns the date of the current Microsoft Dynamics 365 Finance session, December 24, 2015, as **12/24/2015 12:00:00 AM**.</span></span> <span data-ttu-id="36cec-114">In questo esempio, **CompInfo** è l'origine dati della creazione di report elettronici (ER) del tipo **Finance and Operations/Tabella** e fa riferimento alla tabella CompanyInfo.</span><span class="sxs-lookup"><span data-stu-id="36cec-114">In this example, **CompInfo** is an Electronic reporting (ER) data source of the **Finance and Operations/Table** type, and it refers to the CompanyInfo table.</span></span>

## <a name="example-2"></a><span data-ttu-id="36cec-115">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="36cec-115">Example 2</span></span>

<span data-ttu-id="36cec-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` restituisce il valore data/ora **11/12/2019 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="36cec-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` returns the date/time value **11/12/2019 12:00:00 AM**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="36cec-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="36cec-117">Additional resources</span></span>

[<span data-ttu-id="36cec-118">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="36cec-118">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]