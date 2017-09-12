--- 
title: Creare criteri di selezione di prezzo di vendita
description: In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi.
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ce805b0bf43c931ebca13720d43754c18094fc85
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="bfe45-103">Creare criteri di selezione di prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="bfe45-103">Create sales price selection criteria</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bfe45-104">In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="bfe45-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="bfe45-105">L'esecuzione di questa procedura richiede almeno un modello di prezzo di vendita disponibile.</span><span class="sxs-lookup"><span data-stu-id="bfe45-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="bfe45-106">In questo esempio viene utilizzato il modello di prezzo di vendita della soluzione Speaker nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="bfe45-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="bfe45-107">In genere, un responsabile di prodotto usa questa procedura.</span><span class="sxs-lookup"><span data-stu-id="bfe45-107">Typically, a product manager uses this procedure.</span></span>


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="bfe45-108">Aggiungere un nuovo criterio per un modello di prezzo di vendita esistente</span><span class="sxs-lookup"><span data-stu-id="bfe45-108">Add a new criterion for an existing sales price model</span></span>
1. <span data-ttu-id="bfe45-109">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="bfe45-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="bfe45-110">Fare clic su Modelli di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="bfe45-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="bfe45-111">Nell'elenco, selezionare la riga per il modello prodotto della soluzione Speaker, ma non fare clic sul collegamento corrispondente al nome del modello.</span><span class="sxs-lookup"><span data-stu-id="bfe45-111">In the list, select the row for the Speaker solution product model, but don’t click the link for the model name.</span></span>
4. <span data-ttu-id="bfe45-112">Nel riquadro azioni, fare clic su Modello.</span><span class="sxs-lookup"><span data-stu-id="bfe45-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="bfe45-113">Fare clic su Criteri modello di prezzo.</span><span class="sxs-lookup"><span data-stu-id="bfe45-113">Click Price model criteria.</span></span>
6. <span data-ttu-id="bfe45-114">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="bfe45-114">Click New.</span></span>
7. <span data-ttu-id="bfe45-115">Nel campo Nome digitare ‘Gruppo clienti 10’.</span><span class="sxs-lookup"><span data-stu-id="bfe45-115">In the Name field, type ‘Customer group 10’.</span></span>
    * <span data-ttu-id="bfe45-116">Il nome del criterio per il modello del prezzo viene utilizzato per identificare i criteri di selezione sottostanti.</span><span class="sxs-lookup"><span data-stu-id="bfe45-116">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
8. <span data-ttu-id="bfe45-117">Nel campo Modello di prezzo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bfe45-117">In the Price model field, enter or select a value.</span></span>
9. <span data-ttu-id="bfe45-118">Nel campo Tipo di ordine selezionare Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="bfe45-118">In the Order type field, select Sales order.</span></span>
    * <span data-ttu-id="bfe45-119">Il tipo di ordine determina i campi di database da rendere disponibili per la query di selezione.</span><span class="sxs-lookup"><span data-stu-id="bfe45-119">The order type determines the database fields that will be available for the selection query.</span></span>  
10. <span data-ttu-id="bfe45-120">Immettere una data nel campo Data di inizio validità.</span><span class="sxs-lookup"><span data-stu-id="bfe45-120">In the Valid from field, enter a date.</span></span>
11. <span data-ttu-id="bfe45-121">Nel campo Data scadenza immettere una data.</span><span class="sxs-lookup"><span data-stu-id="bfe45-121">In the Expire by field, enter a date.</span></span>
12. <span data-ttu-id="bfe45-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="bfe45-122">Click Save.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="bfe45-123">Creare la query per i criteri di selezione</span><span class="sxs-lookup"><span data-stu-id="bfe45-123">Create the query for the selection criteria</span></span>
1. <span data-ttu-id="bfe45-124">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="bfe45-124">Click Edit.</span></span>
2. <span data-ttu-id="bfe45-125">Selezionare Clienti nel campo Tabella.</span><span class="sxs-lookup"><span data-stu-id="bfe45-125">In the Table field, select Customers.</span></span> 
3. <span data-ttu-id="bfe45-126">Selezionare Gruppo di clienti nel campo Campo.</span><span class="sxs-lookup"><span data-stu-id="bfe45-126">In the Field field, select Customer group.</span></span>
    * <span data-ttu-id="bfe45-127">In questo esempio, useremo uno specifico gruppo di clienti per i criteri di selezione.</span><span class="sxs-lookup"><span data-stu-id="bfe45-127">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="bfe45-128">Nel campo Criteri selezionare Gruppo di clienti 10.</span><span class="sxs-lookup"><span data-stu-id="bfe45-128">In the Criteria field, select Customer group 10.</span></span> 
5. <span data-ttu-id="bfe45-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bfe45-129">Click OK.</span></span>

