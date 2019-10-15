---
title: Configurazione dei costi per la gestione ordini distribuiti
description: In questo argomento viene descritta la configurazione dei costi per la gestione degli ordini distribuiti (DOM, Distributed Order Management) in Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b5e3e1997f3d3b61b7b3c7486f5531e386293537
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2019441"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a><span data-ttu-id="e8986-103">Configurazione dei costi per la gestione ordini distribuiti</span><span class="sxs-lookup"><span data-stu-id="e8986-103">Cost configuration for distributed order management (DOM)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8986-104">Per stabilire l'ubicazione ottimale da cui evadere un ordine, le organizzazioni prendono in considerazione più componenti di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-104">Organizations consider multiple cost components to determine the optimal location to fulfill an order from.</span></span> <span data-ttu-id="e8986-105">Alcune componenti sono rappresentate dalla spedizione, il trasporto e l'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="e8986-105">Some of these cost components are shipping cost, handling cost, and packaging cost.</span></span> <span data-ttu-id="e8986-106">Per determinare l'ubicazione di evasione, viene calcolata una combinazione di tali costi.</span><span class="sxs-lookup"><span data-stu-id="e8986-106">A combination of these costs is calculated to determine the fulfillment location.</span></span>

<span data-ttu-id="e8986-107">Nell'ottimizzazione dell'assegnazione degli ordini nelle ubicazioni di evasione durante la prima iterazione di gestione degli ordini distribuiti (DOM) in Dynamics 365 Retail, si teneva conto solo della distanza.</span><span class="sxs-lookup"><span data-stu-id="e8986-107">When the first iteration of distributed order management (DOM) in Dynamics 365 Retail optimized the assignment of orders to fulfillment locations, it factored in distance only.</span></span> <span data-ttu-id="e8986-108">Sebbene la distanza possa essere correlata ai costi, non può essere considerati alla pari di un costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-108">Although distance can be correlated with cost, it isn't the same as cost.</span></span> <span data-ttu-id="e8986-109">Una spedizione effettuata durante la notte, ad esempio, costa più di una spedizione di tre giorni o di sette giorni sulla stessa distanza.</span><span class="sxs-lookup"><span data-stu-id="e8986-109">For example, an overnight shipping method costs more than three-day shipping or seven-day shipping over the same distance.</span></span>

<span data-ttu-id="e8986-110">La funzionalità di configurazione dei costi consente ai rivenditori di definire e configurare componenti di costo aggiuntivo che verranno calcolate e prese in considerazione per determinare l'ubicazione ottimale da cui evadere le righe ordine.</span><span class="sxs-lookup"><span data-stu-id="e8986-110">The cost configuration feature lets retailers define and configure additional cost components that will be calculated and factored in to determine the optimal location to fulfill order lines from.</span></span>

<span data-ttu-id="e8986-111">Quando le componenti di costo vengono configurate, il risolutore DOM utilizza solo tali definizioni di costo per determinare l'ubicazione ottimale per l'evasione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="e8986-111">When cost components are configured, the DOM solver uses only those cost definitions to determine the optimal location for order fulfillment.</span></span> <span data-ttu-id="e8986-112">La distanza non viene considerata come componente di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-112">It doesn't consider the distance component as a cost.</span></span> <span data-ttu-id="e8986-113">Se non viene configurata alcune componente di costo, tuttavia, il risolutore DOM utilizza la distanza come componente di costo per determinare l'ubicazione ottimale per l'evasione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="e8986-113">However, if no cost components are configured, the DOM solver does use the distance component as a cost to determine the optimal location for order fulfillment.</span></span>

## <a name="set-up-cost-components"></a><span data-ttu-id="e8986-114">Configurare le componenti di costo</span><span class="sxs-lookup"><span data-stu-id="e8986-114">Set up cost components</span></span>

<span data-ttu-id="e8986-115">Nel sistema è possibile definire due tipi di componenti di costo principali: **Spedizione** e **Altro**.</span><span class="sxs-lookup"><span data-stu-id="e8986-115">Two major cost component types can be defined in the system: **Shipping** and **Other**.</span></span>

