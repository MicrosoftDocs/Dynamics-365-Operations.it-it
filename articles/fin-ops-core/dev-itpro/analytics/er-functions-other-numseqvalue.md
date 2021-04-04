---
title: Funzione ER NUMSEQVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMSEQVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 23dc112651e4425b8020ee5c843509b4df83e810
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563320"
---
# <a name="numseqvalue-er-function"></a><span data-ttu-id="ccb8b-103">Funzione ER NUMSEQVALUE</span><span class="sxs-lookup"><span data-stu-id="ccb8b-103">NUMSEQVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccb8b-104">La funzione `NUMSEQVALUE` restituisce un valore *Stringa* che rappresenta il nuovo valore generato di una sequenza numerica, in base alla sequenza numerica, all'ambito e all'ID ambito specificati.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-104">The `NUMSEQVALUE` function returns a *String* value that represents the new generated value of a number sequence, based on the specified number sequence, scope, and scope ID.</span></span> <span data-ttu-id="ccb8b-105">L'ID ambito equivale al codice società fornito dal contesto in cui viene eseguito il formato creazione di report elettronici (ER).</span><span class="sxs-lookup"><span data-stu-id="ccb8b-105">The scope ID equals the company code that is supplied by the context that the Electronic reporting (ER) format is run under.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="ccb8b-106">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="ccb8b-106">Syntax 1</span></span>

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a><span data-ttu-id="ccb8b-107">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="ccb8b-107">Syntax 2</span></span>

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a><span data-ttu-id="ccb8b-108">Sintassi 3</span><span class="sxs-lookup"><span data-stu-id="ccb8b-108">Syntax 3</span></span>

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a><span data-ttu-id="ccb8b-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ccb8b-109">Arguments</span></span>

<span data-ttu-id="ccb8b-110">`number sequence code`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="ccb8b-110">`number sequence code`: *String*</span></span>

<span data-ttu-id="ccb8b-111">Un valore di testo che rappresenta il codice della sequenza numerica in cui è richiesto un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-111">A text value that represents the code of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="ccb8b-112">`number sequence record ID`: *Int64*</span><span class="sxs-lookup"><span data-stu-id="ccb8b-112">`number sequence record ID`: *Int64*</span></span>

<span data-ttu-id="ccb8b-113">Un valore *Int64* che rappresenta l'ID record di un record nella tabella NumberSequenceTable che contiene la definizione della sequenza numerica in cui è richiesto un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-113">An *Int64* value that represents the record ID of a record in the NumberSequenceTable table that contains the definition of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="ccb8b-114">`scope type`: *Valore enumerazione*</span><span class="sxs-lookup"><span data-stu-id="ccb8b-114">`scope type`: *Enum value*</span></span>

<span data-ttu-id="ccb8b-115">Un valore di enumerazione dell'enumerazione **ERExpressionNumberSequenceScopeType** che definisce l'ambito della sequenza numerica in cui è richiesto un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-115">An enumeration value of the **ERExpressionNumberSequenceScopeType** enumeration that defines the scope of the number sequence that a new value is required in.</span></span> <span data-ttu-id="ccb8b-116">I tipi di ambito disponibili sono **Condiviso**, **Persona giuridica** e **Società**.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-116">The available scope types are **Shared**, **Legal entity**, and **Company**.</span></span>

<span data-ttu-id="ccb8b-117">`scope ID`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="ccb8b-117">`scope ID`: *String*</span></span>

<span data-ttu-id="ccb8b-118">Un valore *Stringa* che identifica l'ambito, in base al tipo di ambito specificato.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-118">A *String* value that identifies the scope, based on the specified scope type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ccb8b-119">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="ccb8b-119">Return values</span></span>

<span data-ttu-id="ccb8b-120">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="ccb8b-120">*String*</span></span>

<span data-ttu-id="ccb8b-121">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-121">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ccb8b-122">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="ccb8b-122">Usage notes</span></span>

<span data-ttu-id="ccb8b-123">Per il tipo di ambito **Condiviso**, specificare una stringa vuota come ID ambito.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-123">For the **Shared** scope type, specify an empty string as the scope ID.</span></span>

<span data-ttu-id="ccb8b-124">Per i tipi di ambiti **Persona giuridica** e **Società**, specificare il codice società come ID ambito.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-124">For the **Company** and **Legal entity** scope types, specify the company code as the scope ID.</span></span> <span data-ttu-id="ccb8b-125">Se si specifica una stringa vuota come ID ambito per questi tipi di ambito, il codice corrente della società viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-125">If you specify an empty string as the scope ID for these scope types, the current company code is used.</span></span>

