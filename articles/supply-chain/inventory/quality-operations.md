---
title: Operazioni per non conformità
description: Questo argomento descrive come creare e utilizzare le operazioni per le non conformità.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9a6cc88b80f82d77edac0341cb6a3c0db4b42ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022206"
---
# <a name="operations-for-nonconformances"></a><span data-ttu-id="1da02-103">Operazioni per non conformità</span><span class="sxs-lookup"><span data-stu-id="1da02-103">Operations for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1da02-104">Questo argomento descrive come creare e utilizzare le operazioni per le non conformità.</span><span class="sxs-lookup"><span data-stu-id="1da02-104">This topic describes how to create and use operations for nonconformances.</span></span>

<span data-ttu-id="1da02-105">Puoi Utilizzare la pagina **Operazioni** per definire classificazioni del lavoro che è possibile eseguire per una non conformità approvata.</span><span class="sxs-lookup"><span data-stu-id="1da02-105">You can use the **Operations** page to define classifications of the work that can be performed for an approved nonconformance.</span></span> <span data-ttu-id="1da02-106">Quando si assegna un'operazione correlata a una non conformità, è possibile fornire informazioni dettagliate, ad esempio sul materiale associato, sulle ore di manodopera e sulle spese varie, necessarie per l'esecuzione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="1da02-106">When you assign a related operation to a nonconformance, you can provide details such as the associated material, labor hours, and charges that are required to do the operation.</span></span> <span data-ttu-id="1da02-107">Queste informazioni vengono utilizzate dal sistema per calcolare un costo stimato per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="1da02-107">The system uses this information to calculate an estimated cost for the operation.</span></span> <span data-ttu-id="1da02-108">Le informazioni dettagliate e i costi stimati vengono forniti a scopo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="1da02-108">The detailed information and estimated costs are for reference.</span></span> <span data-ttu-id="1da02-109">Le operazioni correlate del controllo qualità sono diverse da quelle che è possibile definire per un ciclo di lavorazione produzione.</span><span class="sxs-lookup"><span data-stu-id="1da02-109">The related operations for quality differ from the operations that can be defined for a production route.</span></span>

> [!NOTE]
> <span data-ttu-id="1da02-110">Sebbene sia possibile tenere traccia dei costi, del tempo e degli articoli utilizzati in un'operazione correlata a una non conformità, i dati immessi sono solo informativi.</span><span class="sxs-lookup"><span data-stu-id="1da02-110">Although you can track costs, time, and the items that are used in an operation that is related to a nonconformance, the data that you enter is only informational.</span></span> <span data-ttu-id="1da02-111">Non vengono integrati automaticamente con la contabilità generale, la contabilità secondaria di magazzino o il modulo **Orario e presenze**.</span><span class="sxs-lookup"><span data-stu-id="1da02-111">It isn't automatically integrated with the general ledger, inventory subledger, or the **Time and attendance** module.</span></span>

## <a name="examples-of-operations"></a><span data-ttu-id="1da02-112">Esempi di operazioni</span><span class="sxs-lookup"><span data-stu-id="1da02-112">Examples of operations</span></span>

<span data-ttu-id="1da02-113">Lavori per un'azienda manifatturiera.</span><span class="sxs-lookup"><span data-stu-id="1da02-113">You work for a manufacturing company.</span></span> <span data-ttu-id="1da02-114">È stata creata e approvata una non conformità per gli articoli che non hanno superato un test di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="1da02-114">A nonconformance was created and approved for items that failed a quality test.</span></span> <span data-ttu-id="1da02-115">È stata creata una correzione per indicare che il problema era correlato a un cuscinetto difettoso su una macchina.</span><span class="sxs-lookup"><span data-stu-id="1da02-115">A correction was created to indicate that the problem was related to a bad bearing on a machine.</span></span> <span data-ttu-id="1da02-116">Sono necessari diversi passaggi per sostituire il cuscinetto e la responsabilità di ciascuna operazione viene monitorata.</span><span class="sxs-lookup"><span data-stu-id="1da02-116">Several steps are required to replace the bearing, and the responsibility for each operation is tracked.</span></span> <span data-ttu-id="1da02-117">Ad esempio, potrebbero essere necessari i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="1da02-117">For example, the following steps might be required:</span></span>

