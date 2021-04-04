---
title: Funzione LISTDISTINCT ER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LISTDISTINCT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 7/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: f20565d73cea8d0cc1361bd03cda86a79a97955e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563826"
---
# <a name="listdistinct-er-function"></a><span data-ttu-id="06aec-103">Funzione LISTDISTINCT ER</span><span class="sxs-lookup"><span data-stu-id="06aec-103">LISTDISTINCT ER Function</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="06aec-104">La funzione  `LISTDISTINCT` calcola l'espressione specificata come selettore per ogni record dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="06aec-104">The `LISTDISTINCT` function calculates the specified expression as a selector for every record of the specified list.</span></span> <span data-ttu-id="06aec-105">Restituisce un nuovo valore *Elenco di record* che contiene un singolo record per ogni valore del selettore univoco.</span><span class="sxs-lookup"><span data-stu-id="06aec-105">It returns a new *Record list* value that contains a single record for each unique selector value.</span></span>

## <a name="syntax"></a><span data-ttu-id="06aec-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06aec-106">Syntax</span></span>

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a><span data-ttu-id="06aec-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="06aec-107">Arguments</span></span>

<span data-ttu-id="06aec-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="06aec-108">`list`: *Record list*</span></span>

<span data-ttu-id="06aec-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="06aec-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="06aec-110">`selector`: *tipo di dati primitivi*</span><span class="sxs-lookup"><span data-stu-id="06aec-110">`selector`: *Primitive data type*</span></span>

<span data-ttu-id="06aec-111">Un'espressione valida utilizzata per calcolare un valore del selettore per ogni record nell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="06aec-111">A valid expression that is used to calculate a selector value for every record in the specified list.</span></span>

<span data-ttu-id="06aec-112">I seguenti tipi di dati sono supportati per questo parametro:</span><span class="sxs-lookup"><span data-stu-id="06aec-112">The following data types are supported for this parameter:</span></span>

- <span data-ttu-id="06aec-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="06aec-113">Boolean</span></span>
- <span data-ttu-id="06aec-114">Data</span><span class="sxs-lookup"><span data-stu-id="06aec-114">Date</span></span>
- <span data-ttu-id="06aec-115">DateTime</span><span class="sxs-lookup"><span data-stu-id="06aec-115">DateTime</span></span>
- <span data-ttu-id="06aec-116">Guid</span><span class="sxs-lookup"><span data-stu-id="06aec-116">GUID</span></span>
- <span data-ttu-id="06aec-117">Integer</span><span class="sxs-lookup"><span data-stu-id="06aec-117">Integer</span></span>
- <span data-ttu-id="06aec-118">Int64</span><span class="sxs-lookup"><span data-stu-id="06aec-118">Int64</span></span>
- <span data-ttu-id="06aec-119">Real</span><span class="sxs-lookup"><span data-stu-id="06aec-119">Real</span></span>
- <span data-ttu-id="06aec-120">String</span><span class="sxs-lookup"><span data-stu-id="06aec-120">String</span></span>

## <a name="return-values"></a><span data-ttu-id="06aec-121">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="06aec-121">Return values</span></span>

<span data-ttu-id="06aec-122">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="06aec-122">*Record list*</span></span>

<span data-ttu-id="06aec-123">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="06aec-123">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="06aec-124">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="06aec-124">Usage notes</span></span>

<span data-ttu-id="06aec-125">La struttura dell'elenco creato corrisponde alla struttura dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="06aec-125">The structure of the list that is created matches the structure of the specified list.</span></span>

<span data-ttu-id="06aec-126">Lo stesso valore del selettore potrebbe essere calcolato per più record nell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="06aec-126">The same selector value might be calculated for multiple records in the specified list.</span></span> <span data-ttu-id="06aec-127">In questo caso, i valori dei campi del record corrispondente nell'elenco creato sono uguali ai valori del primo record dell'elenco specificato per cui viene calcolato il valore del selettore.</span><span class="sxs-lookup"><span data-stu-id="06aec-127">In this case, field values of the corresponding record in the created list equal the values of the first record from the specified list that the selector value is calculated for.</span></span>

