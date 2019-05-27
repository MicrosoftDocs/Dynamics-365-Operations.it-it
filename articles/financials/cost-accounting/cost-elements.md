---
title: Dimensioni elemento di costo
description: Uno dei pilastri fondamentali della contabilità industriale, le dimensioni elemento di costo vengono utilizzate per categorizzare e tracciare il flusso dei costi.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c703d1a9ae36d4342dc652d70dd82379187057c1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565744"
---
# <a name="cost-element-dimensions"></a><span data-ttu-id="3172e-103">Dimensioni elemento di costo</span><span class="sxs-lookup"><span data-stu-id="3172e-103">Cost element dimensions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3172e-104">Uno dei pilastri fondamentali della contabilità industriale, le dimensioni elemento di costo vengono utilizzate per categorizzare e tracciare il flusso dei costi.</span><span class="sxs-lookup"><span data-stu-id="3172e-104">As one of the core pillars in Cost accounting, cost element dimensions are used to categorize and track where costs flow to.</span></span> 

<span data-ttu-id="3172e-105">Un elemento di costo corrisponde a un articolo pertinente per i costi nel piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="3172e-105">A cost element corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="3172e-106">In sostanza, può essere qualsiasi tipo di elemento al livello più basso di un'azienda in cui i costi possono fluire.</span><span class="sxs-lookup"><span data-stu-id="3172e-106">Basically, it can be any type of element at the lowest level in a business where costs can flow to.</span></span> <span data-ttu-id="3172e-107">Gli elementi di costo come concetto variano dai conti CoGe a tutte le risorse pertinenti per i costi.</span><span class="sxs-lookup"><span data-stu-id="3172e-107">Cost elements as a concept range from ledger accounts to all cost-relevant resources.</span></span> <span data-ttu-id="3172e-108">Attualmente, la contabilità industriale supporta i conti CoGe.</span><span class="sxs-lookup"><span data-stu-id="3172e-108">Currently, Cost accounting supports ledger accounts.</span></span>

## <a name="two-types-of-cost-elements"></a><span data-ttu-id="3172e-109">Due tipi di elementi di costo</span><span class="sxs-lookup"><span data-stu-id="3172e-109">Two types of cost elements</span></span>
<span data-ttu-id="3172e-110">Sono disponibili due tipi di elementi di costo: elementi di costo primari ed elementi di costo secondari.</span><span class="sxs-lookup"><span data-stu-id="3172e-110">There are two types of cost elements: primary cost elements and secondary cost elements.</span></span> <span data-ttu-id="3172e-111">Nella tabella seguente vengono descritte le differenze tra i due tipi.</span><span class="sxs-lookup"><span data-stu-id="3172e-111">The following table describes the difference between the two types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3172e-112"><strong>Elementi di costo primari</strong></span><span class="sxs-lookup"><span data-stu-id="3172e-112"><strong>Primary cost elements</strong></span></span></td>
<td><span data-ttu-id="3172e-113"><strong>Elementi di costo secondari</strong></span><span class="sxs-lookup"><span data-stu-id="3172e-113"><strong>Secondary cost elements</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3172e-114">Gli elementi di costo primari rappresentano il flusso dei costi dalla contabilità finanziaria alla contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="3172e-114">The primary cost elements represent the flow of costs from financial accounting to cost accounting.</span></span> <span data-ttu-id="3172e-115">La struttura degli elementi di costo corrisponde alla struttura dei conti profitti e perdite in Contabilità generale, dove un elemento di costo può corrispondere a un conto principale.</span><span class="sxs-lookup"><span data-stu-id="3172e-115">The cost element structure corresponds to the profit and loss account structure in the general ledger, where a cost element can correspond to a main account.</span></span> <span data-ttu-id="3172e-116">Non tutti i conti principali possono necessariamente essere rappresentati come elementi di costo in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="3172e-116">Not all main accounts may necessarily be represented as cost elements depending on the business needs.</span></span> <span data-ttu-id="3172e-117">Esempi di elementi di costo primari sono:</span><span class="sxs-lookup"><span data-stu-id="3172e-117">Examples of primary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="3172e-118">I costi delle merci vendute (COGs)</span><span class="sxs-lookup"><span data-stu-id="3172e-118">Costs of goods sold (COGs)</span></span></li>
<li><span data-ttu-id="3172e-119">Costi indiretti materiali</span><span class="sxs-lookup"><span data-stu-id="3172e-119">Indirect material costs</span></span></li>
<li><span data-ttu-id="3172e-120">Costi del personale</span><span class="sxs-lookup"><span data-stu-id="3172e-120">Personnel costs</span></span></li>
<li><span data-ttu-id="3172e-121">Costi energetici</span><span class="sxs-lookup"><span data-stu-id="3172e-121">Energy costs</span></span></li>
</ul></td>
<td><span data-ttu-id="3172e-122">Gli elementi di costo secondari rappresentano il flusso dei costi internamente perché tali costi vengono creati e utilizzati solo nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="3172e-122">The secondary cost elements represent the flow of costs internally because these costs are created and used only in Cost accounting.</span></span> <span data-ttu-id="3172e-123">Vengono utilizzati per assicurare la traccia dell'origine dei costi.</span><span class="sxs-lookup"><span data-stu-id="3172e-123">They are used to secure that the source of costs can be traced.</span></span> <span data-ttu-id="3172e-124">Questi elementi di costo vengono utilizzati nelle allocazioni dei costi e nei calcoli dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="3172e-124">These cost elements are used in cost allocations and overhead calculations.</span></span> <span data-ttu-id="3172e-125">Esempi di elementi di costo secondari sono:</span><span class="sxs-lookup"><span data-stu-id="3172e-125">Examples of secondary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="3172e-126">Costi di produzione</span><span class="sxs-lookup"><span data-stu-id="3172e-126">Production costs</span></span></li>
<li><span data-ttu-id="3172e-127">Costi generali di produzione, materiali e marketing</span><span class="sxs-lookup"><span data-stu-id="3172e-127">Production, material, and marketing overheads</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a><span data-ttu-id="3172e-128">Dimensioni elemento di costo e membri di dimensioni elemento di costo</span><span class="sxs-lookup"><span data-stu-id="3172e-128">Cost element dimensions and cost element dimension members</span></span>
<span data-ttu-id="3172e-129">Gli elementi di costo vengono indicati come *dimensioni elemento di costo*.</span><span class="sxs-lookup"><span data-stu-id="3172e-129">Cost elements are referred to as *cost element dimensions* .</span></span> <span data-ttu-id="3172e-130">I singoli valori delle dimensioni vengono denominati *membri delle dimensioni elemento di costo*.</span><span class="sxs-lookup"><span data-stu-id="3172e-130">The individual dimension values are called *cost element dimension members*.</span></span> <span data-ttu-id="3172e-131">Ad esempio, si dispone di una struttura del piano dei conti statunitense (COA) che costituisce la base per il reporting statutario.</span><span class="sxs-lookup"><span data-stu-id="3172e-131">For example, you have a US chart of accounts structure (COA) that is the base for your statutory reporting.</span></span> <span data-ttu-id="3172e-132">Questo COA viene utilizzato come dimensione elemento di costo.</span><span class="sxs-lookup"><span data-stu-id="3172e-132">This COA is used as the cost element dimension.</span></span> <span data-ttu-id="3172e-133">I conti, ovvero elementi di costo primari, sono rappresentati come membri della dimensione elemento di costo nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="3172e-133">The accounts, which are primary cost elements, are represented as the cost element dimension members in Cost accounting.</span></span> <span data-ttu-id="3172e-134">Nella schermata seguente è illustrato un esempio dei conti principali come dimensione elemento di costo con i relativi conti principali effettivi come membri della dimensione elemento di costo.</span><span class="sxs-lookup"><span data-stu-id="3172e-134">The following screenshot shows an example of Main Accounts as the cost element dimension with its actual main accounts as the cost element dimension members.</span></span> 

