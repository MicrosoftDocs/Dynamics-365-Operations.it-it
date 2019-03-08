---
title: Codici motivo conteggio scorte
description: In questo argomento viene descritto come impostare e applicare i codici motivo ai fini delle attività di conteggio
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2f4332432ad73861cd9b6b6452685d3175ace56b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "320836"
---
# <a name="reason-codes-for-inventory-counting"></a><span data-ttu-id="662e0-103">Codici motivo conteggio scorte</span><span class="sxs-lookup"><span data-stu-id="662e0-103">Reason codes for inventory counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="662e0-104">I codici motivo consentono di analizzare i risultati di un processo di conteggio e le eventuali discrepanze che si verificano durante tale processo.</span><span class="sxs-lookup"><span data-stu-id="662e0-104">Reason codes let you analyze the results of a counting process and any discrepancies that occur during that process.</span></span> <span data-ttu-id="662e0-105">È possibile specificare il motivo del conteggio, ad esempio un pallet rotto o una correzione dello scorte basata su campioni di inventario.</span><span class="sxs-lookup"><span data-stu-id="662e0-105">You can specify the reason for doing the count, such as a broken pallet or a stock adjustment that is based on inventory samples.</span></span>

## <a name="recommendation"></a><span data-ttu-id="662e0-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="662e0-106">Recommendation</span></span>

<span data-ttu-id="662e0-107">Prima di impostare il sistema, si consiglia di definire una strategia per la gestione dei codici motivo.</span><span class="sxs-lookup"><span data-stu-id="662e0-107">Before you set up the system, we recommend that you define a strategy for working with reason codes.</span></span> <span data-ttu-id="662e0-108">Ad esempio, provare a rispondere alle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="662e0-108">For example, try to answer the following questions:</span></span>

- <span data-ttu-id="662e0-109">I codici motivo devono essere obbligatori nei magazzini?</span><span class="sxs-lookup"><span data-stu-id="662e0-109">Should reason codes be mandatory on warehouses?</span></span>
- <span data-ttu-id="662e0-110">I codici motivo devono essere obbligatori o facoltativi per alcuni articoli?</span><span class="sxs-lookup"><span data-stu-id="662e0-110">Should reason codes be mandatory or optional on some items?</span></span>
- <span data-ttu-id="662e0-111">Quanti codici motivo sono necessari?</span><span class="sxs-lookup"><span data-stu-id="662e0-111">How many reason codes do you require?</span></span>
- <span data-ttu-id="662e0-112">In che modo dei lettori di codici a barre devono utilizzare codici motivo?</span><span class="sxs-lookup"><span data-stu-id="662e0-112">How should users of barcode scanners use reason codes?</span></span> <span data-ttu-id="662e0-113">I codici motivo devono essere preselezionati, obbligatori o non modificabili?</span><span class="sxs-lookup"><span data-stu-id="662e0-113">Should the reason codes be preselected, mandatory, or not editable?</span></span>
- <span data-ttu-id="662e0-114">I lavoratori di magazzino richiedono un diverso comportamento del codice motivo sui lettori mobili?</span><span class="sxs-lookup"><span data-stu-id="662e0-114">Do warehouse workers require different reason code behavior on mobile scanners?</span></span> <span data-ttu-id="662e0-115">Se la risposta è sì, puoi creare più voci di menu e assegnarle a persone diverse.</span><span class="sxs-lookup"><span data-stu-id="662e0-115">If the answer is yes, you can create more menu items and assign them to different people.</span></span>

## <a name="where-reason-codes-apply"></a><span data-ttu-id="662e0-116">Dove si applicano i codici motivo</span><span class="sxs-lookup"><span data-stu-id="662e0-116">Where reason codes apply</span></span>