<span data-ttu-id="e8986-116">Entrambi i tipi supportano più basi di calcolo, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e8986-116">Both cost component types support multiple calculation bases, as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e8986-117">Tipo di componente di costo</span><span class="sxs-lookup"><span data-stu-id="e8986-117">Cost component type</span></span></th>
<th><span data-ttu-id="e8986-118">Base di calcolo</span><span class="sxs-lookup"><span data-stu-id="e8986-118">Calculation basis</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e8986-119">Spedizione</span><span class="sxs-lookup"><span data-stu-id="e8986-119">Shipping</span></span></td>
<td>
<ul>
<li><span data-ttu-id="e8986-120">Semplice</span><span class="sxs-lookup"><span data-stu-id="e8986-120">Simple</span></span></li>
<li><span data-ttu-id="e8986-121">A livelli</span><span class="sxs-lookup"><span data-stu-id="e8986-121">Tiered</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="e8986-122">Altro</span><span class="sxs-lookup"><span data-stu-id="e8986-122">Other</span></span></td>
<td>
<ul>
<li><span data-ttu-id="e8986-123">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="e8986-123">Sales order</span></span></li>
<li><span data-ttu-id="e8986-124">Riga di vendita</span><span class="sxs-lookup"><span data-stu-id="e8986-124">Sales line</span></span></li>
<li><span data-ttu-id="e8986-125">Ubicazione</span><span class="sxs-lookup"><span data-stu-id="e8986-125">Location</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a><span data-ttu-id="e8986-126">Tipo di componente di costo Spedizione</span><span class="sxs-lookup"><span data-stu-id="e8986-126">Shipping cost component type</span></span>

<span data-ttu-id="e8986-127">In questa sezione viene descritto come configurare ciascuna combinazione del tipo di componente di costo **Spedizione** e di base di calcolo per i costi di spedizione.</span><span class="sxs-lookup"><span data-stu-id="e8986-127">This section explains how to set up each combination of the **Shipping** cost component type and a calculation basis for shipping costs.</span></span> <span data-ttu-id="e8986-128">Viene inoltre illustrato come il risolutore DOM utilizza ciascuna combinazione.</span><span class="sxs-lookup"><span data-stu-id="e8986-128">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a><span data-ttu-id="e8986-129">Tipo componente di costo = Spedizione e base di calcolo = Semplice</span><span class="sxs-lookup"><span data-stu-id="e8986-129">Cost component type = Shipping and Calculation basis = Simple</span></span>

<span data-ttu-id="e8986-130">Se viene utilizzata una combinazione del tipo di componente di costo **Spedizione** e della base di calcolo **Semplice**, il costo di spedizione per una modalità di consegna si basa su un costo forfettario o sulla distanza.</span><span class="sxs-lookup"><span data-stu-id="e8986-130">If a combination of the **Shipping** cost component type and the **Simple** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span>

<span data-ttu-id="e8986-131">Per questa combinazione, è necessario impostare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8986-131">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="e8986-132">**Fattore costo** - Immettere un identificatore univoco per il fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-132">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="e8986-133">**Descrizione** - Immettere il nome e la descrizione del fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-133">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="e8986-134">**Data di inizio** e **Data di fine** - Questi campi consentono di limitare il fattore di costo per un intervallo di date specifico.</span><span class="sxs-lookup"><span data-stu-id="e8986-134">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="e8986-135">Se questi campi vengono lasciati vuoti, il fattore di costo è valido per un periodo di tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="e8986-135">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="e8986-136">**Attivo** - Indica se il fattore di costo è attivo.</span><span class="sxs-lookup"><span data-stu-id="e8986-136">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="e8986-137">La funzionalità DOM prende in considerazione solo i fattori di costo attivi associati al profilo di evasione.</span><span class="sxs-lookup"><span data-stu-id="e8986-137">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="e8986-138">**Società** - Specifica la persona giuridica per cui è configurato il fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-138">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="e8986-139">Tutte le righe dei criteri di calcolo devono essere correlate alla stessa persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="e8986-139">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="e8986-140">**Modalità di consegna** - Specifica le modalità di consegna per cui è configurato il costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-140">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="e8986-141">**Tipo di calcolo** - Specifica le modalità di calcolo del costo per una determinata modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="e8986-141">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery.</span></span> <span data-ttu-id="e8986-142">Sono supportati due tipi di calcolo:</span><span class="sxs-lookup"><span data-stu-id="e8986-142">Two calculation types are supported:</span></span>

    - <span data-ttu-id="e8986-143">**Fisso** - Per la modalità di consegna viene utilizzato un costo forfettario.</span><span class="sxs-lookup"><span data-stu-id="e8986-143">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="e8986-144">Se si seleziona questo tipo di calcolo, il campo **Costo** definisce il costo forfettario.</span><span class="sxs-lookup"><span data-stu-id="e8986-144">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="e8986-145">**Per unità di distanza** - Il costo per la modalità di consegna viene calcolato come il valore del costo specificato nel campo **Costo** moltiplicato per la distanza tra l'indirizzo di consegna e le ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="e8986-145">**Per-distance unit** – The cost for the mode of delivery is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="e8986-146">**Costo** - Specifica il valore di costo utilizzato in combinazione con il campo **Tipo di calcolo** per calcolare il costo di una modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="e8986-146">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a><span data-ttu-id="e8986-147">Tipo componente di costo = Spedizione e base di calcolo = A livelli</span><span class="sxs-lookup"><span data-stu-id="e8986-147">Cost component type = Shipping and Calculation basis = Tiered</span></span>

