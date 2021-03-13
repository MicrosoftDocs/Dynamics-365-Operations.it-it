---
title: Fattura per manutenzione su cespiti di proprietà del cliente
description: In questo argomento viene illustrato come creare, elaborare e fatturare il lavoro di manutenzione eseguito sui cespiti di proprietà dei clienti.
author: johanhoffmann
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 643e59f082949ed51ab61d79648a98b83a7f0b03
ms.sourcegitcommit: 1e615288db245f83c5d5e0cd45315400f8946beb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "5131843"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a><span data-ttu-id="b0852-103">Fattura per manutenzione su cespiti di proprietà del cliente</span><span class="sxs-lookup"><span data-stu-id="b0852-103">Bill for maintenance on customer-owned assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b0852-104">La funzionalità *Fatturazione ordini di lavoro* consente di creare, elaborare e fatturare il lavoro di manutenzione svolto sui cespiti di proprietà dei clienti.</span><span class="sxs-lookup"><span data-stu-id="b0852-104">The *Work order billing* feature lets you create, process, and bill maintenance work that is done on assets that your customers own.</span></span> <span data-ttu-id="b0852-105">Questa funzionalità consente di svolgere le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0852-105">This feature lets you perform the following tasks:</span></span>

- <span data-ttu-id="b0852-106">Connetti i clienti ai cespiti di loro proprietà.</span><span class="sxs-lookup"><span data-stu-id="b0852-106">Connect customers to the assets that they own.</span></span>
- <span data-ttu-id="b0852-107">Seleziona un cliente e visualizza i cespiti di cui è proprietario quando crei un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0852-107">Select a customer and view the assets that customer owns when you create a work order.</span></span>
- <span data-ttu-id="b0852-108">Configura un progetto padre per ogni cliente.</span><span class="sxs-lookup"><span data-stu-id="b0852-108">Set up a parent project for each customer.</span></span>
- <span data-ttu-id="b0852-109">Registrare ore, articoli, spese e commissioni a fronte dell'ordine di lavoro, quindi creare una proposta di fatturazione per il cliente in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="b0852-109">Register hours, items, expenses, and fees against the work order, and then create an invoice proposal for the customer later.</span></span>

<span data-ttu-id="b0852-110">Inoltre, fornisce le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="b0852-110">In addition, the feature provides the following functionality:</span></span>

- <span data-ttu-id="b0852-111">Il contratto di progetto dal progetto padre di un cliente viene automaticamente copiato nel progetto dell'ordine di lavoro pertinente.</span><span class="sxs-lookup"><span data-stu-id="b0852-111">The project contract from a customer's parent project is automatically copied to the relevant work order project.</span></span>
- <span data-ttu-id="b0852-112">La gestione dei cespiti può ora utilizzare il tipo di transazione di progetto *commissione* sia nelle previsioni degli ordini di lavoro che nei giornali di registrazione degli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0852-112">Asset management can now use the *fee* project transaction type on both work order forecasts and work order journals.</span></span>

## <a name="turn-on-the-customer-billing-feature"></a><span data-ttu-id="b0852-113">Attivare la funzionalità di fatturazione al cliente</span><span class="sxs-lookup"><span data-stu-id="b0852-113">Turn on the customer billing feature</span></span>

<span data-ttu-id="b0852-114">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="b0852-114">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="b0852-115">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla.</span><span class="sxs-lookup"><span data-stu-id="b0852-115">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="b0852-116">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b0852-116">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b0852-117">**Modulo:** *Gestione progetti e contabilità*</span><span class="sxs-lookup"><span data-stu-id="b0852-117">**Module:** *Project management and accounting*</span></span>
- <span data-ttu-id="b0852-118">**Nome funzionalità:** *Fatturazione ordini di lavoro*</span><span class="sxs-lookup"><span data-stu-id="b0852-118">**Feature name:** *Work order billing*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="b0852-119">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="b0852-119">Example scenario</span></span>

