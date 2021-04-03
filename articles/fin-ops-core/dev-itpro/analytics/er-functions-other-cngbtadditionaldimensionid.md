---
title: Funzione ER CN_GBT_ADDITIONALDIMENSIONID
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CN_GBT_ADDITIONALDIMENSIONID della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 5774bb6928ae321af923819d6b2cc609dbf35b99
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564144"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="4f0d5-103">Funzione ER CN_GBT_ADDITIONALDIMENSIONID</span><span class="sxs-lookup"><span data-stu-id="4f0d5-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f0d5-104">La funzione `CN_GBT_ADDITIONALDIMENSIONID` restituisce un valore *Stringa* che rappresenta un singolo ID dimensione finanziaria preso dalla stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="4f0d5-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="4f0d5-105">La stringa specificata presenta tutte le dimensioni come un elenco di ID separato da virgole.</span><span class="sxs-lookup"><span data-stu-id="4f0d5-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f0d5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f0d5-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="4f0d5-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4f0d5-107">Arguments</span></span>

<span data-ttu-id="4f0d5-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="4f0d5-108">`text`: *String*</span></span>

<span data-ttu-id="4f0d5-109">Un valore *Stringa* che presenta tutte le dimensioni come un elenco di ID separato da virgole.</span><span class="sxs-lookup"><span data-stu-id="4f0d5-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="4f0d5-110">`number`: Intero</span><span class="sxs-lookup"><span data-stu-id="4f0d5-110">`number`: Integer</span></span>

<span data-ttu-id="4f0d5-111">Un valore *Intero* che definisce il codice di sequenza della dimensione richiesta nella stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="4f0d5-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="4f0d5-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="4f0d5-112">Return values</span></span>

<span data-ttu-id="4f0d5-113">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="4f0d5-113">*String*</span></span>

<span data-ttu-id="4f0d5-114">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="4f0d5-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="4f0d5-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f0d5-115">Example</span></span>

<span data-ttu-id="4f0d5-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` restituisce **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="4f0d5-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4f0d5-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4f0d5-117">Additional resources</span></span>

[<span data-ttu-id="4f0d5-118">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="4f0d5-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]