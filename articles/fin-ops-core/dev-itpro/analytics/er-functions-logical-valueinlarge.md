---
title: Funzione ER VALUEINLARGE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione VALUEINLARGE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 26a7148a4caa80a191688145bac625bdf0bf83b2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686908"
---
# <a name="valueinlarge-er-function"></a><span data-ttu-id="4b344-103">Funzione ER VALUEINLARGE</span><span class="sxs-lookup"><span data-stu-id="4b344-103">VALUEINLARGE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b344-104">La funzione `VALUEINLARGE` determina se l'input specificato di tipo *Int64* o *Intero* corrisponde a qualsiasi valore di una voce specificata nell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="4b344-104">The `VALUEINLARGE` function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="4b344-105">La funzione restituisce un valore *Booleano* **TRUE** se l'input specificato corrisponde al risultato dell'esecuzione dell'espressione specificata per almeno un record dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="4b344-105">The function returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="4b344-106">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="4b344-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> <span data-ttu-id="4b344-107">Per capire la differenza con la funzione `VALUEIN`, vedere la [Nota di utilizzo](#usage_note) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4b344-107">To understand the difference with the `VALUEIN` function, see the [Usage note](#usage_note) section later in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b344-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b344-108">Syntax</span></span>

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="4b344-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4b344-109">Arguments</span></span>

<span data-ttu-id="4b344-110">`input`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="4b344-110">`input`: *Field*</span></span>

<span data-ttu-id="4b344-111">Il percorso valido di un elemento origine dati del tipo *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="4b344-111">The valid path of a data source item of the *Record list* type.</span></span> <span data-ttu-id="4b344-112">Il valore di questa voce verrà associato.</span><span class="sxs-lookup"><span data-stu-id="4b344-112">The value of this item will be matched.</span></span>

<span data-ttu-id="4b344-113">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="4b344-113">`list`: *Record list*</span></span>

<span data-ttu-id="4b344-114">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="4b344-114">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="4b344-115">`list item expression`: *Espressione*</span><span class="sxs-lookup"><span data-stu-id="4b344-115">`list item expression`: *Expression*</span></span>

<span data-ttu-id="4b344-116">Un'espressione condizionale valida che indica o contiene un singolo campo dell'elenco specificato da utilizzare per la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="4b344-116">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="4b344-117">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="4b344-117">Return values</span></span>

<span data-ttu-id="4b344-118">*Boolean*</span><span class="sxs-lookup"><span data-stu-id="4b344-118">*Boolean*</span></span>

<span data-ttu-id="4b344-119">Il valore *Booleano* risultante.</span><span class="sxs-lookup"><span data-stu-id="4b344-119">The resulting *Boolean* value.</span></span>

## <a name=""></a><span data-ttu-id="4b344-120"><a name="usage_note">Note sull'utilizzo</a></span><span class="sxs-lookup"><span data-stu-id="4b344-120"><a name="usage_note">Usage notes</a></span></span>

<span data-ttu-id="4b344-121">Quando l'input specificato rappresenta un tipo *Int64* o *Intero* di un elemento dell'origine dati, la chiamata è traducibile in un'istruzione SQL diretta, l'elenco specificato viene convertito in una tabella SQL temporanea e la corrispondenza viene eseguita nel database eseguendo una singola query `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="4b344-121">When the specified input represents an *Int64* or *Integer* type of a data source item, the call to which is translatable to a direct SQL statement, the specified list is converted to a temporary SQL table and matching is performed in the database by executing a single `EXISTS JOIN` query.</span></span> <span data-ttu-id="4b344-122">Altrimenti, questa funzione funziona come la funzione [`VALUEIN`](er-functions-logical-valuein.md).</span><span class="sxs-lookup"><span data-stu-id="4b344-122">Otherwise, this function works as the [`VALUEIN`](er-functions-logical-valuein.md) function.</span></span>

<span data-ttu-id="4b344-123">Quando l'input specificato rappresenta un elemento dell'origine dati progettato come elemento diverso dal tipo *Int64* e *Intero*, si verifica un errore in fase di progettazione che informa che la funzione `VALUEINLARGE` non è applicabile per l'espressione ER configurata.</span><span class="sxs-lookup"><span data-stu-id="4b344-123">When the specified input represents a data source item that is designed as an item other than *Int64* and *Integer* type, an error occurs at design time informing you that the `VALUEINLARGE` function is not applicable for the configured ER expression.</span></span>

<span data-ttu-id="4b344-124">Quando l'espressione della funzione `VALUEINLARGE` viene eseguita e viene utilizzata più di una tabella temporanea nell'ambito di questa esecuzione, si verifica un errore di runtime.</span><span class="sxs-lookup"><span data-stu-id="4b344-124">When the `VALUEINLARGE` function expression is executed and more than one temporary table is used in scope of this execution, a runtime error occurs.</span></span>

## <a name="example"></a><span data-ttu-id="4b344-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b344-125">Example</span></span>

<span data-ttu-id="4b344-126">Definire le origini dati seguenti nel mapping di modello:</span><span class="sxs-lookup"><span data-stu-id="4b344-126">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="4b344-127">L'origine dati **In** del tipo *Record di tabella*.</span><span class="sxs-lookup"><span data-stu-id="4b344-127">The **In** data source of the *Table records* type.</span></span>
    - <span data-ttu-id="4b344-128">Questa origine dati fa riferimento alla tabella **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="4b344-128">This data source refers to the **Intrastat** table.</span></span>
    - <span data-ttu-id="4b344-129">L'opzione **Interaziendale** è impostata su **No**.</span><span class="sxs-lookup"><span data-stu-id="4b344-129">The **Cross-company** option is set to **No**.</span></span>
- <span data-ttu-id="4b344-130">L'origine dati **InMemory** del tipo *Campo calcolato*.</span><span class="sxs-lookup"><span data-stu-id="4b344-130">The **InMemory** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="4b344-131">Questa origine dati contiene l'espressione `WHERE (In, In.Port <> "")`.</span><span class="sxs-lookup"><span data-stu-id="4b344-131">This data source contains the expression `WHERE (In, In.Port <> "")`.</span></span>
- <span data-ttu-id="4b344-132">L'origine dati **InFiltered** del tipo *Campo calcolato*.</span><span class="sxs-lookup"><span data-stu-id="4b344-132">The **InFiltered** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="4b344-133">Questa origine dati contiene l'espressione `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span><span class="sxs-lookup"><span data-stu-id="4b344-133">This data source contains the expression `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span></span>

<span data-ttu-id="4b344-134">Quando l'origine dati **InFiltered** è chiamata nell'ambito della società **DEMF**, viene creata una nuova tabella temporanea nel database dell'applicazione, l'elenco dei codici di identificazione dei record raccolti in memoria viene inserito in questa tabella e viene generata la seguente istruzione SQL per restituire i record filtrati della tabella **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="4b344-134">When the data source **InFiltered** is called under the context of the company **DEMF**, a new temporary table is created in the application database, the collected in memory list of record identification codes are inserted to this table, and the following SQL statement is generated to return filtered records of the **Intrastat** table.</span></span>

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a><span data-ttu-id="4b344-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4b344-135">Additional resources</span></span>

[<span data-ttu-id="4b344-136">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="4b344-136">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="4b344-137">Funzioni VALUEIN</span><span class="sxs-lookup"><span data-stu-id="4b344-137">VALUEIN functions</span></span>](er-functions-logical-valuein.md)
