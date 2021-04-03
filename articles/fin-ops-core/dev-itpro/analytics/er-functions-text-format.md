---
title: Funzione ER FORMAT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FORMAT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: fc8b0d6e25e12165e2a89f11d3c577d5ba8c7706
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566152"
---
# <a name="format-er-function"></a><span data-ttu-id="d7411-103">Funzione ER FORMAT</span><span class="sxs-lookup"><span data-stu-id="d7411-103">FORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d7411-104">La funzione `FORMAT` restituisce la stringa specificata come un valore *Stringa* dopo che è stata formattata sostituendo tutte le occorrenze di **%N** con l'argomento *n*-esimo.</span><span class="sxs-lookup"><span data-stu-id="d7411-104">The `FORMAT` function returns the specified string as a *String* value after it has been formatted by substituting any occurrences of **%N** with the *N* th argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="d7411-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7411-105">Syntax</span></span>

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a><span data-ttu-id="d7411-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d7411-106">Arguments</span></span>

<span data-ttu-id="d7411-107">`string`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d7411-107">`string`: *String*</span></span>

<span data-ttu-id="d7411-108">Un riferimento a un'origine dati di tipo *Stringa* che deve essere formattata.</span><span class="sxs-lookup"><span data-stu-id="d7411-108">A reference to a data source of the *String* type that must be formatted.</span></span> <span data-ttu-id="d7411-109">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d7411-109">This argument is required.</span></span>

<span data-ttu-id="d7411-110">`argument 1`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d7411-110">`argument 1`: *String*</span></span>

<span data-ttu-id="d7411-111">Il primo argomento, che viene utilizzato per sostituire le occorrenze di **%1**.</span><span class="sxs-lookup"><span data-stu-id="d7411-111">The first argument, which is used to replace occurrences of **%1**.</span></span> <span data-ttu-id="d7411-112">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d7411-112">This argument is required.</span></span>

<span data-ttu-id="d7411-113">`argument N`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d7411-113">`argument N`: *String*</span></span>

<span data-ttu-id="d7411-114">L'argomento *n*-esimo, che viene utilizzato per sostituire le occorrenze di **%2**, **%3** e così via.</span><span class="sxs-lookup"><span data-stu-id="d7411-114">The *N* th argument, which is used to replace occurrences of **%2**, **%3**, and so on.</span></span> <span data-ttu-id="d7411-115">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="d7411-115">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="d7411-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="d7411-116">Return values</span></span>

<span data-ttu-id="d7411-117">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="d7411-117">*String*</span></span>

<span data-ttu-id="d7411-118">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="d7411-118">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d7411-119">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="d7411-119">Usage notes</span></span>

<span data-ttu-id="d7411-120">Se un argomento non viene fornito per un parametro, il parametro viene restituito come **"%N"** nella stringa.</span><span class="sxs-lookup"><span data-stu-id="d7411-120">If an argument isn't provided for a parameter, the parameter is returned as **"%N"** in the string.</span></span> <span data-ttu-id="d7411-121">Per i valori di tipo *Reale*, la conversione di stringhe predefinita è limitata a due posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="d7411-121">For values of the *Real* type, the default string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="d7411-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7411-122">Example</span></span>

<span data-ttu-id="d7411-123">Nell'illustrazione seguente, l'origine dati **PaymentModel** restituisce un elenco di record dei clienti utilizzando il componente **Customer**.</span><span class="sxs-lookup"><span data-stu-id="d7411-123">In the following illustration, the **PaymentModel** data source returns a list of customer records by using the **Customer** component.</span></span> <span data-ttu-id="d7411-124">Restituisce il valore della data di elaborazione utilizzando il campo **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="d7411-124">It returns the processing date value by using the **ProcessingDate** field.</span></span>

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

<span data-ttu-id="d7411-125">Nel formato creazione di report elettronici (ER) che è progettato per generare un file elettronico per i clienti selezionati, **PaymentModel** è selezionato come origine dati e controlla il flusso di processo.</span><span class="sxs-lookup"><span data-stu-id="d7411-125">In the Electronic reporting (ER) format that is designed to generate an electronic file for selected customers, **PaymentModel** is selected as a data source, and it controls the process flow.</span></span> <span data-ttu-id="d7411-126">Se un cliente selezionato viene interrotto per la data in cui il report viene elaborato, viene generata un'eccezione per informare l'utente.</span><span class="sxs-lookup"><span data-stu-id="d7411-126">If a selected customer is stopped for the date when the report is processed, an exception is thrown to notify the user.</span></span> <span data-ttu-id="d7411-127">La formula che è stata progettata per questo tipo di controllo di processo può utilizzare le risorse indicate di seguito:</span><span class="sxs-lookup"><span data-stu-id="d7411-127">The formula that is designed for this type of processing control can use the following resources:</span></span>

