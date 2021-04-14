---
title: Funzione ER VALUEIN
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione VALUEIN della creazione di report elettronici (ER).
author: NickSelin
ms.date: 08/18/2020
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
ms.openlocfilehash: 909aef5e52817a67e400f3132cb5d6ecc8a18906
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751752"
---
# <a name="valuein-er-function"></a><span data-ttu-id="a491c-103">Funzione ER VALUEIN</span><span class="sxs-lookup"><span data-stu-id="a491c-103">VALUEIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a491c-104">La funzione `VALUEIN` determina se l'input specificato corrisponde a qualsiasi valore di una voce specificata nell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="a491c-104">The `VALUEIN` function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="a491c-105">Restituisce un valore *Booleano* **TRUE** se l'input specificato corrisponde al risultato dell'esecuzione dell'espressione specificata per almeno un record dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="a491c-105">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="a491c-106">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="a491c-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="a491c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a491c-107">Syntax</span></span>

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="a491c-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a491c-108">Arguments</span></span>

<span data-ttu-id="a491c-109">`input`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="a491c-109">`input`: *Field*</span></span>

<span data-ttu-id="a491c-110">Il percorso valido di un elemento di un'origine dati del tipo *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="a491c-110">The valid path of an item of a data source of the *Record list* type.</span></span> <span data-ttu-id="a491c-111">Il valore di questa voce verrà associato.</span><span class="sxs-lookup"><span data-stu-id="a491c-111">The value of this item will be matched.</span></span>

<span data-ttu-id="a491c-112">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="a491c-112">`list`: *Record list*</span></span>

<span data-ttu-id="a491c-113">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="a491c-113">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="a491c-114">`list item expression`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="a491c-114">`list item expression`: *Boolean*</span></span>

<span data-ttu-id="a491c-115">Un'espressione condizionale valida che indica o contiene un singolo campo dell'elenco specificato da utilizzare per la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="a491c-115">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="a491c-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="a491c-116">Return values</span></span>

<span data-ttu-id="a491c-117">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="a491c-117">*Boolean*</span></span>

<span data-ttu-id="a491c-118">Il valore *Booleano* risultante.</span><span class="sxs-lookup"><span data-stu-id="a491c-118">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a491c-119">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="a491c-119">Usage notes</span></span>

<span data-ttu-id="a491c-120">In generale la funzione `VALUEIN` viene convertita in un set di condizioni **OR** .</span><span class="sxs-lookup"><span data-stu-id="a491c-120">In general, the `VALUEIN` function is translated to a set of **OR** conditions.</span></span> <span data-ttu-id="a491c-121">Se l'elenco di condizioni **OR** è grande e la lunghezza totale massima di un'istruzione SQL potrebbe essere superata, prendere in considerazione l'utilizzo della funzione [`VALUEINLARGE`](er-functions-logical-valueinlarge.md).</span><span class="sxs-lookup"><span data-stu-id="a491c-121">If the list of **OR** conditions is large and the maximum total length of an SQL statement might be exceeded, consider using the [`VALUEINLARGE`](er-functions-logical-valueinlarge.md) function.</span></span>

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