<span data-ttu-id="662e0-117">È possibile creare più criteri di codici motivo e ogni criterio di codice motivo può avere due criteri di codice motivo di conteggio.</span><span class="sxs-lookup"><span data-stu-id="662e0-117">You can create multiple reason code policies, and each reason code policy can have two counting reason code policies.</span></span> <span data-ttu-id="662e0-118">I criteri di conteggio di codici motivo possono essere utilizzati nel magazzino o a livello dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="662e0-118">The counting reason code policies can be used at the warehouse level or the item level.</span></span>

## <a name="set-up-reason-code-policies"></a><span data-ttu-id="662e0-119">Impostare i criteri di codici motivo</span><span class="sxs-lookup"><span data-stu-id="662e0-119">Set up reason code policies</span></span>

1. <span data-ttu-id="662e0-120">Selezionare **Gestione inventario** \> **Impostazione** \> **Magazzino** \> **Criteri codice motivo conteggio** e creare nuovi criteri del codice motivo.</span><span class="sxs-lookup"><span data-stu-id="662e0-120">Select **Inventory management** \> **Setup** \> **Inventory** \> **Counting reason code policies**, and create a new reason code policy.</span></span>
2. <span data-ttu-id="662e0-121">Nel campo **Tipo di codice motivo conteggio** selezionare **Obbligatorio** o **Facoltativo** per specificare se la selezione di un codice motivo deve essere un'azione facoltativa o obbligatoria in uno dei seguenti giornali di registrazione di conteggio:</span><span class="sxs-lookup"><span data-stu-id="662e0-121">In the **Counting reason code type** field, select either **Mandatory** or **Optional** to specify whether selection of a reason code should be an optional or mandatory action in one of the following counting journals:</span></span>

    - <span data-ttu-id="662e0-122">Conteggio ciclo (dispositivo mobile)</span><span class="sxs-lookup"><span data-stu-id="662e0-122">Cycle Count (mobile device)</span></span>
    - <span data-ttu-id="662e0-123">Conteggio ciclo a campione (dispositivo mobile)</span><span class="sxs-lookup"><span data-stu-id="662e0-123">Spot Count (mobile device)</span></span>
    - <span data-ttu-id="662e0-124">Conteggio soglia (dispositivo mobile)</span><span class="sxs-lookup"><span data-stu-id="662e0-124">Threshold Count (mobile device)</span></span>
    - <span data-ttu-id="662e0-125">Rettifica in entrata (dispositivo mobile)</span><span class="sxs-lookup"><span data-stu-id="662e0-125">Adjustment In (mobile device)</span></span>
    - <span data-ttu-id="662e0-126">Rettifica in uscita (dispositivo mobile)</span><span class="sxs-lookup"><span data-stu-id="662e0-126">Adjustment Out (mobile device)</span></span>
    - <span data-ttu-id="662e0-127">Giornale di registrazione di conteggio (rich client)</span><span class="sxs-lookup"><span data-stu-id="662e0-127">Counting Journal (rich client)</span></span>

<span data-ttu-id="662e0-128">È inoltre possibile impostare codici motivo per singoli magazzini e prodotti.</span><span class="sxs-lookup"><span data-stu-id="662e0-128">You can also set up reason codes for individual warehouses and for products.</span></span> <span data-ttu-id="662e0-129">L'impostazione di codici motivo per i prodotti può ignorare le impostazioni per i magazzini.</span><span class="sxs-lookup"><span data-stu-id="662e0-129">The reason code setup for products can disregard the setup for warehouses.</span></span>

## <a name="mandatory-reason-codes"></a><span data-ttu-id="662e0-130">Codici motivo obbligatori</span><span class="sxs-lookup"><span data-stu-id="662e0-130">Mandatory reason codes</span></span>

<span data-ttu-id="662e0-131">Se il parametro **Obbligatorio** è impostato nella configurazione dei codici motivo per magazzini o articoli, il giornale di registrazione di conteggio non può essere completato e chiuso finché non viene fornito un codice motivo.</span><span class="sxs-lookup"><span data-stu-id="662e0-131">If the **Mandatory** parameter is set in the configuration of reason codes for warehouses or items, the counting journal can't be completed and closed until a reason code is provided.</span></span>

