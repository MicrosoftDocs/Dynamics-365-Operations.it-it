---
title: Impostare un magazzino
description: Questo argomento descrive come impostare un magazzino da utilizzare con un nuovo canale in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9ba12876a8c8f841733d8ec49c33e900211c4ab4
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057858"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="46f61-103">impostare un magazzino</span><span class="sxs-lookup"><span data-stu-id="46f61-103">Warehouse set up</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="46f61-104">Questo argomento descrive come impostare un magazzino da utilizzare con un nuovo canale in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="46f61-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="46f61-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="46f61-105">Overview</span></span>

<span data-ttu-id="46f61-106">A ogni canale di Commerce è necessario associare un magazzino configurato.</span><span class="sxs-lookup"><span data-stu-id="46f61-106">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="46f61-107">Le seguenti procedure forniscono la configurazione minima richiesta per impostare un magazzino per un canale di Commerce.</span><span class="sxs-lookup"><span data-stu-id="46f61-107">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="46f61-108">Per ulteriori informazioni sull'impostazione di un magazzino, consultare [Panoramica della gestione magazzino](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview).</span><span class="sxs-lookup"><span data-stu-id="46f61-108">For more information regarding warehouse setup, please see the [Warehouse management overview](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="46f61-109">Configurare un sito di magazzino</span><span class="sxs-lookup"><span data-stu-id="46f61-109">Configure a warehouse site</span></span>

<span data-ttu-id="46f61-110">Prima di impostare un magazzino, è necessario configurare un sito di magazzino.</span><span class="sxs-lookup"><span data-stu-id="46f61-110">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="46f61-111">Per configurare un sito di magazzino, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="46f61-111">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="46f61-112">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Siti**.</span><span class="sxs-lookup"><span data-stu-id="46f61-112">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="46f61-113">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="46f61-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="46f61-114">Nel campo **Sito** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="46f61-114">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="46f61-115">Nel campo **Nome** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="46f61-115">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="46f61-116">Nella sezione **Generale**, impostare il **Fuso orario** appropriato.</span><span class="sxs-lookup"><span data-stu-id="46f61-116">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="46f61-117">Nella sezione **Indirizzi** immettere un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="46f61-117">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="46f61-118">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="46f61-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="46f61-119">L'immagine seguente mostra un esempio di sito di magazzino.</span><span class="sxs-lookup"><span data-stu-id="46f61-119">The following image shows an example warehouse site.</span></span>

