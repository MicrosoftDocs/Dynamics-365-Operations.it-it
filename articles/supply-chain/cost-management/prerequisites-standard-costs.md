---
title: Panoramica dei prerequisiti per costi standard
description: In questo argomento vengono descritti i passaggi di base per l'utilizzo dei costi standard.
author: AndersGirke
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f66f7061c608379689016e3c0b9c5ba4ad23dc9e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431321"
---
# <a name="prerequisites-for-standard-costs-overview"></a><span data-ttu-id="76383-103">Panoramica dei prerequisiti per costi standard</span><span class="sxs-lookup"><span data-stu-id="76383-103">Prerequisites for standard costs overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76383-104">In questo argomento vengono descritti i passaggi di base per l'utilizzo dei costi standard.</span><span class="sxs-lookup"><span data-stu-id="76383-104">This topic describes the basic steps for using standard costs.</span></span> <span data-ttu-id="76383-105">I passaggi successivi dipendono dalle operazioni svolte dalla società.</span><span class="sxs-lookup"><span data-stu-id="76383-105">Subsequent steps depend on the company's operations.</span></span> <span data-ttu-id="76383-106">Ad esempio, i passaggi variano a seconda che si operi in un ambiente non di produzione, in un ambiente di produzione che non utilizza cicli di lavorazione o in un ambiente di produzione che utilizza cicli di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="76383-106">For example, the steps differ for a nonmanufacturing environment, a manufacturing environment that doesn't use routings, and a manufacturing environment that uses routings.</span></span> 

<span data-ttu-id="76383-107">Per impostare i costi standard, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="76383-107">To set up standard costs, follow these steps.</span></span>

<span data-ttu-id="76383-108">**1. Creare un gruppo di modelli di articoli per costi standard.**</span><span class="sxs-lookup"><span data-stu-id="76383-108">**1. Create an item model group for standard costs.**</span></span>

<span data-ttu-id="76383-109">Utilizzare la pagina **Gruppi di modelli di articoli** per creare un nuovo gruppo per costi standard e assegnare un modello inventariale **Costo standard**.</span><span class="sxs-lookup"><span data-stu-id="76383-109">Use the **Item model groups** page to create a new group for standard costs, and assign an inventory model of **Standard cost**.</span></span> <span data-ttu-id="76383-110">Assegnare un identificatore significativo al gruppo di modelli di articoli, ad esempio **Costo standard**.</span><span class="sxs-lookup"><span data-stu-id="76383-110">The identifier for the item model group should be meaningful, such as **Std Cost**.</span></span> <span data-ttu-id="76383-111">Selezionare le caselle di controllo appropriate per indicare che il gruppo deve consentire le scorte finanziarie negative e che deve effettuare la registrazione dell'inventario fisico e dell'inventario finanziario.</span><span class="sxs-lookup"><span data-stu-id="76383-111">Select the check boxes to indicate that the group should allow financial negative inventory, and that it should post physical inventory and financial inventory.</span></span> <span data-ttu-id="76383-112">Questo gruppo di costi standard verrà assegnato agli articoli.</span><span class="sxs-lookup"><span data-stu-id="76383-112">This standard cost group will be assigned to items.</span></span>

<span data-ttu-id="76383-113">**2. Definire conti CoGe correlati a scostamenti dei costi standard.**</span><span class="sxs-lookup"><span data-stu-id="76383-113">**2. Define ledger accounts that are related to standard cost variances.**</span></span> 

<span data-ttu-id="76383-114">Utilizzare la pagina **Piano dei conti** per definire conti CoGe correlati a scostamenti dei costi standard.</span><span class="sxs-lookup"><span data-stu-id="76383-114">Use the **Chart of accounts** page to define ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="76383-115">Questi conti CoGe devono essere definiti prima dell'assegnazione nella pagina **Registrazione**.</span><span class="sxs-lookup"><span data-stu-id="76383-115">These ledger accounts must be defined before they can be assigned on the **Posting** page.</span></span> <span data-ttu-id="76383-116">I conti CoGe possono riflettere gruppi di articoli e gruppi di costi.</span><span class="sxs-lookup"><span data-stu-id="76383-116">The ledger accounts can reflect item groups and cost groups.</span></span>

<span data-ttu-id="76383-117">**3. Assegnare conti CoGe a registrazioni articoli correlate a scostamenti dei costi standard.**</span><span class="sxs-lookup"><span data-stu-id="76383-117">**3. Assign ledger accounts to item postings that are related to standard cost variances.**</span></span> 

