---
title: Pianificazione interaziendale
description: Questo argomento descrive la pianificazione interaziendale e spiega come configurare la pianificazione interaziendale con Ottimizzazione pianificazione in Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd498489e18eaba81720757faa14c0bf7b7d67f1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263400"
---
# <a name="intercompany-planning"></a><span data-ttu-id="ae7b2-103">Pianificazione interaziendale</span><span class="sxs-lookup"><span data-stu-id="ae7b2-103">Intercompany planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ae7b2-104">Per alcune organizzazioni, le operazioni logistiche dipendono da altre persone giuridiche (società) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-104">For some organizations, logistics operations depend on other legal entities (companies) in the organization.</span></span> <span data-ttu-id="ae7b2-105">Queste operazioni vengono gestite utilizzando le vendite e gli acquisti interaziendali, poiché ogni persona giuridica ha un piano dei conti separato.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-105">These operations are handled by using intercompany sales and purchases, because each legal entity has a separate chart of accounts.</span></span>

<span data-ttu-id="ae7b2-106">Questo argomento descrive la pianificazione interaziendale e spiega come configurare la pianificazione interaziendale con Ottimizzazione pianificazione in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-106">This topic describes intercompany planning and explains how to configure intercompany planning with Planning Optimization in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="ae7b2-107">In questo argomento vengono utilizzati i seguenti importanti termini interaziendali:</span><span class="sxs-lookup"><span data-stu-id="ae7b2-107">This topic uses the following important intercompany terms:</span></span>

- <span data-ttu-id="ae7b2-108">**Upstream** - Un riferimento relativo in un'azienda o catena di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-108">**Upstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="ae7b2-109">Indica il movimento nella direzione del fornitore della materia prima.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-109">It indicates movement in the direction of the raw material supplier.</span></span>
- <span data-ttu-id="ae7b2-110">**Downstream** - Un riferimento relativo in un'azienda o catena di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-110">**Downstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="ae7b2-111">Indica il movimento nella direzione del cliente.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-111">It indicates movement in the direction of the customer.</span></span>
- <span data-ttu-id="ae7b2-112">**Domanda interaziendale pianificata** - Domanda pianificata per un prodotto in un'azienda, basata sulla domanda pianificata per il prodotto da un'azienda downstream.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-112">**Planned intercompany demand** – Planned demand for a product in a company, based on planned demand for the product from a downstream company.</span></span>

<span data-ttu-id="ae7b2-113">Nella pianificazione generale, un piano in una società può includere una domanda interaziendale pianificata correlata agli ordini pianificati di un piano di un'altra società.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-113">In master planning, a plan in one company can include planned intercompany demand that is related to planned orders from a plan in another company.</span></span> <span data-ttu-id="ae7b2-114">Questa funzionalità è utile perché fornisce piena visibilità degli ordini pianificati tra le aziende.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-114">This capability is useful, because it provides full visibility into planned orders across companies.</span></span> <span data-ttu-id="ae7b2-115">Assicura inoltre che tutti gli ordini di fornitura pianificati richiesti vengano creati, ma senza richiedere che gli ordini pianificati vengano consolidati per la domanda interaziendale.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-115">It also ensures that all required planned supply orders are created, but without requiring that planned orders be firmed for the intercompany demand.</span></span>

<span data-ttu-id="ae7b2-116">Se si esegue la pianificazione generale da un piano generale che include la domanda downstream pianificata, gli ordini fornitore pianificati dai fornitori interaziendali correlati verranno inclusi nel piano come domanda.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-116">If you run master planning from a master plan that includes planned downstream demand, planned purchase orders from the related intercompany vendors will be included in the plan as demand.</span></span>

## <a name="required-setup"></a><span data-ttu-id="ae7b2-117">Impostazione richiesta</span><span class="sxs-lookup"><span data-stu-id="ae7b2-117">Required setup</span></span>

<span data-ttu-id="ae7b2-118">Per utilizzare la pianificazione interaziendale, è necessario preparare il sistema nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ae7b2-118">To use intercompany planning, you must prepare your system in the following way:</span></span>

1. <span data-ttu-id="ae7b2-119">I prodotti rilevanti devono essere rilasciati in tutte le società interessate.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-119">The relevant products must be released in all the relevant companies.</span></span> <span data-ttu-id="ae7b2-120">Per ulteriori informazioni, vedere [Configurare e usare il commercio interaziendale in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) in Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-120">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="ae7b2-121">La domanda downstream deve essere coperta da acquisti da un fornitore che ha una relazione interaziendale con la società upstream e le relative dimensioni di inventario predefinite (sito e magazzino) per il cliente.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-121">Downstream demand must be covered by purchases from a vendor that has an intercompany relation to the upstream company and relevant default inventory dimensions (site and warehouse) on the customer.</span></span> <span data-ttu-id="ae7b2-122">Per ulteriori informazioni, vedere [Configurare e usare il commercio interaziendale in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) in Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-122">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="ae7b2-123">Il piano generale nella società upstream deve includere la domanda downstream pianificata e la società e il piano generale pertinenti devono essere specificati nei piani downstream.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-123">The master plan in the upstream company must include planned downstream demand, and the relevant company and master plan must be specified in the downstream plans.</span></span>

