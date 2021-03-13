---
title: Ordini di magazzino per unità di scala nel cloud e nella rete perimetrale
description: In questo argomento vengono fornite informazioni sulla capacità degli ordini di magazzino utilizzata come parte del carico di lavoro dell'unità di scala di magazzino.
author: perlynne
manager: tfeyr
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c04127b9fe621d962be2d7fe06358b3bd1b78916
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5105714"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a><span data-ttu-id="a177a-103">Ordini di magazzino per unità di scala nel cloud e nella rete perimetrale</span><span class="sxs-lookup"><span data-stu-id="a177a-103">Warehouse orders for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="a177a-104">Non tutte le funzionalità aziendali sono completamente supportate nell'anteprima pubblica quando vengono utilizzati i carichi di lavoro delle unità di scala.</span><span class="sxs-lookup"><span data-stu-id="a177a-104">Not all business functionality is fully supported in the public preview when scale unit workloads are used.</span></span> <span data-ttu-id="a177a-105">Se stai utilizzando le unità di scala, assicurati di utilizzare solo i processi che in questo argomento vengono descritti come supportati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="a177a-105">If you're using scale units, be sure to use only those processes that this topic explicitly describes as supported.</span></span>

## <a name="what-are-warehouse-orders"></a><span data-ttu-id="a177a-106">Cosa sono gli ordini di magazzino?</span><span class="sxs-lookup"><span data-stu-id="a177a-106">What are warehouse orders?</span></span>

<span data-ttu-id="a177a-107">Gli *ordini di magazzino* sono un tipo di ordine creato per supportare le distribuzioni di hub e unità di scala in magazzino.</span><span class="sxs-lookup"><span data-stu-id="a177a-107">*Warehouse orders* are a type of order that was created to support hub and scale unit warehouse deployments.</span></span> <span data-ttu-id="a177a-108">Ti consentono di ricevere le scorte quando esegui un carico di lavoro di magazzino su un'unità di scala.</span><span class="sxs-lookup"><span data-stu-id="a177a-108">They let you receive inventory when you're running a warehouse workload on a scale unit.</span></span> <span data-ttu-id="a177a-109">Attualmente sono utilizzati solo con ordini di acquisto.</span><span class="sxs-lookup"><span data-stu-id="a177a-109">They are currently used only with purchase orders.</span></span>

<span data-ttu-id="a177a-110">Gli ordini di magazzino vengono utilizzati come parte dell'elaborazione della gestione del magazzino, ad esempio quando l'app di magazzino viene utilizzata per registrare le scorte fisiche disponibili durante l'elaborazione di un ordine fornitore in entrata.</span><span class="sxs-lookup"><span data-stu-id="a177a-110">Warehouse orders are used as part of warehouse management processing, such as when the warehouse app is used to register physical on-hand inventory during processing of an inbound purchase order.</span></span> <span data-ttu-id="a177a-111">Gli ordini di magazzino vengono creati come parte del processo *Rilascia in magazzino* disponibile per ordini fornitore che specificano un magazzino di unità di scala e articoli abilitati all'utilizzo dei processi di gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="a177a-111">Warehouse orders are created as part of the *Release to warehouse* process that is available for purchase orders that specify a scale unit warehouse and items that are enabled to use warehouse management processes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a177a-112">Gli ordini di magazzino sono disponibili solo nelle distribuzioni che utilizzano [carichi di lavoro di gestione del magazzino per unità di scala cloud e perimetrali](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="a177a-112">Warehouse orders are available only in deployments that use [warehouse management workloads for cloud and edge scale units](cloud-edge-workload-warehousing.md).</span></span>

## <a name="create-a-warehouse-order"></a><span data-ttu-id="a177a-113">Creare un ordine di magazzino</span><span class="sxs-lookup"><span data-stu-id="a177a-113">Create a warehouse order</span></span>

<span data-ttu-id="a177a-114">Per creare un ordine di magazzino, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a177a-114">To create a warehouse order, follow these steps.</span></span>

1. <span data-ttu-id="a177a-115">Accedi all'istanza di Microsoft Dynamics 365 Supply Chain Management in esecuzione nell'hub.</span><span class="sxs-lookup"><span data-stu-id="a177a-115">Sign in to the instance of Microsoft Dynamics 365 Supply Chain Management that is running on the hub.</span></span> <span data-ttu-id="a177a-116">Devi avviare il processo *Rilascia in magazzino* mentre sei connesso all'hub.</span><span class="sxs-lookup"><span data-stu-id="a177a-116">(You must initiate the *Release to warehouse* process while you're signed in on the hub.)</span></span>
1. <span data-ttu-id="a177a-117">Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="a177a-117">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="a177a-118">Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a177a-118">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="a177a-119">Per visualizzare le righe dell'ordine di magazzino correlate, apri l'ordine fornitore acquisto pertinente, seleziona una riga nella sezione **Righe ordine di acquisto**, quindi, sulla barra degli strumenti, seleziona **Magazzino \> Righe ordine di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a177a-119">To view the related warehouse order lines, open the relevant purchase order, select a line in the **Purchase order lines** section, and then, on the toolbar, select **Warehouse \> Warehouse order lines**.</span></span> <span data-ttu-id="a177a-120">Per visualizzare tutte le righe, vai a **Gestione magazzino \> Richieste e segnalazioni \> Righe ordine di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a177a-120">To view all the lines, go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>