### <a name="set-up-reason-codes-for-warehouses"></a><span data-ttu-id="662e0-132">Imposta codici motivo per i magazzini</span><span class="sxs-lookup"><span data-stu-id="662e0-132">Set up reason codes for warehouses</span></span>

1. <span data-ttu-id="662e0-133">Selezionare **Gestione articoli** \> **Impostazioni** \> **Suddivisione scorte** \> **Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="662e0-133">Select **Inventory Management** \> **Setup** \> **Inventory breakdown** \> **Warehouses**.</span></span>
2. <span data-ttu-id="662e0-134">Nella scheda **Magazzino**, nel campo **Criteri codice motivo conteggio** selezionare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="662e0-134">On the **Warehouse** tab, in the **Counting reason code policy** field, select one of the following options:</span></span>

    - <span data-ttu-id="662e0-135">**Vuoto**: il parametro impostato per l'articolo viene utilizzato per determinare se i giornali di registrazione di conteggio sono obbligatori per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="662e0-135">**Blank** – The parameter that is set up for the item is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="662e0-136">**Obbligatorio**: il codice motivo è sempre obbligatorio per i giornali di registrazione di conteggio per il magazzino.</span><span class="sxs-lookup"><span data-stu-id="662e0-136">**Mandatory** – A reason code is always required on counting journals for the warehouse.</span></span>
    - <span data-ttu-id="662e0-137">**Facoltativo**: il codice motivo non è obbligatorio per i giornali di registrazione di conteggio per il magazzino.</span><span class="sxs-lookup"><span data-stu-id="662e0-137">**Optional** – A reason code isn't required on counting journals for the warehouse.</span></span>

### <a name="set-up-reason-codes-for-products"></a><span data-ttu-id="662e0-138">Imposta codici motivo per i prodotti</span><span class="sxs-lookup"><span data-stu-id="662e0-138">Set up reason codes for products</span></span>

1. <span data-ttu-id="662e0-139">Selezionare **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="662e0-139">Select **Product information management** \> **Products** \> **Released products**.</span></span>
2. <span data-ttu-id="662e0-140">Nella scheda **Prodotto** selezionare **Criteri codice motivo conteggio** e quindi una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="662e0-140">On the **Product** tab, select **Counting reason code policy**, and then select one of the following options:</span></span>

    - <span data-ttu-id="662e0-141">**Vuoto**: il parametro impostato per il magazzino viene utilizzato per determinare se i giornali di registrazione di conteggio sono obbligatori per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="662e0-141">**Blank** – The parameter that is set up for the warehouse is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="662e0-142">**Obbligatorio**: il codice motivo è sempre obbligatorio per i giornali di registrazione di conteggio per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="662e0-142">**Mandatory** – A reason code is always required on counting journals for the product.</span></span> <span data-ttu-id="662e0-143">Questa impostazione ha la priorità su qualsiasi impostazione di codici motivo a livello di magazzino.</span><span class="sxs-lookup"><span data-stu-id="662e0-143">This setting overrides any reason code setting at the warehouse level.</span></span>
    - <span data-ttu-id="662e0-144">**Facoltativo**: il codice motivo non è obbligatorio per i giornali di registrazione di conteggio per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="662e0-144">**Optional** – A reason code isn't required on counting journals for the product.</span></span> <span data-ttu-id="662e0-145">Questa impostazione ha la priorità su qualsiasi impostazione di codici motivo a livello di magazzino.</span><span class="sxs-lookup"><span data-stu-id="662e0-145">This setting overrides any reason code setting at the warehouse level.</span></span>

### <a name="use-reason-codes-in-counting-journals"></a><span data-ttu-id="662e0-146">Utilizzare i codici motivo nei giornali di registrazione di conteggio</span><span class="sxs-lookup"><span data-stu-id="662e0-146">Use reason codes in counting journals</span></span>

<span data-ttu-id="662e0-147">In un giornale di registrazione, è possibile aggiungere i codici motivo per i conteggi dei seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="662e0-147">In a counting journal, you can add reason codes for counts of the following types:</span></span>