<span data-ttu-id="e8986-148">Se viene utilizzata una combinazione del tipo di componente di costo **Spedizione** e della base di calcolo **A livelli**, il costo di spedizione per una modalità di consegna si basa su un costo forfettario o sulla distanza.</span><span class="sxs-lookup"><span data-stu-id="e8986-148">If a combination of the **Shipping** cost component type and the **Tiered** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span> <span data-ttu-id="e8986-149">In questa combinazione, tuttavia, la distanza si basa su un intervallo di distanze a livelli.</span><span class="sxs-lookup"><span data-stu-id="e8986-149">However, in this combination, the distance is based on a tiered range of distances.</span></span>

<span data-ttu-id="e8986-150">Per questa combinazione, è necessario impostare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8986-150">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="e8986-151">**Fattore costo** - Immettere un identificatore univoco per il fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-151">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="e8986-152">**Descrizione** - Immettere il nome e la descrizione del fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-152">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="e8986-153">**Costo predefinito** - Specifica il costo da utilizzare per una modalità di consegna se la distanza tra l'indirizzo di consegna e l'ubicazione non rientra in una delle distanze a livelli per la modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="e8986-153">**Default cost** – Specify the cost that should be used for a mode of delivery if the distance between the delivery address and the location doesn't fall into any of the tiered distances for the mode of delivery.</span></span>
- <span data-ttu-id="e8986-154">**Data di inizio** e **Data di fine** - Questi campi consentono di limitare il fattore di costo per un intervallo di date specifico.</span><span class="sxs-lookup"><span data-stu-id="e8986-154">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="e8986-155">Se questi campi vengono lasciati vuoti, il fattore di costo è valido per un periodo di tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="e8986-155">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="e8986-156">**Attivo** - Indica se il fattore di costo è attivo.</span><span class="sxs-lookup"><span data-stu-id="e8986-156">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="e8986-157">La funzionalità DOM prende in considerazione solo i fattori di costo attivi associati al profilo di evasione.</span><span class="sxs-lookup"><span data-stu-id="e8986-157">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="e8986-158">**Società** - Specifica la persona giuridica per cui è configurato il fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-158">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="e8986-159">Tutte le righe dei criteri di calcolo devono essere correlate alla stessa persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="e8986-159">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="e8986-160">**Modalità di consegna** - Specifica le modalità di consegna per cui è configurato il costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-160">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="e8986-161">**Tipo distanza** - Specifica se la definizione di distanza a livelli è aerea o stradale.</span><span class="sxs-lookup"><span data-stu-id="e8986-161">**Distance type** – Specify whether the tiered distance definition is an aerial distance or a road distance.</span></span>
- <span data-ttu-id="e8986-162">**Unità di distanza** - Specifica l'unità di misura della distanza a livelli.</span><span class="sxs-lookup"><span data-stu-id="e8986-162">**Distance units** – Specify the unit that the tiered distance is measured in.</span></span>
- <span data-ttu-id="e8986-163">**Distanza da** - Specifica l'intervallo iniziale per la distanza a livelli.</span><span class="sxs-lookup"><span data-stu-id="e8986-163">**Distance from** – Specify the start range for the tiered distance.</span></span>
- <span data-ttu-id="e8986-164">**Distanza a** - Specifica l'intervallo finale per la distanza a livelli.</span><span class="sxs-lookup"><span data-stu-id="e8986-164">**Distance to** – Specify the end range for the tiered distance.</span></span>
- <span data-ttu-id="e8986-165">**Tipo di calcolo** - Specifica le modalità di calcolo del costo per una modalità di consegna e una distanza a livelli specifiche.</span><span class="sxs-lookup"><span data-stu-id="e8986-165">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery and tiered distance.</span></span> <span data-ttu-id="e8986-166">Sono supportati due tipi di calcolo:</span><span class="sxs-lookup"><span data-stu-id="e8986-166">Two calculation types are supported:</span></span>

    - <span data-ttu-id="e8986-167">**Fisso** - Per la modalità di consegna viene utilizzato un costo forfettario.</span><span class="sxs-lookup"><span data-stu-id="e8986-167">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="e8986-168">Se si seleziona questo tipo di calcolo, il campo **Costo** definisce il costo forfettario.</span><span class="sxs-lookup"><span data-stu-id="e8986-168">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="e8986-169">**Per unità di distanza** - Il costo per la modalità di consegna e la distanza a livelli viene calcolato come il valore del costo specificato nel campo **Costo** moltiplicato per la distanza tra l'indirizzo di consegna e le ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="e8986-169">**Per distance unit** – The cost for the mode of delivery and tiered distance is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="e8986-170">**Costo** - Specifica il valore di costo utilizzato in combinazione con il campo **Tipo di calcolo** per calcolare il costo di una modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="e8986-170">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