<span data-ttu-id="b0852-120">Per scoprire come funziona questa funzionalità, utilizza il seguente scenario di esempio.</span><span class="sxs-lookup"><span data-stu-id="b0852-120">To learn how this feature works, work through the following example scenario.</span></span>

<span data-ttu-id="b0852-121">Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard.</span><span class="sxs-lookup"><span data-stu-id="b0852-121">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="b0852-122">È necessario selezionare la persona giuridica **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="b0852-122">You must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="b0852-123">È inoltre possibile utilizzare questo scenario come indicazioni per l'utilizzo di questa funzionalità quando si lavora su un sistema di produzione.</span><span class="sxs-lookup"><span data-stu-id="b0852-123">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="b0852-124">Tuttavia, in questo caso, è necessario sostituire i propri valori e potrebbero mancare alcuni tipi di record richiesti forniti dai dati demo standard.</span><span class="sxs-lookup"><span data-stu-id="b0852-124">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a><span data-ttu-id="b0852-125">Passaggio 1: creare un nuovo contratto di progetto per il cliente</span><span class="sxs-lookup"><span data-stu-id="b0852-125">Step 1: Create a new project contract for the customer</span></span>

1. <span data-ttu-id="b0852-126">Passare a **Gestione progetti e contabilità \> Progetti \> Contratti di progetto**.</span><span class="sxs-lookup"><span data-stu-id="b0852-126">Go to **Project management and accounting \> Projects \> Project contracts**.</span></span>
1. <span data-ttu-id="b0852-127">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b0852-127">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b0852-128">Nella finestra di dialogo **Nuovo contratto di progetto**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b0852-128">In the **New project contract** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b0852-129">**Nome:** *Pelican Wholesales*</span><span class="sxs-lookup"><span data-stu-id="b0852-129">**Name:** *Pelican Wholesales*</span></span>
    - <span data-ttu-id="b0852-130">**Tipo di finanziamento:** *Cliente*</span><span class="sxs-lookup"><span data-stu-id="b0852-130">**Funding type:** *Customer*</span></span>
    - <span data-ttu-id="b0852-131">**Fonte di finanziamento:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="b0852-131">**Funding source:** *US-013* (*Pelican Wholesales*)</span></span>

1. <span data-ttu-id="b0852-132">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0852-132">Select **OK**.</span></span>

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a><span data-ttu-id="b0852-133">Passaggio 2: creare un nuovo progetto padre per il cliente</span><span class="sxs-lookup"><span data-stu-id="b0852-133">Step 2: Create a new parent project for the customer</span></span>

<span data-ttu-id="b0852-134">Il progetto padre creato qui verrà utilizzato quando vengono creati gli ordini di lavoro per il cliente.</span><span class="sxs-lookup"><span data-stu-id="b0852-134">The parent project that you create here will be used when work orders for the customer are created.</span></span>

1. <span data-ttu-id="b0852-135">Passare a **Gestione progetti e contabilità \> Progetti \> Tutti i progetti**.</span><span class="sxs-lookup"><span data-stu-id="b0852-135">Go to **Project management and accounting \> Projects \> All projects**.</span></span>
1. <span data-ttu-id="b0852-136">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b0852-136">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b0852-137">Nella finestra di dialogo **Nuovo progetto**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b0852-137">In the **New project** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b0852-138">**Tipo di progetto**: *Tempistica e materiali*</span><span class="sxs-lookup"><span data-stu-id="b0852-138">**Project type:** *Time and material*</span></span>
    - <span data-ttu-id="b0852-139">**Nome progetto:** *Ordini di lavoro Pelican Wholesales*</span><span class="sxs-lookup"><span data-stu-id="b0852-139">**Project name:** *Pelican Wholesales work orders*</span></span>
    - <span data-ttu-id="b0852-140">**Gruppo di progetto**: *TM*</span><span class="sxs-lookup"><span data-stu-id="b0852-140">**Project group:** *TM*</span></span>
    - <span data-ttu-id="b0852-141">**ID contratto di progetto:** *Pelican Wholesales* (il contratto che hai creato in precedenza)</span><span class="sxs-lookup"><span data-stu-id="b0852-141">**Project contract ID:** *Pelican Wholesales* (the contract that you created earlier)</span></span>
    - <span data-ttu-id="b0852-142">**Data di inizio:** selezionare la data odierna.</span><span class="sxs-lookup"><span data-stu-id="b0852-142">**Start date:** Select today's date.</span></span>

