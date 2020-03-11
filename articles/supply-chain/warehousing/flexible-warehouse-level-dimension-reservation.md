---
title: Criteri flessibili di prenotazione delle dimensioni a livello di magazzino
description: In questo argomento vengono descritti i criteri di prenotazione di inventario che consentono alle aziende che vendono prodotti tracciati in batch ed eseguono la propria logistica come operazioni abilitate WMS di prenotare batch specifici per gli ordini cliente, anche se la gerarchia di prenotazioni associata ai prodotti impedisce la prenotazione di specifici batch.
author: omulvad
manager: AnnBe
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: cd6ec1013de757214db99ada02170bb6e2af96c0
ms.sourcegitcommit: f52ddcad105aac4ad2caef709751ff80caf363c0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036931"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a><span data-ttu-id="c3f69-103">Criteri flessibili di prenotazione delle dimensioni a livello di magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-103">Flexible warehouse-level dimension reservation policy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3f69-104">Quando una gerarchia di prenotazioni di inventario di tipo "Batch-below\[location\]" è associata ai prodotti, le aziende che vendono prodotti tracciati in batch ed eseguono la propria logistica come operazioni abilitate per il sistema di gestione del magazzino (Warehouse Management System, WMS) di Microsoft Dynamics 365 non possono prenotare specifici batch di tali prodotti per gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-104">When an inventory reservation hierarchy of the "Batch-below\[location\]" type is associated with products, businesses that sell batch-tracked products and run their logistics as operations that are enabled for the Microsoft Dynamics 365 Warehouse Management System (WMS) can't reserve specific batches of those products for customer sales orders.</span></span> <span data-ttu-id="c3f69-105">Questo argomento descrive i criteri di prenotazione delle scorte che consentono a queste aziende di prenotare specifici batch, anche quando i prodotti sono associati azuna gerarchia di prenotazioni "Batch-below\[location\]".</span><span class="sxs-lookup"><span data-stu-id="c3f69-105">This topic describes the inventory reservation policy that lets these businesses reserve specific batches, even when the products are associated with a "Batch-below\[location\]" reservation hierarchy.</span></span>

## <a name="inventory-reservation-hierarchy"></a><span data-ttu-id="c3f69-106">Gerarchia di prenotazioni di inventario</span><span class="sxs-lookup"><span data-stu-id="c3f69-106">Inventory reservation hierarchy</span></span>

<span data-ttu-id="c3f69-107">Questa sezione riassume la gerarchia di prenotazioni di inventario esistente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-107">This section summarizes the existing inventory reservation hierarchy.</span></span> <span data-ttu-id="c3f69-108">Descrive in particolare il modo in cui vengono gestiti gli articoli tracciati in batch e quelli tracciati in serie.</span><span class="sxs-lookup"><span data-stu-id="c3f69-108">It focuses on the way that batch-tracked and serial-tracked items are handled.</span></span>

<span data-ttu-id="c3f69-109">La gerarchia di prenotazioni di inventario impone che, per quanto riguarda le dimensioni di immagazzinamento, l'ordine con domanda include le dimensioni obbligatorie di sito, magazzino e stato delle scorte, mentre la logica di magazzino è responsabile dell'assegnazione di un'ubicazione alle quantità richieste e della prenotazione dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c3f69-109">The inventory reservation hierarchy dictates that, as far as storage dimensions are concerned, the demand order carries the mandatory dimensions of site, warehouse, and inventory status, whereas the warehouse logic is responsible for assigning a location to the requested quantities and reserving the location.</span></span> <span data-ttu-id="c3f69-110">In altre parole, nelle interazioni tra l'ordine con domanda e le operazioni di magazzino, l'ordine di domanda dovrebbe indicare da dove deve essere spedito l'ordine (ovvero, quale sito e magazzino).</span><span class="sxs-lookup"><span data-stu-id="c3f69-110">In other words, in the interactions between the demand order and the warehouse operations, the demand order is expected to indicate where the order must be shipped from (that is, what site and warehouse).</span></span> <span data-ttu-id="c3f69-111">Il magazzino si affida quindi alla relativa logica per trovare la quantità richiesta nei locali del magazzino.</span><span class="sxs-lookup"><span data-stu-id="c3f69-111">The warehouse then relies on its logic to find the required quantity in the warehouse premises.</span></span>

<span data-ttu-id="c3f69-112">Tuttavia, per riflettere il modello operativo dell'azienda, le dimensioni di tracciabilità (numeri di batch e di serie) sono soggette a maggiore flessibilità.</span><span class="sxs-lookup"><span data-stu-id="c3f69-112">However, to reflect the operational model of the business, tracking dimensions (batch and serial numbers) are subject to more flexibility.</span></span> <span data-ttu-id="c3f69-113">Una gerarchia di prenotazioni di inventario può rivelarsi appropriata per gli scenari in cui si applicano le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="c3f69-113">An inventory reservation hierarchy can accommodate scenarios where the following conditions apply:</span></span>

- <span data-ttu-id="c3f69-114">L'azienda si affida alle proprie operazioni di magazzino per gestire il prelievo di quantità che hanno numeri di batch o di serie dopo che le quantità sono state trovate nello spazio di stoccaggio del magazzino.</span><span class="sxs-lookup"><span data-stu-id="c3f69-114">The business relies on its warehouse operations to manage picking of quantities that have batch or serial numbers after the quantities have been found in the warehousing storage space.</span></span> <span data-ttu-id="c3f69-115">Questo modello viene spesso definito come *Batch-below\[location\]*.</span><span class="sxs-lookup"><span data-stu-id="c3f69-115">This model is often referred to as *Batch-below\[location\]*.</span></span> <span data-ttu-id="c3f69-116">Viene in genere utilizzato quando l'identificazione del numero di batch o di serie di un prodotto non è importante per i clienti che inoltrano la domanda alla società venditrice.</span><span class="sxs-lookup"><span data-stu-id="c3f69-116">It's typically used when a product's batch or serial number identification isn't important to the customers who place the demand with the selling company.</span></span>
- <span data-ttu-id="c3f69-117">Se i numeri di batch o di serie fanno parte di una specifica per ordini di un cliente e vengono registrati nell'ordine con domanda, le operazioni di magazzino che trovano le quantità nel magazzino sono vincolate dai numeri specifici richiesti e non possono modificarle.</span><span class="sxs-lookup"><span data-stu-id="c3f69-117">If batch or serial numbers are part of a customer's order specification, and they are recorded on the demand order, the warehouse operations that find the quantities in the warehouse are constrained by the specific requested numbers and aren't allowed to change them.</span></span> <span data-ttu-id="c3f69-118">Questo modello è definito *Batch-above\[location\]*.</span><span class="sxs-lookup"><span data-stu-id="c3f69-118">This model is referred to as *Batch-above\[location\]*.</span></span>

<span data-ttu-id="c3f69-119">In questi scenari, la difficoltà risiede nel fatto che una sola gerarchia di prenotazioni di inventario può essere assegnata a ogni prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-119">In these scenarios, the challenge is that only one inventory reservation hierarchy can be assigned to each released product.</span></span> <span data-ttu-id="c3f69-120">Pertanto, affinché WMS gestisca gli articoli tracciati, dopo che l'assegnazione della gerarchia determina quando il numero di batch o di serie deve essere prenotato (quando viene preso l'ordine con domanda o durante il lavoro di prelievo in magazzino), questa tempistica non può essere modificata su una base ad-hoc.</span><span class="sxs-lookup"><span data-stu-id="c3f69-120">Therefore, for the WMS to handle tracked items, after the hierarchy assignment determines when the batch or serial number should be reserved (either when the demand order is taken or during the warehouse picking work), this timing can't be changed on an ad-hoc basis.</span></span>

## <a name="flexible-reservation-for-batch-tracked-items"></a><span data-ttu-id="c3f69-121">Prenotazione flessibile per articoli tracciati in batch</span><span class="sxs-lookup"><span data-stu-id="c3f69-121">Flexible reservation for batch-tracked items</span></span>

### <a name="business-scenario"></a><span data-ttu-id="c3f69-122">Scenario aziendale</span><span class="sxs-lookup"><span data-stu-id="c3f69-122">Business scenario</span></span>

<span data-ttu-id="c3f69-123">In questo scenario, una società utilizza una strategia di inventario in cui i prodotti finiti vengono tracciati mediante numeri di batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-123">In this scenario, a company uses an inventory strategy where finished goods are tracked by batch numbers.</span></span> <span data-ttu-id="c3f69-124">Questa società utilizza anche il carico di lavoro WMS.</span><span class="sxs-lookup"><span data-stu-id="c3f69-124">This company also uses the WMS workload.</span></span> <span data-ttu-id="c3f69-125">Poiché questo carico di lavoro ha una logica adeguata per la pianificazione e l'esecuzione delle operazioni di prelievo e spedizione in magazzino per articoli abilitati per batch, la maggior parte degli articoli finiti è associata a una gerarchia di prenotazioni di inventario "Batch-below\[location\]".</span><span class="sxs-lookup"><span data-stu-id="c3f69-125">Because this workload has well-equipped logic for planning and running warehouse picking and shipping operations for batch-enabled items, most of the finished items are associated with a "Batch-below\[location\]" inventory reservation hierarchy.</span></span> <span data-ttu-id="c3f69-126">Il vantaggio di questo tipo di impostazione operativa è che le decisioni (che sono in realtà decisioni di prenotazione) relative a quali batch prelevare e dove stoccarli nel magazzino vengono rinviate fino all'inizio delle operazioni di prelievo in magazzino.</span><span class="sxs-lookup"><span data-stu-id="c3f69-126">The advantage of this type of operational setup is that decisions (which are effectively reservation decisions) about which batches to pick and where to put them in the warehouse are postponed until the warehouse picking operations start.</span></span> <span data-ttu-id="c3f69-127">Non vengono effettuate quando l'ordine del cliente viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="c3f69-127">They aren't made when the customer's order is placed.</span></span>

<span data-ttu-id="c3f69-128">Sebbene la gerarchia di prenotazioni "Batch-below\[location\]" soddisfi pienamente gli obiettivi di business della società, molti dei clienti usuali dell'azienda richiedono lo stesso batch che avevano acquistato in precedenza quando riordinano i prodotti.</span><span class="sxs-lookup"><span data-stu-id="c3f69-128">Although the "Batch-below\[location\]" reservation hierarchy serves the company's business goals well, many of the company's established customers require the same batch that they previously purchased when they reorder products.</span></span> <span data-ttu-id="c3f69-129">Pertanto, la società necessita di flessibilità nel modo in cui vengono gestite le regole di prenotazione di batch, di modo che, a seconda della domanda dei clienti per lo stesso articolo, si verifichino i seguenti comportamenti:</span><span class="sxs-lookup"><span data-stu-id="c3f69-129">Therefore, the company is looking for flexibility in the way that the batch reservation rules are handled, so that, depending on the customers' demand for the same item, the following behaviors occur:</span></span>

- <span data-ttu-id="c3f69-130">Un numero di batch può essere registrato e prenotato quando l'ordine viene preso dall'addetto alle vendite e non può essere modificato durante le operazioni di magazzino e/o preso da altre domande.</span><span class="sxs-lookup"><span data-stu-id="c3f69-130">A batch number can be recorded and reserved when the order is taken by the sales processor, and it can't be changed during warehouse operations and/or taken by other demands.</span></span> <span data-ttu-id="c3f69-131">Questo comportamento garantisce che il numero di batch ordinato sia spedito al cliente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-131">This behavior helps guarantee that the batch number that was ordered is shipped to the customer.</span></span>
- <span data-ttu-id="c3f69-132">Se il numero di batch non è importante per il cliente, le operazioni di magazzino possono determinare un numero di batch durante il lavoro di prelievo, dopo l'esecuzione della registrazione e della prenotazione dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-132">If the batch number isn't important to the customer, the warehouse operations can determine a batch number during picking work, after sales order registration and reservation have been done.</span></span>

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a><span data-ttu-id="c3f69-133">Consentire la prenotazione di un batch specifico nell'ordine cliente</span><span class="sxs-lookup"><span data-stu-id="c3f69-133">Allowing reservation of a specific batch on the sales order</span></span>

