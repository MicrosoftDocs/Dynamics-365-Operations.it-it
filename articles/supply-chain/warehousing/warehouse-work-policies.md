---
title: Criteri di lavoro magazzino
description: i criteri di lavoro del magazzino controllano se il lavoro del magazzino viene creato da processi di magazzino durante la produzione, in base al tipo di ordine di lavoro, all'ubicazione del magazzino e al prodotto.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 83e8dc76350e0d40a392e9a04ddca5b4b45d0da0
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="warehouse-work-policies"></a><span data-ttu-id="2633f-103">Criteri di lavoro magazzino</span><span class="sxs-lookup"><span data-stu-id="2633f-103">Warehouse work policies</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2633f-104">I criteri di lavoro del magazzino in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition controllano se il lavoro del magazzino viene creato da processi di magazzino durante la produzione, in base al tipo di ordine di lavoro, all'ubicazione del magazzino e al prodotto.</span><span class="sxs-lookup"><span data-stu-id="2633f-104">Warehouse work policies in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition control whether warehouse work is created by warehouse processes in manufacturing, based on work order type, inventory location, and product.</span></span>

<span data-ttu-id="2633f-105">Questi criteri di lavoro controllano se il lavoro del magazzino è stato creato per i processi di magazzino in fase di produzione.</span><span class="sxs-lookup"><span data-stu-id="2633f-105">This work policy controls whether warehouse work is created for warehouse processes in manufacturing.</span></span> <span data-ttu-id="2633f-106">È possibile impostare i criteri di lavoro mediante una combinazione di **tipi di ordine di lavoro**, una **ubicazione di magazzino** e un **prodotto**.</span><span class="sxs-lookup"><span data-stu-id="2633f-106">You can set up the work policy by using a combination of **work order types**, an **inventory location**, and a **product**.</span></span> <span data-ttu-id="2633f-107">Ad esempio, il prodotto L0101 viene dichiarato finito nell'ubicazione di uscita 001.</span><span class="sxs-lookup"><span data-stu-id="2633f-107">For example, product L0101 is reported as finished to output location 001.</span></span> <span data-ttu-id="2633f-108">Il prodotto finito viene successivamente consumato in un altro ordine di produzione all'ubicazione di uscita 001.</span><span class="sxs-lookup"><span data-stu-id="2633f-108">The finished good is later consumed in another production order at output location 001.</span></span> <span data-ttu-id="2633f-109">In questo caso, è possibile impostare i criteri di lavoro per impedire che lavoro per lo stoccaggio di prodotti finiti venga creato quando si dichiara il prodotto L0101 finito nell'ubicazione di uscita 001.</span><span class="sxs-lookup"><span data-stu-id="2633f-109">In this case, you can set up a work policy to prevent the work for finished goods put-away from being created when you report product L0101 as finished to output location 001.</span></span> <span data-ttu-id="2633f-110">I criteri di lavoro sono una singola entità che può essere descritta con le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="2633f-110">The work policy is an individual entity that can be described through the following information:</span></span>

-   <span data-ttu-id="2633f-111">**Nome dei criteri di lavoro**(identificatore univoco dei criteri di lavoro)</span><span class="sxs-lookup"><span data-stu-id="2633f-111">**Work policy name** (the unique identifier of the work policy)</span></span>
-   <span data-ttu-id="2633f-112">**Tipi di ordine di lavoro** e **Metodo di creazione lavoro**</span><span class="sxs-lookup"><span data-stu-id="2633f-112">**Work order types** and **Work creation method**</span></span>
-   <span data-ttu-id="2633f-113">**Ubicazioni di magazzino**</span><span class="sxs-lookup"><span data-stu-id="2633f-113">**Inventory locations**</span></span>
-   <span data-ttu-id="2633f-114">**Prodotti**</span><span class="sxs-lookup"><span data-stu-id="2633f-114">**Products**</span></span>

## <a name="work-order-types"></a><span data-ttu-id="2633f-115">Tipi di ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="2633f-115">Work order types</span></span>
<span data-ttu-id="2633f-116">È possibile scegliere i seguenti tipi di ordine di lavoro:</span><span class="sxs-lookup"><span data-stu-id="2633f-116">You can select the following work order types:</span></span>