<span data-ttu-id="76383-118">Utilizzare la pagina **Registrazione** per assegnare i conti CoGe correlati a scostamenti dei costi standard.</span><span class="sxs-lookup"><span data-stu-id="76383-118">Use the **Posting** page to assign the ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="76383-119">È possibile specificare il conto CoGe di uno scostamento per articolo o gruppo di articoli oppure per gruppo di costi o tipo di gruppo di costi, nonché specificare che il conto CoGe si applica a tutti gli articoli e a tutti i gruppi di costi.</span><span class="sxs-lookup"><span data-stu-id="76383-119">You can specify a variance's ledger account by item (or item group) and by cost group (or cost group type), or you can specify that the ledger account applies to all items and all cost groups.</span></span> <span data-ttu-id="76383-120">Queste opzioni corrispondono alle relazioni costi per tabelle, gruppi e tutto.</span><span class="sxs-lookup"><span data-stu-id="76383-120">These options correspond to cost relations for tables, groups, and all.</span></span> 

<span data-ttu-id="76383-121">Prima di definire le regole di registrazione articoli, utilizzare il modulo **Combinazioni di transazioni** per attivare le relazioni costi (per tabelle, gruppi e tutti gli elementi).</span><span class="sxs-lookup"><span data-stu-id="76383-121">Before you define the item posting rules, use the **Transaction combinations** page to enable cost relations (for tables, groups, and all).</span></span>

<span data-ttu-id="76383-122">**4. Definire parametri di Gestione articoli correlati ai costi standard.**</span><span class="sxs-lookup"><span data-stu-id="76383-122">**4. Define inventory parameters that are related to standard costs.**</span></span> 

-  <span data-ttu-id="76383-123">Utilizzare la scheda **Contabilità inventario** nella pagina **Impostazione criteri contabili inventario > Parametri** per definire due parametri di controllo dei costi correlati ai costi standard.</span><span class="sxs-lookup"><span data-stu-id="76383-123">Use the **Inventory accounting** tab on the **Inventory accounting policies setup > Parameters** page to define two cost control parameters that are related to standard costs.</span></span>

    -  <span data-ttu-id="76383-124">Nel campo **Scomposizione costi** selezionare **Nessuna** o **Contabilità secondaria**.</span><span class="sxs-lookup"><span data-stu-id="76383-124">In the **Cost breakdown** field, select **None** or **Sub ledger**.</span></span> <span data-ttu-id="76383-125">Se si seleziona **Contabilità secondaria**, la scomposizione dei costi sarà una scomposizione costi *attiva*.</span><span class="sxs-lookup"><span data-stu-id="76383-125">If you select **Sub ledger**, the cost breakdown is an *active* cost breakdown.</span></span> <span data-ttu-id="76383-126">La scomposizione dei costi attiva è fondamentale per il calcolo, il mantenimento e la visualizzazione della segmentazione per gruppi di costi in una struttura di prodotti multilivello per voci di costo standard.</span><span class="sxs-lookup"><span data-stu-id="76383-126">An active cost breakdown is critical for calculating, retaining, and viewing cost group segmentation across a multilevel product structure for standard cost items.</span></span> <span data-ttu-id="76383-127">Quando la scomposizione dei costi è attiva, è possibile eseguire il reporting e l'analisi dell'inventario, di WIP e del costo del venduto (COGS) per gruppo di costi in un formato a livello singolo, multilivello o totale.</span><span class="sxs-lookup"><span data-stu-id="76383-127">When the cost breakdown is active, you can report and analyze inventory, work in process (WIP), and cost of goods sold (COGS) per cost group in a single-level, multilevel, or total format.</span></span> <span data-ttu-id="76383-128">Quando la scomposizione dei costi è attiva, se si attiva un costo di un articolo prodotto, questo determina l'archiviazione della segmentazione dei gruppi di costi nel record del costo dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="76383-128">When the cost breakdown is active, if you activate a manufactured item's cost, the cost group segmentation will be stored in the item's cost record.</span></span> 

    -  <span data-ttu-id="76383-129">Se si seleziona **Nessuna**, non verrà eseguita nessuna segmentazione per gruppi di costi per le voci di costo standard.</span><span class="sxs-lookup"><span data-stu-id="76383-129">If you select **None**, cost group segmentation won't be maintained for standard cost items.</span></span> <span data-ttu-id="76383-130">Ovvero, il costo standard di un articolo prodotto verrà calcolato e gestito come singolo importo, senza segmentazione per gruppi di costi.</span><span class="sxs-lookup"><span data-stu-id="76383-130">In other words, a manufactured item's standard cost will be calculated and maintained as a single amount, without cost group segmentation.</span></span> <span data-ttu-id="76383-131">I contributi costi dei componenti prodotti verranno aggregati nell'importo singolo.</span><span class="sxs-lookup"><span data-stu-id="76383-131">The cost contributions of manufactured components will be aggregated into the single amount.</span></span>

