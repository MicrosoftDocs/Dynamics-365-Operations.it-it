---
title: Funzione ER GETENUMVALUEBYNAME
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione GETENUMVALUEBYNAME della creazione di report elettronici (ER).
author: NickSelin
ms.date: 09/23/2020
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
ms.openlocfilehash: 72b5831e3d2bc2e839b0a569fb314a8ec074a5a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746413"
---
# <a name="getenumvaluebyname-er-function"></a><span data-ttu-id="6ba6c-103">Funzione ER GETENUMVALUEBYNAME</span><span class="sxs-lookup"><span data-stu-id="6ba6c-103">GETENUMVALUEBYNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ba6c-104">La funzione `GETENUMVALUEBYNAME` cerca un valore specifico *Enum* nell'origine dati di enumerazione specificata utilizzando il nome dell'enumerazione specificato come un valore *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="6ba6c-105">Se viene trovato il valore *Enum*, la funzione lo restituisce.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="6ba6c-106">Altrimenti, la funzione restituisce il valore di enumerazione **nullo**.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ba6c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ba6c-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="6ba6c-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6ba6c-108">Arguments</span></span>

<span data-ttu-id="6ba6c-109">`enumeration data source path`: *Enumerazione*</span><span class="sxs-lookup"><span data-stu-id="6ba6c-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="6ba6c-110">Il percorso valido di un'origine dati di uno dei seguenti tipi di enumerazione:</span><span class="sxs-lookup"><span data-stu-id="6ba6c-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="6ba6c-111">Enumerazione di modelli di creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="6ba6c-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="6ba6c-112">Enumerazione formato ER</span><span class="sxs-lookup"><span data-stu-id="6ba6c-112">ER format enumeration</span></span>
- <span data-ttu-id="6ba6c-113">Enumerazione Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="6ba6c-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="6ba6c-114">`enumeration value text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="6ba6c-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="6ba6c-115">Un valore di stringa che rappresenta il nome di un singolo valore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="6ba6c-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="6ba6c-116">Return values</span></span>

<span data-ttu-id="6ba6c-117">*Enum* nullable</span><span class="sxs-lookup"><span data-stu-id="6ba6c-117">Nullable *Enum*</span></span>

<span data-ttu-id="6ba6c-118">Il valore di enumerazione risultante.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6ba6c-119">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="6ba6c-119">Usage notes</span></span>

<span data-ttu-id="6ba6c-120">Nessuna eccezione viene generata se non viene trovato un valore *Enum* utilizzando il nome del valore di enumerazione specificato come un valore *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="6ba6c-121">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="6ba6c-121">Example 1</span></span>

<span data-ttu-id="6ba6c-122">Nella seguente figura viene illustrata l'enumerazione **ReportDirection** introdotta in un modello dati.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="6ba6c-123">Tenere presente che le etichette vengono definite per i valori dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-123">Notice that labels are defined for the enumeration values.</span></span>

