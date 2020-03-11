---
title: Funzione ER CN_GBT_ADDITIONALDIMENSIONID
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CN_GBT_ADDITIONALDIMENSIONID della creazione di report elettronici (ER).
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
ms.openlocfilehash: 2395a1932e543e35ced28a2a6e56ab44835de19a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041540"
---
# <span data-ttu-id="36728-103"><a name="CN_GBT_ADDITIONALDIMENSIONID">Funzione ER CN_GBT_ADDITIONALDIMENSIONID</a></span><span class="sxs-lookup"><span data-stu-id="36728-103"><a name="CN_GBT_ADDITIONALDIMENSIONID">CN_GBT_ADDITIONALDIMENSIONID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36728-104">La funzione `CN_GBT_ADDITIONALDIMENSIONID` restituisce un valore *Stringa* che rappresenta un singolo ID dimensione finanziaria preso dalla stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="36728-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="36728-105">La stringa specificata presenta tutte le dimensioni come un elenco di ID separato da virgole.</span><span class="sxs-lookup"><span data-stu-id="36728-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="36728-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36728-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="36728-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="36728-107">Arguments</span></span>

<span data-ttu-id="36728-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="36728-108">`text`: *String*</span></span>

<span data-ttu-id="36728-109">Un valore *Stringa* che presenta tutte le dimensioni come un elenco di ID separato da virgole.</span><span class="sxs-lookup"><span data-stu-id="36728-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="36728-110">`number`: Intero</span><span class="sxs-lookup"><span data-stu-id="36728-110">`number`: Integer</span></span>

<span data-ttu-id="36728-111">Un valore *Intero* che definisce il codice di sequenza della dimensione richiesta nella stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="36728-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="36728-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="36728-112">Return values</span></span>

<span data-ttu-id="36728-113">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="36728-113">*String*</span></span>

<span data-ttu-id="36728-114">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="36728-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="36728-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="36728-115">Example</span></span>

<span data-ttu-id="36728-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` restituisce **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="36728-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="36728-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="36728-117">Additional resources</span></span>

[<span data-ttu-id="36728-118">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="36728-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
