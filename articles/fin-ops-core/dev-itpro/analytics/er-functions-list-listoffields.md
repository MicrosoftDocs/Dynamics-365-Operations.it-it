---
title: Funzione ER LISTOFFIELDS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LISTOFFIELDS della creazione di report elettronici (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d8d9f41d6ee5256f560c83486c95ecd47f5b081
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686514"
---
# <a name="listoffields-er-function"></a><span data-ttu-id="71253-103">Funzione ER LISTOFFIELDS</span><span class="sxs-lookup"><span data-stu-id="71253-103">LISTOFFIELDS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71253-104">La funzione `LISTOFFIELDS` restituisce un valore *Elenco di record* creato in base alla struttura dell'argomento specificato del tipo *Enumerazione* o *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="71253-104">The `LISTOFFIELDS` function returns a *Record list* value that is created based on the structure of the specified argument of the *Enumeration* or *Container (record)* type.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="71253-105">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="71253-105">Syntax 1</span></span>

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a><span data-ttu-id="71253-106">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="71253-106">Syntax 2</span></span>

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a><span data-ttu-id="71253-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="71253-107">Arguments</span></span>

<span data-ttu-id="71253-108">`path`: riferimento origine dati</span><span class="sxs-lookup"><span data-stu-id="71253-108">`path`: Data source reference</span></span>

<span data-ttu-id="71253-109">Il percorso di riferimento valido di un'origine dati di uno dei seguenti tipi di dati:</span><span class="sxs-lookup"><span data-stu-id="71253-109">The valid reference path of a data source of one of the following data types:</span></span>

- <span data-ttu-id="71253-110">Enumerazione modello</span><span class="sxs-lookup"><span data-stu-id="71253-110">Model enumeration</span></span>
- <span data-ttu-id="71253-111">Enumerazione formato</span><span class="sxs-lookup"><span data-stu-id="71253-111">Format enumeration</span></span>
- <span data-ttu-id="71253-112">Enumerazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="71253-112">Application enumeration</span></span>
- <span data-ttu-id="71253-113">Contenitore (record)</span><span class="sxs-lookup"><span data-stu-id="71253-113">Container (record)</span></span>

<span data-ttu-id="71253-114">`language`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="71253-114">`language`: *String*</span></span>

<span data-ttu-id="71253-115">Testo che rappresenta un codice lingua.</span><span class="sxs-lookup"><span data-stu-id="71253-115">Text that represents a language code.</span></span>

## <a name="return-values"></a><span data-ttu-id="71253-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="71253-116">Return values</span></span>

<span data-ttu-id="71253-117">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="71253-117">*Record list*</span></span>

<span data-ttu-id="71253-118">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="71253-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="71253-119">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="71253-119">Usage notes</span></span>

<span data-ttu-id="71253-120">L'elenco creato contiene record con i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="71253-120">The list that is created consists of records that have the following fields:</span></span>

- <span data-ttu-id="71253-121">**Nome** (tipo di dati *Stringa*)</span><span class="sxs-lookup"><span data-stu-id="71253-121">**Name** (*String* data type)</span></span>
- <span data-ttu-id="71253-122">**Etichetta** (tipo di dati *Stringa*)</span><span class="sxs-lookup"><span data-stu-id="71253-122">**Label** (*String* data type)</span></span>
- <span data-ttu-id="71253-123">**Descrizione** (tipo di dati *Stringa*)</span><span class="sxs-lookup"><span data-stu-id="71253-123">**Description** (*String* data type)</span></span>
- <span data-ttu-id="71253-124">**IsTranslated** (tipo di dati *Booleano*)</span><span class="sxs-lookup"><span data-stu-id="71253-124">**IsTranslated** (*Boolean* data type)</span></span>

<span data-ttu-id="71253-125">Se l'argomento `path` si riferisce a un'origine dati di tipo *Contenitore (Record)*, per ogni campo del record contenitore di riferimento all'elenco creato viene aggiunto un nuovo record.</span><span class="sxs-lookup"><span data-stu-id="71253-125">If the `path` argument refers to a data source of the *Container (Record)* type, for every field of the referenced container record, a new record is added to the list that is created.</span></span> <span data-ttu-id="71253-126">Per ogni record creato, il campo **Nome** restituisce il nome del campo del record contenitore di riferimento per cui è stato creato il record corrente.</span><span class="sxs-lookup"><span data-stu-id="71253-126">For every record that is created, the **Name** field returns the name of the field of the referenced container record that the current record was created for.</span></span>

<span data-ttu-id="71253-127">Se l'argomento `path` si riferisce a un'origine dati uno dei tipi *Enumerazione*, per ogni valore di enumerazione dell'enumerazione di riferimento all'elenco creato viene aggiunto un nuovo record.</span><span class="sxs-lookup"><span data-stu-id="71253-127">If the `path` argument refers to a data source of one of the *Enumeration* types, for every enumeration value of the referenced enumeration, a new record is added to the list that is created.</span></span> <span data-ttu-id="71253-128">Per ogni record creato, il campo **Nome** restituisce il valore dell'enumerazione di riferimento per cui è stato creato il record corrente, il campo **Descrizione** restituisce la descrizione dell'enumerazione e il campo **Etichetta** restituisce l'etichetta dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="71253-128">For every record that is created, the **Name** field returns the value of the referenced enumeration that the current record was created for, the **Description** field returns the description of that enumeration, and the **Label** field returns the label of that enumeration.</span></span>

<span data-ttu-id="71253-129">In fase di runtime, quando viene utilizzata la sintassi 1, i campi **Etichetta** e **Descrizione** devono restituire valori basati sulle impostazioni della lingua del formato creazione di report elettronici (ER) in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="71253-129">At runtime, when syntax 1 is used, the **Label** and **Description** fields must return values that are based on the language settings of the Electronic reporting (ER) format that is running:</span></span>

- <span data-ttu-id="71253-130">Se sono disponibili le etichette e le descrizioni per la lingua richiesta, i campi **Etichetta** e **Descrizione** restituiscono valori basati su quella lingua e il campo **IsTranslated** restituisce **True**.</span><span class="sxs-lookup"><span data-stu-id="71253-130">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="71253-131">Se le etichette e le descrizioni per la lingua richiesta non sono disponibili, i campi **Etichetta** e **Descrizione** restituiscono valori basati su quella lingua **EN-US** predefinita e il campo **IsTranslated** restituisce **False**.</span><span class="sxs-lookup"><span data-stu-id="71253-131">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the default **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

<span data-ttu-id="71253-132">In fase di runtime, quando viene utilizzata la sintassi 2, i campi **Etichetta** e **Descrizione** devono restituire valori basati sulle impostazioni della lingua definite come secondo argomento della funzione chiamata:</span><span class="sxs-lookup"><span data-stu-id="71253-132">At runtime, when syntax 2 is used, the **Label** and **Description** fields must return values that are based on the language that is defined as the second argument of the called function:</span></span>

- <span data-ttu-id="71253-133">Se sono disponibili le etichette e le descrizioni per la lingua richiesta, i campi **Etichetta** e **Descrizione** restituiscono valori basati su quella lingua e il campo **IsTranslated** restituisce **True**.</span><span class="sxs-lookup"><span data-stu-id="71253-133">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="71253-134">Se le etichette e le descrizioni per la lingua richiesta non sono disponibili, i campi **Etichetta** e **Descrizione** restituiscono valori basati su quella lingua **EN-US** e il campo **IsTranslated** restituisce **False**.</span><span class="sxs-lookup"><span data-stu-id="71253-134">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

## <a name="example-1"></a><span data-ttu-id="71253-135">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="71253-135">Example 1</span></span>

<span data-ttu-id="71253-136">Nella seguente figura viene illustrata l'enumerazione introdotta in un modello dati ER.</span><span class="sxs-lookup"><span data-stu-id="71253-136">In the following illustration, an enumeration is introduced in an ER data model.</span></span>

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

<span data-ttu-id="71253-137">La figura di seguito mostra questi dettagli:</span><span class="sxs-lookup"><span data-stu-id="71253-137">The following illustration shows these details:</span></span>

- <span data-ttu-id="71253-138">L'enumerazione del modello viene inserita in un report come origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="71253-138">The model enumeration is inserted into a report as a data source.</span></span>
- <span data-ttu-id="71253-139">Un'espressione ER utilizza l'enumerazione modello come parametro della funzione `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="71253-139">An ER expression uses the model enumeration as a parameter of the `LISTOFFIELDS` function.</span></span>
- <span data-ttu-id="71253-140">Un'origine dati del tipo *Elenco di record* viene inserita in un report mediante l'espressione ER creata.</span><span class="sxs-lookup"><span data-stu-id="71253-140">A data source of the *Record list* type is inserted into a report by using the ER expression that is created.</span></span>

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

<span data-ttu-id="71253-141">L'esempio seguente illustra gli elementi di formato ER che sono collegati all'origine dati del tipo *Elenco di record* creato utilizzando la funzione `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="71253-141">The following example shows the ER format elements that are bound to the data source of the *Record list* type that was created by using the `LISTOFFIELDS` function.</span></span>

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

<span data-ttu-id="71253-142">Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.</span><span class="sxs-lookup"><span data-stu-id="71253-142">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> <span data-ttu-id="71253-143">Il testo tradotto per le etichette e le descrizioni viene immesso nell'output del formato ER in base alle impostazioni di lingua configurate per gli elementi di formato **FILE** e **FOLDER** padre.</span><span class="sxs-lookup"><span data-stu-id="71253-143">Based on the language settings of the parent **FILE** and **FOLDER** format elements, translated text for labels and descriptions is entered in the output of the ER format.</span></span>

## <a name="example-2"></a><span data-ttu-id="71253-144">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="71253-144">Example 2</span></span>

<span data-ttu-id="71253-145">Utilizzare il tipo di origine dati *Campo calcolato* per configurare le origini dati **enumType\_de** e **enumType\_deCH** per l'enumerazione del modello dati **enumType**.</span><span class="sxs-lookup"><span data-stu-id="71253-145">You use the *Calculated field* data source type to configure **enumType\_de** and **enumType\_deCH** data sources for the **enumType** data model enumeration:</span></span>

- <span data-ttu-id="71253-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span><span class="sxs-lookup"><span data-stu-id="71253-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span></span>
- <span data-ttu-id="71253-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span><span class="sxs-lookup"><span data-stu-id="71253-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span></span>

<span data-ttu-id="71253-148">In questo caso, è possibile utilizzare la seguente espressione per visualizzare l'etichetta del valore enumerato in svizzero tedesco, se la traduzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="71253-148">In this case, you can use the following expression to get the label of the enumeration value in Swiss German, if that translation is available.</span></span> <span data-ttu-id="71253-149">Se la traduzione tedesca svizzera non è disponibile, l'etichetta è in tedesco.</span><span class="sxs-lookup"><span data-stu-id="71253-149">If the Swiss German translation isn't available, the label is in German.</span></span>

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a><span data-ttu-id="71253-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="71253-150">Additional resources</span></span>

[<span data-ttu-id="71253-151">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="71253-151">List functions</span></span>](er-functions-category-list.md)
