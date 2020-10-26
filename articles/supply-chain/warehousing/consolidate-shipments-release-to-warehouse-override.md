---
title: Consolidare le spedizioni quando i criteri di consolidamento delle spedizioni vengono ignorati dalla pagina Rilascia in magazzino
description: Questo argomento presenta uno scenario in cui una o più righe di vendita devono essere rilasciate manualmente al magazzino dalla pagina Rilascia in magazzino e i criteri di consolidamento della spedizione definiti dal sistema devono essere ignorati prima del rilascio.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 406ff268eede4a9d448b3b9c1729a00fcec8f21e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986746"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden-from-the-release-to-warehouse-page"></a><span data-ttu-id="d1254-103">Consolidare le spedizioni quando i criteri di consolidamento delle spedizioni vengono ignorati dalla pagina Rilascia in magazzino</span><span class="sxs-lookup"><span data-stu-id="d1254-103">Consolidate shipments when the shipment consolidation policy is overridden from the Release to warehouse page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1254-104">Questo argomento presenta uno scenario in cui una o più righe di vendita devono essere rilasciate manualmente al magazzino dalla pagina **Rilascia in magazzino** e i criteri di consolidamento della spedizione definiti dal sistema devono essere ignorati prima del rilascio.</span><span class="sxs-lookup"><span data-stu-id="d1254-104">This topic presents a scenario where one or more sales lines must be manually released to the warehouse from the **Release to warehouse** page, and the system-defined shipment consolidation policy must be overridden before the release.</span></span> <span data-ttu-id="d1254-105">Potrebbe essere necessario sostituire i criteri di consolidamento della spedizione se, ad esempio, un ordine che di solito non è consolidato con spedizioni aperte deve essere consolidato con spedizioni aperte.</span><span class="sxs-lookup"><span data-stu-id="d1254-105">An override of the shipment consolidation policy might be required if, for example, an order that isn't usually consolidated with open shipments must be consolidated with open shipments.</span></span>

<span data-ttu-id="d1254-106">Durante lo scenario, creerai un insieme di ordini cliente e quindi sovrascriverai i criteri di consolidamento della spedizione predefinita prima di rilasciare gli ordini al magazzino.</span><span class="sxs-lookup"><span data-stu-id="d1254-106">During the scenario, you will create a set of sales orders and then override the default shipment consolidation policy before you release the orders to the warehouse.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="d1254-107">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="d1254-107">Make demo data available</span></span>

<span data-ttu-id="d1254-108">Lo scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d1254-108">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d1254-109">Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="d1254-109">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="d1254-110">Impostare i criteri di consolidamento delle spedizioni e i filtri per i prodotti</span><span class="sxs-lookup"><span data-stu-id="d1254-110">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="d1254-111">Lo scenario qui descritto presuppone che tu abbia già attivato la funzione, eseguito gli esercizi [Configurare i criteri di consolidamento della spedizione](configure-shipment-consolidation-policies.md) e creato i criteri e altri record ivi descritti.</span><span class="sxs-lookup"><span data-stu-id="d1254-111">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="d1254-112">Assicurati di eseguire quegli esercizi prima di continuare con questo scenario.</span><span class="sxs-lookup"><span data-stu-id="d1254-112">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="d1254-113">Crea gli ordini cliente per questo scenario</span><span class="sxs-lookup"><span data-stu-id="d1254-113">Create the sales orders for this scenario</span></span>

1. <span data-ttu-id="d1254-114">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini clienti** e crea tre ordini clienti identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="d1254-114">Go to **Accounts receivable \> Orders \> All sales orders**, and create three identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="d1254-115">**Conto cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="d1254-115">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="d1254-116">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="d1254-116">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="d1254-117">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="d1254-117">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="d1254-118">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="d1254-118">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="d1254-119">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="d1254-119">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a><span data-ttu-id="d1254-120">Rilascia gli ordini cliente dalla pagina Rilascia in magazzino</span><span class="sxs-lookup"><span data-stu-id="d1254-120">Release the sales orders from the Release to warehouse page</span></span>

<span data-ttu-id="d1254-121">Segui questi passaggi per sovrascrivere i criteri di consolidamento della spedizione durante il rilascio al magazzino.</span><span class="sxs-lookup"><span data-stu-id="d1254-121">Follow these steps to override the shipment consolidation policy during the release to the warehouse.</span></span>

