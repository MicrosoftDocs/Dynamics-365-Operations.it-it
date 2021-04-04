---
title: Funzione ER COLLECTEDLIST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione COLLECTEDLIST della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: ff48170247130a03b10dc8fe2973f8d774046944
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561400"
---
# <a name="collectedlist-er-function"></a><span data-ttu-id="c79db-103">Funzione ER COLLECTEDLIST</span><span class="sxs-lookup"><span data-stu-id="c79db-103">COLLECTEDLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c79db-104">La funzione `COLLECTEDLIST` restituisce un valore *Elenco di record* che contiene l'elenco di valori restituiti dalla proprietà **Valore chiave dati raccolti** degli elementi di formato e raccolti quando gli elementi di formato sono stati utilizzati per generare documenti in uscita durante l'esecuzione e ciò soddisfa le condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="c79db-104">The `COLLECTEDLIST` function a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate outbound documents during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="c79db-105">Ogni condizione è costituita da un intervallo di chiavi e un valore chiave.</span><span class="sxs-lookup"><span data-stu-id="c79db-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="c79db-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c79db-106">Syntax</span></span>

```vb
COLLECTEDLIST (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="c79db-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c79db-107">Arguments</span></span>

<span data-ttu-id="c79db-108">`condition 1 range`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="c79db-108">`condition 1 range`: *String*</span></span>

<span data-ttu-id="c79db-109">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Nome chiave dati raccolti** di un componente di formato creazione di report elettronici (ER).</span><span class="sxs-lookup"><span data-stu-id="c79db-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span> <span data-ttu-id="c79db-110">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c79db-110">This argument is mandatory.</span></span>

<span data-ttu-id="c79db-111">`condition 1 value`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="c79db-111">`condition 1 value`: *String*</span></span>

<span data-ttu-id="c79db-112">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Valore chiave dati raccolti** di un componente del formato ER.</span><span class="sxs-lookup"><span data-stu-id="c79db-112">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="c79db-113">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c79db-113">This argument is mandatory.</span></span>

<span data-ttu-id="c79db-114">`condition N range`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="c79db-114">`condition N range`: *String*</span></span>

<span data-ttu-id="c79db-115">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Nome chiave dati raccolti** di un componente del formato ER.</span><span class="sxs-lookup"><span data-stu-id="c79db-115">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="c79db-116">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="c79db-116">These additional arguments are optional.</span></span>

<span data-ttu-id="c79db-117">`condition N value`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="c79db-117">`condition N value`: *String*</span></span>

<span data-ttu-id="c79db-118">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Valore chiave dati raccolti** di un componente del formato ER.</span><span class="sxs-lookup"><span data-stu-id="c79db-118">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="c79db-119">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="c79db-119">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="c79db-120">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="c79db-120">Return values</span></span>

<span data-ttu-id="c79db-121">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="c79db-121">*Record list*</span></span>

<span data-ttu-id="c79db-122">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="c79db-122">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c79db-123">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="c79db-123">Usage notes</span></span>

<span data-ttu-id="c79db-124">Le proprietà **Nome chiave dati raccolti** e **Valore chiave dei dati raccolti** possono essere configurate per entrambi i componenti **Sequenza** o **Elemento XML** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.</span><span class="sxs-lookup"><span data-stu-id="c79db-124">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="c79db-125">Questa funzione restituisce un elenco vuoto se l'opzione **Raccogli dettagli di output** del componente corrente **Common\\File** è disattivato.</span><span class="sxs-lookup"><span data-stu-id="c79db-125">This function returns an empty list when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="c79db-126">Negli argomenti `condition range`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.</span><span class="sxs-lookup"><span data-stu-id="c79db-126">In `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="c79db-127">Negli argomenti `condition value`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.</span><span class="sxs-lookup"><span data-stu-id="c79db-127">In `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="c79db-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="c79db-128">Example</span></span>

<span data-ttu-id="c79db-129">Per ulteriori informazioni sull'utilizzo di questa funzione, fare riferimento alla guida attività [ER Utilizzare i dati dell'output del formato per il conteggio e la somma](tasks/er-format-counting-summing-1.md) che è parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**.</span><span class="sxs-lookup"><span data-stu-id="c79db-129">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c79db-130">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c79db-130">Additional resources</span></span>

[<span data-ttu-id="c79db-131">Funzioni raccolta dati</span><span class="sxs-lookup"><span data-stu-id="c79db-131">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]