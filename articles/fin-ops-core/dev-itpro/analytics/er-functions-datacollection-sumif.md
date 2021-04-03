---
title: Funzione ER SUMIF
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SUMIF della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 04/27/2020
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
ms.openlocfilehash: 6f5069d197abf2e38d09012defeb982a9e5e1234
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565966"
---
# <a name="sumif-er-function"></a><span data-ttu-id="d4728-103">Funzione ER SUMIF</span><span class="sxs-lookup"><span data-stu-id="d4728-103">SUMIF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d4728-104">La funzione `SUMIF` restituisce un valore *Reale* che rappresenta la somma dei valori restituiti da associazioni di elementi di formato e raccolti quando sono stati utilizzati per generare un documento in uscita durante l'esecuzione del formato e che soddisfano la condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="d4728-104">The `SUMIF` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="d4728-105">La condizione è costituita da un intervallo di chiavi e un valore chiave.</span><span class="sxs-lookup"><span data-stu-id="d4728-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="d4728-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4728-106">Syntax</span></span>

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="d4728-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d4728-107">Arguments</span></span>

<span data-ttu-id="d4728-108">`key name for summing`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d4728-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="d4728-109">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Nome chiave dati raccolti** del componente del formato creazione di report elettronici (ER) per il quale il valore dell'associazione deve essere utilizzato per la somma.</span><span class="sxs-lookup"><span data-stu-id="d4728-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="d4728-110">La proprietà **Valore chiave dei dati raccolti** può essere configurata per un componente **Sequence** o **XML Element** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.</span><span class="sxs-lookup"><span data-stu-id="d4728-110">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="d4728-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="d4728-111">Return values</span></span>

<span data-ttu-id="d4728-112">*Reale*</span><span class="sxs-lookup"><span data-stu-id="d4728-112">*Real*</span></span>

<span data-ttu-id="d4728-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="d4728-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d4728-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="d4728-114">Usage notes</span></span>

<span data-ttu-id="d4728-115">Questa funzione restituisce un valore **0** (zero) se l'opzione **Raccogli dettagli di output** del componente corrente **Common\\File** è disattivata.</span><span class="sxs-lookup"><span data-stu-id="d4728-115">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="d4728-116">Nell'argomento `condition range`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.</span><span class="sxs-lookup"><span data-stu-id="d4728-116">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="d4728-117">Nell'argomento `condition value`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.</span><span class="sxs-lookup"><span data-stu-id="d4728-117">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="d4728-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4728-118">Example</span></span>

<span data-ttu-id="d4728-119">Per ulteriori informazioni sull'utilizzo di questa funzione, fare riferimento alla guida attività [ER Utilizzare i dati dell'output del formato per il conteggio e la somma](tasks/er-format-counting-summing-1.md) che è parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**.</span><span class="sxs-lookup"><span data-stu-id="d4728-119">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

<span data-ttu-id="d4728-120">Per ulteriori informazioni ed esempi sull'uso di questa funzione, vedere [Differire l'esecuzione di elementi di sequenza in formati ER](er-defer-sequence-element.md#Example) e [Differire l'esecuzione di elementi XML in formati ER](er-defer-xml-element.md#Example).</span><span class="sxs-lookup"><span data-stu-id="d4728-120">For more information and examples about using this function, see [Defer the execution of sequence elements in ER formats](er-defer-sequence-element.md#Example) and [Defer the execution of XML elements in ER formats](er-defer-xml-element.md#Example).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d4728-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d4728-121">Additional resources</span></span>

[<span data-ttu-id="d4728-122">Funzioni raccolta dati</span><span class="sxs-lookup"><span data-stu-id="d4728-122">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]