---
title: Risolvere i problemi del configuratore di prodotto
description: Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizza il configuratore di prodotto.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e6cfeb6a2b4166dfa9a5a5cc1b7d3d913b865ce2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999608"
---
# <a name="troubleshoot-the-product-configurator"></a><span data-ttu-id="0726c-103">Risolvere i problemi del configuratore di prodotto</span><span class="sxs-lookup"><span data-stu-id="0726c-103">Troubleshoot the product configurator</span></span>

<span data-ttu-id="0726c-104">Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizza il configuratore di prodotto.</span><span class="sxs-lookup"><span data-stu-id="0726c-104">This topic describes how to fix issues that you might encounter while you work with the product configurator.</span></span>

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a><span data-ttu-id="0726c-105">Il testo dell'articolo viene sovrascritto quando si configura un prodotto in una riga dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="0726c-105">Item text is overwritten when I configure a product on a sales order line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="0726c-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="0726c-106">Issue description</span></span>

<span data-ttu-id="0726c-107">Questo problema si verifica quando si crea una riga di ordine cliente per un articolo configurabile e quindi si modifica il testo dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="0726c-107">This issue occurs when you create a sales order line for a configurable item and then modify the item text.</span></span> <span data-ttu-id="0726c-108">Quando si configura l'articolo e quindi si seleziona **OK**, il testo viene sovrascritto con il testo standard.</span><span class="sxs-lookup"><span data-stu-id="0726c-108">When you configure the item and then select **OK**, the text is overwritten with the standard text.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="0726c-109">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="0726c-109">Issue resolution</span></span>

<span data-ttu-id="0726c-110">Questo comportamento è previsto.</span><span class="sxs-lookup"><span data-stu-id="0726c-110">This behavior is expected.</span></span> <span data-ttu-id="0726c-111">Il campo di testo include il nome della variante, che viene compilato solo dopo aver configurato la riga.</span><span class="sxs-lookup"><span data-stu-id="0726c-111">The text field includes the variant name, which is filled in only after you configure the line.</span></span> <span data-ttu-id="0726c-112">Pertanto, è necessario modificare il testo dopo aver configurato la riga, non prima.</span><span class="sxs-lookup"><span data-stu-id="0726c-112">Therefore, you must change the text after you've configured the line, not before.</span></span>

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a><span data-ttu-id="0726c-113">Gli attributi interi vengono arrotondati in modo errato quando vengono calcolati i modelli di configurazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="0726c-113">Integer attributes are incorrectly rounded when product configuration models are calculated.</span></span>

### <a name="issue-description"></a><span data-ttu-id="0726c-114">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="0726c-114">Issue description</span></span>

<span data-ttu-id="0726c-115">Questo problema può verificarsi quando si eseguono le seguenti serie di azioni:</span><span class="sxs-lookup"><span data-stu-id="0726c-115">This issue can occur when you perform the following series of actions:</span></span>

1. <span data-ttu-id="0726c-116">Impostare i seguenti attributi su un modello di configurazione di produzione:</span><span class="sxs-lookup"><span data-stu-id="0726c-116">Set up the following attributes on a production configuration model:</span></span>

    - <span data-ttu-id="0726c-117">Input (numero intero)</span><span class="sxs-lookup"><span data-stu-id="0726c-117">Input (integer)</span></span>
    - <span data-ttu-id="0726c-118">Percentuale (decimale)</span><span class="sxs-lookup"><span data-stu-id="0726c-118">Percent (decimal)</span></span>
    - <span data-ttu-id="0726c-119">Risultato (numero intero)</span><span class="sxs-lookup"><span data-stu-id="0726c-119">Result (integer)</span></span>

2. <span data-ttu-id="0726c-120">Crea un calcolo con la seguente espressione:</span><span class="sxs-lookup"><span data-stu-id="0726c-120">Create a calculation that has the following expression:</span></span>

    <span data-ttu-id="0726c-121">*Risultato* = *Input* × *Percentuale* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="0726c-121">*Result* = *Input* × *Percent* ÷ 100</span></span>

