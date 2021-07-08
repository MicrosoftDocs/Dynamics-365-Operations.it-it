---
title: Gruppi di gestione degli sconti
description: In questo argomento viene descritto come impostare i gruppi di gestione degli sconti. I gruppi di gestione degli sconti possono essere utilizzati durante i calcoli degli sconti e possono essere allegati a un record di dati master.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: ee5a195b3d2881ff70fb1f0d4063ed681e874648
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271079"
---
# <a name="rebate-management-groups"></a><span data-ttu-id="6bcbc-104">Gruppi di gestione degli sconti</span><span class="sxs-lookup"><span data-stu-id="6bcbc-104">Rebate management groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6bcbc-105">I calcoli della gestione degli sconti possono essere guidati da gruppi.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-105">Rebate management calculations can be driven by groups.</span></span> <span data-ttu-id="6bcbc-106">È possibile creare gruppi di gestione degli sconti per clienti, fornitori e articoli.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-106">Rebate management groups can be created for customers, vendors, and items.</span></span> <span data-ttu-id="6bcbc-107">Possono essere allegati a un record di dati master.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-107">They can be attached to a master record.</span></span>

## <a name="rebate-management-customer-groups"></a><span data-ttu-id="6bcbc-108">Gruppi di clienti di gestione degli sconti</span><span class="sxs-lookup"><span data-stu-id="6bcbc-108">Rebate management customer groups</span></span>

<span data-ttu-id="6bcbc-109">Il calcolo per un gruppo di clienti viene spesso creato per una catena di aziende, come una catena di supermercati o una società in franchising.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-109">The calculation for a group of customers is often created for a chain of companies, such as a supermarket chain or a franchise company.</span></span> <span data-ttu-id="6bcbc-110">Questo tipo di calcolo è solitamente correlato a uno sconto.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-110">This type of calculation is usually related to a rebate.</span></span>

<span data-ttu-id="6bcbc-111">Spesso viene calcolata una detrazione senza considerare a chi è stato venduto l'ordine idoneo.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-111">A deduction is often calculated without considering who the qualifying order was sold to.</span></span> <span data-ttu-id="6bcbc-112">Tuttavia, vi sono alcune eccezioni.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-112">However, there are exceptions.</span></span> <span data-ttu-id="6bcbc-113">Ad esempio, un licenziatario potrebbe creare uno schema di detrazione in cui il gruppo di clienti A riceverà il 4% e il gruppo di clienti B riceverà solo il 3%.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-113">For example, a licensee might create a deduction scheme where customer group A will receive 4 percent, but customer group B will receive only 3 percent.</span></span>

### <a name="set-up-customer-groups"></a><span data-ttu-id="6bcbc-114">Imposta i gruppi di clienti</span><span class="sxs-lookup"><span data-stu-id="6bcbc-114">Set up customer groups</span></span>

<span data-ttu-id="6bcbc-115">Per lavorare con i gruppi di clienti per la gestione degli sconti, vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di clienti**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-115">To work with Rebate management customer groups, go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span> <span data-ttu-id="6bcbc-116">Puoi utilizzare i pulsanti nel riquadro azioni per aggiungere e rimuovere i gruppi come necessario.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-116">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="6bcbc-117">Per ciascun gruppo imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="6bcbc-117">For each group, set the following fields:</span></span>

- <span data-ttu-id="6bcbc-118">**Gruppi di gestione degli sconti** – Immetti un nome univoco per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-118">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="6bcbc-119">**Descrizione** - Immetti una descrizione del gruppo per fornire ulteriori informazioni su come dovrebbe essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-119">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-customer-group-assignments"></a><span data-ttu-id="6bcbc-120">Gestire le assegnazioni dei gruppi di clienti</span><span class="sxs-lookup"><span data-stu-id="6bcbc-120">Manage customer group assignments</span></span>