<span data-ttu-id="3172e-135">[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="3172e-135">[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span></span>

## <a name="import-cost-element-dimension-members-through-data-connectors"></a><span data-ttu-id="3172e-136">Importare i membri delle dimensioni elemento di costo tramite connettori dati</span><span class="sxs-lookup"><span data-stu-id="3172e-136">Import cost element dimension members through data connectors</span></span>
<span data-ttu-id="3172e-137">Per semplificare l'impostazione dei membri delle dimensioni elemento di costo nella contabilità industriale, è possibile utilizzare connettori dati predefiniti o personalizzati per recuperare gli elementi di costo primari da uno o più sistemi di origine.</span><span class="sxs-lookup"><span data-stu-id="3172e-137">To ease the setup of cost element dimension members in Cost accounting, you can use data connectors that are either pre-built or your custom build to retrieve the primary cost elements from one or more source systems.</span></span>

## <a name="implementation-considerations"></a><span data-ttu-id="3172e-138">Considerazioni sull'implementazione</span><span class="sxs-lookup"><span data-stu-id="3172e-138">Implementation considerations</span></span>
<span data-ttu-id="3172e-139">Poiché gli elementi di costo rappresentano il livello minimo dei dettagli di costo, è necessario assicurarsi che tutti gli elementi di costo richiesti per effettuare il reporting gestionale siano inclusi durante l'implementazione della struttura degli elementi di costo.</span><span class="sxs-lookup"><span data-stu-id="3172e-139">As cost elements represent the lowest level of cost details, you should make sure that all the cost elements required to make the managerial reporting are included when you implement the cost elements structure.</span></span> <span data-ttu-id="3172e-140">Può essere una sfida individuare un numero appropriato di elementi di costo per il controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="3172e-140">It can be a challenge to find an appropriate number of cost elements for cost control.</span></span> <span data-ttu-id="3172e-141">La disponibilità di migliaia di elementi di costo può rendere difficile controllare ogni elemento di costo.</span><span class="sxs-lookup"><span data-stu-id="3172e-141">Having thousands of cost elements can make it difficult to control each cost element.</span></span> <span data-ttu-id="3172e-142">In alternativa, è possibile raggruppare gli elementi di costo e gestire il controllo costi a livello aggregato.</span><span class="sxs-lookup"><span data-stu-id="3172e-142">As an alternative, you can group cost elements and manage cost control at an aggregated level.</span></span>



