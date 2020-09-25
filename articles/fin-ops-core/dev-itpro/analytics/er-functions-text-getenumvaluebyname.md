---
title: Funzione ER GETENUMVALUEBYNAME
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione GETENUMVALUEBYNAME della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 33ccf358dc5355cd00d5ff41ebd8148a334cba38
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743857"
---
# <a name="getenumvaluebyname-er-function"></a><span data-ttu-id="34b49-103">Funzione ER GETENUMVALUEBYNAME</span><span class="sxs-lookup"><span data-stu-id="34b49-103">GETENUMVALUEBYNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34b49-104">La funzione `GETENUMVALUEBYNAME` cerca un valore specifico *Enum* nell'origine dati di enumerazione specificata utilizzando il nome dell'enumerazione specificato come un valore *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="34b49-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="34b49-105">Se viene trovato il valore *Enum*, la funzione lo restituisce.</span><span class="sxs-lookup"><span data-stu-id="34b49-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="34b49-106">Altrimenti, la funzione restituisce il valore di enumerazione **nullo**.</span><span class="sxs-lookup"><span data-stu-id="34b49-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="34b49-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34b49-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="34b49-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="34b49-108">Arguments</span></span>

<span data-ttu-id="34b49-109">`enumeration data source path`: *Enumerazione*</span><span class="sxs-lookup"><span data-stu-id="34b49-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="34b49-110">Il percorso valido di un'origine dati di uno dei seguenti tipi di enumerazione:</span><span class="sxs-lookup"><span data-stu-id="34b49-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="34b49-111">Enumerazione di modelli di creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="34b49-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="34b49-112">Enumerazione formato ER</span><span class="sxs-lookup"><span data-stu-id="34b49-112">ER format enumeration</span></span>
- <span data-ttu-id="34b49-113">Enumerazione Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="34b49-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="34b49-114">`enumeration value text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="34b49-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="34b49-115">Un valore di stringa che rappresenta il nome di un singolo valore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="34b49-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="34b49-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="34b49-116">Return values</span></span>

<span data-ttu-id="34b49-117">*Enum* nullable</span><span class="sxs-lookup"><span data-stu-id="34b49-117">Nullable *Enum*</span></span>

<span data-ttu-id="34b49-118">Il valore di enumerazione risultante.</span><span class="sxs-lookup"><span data-stu-id="34b49-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="34b49-119">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="34b49-119">Usage notes</span></span>

<span data-ttu-id="34b49-120">Nessuna eccezione viene generata se non viene trovato un valore *Enum* utilizzando il nome del valore di enumerazione specificato come un valore *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="34b49-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example"></a><span data-ttu-id="34b49-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="34b49-121">Example</span></span>

<span data-ttu-id="34b49-122">Nella seguente figura viene illustrata l'enumerazione **ReportDirection** introdotta in un modello dati.</span><span class="sxs-lookup"><span data-stu-id="34b49-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="34b49-123">Tenere presente che le etichette vengono definite per i valori dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="34b49-123">Notice that labels are defined for the enumeration values.</span></span>

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="34b49-124">La figura di seguito mostra questi dettagli:</span><span class="sxs-lookup"><span data-stu-id="34b49-124">The following illustration shows these details:</span></span>

- <span data-ttu-id="34b49-125">L'origine dati **$ Direction** è configurata in un report ER.</span><span class="sxs-lookup"><span data-stu-id="34b49-125">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="34b49-126">Questa origine dati è configurata in base all'enumerazione del modello **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="34b49-126">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="34b49-127">L'espressione `$IsArrivals` viene progettata per l'utilizzo dell'origine dati **$Direction** basata sull'enumerazione di modello come parametro di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="34b49-127">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="34b49-128">Il valore di questa espressione di confronto è **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="34b49-128">The value of this comparison expression is **TRUE**.</span></span>

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a><span data-ttu-id="34b49-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="34b49-129">Additional resources</span></span>

[<span data-ttu-id="34b49-130">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="34b49-130">Text functions</span></span>](er-functions-category-text.md)