<span data-ttu-id="ccb8b-126">Quando si utilizza la sintassi 1, la sequenza numerica è richiesta per il tipo di ambito **Società** e il codice società viene fornito dal contesto in cui viene eseguito il formato ER.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-126">When syntax 1 is used, the number sequence is requested for the **Company** scope type, and the company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-1"></a><span data-ttu-id="ccb8b-127">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="ccb8b-127">Example 1</span></span>

<span data-ttu-id="ccb8b-128">Nel formato ER, si definisce l'origine dati **AskNumSeq** del tipo *Parametro di input utente*.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-128">In your ER format, you define the **AskNumSeq** data source of the *User input parameter* type.</span></span> <span data-ttu-id="ccb8b-129">Questa origine dati fa riferimento all'Extended Data Type (EDT) **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-129">This data source refers to the **Description** extended data type (EDT).</span></span> <span data-ttu-id="ccb8b-130">Successivamente, si definisce l'origine dati **NumSeq** del tipo *Campo calcolato*.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-130">Next, you define the **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="ccb8b-131">Questa origine dati contiene l'espressione `NUMSEQVALUE (AskNumSeq)`.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-131">This data source contains the expression `NUMSEQVALUE (AskNumSeq)`.</span></span> <span data-ttu-id="ccb8b-132">Quando viene chiamata l'origine dati **NumSeq**, restituisce il nuovo valore generato della sequenza numerica che è stata specificata in fase di esecuzione immettendo il relativo codice nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-132">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that was specified at runtime by entering its code in the dialog box.</span></span> <span data-ttu-id="ccb8b-133">La sequenza numerica è richiesta per il tipo di ambito **Società**.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-133">The number sequence is requested for the **Company** scope type.</span></span> <span data-ttu-id="ccb8b-134">Il codice società viene fornito dal contesto in cui viene eseguito il formato ER.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-134">The company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-2"></a><span data-ttu-id="ccb8b-135">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="ccb8b-135">Example 2</span></span>

<span data-ttu-id="ccb8b-136">Le origini dati seguenti sono definite nel mapping di modello:</span><span class="sxs-lookup"><span data-stu-id="ccb8b-136">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="ccb8b-137">L'origine dati **LedgerParms** del tipo *Tabella*.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-137">The **LedgerParms** data source of the *Table* type.</span></span> <span data-ttu-id="ccb8b-138">Questa origine dati fa riferimento alla tabella LedgerParameters.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-138">This data source refers to the LedgerParameters table.</span></span>
- <span data-ttu-id="ccb8b-139">L'origine dati **NumSeq** del tipo *Campo calcolato*.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-139">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="ccb8b-140">Questa origine dati contiene l'espressione `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-140">This data source contains the expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span></span>

<span data-ttu-id="ccb8b-141">Se l'origine dati **NumSeq** viene chiamata, restituisce il nuovo valore generato della sequenza numerica che è stata configurata nei parametri di contabilità generaòe per la società che fornisce il contesto in cui il formato ER viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-141">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that has been configured in the General ledger parameters for the company that supplies the context that the ER format is run under.</span></span> <span data-ttu-id="ccb8b-142">Questa sequenza numerica identifica univocamente giornali di registrazione e funge da numero batch per collegare insieme le transazioni.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-142">This number sequence uniquely identifies journals and acts as a batch number that links the transactions together.</span></span>

## <a name="example-3"></a><span data-ttu-id="ccb8b-143">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="ccb8b-143">Example 3</span></span>

<span data-ttu-id="ccb8b-144">Le origini dati seguenti sono definite nel mapping di modello:</span><span class="sxs-lookup"><span data-stu-id="ccb8b-144">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="ccb8b-145">L'origine dati **enumScope** del tipo di *enumerazione* Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-145">The **enumScope** data source of the Microsoft Dynamics 365 Finance *enumeration* type.</span></span> <span data-ttu-id="ccb8b-146">Questa origine dati fa riferimento all'enumerazione **ERExpressionNumberSequenceScopeType**.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-146">This data source refers to the **ERExpressionNumberSequenceScopeType** enumeration.</span></span>
- <span data-ttu-id="ccb8b-147">L'origine dati **NumSeq** del tipo *Campo calcolato*.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-147">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="ccb8b-148">Questa origine dati contiene l'espressione `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-148">This data source contains the expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span></span>

<span data-ttu-id="ccb8b-149">Se l'origine dati **NumSeq** viene chiamata, restituisce il nuovo valore generato della sequenza numerica **Gene\_1** che è stata configurata per la società che fornisce il contesto in cui il formato ER viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-149">When the **NumSeq** data source is called, it returns the new generated value of the **Gene\_1** number sequence that has been configured for the company that supplies the context that the ER format is run under.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ccb8b-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ccb8b-150">Additional resources</span></span>

[<span data-ttu-id="ccb8b-151">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="ccb8b-151">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]