![Esempio di sito di magazzino](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="46f61-121">Impostare un magazzino</span><span class="sxs-lookup"><span data-stu-id="46f61-121">Set up a warehouse</span></span>

<span data-ttu-id="46f61-122">Per impostare un magazzino, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="46f61-122">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="46f61-123">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="46f61-123">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="46f61-124">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="46f61-124">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="46f61-125">Nel campo **Magazzino** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="46f61-125">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="46f61-126">Se si tratta di una mappatura 1:1 a un punto vendita, considerare l'utilizzo di un nome di punto vendita o di un nome di centro di distribuzione regionale.</span><span class="sxs-lookup"><span data-stu-id="46f61-126">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="46f61-127">Nel campo **Nome** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="46f61-127">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="46f61-128">Nell'elenco a discesa **Sito**, selezionare il sito di magazzino creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46f61-128">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="46f61-129">Nel campo **Tipo** selezionare **Predefinito**.</span><span class="sxs-lookup"><span data-stu-id="46f61-129">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="46f61-130">Se si desidera impostare un **Magazzino di quarantena**, è necessario dapprima seguire questi passaggi per creare un magazzino aggiuntivo dove **Tipo** è impostato su **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="46f61-130">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="46f61-131">Se si desidera impostare un **Magazzino di transito**, è necessario dapprima seguire questi passaggi per creare un magazzino aggiuntivo dove **Tipo** è impostato su **Transito**.</span><span class="sxs-lookup"><span data-stu-id="46f61-131">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="46f61-132">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="46f61-132">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="46f61-133">Impostare le sezioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="46f61-133">Set up inventory aisles</span></span>

<span data-ttu-id="46f61-134">Per impostare le sezioni di magazzino, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="46f61-134">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="46f61-135">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Impostazione ubicazione \> Sezioni magazzino**.</span><span class="sxs-lookup"><span data-stu-id="46f61-135">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="46f61-136">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="46f61-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="46f61-137">Nell'elenco a discesa **Magazzino**, selezionare il magazzino creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46f61-137">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="46f61-138">Nel campo **Sezione**, immettere un nome (ad esempio "Predef").</span><span class="sxs-lookup"><span data-stu-id="46f61-138">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="46f61-139">Nel campo **Nome**, immettere un nome (ad esempio "Sezione predefinita").</span><span class="sxs-lookup"><span data-stu-id="46f61-139">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="46f61-140">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="46f61-140">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="46f61-141">Impostare le ubicazioni delle scorte magazzino</span><span class="sxs-lookup"><span data-stu-id="46f61-141">Set up warehouse inventory locations</span></span>

<span data-ttu-id="46f61-142">Per impostare le ubicazioni delle scorte magazzino per scorte standard, danneggiate e restituite, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="46f61-142">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="46f61-143">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="46f61-143">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="46f61-144">Selezionare il magazzino creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46f61-144">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="46f61-145">Nel riquadro azioni selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="46f61-145">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="46f61-146">Nel riquadro azioni, selezionare **Magazzino**, quindi selezionare **Ubicazione di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="46f61-146">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="46f61-147">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="46f61-147">On the action pane, select **New**.</span></span> <span data-ttu-id="46f61-148">Per impostazione predefinita, nell'elenco a discesa **Magazzino** dovrebbe essere visualizzato il nuovo magazzino.</span><span class="sxs-lookup"><span data-stu-id="46f61-148">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="46f61-149">Nella casella **Sezione**, immettere il nome della sezione specificata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46f61-149">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="46f61-150">Impostare **Aggiornamento manuale** su **Sì**</span><span class="sxs-lookup"><span data-stu-id="46f61-150">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="46f61-151">Nella casella **Ubicazione**, immettere il nome del magazzino.</span><span class="sxs-lookup"><span data-stu-id="46f61-151">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="46f61-152">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="46f61-152">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="46f61-153">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="46f61-153">On the action pane, select **New**.</span></span>  <span data-ttu-id="46f61-154">Per impostazione predefinita, nell'elenco a discesa **Magazzino** dovrebbe essere visualizzato il nuovo magazzino.</span><span class="sxs-lookup"><span data-stu-id="46f61-154">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="46f61-155">Nella casella **Sezione**, immettere il nome della sezione specificata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46f61-155">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="46f61-156">Impostare **Aggiornamento manuale** su **Sì**</span><span class="sxs-lookup"><span data-stu-id="46f61-156">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="46f61-157">Nella casella **Ubicazione**, immettere "Danneggiato".</span><span class="sxs-lookup"><span data-stu-id="46f61-157">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="46f61-158">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="46f61-158">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="46f61-159">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="46f61-159">On the action pane, select **New**.</span></span>  <span data-ttu-id="46f61-160">Per impostazione predefinita, nell'elenco a discesa **Magazzino** dovrebbe essere visualizzato il nuovo magazzino.</span><span class="sxs-lookup"><span data-stu-id="46f61-160">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="46f61-161">Nella casella **Sezione**, immettere il nome della sezione specificata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46f61-161">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="46f61-162">Impostare **Aggiornamento manuale** su **Sì**</span><span class="sxs-lookup"><span data-stu-id="46f61-162">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="46f61-163">Nella casella **Ubicazione**, immettere "Resi".</span><span class="sxs-lookup"><span data-stu-id="46f61-163">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="46f61-164">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="46f61-164">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="46f61-165">L'immagine seguente mostra l'impostazione dell'ubicazione delle scorte magazzino a San Francisco.</span><span class="sxs-lookup"><span data-stu-id="46f61-165">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Esempio di impostazione dell'ubicazione delle scorte](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="46f61-167">Completare l'impostazione del magazzino</span><span class="sxs-lookup"><span data-stu-id="46f61-167">Complete warehouse setup</span></span>

<span data-ttu-id="46f61-168">Per completare l'impostazione del magazzino, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="46f61-168">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="46f61-169">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="46f61-169">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="46f61-170">Selezionare il magazzino creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46f61-170">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="46f61-171">Nel riquadro azioni selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="46f61-171">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="46f61-172">Sotto **Gestione articoli e magazzino**:</span><span class="sxs-lookup"><span data-stu-id="46f61-172">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="46f61-173">Impostare **Ubicazione predefinita entrata** sull'ubicazione predefinita creata sopra.</span><span class="sxs-lookup"><span data-stu-id="46f61-173">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="46f61-174">Selezionare **Ubicazione predefinita uscita** sull'ubicazione predefinita creata sopra.</span><span class="sxs-lookup"><span data-stu-id="46f61-174">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="46f61-175">Sotto la sezione **Indirizzi**, immettere un indirizzo di magazzino.</span><span class="sxs-lookup"><span data-stu-id="46f61-175">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="46f61-176">Sotto la sezione **Al dettaglio**:</span><span class="sxs-lookup"><span data-stu-id="46f61-176">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="46f61-177">Nella casella **Ubicazione reso predefinita**, immettere l'ubicazione dei resi creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46f61-177">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="46f61-178">Impostare **Punto vendita** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="46f61-178">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="46f61-179">Impostare **Peso** su **1,00**.</span><span class="sxs-lookup"><span data-stu-id="46f61-179">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="46f61-180">Nella casella **Dimensioni di immagazzinamento**, immettere l'ubicazione predefinita creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46f61-180">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="46f61-181">Sotto la sezione **Magazzino**, impostare **Scorte fisiche negative** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="46f61-181">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="46f61-182">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="46f61-182">On the action pane, select **Save**.</span></span>

<span data-ttu-id="46f61-183">L'immagine seguente mostra i dettagli di un magazzino configurato.</span><span class="sxs-lookup"><span data-stu-id="46f61-183">The following image shows details for a configured warehouse.</span></span>

![Esempio di magazzino configurato](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="46f61-185">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="46f61-185">Additional resources</span></span>

[<span data-ttu-id="46f61-186">Panoramica gestione del magazzino</span><span class="sxs-lookup"><span data-stu-id="46f61-186">Warehouse management overview</span></span>](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview)

[<span data-ttu-id="46f61-187">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="46f61-187">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="46f61-188">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="46f61-188">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="46f61-189">Impostare un canale di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="46f61-189">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="46f61-190">Impostare un canale online</span><span class="sxs-lookup"><span data-stu-id="46f61-190">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="46f61-191">Impostare un canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="46f61-191">Set up a call center channel</span></span>](channel-setup-callcenter.md)