<span data-ttu-id="a491c-122">In alcuni casi, può essere tradotta in un'istruzione di database SQL utilizzando l'operatore `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="a491c-122">In some cases, it can be translated to a database SQL statement by using the `EXISTS JOIN` operator.</span></span>

## <a name="example-1"></a><span data-ttu-id="a491c-123">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="a491c-123">Example 1</span></span>

<span data-ttu-id="a491c-124">Nel mapping di modelli viene definita l'origine dati **List** del tipo *Campo calcolato*.</span><span class="sxs-lookup"><span data-stu-id="a491c-124">In your model mapping, you define the **List** data source of the *Calculated field* type.</span></span> <span data-ttu-id="a491c-125">Questa origine dati contiene l'espressione `SPLIT ("a,b,c", ",")`.</span><span class="sxs-lookup"><span data-stu-id="a491c-125">This data source contains the expression `SPLIT ("a,b,c", ",")`.</span></span>

<span data-ttu-id="a491c-126">Quando viene chiamata un'origine dati, se è stata configurata come espressione `VALUEIN ("B", List, List.Value)`, restituisce **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="a491c-126">When a data source is called, if it has been configured as the `VALUEIN ("B", List, List.Value)` expression, it returns **TRUE**.</span></span> <span data-ttu-id="a491c-127">In questo caso la funzione `VALUEIN` viene convertita nel seguente set di condizioni: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, dove `("B" = "b")` corrisponde a **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="a491c-127">In this case, the `VALUEIN` function is translated to the following set of conditions: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, where `("B" = "b")` equals **TRUE**.</span></span>

<span data-ttu-id="a491c-128">Quando viene chiamata un'origine dati, se è stata configurata come espressione `VALUEIN ("B", List, LEFT(List.Value, 0))`, restituisce **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="a491c-128">When a data source is called, if it has been configured as the `VALUEIN ("B", List, LEFT(List.Value, 0))` expression, it returns **FALSE**.</span></span> <span data-ttu-id="a491c-129">In questo caso la funzione `VALUEIN` viene convertita nella seguente condizione: `("B" = "")`, che non corrisponde a **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="a491c-129">In this case, the `VALUEIN` function is translated to the following condition: `("B" = "")`, which doesn't equal **TRUE**.</span></span>

<span data-ttu-id="a491c-130">Il limite massimo per il numero di caratteri nel testo di tale condizione è di 32.768 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a491c-130">The upper limit for the number of characters in the text of such a condition is 32,768 characters.</span></span> <span data-ttu-id="a491c-131">Di conseguenza, evitare di creare origini dati che potrebbero superare il limite in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a491c-131">Therefore, you should not create data sources that might exceed this limit at runtime.</span></span> <span data-ttu-id="a491c-132">Se il limite viene superato, l'applicazione smette di funzionare e viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a491c-132">If the limit is exceeded, the application stops running, and an exception is thrown.</span></span> <span data-ttu-id="a491c-133">Ad esempio, questa situazione può verificarsi se l'origine dati viene configurata come `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)` e gli elenchi **List1** e **List2** contengono un ampio volume di record.</span><span class="sxs-lookup"><span data-stu-id="a491c-133">For example, this situation can occur if the data source is configured as `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, and the **List1** and **List2** lists contain a large volume of records.</span></span>

