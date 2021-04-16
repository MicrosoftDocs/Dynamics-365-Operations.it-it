---
title: Calcoli per il modello di configurazione prodotto
description: In questo argomento viene descritto come creare i calcoli per gli attributi in un modello di configurazione prodotto
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eaf6264f060d33575740ad38e7a65158baba296b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829620"
---
# <a name="product-configuration-model-calculations"></a><span data-ttu-id="7f4e1-103">Calcoli per il modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="7f4e1-103">Product configuration model calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7f4e1-104">In questo argomento viene descritto come creare i calcoli per gli attributi in un modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-104">This topic describes how to create calculations for attributes in a product configuration model.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7f4e1-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7f4e1-105">Prerequisites</span></span>

<span data-ttu-id="7f4e1-106">I calcoli vengono utilizzati nel modello di configurazione prodotto per calcolare i valori di configurazione per un prodotto.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-106">Calculations are used in a product configuration model to calculate the configuration values for a product.</span></span> <span data-ttu-id="7f4e1-107">Prima di poter iniziare a impostare i calcoli, è necessario che esista il modello di configurazione prodotto correlato.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-107">Before you can start to set up calculations, the related product configuration model must exist.</span></span> <span data-ttu-id="7f4e1-108">Per una panoramica del processo di configurazione per i modelli di configurazione e le attività correlate, vedi [Impostare un modello di configurazione prodotto](set-up-maintain-product-configuration-model.md).</span><span class="sxs-lookup"><span data-stu-id="7f4e1-108">For an overview of the setup process for configuration models and the related tasks, see [Set up a product configuration model](set-up-maintain-product-configuration-model.md).</span></span>

## <a name="create-a-calculation"></a><span data-ttu-id="7f4e1-109">Creare un calcolo</span><span class="sxs-lookup"><span data-stu-id="7f4e1-109">Create a calculation</span></span>

<span data-ttu-id="7f4e1-110">Un calcolo è costituito da un'espressione e da un attributo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-110">A calculation consists of an expression and a target attribute.</span></span> <span data-ttu-id="7f4e1-111">Per ulteriori informazioni vedi, [Domande frequenti sui calcoli per i modelli di configurazione prodotto](calculate-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="7f4e1-111">For more information, see [Calculations for product configuration models FAQ](calculate-product-configuration-models.md).</span></span>

<span data-ttu-id="7f4e1-112">Per creare un calcolo per un modello di prodotto esistente, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-112">To create a calculation for an existing product model, follow these steps.</span></span>

1. <span data-ttu-id="7f4e1-113">Vai a **Gestione informazioni sul prodotto \> Comune \> Modelli di configurazione prodotto**.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-113">Go to **Product information management \> Common \> Product configuration models**.</span></span>
1. <span data-ttu-id="7f4e1-114">Apri un modello di configurazione prodotto e seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-114">Open a product configuration model, and then select **Edit**.</span></span>
1. <span data-ttu-id="7f4e1-115">Nella Scheda dettaglio **Calcoli**, seleziona **Aggiungi** per aggiungere un calcolo e quindi imposta i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f4e1-115">On the **Calculations** FastTab, select **Add** to add a calculation, and then set the following fields:</span></span>

    - <span data-ttu-id="7f4e1-116">**Nome** - Immetti un nome per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-116">**Name** – Enter a name for the calculation.</span></span>
    - <span data-ttu-id="7f4e1-117">**Descrizione** - Immetti una descrizione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-117">**Description** – Enter a description of the calculation.</span></span>
    - <span data-ttu-id="7f4e1-118">**Attributo di destinazione** - Seleziona l'attributo per il quale stai effettuando il calcolo.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-118">**Target attribute** – Select the attribute that you're making the calculation for.</span></span>

1. <span data-ttu-id="7f4e1-119">Seleziona **Modifica espressione**.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-119">Select **Edit expression**.</span></span>
1. <span data-ttu-id="7f4e1-120">Nella finestra di dialogo **Immettere un calcolo**, aggiungi gli attributi, gli operatori e i valori richiesti all'espressione.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-120">In the **Enter a calculation** dialog box, add the required attributes, operators, and values to the expression.</span></span> <span data-ttu-id="7f4e1-121">Per ulteriori informazioni su come utilizzare questi elementi, vedi [Vincoli di espressione e vincoli di tabella nei modelli di configurazione del prodotto](expression-constraints-table-constraints-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="7f4e1-121">For more information about how to work with these elements, see [Expression constraints and table constraints in product configuration models](expression-constraints-table-constraints-product-configuration-models.md).</span></span>
1. <span data-ttu-id="7f4e1-122">Quando la tua espressione è pronta, seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-122">When your expression is ready, select **OK**.</span></span>