1. <span data-ttu-id="b0852-143">Selezionare **Crea progetto**.</span><span class="sxs-lookup"><span data-stu-id="b0852-143">Select **Create project**.</span></span>
1. <span data-ttu-id="b0852-144">Il nuovo progetto è aperto.</span><span class="sxs-lookup"><span data-stu-id="b0852-144">The new project is opened.</span></span> <span data-ttu-id="b0852-145">Prendi nota del valore **ID progetto**.</span><span class="sxs-lookup"><span data-stu-id="b0852-145">Make a note of the **Project ID** value.</span></span> <span data-ttu-id="b0852-146">Dovrai inserirlo più tardi.</span><span class="sxs-lookup"><span data-stu-id="b0852-146">You will have to enter it later.</span></span>

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a><span data-ttu-id="b0852-147">Passaggio 3: creare un nuovo tipo di ordine di lavoro in Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="b0852-147">Step 3: Create a new work order type in Asset management</span></span>

1. <span data-ttu-id="b0852-148">Passare a **Gestione cespiti \> Impostazione \> Ordini di lavoro \> Tipi di ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b0852-148">Go to **Asset management \> Setup \> Work order \> Work order types**.</span></span>
1. <span data-ttu-id="b0852-149">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b0852-149">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b0852-150">Un nuovo record viene aggiunto all'elenco.</span><span class="sxs-lookup"><span data-stu-id="b0852-150">A new record is added to the list.</span></span> <span data-ttu-id="b0852-151">Impostare i seguenti valori per questo record:</span><span class="sxs-lookup"><span data-stu-id="b0852-151">Set the following values for it:</span></span>

    - <span data-ttu-id="b0852-152">**Tipo ordine di lavoro:** *Servizio*</span><span class="sxs-lookup"><span data-stu-id="b0852-152">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="b0852-153">**Nome:** *Ordini di lavoro di servizio*</span><span class="sxs-lookup"><span data-stu-id="b0852-153">**Name:** *Service work orders*</span></span>
    - <span data-ttu-id="b0852-154">**Stato del ciclo di vita ordine di lavoro:** *Standard*</span><span class="sxs-lookup"><span data-stu-id="b0852-154">**Work order lifecycle state:** *Standard*</span></span>

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a><span data-ttu-id="b0852-155">Passaggio 4: collegare l'account cliente al progetto padre</span><span class="sxs-lookup"><span data-stu-id="b0852-155">Step 4: Link the customer account to the parent project</span></span>

<span data-ttu-id="b0852-156">È ora necessario collegare l'account cliente al progetto padre nella configurazione del progetto in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="b0852-156">You must now link the customer account to the parent project in the project setup in Asset management.</span></span>

1. <span data-ttu-id="b0852-157">Passare a **Gestione cespiti \> Imposta \> Ordini di lavoro \> Impostazione progetto**.</span><span class="sxs-lookup"><span data-stu-id="b0852-157">Go to **Asset management \> Setup \> Work orders \> Project setup**.</span></span>
1. <span data-ttu-id="b0852-158">Sulla scheda **Progetto padre**, seleziona e **Aggiungi** per aggiungere una riga.</span><span class="sxs-lookup"><span data-stu-id="b0852-158">On the **Parent project** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="b0852-159">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b0852-159">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b0852-160">**Account cliente:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="b0852-160">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="b0852-161">**ID progetto:** immetti l'ID progetto della spedizione di cui hai preso nota in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b0852-161">**Project ID:** Enter the project ID that you made a note of earlier.</span></span>

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a><span data-ttu-id="b0852-162">Passaggio 5: collegare il tipo e il gruppo di progetto al progetto dell'ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="b0852-162">Step 5: Link the project group and type to the work order project</span></span>