<span data-ttu-id="c3f69-134">Per consentire la flessibilità desiderata nel comportamento di prenotazione di batch per gli articoli associati a una gerarchia di prenotazioni di inventario "Batch-below\[location\]", i responsabili delle scorte devono selezionare la casella di controllo **Consenti prenotazione su ordine con domanda** per il livello **Numero batch** nella pagina **Gerarchie prenotazioni inventario**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-134">To accommodate the desired flexibility in the batch reservation behavior for items that are associated with a "Batch-below\[location\]" inventory reservation hierarchy, inventory managers must select the **Allow reservation on demand order** check box for the **Batch number** level on the **Inventory reservation hierarchies** page.</span></span>

![Rendere flessibile la gerarchia di prenotazioni di inventario](media/Flexible-inventory-reservation-hierarchy.png)

<span data-ttu-id="c3f69-136">Quando il livello **Numero batch** nella gerarchia è selezionato, tutte le dimensioni al di sopra di quel livello e fino al livello **Ubicazione** verranno selezionate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-136">When the **Batch number** level in the hierarchy is selected, all dimensions above that level and up through the **Location** level will be automatically selected.</span></span> <span data-ttu-id="c3f69-137">(per impostazione predefinita, tutte le dimensioni sopra il livello **Ubicazione** sono preselezionate). Questo comportamento riflette la logica in cui tutte le dimensioni nell'intervallo tra il numero di batch e l'ubicazione vengono automaticamente prenotate dopo la prenotazione di un numero di batch specifico nella riga ordine.</span><span class="sxs-lookup"><span data-stu-id="c3f69-137">(By default, all dimensions above the **Location** level are preselected.) This behavior reflects the logic where all dimensions in the range between the batch number and location are also automatically reserved after you reserve a specific batch number on the order line.</span></span>

> [!NOTE]
> <span data-ttu-id="c3f69-138">La casella di controllo **Consenti prenotazione su ordine con domanda** si applica solo ai livelli di gerarchia di prenotazioni al di sotto della dimensione di ubicazione magazzino.</span><span class="sxs-lookup"><span data-stu-id="c3f69-138">The **Allow reservation on demand order** check box applies only to reservation hierarchy levels that are below the warehouse location dimension.</span></span>
>
> <span data-ttu-id="c3f69-139">**Numero batch** è l'unico livello nella gerarchia che è aperto per i criteri di prenotazione flessibili.</span><span class="sxs-lookup"><span data-stu-id="c3f69-139">**Batch number** is the only level in the hierarchy that is open for the flexible reservation policy.</span></span> <span data-ttu-id="c3f69-140">In altre parole, non è possibile selezionare la casella di controllo **Consenti prenotazione su ordine con domanda** per il livello **Ubicazione**, **Targa** o **Numero di serie**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-140">In other words, you can't select the **Allow reservation on demand order** check box for the **Location**, **License plate**, or **Serial number** level.</span></span>
>
> <span data-ttu-id="c3f69-141">Se la gerarchia di prenotazioni include la dimensione numero di serie (che deve essere sempre inferiore al livello **Numero batch**) e la prenotazione specifica al batch per il numero di batch, il sistema continuerà a gestire le operazioni di prenotazione e prelievo di numeri di serie, in base alle regole che si applicano ai criteri di prenotazione "Serial-below\[location\]".</span><span class="sxs-lookup"><span data-stu-id="c3f69-141">If your reservation hierarchy includes the serial number dimension (which must always be below the **Batch number** level), and if you've turned on batch-specific reservation for the batch number, the system will continue to handle serial number reservation and picking operations, based on the rules that apply to the "Serial-below\[location\]" reservation policy.</span></span>

<span data-ttu-id="c3f69-142">In qualsiasi momento, è possibile consentire la prenotazione specifica al batch per una gerarchia di prenotazioni "Batch-below\[location\]" esistente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c3f69-142">At any point, you can allow batch-specific reservation for an existing "Batch-below\[location\]" reservation hierarchy in your deployment.</span></span> <span data-ttu-id="c3f69-143">Questa modifica non avrà alcun effetto sulle prenotazioni e i lavori di magazzino aperti creati prima della modifica.</span><span class="sxs-lookup"><span data-stu-id="c3f69-143">This change won't affect any reservations and open warehouse work that were created before the change occurred.</span></span> <span data-ttu-id="c3f69-144">Tuttavia, la casella di controllo **Consenti prenotazione su ordine con domanda** non può essere deselezionata se esistono operazioni di magazzino problematiche di tipo **Ordinato prenotato**, **Fisico prenotato** o **Ordinato** per uno o più articoli associati a quella gerarchia di prenotazioni.</span><span class="sxs-lookup"><span data-stu-id="c3f69-144">However, the **Allow reservation on demand order** check box can't be cleared if inventory transactions of the **Reserved ordered**, **Reserved physical**, or **Ordered** issue type exist for one or more items that are associated with that reservation hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="c3f69-145">Se la gerarchia di prenotazioni esistente di un articolo non consente la specifica del batch nell'ordine, è possibile riassegnarlo a una gerarchia di prenotazioni che consente la specifica del batch, a condizione che la struttura a livello di gerarchia sia la stessa in entrambe le gerarchie.</span><span class="sxs-lookup"><span data-stu-id="c3f69-145">If an item's existing reservation hierarchy doesn't allow batch specification on the order, you can reassign it to a reservation hierarchy that does allow batch specification, provided that the hierarchy level structure is the same in both hierarchies.</span></span> <span data-ttu-id="c3f69-146">Utilizzare la funzione **Modifica gerarchia prenotazioni per articoli** per eseguire la riassegnazione.</span><span class="sxs-lookup"><span data-stu-id="c3f69-146">Use the **Change reservation hierarchy for items** function to do the reassignment.</span></span> <span data-ttu-id="c3f69-147">Questa modifica potrebbe essere pertinente quando si desidera impedire la prenotazione flessibile di batch per un sottoinsieme di articoli tracciati in batch ma consentirla per il resto del portafoglio prodotti.</span><span class="sxs-lookup"><span data-stu-id="c3f69-147">This change might be relevant when you want to prevent flexible batch reservation for a subset of batch-tracked items but allow it for the rest of the product portfolio.</span></span>

<span data-ttu-id="c3f69-148">Indipendentemente dalla selezione o meno della casella di controllo **Consenti prenotazione su ordine con domanda**, se non si desidera prenotare uno specifico numero di batch per l'articolo in una riga ordine, la logica delle operazioni di magazzino predefinita che è valida per una gerarchia di prenotazioni "Batch-below\[location\]" verrà comunque applicata.</span><span class="sxs-lookup"><span data-stu-id="c3f69-148">Regardless of whether you've selected the **Allow reservation on demand order** check box, if you don't want to reserve a specific batch number for the item on an order line, default warehouse operations logic that is valid for a "Batch-below\[location\]" reservation hierarchy will still apply.</span></span>

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a><span data-ttu-id="c3f69-149">Prenotare un numero di batch specifico per un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="c3f69-149">Reserve a specific batch number for a customer order</span></span>

<span data-ttu-id="c3f69-150">Dopo l'impostazione di una gerarchia di prenotazioni di inventario "Batch-below\[location\] di un articolo tracciato in batch per consentire la prenotazione di specifici numeri di batch negli ordini cliente, gli addetti agli ordini cliente possono prendere gli ordini dei clienti per lo stesso articolo in uno dei seguenti modi, a seconda della richiesta del cliente:</span><span class="sxs-lookup"><span data-stu-id="c3f69-150">After a batch-tracked item's "Batch-below\[location\]" inventory reservation hierarchy is set up to allow reservation of specific batch numbers on sales orders, sales order processors can take customer orders for the same item in one of the following ways, depending on the customer's request:</span></span>

- <span data-ttu-id="c3f69-151">**Immettere i dettagli dell'ordine senza specificare un numero di batch** - Questo approccio deve essere utilizzato quando la specifica del batch del prodotto non è importante per il cliente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-151">**Enter order details without specifying a batch number** – This approach should be used when the product's batch specification isn't important to the customer.</span></span> <span data-ttu-id="c3f69-152">Tutti i processi esistenti associati alla gestione di un ordine di questo tipo nel sistema rimangono invariati.</span><span class="sxs-lookup"><span data-stu-id="c3f69-152">All existing processes that are associated with handling an order of this type in the system remain unchanged.</span></span> <span data-ttu-id="c3f69-153">Non sono richieste ulteriori considerazioni da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c3f69-153">No additional considerations are required on the part of users.</span></span>
- <span data-ttu-id="c3f69-154">**Immettere i dettagli dell'ordine e prenotare un numero di batch specifico** - Questo approccio deve essere utilizzato quando il cliente richiede un batch specifico.</span><span class="sxs-lookup"><span data-stu-id="c3f69-154">**Enter order details and reserve a specific batch number** – This approach should be used when the customer requests a specific batch.</span></span> <span data-ttu-id="c3f69-155">In genere, i clienti richiedono un batch specifico quando riordinano un prodotto che hanno acquistato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c3f69-155">Typically, customers will request a specific batch when they are reordering a product that they previously purchased.</span></span> <span data-ttu-id="c3f69-156">Questo tipo di prenotazione specifica al batch è denominato *prenotazione impegnata nell'ordine*.</span><span class="sxs-lookup"><span data-stu-id="c3f69-156">This type of batch-specific reservation is referred to as *order-committed reservation*.</span></span>

<span data-ttu-id="c3f69-157">Il seguente set di regole è valido quando le quantità vengono elaborate e un numero di batch viene impegnato in un ordine specifico:</span><span class="sxs-lookup"><span data-stu-id="c3f69-157">The following set of rules is valid when quantities are processed, and a batch number is committed to a specific order:</span></span>

- <span data-ttu-id="c3f69-158">Per consentire la prenotazione di un numero di batch specifico per un articolo secondo i criteri di prenotazione "Batch-below\[location\]", il sistema deve prenotare tutte le dimensioni fino all'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c3f69-158">To allow reservation of a specific batch number for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="c3f69-159">Questo intervallo include in genere la dimensione della targa.</span><span class="sxs-lookup"><span data-stu-id="c3f69-159">This range typically includes the license plate dimension.</span></span>
- <span data-ttu-id="c3f69-160">Le direttive sull'ubicazione non vengono utilizzate quando si crea il lavoro di prelievo per una riga di vendita che utilizza la prenotazione di batch impegnata nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c3f69-160">Location directives aren't used when picking work is created for a sales line that uses order-committed batch reservation.</span></span>
- <span data-ttu-id="c3f69-161">Durante l'elaborazione in magazzino del lavoro per i batch impegnati nell'ordine, né l'utente né il sistema possono modificare il numero di batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-161">During warehouse processing of work for order-committed batches, neither the user nor the system is allowed to change the batch number.</span></span> <span data-ttu-id="c3f69-162">(questa elaborazione include la gestione delle eccezioni).</span><span class="sxs-lookup"><span data-stu-id="c3f69-162">(This processing includes exception handling.)</span></span>

<span data-ttu-id="c3f69-163">L'esempio seguente mostra il flusso end-to-end.</span><span class="sxs-lookup"><span data-stu-id="c3f69-163">The following example shows the end-to-end flow.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="c3f69-164">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="c3f69-164">Example scenario</span></span>

