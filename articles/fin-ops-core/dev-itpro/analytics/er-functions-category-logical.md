---
title: Elenco delle funzioni ER nella categoria logica
description: Questo argomento fornisce informazioni sulle funzioni logiche supportate nella creazione di report elettronici (ER).
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
ms.openlocfilehash: 408b3c5ec37b24e0ccf6e368012a936701eedf0f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916639"
---
# <a name="list-of-er-functions-in-the-logical-category"></a><span data-ttu-id="5493f-103">Elenco delle funzioni ER nella categoria logica</span><span class="sxs-lookup"><span data-stu-id="5493f-103">List of ER functions in the logical category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5493f-104">Le funzioni logiche della creazione di report elettronici (ER) possono essere utilizzate per utilizzare i valori logici per eseguire più di un confronto in una singola espressione o testare più condizioni.</span><span class="sxs-lookup"><span data-stu-id="5493f-104">Electronic reporting (ER) logical functions can be used to work with logical values to perform more than one comparison in a single expression or test multiple conditions.</span></span> <span data-ttu-id="5493f-105">Questo argomento fornisce un riepilogo di queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="5493f-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="5493f-106">Elenco delle funzioni supportate</span><span class="sxs-lookup"><span data-stu-id="5493f-106">List of supported functions</span></span>

| <span data-ttu-id="5493f-107">Funzione</span><span class="sxs-lookup"><span data-stu-id="5493f-107">Function</span></span> | <span data-ttu-id="5493f-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5493f-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="5493f-109">E</span><span class="sxs-lookup"><span data-stu-id="5493f-109">And</span></span>](er-functions-logical-and.md)                       | <span data-ttu-id="5493f-110">Questa funzione restituisce un valore *Booleano* **TRUE** se tutte le condizioni specificate sono vere.</span><span class="sxs-lookup"><span data-stu-id="5493f-110">This function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="5493f-111">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="5493f-111">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="5493f-112">Caso</span><span class="sxs-lookup"><span data-stu-id="5493f-112">Case</span></span>](er-functions-logical-case.md)                     | <span data-ttu-id="5493f-113">Questa funzione valuta il valore dell'espressione specificata rispetto alle opzioni alternative specificate e restituisce il risultato della prima opzione che è uguale al valore dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="5493f-113">This function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="5493f-114">In caso contrario, restituisce un risultato predefinito facoltativo, se viene specificato un risultato predefinito come ultimo argomento della funzione richiamata che non è preceduto da un'opzione.</span><span class="sxs-lookup"><span data-stu-id="5493f-114">Otherwise, it returns an optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="5493f-115">Il valore restituito può essere un valore di uno qualsiasi dei tipi di dati supportati.</span><span class="sxs-lookup"><span data-stu-id="5493f-115">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="5493f-116">Se</span><span class="sxs-lookup"><span data-stu-id="5493f-116">If</span></span>](er-functions-logical-if.md)                         | <span data-ttu-id="5493f-117">Questa funzione restituisce il primo valore specificato se viene soddisfatta la condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="5493f-117">This function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="5493f-118">In caso contrario, restituisce il secondo valore specificato.</span><span class="sxs-lookup"><span data-stu-id="5493f-118">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="5493f-119">Il valore restituito può essere un valore di uno qualsiasi dei tipi di dati supportati.</span><span class="sxs-lookup"><span data-stu-id="5493f-119">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="5493f-120">Non</span><span class="sxs-lookup"><span data-stu-id="5493f-120">Not</span></span>](er-functions-logical-not.md)                       | <span data-ttu-id="5493f-121">Questa funzione restituisce il valore logico inverso della condizione specificata come valore *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="5493f-121">This function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span> |
| [<span data-ttu-id="5493f-122">Or</span><span class="sxs-lookup"><span data-stu-id="5493f-122">Or</span></span>](er-functions-logical-or.md)                         | <span data-ttu-id="5493f-123">Questa funzione restituisce un valore *Booleano* **FALSE** se tutte le condizioni specificate sono false.</span><span class="sxs-lookup"><span data-stu-id="5493f-123">This function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="5493f-124">Se una condizione specificata è vera, la funzione restituisce un valore *Booleano* **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="5493f-124">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span> |
| [<span data-ttu-id="5493f-125">ValueIn</span><span class="sxs-lookup"><span data-stu-id="5493f-125">ValueIn</span></span>](er-functions-logical-valuein.md)               | <span data-ttu-id="5493f-126">Questa funzione determina se l'input specificato corrisponde a qualsiasi valore di una voce specificata nell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="5493f-126">This function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="5493f-127">Restituisce un valore *Booleano* **TRUE** se l'input specificato corrisponde al risultato dell'esecuzione dell'espressione specificata per almeno un record dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="5493f-127">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="5493f-128">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="5493f-128">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="5493f-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5493f-129">Additional resources</span></span>

[<span data-ttu-id="5493f-130">Panoramica sui report elettronici</span><span class="sxs-lookup"><span data-stu-id="5493f-130">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="5493f-131">Designer formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="5493f-131">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="5493f-132">Linguaggio della formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="5493f-132">Electronic reporting formula language</span></span>](er-formula-language.md)