> [!NOTE]
> - <span data-ttu-id="e8986-171">Quando si definiscono le distanze a livelli, nel sistema viene verificato che tutte le distanze siano presenti e che non siano presenti distanze sovrapposte.</span><span class="sxs-lookup"><span data-stu-id="e8986-171">When you define tiered distances, the system validates that there are no missing or overlapping distances.</span></span>
> - <span data-ttu-id="e8986-172">Il tipo di distanza utilizzato per la modalità di consegna deve essere lo stesso per tutte le distanze a livelli.</span><span class="sxs-lookup"><span data-stu-id="e8986-172">The distance type that is used for a mode of delivery must be the same across all the tiered distances.</span></span>

### <a name="other-cost-component-type"></a><span data-ttu-id="e8986-173">Altro tipo di componente di costo</span><span class="sxs-lookup"><span data-stu-id="e8986-173">Other cost component type</span></span>

<span data-ttu-id="e8986-174">In questa sezione viene descritto come configurare ciascuna combinazione del tipo di componente di costo **Altro** e di un altro tipo di costo per costi diversi da quelli di spedizione.</span><span class="sxs-lookup"><span data-stu-id="e8986-174">This section explains how to set up each combination of the **Other** cost component type and an other cost type for non-shipping costs.</span></span> <span data-ttu-id="e8986-175">Viene inoltre illustrato come il risolutore DOM utilizza ciascuna combinazione.</span><span class="sxs-lookup"><span data-stu-id="e8986-175">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a><span data-ttu-id="e8986-176">Tipo di componente di costo = Altro e altro tipo di costo = Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="e8986-176">Cost component type = Other and Other cost type = Sales order</span></span>

<span data-ttu-id="e8986-177">Una combinazione del tipo di componente di costo **Altro** e di un altro tipo di costo **Ordine cliente** viene utilizzata per definire costi diversi da quelli di spedizione a livello di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="e8986-177">A combination of the **Other** cost component type and the **Sales order** other cost type is used to define non-shipping costs at the sales order level.</span></span>

<span data-ttu-id="e8986-178">Per questa combinazione, è necessario impostare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8986-178">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="e8986-179">**Fattore costo** - Immettere un identificatore univoco per il fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-179">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="e8986-180">**Descrizione** - Immettere il nome e la descrizione del fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-180">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="e8986-181">**Data di inizio** e **Data di fine** - Questi campi consentono di limitare il fattore di costo per un intervallo di date specifico.</span><span class="sxs-lookup"><span data-stu-id="e8986-181">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="e8986-182">Se questi campi vengono lasciati vuoti, il fattore di costo è valido per un periodo di tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="e8986-182">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="e8986-183">**Attivo** - Indica se il fattore di costo è attivo.</span><span class="sxs-lookup"><span data-stu-id="e8986-183">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="e8986-184">La funzionalità DOM prende in considerazione solo i fattori di costo attivi associati al profilo di evasione.</span><span class="sxs-lookup"><span data-stu-id="e8986-184">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="e8986-185">**Costo** - Specifica il valore del costo per un costo diverso da quello di spedizione a livello di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="e8986-185">**Cost** – Specify the cost value for a non-shipping cost at the sales order level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a><span data-ttu-id="e8986-186">Tipo di componente di costo = Altro e altro tipo di costo = Riga ordine</span><span class="sxs-lookup"><span data-stu-id="e8986-186">Cost component type = Other and Other cost type = Sales line</span></span>

<span data-ttu-id="e8986-187">Una combinazione del tipo di componente di costo **Altro** e di un altro tipo di costo **Riga vendita** viene utilizzata per definire costi diversi da quelli di spedizione a livello di riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="e8986-187">A combination of the **Other** cost component type and the **Sales line** other cost type is used to define non-shipping costs at the sales order line level.</span></span>

