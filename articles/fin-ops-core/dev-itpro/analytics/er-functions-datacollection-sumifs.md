---
title: Funzione ER SUMIFS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SUMIFS della creazione di report elettronici (ER).
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
ms.openlocfilehash: a3adfe62d9fd7bdc23784cf7311f65a4d2e88960
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747085"
---
# <a name="sumifs-er-function"></a><span data-ttu-id="d878c-103">Funzione ER SUMIFS</span><span class="sxs-lookup"><span data-stu-id="d878c-103">SUMIFS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d878c-104">La funzione `SUMIFS` restituisce un valore *Reale* che rappresenta la somma dei valori restituiti da associazioni di elementi di formato e raccolti quando sono stati utilizzati per generare un documento in uscita durante l'esecuzione del formato e che soddisfano le condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="d878c-104">The `SUMIFS` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="d878c-105">Ogni condizione è costituita da un intervallo di chiavi e un valore chiave.</span><span class="sxs-lookup"><span data-stu-id="d878c-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="d878c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d878c-106">Syntax</span></span>

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="d878c-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d878c-107">Arguments</span></span>

<span data-ttu-id="d878c-108">`key name for summing`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d878c-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="d878c-109">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Nome chiave dati raccolti** del componente del formato creazione di report elettronici (ER) per il quale il valore dell'associazione deve essere utilizzato per la somma.</span><span class="sxs-lookup"><span data-stu-id="d878c-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="d878c-110">La proprietà **Nome chiave dei dati raccolti** può essere configurata per un componente **Numeric** o **Stringa** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.</span><span class="sxs-lookup"><span data-stu-id="d878c-110">The **Collected data key name** property can be configured for either a **Numeric** component or a **String** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="d878c-111">`condition 1 range`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d878c-111">`condition 1 range`: *String*</span></span>

<span data-ttu-id="d878c-112">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Nome chiave dati raccolti** di un componente del formato ER.</span><span class="sxs-lookup"><span data-stu-id="d878c-112">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="d878c-113">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d878c-113">This argument is mandatory.</span></span>

<span data-ttu-id="d878c-114">La proprietà **Nome chiave dei dati raccolti** può essere configurata per un componente **Sequence** o **XML Element** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.</span><span class="sxs-lookup"><span data-stu-id="d878c-114">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="d878c-115">`condition 1 value`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d878c-115">`condition 1 value`: *String*</span></span>

<span data-ttu-id="d878c-116">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Valore chiave dati raccolti** di un componente del formato ER.</span><span class="sxs-lookup"><span data-stu-id="d878c-116">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="d878c-117">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d878c-117">This argument is mandatory.</span></span>

<span data-ttu-id="d878c-118">La proprietà **Valore chiave dei dati raccolti** può essere configurata per un componente **Sequence** o **XML Element** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.</span><span class="sxs-lookup"><span data-stu-id="d878c-118">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="d878c-119">`condition N range`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d878c-119">`condition N range`: *String*</span></span>

<span data-ttu-id="d878c-120">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Nome chiave dati raccolti** di un componente del formato ER.</span><span class="sxs-lookup"><span data-stu-id="d878c-120">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="d878c-121">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="d878c-121">These additional arguments are optional.</span></span>

<span data-ttu-id="d878c-122">La proprietà **Nome chiave dei dati raccolti** può essere configurata per un componente **Sequence** o **XML Element** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.</span><span class="sxs-lookup"><span data-stu-id="d878c-122">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="d878c-123">`condition N value`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d878c-123">`condition N value`: *String*</span></span>

<span data-ttu-id="d878c-124">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Valore chiave dati raccolti** di un componente del formato ER.</span><span class="sxs-lookup"><span data-stu-id="d878c-124">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="d878c-125">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="d878c-125">These additional arguments are optional.</span></span>

<span data-ttu-id="d878c-126">La proprietà **Valore chiave dei dati raccolti** può essere configurata per un componente **Sequence** o **XML Element** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.</span><span class="sxs-lookup"><span data-stu-id="d878c-126">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="d878c-127">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="d878c-127">Return values</span></span>

<span data-ttu-id="d878c-128">*Reale*</span><span class="sxs-lookup"><span data-stu-id="d878c-128">*Real*</span></span>

<span data-ttu-id="d878c-129">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="d878c-129">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d878c-130">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="d878c-130">Usage notes</span></span>

<span data-ttu-id="d878c-131">Questa funzione restituisce un valore **0** (zero) se l'opzione **Raccogli dettagli di output** del componente corrente **Common\\File** è disattivata.</span><span class="sxs-lookup"><span data-stu-id="d878c-131">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="d878c-132">Negli argomenti `condition range`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.</span><span class="sxs-lookup"><span data-stu-id="d878c-132">In the `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="d878c-133">Negli argomenti `condition value`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.</span><span class="sxs-lookup"><span data-stu-id="d878c-133">In the `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="d878c-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="d878c-134">Example</span></span>

<span data-ttu-id="d878c-135">Per ulteriori informazioni sull'utilizzo di questa funzione, fare riferimento alla guida attività [ER Utilizzare i dati dell'output del formato per il conteggio e la somma](tasks/er-format-counting-summing-1.md) che è parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**.</span><span class="sxs-lookup"><span data-stu-id="d878c-135">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d878c-136">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d878c-136">Additional resources</span></span>

[<span data-ttu-id="d878c-137">Funzioni raccolta dati</span><span class="sxs-lookup"><span data-stu-id="d878c-137">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]