1. <span data-ttu-id="1da02-118">La linea di produzione viene arrestata e viene eseguita la routine di pulizia.</span><span class="sxs-lookup"><span data-stu-id="1da02-118">The production line is stopped, and the clean-out routine is performed.</span></span>
1. <span data-ttu-id="1da02-119">Il personale di manutenzione sostituisce il cuscinetto.</span><span class="sxs-lookup"><span data-stu-id="1da02-119">Maintenance personnel replace the bearing.</span></span>
1. <span data-ttu-id="1da02-120">Il personale addetto al controllo qualità ispeziona la macchina prima che venga riaccesa.</span><span class="sxs-lookup"><span data-stu-id="1da02-120">Quality assurance personnel inspect the machine before it's turned back on.</span></span>

<span data-ttu-id="1da02-121">Per questo esempio, possono essere create le seguenti operazioni per rappresentare il lavoro che deve essere fatto:</span><span class="sxs-lookup"><span data-stu-id="1da02-121">For this example, the following operations can be created to represent the work that must be done:</span></span>

- <span data-ttu-id="1da02-122">Fermare la linea di produzione.</span><span class="sxs-lookup"><span data-stu-id="1da02-122">Stop the production line.</span></span>
- <span data-ttu-id="1da02-123">Pulisci la linea di produzione.</span><span class="sxs-lookup"><span data-stu-id="1da02-123">Clean out the production line.</span></span>
- <span data-ttu-id="1da02-124">Effettuare la manutenzione della macchina.</span><span class="sxs-lookup"><span data-stu-id="1da02-124">Perform machine maintenance.</span></span>
- <span data-ttu-id="1da02-125">Ispeziona la macchina.</span><span class="sxs-lookup"><span data-stu-id="1da02-125">Inspect the machine.</span></span>

## <a name="create-an-operation"></a><span data-ttu-id="1da02-126">Creare un'operazione</span><span class="sxs-lookup"><span data-stu-id="1da02-126">Create an operation</span></span>

1. <span data-ttu-id="1da02-127">Andare a **Gestione articoli \> Impostazioni \> Gestione qualità \> Operazioni**.</span><span class="sxs-lookup"><span data-stu-id="1da02-127">Go to **Inventory management \> Setup \> Quality management \> Operations**.</span></span>
1. <span data-ttu-id="1da02-128">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="1da02-128">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="1da02-129">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="1da02-129">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="1da02-130">**Operazione** – Immetti un ID o nome univoco per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="1da02-130">**Operation** – Enter a unique ID or name for the operation.</span></span>
    - <span data-ttu-id="1da02-131">**Descrizione** - Immettere una descrizione dettagliata della operazione.</span><span class="sxs-lookup"><span data-stu-id="1da02-131">**Description** – Enter a detailed description of the operation.</span></span>
    - <span data-ttu-id="1da02-132">**Tipo** - Se l'operazione può essere utilizzata solo con non conformità correlate a un tipo specifico di ordine, selezionare il tipo di ordine (*Ordine fornitore* o *Ordine cliente*).</span><span class="sxs-lookup"><span data-stu-id="1da02-132">**Type** – If the operation can be used only with nonconformances that are related to a specific type of order, select the order type (*Purchase order* or *Sales order*).</span></span>

1. <span data-ttu-id="1da02-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1da02-133">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1da02-134">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1da02-134">Additional resources</span></span>

- [<span data-ttu-id="1da02-135">Panoramica gestione qualità</span><span class="sxs-lookup"><span data-stu-id="1da02-135">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="1da02-136">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="1da02-136">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="1da02-137">Creare ed elaborare non conformità</span><span class="sxs-lookup"><span data-stu-id="1da02-137">Create and process nonconformances</span></span>](tasks/create-process-non-conformance.md)
- [<span data-ttu-id="1da02-138">Lavoratori responsabili dell'approvazione delle non conformità</span><span class="sxs-lookup"><span data-stu-id="1da02-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="1da02-139">Aree di quarantena per non conformità</span><span class="sxs-lookup"><span data-stu-id="1da02-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="1da02-140">Tipi di diagnostica per non conformità</span><span class="sxs-lookup"><span data-stu-id="1da02-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="1da02-141">Spese di gestione qualità per non conformità</span><span class="sxs-lookup"><span data-stu-id="1da02-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="1da02-142">Tipi di problemi per non conformità</span><span class="sxs-lookup"><span data-stu-id="1da02-142">Problem types for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="1da02-143">Gestione qualità per i processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="1da02-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