<span data-ttu-id="c3f69-165">Per questo esempio, i dati dimostrativi devono essere installati ed è necessario utilizzare la società di dati dimostrativi **USMF**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-165">For this example, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><span data-ttu-id="c3f69-166">Impostare una gerarchia di prenotazioni di inventario per consentire la prenotazione specifica al batch</span><span class="sxs-lookup"><span data-stu-id="c3f69-166">Set up an inventory reservation hierarchy to allow batch-specific reservation</span></span>

1. <span data-ttu-id="c3f69-167">Selezionare **Gestione magazzino** \> **Impostazione** \> **Scorte \> Gerarchia prenotazioni**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-167">Go to **Warehouse management** \> **Setup** \> **Inventory \> Reservation hierarchy**.</span></span>
2. <span data-ttu-id="c3f69-168">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-168">Select **New**.</span></span>
3. <span data-ttu-id="c3f69-169">Nel campo **Nome**, immettere un nome (ad esempio **BatchFles**).</span><span class="sxs-lookup"><span data-stu-id="c3f69-169">In the **Name** field, enter a name (for example, **BatchFlex**).</span></span>
4. <span data-ttu-id="c3f69-170">Nel campo **Descrizione**, immettere una descrizione (ad esempio, **Batch below flessibile**).</span><span class="sxs-lookup"><span data-stu-id="c3f69-170">In the **Description** field, enter a description (for example, **Batch below flexible**).</span></span>
5. <span data-ttu-id="c3f69-171">Nel campo **Selezionato**, selezionare **Numero di serie** e **Proprietario**, quindi selezionare il pulsante freccia sinistra per spostarli nel campo **Disponibile**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-171">In the **Selected** field, select **Serial number** and **Owner**, and then select the left arrow button to move them to the **Available** field.</span></span>
6. <span data-ttu-id="c3f69-172">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-172">Select **OK**.</span></span>
7. <span data-ttu-id="c3f69-173">Nella riga per il livello di dimensione **Numero batch**, selezionare la casella di controllo **Consenti prenotazione su ordine con domanda**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-173">In the row for the **Batch number** dimension level, select the **Allow reservation on demand order** check box.</span></span> <span data-ttu-id="c3f69-174">I livelli **Targa**e **Ubicazione** vengono selezionati automaticamente e non è possibile deselezionare le caselle di controllo corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c3f69-174">The **License plate** and **Location** levels are automatically selected, and you can't clear the check boxes for them.</span></span>
8. <span data-ttu-id="c3f69-175">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-175">Select **Save**.</span></span>

### <a name="create-a-new-released-product"></a><span data-ttu-id="c3f69-176">Creare un nuovo prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="c3f69-176">Create a new released product</span></span>

1. <span data-ttu-id="c3f69-177">Impostare i tre parametri di dati master del prodotto utilizzando questi valori:</span><span class="sxs-lookup"><span data-stu-id="c3f69-177">Set the product's three master data parameters by using these values:</span></span>

    - <span data-ttu-id="c3f69-178">Nel campo **Gruppo di dimensioni di immagazzinamento**, selezionare **Magaz**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-178">In the **Storage dimension group** field, select **Ware**.</span></span>
    - <span data-ttu-id="c3f69-179">Nel campo **Gruppo di dimensioni di tracciabilità**, selezionare **Batch-Fis**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-179">In the **Tracking dimension group** field, select **Batch-Phy**.</span></span>
    - <span data-ttu-id="c3f69-180">Nel campo **Gerarchia prenotazioni** selezionare **BatchFles**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-180">In the **Reservation hierarchy** field, select **BatchFlex**.</span></span>

2. <span data-ttu-id="c3f69-181">Creare due numeri di batch ad esempio **B11**e **B22**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-181">Create two batch numbers, such as **B11** and **B22**.</span></span>
3. <span data-ttu-id="c3f69-182">Aggiungere quantità di articoli allo scorte disponibili utilizzando i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="c3f69-182">Add item quantities to on-hand stock by using the following values.</span></span>

    | <span data-ttu-id="c3f69-183">Magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-183">Warehouse</span></span> | <span data-ttu-id="c3f69-184">Numero batch</span><span class="sxs-lookup"><span data-stu-id="c3f69-184">Batch number</span></span> | <span data-ttu-id="c3f69-185">Ubicazione</span><span class="sxs-lookup"><span data-stu-id="c3f69-185">Location</span></span> | <span data-ttu-id="c3f69-186">Targa</span><span class="sxs-lookup"><span data-stu-id="c3f69-186">License plate</span></span> | <span data-ttu-id="c3f69-187">Quantità</span><span class="sxs-lookup"><span data-stu-id="c3f69-187">Quantity</span></span> |
    |-----------|--------------|----------|---------------|----------|
    | <span data-ttu-id="c3f69-188">24</span><span class="sxs-lookup"><span data-stu-id="c3f69-188">24</span></span>        | <span data-ttu-id="c3f69-189">B11</span><span class="sxs-lookup"><span data-stu-id="c3f69-189">B11</span></span>          | <span data-ttu-id="c3f69-190">BULK-001</span><span class="sxs-lookup"><span data-stu-id="c3f69-190">BULK-001</span></span> | <span data-ttu-id="c3f69-191">Nessuna</span><span class="sxs-lookup"><span data-stu-id="c3f69-191">None</span></span>          | <span data-ttu-id="c3f69-192">10</span><span class="sxs-lookup"><span data-stu-id="c3f69-192">10</span></span>       |
    | <span data-ttu-id="c3f69-193">24</span><span class="sxs-lookup"><span data-stu-id="c3f69-193">24</span></span>        | <span data-ttu-id="c3f69-194">B11</span><span class="sxs-lookup"><span data-stu-id="c3f69-194">B11</span></span>          | <span data-ttu-id="c3f69-195">FL-001</span><span class="sxs-lookup"><span data-stu-id="c3f69-195">FL-001</span></span>   | <span data-ttu-id="c3f69-196">LP11</span><span class="sxs-lookup"><span data-stu-id="c3f69-196">LP11</span></span>          | <span data-ttu-id="c3f69-197">10</span><span class="sxs-lookup"><span data-stu-id="c3f69-197">10</span></span>       |
    | <span data-ttu-id="c3f69-198">24</span><span class="sxs-lookup"><span data-stu-id="c3f69-198">24</span></span>        | <span data-ttu-id="c3f69-199">B22</span><span class="sxs-lookup"><span data-stu-id="c3f69-199">B22</span></span>          | <span data-ttu-id="c3f69-200">FL-002</span><span class="sxs-lookup"><span data-stu-id="c3f69-200">FL-002</span></span>   | <span data-ttu-id="c3f69-201">LP22</span><span class="sxs-lookup"><span data-stu-id="c3f69-201">LP22</span></span>          | <span data-ttu-id="c3f69-202">10</span><span class="sxs-lookup"><span data-stu-id="c3f69-202">10</span></span>       |

### <a name="enter-sales-order-details"></a><span data-ttu-id="c3f69-203">Immettere i dettagli degli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="c3f69-203">Enter sales order details</span></span>

1. <span data-ttu-id="c3f69-204">Andare a **Vendite e marketing** \> **Ordini cliente** \> **Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-204">Go to **Sales and marketing** \> **Sales orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="c3f69-205">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-205">Select **New**.</span></span>
3. <span data-ttu-id="c3f69-206">Nell'intestazione dell'ordine cliente, nel campo **Conto cliente**, immettere **US-003**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-206">On the sales order header, in the **Customer account** field, enter **US-003**.</span></span>
4. <span data-ttu-id="c3f69-207">Aggiungere una riga per il nuovo articolo e immettere **10** come quantità.</span><span class="sxs-lookup"><span data-stu-id="c3f69-207">Add a line for the new item, and enter **10** as the quantity.</span></span> <span data-ttu-id="c3f69-208">Assicurarsi che il campo **Magazzino** sia impostato su **24**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-208">Make sure that the **Warehouse** field is set to **24**.</span></span>
5. <span data-ttu-id="c3f69-209">Nella scheda dettaglio **Righe ordine cliente** selezionare **Scorte** e quindi nel gruppo **Gestisci**, selezionare **Prenotazione batch**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-209">On the **Sales order lines** FastTab, select **Inventory**, and then, in the **Maintain** group, select **Batch reservation**.</span></span> <span data-ttu-id="c3f69-210">La pagina **Prenotazione batch** mostra un elenco di batch disponibili per la prenotazione per la riga ordine.</span><span class="sxs-lookup"><span data-stu-id="c3f69-210">The **Batch reservation** page shows a list of batches that are available for reservation for the order line.</span></span> <span data-ttu-id="c3f69-211">Per questo esempio, mostra una quantità **20** per il numero di batch **B11** e una quantità **10** per il numero di batch **B22**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-211">For this example, it shows a quantity of **20** for batch number **B11** and a quantity of **10** for batch number **B22**.</span></span> <span data-ttu-id="c3f69-212">Si noti che non è possibile accedere alla pagina **Prenotazione batch** da una riga se l'articolo in quella riga è associato alla gerarchia di prenotazioni "Batch-below\[location\]" a meno che non sia impostata per consentire la prenotazione specifica al batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-212">Note that the **Batch reservation** page cannot be accessed from a line if the item on that line is associated with "Batch-below\[location\]" reservation hierarchy unless it is set up to allow batch-specific reservation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3f69-213">Per prenotare un batch specifico per un ordine cliente, è necessario utilizzare la pagina **Prenotazione batch**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-213">To reserve a specific batch for a sales order, you must use the **Batch reservation** page.</span></span>
    >
    > <span data-ttu-id="c3f69-214">Se si inserisce il numero di batch direttamente nella riga ordine cliente, il sistema si comporterà come se si fosse immesso un valore di batch specifico per un articolo che è soggetto ai criteri di prenotazione "Batch-below\[location\]".</span><span class="sxs-lookup"><span data-stu-id="c3f69-214">If you enter the batch number directly on the sales order line, the system will behave as though you entered a specific batch value for an item that is subject to the "Batch-below\[location\]" reservation policy.</span></span> <span data-ttu-id="c3f69-215">Quando si salva la riga, viene visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="c3f69-215">When you save the line, you will receive a warning message.</span></span> <span data-ttu-id="c3f69-216">Se si conferma che il numero di batch deve essere specificato direttamente nella riga ordine, la riga non verrà gestita dalla logica di gestione del magazzino normale.</span><span class="sxs-lookup"><span data-stu-id="c3f69-216">If you confirm that the batch number should be specified directly on the order line, the line won't be handled by the regular warehouse management logic.</span></span>
    >
    > <span data-ttu-id="c3f69-217">Se si prenota la quantità nella pagina **Prenotazione**, non verrà prenotato alcun batch specifico e l'esecuzione delle operazioni di magazzino per la riga seguirà le regole applicabili in base ai criteri di prenotazione "Batch-below\[location\]".</span><span class="sxs-lookup"><span data-stu-id="c3f69-217">If you reserve the quantity from the **Reservation** page, no specific batch will be reserved, and the execution of warehouse operations for the line will follow the rules that are applicable under the "Batch-below\[location\]" reservation policy.</span></span>

    <span data-ttu-id="c3f69-218">In genere, questa pagina funziona e interagisce nello stesso modo in cui funziona e interagisce con gli articoli a cui è associata una gerarchia di prenotazioni di tipo "Batch-above\[location\]".</span><span class="sxs-lookup"><span data-stu-id="c3f69-218">In general, this page works and is interacted with in the same way that it works and is interacted with for items that have an associated reservation hierarchy of the "Batch-above\[location\]" type.</span></span> <span data-ttu-id="c3f69-219">Tuttavia, si applicano le seguenti eccezioni:</span><span class="sxs-lookup"><span data-stu-id="c3f69-219">However, the following exceptions apply:</span></span>

    - <span data-ttu-id="c3f69-220">La scheda dettaglio **Numeri di batch impegnati nella riga di origine** mostra i numeri di batch prenotati per la riga ordine.</span><span class="sxs-lookup"><span data-stu-id="c3f69-220">The **Batch numbers committed to source line** FastTab shows the batch numbers that are reserved for the order line.</span></span> <span data-ttu-id="c3f69-221">I valori batch nella griglia verranno visualizzati durante l'intero ciclo di evasione della riga ordine, comprese le fasi di elaborazione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="c3f69-221">The batch values in the grid will be shown throughout the fulfilment cycle of the order line, including the warehouse processing stages.</span></span> <span data-ttu-id="c3f69-222">Invece, nella scheda dettaglio **Panoramica**, la prenotazione normale nella riga ordine (ovvero la prenotazione effettuata per le dimensioni superiori al livello **Ubicazione**) viene visualizzata nella griglia fino al momento in cui viene creato il lavoro di magazzino.</span><span class="sxs-lookup"><span data-stu-id="c3f69-222">By contrast, on the **Overview** FastTab, regular order line reservation (that is, reservation that is done for the dimensions above the **Location** level) is shown in the grid up to the point when warehouse work is created.</span></span> <span data-ttu-id="c3f69-223">L'entità di lavoro gestisce quindi la prenotazione nella riga e questa non viene più visualizzata nella pagina.</span><span class="sxs-lookup"><span data-stu-id="c3f69-223">The work entity then takes over the line reservation, and the line reservation no longer appears on the page.</span></span> <span data-ttu-id="c3f69-224">La scheda dettaglio **Numeri batch impegnati nella riga di origine** consente al gestore degli ordini cliente di visualizzare i numeri di batch che sono stati impegnati nell'ordine del cliente in qualsiasi momento durante il relativo ciclo di vita, fino alla fatturazione.</span><span class="sxs-lookup"><span data-stu-id="c3f69-224">The **Batch numbers committed to source line** FastTab helps guarantee that the sales order processor can view the batch numbers that were committed to the customer's order at any point during its lifecycle, up through invoicing.</span></span>
    - <span data-ttu-id="c3f69-225">Oltre a prenotare un batch specifico, un utente può selezionare manualmente la targa e l'ubicazione specifiche del batch anziché lasciare al sistema il compito di selezionarli automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-225">In addition to reserving a specific batch, a user can manually select the batch's specific location and license plate instead of letting the system automatically select them.</span></span> <span data-ttu-id="c3f69-226">Questa funzionalità è correlata alla progettazione del meccanismo di prenotazione di batch impegnati nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c3f69-226">This capability is related to the design of the order-committed batch reservation mechanism.</span></span> <span data-ttu-id="c3f69-227">Come menzionato precedentemente, quando un numero di batch specifico viene prenotato per un articolo secondo i criteri di prenotazione "Batch-below\[location\]", il sistema deve prenotare tutte le dimensioni fino all'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c3f69-227">As was mentioned earlier, when a batch number is reserved for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="c3f69-228">Pertanto, il lavoro di magazzino avrà le stesse dimensioni di immagazzinamento prenotate dagli utenti che hanno lavorato sugli ordini e a volte potrebbe non rappresentare la posizione di stoccaggio degli articoli più conveniente o addirittura possibile per le operazioni di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-228">Therefore, warehouse work will carry the same storage dimensions that were reserved by the users who worked with the orders, and it might not always represent the item storage placement that is convenient, or even possible, for picking operations.</span></span> <span data-ttu-id="c3f69-229">Se i gestori degli ordini sono consapevoli dei vincoli inerenti al magazzino, potrebbero voler selezionare manualmente le targhe e le ubicazioni quando prenotano un batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-229">If order processors are aware of the warehouse constraints, they might want to manually select the specific locations and license plates when they reserve a batch.</span></span> <span data-ttu-id="c3f69-230">In questo caso, l'utente deve utilizzare la funzionalità **Visualizza dimensioni** nell'intestazione della pagina e deve aggiungere l'ubicazione e la targa nella griglia della scheda dettaglio **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-230">In this case, the user must use the **Display dimensions** functionality on the page header, and must add the location and license plate in the grid on the **Overview** FastTab.</span></span>

