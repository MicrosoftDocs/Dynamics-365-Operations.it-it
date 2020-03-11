---
title: Funzione ER FA_SUM
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FA_SUM della creazione di report elettronici (ER).
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
ms.openlocfilehash: 03bed091350b39601edb22b5af6bda5a83af47eb
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041356"
---
# <span data-ttu-id="0f0b3-103"><a name="FA_SUM">Funzione ER FA_SUM</a></span><span class="sxs-lookup"><span data-stu-id="0f0b3-103"><a name="FA_SUM">FA_SUM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f0b3-104">La funzione `FA_SUM` restituisce un valore *Contenitore (record)* costituito dai dati per gli importi cespiti per l'articolo dei cespiti specificato, il codice del modello di valore e il periodo di date.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f0b3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f0b3-105">Syntax</span></span>

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="0f0b3-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0f0b3-106">Arguments</span></span>

<span data-ttu-id="0f0b3-107">`fixed asset code`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="0f0b3-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="0f0b3-108">Un valore *Stringa* che rappresenta il codice di un articolo dei cespiti per il quale viene calcolato il saldo.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="0f0b3-109">`value model code`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="0f0b3-109">`value model code`: *String*</span></span>

<span data-ttu-id="0f0b3-110">Un valore *Stringa* che rappresenta il codice di un modello di valore per il quale viene calcolato il saldo.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="0f0b3-111">`start date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="0f0b3-111">`start date`: *Date*</span></span>

<span data-ttu-id="0f0b3-112">Un valore *Data* che rappresenta la data di inizio di un periodo per il quale sono calcolati gli importi cespiti.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="0f0b3-113">`end date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="0f0b3-113">`end date`: *Date*</span></span>

<span data-ttu-id="0f0b3-114">Un valore *Data* che rappresenta la data di fine di un periodo per il quale sono calcolati gli importi cespiti.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="0f0b3-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="0f0b3-115">Return values</span></span>

<span data-ttu-id="0f0b3-116">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="0f0b3-116">*Container (record)*</span></span>

<span data-ttu-id="0f0b3-117">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="0f0b3-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f0b3-118">Example</span></span>

<span data-ttu-id="0f0b3-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` restituisce il contenitore di dati per il cespite **COMP-000001** che è stato preparato per il modello di valore **corrente** e per un periodo da **Date1** a **Date2**.</span><span class="sxs-lookup"><span data-stu-id="0f0b3-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f0b3-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0f0b3-120">Additional resources</span></span>

[<span data-ttu-id="0f0b3-121">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="0f0b3-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
