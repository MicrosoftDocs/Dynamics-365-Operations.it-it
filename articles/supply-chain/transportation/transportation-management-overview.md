---
title: Panoramica sulla gestione trasporto
description: In questo argomento viene fornita una panoramica della funzionalità di gestione del trasporto in Supply Chain Management.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench, TMSLoadBuildTemplateApply, WHSLoadTemplate, TMSTransportationStatus, TMSLoadSeal, TMSLoadBuildProposal, TMSLoadBuildWorkbench, TMSLoadBuildStrategy, TMSLoadBuildStrategyAttributeValue
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fca83ef2c80ed6df9cfbdedd2805e453df3f737a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006493"
---
# <a name="transportation-management-overview"></a><span data-ttu-id="8e6c1-103">Panoramica gestione trasporto</span><span class="sxs-lookup"><span data-stu-id="8e6c1-103">Transportation management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8e6c1-104">In questo argomento viene fornita una panoramica della funzionalità di gestione del trasporto in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-104">This topic gives an overview of the transportation management functionality in Supply Chain Management.</span></span>

<span data-ttu-id="8e6c1-105">Gestione trasporto consente di utilizzare il trasporto della società e di identificare soluzioni fornitori e percorsi di trasferimento per gli ordini in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-105">Transportation management lets you use your company’s transportation, and also lets you identify vendor and routing solutions for inbound and outbound orders.</span></span> <span data-ttu-id="8e6c1-106">Ad esempio, è possibile identificare il ciclo di lavorazione più veloce o la tariffa più economica per una spedizione.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-106">For example, you can identify the fastest route or the least expensive rate for a shipment.</span></span> <span data-ttu-id="8e6c1-107">Nella tabella seguente vengono descritti gli scenari principali per l'uso di Gestione trasporto.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-107">The following table describes the main scenarios for using Transportation management.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e6c1-108">Scenario</span><span class="sxs-lookup"><span data-stu-id="8e6c1-108">Scenario</span></span></th>
<th><span data-ttu-id="8e6c1-109">Utilità di Gestione trasporto</span><span class="sxs-lookup"><span data-stu-id="8e6c1-109">How Transportation management can help</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8e6c1-110">Utilizzare i provider di servizi logistici esterni per le attività di trasporto.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-110">Use external logistics providers for transportation activities.</span></span></td>
<td><span data-ttu-id="8e6c1-111">Utilizzare Gestione trasporto per il trasporto in uscita e/o in ingresso.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-111">Use Transportation management for inbound and/or outbound transportation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8e6c1-112">La flotta della società è disponibile per la consegna/prelievo e le spese di consegna vengono passate ai clienti.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-112">The company&#39;s own fleet is available for delivery/pickup, and delivery charges are passed on to customers.</span></span></td>
<td><span data-ttu-id="8e6c1-113">Per i processi in uscita, è possibile utilizzare Gestione trasporto per determinare le spese di trasporto e passarle ai clienti.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-113">For the outbound processes, you can use Transportation management to determine the transportation charges and pass them on to customers.</span></span> <span data-ttu-id="8e6c1-114">Tuttavia, il processo di riconciliazione fattura vettore non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-114">However, the carrier invoice reconciliation process isn&#39;t required.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8e6c1-115">La flotta specifica della società è disponibile per la consegna/prelievo, ma le spese di consegna non vengono passate ai clienti perché i prezzi dei prodotti includono il trasporto.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-115">The company&#39;s own fleet is available for delivery/pickup, but delivery charges aren&#39;t passed on to customers, because product prices include transportation.</span></span></td>
<td><span data-ttu-id="8e6c1-116">Molte delle funzionalità di gestione trasporto non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-116">A lot of the Transportation management functionality isn&#39;t required.</span></span> <span data-ttu-id="8e6c1-117">È tuttavia possibile utilizzare Gestione trasporto per determinare le tariffe di trasporto e modificare di conseguenza il prezzo di vendita.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-117">However, you can use Transportation management to determine the transportation rates and adjust the sales price accordingly.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8e6c1-118">Il servizio di logistica viene fornito da un'altra persona giuridica della stessa società.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-118">Logistics service is provided by another legal entity in the same company.</span></span></td>
<td><ul>
<li><span data-ttu-id="8e6c1-119">È possibile utilizzare Gestione trasporto trattando l'altra persona giuridica come qualsiasi altro vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-119">You can use Transportation management by treating the other legal entity like any other shipping carrier.</span></span> <span data-ttu-id="8e6c1-120">Non è possibile automatizzare le transazioni economiche tra persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-120">You can&#39;t automate the economic transactions between legal entities.</span></span> <span data-ttu-id="8e6c1-121">Di conseguenza, è necessario gestire le transazioni manualmente, creando, ad esempio, un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-121">Therefore, you must handle these transactions manually (for example, by creating a purchase order).</span></span></li>
<li><span data-ttu-id="8e6c1-122">Nella persona giuridica che fornisce i servizi di logistica, la funzionalità Gestione trasporto può essere utilizzata per determinare le tariffe di trasporto.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-122">In the legal entity that provides the logistics services, Transportation management can be used to determine transportation rates.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-supply-chain-management"></a><span data-ttu-id="8e6c1-123">Pianificazione del trasporto in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8e6c1-123">Planning transportation in Supply Chain Management</span></span>
<span data-ttu-id="8e6c1-124">In Gestione trasporto, la pianificazione del trasporto può essere basata sugli ordini o sulle spedizioni create in base a tali ordini.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-124">In Transportation management, transportation planning can be based either on orders or on the shipments that are created based on those orders.</span></span> <span data-ttu-id="8e6c1-125">Le spedizioni sono sempre presenti in un determinato momento, ma non sono necessarie per la pianificazione del trasporto.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-125">The shipments always exist at some point in time but aren't required for transportation planning.</span></span> <span data-ttu-id="8e6c1-126">Gli ordini di trasferimento fanno parte dello scenario in uscita e possono essere pianificati insieme agli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-126">Transfer orders are part of the outbound scenario and can be planned together with sales orders.</span></span> 