6. <span data-ttu-id="c3f69-231">Nella pagina **Prenotazione batch**, selezionare la riga per il batch **B11**, quindi selezionare **Prenota riga**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-231">On the **Batch reservation** page, select the line for batch **B11**, and then select **Reserve line**.</span></span> <span data-ttu-id="c3f69-232">Non esiste una logica designata per l'assegnazione di ubicazioni e targhe durante la prenotazione automatica.</span><span class="sxs-lookup"><span data-stu-id="c3f69-232">There is no designated logic for assigning locations and license plates during automatic reservation.</span></span> <span data-ttu-id="c3f69-233">È possibile inserire manualmente la quantità nel campo **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-233">You can manually enter the quantity in the **Reservation** field.</span></span> <span data-ttu-id="c3f69-234">Si noti che nella scheda dettaglio **Numeri batch impegnati nella riga di origine** il batch **B11** è visualizzato come **Impegnato**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-234">Notice that, on the **Batch numbers committed to source line** FastTab, batch **B11** is shown as **Committed**.</span></span>

    ![Impegnare un numero di batch specifico in una riga ordine cliente nella pagina Prenotazione batch](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > <span data-ttu-id="c3f69-236">La prenotazione della quantità in una riga ordine cliente può essere effettuata su più batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-236">Reservation of the quantity on a sales order line can be done across multiple batches.</span></span> <span data-ttu-id="c3f69-237">Allo stesso modo, la prenotazione dello stesso batch può essere effettuata in più ubicazioni e targhe (se le targhe sono abilitate per le ubicazioni).</span><span class="sxs-lookup"><span data-stu-id="c3f69-237">Likewise, reservation of the same batch can be done against multiple locations and license plates (if license plates are enabled for the locations).</span></span>
    >
    > <span data-ttu-id="c3f69-238">La prenotazione di un batch specifico per la quantità in una riga ordine cliente può anche essere parziale.</span><span class="sxs-lookup"><span data-stu-id="c3f69-238">Reservation of a specific batch for the quantity on a sales order line can also be partial.</span></span> <span data-ttu-id="c3f69-239">Ad esempio, la quantità totale di 100 unità può essere prenotata in modo che un batch specifico venga impegnato per 20 unità, mentre 80 unità sono prenotate a livello di sito e magazzino per qualsiasi batch disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-239">For example, the total quantity of 100 units can be reserved so that a specific batch is committed to 20 units, whereas 80 units are reserved at the site and warehouse levels for any available batch.</span></span> <span data-ttu-id="c3f69-240">In questo caso, WMS gestirà le operazioni di prelievo utilizzando due righe lavoro distinte.</span><span class="sxs-lookup"><span data-stu-id="c3f69-240">In this case, the WMS will handle picking operations by using two separate work lines.</span></span>

7. <span data-ttu-id="c3f69-241">Selezionare **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-241">Go to **Product information management** \> **Products** \> **Released products**.</span></span> <span data-ttu-id="c3f69-242">Selezionare l'articolo, quindi selezionare **Gestione articoli** \> **Visualizza** \> **Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-242">Select your item, and then select **Manage inventory** \> **View** \> **Transactions**.</span></span>

    ![Prenotazione impegnata nell'ordine come tipo di operazione di magazzino](media/Inventory-transactions-for-order-committed-reservation.png)

8. <span data-ttu-id="c3f69-244">Esaminare le operazioni di magazzino dell'articolo correlate alla prenotazione nella riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-244">Review the item's inventory transactions that are related to the sales order line reservation.</span></span>

    - <span data-ttu-id="c3f69-245">Una transazione in cui il campo **Riferimento** è impostato su **Ordine cliente** e il campo **Problema** è impostato su **Fisico prenotato** rappresenta la prenotazione nella riga ordine per le dimensioni inventariali sopra il livello **Ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-245">A transaction where the **Reference** field is set to **Sales order** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the inventory dimensions above the **Location** level.</span></span> <span data-ttu-id="c3f69-246">Secondo la gerarchia di prenotazioni di inventario dell'articolo, tali dimensioni sono sito, magazzino e stato dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="c3f69-246">According to the item's inventory reservation hierarchy, those dimensions are site, warehouse, and inventory status.</span></span>
    - <span data-ttu-id="c3f69-247">Una transazione in cui il campo **Riferimento** è impostato su **Prenotazione impegnata nell'ordine** e il campo **Problema** è impostato su **Fisico prenotato** rappresenta la prenotazione nella riga ordine per il batch specifico e tutte le dimensioni inventariali superiori.</span><span class="sxs-lookup"><span data-stu-id="c3f69-247">A transaction where the **Reference** field is set to **Order-committed reservation** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the specific batch and all inventory dimensions above it.</span></span> <span data-ttu-id="c3f69-248">Secondo la gerarchia di prenotazioni di inventario dell'articolo, tali dimensioni sono numero batch e ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c3f69-248">According to the item's inventory reservation hierarchy, those dimensions are batch number and location.</span></span> <span data-ttu-id="c3f69-249">In questo esempio, l'ubicazione è **Bulk-001**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-249">In this example, the location is **Bulk-001**.</span></span>

9. <span data-ttu-id="c3f69-250">Nell'intestazione dell'ordine cliente, selezionare **Magazzino** \> **Azioni** \> **Rilascio in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-250">On the sales order header, select **Warehouse** \> **Actions** \> **Release to warehouse**.</span></span> <span data-ttu-id="c3f69-251">La riga ordine è ora in ondata e vengono creati un carico e un lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3f69-251">The order line is now waved, and a load and work are created.</span></span>

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="c3f69-252">Esaminare ed elaborare il lavoro di magazzino che ha numeri di batch impegnati nell'ordine</span><span class="sxs-lookup"><span data-stu-id="c3f69-252">Review and process warehouse work that has order-committed batch numbers</span></span>

1. <span data-ttu-id="c3f69-253">Nella scheda dettaglio **Righe ordine cliente**, selezionare **Magazzino** \> **Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-253">On the **Sales order lines** FastTab, select **Warehouse** \> **Work details**.</span></span>

    <span data-ttu-id="c3f69-254">Il lavoro che gestisce l'operazione di prelievo per le quantità batch impegnate nella riga ordine cliente presenta le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="c3f69-254">The work that handles the picking operation for batch quantities that are committed to the sales order line has the following characteristics:</span></span>

    - <span data-ttu-id="c3f69-255">Per creare lavoro, il sistema utilizza modelli di lavoro ma non direttive sull'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c3f69-255">To create work, the system uses work templates but not location directives.</span></span> <span data-ttu-id="c3f69-256">Tutte le impostazioni standard definite per i modelli di lavoro, come un numero massimo di righe di prelievo o un'unità di misura specifica, verranno applicate per determinare quando è necessario creare un nuovo lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3f69-256">All the standard settings that are defined for work templates, such as a maximum number of pick lines or a specific unit of measure, will be applied to determine when new work should be created.</span></span> <span data-ttu-id="c3f69-257">Tuttavia, le regole associate alle direttive sull'ubicazione per l'identificazione delle ubicazioni di prelievo non vengono prese in considerazione poiché la prenotazione impegnata nell'ordine specifica già tutte le dimensioni inventariali.</span><span class="sxs-lookup"><span data-stu-id="c3f69-257">However, the rules that are associated with location directives for identifying pick locations aren't considered, because the order-committed reservation already specifies all the inventory dimensions.</span></span> <span data-ttu-id="c3f69-258">Tali dimensioni inventariali includono le dimensioni a livello di stoccaggio in magazzino.</span><span class="sxs-lookup"><span data-stu-id="c3f69-258">Those inventory dimensions include the dimensions at the warehouse storage level.</span></span> <span data-ttu-id="c3f69-259">Pertanto, il lavoro eredita tali dimensioni senza dover consultare le direttive sull'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c3f69-259">Therefore, the work inherits those dimensions without having to consult location directives.</span></span>
    - <span data-ttu-id="c3f69-260">Il numero di batch non viene visualizzato nella riga di prelievo (come nel caso della riga di lavoro creata per un articolo a cui è associata la gerarchia di prenotazioni "Batch-above\[location\]"). Invece, il numero di batch "da" e tutte le altre dimensioni di immagazzinamento vengono visualizzati nell'operazione di magazzino della riga lavoro a cui si fa riferimento dalle operazioni di magazzino associate.</span><span class="sxs-lookup"><span data-stu-id="c3f69-260">The batch number isn't shown on the pick line (as is the case for the work line that is created for an item that has an associated "Batch-above\[location\]" reservation hierarchy.) Instead, the "from" batch number and all other storage dimensions are shown on the work line's work inventory transaction that is referenced from the associated inventory transactions.</span></span>

        ![Operazione di magazzino per lavori originati da una prenotazione impegnata nell'ordine](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - <span data-ttu-id="c3f69-262">Dopo aver creato il lavoro, l'operazione di magazzino dove il campo **Riferimento** è impostato su **Prenotazione impegnata nell'ordine** viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="c3f69-262">After work is created, the item's inventory transaction where the **Reference** field is set to **Order-committed reservation** is removed.</span></span> <span data-ttu-id="c3f69-263">L'operazione di magazzino in cui il campo **Riferimento** è impostato su **Lavoro** ora detiene la prenotazione fisica in tutte le dimensioni inventariali della quantità.</span><span class="sxs-lookup"><span data-stu-id="c3f69-263">The inventory transaction where the **Reference** field is set to **Work** now holds the physical reservation on all the quantity's inventory dimensions.</span></span>

        <span data-ttu-id="c3f69-264">Le operazioni di magazzino possono procedere alla gestione dell'esecuzione del lavoro nel modo consueto.</span><span class="sxs-lookup"><span data-stu-id="c3f69-264">Warehouse operations can proceed to handle execution of the work in the usual manner.</span></span> <span data-ttu-id="c3f69-265">Tuttavia, le istruzioni sul dispositivo mobile indicheranno al lavoratore di prelevare un numero di batch specifico.</span><span class="sxs-lookup"><span data-stu-id="c3f69-265">However, the instructions on the mobile device will instruct the worker to pick a specific batch number.</span></span> <span data-ttu-id="c3f69-266">In ambienti di magazzino in cui le ubicazioni sono controllate dalla targa, dopo che un lavoratore ha raggiunto un'ubicazione in cui lo stesso batch si trova in più targhe, può prelevare da qualsiasi targa non ancora prenotata (ad esempio, da un'altra prenotazione impegnata nell'ordine o dal lavoro originato da una prenotazione di quel tipo).</span><span class="sxs-lookup"><span data-stu-id="c3f69-266">In warehouse environments where locations are license plate–controlled, after a worker reaches a location that stores the same batch on multiple license plates, he or she can pick from any license plate that isn't already reserved (for example, by another order-committed reservation or work that originates from a reservation of that type.)</span></span>

        <span data-ttu-id="c3f69-267">Se risulta poco pratico prelevare dall'ubicazione specificata nella riga lavoro, gli operatori di magazzino possono utilizzare una delle seguenti azioni per reindirizzare il prelievo del batch specifico da un'ubicazione più conveniente:</span><span class="sxs-lookup"><span data-stu-id="c3f69-267">If it turns out to be impractical to pick from the location that is specified on the work line, the warehouse operators can use one of the following actions to redirect picking of the specific batch from a more convenient location:</span></span>

        - <span data-ttu-id="c3f69-268">L'azione standard **Ignora ubicazione** su un dispositivo mobile (a condizione che l'impostazione **Consenti override ubicazione prelievo** dell'addetto al magazzino sia abilitata)</span><span class="sxs-lookup"><span data-stu-id="c3f69-268">The standard **Override location** action on a mobile device (provided that the warehouse worker's **Allow pick location override** setting is enabled)</span></span>
        - <span data-ttu-id="c3f69-269">L'azione **Modifica ubicazione** nella pagina **Dettagli elenco di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-269">The **Change location** action on the **Work list details** page.</span></span> 

2. <span data-ttu-id="c3f69-270">Sul dispositivo mobile, terminare il prelievo e lo stoccaggio del lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3f69-270">On the mobile device, finish picking and putting the work.</span></span>

    <span data-ttu-id="c3f69-271">La quantità **10** per il numero di batch **B11** viene ora prelevata per la riga ordine cliente e inserita nell'ubicazione **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-271">The quantity of **10** for batch number **B11** is now picked for the sales order line and put in the **Baydoor** location.</span></span> <span data-ttu-id="c3f69-272">A questo punto, è pronta per essere caricata sul camion e spedita all'indirizzo del cliente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-272">At this point, it's ready to be loaded onto the truck and dispatched to the customer's address.</span></span>

## <a name="exception-handling-of-warehouse-work-thas-has-order-committed-batch-numbers"></a><span data-ttu-id="c3f69-273">Gestione delle eccezioni per lavoro di magazzino che ha numeri batch impegnati nell'ordine</span><span class="sxs-lookup"><span data-stu-id="c3f69-273">Exception handling of warehouse work thas has order-committed batch numbers</span></span>

<span data-ttu-id="c3f69-274">Il lavoro di magazzino per il prelievo di numeri batch impegnati nell'ordine è soggetto alle stesse azioni e gestione standard delle eccezioni di magazzino del lavoro normale.</span><span class="sxs-lookup"><span data-stu-id="c3f69-274">Warehouse work for picking order-committed batch numbers is subject to the same standard warehouse exception handling and actions as regular work.</span></span> <span data-ttu-id="c3f69-275">In generale, il lavoro o la riga lavoro aperto può essere annullato, interrotto perché l'ubicazione di un utente è piena, prelevato in modo insufficiente e aggiornato a causa di un movimento.</span><span class="sxs-lookup"><span data-stu-id="c3f69-275">In general, the open work or work line can be canceled, it can be interrupted because a user location is full, it can be short-picked, and it can be updated because of a movement.</span></span> <span data-ttu-id="c3f69-276">Allo stesso modo, la quantità di lavoro prelevata che è già stata completata può essere ridotta oppure il lavoro può essere stornato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-276">Likewise, the picked quantity of work that has already been completed can be reduced, or the work can be reversed.</span></span>

<span data-ttu-id="c3f69-277">La seguente regola chiave viene applicata a tutte queste azioni di gestione delle eccezioni: il numero di batch prenotato per il cliente non può mai essere sostituito con un numero di batch differente, ma le relative dimensioni di immagazzinamento (ubicazione e targa) possono essere modificate mediante un aggiornamento manuale effettuato dall'utente o un aggiornamento automatico eseguito dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c3f69-277">The following key rule is applied to all these exception handling actions: the batch number that was reserved for the customer can never be replaced with a different batch number, but its storage dimensions (location and license plate) can be changed through either a manual update by the user or an automatic update by the system.</span></span> <span data-ttu-id="c3f69-278">L'aggiornamento automatico si basa sulla stessa assegnazione casuale delle dimensioni di immagazzinamento che è stata applicata quando un batch specifico è stato prenotato automaticamente ma non sono state specificate dimensioni di immagazzinamento.</span><span class="sxs-lookup"><span data-stu-id="c3f69-278">The automatic update is based on the same random assignment of storage dimensions that applied when a specific batch was automatically reserved but no storage dimensions were specified.</span></span>

### <a name="example-scenario"></a><span data-ttu-id="c3f69-279">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="c3f69-279">Example scenario</span></span>

<span data-ttu-id="c3f69-280">Un esempio di questo scenario è una situazione in cui il prelievo di un lavoro precedentemente completato viene annullato utilizzando la funzione **Riduci quantità prelevata**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-280">An example of this scenario is a situation where previously completed work is being unpicked by using the **Reduce picked quantity** function.</span></span> <span data-ttu-id="c3f69-281">Questo esempio continua l'esempio precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c3f69-281">This example continues the previous example in this topic.</span></span>

1. <span data-ttu-id="c3f69-282">Selezionare **Gestione magazzino** \> **Carichi** \> **Carichi attivi**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-282">Go to **Warehouse management** \> **Loads** \> **Active loads**.</span></span>
2. <span data-ttu-id="c3f69-283">Seleziona il carico che è stato creato in relazione alla spedizione dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-283">Select the load that was created in connection with the shipment of your sales order.</span></span>
3. <span data-ttu-id="c3f69-284">Nella scheda dettaglio **Carica righe ordine**, selezionare **Riduci quantità prelevata**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-284">From the **Load order lines** FastTab, select **Reduce picked quantity**.</span></span>
4. <span data-ttu-id="c3f69-285">Nella pagina **Riduce quantità prelevata**, nel campo **Sposta nell'ubicazione**, seleziona **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-285">On the **Reduce picked quantity** page, in the **Move to location** field, select **FL-001**.</span></span>
5. <span data-ttu-id="c3f69-286">Nel campo **Passa a targa** selezionare **LP33**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-286">In the **Move to license plate** field, select **LP33**.</span></span>
6. <span data-ttu-id="c3f69-287">Nella griglia, nel campo **Quantità inventario per annullamento prelievo**, immettere **10**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-287">In the grid, in the **Inventory quantity to unpick** field, enter **10**.</span></span>
7. <span data-ttu-id="c3f69-288">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-288">Select **OK**.</span></span>

<span data-ttu-id="c3f69-289">Di seguito sono riportati i risultati dell'azione di annullamento del prelievo:</span><span class="sxs-lookup"><span data-stu-id="c3f69-289">Here are the results of the unpicking action:</span></span>

- <span data-ttu-id="c3f69-290">Lo stato del lavoro chiuso precedentemente diventa **Annullato**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-290">The status of the previously closed work is set to **Canceled**.</span></span>
- <span data-ttu-id="c3f69-291">Un nuovo lavoro di tipo **Movimenti scorte** viene creato per la quantità **10** non prelevata per il numero di batch **B11**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-291">New work of the **Inventory movement** type is created for the unpicked quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="c3f69-292">Questo lavoro rappresenta il movimento dall'ubicazione **Baydoor** alla targa **LP33** nell'ubicazione **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-292">This work represents the movement from the **Baydoor** location to license plate **LP33** in location **FL-001**.</span></span> <span data-ttu-id="c3f69-293">Lo stato diventa **Chiuso**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-293">The status is set to **Closed**.</span></span>
- <span data-ttu-id="c3f69-294">Il sistema prenota nuovamente il numero di batch originariamente ordinato e assegna gli ID ubicazione e targa</span><span class="sxs-lookup"><span data-stu-id="c3f69-294">The system re-reserves the batch number that was originally ordered, and assigns the location and license plate IDs.</span></span> <span data-ttu-id="c3f69-295">(questo processo equivale all'esecuzione della funzione **Prenota riga** per la riga ordine per un determinato numero di batch).</span><span class="sxs-lookup"><span data-stu-id="c3f69-295">(This process is equivalent to running the **Reserve line** function for the order line for a given batch number).</span></span> <span data-ttu-id="c3f69-296">Di conseguenza, il batch **B11** viene visualizzato come impegnato nella scheda **Numeri batch impegnati nella riga di origine** della pagina **Prenotazione batch** e il campo **Prenotazione** contiene la quantità **10** per il numero di batch **B11**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-296">As a result, batch **B11** is shown as committed on the **Batch numbers committed to source line** FastTab of the **Batch reservation** page, and the **Reservation** field contains a quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="c3f69-297">Inoltre, il campo **Ubicazione** è impostato su **FL-001** e il campo **Targa** è impostato su **LP11**</span><span class="sxs-lookup"><span data-stu-id="c3f69-297">Additionally, the **Location** field is set to **FL-001**, and the **License plate** field is set to **LP11**.</span></span> <span data-ttu-id="c3f69-298">(è possibile aggiungere questi campi alla griglia se non sono visibili).</span><span class="sxs-lookup"><span data-stu-id="c3f69-298">(You can add these fields to the grid if they aren't visible.)</span></span>

<span data-ttu-id="c3f69-299">Le tabelle seguenti forniscono una panoramica che mostra come il sistema gestisce la prenotazione di batch impegnati nell'ordine per specifiche azioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="c3f69-299">The following tables provide an overview that shows how the system handles order-committed batch reservation for specific warehouse actions.</span></span> <span data-ttu-id="c3f69-300">Per interpretare il contenuto delle tabelle, è necessario supporre che ogni azione di magazzino venga eseguita nel contesto di un lavoro di magazzino esistente originato da una prenotazione batch impegnata nell'ordine o che l'esecuzione di ogni azione di magazzino influisce sul lavoro di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-300">To interpret the content in the tables, assume that each warehouse action is run in the context of existing warehouse work that originates from an order-committed batch reservation, or that execution of each warehouse action affects work of that type.</span></span>

> [!NOTE]
> <span data-ttu-id="c3f69-301">In queste tabelle, la colonna "Quantità batch disponibile" indica se è disponibile una quantità batch oltre alla quantità già prenotata per le prenotazioni impegnate nell'ordine correnti o già prenotata dal lavoro di magazzino originato da prenotazioni di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-301">In these tables, the "Batch quantity is available" column indicates whether a batch quantity is available in addition to the quantity that is either already reserved for the current order-committed reservations or already reserved by the warehouse work that originates from reservations of that type.</span></span>

#### <a name="override-the-pick-location-on-the-open-work"></a><span data-ttu-id="c3f69-302">Override dell'ubicazione di prelievo nel lavoro aperto</span><span class="sxs-lookup"><span data-stu-id="c3f69-302">Override the pick location on the open work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c3f69-303">Parametro di impostazione chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-303">Key setup parameter</span></span></th>
<th><span data-ttu-id="c3f69-304">Quantità batch disponibile</span><span class="sxs-lookup"><span data-stu-id="c3f69-304">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c3f69-305">Passaggi utente chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-305">Key user steps</span></span></th>
<th><span data-ttu-id="c3f69-306">Lavoro di magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-306">Warehouse work</span></span></th>
<th><span data-ttu-id="c3f69-307">Prenotazione batch impegnata dall'ordine</span><span class="sxs-lookup"><span data-stu-id="c3f69-307">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="c3f69-308">L'opzione <strong>Consenti override ubicazione prelievo</strong> è abilitata per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="c3f69-308">The <strong>Allow pick location override</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="c3f69-309">Sì</span><span class="sxs-lookup"><span data-stu-id="c3f69-309">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-310">Selezionare la voce di menu <strong>Ignora ubicazione</strong> nell'app Warehouse Mobile (WMA) quando si inizia il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-310">Select the <strong>Override location</strong> menu item on the Warehouse Mmobile App (WMA) when you start picking work.</span></span></li>
<li><span data-ttu-id="c3f69-311">Selezionare <strong>Suggerisci</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-311">Select <strong>Suggest</strong>.</span></span></li>
<li><span data-ttu-id="c3f69-312">Confermare la nuova ubicazione suggerita in base alla disponibilità della quantità batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-312">Confirm the new location that is suggested based on batch quantity availability.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c3f69-313">Nel lavoro corrente, si verificano le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="c3f69-313">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="c3f69-314">L'ubicazione nella riga di prelievo viene aggiornata alla nuova ubicazione</span><span class="sxs-lookup"><span data-stu-id="c3f69-314">The location on the pick line is updated to the new location.</span></span> <span data-ttu-id="c3f69-315">(se l'ubicazione è controllata dalla targa, una targa casuale viene assegnata all'operazione di magazzino e il lavoratore può prelevare da qualsiasi targa che abbia la quantità disponibile).</span><span class="sxs-lookup"><span data-stu-id="c3f69-315">(If the location is license plate–controlled, a random license plate is assigned to the work inventory transaction, and the worker can pick from any license plate that has available quantity.)</span></span></li>
<li><span data-ttu-id="c3f69-316">Se la quantità viene trovata in più targhe nella nuova ubicazione, la riga di prelievo originale viene suddivisa in più righe per corrispondere a ciascuna targa.</span><span class="sxs-lookup"><span data-stu-id="c3f69-316">If the quantity is found on more than one license plate in the new location, the original pick line is split into multiple lines to match each license plate.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c3f69-317">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-317">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-318">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-318">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-319">Selezionare la voce di menu <strong>Ignora ubicazione</strong> nell'app WMA quando si inizia il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-319">Select the <strong>Override location</strong> menu item on the WMA when you start picking work.</span></span></li>
<li><span data-ttu-id="c3f69-320">Immettere un'ubicazione manualmente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-320">Manually enter a location.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c3f69-321">L'azione <strong>Ignora ubicazione</strong> non è possibile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-321">The <strong>Override location</strong> action isn't possible.</span></span> <span data-ttu-id="c3f69-322">Non viene eseguita correttamente e viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="c3f69-322">It fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="c3f69-323">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-323">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a><span data-ttu-id="c3f69-324">Pulsante Completo - Suddividere una riga lavoro a causa dell'overflow nell'ubicazione dell'utente</span><span class="sxs-lookup"><span data-stu-id="c3f69-324">Full button – Split a work line because of overflow on the user location</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c3f69-325">Parametro di impostazione chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-325">Key setup parameter</span></span></th>
<th><span data-ttu-id="c3f69-326">Quantità batch disponibile</span><span class="sxs-lookup"><span data-stu-id="c3f69-326">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c3f69-327">Passaggi utente chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-327">Key user steps</span></span></th>
<th><span data-ttu-id="c3f69-328">Lavoro di magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-328">Warehouse work</span></span></th>
<th><span data-ttu-id="c3f69-329">Prenotazione batch impegnata dall'ordine</span><span class="sxs-lookup"><span data-stu-id="c3f69-329">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c3f69-330">L'opzione <strong>Consenti suddivisione del lavoro</strong> è abilitata nella voce di menu sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-330">The <strong>Allow splitting of work</strong> option is enabled on the mobile device menu item.</span></span></td>
<td><span data-ttu-id="c3f69-331">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-331">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-332">Selezionare la voce di menu <strong>Completo</strong> nell'app WMA quando si elabora il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-332">Select the <strong>Full</strong> menu item on the WMA when you process picking work.</span></span></li>
<li><span data-ttu-id="c3f69-333">Nel campo <strong>Qtà prelievo</strong>, immettere una quantità parziale del prelievo necessario per indicare la piena capacità.</span><span class="sxs-lookup"><span data-stu-id="c3f69-333">In the <strong>Pick Qty</strong> field, enter a partial quantity of the required pick to indicate the full capacity.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c3f69-334">Nel lavoro corrente, la quantità viene aggiornata alla quantità rimanente che deve essere prelevata.</span><span class="sxs-lookup"><span data-stu-id="c3f69-334">On the current work, the quantity is updated to the remaining quantity that must be picked.</span></span></li>
<li><span data-ttu-id="c3f69-335">Il nuovo lavoro per la quantità prelevata viene creato e chiuso.</span><span class="sxs-lookup"><span data-stu-id="c3f69-335">New work for the picked quantity is created and closed.</span></span></li>
</ul></td>
<td><span data-ttu-id="c3f69-336">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-336">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a><span data-ttu-id="c3f69-337">Ridurre la quantità prelevato del lavoro completato (da un carico)</span><span class="sxs-lookup"><span data-stu-id="c3f69-337">Reduce the picked quantity of completed work (from a load)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c3f69-338">Parametro di impostazione chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-338">Key setup parameter</span></span></th>
<th><span data-ttu-id="c3f69-339">Quantità batch disponibile</span><span class="sxs-lookup"><span data-stu-id="c3f69-339">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c3f69-340">Passaggi utente chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-340">Key user steps</span></span></th>
<th><span data-ttu-id="c3f69-341">Lavoro di magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-341">Warehouse work</span></span></th>
<th><span data-ttu-id="c3f69-342">Prenotazione batch impegnata dall'ordine</span><span class="sxs-lookup"><span data-stu-id="c3f69-342">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="c3f69-343">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-343">Not applicable</span></span></td>
<td><span data-ttu-id="c3f69-344">Sì</span><span class="sxs-lookup"><span data-stu-id="c3f69-344">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-345">Aprire la pagina <strong>Riduci quantità prelevata</strong> dalla riga di carico.</span><span class="sxs-lookup"><span data-stu-id="c3f69-345">Open the <strong>Reduce picked quantity</strong> page from the load line.</span></span></li>
<li><span data-ttu-id="c3f69-346">Immettere la quantità completa per la quale annullare il prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-346">Enter the full quantity to unpick.</span></span></li>
<li><span data-ttu-id="c3f69-347">Selezionare un'ubicazione/targa "sposta in".</span><span class="sxs-lookup"><span data-stu-id="c3f69-347">Select a "move to" location/license plate.</span></span></li>
</ol>
</td>
<td>
<ul> 
<li><span data-ttu-id="c3f69-348">Il lavoro associato alla riga di carico viene annullato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-348">Work that is associated with the load line is canceled.</span></span></li>
<li><span data-ttu-id="c3f69-349">Il nuovo lavoro per il movimento scorte viene creato e chiuso.</span><span class="sxs-lookup"><span data-stu-id="c3f69-349">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c3f69-350">La quantità viene prenotata nuovamente per lo stesso batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-350">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c3f69-351">Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-351">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-352">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-352">No</span></span></td>
<td><span data-ttu-id="c3f69-353">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-353">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-354">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-354">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-355">La quantità viene prenotata nuovamente per lo stesso batch e per le stesse ubicazione e targa (se l'ubicazione è controllata dalla targa) immesse durante l'annullamento del prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-355">The quantity is re-reserved for the same batch, and for the same location and license plate (if the location is license plate–controlled) that were entered during unpicking.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a><span data-ttu-id="c3f69-356">Spostare un articolo in un magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-356">Move an item within a warehouse</span></span>

> [!NOTE]
> <span data-ttu-id="c3f69-357">Questa azione di magazzino è applicabile solo a un movimento di tipo **Processo di creazione lavoro**, non al movimento per modello.</span><span class="sxs-lookup"><span data-stu-id="c3f69-357">This warehouse action is applicable only to movement of the **Work creation process** type, not to movement by template.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c3f69-358">Parametro di impostazione chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-358">Key setup parameter</span></span></th>
<th><span data-ttu-id="c3f69-359">Quantità batch disponibile</span><span class="sxs-lookup"><span data-stu-id="c3f69-359">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c3f69-360">Passaggi utente chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-360">Key user steps</span></span></th>
<th><span data-ttu-id="c3f69-361">Lavoro di magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-361">Warehouse work</span></span></th>
<th><span data-ttu-id="c3f69-362">Prenotazione batch impegnata dall'ordine</span><span class="sxs-lookup"><span data-stu-id="c3f69-362">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="c3f69-363">L'opzione <strong>Consenti movimento di magazzino e lavoro associato</strong> è abilitata per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="c3f69-363">The <strong>Allow movement of inventory with associated work</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="c3f69-364">Sì</span><span class="sxs-lookup"><span data-stu-id="c3f69-364">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-365">Iniziare un movimento sull'app WMA.</span><span class="sxs-lookup"><span data-stu-id="c3f69-365">Start a movement on the WMA.</span></span></li>
<li><span data-ttu-id="c3f69-366">Immettere le ubicazioni "da" e "a".</span><span class="sxs-lookup"><span data-stu-id="c3f69-366">Enter "from" and "to" locations.</span></span></li>
</ol></td>
<td>
<ul>
<li><span data-ttu-id="c3f69-367">Per tutto il lavoro esistente interessato dallo spostamento, l'ubicazione di prelievo viene aggiornata alla nuova ubicazione "a".</span><span class="sxs-lookup"><span data-stu-id="c3f69-367">On all existing work that is affected by the move, the pick location is updated to the new "to" location.</span></span></li>
<li><span data-ttu-id="c3f69-368">Il nuovo lavoro per il movimento scorte viene creato e chiuso.</span><span class="sxs-lookup"><span data-stu-id="c3f69-368">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c3f69-369">Tutte le prenotazioni esistenti interessate dal movimento di quantità dall'ubicazione specificata vengono ripetute per lo stesso batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-369">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch.</span></span> <span data-ttu-id="c3f69-370">Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-370">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-371">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-371">No</span></span></td>
<td><span data-ttu-id="c3f69-372">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-372">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-373">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-373">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-374">Tutte le prenotazioni esistenti interessate dal movimento di quantità dall'ubicazione indicata vengono ripetute per lo stesso batch e per la nuova targa e ubicazione "a" (se l'ubicazione è controllata dalla targa).</span><span class="sxs-lookup"><span data-stu-id="c3f69-374">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch, and for the new "to" location and license plate (if the location is license plate–controlled).</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a><span data-ttu-id="c3f69-375">Stornare la quantità prelevata di lavoro completato (da un carico o un'ondata)</span><span class="sxs-lookup"><span data-stu-id="c3f69-375">Reverse the picked quantity of completed work (from a load or a wave)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c3f69-376">Parametro di impostazione chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-376">Key setup parameter</span></span></th>
<th><span data-ttu-id="c3f69-377">Quantità batch disponibile</span><span class="sxs-lookup"><span data-stu-id="c3f69-377">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c3f69-378">Passaggi utente chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-378">Key user steps</span></span></th>
<th><span data-ttu-id="c3f69-379">Lavoro di magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-379">Warehouse work</span></span></th>
<th><span data-ttu-id="c3f69-380">Prenotazione batch impegnata dall'ordine</span><span class="sxs-lookup"><span data-stu-id="c3f69-380">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'><span data-ttu-id="c3f69-381">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-381">Not applicable</span></span></td>
<td><span data-ttu-id="c3f69-382">Sì</span><span class="sxs-lookup"><span data-stu-id="c3f69-382">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-383">Aprire la pagina <strong>Storna lavoro</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-383">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="c3f69-384">Nella pagina della richiesta, selezionare l'opzione <strong>Lascia articoli nell'ubicazione corrente</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-384">On the request page, select the <strong>Leave items at current location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c3f69-385">Tutto il lavoro associato al carico viene annullato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-385">All work that is associated with the load is canceled.</span></span></td>
<td><span data-ttu-id="c3f69-386">La quantità viene prenotata nuovamente per lo stesso batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-386">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c3f69-387">Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-387">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-388">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-388">No</span></span></td>
<td><span data-ttu-id="c3f69-389">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-389">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-390">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-390">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-391">La quantità viene prenotata nuovamente per lo stesso batch e per l'ubicazione e la targa in cui la quantità è stata lasciata al momento dello storno.</span><span class="sxs-lookup"><span data-stu-id="c3f69-391">The quantity is re-reserved for the same batch, and for the location and license plate where the quantity was left upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-392">Sì</span><span class="sxs-lookup"><span data-stu-id="c3f69-392">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-393">Aprire la pagina <strong>Storna lavoro</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-393">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="c3f69-394">Nella pagina della richiesta, selezionare l'opzione <strong>Assegna articoli a questa ubicazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-394">On the request page, select the <strong>Assign items to this location</strong> option.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c3f69-395">Il lavoro corrente viene annullato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-395">The current work is canceled.</span></span></li>
<li><span data-ttu-id="c3f69-396">Il nuovo lavoro per il movimento scorte viene creato e chiuso.</span><span class="sxs-lookup"><span data-stu-id="c3f69-396">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c3f69-397">La quantità viene prenotata nuovamente per lo stesso batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-397">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c3f69-398">Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-398">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-399">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-399">No</span></span></td>
<td><span data-ttu-id="c3f69-400">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-400">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-401">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-401">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-402">La quantità viene prenotata nuovamente per lo stesso batch e per l'ubicazione e la targa a cui la quantità è stata assegnata al momento dello storno.</span><span class="sxs-lookup"><span data-stu-id="c3f69-402">The quantity is re-reserved for the same batch, and for the location and license plate that the quantity was assigned to upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-403">Sì/No</span><span class="sxs-lookup"><span data-stu-id="c3f69-403">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-404">Aprire la pagina <strong>Storna lavoro</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-404">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="c3f69-405">Nella pagina della richiesta, selezionare l'opzione <strong>Sposta articoli a questa ubicazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-405">On the request page, select the <strong>Move items to this location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c3f69-406">Lo storno non è supportato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-406">Reversal isn't supported.</span></span></td>
<td><span data-ttu-id="c3f69-407">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-407">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-408">Sì/No</span><span class="sxs-lookup"><span data-stu-id="c3f69-408">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-409">Aprire la pagina <strong>Storna lavoro</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-409">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="c3f69-410">Nella pagina della richiesta, selezionare l'opzione <strong>Sposta articoli in base alle direttive ubicazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-410">On the request page, select the <strong>Move items based on location directives</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c3f69-411">Lo storno non è supportato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-411">Reversal isn't supported.</span></span> </td>
<td><span data-ttu-id="c3f69-412">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-412">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a><span data-ttu-id="c3f69-413">Prelevare in difetto una quantità - Registrare la quantità come fisicamente non trovata nell'ubicazione/targa durante il lavoro di prelievo</span><span class="sxs-lookup"><span data-stu-id="c3f69-413">Short-pick a quantity – Register the quantity as physically not found at the location/license plate while you perform picking work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c3f69-414">Parametro di impostazione chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-414">Key setup parameter</span></span></th>
<th><span data-ttu-id="c3f69-415">Quantità batch disponibile</span><span class="sxs-lookup"><span data-stu-id="c3f69-415">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c3f69-416">Passaggi utente chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-416">Key user steps</span></span></th>
<th><span data-ttu-id="c3f69-417">Lavoro di magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-417">Warehouse work</span></span></th>
<th><span data-ttu-id="c3f69-418">Prenotazione batch impegnata dall'ordine</span><span class="sxs-lookup"><span data-stu-id="c3f69-418">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="c3f69-419">Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Nessuna</strong>, <strong>Correggi magazzino</strong> = <strong>Sì</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>No</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-419">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span></td>
<td><span data-ttu-id="c3f69-420">Sì</span><span class="sxs-lookup"><span data-stu-id="c3f69-420">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-421">Selezionare la voce di menu <strong>Prelievo in difetto</strong> nell'app WMA quando si esegue il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-421">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c3f69-422">Nel campo <strong>Quantità prelievo</strong> immettere <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c3f69-422">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c3f69-423">Nel campo <strong>Motivo</strong>, immettere <strong>Nessuna riallocazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-423">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c3f69-424">Il lavoro corrente viene chiuso e la quantità prelevata è 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c3f69-424">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="c3f69-425">Un'operazione di magazzino di tipo <strong>Conteggio</strong> e il tipo di problema <strong>Venduto</strong> vengono creati per rappresentare la rettifica.</span><span class="sxs-lookup"><span data-stu-id="c3f69-425">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c3f69-426">La quantità viene prenotata nuovamente per lo stesso batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-426">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c3f69-427">Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-427">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-428">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-428">No</span></span></td>
<td><span data-ttu-id="c3f69-429">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-429">See the previous row.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="c3f69-430">L'azione di prelievo in difetto non riesce e viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="c3f69-430">The short-picking action fails, and an error is thrown.</span></span></li>
<li><span data-ttu-id="c3f69-431">Il lavoro corrente rimane aperto.</span><span class="sxs-lookup"><span data-stu-id="c3f69-431">The current work remains open.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c3f69-432">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-432">Not applicable</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="c3f69-433">Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Nessuna</strong>, <strong>Correggi magazzino</strong> = <strong>Sì</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>Sì</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-433">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span></td>
<td><span data-ttu-id="c3f69-434">Sì</span><span class="sxs-lookup"><span data-stu-id="c3f69-434">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-435">Selezionare la voce di menu <strong>Prelievo in difetto</strong> nell'app WMA quando si esegue il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-435">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c3f69-436">Nel campo <strong>Quantità prelievo</strong> immettere <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c3f69-436">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c3f69-437">Nel campo <strong>Motivo</strong>, immettere <strong>Nessuna riallocazione</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-437">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c3f69-438">Il lavoro corrente viene chiuso e la quantità prelevata è 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c3f69-438">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="c3f69-439">Un'operazione di magazzino di tipo <strong>Conteggio</strong> e il tipo di problema <strong>Venduto</strong> vengono creati per rappresentare la rettifica.</span><span class="sxs-lookup"><span data-stu-id="c3f69-439">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c3f69-440">Tutte le prenotazioni esistenti interessate dalla rettifica della quantità nell'ubicazione del prelievo in difetto vengono ripetute per lo stesso batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-440">All existing reservations that are affected by the quantity adjustment in the short-picked location are re-reserved for the same batch.</span></span> <span data-ttu-id="c3f69-441">Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-441">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-442">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-442">No</span></span></td>
<td><span data-ttu-id="c3f69-443">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-443">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-444">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-444">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-445">Tutte le prenotazioni esistenti interessate dalla rettifica della quantità nell'ubicazione del prelievo in difetto vengono rimosse per lo stesso batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-445">All existing reservations that are affected by the quantity adjustment in the short-picked location are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-446">Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Manuale</strong>, <strong>Correggi magazzino</strong> = <strong>Sì</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>Sì</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-446">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No/Yes</strong>.</span></span> <span data-ttu-id="c3f69-447">Inoltre, l'opzione <strong>Consenti riallocazione manuale articolo</strong> è abilitata per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="c3f69-447">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="c3f69-448">Sì</span><span class="sxs-lookup"><span data-stu-id="c3f69-448">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-449">Selezionare la voce di menu <strong>Prelievo in difetto</strong> nell'app WMA quando si esegue il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-449">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c3f69-450">Nel campo <strong>Quantità prelievo in difetto</strong> immettere <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c3f69-450">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c3f69-451">Nel campo <strong>Motivo</strong>, selezionare <strong>Prelievo in difetto con riallocazione manuale</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-451">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="c3f69-452">Selezionare l'ubicazione/targa nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c3f69-452">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c3f69-453">Nel lavoro corrente, si verificano le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="c3f69-453">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="c3f69-454">La riga di prelievo viene chiusa e la quantità prelevata è 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c3f69-454">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="c3f69-455">La riga di stoccaggio viene cancellata.</span><span class="sxs-lookup"><span data-stu-id="c3f69-455">The put line is canceled.</span></span></li>
<li><span data-ttu-id="c3f69-456">Viene creata una nuova riga di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-456">A new pick line is created.</span></span> <span data-ttu-id="c3f69-457">che utilizza l'ubicazione/la targa che l'utente ha selezionato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-457">It uses the location/license plate that the user selected.</span></span></li>
<li><span data-ttu-id="c3f69-458">Viene creata una nuova riga di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="c3f69-458">A new put line is created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="c3f69-459">Un'operazione di magazzino di tipo <strong>Conteggio</strong> e il tipo di problema <strong>Venduto</strong> vengono creati per rappresentare la rettifica.</span><span class="sxs-lookup"><span data-stu-id="c3f69-459">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c3f69-460">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-460">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-461">Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Manuale</strong>, <strong>Correggi magazzino</strong> = <strong>Sì</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>No</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-461">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span> <span data-ttu-id="c3f69-462">Inoltre, l'opzione <strong>Consenti riallocazione manuale articolo</strong> è abilitata per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="c3f69-462">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="c3f69-463">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-463">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-464">Selezionare la voce di menu <strong>Prelievo in difetto</strong> nell'app WMA quando si esegue il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-464">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c3f69-465">Nel campo <strong>Quantità prelievo in difetto</strong> immettere <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c3f69-465">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c3f69-466">Nel campo <strong>Motivo</strong>, selezionare <strong>Prelievo in difetto con riallocazione manuale</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-466">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c3f69-467">L'azione di prelievo in difetto non riesce e viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="c3f69-467">The short-picking action fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="c3f69-468">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-468">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-469">Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Manuale</strong>, <strong>Correggi magazzino</strong> = <strong>Sì</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>Sì</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-469">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span> <span data-ttu-id="c3f69-470">Inoltre, l'opzione <strong>Consenti riallocazione manuale articolo</strong> è abilitata per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="c3f69-470">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="c3f69-471">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-471">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-472">Selezionare la voce di menu <strong>Prelievo in difetto</strong> nell'app WMA quando si esegue il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-472">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c3f69-473">Nel campo <strong>Quantità prelievo in difetto</strong> immettere <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c3f69-473">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c3f69-474">Nel campo <strong>Motivo</strong>, selezionare <strong>Prelievo in difetto con riallocazione manuale</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-474">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="c3f69-475">Selezionare l'ubicazione/targa nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c3f69-475">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="c3f69-476">Nel lavoro corrente, si verificano le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="c3f69-476">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="c3f69-477">La riga di prelievo viene chiusa e la quantità prelevata è 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c3f69-477">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="c3f69-478">La riga di stoccaggio viene cancellata.</span><span class="sxs-lookup"><span data-stu-id="c3f69-478">The put line is canceled.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="c3f69-479">Un'operazione di magazzino di tipo <strong>Conteggio</strong> e il tipo di problema <strong>Venduto</strong> vengono creati per rappresentare la rettifica.</span><span class="sxs-lookup"><span data-stu-id="c3f69-479">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="c3f69-480">Tutte le prenotazioni esistenti interessate dalla rettifica della quantità nell'ubicazione/targa del prelievo in difetto vengono rimosse per lo stesso batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-480">All existing reservations that are affected by the quantity adjustment in the short-picked location/license plate are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-481">Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Automatica</strong>, <strong>Correggi magazzino</strong> = <strong>Sì/No</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>Sì/No</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-481">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Automatic</strong>, <strong>Adjust inventory</strong> = <strong>Yes/No</strong>, and <strong>Remove reservations</strong> = <strong>Yes/No</strong>.</span></span></td>
<td><span data-ttu-id="c3f69-482">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-482">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-483">Selezionare la voce di menu <strong>Prelievo in difetto</strong> nell'app WMA quando si esegue il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-483">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="c3f69-484">Nel campo <strong>Quantità prelievo in difetto</strong> immettere <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="c3f69-484">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="c3f69-485">Nel campo <strong>Motivo</strong>, selezionare <strong>Prelievo in difetto con riallocazione automatica</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-485">In the <strong>Reason</strong> field, select <strong>Short Picking with automatic reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c3f69-486">Il prelievo in difetto che comporta la riallocazione automatica non è supportato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-486">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
<td><span data-ttu-id="c3f69-487">Il prelievo in difetto che comporta la riallocazione automatica non è supportato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-487">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a><span data-ttu-id="c3f69-488">Cambia lo stato magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-488">Change the inventory status</span></span>

> [!NOTE]
> <span data-ttu-id="c3f69-489">Questa azione di magazzino può essere eseguita da più punti di ingresso.</span><span class="sxs-lookup"><span data-stu-id="c3f69-489">This warehouse action can be performed from multiple entry points.</span></span> <span data-ttu-id="c3f69-490">L'esempio che viene mostrato qui utilizza l'azione **Modifica stato inventario** nella pagina **Disponibili per ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="c3f69-490">The example that is shown here uses **Inventory status change** action on the **On-hand by location** page.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c3f69-491">Parametro di impostazione chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-491">Key setup parameter</span></span></th>
<th><span data-ttu-id="c3f69-492">Quantità batch disponibile</span><span class="sxs-lookup"><span data-stu-id="c3f69-492">Batch quantity is available</span></span></th>
<th><span data-ttu-id="c3f69-493">Passaggi utente chiave</span><span class="sxs-lookup"><span data-stu-id="c3f69-493">Key user steps</span></span></th>
<th><span data-ttu-id="c3f69-494">Lavoro di magazzino</span><span class="sxs-lookup"><span data-stu-id="c3f69-494">Warehouse work</span></span></th>
<th><span data-ttu-id="c3f69-495">Prenotazione batch impegnata dall'ordine</span><span class="sxs-lookup"><span data-stu-id="c3f69-495">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="c3f69-496">Nella scheda <strong>Magazzino</strong>, nel record <strong>Magazzino</strong>, il campo <strong>Rimuovi prenotazioni e contrassegni</strong> è impostato su <strong>Prenotazioni</strong> o <strong>Contrassegni e prenotazioni</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-496">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>Reservations</strong> or <strong>Markings and reservations</strong>.</span></span></td>
<td><span data-ttu-id="c3f69-497">Sì</span><span class="sxs-lookup"><span data-stu-id="c3f69-497">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-498">Selezionare un'ubicazione specifica.</span><span class="sxs-lookup"><span data-stu-id="c3f69-498">Select a specific location.</span></span></li>
<li><span data-ttu-id="c3f69-499">Selezionare una riga con un articolo, un'ubicazione e una targa specifici (se l'ubicazione è controllata dalla targa).</span><span class="sxs-lookup"><span data-stu-id="c3f69-499">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="c3f69-500">Selezionare <strong>Modifica stato inventario</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-500">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="c3f69-501">Impostare il campo <strong>Stato inventario</strong> su <strong>Blocco</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-501">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c3f69-502">Le modifiche allo stato dell'inventario non sono consentite per le quantità prenotate per il lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3f69-502">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="c3f69-503">La quantità viene prenotata nuovamente per lo stesso batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-503">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c3f69-504">Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-504">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></li>
<li><span data-ttu-id="c3f69-505">Due operazioni di magazzino di tipo <strong>Modifica stato inventario</strong> vengono create per rappresentare la modifica nella dimensione stato inventario.</span><span class="sxs-lookup"><span data-stu-id="c3f69-505">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="c3f69-506">Un'operazione di magazzino di tipo <strong>Blocco scorte</strong> e il tipo di problema <strong>Fisico prenotato</strong> vengono creati per rappresentare la prenotazione della quantità bloccata.</span><span class="sxs-lookup"><span data-stu-id="c3f69-506">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-507">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-507">No</span></span></td>
<td><span data-ttu-id="c3f69-508">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-508">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-509">Le modifiche allo stato dell'inventario non sono consentite per le quantità prenotate per il lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3f69-509">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="c3f69-510">La prenotazione viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="c3f69-510">The reservation is removed.</span></span></li>
<li><span data-ttu-id="c3f69-511">Due operazioni di magazzino di tipo <strong>Modifica stato inventario</strong> vengono create per rappresentare la modifica nella dimensione stato inventario.</span><span class="sxs-lookup"><span data-stu-id="c3f69-511">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="c3f69-512">Un'operazione di magazzino di tipo <strong>Blocco scorte</strong> e il tipo di problema <strong>Fisico prenotato</strong> vengono creati per rappresentare la prenotazione della quantità bloccata.</span><span class="sxs-lookup"><span data-stu-id="c3f69-512">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="c3f69-513">Nella scheda <strong>Magazzino</strong>, nel record <strong>Magazzino</strong>, il campo <strong>Rimuovi prenotazioni e contrassegni</strong> è impostato su <strong>Nssuno</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-513">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>None</strong>.</span></span></td>
<td><span data-ttu-id="c3f69-514">Sì</span><span class="sxs-lookup"><span data-stu-id="c3f69-514">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="c3f69-515">Selezionare un'ubicazione specifica.</span><span class="sxs-lookup"><span data-stu-id="c3f69-515">Select a specific location.</span></span></li>
<li><span data-ttu-id="c3f69-516">Selezionare una riga con un articolo, un'ubicazione e una targa specifici (se l'ubicazione è controllata dalla targa).</span><span class="sxs-lookup"><span data-stu-id="c3f69-516">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="c3f69-517">Selezionare <strong>Modifica stato inventario</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-517">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="c3f69-518">Impostare il campo <strong>Stato inventario</strong> su <strong>Blocco</strong>.</span><span class="sxs-lookup"><span data-stu-id="c3f69-518">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="c3f69-519">Le modifiche allo stato dell'inventario non sono consentite per le quantità prenotate per il lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3f69-519">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="c3f69-520">La quantità viene prenotata nuovamente per lo stesso batch.</span><span class="sxs-lookup"><span data-stu-id="c3f69-520">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="c3f69-521">Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c3f69-521">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c3f69-522">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c3f69-522">No</span></span></td>
<td><span data-ttu-id="c3f69-523">Vedere la riga precedente.</span><span class="sxs-lookup"><span data-stu-id="c3f69-523">See the previous row.</span></span></td>
<td><span data-ttu-id="c3f69-524">Le modifiche allo stato dell'inventario non sono consentite per le quantità prenotate per il lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3f69-524">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="c3f69-525">Le modifiche allo stato dell'inventario non sono consentite.</span><span class="sxs-lookup"><span data-stu-id="c3f69-525">Inventory status changes aren't allowed.</span></span></td>
</tr>
</tbody>
</table>

## <a name="limitations"></a><span data-ttu-id="c3f69-526">Limiti</span><span class="sxs-lookup"><span data-stu-id="c3f69-526">Limitations</span></span>

- <span data-ttu-id="c3f69-527">I criteri flessibili di prenotazione delle dimensioni a livello di magazzino non supportano le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="c3f69-527">The flexible warehouse-level dimension reservation functionality doesn't support the following features:</span></span>

    - <span data-ttu-id="c3f69-528">Gestione del peso variabile</span><span class="sxs-lookup"><span data-stu-id="c3f69-528">Catch weight management</span></span>
    - <span data-ttu-id="c3f69-529">Scorte fisiche negative</span><span class="sxs-lookup"><span data-stu-id="c3f69-529">Physical negative inventory</span></span>
    - <span data-ttu-id="c3f69-530">Prenotazione contro fornitura ordinata</span><span class="sxs-lookup"><span data-stu-id="c3f69-530">Reservation against ordered supply</span></span>
    - <span data-ttu-id="c3f69-531">Ordini di trasferimento e prelievo di materie prime</span><span class="sxs-lookup"><span data-stu-id="c3f69-531">Transfer orders and raw material picking</span></span>

- <span data-ttu-id="c3f69-532">La regola di consolidamento dei contenitori per l'imballaggio per unità direttiva presenta dei limiti.</span><span class="sxs-lookup"><span data-stu-id="c3f69-532">The container consolidation rule for packing by directive unit has limitations.</span></span> <span data-ttu-id="c3f69-533">Per le prenotazioni impegnate in ordini, si consiglia di non utilizzare modelli di build contenitore dove il campo **Imballa per unità direttiva** è abilitato.</span><span class="sxs-lookup"><span data-stu-id="c3f69-533">For order-committed reservations, we recommend that you not use container build templates where the **Pack by directive unit** field is enabled.</span></span> <span data-ttu-id="c3f69-534">Nella progettazione attuale, le direttive di ubicazione non vengono utilizzate durante la creazione di lavoro di magazzino.</span><span class="sxs-lookup"><span data-stu-id="c3f69-534">In the current design, location directives aren't used when warehouse work is created.</span></span> <span data-ttu-id="c3f69-535">Pertanto, solo l'unità più bassa nel gruppo di sequenze unità (l'unità di magazzino) viene applicata durante il passaggio ondata di containerizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3f69-535">Therefore, only the lowest unit in the unit sequence group (the inventory unit) is applied during the containerization wave step.</span></span>