## <a name="cancel-a-warehouse-order"></a><span data-ttu-id="a177a-121">Annullare un ordine di magazzino</span><span class="sxs-lookup"><span data-stu-id="a177a-121">Cancel a warehouse order</span></span>

<span data-ttu-id="a177a-122">Come parte del processo *Rilascia in magazzino*, le transazioni di magazzino dell'ordine fornitore sono collegate agli ordini di magazzino e bloccate dall'aggiornamento dall'hub.</span><span class="sxs-lookup"><span data-stu-id="a177a-122">As part of the *Release to warehouse* process, purchase order inventory transactions are linked to warehouse orders and locked from being updated by the hub.</span></span> <span data-ttu-id="a177a-123">Se hai rilasciato al magazzino per errore o se hai altri motivi per annullare la creazione di righe ordine di magazzino, puoi richiedere di annullare le righe ordine di magazzino.</span><span class="sxs-lookup"><span data-stu-id="a177a-123">If you released to the warehouse by mistake, or if you have some other reason to reverse the creation of warehouse order lines, you can request to cancel warehouse order lines.</span></span>

<span data-ttu-id="a177a-124">Per annullare le righe dell'ordine di magazzino, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a177a-124">To cancel warehouse order lines, follow these steps.</span></span>

1. <span data-ttu-id="a177a-125">Accedi all'istanza di Supply Chain Management in esecuzione nell'hub.</span><span class="sxs-lookup"><span data-stu-id="a177a-125">Sign in to the Supply Chain Management instance that is running on the hub.</span></span>
1. <span data-ttu-id="a177a-126">Vai a **Gestione magazzino \> Richieste e segnalazioni \> Righe ordine di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a177a-126">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>
1. <span data-ttu-id="a177a-127">Seleziona la riga pertinente.</span><span class="sxs-lookup"><span data-stu-id="a177a-127">Select the relevant line.</span></span>
1. <span data-ttu-id="a177a-128">Nel riquadro azioni seleziona **Annulla righe ordine di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a177a-128">On the Action Pane, select **Cancel warehouse order lines**.</span></span>

> [!NOTE]
> <span data-ttu-id="a177a-129">La richiesta di annullamento delle righe verrà rifiutata per tutte le righe che sono già in attesa di annullamento o che sono attivamente elaborate in un magazzino che esegue il proprio carico di lavoro su un'unità di scala.</span><span class="sxs-lookup"><span data-stu-id="a177a-129">The request to cancel lines will be denied for any lines that are already pending cancellation or that are actively being processed at a warehouse that is running its workload on a scale unit.</span></span>

## <a name="monitor-a-warehouse-order"></a><span data-ttu-id="a177a-130">Monitorare un ordine di magazzino</span><span class="sxs-lookup"><span data-stu-id="a177a-130">Monitor a warehouse order</span></span>

<span data-ttu-id="a177a-131">Nella visualizzazione **Righe ordine di magazzino** è possibile monitorare l'avanzamento del ricevimento in entrata rivedendo i valori nella colonna **Quantità rimasta da ricevere**.</span><span class="sxs-lookup"><span data-stu-id="a177a-131">In the **Warehouse order lines** view, you can monitor the progress of inbound receiving by reviewing the values in the **Quantity left to receive** column.</span></span> <span data-ttu-id="a177a-132">Per visualizzare i dettagli relativi al lavoro svolto utilizzando l'app di magazzino, segui uno di questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a177a-132">To view details that are related to work that is done by using the warehouse app, follow one of these steps.</span></span>

- <span data-ttu-id="a177a-133">Vai a **Gestione magazzino \> Richieste e segnalazioni \> Righe ordine di magazzino** e utilizza il filtro per trovare le righe che stai cercando.</span><span class="sxs-lookup"><span data-stu-id="a177a-133">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**, and use the filter to find the lines that you're looking for.</span></span>
- <span data-ttu-id="a177a-134">Vai a **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore** e apri l'ordine fornitore pertinente.</span><span class="sxs-lookup"><span data-stu-id="a177a-134">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**, and open the relevant purchase order.</span></span> <span data-ttu-id="a177a-135">Nella sezione **Righe ordine fornitore**, seleziona una o più righe, quindi, sulla barra degli strumenti, seleziona **Magazzino \> Voci di ricevimento magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a177a-135">In the **Purchase order lines** section, select one or more lines, and then, on the toolbar, select **Warehouse \> Warehouse receipt entries**.</span></span>