-   <span data-ttu-id="2633f-117">Stoccaggio prodotti finiti</span><span class="sxs-lookup"><span data-stu-id="2633f-117">Finished goods put away</span></span>
-   <span data-ttu-id="2633f-118">Stoccaggio co-prodotti e sottoprodotti</span><span class="sxs-lookup"><span data-stu-id="2633f-118">Co-product and by-product put away</span></span>
-   <span data-ttu-id="2633f-119">Prelievo materie prime</span><span class="sxs-lookup"><span data-stu-id="2633f-119">Raw material picking</span></span>

<span data-ttu-id="2633f-120">Il campo **Metodo di creazione lavoro** ha il valore **Mai**.</span><span class="sxs-lookup"><span data-stu-id="2633f-120">The **Work creation method** field has the value **Never**.</span></span> <span data-ttu-id="2633f-121">Questo valore indica che i criteri di lavoro impediranno la creazione di lavoro di magazzino per il tipo di ordine di lavoro selezionato.</span><span class="sxs-lookup"><span data-stu-id="2633f-121">This value indicates that the work policy will prevent warehouse work from being created for the selected work order type.</span></span>

## <a name="inventory-locations"></a><span data-ttu-id="2633f-122">Ubicazioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="2633f-122">Inventory locations</span></span>
<span data-ttu-id="2633f-123">È possibile selezionare un'ubicazione a cui i criteri di lavoro vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="2633f-123">You can select a location that the work policy applies to.</span></span> <span data-ttu-id="2633f-124">Se non si specifica una ubicazione associata ai criteri di lavoro, i criteri di lavoro non sono applicabili ad alcun processo.</span><span class="sxs-lookup"><span data-stu-id="2633f-124">If no location is associated with a work policy, the work policy doesn’t apply to any processes.</span></span> <span data-ttu-id="2633f-125">Nella pagina **Ubicazioni**, è inoltre possibile selezionare o annullare la selezione dei criteri di lavoro per una determinata ubicazione.</span><span class="sxs-lookup"><span data-stu-id="2633f-125">On the **Locations** page, you can also select or cancel the selection of the work policy for a specific location.</span></span>

## <a name="products"></a><span data-ttu-id="2633f-126">Prodotti</span><span class="sxs-lookup"><span data-stu-id="2633f-126">Products</span></span>
<span data-ttu-id="2633f-127">È possibile selezionare un prodotto a cui i criteri di lavoro vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="2633f-127">You can select a product that the work policy applies to.</span></span> <span data-ttu-id="2633f-128">È possibile applicare i criteri di lavoro a tutti i prodotti o a prodotti selezionati.</span><span class="sxs-lookup"><span data-stu-id="2633f-128">You can apply the work policy to either all products or selected products.</span></span>

## <a name="example"></a><span data-ttu-id="2633f-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="2633f-129">Example</span></span>
<span data-ttu-id="2633f-130">Nel seguente esempio, sono presenti due ordini di produzione, PRD-001 e PRD-00*2*.</span><span class="sxs-lookup"><span data-stu-id="2633f-130">In the following example, there are two production orders, PRD-001 and PRD-00*2*.</span></span> <span data-ttu-id="2633f-131">L'ordine di produzione PRD-001 ha un'operazione denominata **Assemblaggio**, in cui il prodotto SC1 viene dichiarato finito nell'ubicazione O1.</span><span class="sxs-lookup"><span data-stu-id="2633f-131">Production order PRD-001 has an operation that is named **Assembly**, where product SC1 is being reported as finished to location O1.</span></span> <span data-ttu-id="2633f-132">L'ordine di produzione PRD-002 ha un'operazione denominata **Verniciatura** e utilizza il prodotto SC1 dall'ubicazione O1.</span><span class="sxs-lookup"><span data-stu-id="2633f-132">Production order PRD-002 has an operation that is named **Painting** and consumes product SC1 from location O1.</span></span> <span data-ttu-id="2633f-133">L'ordine di produzione PRD-002 utilizza anche le materie prime RM1 dall'ubicazione O1.</span><span class="sxs-lookup"><span data-stu-id="2633f-133">Production order PRD-002 also consumes raw material RM1 from location O1.</span></span> <span data-ttu-id="2633f-134">RM1 sono immagazzinate nell'ubicazione BULK-001 e verranno prelevate nell'ubicazione O1 dal lavoro di magazzino per il prelievo di materie prime.</span><span class="sxs-lookup"><span data-stu-id="2633f-134">RM1 is stored in warehouse location BULK-001 and will be picked to location O1 by warehouse work for raw material picking.</span></span> <span data-ttu-id="2633f-135">Il lavoro di prelievo viene generato quando l'ordine di produzione PRD-002 viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="2633f-135">The picking work is generated when production PRD-002 is released.</span></span> 