![Valori disponibili per un'enumerazione del modello di dati](./media/ER-data-model-enumeration-values.PNG)

<span data-ttu-id="6ba6c-125">La figura di seguito mostra questi dettagli:</span><span class="sxs-lookup"><span data-stu-id="6ba6c-125">The following illustration shows these details:</span></span>

- <span data-ttu-id="6ba6c-126">L'origine dati **$ Direction** è configurata in un report ER.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-126">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="6ba6c-127">Questa origine dati è configurata in base all'enumerazione del modello **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-127">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="6ba6c-128">L'espressione `$IsArrivals` viene progettata per l'utilizzo dell'origine dati **$Direction** basata sull'enumerazione di modello come parametro di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-128">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="6ba6c-129">Il valore di questa espressione di confronto è **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-129">The value of this comparison expression is **TRUE**.</span></span>

![Esempio di enumerazione di modello dati](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a><span data-ttu-id="6ba6c-131">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="6ba6c-131">Example 2</span></span>

<span data-ttu-id="6ba6c-132">Le funzioni `GETENUMVALUEBYNAME` e [`LISTOFFIELDS`](er-functions-list-listoffields.md) consentono di recuperare i valori e le etichette delle enumerazioni supportate come valori di testo.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-132">The `GETENUMVALUEBYNAME` and [`LISTOFFIELDS`](er-functions-list-listoffields.md) functions let you fetch values and labels of supported enumerations as text values.</span></span> <span data-ttu-id="6ba6c-133">(Le enumerazioni supportate sono enumerazioni di applicazioni, enumerazioni di modelli di dati ed enumerazioni di formato).</span><span class="sxs-lookup"><span data-stu-id="6ba6c-133">(The supported enumerations are application enumerations, data model enumerations, and format enumerations.)</span></span>

<span data-ttu-id="6ba6c-134">Nella seguente figura viene introdotta l'origine dati **TransType** in un mapping dei modelli.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-134">In the following illustration, the **TransType** data source is introduced in a model mapping.</span></span> <span data-ttu-id="6ba6c-135">Questa origine dati fa riferimento all'enumerazione dell'applicazione **LedgerTransType**.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-135">This data source refers to the **LedgerTransType** application enumeration.</span></span>

![Origine dati di un mapping dei modelli che fa riferimento a un'enumerazione dell'applicazione](./media/er-functions-text-getenumvaluebyname-example2-1.png)

<span data-ttu-id="6ba6c-137">Nella seguente figura viene mostrata l'origine dati **TransTypeList** configurata in un mapping dei modelli.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-137">The following illustration shows the **TransTypeList** data source that is configured in a model mapping.</span></span> <span data-ttu-id="6ba6c-138">Questa origine dati è configurata in base all'enumerazione dell'applicazione **TransType**.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-138">This data source is configured based on the **TransType** application enumeration.</span></span> <span data-ttu-id="6ba6c-139">La funzione `LISTOFFIELDS` viene utilizzata per restituire tutti i valori di enumerazione come un elenco di record che contengono campi.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-139">The `LISTOFFIELDS` function is used to return all enumeration values as a list of records that contain fields.</span></span> <span data-ttu-id="6ba6c-140">In questo modo vengono esposti i dettagli di ogni valore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-140">In this way, the details of every enumeration value are exposed.</span></span>

> [!NOTE]
> <span data-ttu-id="6ba6c-141">Il campo **EnumValue** è configurato per l'origine dati **TransTypeList** utilizzando l'espressione `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-141">The **EnumValue** field is configured for the **TransTypeList** data source by using the `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` expression.</span></span> <span data-ttu-id="6ba6c-142">Questo campo restituisce un valore di enumerazione per ogni record in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-142">This field returns an enumeration value for every record in this list.</span></span>

![Origine dati di un mapping dei modelli che restituisce tutti i valori di enumerazione di un'enumerazione selezionata come elenco di record](./media/er-functions-text-getenumvaluebyname-example2-2.png)

<span data-ttu-id="6ba6c-144">Nella seguente figura viene mostrata l'origine dati **VendTrans** configurata in un mapping dei modelli.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-144">The following illustration shows the **VendTrans** data source that is configured in a model mapping.</span></span> <span data-ttu-id="6ba6c-145">Questa origine dati restituisce i record delle transazioni del fornitore dalla tabella delle applicazioni **VendTrans**.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-145">This data source returns vendor transaction records from the **VendTrans** application table.</span></span> <span data-ttu-id="6ba6c-146">Il tipo di libro mastro di ogni transazione è definito dal valore del campo **TransType**.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-146">The ledger type of every transaction is defined by the value of the **TransType** field.</span></span>

> [!NOTE]
> <span data-ttu-id="6ba6c-147">Il campo **TransTypeTitle** è configurato per l'origine dati **VendTrans** utilizzando l'espressione `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-147">The **TransTypeTitle** field is configured for the **VendTrans** data source by using the `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` expression.</span></span> <span data-ttu-id="6ba6c-148">Questo campo restituisce l'etichetta di un valore di enumerazione della transazione corrente come testo, se questo valore di enumerazione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-148">This field returns the label of an enumeration value of the current transaction as text, if this enumeration value is available.</span></span> <span data-ttu-id="6ba6c-149">In caso contrario, restituisce una valore di stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-149">Otherwise, it returns a blank string value.</span></span>
>
> <span data-ttu-id="6ba6c-150">Il campo **TransTypeTitle** è associato al campo **LedgerType** di un modello di dati che consente di utilizzare queste informazioni in ogni formato ER che utilizza il modello di dati come origine di dati.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-150">The **TransTypeTitle** field is bound to the **LedgerType** field of a data model that enables this information to be used in every ER format that uses the data model as a source of data.</span></span>

![Origine dati di un mapping dei modelli che restituisce le transazioni del fornitore](./media/er-functions-text-getenumvaluebyname-example2-3.png)

<span data-ttu-id="6ba6c-152">La figura seguente mostra come utilizzare il [debugger dell'origine dati](er-debug-data-sources.md) per testare il mapping dei modelli configurato.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-152">The following illustration shows how you can use the [data source debugger](er-debug-data-sources.md) to test the configured model mapping.</span></span>

![Utilizzo del debugger dell'origine dati per testare il mapping dei modelli configurato](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

<span data-ttu-id="6ba6c-154">Il campo **LedgerType** di un modello di dati espone le etichette dei tipi di transazione come previsto.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-154">The **LedgerType** field of a data model exposes labels of transaction types as expected.</span></span>

<span data-ttu-id="6ba6c-155">Se prevedi di utilizzare questo approccio per una grande quantità di dati transazionali, è necessario considerare le prestazioni di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6ba6c-155">If you plan to use this approach for a large amount of transactional data, you must consider execution performance.</span></span> <span data-ttu-id="6ba6c-156">Per altre informazioni, vedi [Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="6ba6c-156">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6ba6c-157">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6ba6c-157">Additional resources</span></span>

[<span data-ttu-id="6ba6c-158">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="6ba6c-158">Text functions</span></span>](er-functions-category-text.md)

[<span data-ttu-id="6ba6c-159">Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni</span><span class="sxs-lookup"><span data-stu-id="6ba6c-159">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)

[<span data-ttu-id="6ba6c-160">Funzione ER LISTOFFIELDS</span><span class="sxs-lookup"><span data-stu-id="6ba6c-160">LISTOFFIELDS ER function</span></span>](er-functions-list-listoffields.md)

[<span data-ttu-id="6ba6c-161">Funzione ER FIRSTORNULL</span><span class="sxs-lookup"><span data-stu-id="6ba6c-161">FIRSTORNULL ER function</span></span>](er-functions-list-firstornull.md)

[<span data-ttu-id="6ba6c-162">Funzione ER WHERE</span><span class="sxs-lookup"><span data-stu-id="6ba6c-162">WHERE ER function</span></span>](er-functions-list-where.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]