- <span data-ttu-id="d7411-128">Etichetta SYS70894, con il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="d7411-128">Label SYS70894, which has the following text:</span></span>

    - <span data-ttu-id="d7411-129">**Per la lingua EN-US:** "Nothing to print"</span><span class="sxs-lookup"><span data-stu-id="d7411-129">**For the EN-US language:** "Nothing to print"</span></span>
    - <span data-ttu-id="d7411-130">**Per la lingua DE:** "Nichts zu drucken"</span><span class="sxs-lookup"><span data-stu-id="d7411-130">**For the DE language:** "Nichts zu drucken"</span></span>

- <span data-ttu-id="d7411-131">Etichetta SYS18389, con il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="d7411-131">Label SYS18389, which has the following text:</span></span>

    - <span data-ttu-id="d7411-132">**Per la lingua EN-US:** "Customer %1 is stopped for %2."</span><span class="sxs-lookup"><span data-stu-id="d7411-132">**For the EN-US language:** "Customer %1 is stopped for %2."</span></span>
    - <span data-ttu-id="d7411-133">**Per la lingua DE:** "Debitor '%1' wird für %2 gesperrt."</span><span class="sxs-lookup"><span data-stu-id="d7411-133">**For the DE language:** "Debitor '%1' wird für %2 gesperrt."</span></span>

<span data-ttu-id="d7411-134">Questa è l'espressione che può essere progettata.</span><span class="sxs-lookup"><span data-stu-id="d7411-134">Here is the expression that can be designed.</span></span>

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

<span data-ttu-id="d7411-135">Se un report viene elaborato per il cliente **Litware Retail** il 17 dicembre 2015, nelle impostazioni cultura **EN-US** e la lingua **EN-US**, questa formula restituisce il seguente testo, che può essere presentato all'utente come un messaggio di eccezione:</span><span class="sxs-lookup"><span data-stu-id="d7411-135">If a report is processed for the **Litware Retail** customer on December 17, 2015, in the **EN-US** culture and the **EN-US** language, this formula returns the following text, which can be presented to the user as an exception message:</span></span>

<span data-ttu-id="d7411-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span><span class="sxs-lookup"><span data-stu-id="d7411-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span></span>

<span data-ttu-id="d7411-137">Se lo stesso viene elaborato per il cliente **Litware Retail** il 17 dicembre 2015, nelle impostazioni culture **DE** e la lingua **DE**, la formula restituisce il seguente testo, che utilizza un formato della data diverso:</span><span class="sxs-lookup"><span data-stu-id="d7411-137">If the same report is processed for the **Litware Retail** customer on December 17, 2015, in the **DE** culture and the **DE** language, the formula returns the following text, which uses a different date format:</span></span>

<span data-ttu-id="d7411-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span><span class="sxs-lookup"><span data-stu-id="d7411-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span></span>

>[!NOTE]
> <span data-ttu-id="d7411-139">La seguente sintassi si applica nelle formule ER per le etichette:</span><span class="sxs-lookup"><span data-stu-id="d7411-139">The following syntax is applied in ER formulas for labels:</span></span>
>
> - <span data-ttu-id="d7411-140">**Per le etichette di risorse nell'app Microsoft Dynamics 365 Finance:** **\@X**, dove **X** è l'ID etichetta nell' Application Object Tree (AOT)</span><span class="sxs-lookup"><span data-stu-id="d7411-140">**For labels from resources in the Microsoft Dynamics 365 Finance app:** **\@X**, where **X** is the label ID in the Application Object Tree (AOT)</span></span>
> - <span data-ttu-id="d7411-141">**Per le etichette che si trovano in configurazioni ER:** **@"GER_LABEL:X"**, dove **X** è l'ID etichetta nella configurazione ER</span><span class="sxs-lookup"><span data-stu-id="d7411-141">**For labels that reside in ER configurations:** **@"GER_LABEL:X"**, where **X** is the label ID in the ER configuration</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d7411-142">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d7411-142">Additional resources</span></span>

[<span data-ttu-id="d7411-143">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="d7411-143">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]