- <span data-ttu-id="662e0-148">Conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="662e0-148">Cycle Count</span></span>
- <span data-ttu-id="662e0-149">Conteggio ciclo a campione</span><span class="sxs-lookup"><span data-stu-id="662e0-149">Spot Count</span></span>
- <span data-ttu-id="662e0-150">Conteggio soglia</span><span class="sxs-lookup"><span data-stu-id="662e0-150">Threshold Count</span></span>
- <span data-ttu-id="662e0-151">Rettifica in entrata</span><span class="sxs-lookup"><span data-stu-id="662e0-151">Adjustment In</span></span>
- <span data-ttu-id="662e0-152">Rettifica in uscita</span><span class="sxs-lookup"><span data-stu-id="662e0-152">Adjustment Out</span></span>

<span data-ttu-id="662e0-153">I codici motivo vengono aggiunti alle righe del giornale di registrazione nei i giornali di registrazione di conteggio di tipo **Giornale di registrazione di conteggio**.</span><span class="sxs-lookup"><span data-stu-id="662e0-153">Reason codes are added to the journal lines in counting journals of the **Counting journal** type.</span></span>

1. <span data-ttu-id="662e0-154">Selezionare **Gestione inventario** \> **Inserimenti nel giornale di registrazione** \> **Conteggio articoli** \> **Conteggio**.</span><span class="sxs-lookup"><span data-stu-id="662e0-154">Select **Inventory management** \> **Journal entries** \> **Item counting** \> **Counting**.</span></span>
2. <span data-ttu-id="662e0-155">In dettaglio i dettagli riga del giornale di registrazione di conteggio, nel campo **Codice motivo conteggio** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="662e0-155">In the line details of the counting journal, in the **Counting reason code** field, select an option.</span></span>

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a><span data-ttu-id="662e0-156">Visualizzare la cronologia del conteggio così come è registrata dai codici motivo</span><span class="sxs-lookup"><span data-stu-id="662e0-156">View the counting history as it's recorded by reason codes</span></span>

- <span data-ttu-id="662e0-157">Selezionare **Gestione inventario** \> **Richieste di informazioni e report** \> **Storico conteggio**, quindi nel campo **Codice motivo conteggio**, visualizzare lo storico di conteggio registrato tramite un codice motivo.</span><span class="sxs-lookup"><span data-stu-id="662e0-157">Select **Inventory management** \> **Inquiries and reports** \> **Counting history**, and then, in the **Counting reason code** field, view the counting history that has been recorded through a reason code.</span></span>

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a><span data-ttu-id="662e0-158">Utilizzare un codice motivo per rettifica della quantità</span><span class="sxs-lookup"><span data-stu-id="662e0-158">Use a reason code for a quantity adjustment</span></span>

1. <span data-ttu-id="662e0-159">Nella pagina **Scorte disponibili**, selezionare **Rettifica quantità**.</span><span class="sxs-lookup"><span data-stu-id="662e0-159">On the **On-hand inventory** page, select **Adjust quantity**.</span></span> <span data-ttu-id="662e0-160">È possibile aprire la pagina **Scorte disponibili** in diversi metodi.</span><span class="sxs-lookup"><span data-stu-id="662e0-160">You can open the **On-hand inventory** page in several ways.</span></span> <span data-ttu-id="662e0-161">Ad esempio, selezionando **Gestione inventario** \> **Richieste di informazioni e report** \> **Scorte disponibili**.</span><span class="sxs-lookup"><span data-stu-id="662e0-161">For example, select **Inventory management** \> **Inquiries and reports** \> **On-hand inventory**.</span></span>
2. <span data-ttu-id="662e0-162">Selezionare **Rettifica quantità**, quindi nel campo **Codice motivo conteggio** selezionare un codice motivo.</span><span class="sxs-lookup"><span data-stu-id="662e0-162">Select **Adjust quantity**, and then, in the **Counting reason code** field, select a reason code.</span></span>

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a><span data-ttu-id="662e0-163">Configurare i codici motivo per le voci di menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="662e0-163">Configure reason codes for mobile device menu items</span></span>

