---
title: Cespiti e ordini di lavoro
description: Questo argomento illustra cespiti e ordini di lavoro in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24d75000e2c4b604e1acee94e9581291e156fa5d
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017413"
---
# <a name="assets-and-work-orders"></a><span data-ttu-id="8c79a-103">Cespiti e ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="8c79a-103">Assets and work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="8c79a-104">Questo argomento illustra cespiti e ordini di lavoro in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="8c79a-104">This topic describes assets and work orders in Asset Management.</span></span> <span data-ttu-id="8c79a-105">I cespiti e gli ordini di lavoro sono le parti centrali di Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="8c79a-105">Assets and work orders are the central parts of Asset Management.</span></span> <span data-ttu-id="8c79a-106">Un *cespite* è una macchina o parte di macchina che richiede manutenzione e assistenza regolari.</span><span class="sxs-lookup"><span data-stu-id="8c79a-106">An *asset* is a machine or machine part that requires continuous maintenance and service.</span></span> <span data-ttu-id="8c79a-107">I cespiti possono essere creati in una struttura gerarchica e possono essere correlati alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="8c79a-107">Assets can be created in a hierarchical structure, and they can be related to functional locations.</span></span> <span data-ttu-id="8c79a-108">I processi di manutenzione possono essere pianificati a tutti i livelli della struttura di cespiti.</span><span class="sxs-lookup"><span data-stu-id="8c79a-108">Maintenance jobs can be planned at all levels in the asset structure.</span></span>

<span data-ttu-id="8c79a-109">I vari dati, ad esempio informazioni sul prodotto e specifica del cespite, e i piani di manutenzione necessari sono impostati su ciascun cespite.</span><span class="sxs-lookup"><span data-stu-id="8c79a-109">Various data, such as product information and asset specification, and required maintenance plans are set up on each asset.</span></span> <span data-ttu-id="8c79a-110">Nella seguente figura è illustrata una panoramica dei dati dei cespiti e del rapporto tra cespiti e tipi di processo.</span><span class="sxs-lookup"><span data-stu-id="8c79a-110">The following illustration shows an overview of asset data and the affiliation of assets to job types.</span></span> <span data-ttu-id="8c79a-111">Il rosso testo viene utilizzato per alcuni esempi relativi a ereditarietà e dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8c79a-111">Red text is used for examples that show inheritance and dependencies.</span></span>

![Figura 1](media/05-overview-image.png)

<span data-ttu-id="8c79a-113">Ogni ordine di lavoro ha un tipo di ordine di lavoro, ad esempio manutenzione preventiva, manutenzione correttiva o ispezione.</span><span class="sxs-lookup"><span data-stu-id="8c79a-113">Every work order has a work order type, such preventive maintenance, corrective maintenance, or inspection.</span></span> <span data-ttu-id="8c79a-114">L'ordine di lavoro contiene uno o più processi dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c79a-114">The work order contains one or more work order jobs.</span></span> <span data-ttu-id="8c79a-115">Ogni processo dell'ordine di lavoro definisce un processo che deve essere eseguito su un cespite e un tipo di processo correlato.</span><span class="sxs-lookup"><span data-stu-id="8c79a-115">Every work order job defines a job that must be performed on an asset and a related job type.</span></span> <span data-ttu-id="8c79a-116">Esempi di tipi di processo correlati sono l'ispezione a 10.000 km, a 50.000 km, la revisione dopo un anno e l'ispezione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8c79a-116">Examples of related job types include 10,000 km, 50,000 km, 1-year overhaul, and safety inspection.</span></span> <span data-ttu-id="8c79a-117">Un solo ordine di lavoro può essere correlato a più cespiti.</span><span class="sxs-lookup"><span data-stu-id="8c79a-117">One work order can be related to multiple assets.</span></span>

<span data-ttu-id="8c79a-118">Nella seguente figura è illustrata una panoramica dei dati importanti in un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c79a-118">The following illustration shows an overview of the key data in a work order.</span></span>

![Figura 2](media/06-overview-image.png)

<span data-ttu-id="8c79a-120">Un ordine di lavoro può essere correlato a un altro ordine di lavoro e i tipi di processo possono contenere i successivi processi che creano un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c79a-120">A work order can be related to another work order, and job types can contain succeeding jobs that create a work order.</span></span> <span data-ttu-id="8c79a-121">In generale non ci sono dipendenze tra gli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c79a-121">In general, there are no dependencies between work orders.</span></span> <span data-ttu-id="8c79a-122">Di conseguenza, possono modificare il loro stato del ciclo di vita e possono essere programmati indipendentemente l'uno dall'altro.</span><span class="sxs-lookup"><span data-stu-id="8c79a-122">Therefore, they can change their work order lifecycle state and can be scheduled independently of each other.</span></span>

<span data-ttu-id="8c79a-123">Gli ordini di lavoro possono essere creati in vari modi correlati alla manutenzione correttiva, preventiva o reattiva.</span><span class="sxs-lookup"><span data-stu-id="8c79a-123">Work orders can be created in various ways that are related to corrective, preventive, or reactive maintenance.</span></span> <span data-ttu-id="8c79a-124">È inoltre possibile creare ordini di lavoro manualmente.</span><span class="sxs-lookup"><span data-stu-id="8c79a-124">You can also create work orders manually.</span></span> <span data-ttu-id="8c79a-125">Nella seguente figura è illustrata una panoramica del processo per la creazione automatica o manuale degli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c79a-125">The following illustration shows an overview of the process for automatic or manual creation of work orders.</span></span>

![Figura 3](media/07-overview-image.png)

<span data-ttu-id="8c79a-127">Diversi passaggi devono essere completati quando si desidera programmare ed eseguire un processo di manutenzione in un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c79a-127">Several steps must be completed when you want to schedule and run a maintenance job on a work order.</span></span> <span data-ttu-id="8c79a-128">Nella seguente figura è illustrata una panoramica dell'elaborazione di un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c79a-128">The following illustration shows an overview of the processing for a work order.</span></span>

![Figura 4](media/08-overview-image.png)

> [!NOTE]
> <span data-ttu-id="8c79a-130">In genere quando si lavora in Dynamics 365 Supply Chain Management e nel modulo **Gestione cespiti**, si seleziona **Nuovo** per creare un nuovo record, **Modifica** per aggiornare un record esistente e si seleziona **Salva** per salvare i dati nuovi o modificati.</span><span class="sxs-lookup"><span data-stu-id="8c79a-130">In general, when you work in Dynamics 365 Supply Chain Management and the **Asset Management** module, you select **New** to create a new record, you select **Edit** to update an existing record, and you select **Save** to save new or edited data.</span></span>
