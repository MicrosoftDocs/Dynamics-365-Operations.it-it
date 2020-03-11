---
title: Funzione ER FA_BALANCE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FA_BALANCE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 76a087157ae53e2c571654ade7383d7bd7a005c3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041448"
---
# <span data-ttu-id="a3ef1-103"><a name="FA_BALANCE">Funzione ER FA_BALANCE</a></span><span class="sxs-lookup"><span data-stu-id="a3ef1-103"><a name="FA_BALANCE">FA_BALANCE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3ef1-104">La funzione `FA_BALANCE` restituisce un valore *Contenitore (record)* costituito dai dati per il saldo cespiti per l'articolo dei cespiti specificato, il codice del modello di valore, l'anno di dichiarazione e la data di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="a3ef1-104">The `FA_BALANCE` function returns a *Container (record)* value that consists of data for the fixed asset balance for the specified fixed asset item, value model code, reporting year, and reporting date.</span></span>

## <a name="syntax"></a><span data-ttu-id="a3ef1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3ef1-105">Syntax</span></span>

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a><span data-ttu-id="a3ef1-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a3ef1-106">Arguments</span></span>

<span data-ttu-id="a3ef1-107">`fixed asset code`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="a3ef1-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="a3ef1-108">Un valore *Stringa* che rappresenta il codice di un articolo dei cespiti per il quale viene calcolato il saldo.</span><span class="sxs-lookup"><span data-stu-id="a3ef1-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="a3ef1-109">`value model code`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="a3ef1-109">`value model code`: *String*</span></span>

<span data-ttu-id="a3ef1-110">Un valore *Stringa* che rappresenta il codice di un modello di valore per il quale viene calcolato il saldo.</span><span class="sxs-lookup"><span data-stu-id="a3ef1-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="a3ef1-111">`reporting year`: *Valore enumerazione*</span><span class="sxs-lookup"><span data-stu-id="a3ef1-111">`reporting year`: *Enumeration value*</span></span>

<span data-ttu-id="a3ef1-112">Un valore di enumerazione dell'enumerazione dell'applicazione **AssetYear** che definisce un periodo per il calcolo del saldo.</span><span class="sxs-lookup"><span data-stu-id="a3ef1-112">An enumeration value of the **AssetYear** application enumeration that defines a period for the balance calculation.</span></span>

<span data-ttu-id="a3ef1-113">`reporting date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="a3ef1-113">`reporting date`: *Date*</span></span>

<span data-ttu-id="a3ef1-114">Un valore *Data* che definisce una data per il calcolo del saldo.</span><span class="sxs-lookup"><span data-stu-id="a3ef1-114">A *Date* value that defines a date for the balance calculation.</span></span>

## <a name="return-values"></a><span data-ttu-id="a3ef1-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="a3ef1-115">Return values</span></span>

<span data-ttu-id="a3ef1-116">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="a3ef1-116">*Container (record)*</span></span>

<span data-ttu-id="a3ef1-117">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="a3ef1-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="a3ef1-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="a3ef1-118">Example</span></span>

<span data-ttu-id="a3ef1-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` restituisce il contenitore dati dei saldi del cespite **COMP-000001** che è stato preparato per il modello di valore **Current** sulla data della sessione corrente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a3ef1-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` returns the data container of balances for fixed asset **COMP-000001** that has been prepared for the **Current** value model on the current application session date.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3ef1-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a3ef1-120">Additional resources</span></span>

[<span data-ttu-id="a3ef1-121">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="a3ef1-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