<span data-ttu-id="06aec-128">L'esecuzione di questa funzione viene effettuata su qualsiasi origine dati [Reporting elettronico (ER)](general-electronic-reporting.md) del tipo *Elenco di record* presente in memoria.</span><span class="sxs-lookup"><span data-stu-id="06aec-128">The execution of this function is done on any [Electronic reporting (ER)](general-electronic-reporting.md) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="06aec-129">L'origine dati **GROUPBY** può essere utilizzata anche per generare l'elenco di record per i quali viene calcolato il selettore con valori distinti.</span><span class="sxs-lookup"><span data-stu-id="06aec-129">The **GROUPBY** data source can also be used to generate the list of records that the selector that has distinct values is calculated for.</span></span> <span data-ttu-id="06aec-130">Tuttavia, dal punto di vista delle prestazioni e del consumo di memoria, è meglio usare la funzione `LISTDISTINCT` rispetto all'origine dati **GROUPBY**, perché l'esecuzione della funzione viene eseguita in memoria.</span><span class="sxs-lookup"><span data-stu-id="06aec-130">However, from a performance and memory consumption perspective, it's better to use the `LISTDISTINCT` function than the **GROUPBY** data source, because the execution of the function is done in memory.</span></span>

## <a name="example"></a><span data-ttu-id="06aec-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="06aec-131">Example</span></span>

<span data-ttu-id="06aec-132">L'esempio seguente mostra come ottenere l'elenco dei numeri di conto cliente univoci a cui è stata emessa almeno una fattura di vendita o una fattura di progetto durante un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="06aec-132">The following example shows how you can get the list of unique customer account numbers that at least one sales invoice or project invoice has been issued to during a specific period.</span></span>

1. <span data-ttu-id="06aec-133">Immettere l'origine dati **SalesInvoice** del tipo `Record list` che fa riferimento alla tabella delle applicazioni **CustInvoiceJour** e filtra le fatture di vendita per periodi specifici.</span><span class="sxs-lookup"><span data-stu-id="06aec-133">Enter the **SalesInvoice** data source of the `Record list` type that refers to the **CustInvoiceJour** application table and filters sales invoices for specific periods.</span></span>

    <span data-ttu-id="06aec-134">Il campo `InvoiceAccount` di questa origine dati restituisce il numero di conto di un cliente fatturato.</span><span class="sxs-lookup"><span data-stu-id="06aec-134">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

2. <span data-ttu-id="06aec-135">Immettere l'origine dati **ProjectInvoice** del tipo `Record list` che fa riferimento alla tabella delle applicazioni **ProjInvoiceJour** e filtrare le fatture del progetto per periodi specifici.</span><span class="sxs-lookup"><span data-stu-id="06aec-135">Enter the **ProjectInvoice** data source of the `Record list` type that refers to the **ProjInvoiceJour** application table and filters project invoices for specific periods.</span></span>

    <span data-ttu-id="06aec-136">Il campo `InvoiceAccount` di questa origine dati restituisce il numero di conto di un cliente fatturato.</span><span class="sxs-lookup"><span data-stu-id="06aec-136">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

3. <span data-ttu-id="06aec-137">Configuare l'origine dati **AllInvoices** del tipo `Calculated field` che contiene l'espressione `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span><span class="sxs-lookup"><span data-stu-id="06aec-137">Configure the **AllInvoices** data source of the `Calculated field` type that contains the expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span></span>

    <span data-ttu-id="06aec-138">Questa origine dati restituisce l'elenco unito di fatture di vendita e fatture di progetto.</span><span class="sxs-lookup"><span data-stu-id="06aec-138">This data source returns the joined list of sales invoices and project invoices.</span></span>

4. <span data-ttu-id="06aec-139">Configuare l'origine dati **InvoicedCustomer** del tipo `Record list` che contiene l'espressione `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span><span class="sxs-lookup"><span data-stu-id="06aec-139">Configure the **InvoicedCustomer** data source of the `Record list` type that contains the expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span></span>

    <span data-ttu-id="06aec-140">Questa origine dati restituisce un nuovo elenco che contiene un singolo record per ogni cliente univoco che è stato fatturato durante il periodo definito.</span><span class="sxs-lookup"><span data-stu-id="06aec-140">This data source returns a new list that contains a single record for every unique customer that has been invoiced during the defined period.</span></span> <span data-ttu-id="06aec-141">Il campo `InvoiceAccount` di questo elenco contiene un numero di conto cliente.</span><span class="sxs-lookup"><span data-stu-id="06aec-141">The `InvoiceAccount` field of this list contains a customer account number.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="06aec-142">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="06aec-142">Additional resources</span></span>

[<span data-ttu-id="06aec-143">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="06aec-143">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]