![Emissione del carico](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a><span data-ttu-id="8e6c1-128">Trasporto in uscita</span><span class="sxs-lookup"><span data-stu-id="8e6c1-128">Inbound transportation</span></span>
<span data-ttu-id="8e6c1-129">Quando si ordinano gli articoli da un fornitore e gli articoli devono essere consegnati al proprio magazzino, è consigliabile organizzare il trasporto degli articoli personalmente.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-129">When you order items from a vendor, and the items must be delivered to your warehouse, you might want to arrange the transport of the items yourself.</span></span> <span data-ttu-id="8e6c1-130">È possibile utilizzare Supply Chain Management per pianificare il trasporto e la ricezione del carico in entrata.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-130">You can use Supply Chain Management to plan the transportation and receipt of the inbound load.</span></span> <span data-ttu-id="8e6c1-131">Nella seguente figura viene illustrato il flusso del processo aziendale per pianificare il trasporto per un carico in entrata.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-131">The following illustration shows the business process flow for planning transportation for an inbound load.</span></span> 

![Flusso di processo aziendale per il trasporto del carico in ingresso](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a><span data-ttu-id="8e6c1-133">Trasporto in uscita</span><span class="sxs-lookup"><span data-stu-id="8e6c1-133">Outbound transportation</span></span>
<span data-ttu-id="8e6c1-134">È possibile pianificare ed elaborare un carico in uscita per spedire articoli specifici dal magazzino di una società a un cliente.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-134">You can plan and process an outbound load to ship specific items from a company’s warehouse to a customer.</span></span> <span data-ttu-id="8e6c1-135">È possibile utilizzare Supply Chain Management per pianificare il trasporto e la spedizione di un carico in uscita.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-135">You can use Supply Chain Management to plan the transportation and shipping of an outbound load.</span></span> <span data-ttu-id="8e6c1-136">Nella seguente figura viene illustrato il flusso del processo aziendale per la pianificazione e l'elaborazione di carichi in uscita da spedire.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-136">The following illustration shows the business process flow for planning and processing outbound loads for shipping.</span></span> 

![Pianificazione ed elaborazione dei carichi in uscita](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a><span data-ttu-id="8e6c1-138">Allestimento del carico</span><span class="sxs-lookup"><span data-stu-id="8e6c1-138">Load building</span></span>
<span data-ttu-id="8e6c1-139">Supply Chain Management offre una strategia di allestimento del carico denominata strategia di allestimento del carico basata sul volume.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-139">Supply Chain Management provides a load building strategy that is named the Volume-based load building strategy.</span></span> <span data-ttu-id="8e6c1-140">Questa strategia consente di utilizzare i valori massimi specificati per l'altezza e il peso nel modello di carico o di sostituire le impostazioni con nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-140">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="8e6c1-141">Per utilizzare questa strategia, selezionarla nel campo **Strategia di allestimento del carico** nella scheda dettaglio **Impostazioni** della pagina **Workbench di allestimento del carico**.</span><span class="sxs-lookup"><span data-stu-id="8e6c1-141">To use this strategy, select it in the **Load building strategy** field on the **Setup** FastTab on the **Load building workbench** page.</span></span> <span data-ttu-id="8e6c1-142">Inoltre, è possibile aggiungere strategie di allestimento del carico personalizzate creando una nuova classe nella struttura a oggetti applicativi (AOT).</span><span class="sxs-lookup"><span data-stu-id="8e6c1-142">In addition, you can add your own load-building strategies by creating a new class in the Application Object Tree (AOT).</span></span>