<span data-ttu-id="b0852-163">Dovresti essere ancora nella pagina **Impostazione progetto** (**Gestione cespiti \> Imposta \> Ordini di lavoro\> Impostazione progetto**).</span><span class="sxs-lookup"><span data-stu-id="b0852-163">You should still be on the **Project setup** page (**Asset management \> Setup \> Work orders \> Project setup**).</span></span>

1. <span data-ttu-id="b0852-164">Sulla scheda **Gruppo di progetto**, seleziona e **Aggiungi** per aggiungere una riga.</span><span class="sxs-lookup"><span data-stu-id="b0852-164">On the **Project group** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="b0852-165">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b0852-165">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b0852-166">**Tipo di ordine di lavoro:** *Servizio* (il tipo di ordine di lavoro che hai creato in precedenza)</span><span class="sxs-lookup"><span data-stu-id="b0852-166">**Work order type:** *Service* (the work order type that you created earlier)</span></span>
    - <span data-ttu-id="b0852-167">**Gruppo di progetto**: *TM*</span><span class="sxs-lookup"><span data-stu-id="b0852-167">**Project group:** *TM*</span></span>

> [!NOTE]
> <span data-ttu-id="b0852-168">Il contratto di progetto nel progetto dell'ordine di lavoro viene sempre ereditato dal progetto padre.</span><span class="sxs-lookup"><span data-stu-id="b0852-168">The project contract on the work order project is always inherited from the parent project.</span></span>

### <a name="step-6-link-an-asset-to-the-customer-id"></a><span data-ttu-id="b0852-169">Passaggio 6: collegare un cespite all'ID cliente</span><span class="sxs-lookup"><span data-stu-id="b0852-169">Step 6: Link an asset to the customer ID</span></span>

1. <span data-ttu-id="b0852-170">Andare a **Gestione cespiti \> Cespiti \> Cespiti attivi.**</span><span class="sxs-lookup"><span data-stu-id="b0852-170">Go to **Asset management \> Assets \> Active assets**.</span></span>
1. <span data-ttu-id="b0852-171">Nel campo **Filtro** campo, immetti *VE-102* e seleziona per filtrare per **Cespite**.</span><span class="sxs-lookup"><span data-stu-id="b0852-171">In the **Filter** field, enter *VE-102*, and select to filter by **Asset**.</span></span>
1. <span data-ttu-id="b0852-172">Seleziona la risorsa per aprire le sue impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b0852-172">Select the asset to open its settings.</span></span>
1. <span data-ttu-id="b0852-173">Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-013* (*Pelican Wholesales*).</span><span class="sxs-lookup"><span data-stu-id="b0852-173">On the **Customer** FastTab, set the **Customer account** field to *US-013* (*Pelican Wholesales*).</span></span>

    <span data-ttu-id="b0852-174">Il campo **Nome** viene aggiornato automaticamente su *Pelican Wholesales*.</span><span class="sxs-lookup"><span data-stu-id="b0852-174">The **Name** field is automatically updated to *Pelican Wholesales*.</span></span>

### <a name="step-7-create-a-new-work-order-on-the-asset"></a><span data-ttu-id="b0852-175">Passaggio 7: creare un nuovo ordine a fronte del cespite</span><span class="sxs-lookup"><span data-stu-id="b0852-175">Step 7: Create a new work order on the asset</span></span>