<span data-ttu-id="6bcbc-121">Ogni cliente può appartenere a un numero qualsiasi di gruppi di gestione degli sconti.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-121">Each customer can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="6bcbc-122">Per visualizzare e assegnare i membri del gruppo, puoi iniziare dall'elenco dei gruppi o dall'elenco dei clienti.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-122">To view and assign group members, you can start from either the group list or the customer list.</span></span>

<span data-ttu-id="6bcbc-123">Per visualizzare, aggiungere o rimuovere clienti per un gruppo selezionato, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-123">To view, add, or remove customers for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="6bcbc-124">Vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di clienti**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-124">Go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span>
1. <span data-ttu-id="6bcbc-125">Seleziona il gruppo da gestire.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-125">Select the group to manage.</span></span>
1. <span data-ttu-id="6bcbc-126">Nel riquadro azioni seleziona **Clienti**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-126">On the Action Pane, select **Customers**.</span></span> <span data-ttu-id="6bcbc-127">Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di clienti che sono già membri del gruppo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-127">The **Rebate management groups** page appears and shows a list of customers that are already members of the selected group.</span></span>
1. <span data-ttu-id="6bcbc-128">Per aggiungere un nuovo cliente al gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-128">To add a new customer to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="6bcbc-129">Quindi imposta il seguente campo per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="6bcbc-129">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="6bcbc-130">**Conto cliente** - Seleziona l'ID conto cliente.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-130">**Customer account** – Select the customer account ID.</span></span>

1. <span data-ttu-id="6bcbc-131">Per rimuovere un cliente dal gruppo, seleziona il cliente, quindi seleziona **Elimina** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-131">To remove a customer from the group, select the customer, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="6bcbc-132">Per visualizzare, aggiungere o rimuovere le assegnazioni di gruppo per un cliente selezionato, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-132">To view, add, or remove group assignments for a selected customer, follow these steps.</span></span>

1. <span data-ttu-id="6bcbc-133">Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-133">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="6bcbc-134">Seleziona il cliente con cui lavorare.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-134">Select the customer to work with.</span></span>
1. <span data-ttu-id="6bcbc-135">Nel riquadro azioni, nella scheda **Cliente**, nel gruppo **Gestione degli sconti** seleziona **Gruppi di gestione degli sconti**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-135">On the Action Pane, on the **Customer** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="6bcbc-136">Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di gruppi a cui il cliente già fa parte.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-136">The **Rebate management groups** page appears and shows a list of groups that the selected customer already belongs to.</span></span>
1. <span data-ttu-id="6bcbc-137">Per aggiungere il cliente a un nuovo gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-137">To add the customer to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="6bcbc-138">Quindi imposta il seguente campo per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="6bcbc-138">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="6bcbc-139">**Gruppo di gestione degli sconti** - Seleziona il gruppo a cui aggiungere il cliente.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-139">**Rebate management group** – Select the group to add the customer to.</span></span>

1. <span data-ttu-id="6bcbc-140">Per rimuovere un cliente da un gruppo, seleziona il gruppo, quindi seleziona **Elimina** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-140">To remove a customer from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="rebate-management-vendor-groups"></a><span data-ttu-id="6bcbc-141">Gruppi di fornitori di gestione degli sconti</span><span class="sxs-lookup"><span data-stu-id="6bcbc-141">Rebate management vendor groups</span></span>

<span data-ttu-id="6bcbc-142">Il calcolo per un gruppo di fornitori viene spesso creato per un gruppo di punti di consegna.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-142">The calculation for a group of vendors is often created for a group of delivery points.</span></span> <span data-ttu-id="6bcbc-143">Questo tipo di calcolo è solitamente correlato a uno sconto.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-143">This type of calculation is usually related to a rebate.</span></span>

### <a name="set-up-vendor-groups"></a><span data-ttu-id="6bcbc-144">Impostare gruppi di fornitori</span><span class="sxs-lookup"><span data-stu-id="6bcbc-144">Set up vendor groups</span></span>

