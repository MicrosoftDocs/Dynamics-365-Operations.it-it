---
title: Funzione ER COUNTIF
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione COUNTIF della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: cc857a004d988a421c32722b1f69e86b7fefeb36
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743617"
---
# <a name="countif-er-function"></a><span data-ttu-id="8a8d2-103">Funzione ER COUNTIF</span><span class="sxs-lookup"><span data-stu-id="8a8d2-103">COUNTIF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a8d2-104">La funzione `COUNTIF` restituisce un valore *Intero* che rappresenta il numero di elementi di formato raccolti quando sono stati utilizzati per generare un documento in uscita durante l'esecuzione del formato e che soddisfano la condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="8a8d2-104">The `COUNTIF` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="8a8d2-105">La condizione è costituita da un intervallo di chiavi e un valore chiave.</span><span class="sxs-lookup"><span data-stu-id="8a8d2-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a8d2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a8d2-106">Syntax</span></span>

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="8a8d2-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8a8d2-107">Arguments</span></span>

<span data-ttu-id="8a8d2-108">`condition range`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="8a8d2-108">`condition range`: *String*</span></span>

<span data-ttu-id="8a8d2-109">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Nome chiave dati raccolti** di un componente di formato creazione di report elettronici (ER).</span><span class="sxs-lookup"><span data-stu-id="8a8d2-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span>

<span data-ttu-id="8a8d2-110">`condition value`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="8a8d2-110">`condition value`: *String*</span></span>

<span data-ttu-id="8a8d2-111">Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Valore chiave dati raccolti** di un componente del formato ER.</span><span class="sxs-lookup"><span data-stu-id="8a8d2-111">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span>

## <a name="return-values"></a><span data-ttu-id="8a8d2-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="8a8d2-112">Return values</span></span>

<span data-ttu-id="8a8d2-113">*Intero*</span><span class="sxs-lookup"><span data-stu-id="8a8d2-113">*Integer*</span></span>

<span data-ttu-id="8a8d2-114">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="8a8d2-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8a8d2-115">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="8a8d2-115">Usage notes</span></span>

<span data-ttu-id="8a8d2-116">Le proprietà **Nome chiave dati raccolti** e **Valore chiave dei dati raccolti** possono essere configurate per entrambi i componenti **Sequenza** o **Elemento XML** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.</span><span class="sxs-lookup"><span data-stu-id="8a8d2-116">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="8a8d2-117">Questa funzione restituisce un valore **0** (zero) se l'opzione **Raccogli dettagli di output** del componente corrente **Common\\File** è disattivata.</span><span class="sxs-lookup"><span data-stu-id="8a8d2-117">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="8a8d2-118">Nell'argomento `condition range`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.</span><span class="sxs-lookup"><span data-stu-id="8a8d2-118">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="8a8d2-119">Nell'argomento `condition value`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.</span><span class="sxs-lookup"><span data-stu-id="8a8d2-119">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="8a8d2-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a8d2-120">Example</span></span>

<span data-ttu-id="8a8d2-121">Per ulteriori informazioni sull'utilizzo di questa funzione, fare riferimento alla guida attività [ER Utilizzare i dati dell'output del formato per il conteggio e la somma](tasks/er-format-counting-summing-1.md) che è parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**.</span><span class="sxs-lookup"><span data-stu-id="8a8d2-121">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8a8d2-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8a8d2-122">Additional resources</span></span>

[<span data-ttu-id="8a8d2-123">Funzioni raccolta dati</span><span class="sxs-lookup"><span data-stu-id="8a8d2-123">Data collection functions</span></span>](er-functions-category-data-collection.md)