1. <span data-ttu-id="b0852-176">Passare a **Gestione cespiti \> Ordini di lavoro \> Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="b0852-176">Go to **Asset management \> Work orders \> Active work orders**.</span></span>
1. <span data-ttu-id="b0852-177">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b0852-177">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b0852-178">Nella finestra di dialogo **Crea ordine di lavoro**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b0852-178">In the **Create work order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b0852-179">**Tipo ordine di lavoro:** *Servizio*</span><span class="sxs-lookup"><span data-stu-id="b0852-179">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="b0852-180">**Descrizione:** *Riparazione camion*</span><span class="sxs-lookup"><span data-stu-id="b0852-180">**Description:** *Repair Truck*</span></span>
    - <span data-ttu-id="b0852-181">**Account cliente:** *US-013* (*Pelican Wholesales*)</span><span class="sxs-lookup"><span data-stu-id="b0852-181">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="b0852-182">**Cespite:** *VE-102*</span><span class="sxs-lookup"><span data-stu-id="b0852-182">**Asset:** *VE-102*</span></span>

        > [!NOTE]
        > <span data-ttu-id="b0852-183">La ricerca mostra solo le risorse collegate all'account cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="b0852-183">The lookup shows only assets that are linked to the selected customer account.</span></span>

    - <span data-ttu-id="b0852-184">**Tipo di processo di manutenzione:** *Riparazione*</span><span class="sxs-lookup"><span data-stu-id="b0852-184">**Maintenance job type:** *Repair*</span></span>
    - <span data-ttu-id="b0852-185">**Commercio:** *Meccanico*</span><span class="sxs-lookup"><span data-stu-id="b0852-185">**Trade:** *Mechanic*</span></span>
    - <span data-ttu-id="b0852-186">**Livello servizio:** *4*</span><span class="sxs-lookup"><span data-stu-id="b0852-186">**Service level:** *4*</span></span>

1. <span data-ttu-id="b0852-187">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0852-187">Select **OK**.</span></span>

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a><span data-ttu-id="b0852-188">Passaggio 8: rivedere l'ordine di lavoro e iniziare a lavorarci</span><span class="sxs-lookup"><span data-stu-id="b0852-188">Step 8: Review the work order and start to work on it</span></span>

<span data-ttu-id="b0852-189">In questa sezione lavorerai sull'ordine di lavoro che hai creato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="b0852-189">In this section, you will work on the work order that you created in the previous section.</span></span>

1. <span data-ttu-id="b0852-190">Segui questi passaggi per verificare che il progetto padre sia il progetto *Ordine di lavoro Pelican wholesales*:</span><span class="sxs-lookup"><span data-stu-id="b0852-190">Follow these steps to verify that the parent project is the *Pelican wholesales Work order* project:</span></span>

    1. <span data-ttu-id="b0852-191">Nella sezione **Processi di manutenzione dell'ordine di lavoro**, seleziona una riga.</span><span class="sxs-lookup"><span data-stu-id="b0852-191">In the **Work order maintenance jobs** section, select a line.</span></span>
    1. <span data-ttu-id="b0852-192">Nella Scheda dettagli **Dettagli riga**, ispezionare il valore **ID progetto**.</span><span class="sxs-lookup"><span data-stu-id="b0852-192">On the **Line details** FastTab, inspect the **Project ID** value.</span></span> <span data-ttu-id="b0852-193">Dovrebbe essere un numero con trattino nel modulo *\<Parent-Project-ID\>-\<Project-ID\>*.</span><span class="sxs-lookup"><span data-stu-id="b0852-193">It should be a hyphenated number in the form *\<Parent-Project-ID\>-\<Project-ID\>*.</span></span> <span data-ttu-id="b0852-194">Questo valore è un collegamento.</span><span class="sxs-lookup"><span data-stu-id="b0852-194">This value is a link.</span></span>
    1. <span data-ttu-id="b0852-195">Selezionare il collegamento ID progetto per aprire una pagina in cui è possibile visualizzare il progetto padre e i nomi del progetto.</span><span class="sxs-lookup"><span data-stu-id="b0852-195">Select the project ID link to open a page where you can view the parent project and project names.</span></span>

