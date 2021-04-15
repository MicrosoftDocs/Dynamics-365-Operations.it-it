---
title: Impostare un magazzino
description: Questo argomento descrive come impostare un magazzino da utilizzare con un nuovo canale in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 154ec719e16e4826b0e24deb5ecadf587d938e3c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800497"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="8f690-103">impostare un magazzino</span><span class="sxs-lookup"><span data-stu-id="8f690-103">Warehouse set up</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8f690-104">Questo argomento descrive come impostare un magazzino da utilizzare con un nuovo canale in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8f690-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8f690-105">A ogni canale di Commerce è necessario associare un magazzino configurato.</span><span class="sxs-lookup"><span data-stu-id="8f690-105">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="8f690-106">Le seguenti procedure forniscono la configurazione minima richiesta per impostare un magazzino per un canale di Commerce.</span><span class="sxs-lookup"><span data-stu-id="8f690-106">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="8f690-107">Per ulteriori informazioni sull'impostazione di un magazzino, consultare [Panoramica della gestione magazzino](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="8f690-107">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="8f690-108">Configurare un sito di magazzino</span><span class="sxs-lookup"><span data-stu-id="8f690-108">Configure a warehouse site</span></span>

<span data-ttu-id="8f690-109">Prima di impostare un magazzino, è necessario configurare un sito di magazzino.</span><span class="sxs-lookup"><span data-stu-id="8f690-109">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="8f690-110">Per configurare un sito di magazzino, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="8f690-110">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="8f690-111">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Siti**.</span><span class="sxs-lookup"><span data-stu-id="8f690-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="8f690-112">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8f690-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8f690-113">Nel campo **Sito** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="8f690-113">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="8f690-114">Nel campo **Nome** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="8f690-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="8f690-115">Nella sezione **Generale**, impostare il **Fuso orario** appropriato.</span><span class="sxs-lookup"><span data-stu-id="8f690-115">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="8f690-116">Nella sezione **Indirizzi** immettere un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="8f690-116">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="8f690-117">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f690-117">On the action pane, select **Save**.</span></span>

<span data-ttu-id="8f690-118">L'immagine seguente mostra un esempio di sito di magazzino.</span><span class="sxs-lookup"><span data-stu-id="8f690-118">The following image shows an example warehouse site.</span></span>

![Esempio di sito di magazzino](media/warehouse-site.png)

## <a name="set-up-a-warehouse&quot;></a><span data-ttu-id=&quot;8f690-120&quot;>Impostare un magazzino</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-120&quot;>Set up a warehouse</span></span>

<span data-ttu-id=&quot;8f690-121&quot;>Per impostare un magazzino, seguire questi passaggi.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-121&quot;>To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id=&quot;8f690-122&quot;>Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Magazzini**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-122&quot;>In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id=&quot;8f690-123&quot;>Nel Riquadro azioni selezionare **Nuovo**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-123&quot;>On the action pane, select **New**.</span></span>
1. <span data-ttu-id=&quot;8f690-124&quot;>Nel campo **Magazzino** immettere un valore.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-124&quot;>In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id=&quot;8f690-125&quot;>Se si tratta di una mappatura 1:1 a un punto vendita, considerare l'utilizzo di un nome di punto vendita o di un nome di centro di distribuzione regionale.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-125&quot;>If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id=&quot;8f690-126&quot;>Nel campo **Nome** immettere un valore.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-126&quot;>In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id=&quot;8f690-127&quot;>Nell'elenco a discesa **Sito**, selezionare il sito di magazzino creato in precedenza.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-127&quot;>In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id=&quot;8f690-128&quot;>Nel campo **Tipo** selezionare **Predefinito**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-128&quot;>In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id=&quot;8f690-129&quot;>Se si desidera impostare un **Magazzino di quarantena**, è necessario dapprima seguire questi passaggi per creare un magazzino aggiuntivo dove **Tipo** è impostato su **Quarantena**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-129&quot;>If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id=&quot;8f690-130&quot;>Se si desidera impostare un **Magazzino di transito**, è necessario dapprima seguire questi passaggi per creare un magazzino aggiuntivo dove **Tipo** è impostato su **Transito**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-130&quot;>If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id=&quot;8f690-131&quot;>Nel riquadro azioni selezionare **Salva**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-131&quot;>On the action pane, select **Save**.</span></span>

## <a name=&quot;set-up-inventory-aisles&quot;></a><span data-ttu-id=&quot;8f690-132&quot;>Impostare le sezioni di magazzino</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-132&quot;>Set up inventory aisles</span></span>

<span data-ttu-id=&quot;8f690-133&quot;>Per impostare le sezioni di magazzino, effettuare le seguenti operazioni.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-133&quot;>To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id=&quot;8f690-134&quot;>Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Impostazione ubicazione \> Sezioni magazzino**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-134&quot;>In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id=&quot;8f690-135&quot;>Nel Riquadro azioni selezionare **Nuovo**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-135&quot;>On the action pane, select **New**.</span></span>
1. <span data-ttu-id=&quot;8f690-136&quot;>Nell'elenco a discesa **Magazzino**, selezionare il magazzino creato in precedenza.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8f690-136&quot;>In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id=&quot;8f690-137&quot;>Nel campo **Sezione**, immettere un nome (ad esempio &quot;Predef").</span><span class="sxs-lookup"><span data-stu-id="8f690-137">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="8f690-138">Nel campo **Nome**, immettere un nome (ad esempio "Sezione predefinita").</span><span class="sxs-lookup"><span data-stu-id="8f690-138">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="8f690-139">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f690-139">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="8f690-140">Impostare le ubicazioni delle scorte magazzino</span><span class="sxs-lookup"><span data-stu-id="8f690-140">Set up warehouse inventory locations</span></span>