<span data-ttu-id="6bcbc-145">Per lavorare con i gruppi di fornitori per la gestione degli sconti, vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di fornitori**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-145">To work with Rebate management vendor groups, go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span> <span data-ttu-id="6bcbc-146">Puoi utilizzare i pulsanti nel riquadro azioni per aggiungere e rimuovere i gruppi come necessario.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-146">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="6bcbc-147">Per ciascun gruppo imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="6bcbc-147">For each group, set the following fields:</span></span>

- <span data-ttu-id="6bcbc-148">**Gruppi di gestione degli sconti** – Immetti un nome univoco per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-148">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="6bcbc-149">**Descrizione** - Immetti una descrizione del gruppo per fornire ulteriori informazioni su come dovrebbe essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-149">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-vendor-group-assignments"></a><span data-ttu-id="6bcbc-150">Gestire le assegnazioni dei gruppi di fornitori</span><span class="sxs-lookup"><span data-stu-id="6bcbc-150">Manage vendor group assignments</span></span>

<span data-ttu-id="6bcbc-151">Ogni fornitore può appartenere a un numero qualsiasi di gruppi di gestione degli sconti.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-151">Each vendor can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="6bcbc-152">Per visualizzare e assegnare i membri del gruppo, puoi iniziare dall'elenco dei gruppi o dall'elenco dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-152">To view and assign group members, you can start from either the group list or the vendor list.</span></span>

<span data-ttu-id="6bcbc-153">Per visualizzare, aggiungere o rimuovere fornitori per un gruppo selezionato, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-153">To view, add, or remove vendors for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="6bcbc-154">Vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di fornitori**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-154">Go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span>
1. <span data-ttu-id="6bcbc-155">Seleziona il gruppo da gestire.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-155">Select the group to manage.</span></span>
1. <span data-ttu-id="6bcbc-156">Nel riquadro azioni, seleziona **Fornitori**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-156">On the Action Pane, select **Vendors**.</span></span> <span data-ttu-id="6bcbc-157">Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di fornitori che sono già membri del gruppo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-157">The **Rebate management groups** page appears and shows a list of vendors that are already members of the selected group.</span></span>
1. <span data-ttu-id="6bcbc-158">Per aggiungere un nuovo fornitore al gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-158">To add a new vendor to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="6bcbc-159">Quindi imposta il seguente campo per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="6bcbc-159">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="6bcbc-160">**Conto fornitore** - Seleziona l'ID conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-160">**Vendor account** – Select the vendor account ID.</span></span>

1. <span data-ttu-id="6bcbc-161">Per rimuovere un fornitore dal gruppo, seleziona il fornitore, quindi seleziona **Elimina** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-161">To remove a vendor from the group, select the vendor, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="6bcbc-162">Per visualizzare, aggiungere o rimuovere le assegnazioni di gruppo per un fornitore selezionato, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-162">To view, add, or remove group assignments for a selected vendor, follow these steps.</span></span>

1. <span data-ttu-id="6bcbc-163">Andare a **Contabilità fornitori \>Fornitori \> Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-163">Go to **Accounts payable \> Vendors \> All vendors**.</span></span>
1. <span data-ttu-id="6bcbc-164">Seleziona il fornitore con cui lavorare.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-164">Select the vendor to work with.</span></span>
1. <span data-ttu-id="6bcbc-165">Nel riquadro azioni, nella scheda **Fornitore**, nel gruppo **Gestione degli sconti** seleziona **Gruppi di gestione degli sconti**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-165">On the Action Pane, on the **Vendor** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="6bcbc-166">Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di gruppi a cui il fornitore già fa parte.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-166">The **Rebate management groups** page appears and shows a list of groups that the selected vendor already belongs to.</span></span>
1. <span data-ttu-id="6bcbc-167">Per aggiungere il fornitore a un nuovo gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-167">To add the vendor to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="6bcbc-168">Quindi imposta il seguente campo per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="6bcbc-168">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="6bcbc-169">**Gruppo di gestione degli sconti** - Seleziona il gruppo a cui aggiungere il fornitore.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-169">**Rebate management group** – Select the group to add the vendor to.</span></span>