## <a name="calculation-examples"></a><span data-ttu-id="7f4e1-123">Esempi di calcolo</span><span class="sxs-lookup"><span data-stu-id="7f4e1-123">Calculation examples</span></span>

<span data-ttu-id="7f4e1-124">Questa sezione fornisce alcuni esempi che mostrano come funzionano i calcoli.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-124">This section provides a few examples that show how calculations work.</span></span>

### <a name="example-1"></a><span data-ttu-id="7f4e1-125">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="7f4e1-125">Example 1</span></span>

<span data-ttu-id="7f4e1-126">L'attributo di destinazione è booleano e il calcolo utilizza la seguente espressione condizionale:</span><span class="sxs-lookup"><span data-stu-id="7f4e1-126">The target attribute is Boolean, and the calculation uses the following conditional expression:</span></span>

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

<span data-ttu-id="7f4e1-127">Tale espressione restituisce un valore *True* all'attributo di destinazione se `decimalAttribute2` è maggiore o uguale a `decimalAttribute1`.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-127">This expression returns a value of *True* to the target attribute if `decimalAttribute2` is greater than or equal to `decimalAttribute1`.</span></span> <span data-ttu-id="7f4e1-128">In caso contrario, restituisce il valore *False*.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-128">Otherwise, it returns a value of *False*.</span></span>

### <a name="example-2"></a><span data-ttu-id="7f4e1-129">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="7f4e1-129">Example 2</span></span>

<span data-ttu-id="7f4e1-130">Questo esempio utilizza l'attributo di testo `textFixedList` come attributo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-130">This example uses the text attribute `textFixedList` as the target attribute.</span></span> <span data-ttu-id="7f4e1-131">Questo attributo contiene il seguente elenco fisso.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-131">This attribute contains the following fixed list.</span></span>

| <span data-ttu-id="7f4e1-132">Valore</span><span class="sxs-lookup"><span data-stu-id="7f4e1-132">Value</span></span> | <span data-ttu-id="7f4e1-133">Valore risolutore</span><span class="sxs-lookup"><span data-stu-id="7f4e1-133">Solver value</span></span> |
|---|---|
| <span data-ttu-id="7f4e1-134">A</span><span class="sxs-lookup"><span data-stu-id="7f4e1-134">A</span></span> | <span data-ttu-id="7f4e1-135">1a</span><span class="sxs-lookup"><span data-stu-id="7f4e1-135">1a</span></span> |
| <span data-ttu-id="7f4e1-136">B</span><span class="sxs-lookup"><span data-stu-id="7f4e1-136">B</span></span> | <span data-ttu-id="7f4e1-137">2b</span><span class="sxs-lookup"><span data-stu-id="7f4e1-137">2b</span></span> |
| <span data-ttu-id="7f4e1-138">C</span><span class="sxs-lookup"><span data-stu-id="7f4e1-138">C</span></span> | <span data-ttu-id="7f4e1-139">2c</span><span class="sxs-lookup"><span data-stu-id="7f4e1-139">2c</span></span> |

<span data-ttu-id="7f4e1-140">Lo screenshot seguente mostra come potrebbero apparire le impostazioni per questo attributo nel sistema.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-140">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="7f4e1-141">![Impostazioni del tipo di attributo per l'esempio 2](media/model-calculations-example2.png "Impostazioni del tipo di attributo per l'esempio 2")</span><span class="sxs-lookup"><span data-stu-id="7f4e1-141">![Attribute type settings for example 2](media/model-calculations-example2.png "Attribute type settings for example 2")</span></span>

<span data-ttu-id="7f4e1-142">L'attributo viene utilizzato nella seguente istruzione condizionale:</span><span class="sxs-lookup"><span data-stu-id="7f4e1-142">The attribute is used in the following conditional statement:</span></span>

`If[integerAttribute < 150, 0, 2]`

<span data-ttu-id="7f4e1-143">Se `integerAttribute` è inferiore a 150, questa istruzione restituisce il valore di testo del primo record nell'elenco fisso, *A*. In caso contrario, restituisce il valore di testo del terzo record nell'elenco fisso, *C*.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-143">If `integerAttribute` is less than 150, this statement returns the text value of the first record in the fixed list, *A*. Otherwise, it returns the text value of the third record in the fixed list, *C*.</span></span>