<span data-ttu-id="a491c-134">In alcuni casi, la funzione `VALUEIN` viene convertita in un'istruzione di database utilizzando l'operatore `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="a491c-134">In some cases, the `VALUEIN` function is translated to a database statement by using the `EXISTS JOIN` operator.</span></span> <span data-ttu-id="a491c-135">Questo comportamento avviene quando la funzione [`FILTER`](er-functions-list-filter.md) viene utilizzata e vengono soddisfatte le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="a491c-135">This behavior occurs when the [`FILTER`](er-functions-list-filter.md) function is used and the following conditions are met:</span></span>

- <span data-ttu-id="a491c-136">L'opzione **Chiedi query** è disattivata per l'origine dati della funzione `VALUEIN` che fa riferimento all'elenco di record.</span><span class="sxs-lookup"><span data-stu-id="a491c-136">The **ASK FOR QUERY** option is turned off for the data source of the `VALUEIN` function that refers to the list of records.</span></span> <span data-ttu-id="a491c-137">Nessuna condizione aggiuntiva verrà applicata a questa origine dati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a491c-137">No additional conditions will be applied to this data source at runtime.</span></span>
- <span data-ttu-id="a491c-138">Nessuna espressione nidificata è configurata per l'origine dati della funzione `VALUEIN` che fa riferimento all'elenco di record.</span><span class="sxs-lookup"><span data-stu-id="a491c-138">No nested expressions are configured for the data source of the `VALUEIN` function that refers to the list of records.</span></span>
- <span data-ttu-id="a491c-139">Una voce dell'elenco della funzione `VALUEIN` si riferisce a un campo dell'origine dati specificata, non a un'espressione o un metodo di quell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="a491c-139">A list item of the `VALUEIN` function refers to a field of the specified data source, not to an expression or method of that data source.</span></span>

<span data-ttu-id="a491c-140">Può essere opportuno di utilizzare questa opzione anziché la funzione [`WHERE`](er-functions-list-where.md) descritta in precedenza in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="a491c-140">Consider using this option instead of the [`WHERE`](er-functions-list-where.md) function that is described earlier in this example.</span></span>

## <a name="example-2"></a><span data-ttu-id="a491c-141">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="a491c-141">Example 2</span></span>

<span data-ttu-id="a491c-142">Definire le origini dati seguenti nel mapping di modello:</span><span class="sxs-lookup"><span data-stu-id="a491c-142">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="a491c-143">L'origine dati **In** del tipo *Record di tabella*.</span><span class="sxs-lookup"><span data-stu-id="a491c-143">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="a491c-144">Questa origine dati fa riferimento alla tabella Intrastat.</span><span class="sxs-lookup"><span data-stu-id="a491c-144">This data source refers to the Intrastat table.</span></span>
- <span data-ttu-id="a491c-145">L'origine dati **Port** del tipo *Record di tabella*.</span><span class="sxs-lookup"><span data-stu-id="a491c-145">The **Port** data source of the *Table records* type.</span></span> <span data-ttu-id="a491c-146">Questa origine dati fa riferimento alla tabella IntrastatPort.</span><span class="sxs-lookup"><span data-stu-id="a491c-146">This data source refers to the IntrastatPort table.</span></span>

<span data-ttu-id="a491c-147">Quando viene chiamata un'origine dati che è stata configurata come l'espressione `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)`, la seguente istruzione SQL viene generata per restituire i record filtrati della tabella Intrastat.</span><span class="sxs-lookup"><span data-stu-id="a491c-147">When a data source is called that has been configured as the `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` expression, the following SQL statement is generated to return filtered records of the Intrastat table.</span></span>

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

<span data-ttu-id="a491c-148">Per i campi **dataAreaId**, l'istruzione SQL finale viene generata usando l'operatore `IN`.</span><span class="sxs-lookup"><span data-stu-id="a491c-148">For **dataAreaId** fields, the final SQL statement is generated by the using `IN` operator.</span></span>

## <a name="example-3"></a><span data-ttu-id="a491c-149">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="a491c-149">Example 3</span></span>

<span data-ttu-id="a491c-150">Definire le origini dati seguenti nel mapping di modello:</span><span class="sxs-lookup"><span data-stu-id="a491c-150">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="a491c-151">L'origine dati **Le** del tipo *Campo calcolato*.</span><span class="sxs-lookup"><span data-stu-id="a491c-151">The **Le** data source of the *Calculated field* type.</span></span> <span data-ttu-id="a491c-152">Questa origine dati contiene l'espressione `SPLIT ("DEMF,GBSI,USMF", ",")`.</span><span class="sxs-lookup"><span data-stu-id="a491c-152">This data source contains the expression `SPLIT ("DEMF,GBSI,USMF", ",")`.</span></span>
- <span data-ttu-id="a491c-153">L'origine dati **In** del tipo *Record di tabella*.</span><span class="sxs-lookup"><span data-stu-id="a491c-153">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="a491c-154">Questa origine dati fa riferimento alla tabella Intrastat e l'opzione **Cross-company** è attivata.</span><span class="sxs-lookup"><span data-stu-id="a491c-154">This data source refers to the Intrastat table, and the **Cross-company** option is turned on for it.</span></span>

<span data-ttu-id="a491c-155">Quando viene chiamata un'origine dati che è stata configurata come l'espressione `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, l'istruzione SQL finale contiene la condizione seguente.</span><span class="sxs-lookup"><span data-stu-id="a491c-155">When a data source is called that has been configured as the `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` expression, the final SQL statement contains the following condition.</span></span>

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a><span data-ttu-id="a491c-156">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a491c-156">Additional resources</span></span>

[<span data-ttu-id="a491c-157">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="a491c-157">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="a491c-158">Funzioni VALUEINLARGE</span><span class="sxs-lookup"><span data-stu-id="a491c-158">VALUEINLARGE functions</span></span>](er-functions-logical-valueinlarge.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]