<span data-ttu-id="662e0-164">È possibile configurare i codici motivo per qualsiasi tipo di conteggio su una voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="662e0-164">You can configure reason codes for any type of count on a mobile device menu item.</span></span> <span data-ttu-id="662e0-165">La configurazione della voce di menu del dispositivo mobile include le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="662e0-165">The configuration of the mobile device menu item includes the following information:</span></span>

- <span data-ttu-id="662e0-166">Indica se il codice motivo viene mostrato al lavoratore con il dispositivo mobile durante il conteggio.</span><span class="sxs-lookup"><span data-stu-id="662e0-166">Whether the reason code is shown to the mobile device worker during counting.</span></span>
- <span data-ttu-id="662e0-167">Il codice motivo predefinito mostrato su una voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="662e0-167">The default reason code that is shown on a mobile device menu item.</span></span>
- <span data-ttu-id="662e0-168">Se l'utente può modificare il codice motivo.</span><span class="sxs-lookup"><span data-stu-id="662e0-168">Whether the user can edit the reason code.</span></span>

### <a name="set-up-reason-codes-on-a-mobile-device"></a><span data-ttu-id="662e0-169">Impostare i codici motivo su un dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="662e0-169">Set up reason codes on a mobile device</span></span>

1. <span data-ttu-id="662e0-170">Selezionare **Gestione magazzino** \> **Impostazioni** \> **Dispositivo mobile** \> **Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="662e0-170">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="662e0-171">Nella scheda **Conteggio ciclo**, scegliere **Conteggio ciclo**.</span><span class="sxs-lookup"><span data-stu-id="662e0-171">On the **Cycle count** tab, select **Cycle counting**.</span></span>
3. <span data-ttu-id="662e0-172">Nel campo **Codice motivo conteggio predefinito** impostare il codice motivo predefinito che deve essere registrato quando il conteggio viene eseguito utilizzando la voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="662e0-172">In the **Default counting reason code** field, set the default reason code that should be recorded when counting is done by using the mobile device menu item.</span></span>
4. <span data-ttu-id="662e0-173">Nel campo **Visualizza codice motivo conteggio** selezionare **Riga** per visualizzare il codice motivo dopo ogni scostamento viene registrato.</span><span class="sxs-lookup"><span data-stu-id="662e0-173">In the **Display counting reason code** field, select **Line** to show the reason code after each variance is recorded.</span></span> <span data-ttu-id="662e0-174">In alternativa, selezionare **Nascondi** se il codice motivo non deve essere mostrato.</span><span class="sxs-lookup"><span data-stu-id="662e0-174">Alternatively, select **Hide** if the reason code shouldn't be shown.</span></span>
5. <span data-ttu-id="662e0-175">Impostare l'opzione **Modifica codice motivo conteggio** su **Sì** o **No**.</span><span class="sxs-lookup"><span data-stu-id="662e0-175">Set the **Edit counting reason code** option to either **Yes** or **No**.</span></span> <span data-ttu-id="662e0-176">Se si imposta questa opzione su **Sì**, il lavoratore può modificare il codice motivo quando viene visualizzato sul dispositivo mobile durante il conteggio.</span><span class="sxs-lookup"><span data-stu-id="662e0-176">If you set this option to **Yes**, the worker can edit the reason code when it's shown on the mobile device during counting.</span></span>

> [!NOTE]
> <span data-ttu-id="662e0-177">Il pulsante **Conteggio ciclo** può essere abilitato su qualsiasi voce di menu del dispositivo mobile in cui è possibile eseguire il conteggio.</span><span class="sxs-lookup"><span data-stu-id="662e0-177">The **Cycle counting** button can be enabled on any mobile device menu item where counting can be done.</span></span> <span data-ttu-id="662e0-178">L'esempio include le voci di menu per i conteggi ciclo a campione, il lavoro diretto dall'utente e il lavoro diretto dal sistema.</span><span class="sxs-lookup"><span data-stu-id="662e0-178">Example include the menu items for spot counts, user-directed work, and system-directed work.</span></span>