> [!NOTE]
> <span data-ttu-id="7f4e1-144">L'elenco fisso è equivalente a un'enumerazione in base zero (enum) e ai suoi valori si accede tramite il valore intero appropriato.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-144">The fixed list is equivalent to a zero-based enumeration (enum), and its values are accessed by the appropriate integer value.</span></span> <span data-ttu-id="7f4e1-145">Pertanto, il primo valore di elenco fisso (*A*) è abbinato a *0*, il secondo valore (*B*) è abbinato a *1* e il terzo valore (*C*) è abbinato a *2*.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-145">Therefore, the first fixed list value (*A*) is matched to *0*, the second value (*B*) is matched to *1*, and the third value (*C*) is matched to *2*.</span></span>

### <a name="example-3"></a><span data-ttu-id="7f4e1-146">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="7f4e1-146">Example 3</span></span>

<span data-ttu-id="7f4e1-147">Questo esempio utilizza l'attributo di destinazione `textFixedList` dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-147">This example uses the `textFixedList` target attribute from the previous example.</span></span> <span data-ttu-id="7f4e1-148">Utilizza anche un altro attributo di testo, `textAttribute`, che contiene il seguente elenco fisso.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-148">It also uses another text attribute, `textAttribute`, that contains the following fixed list.</span></span>

| <span data-ttu-id="7f4e1-149">Valore</span><span class="sxs-lookup"><span data-stu-id="7f4e1-149">Value</span></span> | <span data-ttu-id="7f4e1-150">Valore risolutore</span><span class="sxs-lookup"><span data-stu-id="7f4e1-150">Solver value</span></span> |
|---|---|
| <span data-ttu-id="7f4e1-151">AA</span><span class="sxs-lookup"><span data-stu-id="7f4e1-151">AA</span></span> | <span data-ttu-id="7f4e1-152">1aa</span><span class="sxs-lookup"><span data-stu-id="7f4e1-152">1aa</span></span> |
| <span data-ttu-id="7f4e1-153">BB</span><span class="sxs-lookup"><span data-stu-id="7f4e1-153">BB</span></span> | <span data-ttu-id="7f4e1-154">2bb</span><span class="sxs-lookup"><span data-stu-id="7f4e1-154">2bb</span></span> |

<span data-ttu-id="7f4e1-155">Lo screenshot seguente mostra come potrebbero apparire le impostazioni per questo attributo nel sistema.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-155">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="7f4e1-156">![Impostazioni del tipo di attributo per l'esempio 3](media/model-calculations-example3.png "Impostazioni del tipo di attributo per l'esempio 3")</span><span class="sxs-lookup"><span data-stu-id="7f4e1-156">![Attribute type settings for example 3](media/model-calculations-example3.png "Attribute type settings for example 3")</span></span>

<span data-ttu-id="7f4e1-157">Il valore per l'attributo `textFixedList` viene calcolato utilizzando la seguente istruzione condizionale:</span><span class="sxs-lookup"><span data-stu-id="7f4e1-157">The value for the `textFixedList` attribute is calculated by using the following conditional statement:</span></span>

`If[textAttribute == "1aa", 0, 2]`

<span data-ttu-id="7f4e1-158">Se il valore di `textAttribute` ha un valore di soluzione pari a *1aa*, questa espressione restituisce il valore di testo del primo record nell'elenco fisso `textFixedList`, *A*. In caso contrario, restituisce il valore di testo del terzo record nell'elenco fisso `textFixedList`, *C*.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-158">If the `textAttribute` value has a solver value that equals *1aa*, this expression returns the text value of the first record in the `textFixedList` fixed list, *A*. Otherwise, it returns the text value of the third record in the `textFixedList` fixed list, *C*.</span></span>

> [!NOTE]
> - <span data-ttu-id="7f4e1-159">L'istruzione condizionale deve utilizzare il valore di soluzione dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-159">The conditional statement must use the solver value of the attribute.</span></span>
> - <span data-ttu-id="7f4e1-160">Solo gli attributi di testo a elenco fisso possono essere utilizzati nei calcoli.</span><span class="sxs-lookup"><span data-stu-id="7f4e1-160">Only fixed-list text attributes can be used in calculations.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f4e1-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f4e1-161">See also</span></span>

- [<span data-ttu-id="7f4e1-162">Domande frequenti sui calcoli per i modelli di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="7f4e1-162">Calculations for product configuration models FAQ</span></span>](calculate-product-configuration-models.md)
- [<span data-ttu-id="7f4e1-163">Aggiungere un vincolo di espressione a un modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="7f4e1-163">Add an expression constraint to a product configuration model</span></span>](tasks/add-expression-constraint-product-configuration-model.md)
- [<span data-ttu-id="7f4e1-164">Panoramica sui modelli di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="7f4e1-164">Product configuration models overview</span></span>](product-configuration-models.md)