-  <span data-ttu-id="76383-132">Nel campo **Scostamenti rispetto a standard** selezionare **Riepilogo** o **Per gruppo di costo**.</span><span class="sxs-lookup"><span data-stu-id="76383-132">In the **Variances to standard** field, select **Summarized** or **Per cost group**.</span></span> <span data-ttu-id="76383-133">Se si seleziona l'opzione **Per gruppo di costo** è possibile identificare gli scostamenti dei prezzi di acquisto e gli scostamenti produzione per gruppo di costi.</span><span class="sxs-lookup"><span data-stu-id="76383-133">If you select **Per cost group**, you can identify purchase price variances and production variances by cost group.</span></span> <span data-ttu-id="76383-134">È anche possibile di identificare i quattro tipi di scostamenti produzione, ovvero Scostamento dimensioni lotto, Scostamento quantità, Scostamento prezzi e Scostamento sostitutivo.</span><span class="sxs-lookup"><span data-stu-id="76383-134">You can also identify the four types of production variances: the lot size, quantity, price, and substitution variances.</span></span> <span data-ttu-id="76383-135">Se si seleziona **Riepilogo**, non è possibile identificare gli scostamenti per gruppo di costi né identificare i quattro tipi di scostamenti produzione.</span><span class="sxs-lookup"><span data-stu-id="76383-135">If you select **Summarized**, you can't identify variances by cost group, and you can't identify the four types of production variances.</span></span> <span data-ttu-id="76383-136">Sarà solo possibile visualizzare uno scostamento produzione riepilogativo.</span><span class="sxs-lookup"><span data-stu-id="76383-136">You can just view a summarized production variance.</span></span>

-  <span data-ttu-id="76383-137">Il criterio relativo allo scostamento rispetto al costo standard funziona in modo indipendente dal criterio di scomposizione dei costi.</span><span class="sxs-lookup"><span data-stu-id="76383-137">The policy about variance to standard works independently of the cost breakdown policy.</span></span> <span data-ttu-id="76383-138">È possibile pertanto impostare il criterio di scomposizione dei costi su **Nessuna** e gli scostamenti su Per gruppo di costo in modo che vengano comunque acquisiti gli scostamenti produzione per gruppo di costi.</span><span class="sxs-lookup"><span data-stu-id="76383-138">In other words, you can select a cost breakdown policy of **None** and select variances per cost group, so that production variances by cost group will still be captured.</span></span>

<span data-ttu-id="76383-139">**5. Creare versioni di determinazione costi per i costi standard.**</span><span class="sxs-lookup"><span data-stu-id="76383-139">**5. Create costing versions for standard costs.**</span></span> 

<span data-ttu-id="76383-140">Utilizzare la pagina **Impostazione versione di determinazione costi** per creare una o più versioni di determinazione costi per i costi standard.</span><span class="sxs-lookup"><span data-stu-id="76383-140">Use the **Costing version setup** page to create one or more costing versions for standard costs.</span></span> <span data-ttu-id="76383-141">Ciascuna versione di determinazione costi deve essere designata da un tipo di determinazione costi di **Costo standard** e deve consentire l'inclusione di dati relativi ai costi nel contenuto.</span><span class="sxs-lookup"><span data-stu-id="76383-141">Each costing version must be designated by a costing type of **Standard cost** and must allow content to include cost data.</span></span>

<span data-ttu-id="76383-142">**6. Preparare un cliente esistente per l'utilizzo dei costi standard.**</span><span class="sxs-lookup"><span data-stu-id="76383-142">**6. Prepare an existing customer to use standard costs.**</span></span> 

<span data-ttu-id="76383-143">I clienti che desiderano cambiare gli articoli esistenti e impostare un modello inventariale Costo standard devono utilizzare la pagina **Conversioni costo standard**.</span><span class="sxs-lookup"><span data-stu-id="76383-143">Customers who want to change their existing items to a standard cost inventory model must use the **Standard cost conversions** page.</span></span>


<a name="related-topics"></a><span data-ttu-id="76383-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="76383-144">Related topics</span></span>
--------

[<span data-ttu-id="76383-145">Panoramica della conversione in costo standard</span><span class="sxs-lookup"><span data-stu-id="76383-145">Standard cost conversion overview</span></span>](standard-cost-conversion-overview.md)

### <a name="blogs"></a><span data-ttu-id="76383-146">Blog</span><span class="sxs-lookup"><span data-stu-id="76383-146">Blogs</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="76383-147">Blog della Community</span><span class="sxs-lookup"><span data-stu-id="76383-147">Community blogs</span></span>

- [<span data-ttu-id="76383-148">Come impostare i costi standard per i materiali diretti in Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="76383-148">How to set up standard costs for direct materials in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [<span data-ttu-id="76383-149">Costi di manodopera diretti standard in Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="76383-149">Standard direct labor costs in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)
