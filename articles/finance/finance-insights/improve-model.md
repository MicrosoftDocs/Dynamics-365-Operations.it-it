---
title: Migliorare il modello di previsione (anteprima)
description: In questo argomento vengono descritte le funzionalità che puoi utilizzare per migliorare le prestazioni dei modelli di previsione.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 184a1cb5d3851e26b41340b711c51ef38e06eb53
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186644"
---
# <a name="improve-the-prediction-model-preview"></a><span data-ttu-id="780fe-103">Migliorare il modello di previsione (anteprima)</span><span class="sxs-lookup"><span data-stu-id="780fe-103">Improve the prediction model (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="780fe-104">In questo argomento vengono descritte le funzionalità che puoi utilizzare per migliorare le prestazioni dei modelli di previsione.</span><span class="sxs-lookup"><span data-stu-id="780fe-104">This topic describes features that you can use to improve the performance of prediction models.</span></span> <span data-ttu-id="780fe-105">Il miglioramento del tuo modello inizia nell'area di lavoro **Previsioni di pagamento dei clienti** in Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="780fe-105">You start to improve your model in the **Customer payment predictions** workspace in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="780fe-106">I passaggi di miglioramento vengono quindi completati in AI Builder.</span><span class="sxs-lookup"><span data-stu-id="780fe-106">The improvement steps are then completed in AI Builder.</span></span>

## <a name="select-historical-outcomes"></a><span data-ttu-id="780fe-107">Selezionare risultati cronologici</span><span class="sxs-lookup"><span data-stu-id="780fe-107">Select historical outcomes</span></span>

<span data-ttu-id="780fe-108">Seleziona prima uno o più dei tre possibili risultati per le fatture: **Puntuale**, **In ritardo** e **Molto in ritardo**.</span><span class="sxs-lookup"><span data-stu-id="780fe-108">You first select one or more of the three possible outcomes for invoices: **On time**, **Late**, and **Very late**.</span></span> <span data-ttu-id="780fe-109">Tutti e tre i risultati dovrebbero essere selezionati.</span><span class="sxs-lookup"><span data-stu-id="780fe-109">All three outcomes should be selected.</span></span> <span data-ttu-id="780fe-110">Se deselezioni la selezione di uno qualsiasi dei risultati, le fatture verranno escluse dal processo di training e l'accuratezza della previsione verrà ridotta.</span><span class="sxs-lookup"><span data-stu-id="780fe-110">If you clear the selection of any of the outcomes, invoices will be filtered out of the training process and the accuracy of the prediction will be reduced.</span></span>