## <a name="include-planned-downstream-demand"></a><span data-ttu-id="ae7b2-124">Includi domanda downstream pianificata</span><span class="sxs-lookup"><span data-stu-id="ae7b2-124">Include planned downstream demand</span></span>

<span data-ttu-id="ae7b2-125">Seguire questi passaggi per configurare il piano generale in modo che includa la domanda downstream pianificata.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-125">Follow these steps to configure your master plan so that it includes planned downstream demand.</span></span>

1. <span data-ttu-id="ae7b2-126">Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-126">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="ae7b2-127">Selezionare o creare un piano generale.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-127">Select or create a master plan.</span></span>
1. <span data-ttu-id="ae7b2-128">Nella scheda dettaglio **Pianificazione interaziendale**, impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="ae7b2-128">On the **Intercompany planning** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="ae7b2-129">**Includi domanda downstream pianificata** - Impostare questa opzione su *Sì* per abilitare la pianificazione interaziendale per il piano generale.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-129">**Include planned downstream demand** – Set this option to *Yes* to enable intercompany planning for the master plan.</span></span>
    - <span data-ttu-id="ae7b2-130">**Piani downstream** - Se si imposta l'opzione **Includi domanda downstream pianificata** su *Sì*, utilizzare la barra degli strumenti e la griglia per aggiungere i piani generali desiderati da altre società.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-130">**Downstream plans** – If you set the **Include planned downstream demand** option to *Yes*, use the toolbar and grid to add the desired master plans from other companies.</span></span>

## <a name="peg-across-companies-by-using-multilevel-pegging"></a><span data-ttu-id="ae7b2-131">Pegging tra le aziende utilizzando il pegging multilivello</span><span class="sxs-lookup"><span data-stu-id="ae7b2-131">Peg across companies by using multilevel pegging</span></span>

<span data-ttu-id="ae7b2-132">Nel pegging multilivello, è possibile visualizzare il pegging tra le società per vedere l'origine iniziale della domanda coperta da una fornitura.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-132">In multilevel pegging, you can view pegging across companies to see the initial source of demand that is being covered by a supply.</span></span>

<span data-ttu-id="ae7b2-133">Per visualizzare le informazioni sul pegging multilivello, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-133">To view multilevel pegging information, follow these steps.</span></span>

1. <span data-ttu-id="ae7b2-134">Andare a **Pianificazione generale \> Pianificazione generale \> Ordini pianificati**.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-134">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="ae7b2-135">Selezionare o aprire un ordine pianificato.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-135">Select or open a planned order.</span></span>
1. <span data-ttu-id="ae7b2-136">Nella scheda **Visualizza** del riquadro azioni, nel gruppo **Requisiti**, selezionare **Pegging multilivello**.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-136">On the Action Pane, on the **View** tab, in the **Requirements** group, select **Multilevel pegging**.</span></span>

### <a name="intercompany-example-that-involves-two-companies"></a><span data-ttu-id="ae7b2-137">Esempio interaziendale che coinvolge due società</span><span class="sxs-lookup"><span data-stu-id="ae7b2-137">Intercompany example that involves two companies</span></span>

<span data-ttu-id="ae7b2-138">In questo esempio, viene creato un ordine di produzione pianificato nella società USMF per coprire un ordine cliente nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-138">For this example, a planned production order is created in the USMF company to cover a sales order in the DEMF company.</span></span> <span data-ttu-id="ae7b2-139">In USMF, la domanda diretta è la domanda interaziendale pianificata.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-139">In USMF, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="ae7b2-140">Per far apparire questa domanda in USMF, la pianificazione generale viene eseguita prima in DEMF e poi in USMF.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-140">To make this demand appear in USMF, master planning is run first in DEMF and then in USMF.</span></span>

<span data-ttu-id="ae7b2-141">La seguente illustrazione mostra come questo esempio potrebbe apparire nella pagina **Pegging multilivello** per l'ordine di produzione pianificato.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-141">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Esempio interaziendale che coinvolge due società](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a><span data-ttu-id="ae7b2-143">Esempio interaziendale che coinvolge tre società</span><span class="sxs-lookup"><span data-stu-id="ae7b2-143">Intercompany example that involves three companies</span></span>

<span data-ttu-id="ae7b2-144">In questo esempio, viene creato un ordine fornitore pianificato nella società USMF per coprire un ordine cliente nella società FRRT.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-144">For this example, a planned purchase order is created in the USMF company to cover a sales order in the FRRT company.</span></span> <span data-ttu-id="ae7b2-145">Nelle società DEMF e USMF, la domanda diretta è la domanda interaziendale pianificata.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-145">In the DEMF and USMF companies, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="ae7b2-146">Per far apparire questa domanda in USMF, la pianificazione generale viene eseguita prima in FRRT, poi in DEMF e infine in USMF.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-146">To make this demand appear in USMF, master planning is run first in FRRT, then in DEMF, and finally in USMF.</span></span>

<span data-ttu-id="ae7b2-147">La seguente illustrazione mostra come questo esempio potrebbe apparire nella pagina **Pegging multilivello** per l'ordine di produzione pianificato.</span><span class="sxs-lookup"><span data-stu-id="ae7b2-147">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Esempio interaziendale che coinvolge tre società](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]