## <a name="cycle-count-approvals"></a><span data-ttu-id="662e0-179">Approvazioni del conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="662e0-179">Cycle count approvals</span></span>

<span data-ttu-id="662e0-180">Prima che un conteggio venga approvato, l'utente può modificare il codice motivo associato al conteggio.</span><span class="sxs-lookup"><span data-stu-id="662e0-180">Before a count is approved, the user can change the reason code that is associated with the count.</span></span> <span data-ttu-id="662e0-181">Quando il conteggio viene approvato, il codice motivo viene inserito nelle righe del giornale di registrazione di conteggio</span><span class="sxs-lookup"><span data-stu-id="662e0-181">When the count is approved, the reason code is entered on the counting journal lines.</span></span>

### <a name="modify-cycle-count-approvals"></a><span data-ttu-id="662e0-182">Modifica delle approvazioni del conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="662e0-182">Modify cycle count approvals</span></span>

1. <span data-ttu-id="662e0-183">Selezionare **Gestione magazzino** \> **Conteggio ciclo** \> **Lavoro conteggio ciclo con revisione in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="662e0-183">Select **Warehouse management** \> **Cycle counting** \> **Cycle count work pending review**.</span></span>
2. <span data-ttu-id="662e0-184">Selezionare **Conteggio ciclo**, quindi nel campo **Codice motivo** selezionare un nuovo codice motivo.</span><span class="sxs-lookup"><span data-stu-id="662e0-184">Select **Cycle counting**, and then, in the **Reason code** field, select a new reason code.</span></span>

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a><span data-ttu-id="662e0-185">Modificare la voce di menu del dispositivo mobile per Rettifica e Rettifica in uscita</span><span class="sxs-lookup"><span data-stu-id="662e0-185">Modify the mobile device menu item for Adjustment in and Adjustment out</span></span>

1. <span data-ttu-id="662e0-186">Selezionare **Gestione magazzino** \> **Impostazione** \> **Dispositivo mobile** \> **Voci di menu del dispositivo mobile** e quindi **Rettifica in entrata e in uscita**.</span><span class="sxs-lookup"><span data-stu-id="662e0-186">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**, and then select **Adjustment in and out**.</span></span>
2. <span data-ttu-id="662e0-187">Impostare l'opzione **Utilizza lavoro esistente** su **No**.</span><span class="sxs-lookup"><span data-stu-id="662e0-187">Set the **Use existing work** option to **No**.</span></span>
3. <span data-ttu-id="662e0-188">Nel campo **Processo di creazione lavoro** selezionare **Rettifica in entrata**.</span><span class="sxs-lookup"><span data-stu-id="662e0-188">In the **Work creation process** field, select **Adjustment in**.</span></span>

<span data-ttu-id="662e0-189">I seguenti campi verranno aggiunti alla voce di menu del dispositivo mobile quando si seleziona **Rettifica in entrata** o **Rettifica in uscita** durante il processo di creazione del lavoro:</span><span class="sxs-lookup"><span data-stu-id="662e0-189">The following fields will be added to the mobile device menu item when **Adjustment in** or **Adjustment out** is selected during the work creation process:</span></span>

- <span data-ttu-id="662e0-190">Codice motivo conteggio predefinito</span><span class="sxs-lookup"><span data-stu-id="662e0-190">Default counting reason code</span></span>
- <span data-ttu-id="662e0-191">Visualizza codice motivo conteggio</span><span class="sxs-lookup"><span data-stu-id="662e0-191">Display counting reason code</span></span>
- <span data-ttu-id="662e0-192">Modifica codice motivo conteggio</span><span class="sxs-lookup"><span data-stu-id="662e0-192">Edit counting reason code</span></span>