<span data-ttu-id="2633f-136">[![Criteri di lavoro magazzino](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span><span class="sxs-lookup"><span data-stu-id="2633f-136">[![Warehouse work policies](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span></span> 

<span data-ttu-id="2633f-137">Quando si pianifica di configurazione dei criteri di lavoro di magazzino per questo scenario, valutare le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="2633f-137">When you plan to configure a warehouse work policy for this scenario, you should consider the following information:</span></span>

-   <span data-ttu-id="2633f-138">Il lavoro di magazzino per lo stoccaggio di articoli finiti non è richiesto quando si dichiara SC1 come finito dall'ordine di produzione PRD-001 nell'ubicazione O1.</span><span class="sxs-lookup"><span data-stu-id="2633f-138">Warehouse work for finished goods put-away isn’t required when you report product SC1 as finished from production order PRD-001 to location O1.</span></span> <span data-ttu-id="2633f-139">Questo perché l'operazione **Verniciatura** per l'ordine di produzione PRD-002 utilizza SC1 nella stessa ubicazione.</span><span class="sxs-lookup"><span data-stu-id="2633f-139">This is because the **Painting** operation for production order PRD-002 consumes SC1 at the same location.</span></span>
-   <span data-ttu-id="2633f-140">Il lavoro di magazzino per il prelievo di materie prime è necessario per spostare le materie prime RM1 dall'ubicazione di magazzino BULK-001 all'ubicazione O1.</span><span class="sxs-lookup"><span data-stu-id="2633f-140">Warehouse work for raw material picking is required in order to move raw material RM1 from warehouse location BULK-001 to location O1.</span></span>

<span data-ttu-id="2633f-141">Di seguito è riportato un esempio dei criteri di lavoro che è possibile impostare, in base a queste considerazioni.</span><span class="sxs-lookup"><span data-stu-id="2633f-141">Here is an example of the work policy that you can set up, based on these considerations.</span></span>

|                                         |                                                       |
|-----------------------------------------|-------------------------------------------------------|
|<span data-ttu-id="2633f-142">**Nome criteri di lavoro**</span><span class="sxs-lookup"><span data-stu-id="2633f-142">**Work policy name**</span></span><br>                 |<span data-ttu-id="2633f-143">**Tipi di ordine di lavoro**</span><span class="sxs-lookup"><span data-stu-id="2633f-143">**Work order types**</span></span><br>                               |
| <span data-ttu-id="2633f-144">Nessuno stoccaggio 01     \`</span><span class="sxs-lookup"><span data-stu-id="2633f-144">No put away 01     \`</span></span>                    |<span data-ttu-id="2633f-145">- Stoccaggio prodotto finito</span><span class="sxs-lookup"><span data-stu-id="2633f-145">- Finished good put away</span></span><br>                           |
|                                         |<span data-ttu-id="2633f-146">**Ubicazioni**</span><span class="sxs-lookup"><span data-stu-id="2633f-146">**Locations**</span></span><br>                                      |
|                                         |<span data-ttu-id="2633f-147">- O1</span><span class="sxs-lookup"><span data-stu-id="2633f-147">- O1</span></span>   |                                               |
|                                         |<span data-ttu-id="2633f-148">**Prodotti**</span><span class="sxs-lookup"><span data-stu-id="2633f-148">**Products**</span></span> <br>                                      |
|                                         |<span data-ttu-id="2633f-149">- SC1</span><span class="sxs-lookup"><span data-stu-id="2633f-149">- SC1</span></span>                                                  |

<span data-ttu-id="2633f-150">Nelle procedure riportate di seguito vengono fornite istruzioni dettagliate sull'impostazione dei criteri di lavoro di magazzino per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="2633f-150">The following procedures provide step-by-step instructions about how to set up the warehouse work policy for this scenario.</span></span> <span data-ttu-id="2633f-151">Una impostazione di esempio che mostra come dichiarare finito un ordine di produzione  in un'ubicazione non controllata da targhe viene anche descritta.</span><span class="sxs-lookup"><span data-stu-id="2633f-151">A sample setup showing how to report a production order as finished to a location that isn’t license plate–controlled is also described.</span></span>

## <a name="set-up-a-warehouse-work-policy"></a><span data-ttu-id="2633f-152">Impostare criteri di lavoro magazzino</span><span class="sxs-lookup"><span data-stu-id="2633f-152">Set up a warehouse work policy</span></span>
<span data-ttu-id="2633f-153">I processi del magazzino non includono sempre il lavoro in magazzino.</span><span class="sxs-lookup"><span data-stu-id="2633f-153">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="2633f-154">Definendo i criteri di lavoro, è possibile impedire la creazione di lavoro per il prelievo delle materie prime e lo stoccaggio di prodotti finiti per un set di prodotti in ubicazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="2633f-154">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="2633f-155">La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="2633f-155">The USMF demo data company was used to create this procedure.</span></span> 

<span data-ttu-id="2633f-156">PASSAGGI (21)</span><span class="sxs-lookup"><span data-stu-id="2633f-156">STEPS (21)</span></span>

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| <span data-ttu-id="2633f-157">1</span><span class="sxs-lookup"><span data-stu-id="2633f-157">1.</span></span>  | <span data-ttu-id="2633f-158">Andare a Gestione magazzino &gt; Impostazioni &gt; Lavoro &gt; Criteri di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2633f-158">Go to Warehouse management &gt; Setup &gt; Work &gt; Work policies.</span></span>        |
| <span data-ttu-id="2633f-159">2</span><span class="sxs-lookup"><span data-stu-id="2633f-159">2.</span></span>  | <span data-ttu-id="2633f-160">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2633f-160">Click New.</span></span>                                                                 |
| <span data-ttu-id="2633f-161">3</span><span class="sxs-lookup"><span data-stu-id="2633f-161">3.</span></span>  | <span data-ttu-id="2633f-162">Nel campo Nome criteri di lavoro digitare “No lavoro di stoccaggio".</span><span class="sxs-lookup"><span data-stu-id="2633f-162">In the Work policy name field, type 'No put-away work'.</span></span>                    |
| <span data-ttu-id="2633f-163">4</span><span class="sxs-lookup"><span data-stu-id="2633f-163">4.</span></span>  | <span data-ttu-id="2633f-164">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2633f-164">Click Save.</span></span>                                                                |
| <span data-ttu-id="2633f-165">5</span><span class="sxs-lookup"><span data-stu-id="2633f-165">5.</span></span>  | <span data-ttu-id="2633f-166">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="2633f-166">Click Add.</span></span>                                                                 |
| <span data-ttu-id="2633f-167">6</span><span class="sxs-lookup"><span data-stu-id="2633f-167">6.</span></span>  | <span data-ttu-id="2633f-168">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2633f-168">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="2633f-169">7</span><span class="sxs-lookup"><span data-stu-id="2633f-169">7.</span></span>  | <span data-ttu-id="2633f-170">Nel campo Tipo ordine di lavoro selezionare "Stoccaggio prodotti finiti".</span><span class="sxs-lookup"><span data-stu-id="2633f-170">In the Work order type field, select 'Finished goods put away'.</span></span>            |
| <span data-ttu-id="2633f-171">8</span><span class="sxs-lookup"><span data-stu-id="2633f-171">8.</span></span>  | <span data-ttu-id="2633f-172">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="2633f-172">Click Add.</span></span>                                                                 |
| <span data-ttu-id="2633f-173">9</span><span class="sxs-lookup"><span data-stu-id="2633f-173">9.</span></span>  | <span data-ttu-id="2633f-174">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2633f-174">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="2633f-175">10.</span><span class="sxs-lookup"><span data-stu-id="2633f-175">10.</span></span> | <span data-ttu-id="2633f-176">Nel campo Tipo ordine di lavoro selezionare "Stoccaggio co-prodotti e sottoprodotti".</span><span class="sxs-lookup"><span data-stu-id="2633f-176">In the Work order type field, select 'Co-product and by-product put away'.</span></span> |
| <span data-ttu-id="2633f-177">11.</span><span class="sxs-lookup"><span data-stu-id="2633f-177">11.</span></span> | <span data-ttu-id="2633f-178">Espandere la sezione Ubicazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="2633f-178">Expand the Inventory locations section.</span></span>                                    |
| <span data-ttu-id="2633f-179">12.</span><span class="sxs-lookup"><span data-stu-id="2633f-179">12.</span></span> | <span data-ttu-id="2633f-180">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="2633f-180">Click Add.</span></span>                                                                 |
| <span data-ttu-id="2633f-181">13</span><span class="sxs-lookup"><span data-stu-id="2633f-181">13.</span></span> | <span data-ttu-id="2633f-182">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2633f-182">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="2633f-183">14.</span><span class="sxs-lookup"><span data-stu-id="2633f-183">14.</span></span> | <span data-ttu-id="2633f-184">Nell'elenco di magazzino immettere "51".</span><span class="sxs-lookup"><span data-stu-id="2633f-184">In the Warehouse list, enter '51'.</span></span>                                         |
| <span data-ttu-id="2633f-185">15.</span><span class="sxs-lookup"><span data-stu-id="2633f-185">15.</span></span> | <span data-ttu-id="2633f-186">Nel campo Ubicazione immettere o selezionare "001".</span><span class="sxs-lookup"><span data-stu-id="2633f-186">In the Location field, enter or select '001'.</span></span>                              |
| <span data-ttu-id="2633f-187">16.</span><span class="sxs-lookup"><span data-stu-id="2633f-187">16.</span></span> | <span data-ttu-id="2633f-188">Espandere la sezione Prodotti.</span><span class="sxs-lookup"><span data-stu-id="2633f-188">Expand the Products section.</span></span>                                               |
| <span data-ttu-id="2633f-189">17.</span><span class="sxs-lookup"><span data-stu-id="2633f-189">17.</span></span> | <span data-ttu-id="2633f-190">Nel campo Selezione prodotto selezionare "Selezionato".</span><span class="sxs-lookup"><span data-stu-id="2633f-190">In the Product selection field, select 'Selected'.</span></span>                         |
| <span data-ttu-id="2633f-191">18.</span><span class="sxs-lookup"><span data-stu-id="2633f-191">18.</span></span> | <span data-ttu-id="2633f-192">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="2633f-192">Click Add.</span></span>                                                                 |
| <span data-ttu-id="2633f-193">19.</span><span class="sxs-lookup"><span data-stu-id="2633f-193">19.</span></span> | <span data-ttu-id="2633f-194">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2633f-194">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="2633f-195">20.</span><span class="sxs-lookup"><span data-stu-id="2633f-195">20.</span></span> | <span data-ttu-id="2633f-196">Nel campo Numero articolo immettere o selezionare "L0101".</span><span class="sxs-lookup"><span data-stu-id="2633f-196">In the Item number field, enter or select 'L0101'.</span></span>                         |
| <span data-ttu-id="2633f-197">21.</span><span class="sxs-lookup"><span data-stu-id="2633f-197">21.</span></span> | <span data-ttu-id="2633f-198">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2633f-198">Click Save.</span></span>                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a><span data-ttu-id="2633f-199">Dichiarare un ordine di produzione finito in un'ubicazione non controllata da targhe</span><span class="sxs-lookup"><span data-stu-id="2633f-199">Report a production order as finished to a location that isn’t license plate–controlled</span></span>
<span data-ttu-id="2633f-200">In questa procedura è riportato un esempio di dichiarazione di finito a un'ubicazione che non controllata da targhe.</span><span class="sxs-lookup"><span data-stu-id="2633f-200">This procedure shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="2633f-201">I criteri di lavoro applicabili sono il prerequisito per questa attività.</span><span class="sxs-lookup"><span data-stu-id="2633f-201">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="2633f-202">La procedura precedente mostra l'impostazione dei criteri di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2633f-202">The previous procedure shows the setup of the work policy.</span></span> 

<span data-ttu-id="2633f-203">PASSAGGI (25)</span><span class="sxs-lookup"><span data-stu-id="2633f-203">STEPS (25)</span></span>

<table>
<tbody>
<tr>
<td colspan="3"><span data-ttu-id="2633f-204"><strong>Sottoattività: Impostare un'ubicazione di output.</strong></span><span class="sxs-lookup"><span data-stu-id="2633f-204"><strong>Sub-task: Set up an output location.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="2633f-205">Passare a Amministrazione organizzazione &gt; Risorse &gt; Gruppi di risorse.</span><span class="sxs-lookup"><span data-stu-id="2633f-205">Go to Organization administration &gt; Resources &gt; Resource groups.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="2633f-206">Nell'elenco selezionare il gruppo di risorse "5102".</span><span class="sxs-lookup"><span data-stu-id="2633f-206">In the list, select resource group '5102'.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="2633f-207">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="2633f-207">Click Edit.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="2633f-208">Nel campo Magazzino di output immettere "51".</span><span class="sxs-lookup"><span data-stu-id="2633f-208">In the Output warehouse field, enter '51'.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="2633f-209">Nel campo Ubicazione di output immettere "001".</span><span class="sxs-lookup"><span data-stu-id="2633f-209">In the Output location field, enter '001'.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="2633f-210">L'ubicazione 001 non è un'ubicazione controllata da targa.</span><span class="sxs-lookup"><span data-stu-id="2633f-210">Location 001 isn't a license plate–controlled location.</span></span> <span data-ttu-id="2633f-211">È possibile impostare un'ubicazione di output senza targa solo se i criteri di lavoro applicabili sono disponibili per l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="2633f-211">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span></td>
</tr>
<tr>
<td colspan="3"><span data-ttu-id="2633f-212"><strong>Sottoattività: Creare un ordine di produzione e segnalarlo come finito.</strong></span><span class="sxs-lookup"><span data-stu-id="2633f-212"><strong>Sub-task: Create a production order and report it as finished.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="2633f-213">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2633f-213">Close the page.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="2633f-214">Fare clic su Controllo produzione &gt; Ordini di produzione &gt; Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="2633f-214">Go to Production control &gt; Production orders &gt; All production orders.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="2633f-215">Fare clic su Nuovo ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="2633f-215">Click New production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="2633f-216">Nel campo Numero articolo immettere "L0101".</span><span class="sxs-lookup"><span data-stu-id="2633f-216">In the Item number field, enter 'L0101'.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="2633f-217">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="2633f-217">Click Create.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="2633f-218">Nel riquadro azioni, fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="2633f-218">On the Action Pane, click Production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td><span data-ttu-id="2633f-219">Fare clic su Stima.</span><span class="sxs-lookup"><span data-stu-id="2633f-219">Click Estimate.</span></span></td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td><span data-ttu-id="2633f-220">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2633f-220">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td><span data-ttu-id="2633f-221">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="2633f-221">Click Start.</span></span></td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td><span data-ttu-id="2633f-222">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="2633f-222">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td><span data-ttu-id="2633f-223">Nel campo Consumo DBA automatico selezionare "Mai".</span><span class="sxs-lookup"><span data-stu-id="2633f-223">In the Automatic BOM consumption field, select 'Never'.</span></span></td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td><span data-ttu-id="2633f-224">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2633f-224">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td><span data-ttu-id="2633f-225">Fare clic su Dichiarato finito.</span><span class="sxs-lookup"><span data-stu-id="2633f-225">Click Report as finished.</span></span></td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td><span data-ttu-id="2633f-226">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="2633f-226">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td><span data-ttu-id="2633f-227">Selezionare Sì nel campo Accetta errore.</span><span class="sxs-lookup"><span data-stu-id="2633f-227">Select Yes in the Accept error field.</span></span></td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td><span data-ttu-id="2633f-228">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2633f-228">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td><span data-ttu-id="2633f-229">Nel riquadro azioni fare clic su Magazzino.</span><span class="sxs-lookup"><span data-stu-id="2633f-229">On the Action Pane, click Warehouse.</span></span></td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td><span data-ttu-id="2633f-230">Fare clic su Dettagli lavoro.</span><span class="sxs-lookup"><span data-stu-id="2633f-230">Click Work details.</span></span></td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td><span data-ttu-id="2633f-231">Quando l'ordine di produzione è stato dichiarato finito, nessun lavoro è stato generato per lo stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="2633f-231">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="2633f-232">Questa situazione si verifica perché vengono definiti criteri di lavoro che impediscono la generazione del lavoro quando il prodotto L0101 viene dichiarato finito all'ubicazione 001.</span><span class="sxs-lookup"><span data-stu-id="2633f-232">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span></td>
</tr>
</tbody>
</table>