1. <span data-ttu-id="6bcbc-170">Per rimuovere un fornitore da un gruppo, seleziona il gruppo, quindi seleziona **Elimina** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-170">To remove a vendor from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="item-rebate-groups"></a><span data-ttu-id="6bcbc-171">Gruppi di sconti articolo</span><span class="sxs-lookup"><span data-stu-id="6bcbc-171">Item rebate groups</span></span>

<span data-ttu-id="6bcbc-172">Raggruppando gli articoli, hai una maggiore flessibilità quando vengono calcolati sconti e detrazioni.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-172">By grouping items, you have more flexibility when rebates and deductions are calculated.</span></span> <span data-ttu-id="6bcbc-173">Questo approccio è spesso un modo più efficiente per impostare sconti e detrazioni per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-173">This approach is often a more efficient way to set up rebates and deductions for customers and vendors.</span></span>

### <a name="set-up-item-groups"></a><span data-ttu-id="6bcbc-174">Imposta i gruppi di articoli</span><span class="sxs-lookup"><span data-stu-id="6bcbc-174">Set up item groups</span></span>

<span data-ttu-id="6bcbc-175">Per lavorare con i gruppi di articoli per la gestione degli sconti, vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di articoli**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-175">To work with Rebate management item groups, go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span> <span data-ttu-id="6bcbc-176">Puoi utilizzare i pulsanti nel riquadro azioni per aggiungere e rimuovere i gruppi come necessario.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-176">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="6bcbc-177">Per ciascun gruppo imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="6bcbc-177">For each group, set the following fields:</span></span>

- <span data-ttu-id="6bcbc-178">**Gruppi di gestione degli sconti** – Immetti un nome univoco per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-178">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="6bcbc-179">**Descrizione** - Immetti una descrizione del gruppo per fornire ulteriori informazioni su come dovrebbe essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-179">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-item-group-assignments"></a><span data-ttu-id="6bcbc-180">Gestire le assegnazioni dei gruppi di articoli</span><span class="sxs-lookup"><span data-stu-id="6bcbc-180">Manage item group assignments</span></span>

<span data-ttu-id="6bcbc-181">Ogni articolo può appartenere a un numero qualsiasi di gruppi di gestione degli sconti.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-181">Each item can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="6bcbc-182">Per visualizzare e assegnare i membri del gruppo, puoi iniziare dall'elenco dei gruppi o dall'elenco degli articoli.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-182">To view and assign group members, you can start from either the group list or the item list.</span></span> <span data-ttu-id="6bcbc-183">Puoi anche aggiungere elementi in base alla tua gerarchia di categorie.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-183">You can also add items based on your category hierarchy.</span></span>

<span data-ttu-id="6bcbc-184">Per visualizzare, aggiungere o rimuovere articoli per un gruppo selezionato, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-184">To view, add, or remove items for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="6bcbc-185">Vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di articoli**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-185">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="6bcbc-186">Seleziona il gruppo da gestire.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-186">Select the group to manage.</span></span>
1. <span data-ttu-id="6bcbc-187">Nel riquadro azioni seleziona **Articoli**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-187">On the Action Pane, select **Items**.</span></span> <span data-ttu-id="6bcbc-188">Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di articoli che sono già membri del gruppo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-188">The **Rebate management groups** page appears and shows a list of items that are already members of the selected group.</span></span>
1. <span data-ttu-id="6bcbc-189">Per aggiungere un nuovo articolo al gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-189">To add a new item to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="6bcbc-190">Quindi imposta il seguente campo per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="6bcbc-190">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="6bcbc-191">**Conto articolo** - Seleziona l'ID conto articolo.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-191">**Item account** – Select the item account ID.</span></span>

1. <span data-ttu-id="6bcbc-192">Per rimuovere un articolo dal gruppo, seleziona l'articolo, quindi seleziona **Elimina** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-192">To remove an item from the group, select the item, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="6bcbc-193">Per visualizzare, aggiungere o rimuovere le assegnazioni di gruppo per un articolo selezionato, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-193">To view, add, or remove group assignments for a selected item, follow these steps.</span></span>