1. <span data-ttu-id="b0852-196">Nella scheda **Ordine di lavoro** del riquadro azioni, nel gruppo **Stato del ciclo di vita**, selezionare **Aggiorna stato ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b0852-196">On the Action Pane, on the **Work order** tab, in the **Lifecycle state** group, select **Update work order state**.</span></span>
1. <span data-ttu-id="b0852-197">Nella finestra di dialogo **Aggiorna stato ordine di lavoro**, nella colonna **Seleziona** selezionare la casella di controllo per la riga in cui il campo **Stato del ciclo di vita** è impostato su *In corso*.</span><span class="sxs-lookup"><span data-stu-id="b0852-197">In the **Update work order state** dialog box, in the **Select** column, select the check box for the row where the **Lifecycle state** field is set to *In progress*.</span></span>
1. <span data-ttu-id="b0852-198">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0852-198">Select **OK**.</span></span>
1. <span data-ttu-id="b0852-199">Nella finestra di dialogo **Stato del ciclo di vita: InProgress**, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0852-199">In the **Lifecycle state: InProgress** dialog box, select **OK**.</span></span>

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a><span data-ttu-id="b0852-200">Passaggio 9: registrare le ore impiegate per l'ordine di lavoro e creare una nuova proposta di fattura</span><span class="sxs-lookup"><span data-stu-id="b0852-200">Step 9: Post the hours that were spent on the work order and create a new invoice proposal</span></span>

<span data-ttu-id="b0852-201">In questa sezione continuerai a lavorare sull'ordine di lavoro su cui hai lavorato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="b0852-201">In this section, you will continue to work on the work order that you worked on in the previous section.</span></span>

1. <span data-ttu-id="b0852-202">Nella scheda **Ordine di lavoro** del riquadro azioni, nel gruppo **Progetto** seleziona **Giornali di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="b0852-202">On the Action Pane, on the **Work order** tab, in the **Project** group, select **Journals**.</span></span>

    <span data-ttu-id="b0852-203">Viene visualizzata la pagina **Giornali di registrazione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b0852-203">The **Work order journals** page appears.</span></span> <span data-ttu-id="b0852-204">Qui puoi registrare il tempo che hai dedicato all'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0852-204">Here, you can register the time that you spent on the work order.</span></span>

1. <span data-ttu-id="b0852-205">Nella Scheda dettaglio **Ore** selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="b0852-205">On the **Hours** FastTab, select **Add line**.</span></span>
1. <span data-ttu-id="b0852-206">Sulla nuova riga, imposta il campo **Ore** su *4*.</span><span class="sxs-lookup"><span data-stu-id="b0852-206">On the new, line, set the **Hours** field to *4*.</span></span>
1. <span data-ttu-id="b0852-207">Nel riquadro azioni selezionare **Registra giornali**.</span><span class="sxs-lookup"><span data-stu-id="b0852-207">On the Action Pane, select **Post journals**.</span></span>
1. <span data-ttu-id="b0852-208">Chiudi la pagina **Giornali di registrazione ordine di lavoro** per tornare all'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0852-208">Close the **Work order journals** page to return to the work order.</span></span>
1. <span data-ttu-id="b0852-209">Nel riquadro azioni, nella scheda **Fatturazione**, selezionare **Nuova proposta di fatturazione**.</span><span class="sxs-lookup"><span data-stu-id="b0852-209">On the Action Pane, on the **Invoicing** tab, select **New invoice proposal**.</span></span>
1. <span data-ttu-id="b0852-210">Nella finestra di dialogo **Crea proposta di fatturazione**, nella sezione **Transazioni di progetto** selezionare la casella di controllo **Seleziona** per ogni riga che si desidera fatturare.</span><span class="sxs-lookup"><span data-stu-id="b0852-210">In the **Create invoice proposal** dialog box, in the **Project transactions** section, select the **Select** check box for every line  that you want to invoice.</span></span>
1. <span data-ttu-id="b0852-211">Scegliere **OK** per chiudere la finestra di dialogo e visualizzare la nuova proposta di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="b0852-211">Select **OK** to close the dialog box and view the new invoice proposal.</span></span>
