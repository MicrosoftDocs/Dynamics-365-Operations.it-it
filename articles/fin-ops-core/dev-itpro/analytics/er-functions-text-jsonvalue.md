---
title: Funzione ER JSONVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione JSONVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 203fe1b1616f724ddf3015258306e0d9e8d4f599
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570018"
---
# <a name="jsonvalue-er-function"></a><span data-ttu-id="59acc-103">Funzione ER JSONVALUE</span><span class="sxs-lookup"><span data-stu-id="59acc-103">JSONVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59acc-104">La funzione `JSONVALUE` analizza i dati nel formato JSON (JavaScript Object Notation) accessibile nel percorso specificato ed estrae un valore scalare che ha l'ID specifico.</span><span class="sxs-lookup"><span data-stu-id="59acc-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="59acc-105">Quindi restituisce il valore scalare estratto come valore *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="59acc-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="59acc-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59acc-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="59acc-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="59acc-107">Arguments</span></span>

<span data-ttu-id="59acc-108">`input`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="59acc-108">`input`: *String*</span></span>

<span data-ttu-id="59acc-109">Il percorso valido di un'origine dati del tipo di dati *Stringa* che contiene dati JSON.</span><span class="sxs-lookup"><span data-stu-id="59acc-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="59acc-110">`path`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="59acc-110">`path`: *String*</span></span>

<span data-ttu-id="59acc-111">L'identificatore di un valore scalare dei dati JSON.</span><span class="sxs-lookup"><span data-stu-id="59acc-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="59acc-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="59acc-112">Return values</span></span>

<span data-ttu-id="59acc-113">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="59acc-113">*String*</span></span>

<span data-ttu-id="59acc-114">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="59acc-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="59acc-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="59acc-115">Example</span></span>

<span data-ttu-id="59acc-116">L'origine dati **JsonField** contiene i dati seguenti nel formato JSON: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="59acc-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="59acc-117">In questo caso, l'espressione `JSONVALUE (JsonField, "BuildNumber")` restituisce il seguente valore del tipo di dati *Stringa*: **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="59acc-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="59acc-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="59acc-118">Additional resources</span></span>

[<span data-ttu-id="59acc-119">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="59acc-119">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]