<span data-ttu-id="0726c-122">In questo caso, il risultato intero non è sempre arrotondato correttamente.</span><span class="sxs-lookup"><span data-stu-id="0726c-122">In this case, the integer result isn't always correctly rounded.</span></span> <span data-ttu-id="0726c-123">Ad esempio, l'input è 1.000 e la percentuale è 2,40.</span><span class="sxs-lookup"><span data-stu-id="0726c-123">For example, the input is 1,000, and the percentage is 2.40.</span></span> <span data-ttu-id="0726c-124">Pertanto, ci si aspetta che il risultato intero sia 24, perché il 2,40% di 1.000 è 24 (o 24,00 in formato decimale).</span><span class="sxs-lookup"><span data-stu-id="0726c-124">Therefore, you expect the integer result to be 24, because 2.40 percent of 1,000 is 24 (or 24.00 in decimal form).</span></span> <span data-ttu-id="0726c-125">Il risultato viene invece mostrato come 23.</span><span class="sxs-lookup"><span data-stu-id="0726c-125">Instead, the result is shown as 23.</span></span> <span data-ttu-id="0726c-126">Tuttavia, quando la percentuale è 2,39, il calcolo viene arrotondato a 24 anziché a 23.</span><span class="sxs-lookup"><span data-stu-id="0726c-126">However, when the percentage is 2.39, the calculation is rounded to 24 instead of 23.</span></span> <span data-ttu-id="0726c-127">Quando la percentuale è 2,50, il calcolo viene arrotondato a 25 come previsto.</span><span class="sxs-lookup"><span data-stu-id="0726c-127">When the percentage is 2.50, the calculation is rounded to 25, as expected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="0726c-128">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="0726c-128">Issue resolution</span></span>

<span data-ttu-id="0726c-129">Questo problema si verifica a causa del modo in cui Microsoft Solver Foundation internamente rappresenta i numeri utilizzando le frazioni.</span><span class="sxs-lookup"><span data-stu-id="0726c-129">This issue occurs because of the way that Microsoft Solver Foundation internally represents numbers by using fractions.</span></span> <span data-ttu-id="0726c-130">Per l'esempio precedente, il risultato del calcolo in cui la percentuale è 2,40 è rappresentato come 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375.</span><span class="sxs-lookup"><span data-stu-id="0726c-130">For the preceding example, the result of the calculation where the percentage is 2.40 is represented as 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375.</span></span> <span data-ttu-id="0726c-131">Quando .NET esegue il cast di questo valore come numero intero, restituirà 23.</span><span class="sxs-lookup"><span data-stu-id="0726c-131">When .NET casts this value as an integer, it will return 23.</span></span>

<span data-ttu-id="0726c-132">Questo comportamento non verrà modificato, perché altri scenari dipendono da esso.</span><span class="sxs-lookup"><span data-stu-id="0726c-132">This behavior won't be changed, because other scenarios depend on it.</span></span> <span data-ttu-id="0726c-133">Per l'esempio precedente, è possibile risolvere il problema introducendo un attributo decimale aggiuntivo e un calcolo.</span><span class="sxs-lookup"><span data-stu-id="0726c-133">For the preceding example, you can fix the issue by introducing an additional decimal attribute and a calculation.</span></span>

<span data-ttu-id="0726c-134">Ad esempio è possibile impostare i seguenti attributi su un modello di configurazione di produzione:</span><span class="sxs-lookup"><span data-stu-id="0726c-134">For example, you can set up the following attributes on a production configuration model:</span></span>

- <span data-ttu-id="0726c-135">Input (numero intero)</span><span class="sxs-lookup"><span data-stu-id="0726c-135">Input (integer)</span></span>
- <span data-ttu-id="0726c-136">Percentuale (decimale)</span><span class="sxs-lookup"><span data-stu-id="0726c-136">Percent (decimal)</span></span>
- <span data-ttu-id="0726c-137">Risultato decimale (decimale)</span><span class="sxs-lookup"><span data-stu-id="0726c-137">ResultDecimal (decimal)</span></span>
- <span data-ttu-id="0726c-138">Resultato intero (numero intero)</span><span class="sxs-lookup"><span data-stu-id="0726c-138">ResultInteger (integer)</span></span>

<span data-ttu-id="0726c-139">Sarà quindi possibile aggiunger i calcoli riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="0726c-139">You can then add the following calculations:</span></span>

- <span data-ttu-id="0726c-140">*Risultato decimale* = *Input* × *Percentuale* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="0726c-140">*ResultDecimal* = *Input* × *Percent* ÷ 100</span></span>
- <span data-ttu-id="0726c-141">*Risultato intero* = *Risultato decimale*</span><span class="sxs-lookup"><span data-stu-id="0726c-141">*ResultInteger* = *ResultDecimal*</span></span>