<span data-ttu-id="780fe-111">[![Conferma dei risultati](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span><span class="sxs-lookup"><span data-stu-id="780fe-111">[![Confirming outcomes](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span></span>

<span data-ttu-id="780fe-112">Se la tua organizzazione richiede solo due risultati, modifica le soglie **In ritardo** e **Molto in ritardo** su 0 (zero) giorni.</span><span class="sxs-lookup"><span data-stu-id="780fe-112">If your organization requires only two outcomes, change the **Late** and **Very late** thresholds to 0 (zero) days.</span></span> <span data-ttu-id="780fe-113">In questo modo, si comprime efficacemente la previsione in uno stato binario di **Puntuale** o **In ritardo**.</span><span class="sxs-lookup"><span data-stu-id="780fe-113">In this way, you effectively collapse the prediction to a binary state of **On time** or **Late**.</span></span>

## <a name="select-fields"></a><span data-ttu-id="780fe-114">Seleziona campi</span><span class="sxs-lookup"><span data-stu-id="780fe-114">Select fields</span></span>

<span data-ttu-id="780fe-115">Quando selezioni i campi da includere nel modello, tieni presente che l'elenco include tutti i campi disponibili nella tabella Microsoft Dataverse mappata ai dati data lake di Azure.</span><span class="sxs-lookup"><span data-stu-id="780fe-115">When you're selecting fields to include in the model, be aware that the list includes all available fields in the Microsoft Dataverse table that is mapped to the data in the Azure data lake.</span></span> <span data-ttu-id="780fe-116">Alcuni di questi campi **non** dovrebbero essere selezionati.</span><span class="sxs-lookup"><span data-stu-id="780fe-116">Some of these fields should **not** be selected.</span></span> <span data-ttu-id="780fe-117">I campi che non dovrebbero essere selezionati rientrano in una delle tre categorie:</span><span class="sxs-lookup"><span data-stu-id="780fe-117">The fields that should not be selected fall into one of three categories:</span></span>

- <span data-ttu-id="780fe-118">Il campo è obbligatorio per la tabella Dataverse, ma non ci sono dati di supporto per essa nel data lake.</span><span class="sxs-lookup"><span data-stu-id="780fe-118">The field is required for the Dataverse table, but there is no backing data for it in the data lake.</span></span>
- <span data-ttu-id="780fe-119">Il campo è un ID e quindi non ha senso per una funzionalità di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="780fe-119">The field is an ID and therefore doesn't make sense for a machine learning feature.</span></span>
- <span data-ttu-id="780fe-120">Il campo rappresenta le informazioni che non saranno disponibili durante la previsione.</span><span class="sxs-lookup"><span data-stu-id="780fe-120">The field represents information that won't be available during prediction.</span></span>

<span data-ttu-id="780fe-121">Le sezioni seguenti mostrano i campi disponibili per la fattura e le entità cliente ed elencano i campi che **non** dovrebbero essere selezionati per il training.</span><span class="sxs-lookup"><span data-stu-id="780fe-121">The following sections show the fields that are available for the invoice and customer entities, and list the fields that should **not** be selected for training.</span></span> <span data-ttu-id="780fe-122">La categoria specificata per ciascuno di questi campi fa riferimento alle categorie nell'elenco precedente.</span><span class="sxs-lookup"><span data-stu-id="780fe-122">The category that is specified for each of those fields refers to the categories in the preceding list.</span></span>
 
### <a name="invoice-dataverse-table"></a><span data-ttu-id="780fe-123">Tabella delle fatture Dataverse</span><span class="sxs-lookup"><span data-stu-id="780fe-123">Invoice Dataverse table</span></span>

<span data-ttu-id="780fe-124">Nella figura seguente vengono mostrati i campi disponibili per la tabella fattura.</span><span class="sxs-lookup"><span data-stu-id="780fe-124">The following illustration shows the fields that are available for the invoice table.</span></span>

<span data-ttu-id="780fe-125">[![Campi disponibili per la tabella fattura](./media/available-fields.png)](./media/available-fields.png)</span><span class="sxs-lookup"><span data-stu-id="780fe-125">[![Available fields for the invoice table](./media/available-fields.png)](./media/available-fields.png)</span></span>

<span data-ttu-id="780fe-126">I seguenti campi non devono essere selezionati per il training:</span><span class="sxs-lookup"><span data-stu-id="780fe-126">The following fields should not be selected for training:</span></span>

- <span data-ttu-id="780fe-127">**Conto fattura** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="780fe-127">**Invoice Account** (category 2)</span></span>
- <span data-ttu-id="780fe-128">**È chiuso** (categoria 3): questo campo viene utilizzato per filtrare le fatture per il training (chiuso) e la previsione (non chiuso).</span><span class="sxs-lookup"><span data-stu-id="780fe-128">**Is closed** (category 3) – This field is used to filter invoices for training (closed) and prediction (not closed).</span></span>
- <span data-ttu-id="780fe-129">**Nome** (categoria 1)</span><span class="sxs-lookup"><span data-stu-id="780fe-129">**Name** (category 1)</span></span>
- <span data-ttu-id="780fe-130">**ID origine** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="780fe-130">**Source Id** (category 2)</span></span>
- <span data-ttu-id="780fe-131">**Record di origine** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="780fe-131">**Source record** (category 2)</span></span>
- <span data-ttu-id="780fe-132">**Tabella di origine** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="780fe-132">**Source table** (category 2)</span></span>

### <a name="customer-dataverse-table"></a><span data-ttu-id="780fe-133">Tabella clienti Dataverse</span><span class="sxs-lookup"><span data-stu-id="780fe-133">Customer Dataverse table</span></span>

<span data-ttu-id="780fe-134">Nella figura seguente vengono mostrati i campi disponibili per la tabella cliente.</span><span class="sxs-lookup"><span data-stu-id="780fe-134">The following illustration shows the fields that are available for the customer table.</span></span>

<span data-ttu-id="780fe-135">[![Campi disponibili per la tabella cliente](./media/related-entities.png)](./media/related-entities.png)</span><span class="sxs-lookup"><span data-stu-id="780fe-135">[![Available fields for the customer table](./media/related-entities.png)](./media/related-entities.png)</span></span>

<span data-ttu-id="780fe-136">Il campo seguente non deve essere selezionato per il training:</span><span class="sxs-lookup"><span data-stu-id="780fe-136">The following field should not be selected for training:</span></span>

- <span data-ttu-id="780fe-137">**Chiave univoca riga** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="780fe-137">**Row Unique Key** (category 2)</span></span>

## <a name="filters"></a><span data-ttu-id="780fe-138">Filtri</span><span class="sxs-lookup"><span data-stu-id="780fe-138">Filters</span></span>

<span data-ttu-id="780fe-139">I filtri attualmente non supportano lo scenario di previsione dei pagamenti del cliente.</span><span class="sxs-lookup"><span data-stu-id="780fe-139">The filters don't currently support the Customer payment predictor scenario.</span></span> <span data-ttu-id="780fe-140">Pertanto, seleziona **Ignora questo passaggio** e vai alla pagina di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="780fe-140">Therefore, select **Skip this step**, and continue to the summary page.</span></span>

<span data-ttu-id="780fe-141">[![Modello stato attivo con filtri](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span><span class="sxs-lookup"><span data-stu-id="780fe-141">[![Focus model with filters](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