1. <span data-ttu-id="d1254-122">Vai a **Gestione magazzino \> Rilascia in magazzino \> Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="d1254-122">Go to **Warehouse management \> Release to warehouse \> Release to warehouse**.</span></span>
1. <span data-ttu-id="d1254-123">Nel riquadro superiore, seleziona il primo ordine cliente creato per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="d1254-123">In the upper pane, select the first sales order that you created for this scenario.</span></span>
1. <span data-ttu-id="d1254-124">Seleziona **Aggiungi** per aggiungere la riga al rilascio al magazzino.</span><span class="sxs-lookup"><span data-stu-id="d1254-124">Select **Add** to add the line to the release to the warehouse.</span></span> <span data-ttu-id="d1254-125">Tieni presente che il criterio di consolidamento della spedizione *Predefinito* viene applicato nel riquadro inferiore.</span><span class="sxs-lookup"><span data-stu-id="d1254-125">Notice that the *Default* shipment consolidation policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="d1254-126">Nel riquadro inferiore, seleziona **Seleziona nuovi criteri di consolidamento spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="d1254-126">In the bottom pane, select **Select new shipment consolidation policy**.</span></span>
1. <span data-ttu-id="d1254-127">Seleziona un criterio che consenta il consolidamento con altre spedizioni aperte dello stesso criterio.</span><span class="sxs-lookup"><span data-stu-id="d1254-127">Select a policy that allows for consolidation with other open shipments of the same policy.</span></span> <span data-ttu-id="d1254-128">Ad esempio, seleziona il criterio *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="d1254-128">For example, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="d1254-129">Seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="d1254-129">Select **Release to warehouse**.</span></span>
1. <span data-ttu-id="d1254-130">Seleziona il secondo e terzo ordine cliente creato per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="d1254-130">Select the second and third sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="d1254-131">Seleziona **Aggiungi** per aggiungere righe al rilascio al magazzino.</span><span class="sxs-lookup"><span data-stu-id="d1254-131">Select **Add** to add the lines to the release to the warehouse.</span></span> <span data-ttu-id="d1254-132">Tieni presente che il criterio *Predefinito* viene applicato nel riquadro inferiore.</span><span class="sxs-lookup"><span data-stu-id="d1254-132">Notice that the *Default* policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="d1254-133">Seleziona la seconda riga, quindi nel campo **Seleziona nuovi criteri di consolidamento spedizioni**, seleziona il criterio *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="d1254-133">Select the second line, and then, in the **Select new shipment consolidation policy** field, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="d1254-134">Seleziona **Rilascia in magazzino** per entrambe le righe.</span><span class="sxs-lookup"><span data-stu-id="d1254-134">Select **Release to warehouse** for both lines.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="d1254-135">Verifica le spedizioni</span><span class="sxs-lookup"><span data-stu-id="d1254-135">Verify the shipments</span></span>

<span data-ttu-id="d1254-136">Dovrebbero essere state create due spedizioni:</span><span class="sxs-lookup"><span data-stu-id="d1254-136">Two shipments should have been created:</span></span>

- <span data-ttu-id="d1254-137">La prima spedizione contiene due righe ed è stata creata utilizzando il criterio di consolidamento della spedizione *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="d1254-137">The first shipment contains two lines and was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>
- <span data-ttu-id="d1254-138">La seconda spedizione contiene una riga ed è stata creata utilizzando il criterio di consolidamento della spedizione *Predefinito*.</span><span class="sxs-lookup"><span data-stu-id="d1254-138">The second shipment contains one line and was created by using the *Default* shipment consolidation policy.</span></span>

<span data-ttu-id="d1254-139">Segui questi passaggi per rivedere le spedizioni che sono state create.</span><span class="sxs-lookup"><span data-stu-id="d1254-139">Follow these steps to review the shipments that were created.</span></span>

1. <span data-ttu-id="d1254-140">Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="d1254-140">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="d1254-141">Trova e seleziona la spedizione richiesta.</span><span class="sxs-lookup"><span data-stu-id="d1254-141">Find and select the required shipment.</span></span>
1. <span data-ttu-id="d1254-142">Nel campo **Criteri di consolidamento spedizioni**, rivedi il criterio di consolidamento usato al momento della creazione della spedizione.</span><span class="sxs-lookup"><span data-stu-id="d1254-142">In the **Shipment consolidation policy** field, review the consolidation policy that was used when the shipment was created.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d1254-143">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d1254-143">Additional resources</span></span>

- [<span data-ttu-id="d1254-144">Criteri consolidamento spedizione</span><span class="sxs-lookup"><span data-stu-id="d1254-144">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="d1254-145">Configurazione dei criteri di consolidamento delle spedizioni</span><span class="sxs-lookup"><span data-stu-id="d1254-145">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
