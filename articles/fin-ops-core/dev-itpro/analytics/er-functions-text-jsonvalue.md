---
title: Funzione ER JSONVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione JSONVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 75f20632074cb4dead98991fd6522ab9b20b9965
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041228"
---
# <span data-ttu-id="48e68-103"><a name="JSONVALUE">Funzione ER JSONVALUE</a></span><span class="sxs-lookup"><span data-stu-id="48e68-103"><a name="JSONVALUE">JSONVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48e68-104">La funzione `JSONVALUE` analizza i dati nel formato JSON (JavaScript Object Notation) accessibile nel percorso specificato ed estrae un valore scalare che ha l'ID specifico.</span><span class="sxs-lookup"><span data-stu-id="48e68-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="48e68-105">Quindi restituisce il valore scalare estratto come valore *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="48e68-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="48e68-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48e68-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="48e68-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="48e68-107">Arguments</span></span>

<span data-ttu-id="48e68-108">`input`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="48e68-108">`input`: *String*</span></span>

<span data-ttu-id="48e68-109">Il percorso valido di un'origine dati del tipo di dati *Stringa* che contiene dati JSON.</span><span class="sxs-lookup"><span data-stu-id="48e68-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="48e68-110">`path`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="48e68-110">`path`: *String*</span></span>

<span data-ttu-id="48e68-111">L'identificatore di un valore scalare dei dati JSON.</span><span class="sxs-lookup"><span data-stu-id="48e68-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="48e68-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="48e68-112">Return values</span></span>

<span data-ttu-id="48e68-113">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="48e68-113">*String*</span></span>

<span data-ttu-id="48e68-114">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="48e68-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="48e68-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="48e68-115">Example</span></span>

<span data-ttu-id="48e68-116">L'origine dati **JsonField** contiene i dati seguenti nel formato JSON: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="48e68-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="48e68-117">In questo caso, l'espressione `JSONVALUE (JsonField, "BuildNumber")` restituisce il seguente valore del tipo di dati *Stringa*: **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="48e68-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="48e68-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="48e68-118">Additional resources</span></span>

[<span data-ttu-id="48e68-119">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="48e68-119">Text functions</span></span>](er-functions-category-text.md)