<span data-ttu-id="8f690-141">Per impostare le ubicazioni delle scorte magazzino per scorte standard, danneggiate e restituite, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="8f690-141">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="8f690-142">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="8f690-142">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="8f690-143">Selezionare il magazzino creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8f690-143">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="8f690-144">Nel riquadro azioni selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8f690-144">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="8f690-145">Nel riquadro azioni, selezionare **Magazzino**, quindi selezionare **Ubicazione di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="8f690-145">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="8f690-146">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8f690-146">On the action pane, select **New**.</span></span> <span data-ttu-id="8f690-147">Per impostazione predefinita, nell'elenco a discesa **Magazzino** dovrebbe essere visualizzato il nuovo magazzino.</span><span class="sxs-lookup"><span data-stu-id="8f690-147">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="8f690-148">Nella casella **Sezione**, immettere il nome della sezione specificata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8f690-148">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="8f690-149">Impostare **Aggiornamento manuale** su **Sì**</span><span class="sxs-lookup"><span data-stu-id="8f690-149">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="8f690-150">Nella casella **Ubicazione**, immettere il nome del magazzino.</span><span class="sxs-lookup"><span data-stu-id="8f690-150">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="8f690-151">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f690-151">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="8f690-152">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8f690-152">On the action pane, select **New**.</span></span>  <span data-ttu-id="8f690-153">Per impostazione predefinita, nell'elenco a discesa **Magazzino** dovrebbe essere visualizzato il nuovo magazzino.</span><span class="sxs-lookup"><span data-stu-id="8f690-153">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="8f690-154">Nella casella **Sezione**, immettere il nome della sezione specificata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8f690-154">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="8f690-155">Impostare **Aggiornamento manuale** su **Sì**</span><span class="sxs-lookup"><span data-stu-id="8f690-155">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="8f690-156">Nella casella **Ubicazione**, immettere "Danneggiato".</span><span class="sxs-lookup"><span data-stu-id="8f690-156">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="8f690-157">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f690-157">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="8f690-158">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8f690-158">On the action pane, select **New**.</span></span>  <span data-ttu-id="8f690-159">Per impostazione predefinita, nell'elenco a discesa **Magazzino** dovrebbe essere visualizzato il nuovo magazzino.</span><span class="sxs-lookup"><span data-stu-id="8f690-159">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="8f690-160">Nella casella **Sezione**, immettere il nome della sezione specificata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8f690-160">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="8f690-161">Impostare **Aggiornamento manuale** su **Sì**</span><span class="sxs-lookup"><span data-stu-id="8f690-161">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="8f690-162">Nella casella **Ubicazione**, immettere "Resi".</span><span class="sxs-lookup"><span data-stu-id="8f690-162">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="8f690-163">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f690-163">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="8f690-164">L'immagine seguente mostra l'impostazione dell'ubicazione delle scorte magazzino a San Francisco.</span><span class="sxs-lookup"><span data-stu-id="8f690-164">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Esempio di impostazione dell'ubicazione delle scorte](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="8f690-166">Completare l'impostazione del magazzino</span><span class="sxs-lookup"><span data-stu-id="8f690-166">Complete warehouse setup</span></span>

<span data-ttu-id="8f690-167">Per completare l'impostazione del magazzino, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="8f690-167">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="8f690-168">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="8f690-168">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="8f690-169">Selezionare il magazzino creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8f690-169">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="8f690-170">Nel riquadro azioni selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8f690-170">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="8f690-171">Sotto **Gestione articoli e magazzino**:</span><span class="sxs-lookup"><span data-stu-id="8f690-171">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="8f690-172">Impostare **Ubicazione predefinita entrata** sull'ubicazione predefinita creata sopra.</span><span class="sxs-lookup"><span data-stu-id="8f690-172">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="8f690-173">Selezionare **Ubicazione predefinita uscita** sull'ubicazione predefinita creata sopra.</span><span class="sxs-lookup"><span data-stu-id="8f690-173">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="8f690-174">Sotto la sezione **Indirizzi**, immettere un indirizzo di magazzino.</span><span class="sxs-lookup"><span data-stu-id="8f690-174">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="8f690-175">Sotto la sezione **Al dettaglio**:</span><span class="sxs-lookup"><span data-stu-id="8f690-175">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="8f690-176">Nella casella **Ubicazione reso predefinita**, immettere l'ubicazione dei resi creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8f690-176">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="8f690-177">Impostare **Punto vendita** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8f690-177">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="8f690-178">Impostare **Peso** su **1,00**.</span><span class="sxs-lookup"><span data-stu-id="8f690-178">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="8f690-179">Nella casella **Dimensioni di immagazzinamento**, immettere l'ubicazione predefinita creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8f690-179">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="8f690-180">Sotto la sezione **Magazzino**, impostare **Scorte fisiche negative** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8f690-180">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="8f690-181">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f690-181">On the action pane, select **Save**.</span></span>

<span data-ttu-id="8f690-182">L'immagine seguente mostra i dettagli di un magazzino configurato.</span><span class="sxs-lookup"><span data-stu-id="8f690-182">The following image shows details for a configured warehouse.</span></span>

![Esempio di magazzino configurato](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="8f690-184">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8f690-184">Additional resources</span></span>

[<span data-ttu-id="8f690-185">Panoramica gestione del magazzino</span><span class="sxs-lookup"><span data-stu-id="8f690-185">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="8f690-186">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="8f690-186">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="8f690-187">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="8f690-187">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="8f690-188">Impostare un canale di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="8f690-188">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="8f690-189">Impostare un canale online</span><span class="sxs-lookup"><span data-stu-id="8f690-189">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="8f690-190">Impostare un canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="8f690-190">Set up a call center channel</span></span>](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