1. <span data-ttu-id="6bcbc-194">Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-194">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="6bcbc-195">Seleziona l'articolo con cui lavorare.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-195">Select the item to work with.</span></span>
1. <span data-ttu-id="6bcbc-196">Nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Gestione degli sconti** seleziona **Gruppi di gestione degli sconti**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-196">On the Action Pane, on the **Product** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="6bcbc-197">Viene visualizzata la pagina **Gruppi di gestione degli sconti** e mostra un elenco di gruppi a cui l'articolo già fa parte.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-197">The **Rebate management groups** page appears and shows a list of groups that the selected item already belongs to.</span></span>
1. <span data-ttu-id="6bcbc-198">Per aggiungere l'articolo a un nuovo gruppo seleziona **Nuovo** nel riquadro azioni per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-198">To add the item to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="6bcbc-199">Quindi imposta il seguente campo per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="6bcbc-199">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="6bcbc-200">**Gruppo di gestione degli sconti** - Seleziona il gruppo a cui aggiungere l'articolo.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-200">**Rebate management group** – Select the group to add the item to.</span></span>

1. <span data-ttu-id="6bcbc-201">Per rimuovere un articolo da un gruppo, seleziona il gruppo, quindi seleziona **Elimina** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-201">To remove an item from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="6bcbc-202">Per aggiungere articoli a un gruppo in base alla gerarchia delle categorie, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-202">To add items to a group based on your category hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="6bcbc-203">Vai a **Gestione degli sconti \> Impostazione gruppi di gestione degli sconti \> Gruppi di articoli**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-203">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="6bcbc-204">Seleziona il gruppo da gestire.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-204">Select the group to manage.</span></span>
1. <span data-ttu-id="6bcbc-205">Nel riquadro azioni seleziona **Aggiungi articoli**.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-205">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="6bcbc-206">Nella finestra di dialogo **Aggiungi articoli** nel campo **Gerarchia delle categorie** seleziona una categoria di primo livello.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-206">In the **Add items** dialog box, in the **Category hierarchy** field, select a top-level category.</span></span>
1. <span data-ttu-id="6bcbc-207">La gerarchia degli articoli viene aperta nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-207">The item hierarchy is opened in the left pane.</span></span> <span data-ttu-id="6bcbc-208">Seleziona il livello di gerarchia che stai cercando.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-208">Select the hierarchy level that you're looking for.</span></span> 
1. <span data-ttu-id="6bcbc-209">Gli articoli della gerarchia e del livello di gerarchia selezionati sono ora elencati nel riquadro di destra.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-209">Items from the selected hierarchy and hierarchy level are now listed in the right pane.</span></span> <span data-ttu-id="6bcbc-210">Segui questi passaggi per lavorare con il riquadro:</span><span class="sxs-lookup"><span data-stu-id="6bcbc-210">Follow these steps to work with the pane:</span></span>

    - <span data-ttu-id="6bcbc-211">Seleziona la casella di controllo per ogni articolo che vuoi aggiungere.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-211">Select the check box for each item that you want to add.</span></span>
    - <span data-ttu-id="6bcbc-212">Seleziona la casella di controllo nell'intestazione della griglia per selezionare tutti gli articoli elencati.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-212">Select the check box on the grid header to select all the items that are listed.</span></span>
    - <span data-ttu-id="6bcbc-213">Seleziona il pulsante **Mostra selezionati** per filtrare la griglia in modo che mostri solo gli articoli selezionati fino a quel momento.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-213">Select the **Show selected** button to filter the grid so that it shows only the items that you've selected so far.</span></span> <span data-ttu-id="6bcbc-214">Seleziona di nuovo il pulsante per tornare all'elenco completo.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-214">Select the button again to return to the full list.</span></span>

1. <span data-ttu-id="6bcbc-215">Seleziona **OK** per applicare la selezione dell'articolo al gruppo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6bcbc-215">Select **OK** to apply your item selection to the selected group.</span></span>