<span data-ttu-id="e8986-188">Per questa combinazione, è necessario impostare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8986-188">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="e8986-189">**Fattore costo** - Immettere un identificatore univoco per il fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-189">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="e8986-190">**Descrizione** - Immettere il nome e la descrizione del fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-190">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="e8986-191">**Data di inizio** e **Data di fine** - Questi campi consentono di limitare il fattore di costo per un intervallo di date specifico.</span><span class="sxs-lookup"><span data-stu-id="e8986-191">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="e8986-192">Se questi campi vengono lasciati vuoti, il fattore di costo è valido per un periodo di tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="e8986-192">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="e8986-193">**Attivo** - Indica se il fattore di costo è attivo.</span><span class="sxs-lookup"><span data-stu-id="e8986-193">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="e8986-194">La funzionalità DOM prende in considerazione solo i fattori di costo attivi associati al profilo di evasione.</span><span class="sxs-lookup"><span data-stu-id="e8986-194">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="e8986-195">**Costo** - Specifica il valore del costo per un costo diverso da quello di spedizione a livello di riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="e8986-195">**Cost** – Specify the cost value for a non-shipping cost at the sales order line level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--location"></a><span data-ttu-id="e8986-196">Tipo di componente di costo = Altro e altro tipo di costo = Ubicazione</span><span class="sxs-lookup"><span data-stu-id="e8986-196">Cost component type = Other and Other cost type = Location</span></span>

<span data-ttu-id="e8986-197">Una combinazione del tipo di componente di costo **Altro** e di un altro tipo di costo **Ubicazione** viene utilizzato per definire costi diversi da quelli di spedizione per un gruppo di ubicazioni o per un'ubicazione singola.</span><span class="sxs-lookup"><span data-stu-id="e8986-197">A combination of the **Other** cost component type and the **Location** other cost type is used to define non-shipping costs for a group of locations or an individual location.</span></span>

<span data-ttu-id="e8986-198">Per questa combinazione, è necessario impostare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8986-198">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="e8986-199">**Fattore costo** - Immettere un identificatore univoco per il fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-199">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="e8986-200">**Descrizione** - Immettere il nome e la descrizione del fattore di costo.</span><span class="sxs-lookup"><span data-stu-id="e8986-200">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="e8986-201">**Data di inizio** e **Data di fine** - Questi campi consentono di limitare il fattore di costo per un intervallo di date specifico.</span><span class="sxs-lookup"><span data-stu-id="e8986-201">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="e8986-202">Se questi campi vengono lasciati vuoti, il fattore di costo è valido per un periodo di tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="e8986-202">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="e8986-203">**Attivo** - Indica se il fattore di costo è attivo.</span><span class="sxs-lookup"><span data-stu-id="e8986-203">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="e8986-204">La funzionalità DOM prende in considerazione solo i fattori di costo attivi associati al profilo di evasione.</span><span class="sxs-lookup"><span data-stu-id="e8986-204">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="e8986-205">**Gruppo di evasione** - Specifica il gruppo di ubicazioni per cui è definito il costo diverso da quello di spedizione.</span><span class="sxs-lookup"><span data-stu-id="e8986-205">**Fulfillment group** – Specify the group of locations that the non-shipping cost is defined for.</span></span>
- <span data-ttu-id="e8986-206">**Ubicazione di evasione** - Specifica l'ubicazione per cui è definito il costo diverso da quello di spedizione.</span><span class="sxs-lookup"><span data-stu-id="e8986-206">**Fulfillment location** – Specify the location that the non-shipping cost is defined for.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e8986-207">Non è possibile specificare un gruppo di evasione né un'ubicazione di evasione sulla stessa riga per i criteri di calcolo basati sull'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="e8986-207">You can't specify a fulfillment group and a fulfillment location on the same line for location-based calculation criteria.</span></span>

- <span data-ttu-id="e8986-208">**Costo** - Specifica il valore del costo per un costo diverso da quello di spedizione a livello di gruppo o di ubicazione di evasione.</span><span class="sxs-lookup"><span data-stu-id="e8986-208">**Cost** – Specify the cost value for a non-shipping cost at the fulfillment group level or fulfillment location level.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8986-209">La funzionalità DOM prende in considerazione questi costi durante l'esecuzione solo se il fattore di costo viene aggiunto al profilo di evasione rilevante.</span><span class="sxs-lookup"><span data-stu-id="e8986-209">For DOM to consider these costs when it's run, you must add the cost factor to the relevant fulfillment profile.</span></span>
