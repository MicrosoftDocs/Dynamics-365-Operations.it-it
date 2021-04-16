---
title: Tempi di fermo per la manutenzione per ordini di lavoro
description: Questo argomento descrive come creare registrazioni di tempi di fermo per la manutenzione nel cespite selezionato in un ordine di lavoro.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5c0c584ed53dc4ec8a761065838127dc67cbc41e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813727"
---
# <a name="maintenance-downtime-for-work-orders"></a><span data-ttu-id="91ef2-103">Tempi di fermo per la manutenzione per ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="91ef2-103">Maintenance downtime for work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="91ef2-104">È possibile creare registrazioni di tempi di fermo per la manutenzione nel cespite selezionato in un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="91ef2-104">You can create maintenance downtime registrations on the asset that is selected on a work order.</span></span> <span data-ttu-id="91ef2-105">Questa funzionalità è utile se si desidera registrare i tempi di fermo per la manutenzione in una o più macchine nell'area di produzione.</span><span class="sxs-lookup"><span data-stu-id="91ef2-105">This capability is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="91ef2-106">Innanzitutto, creare i codici motivo dei tempi di fermo per la manutenzione che si desidera utilizzare, ad esempio, **Suddivisione** e **Interruzione pianificata**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-106">You first create the maintenance downtime reason codes that you want to use, such as **Breakdown** and **Planned stop**.</span></span> <span data-ttu-id="91ef2-107">Questo passaggio viene eseguito nella pagina **Codici motivo dei tempi di fermo per la manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-107">This step is done on the **Maintenance downtime reason codes** page.</span></span> <span data-ttu-id="91ef2-108">Quindi, è possibile creare registrazioni di tempi di fermo per la manutenzione nella pagina **Tempi di fermo per la manutenzione** e aggiungere i codici motivo dei tempi di fermo per la manutenzione pertinenti.</span><span class="sxs-lookup"><span data-stu-id="91ef2-108">You can then create maintenance downtime registrations on the **Maintenance downtime** page and add the relevant maintenance downtime reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="91ef2-109">Creare codici motivo dei tempi di fermo per la manutenzione</span><span class="sxs-lookup"><span data-stu-id="91ef2-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="91ef2-110">Selezionare **Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Codici motivo dei tempi di fermo per la manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-110">Select **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="91ef2-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-111">Select **New**.</span></span>

3. <span data-ttu-id="91ef2-112">Nel campo **Codici motivo dei tempi di fermo per la manutenzione**, immettere un ID per il codice motivo dei tempi di fermo per la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="91ef2-112">In the **Maintenance downtime reason code** field, enter an ID for the maintenance downtime reason code.</span></span>

4. <span data-ttu-id="91ef2-113">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="91ef2-113">In the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="91ef2-114">Selezionare la casella di controllo **Includi in KPI** se il codice motivo viene incluso nei calcoli degli indicatori di prestazioni chiave (KPI) per il cespite.</span><span class="sxs-lookup"><span data-stu-id="91ef2-114">Select the **KPI include** check box if the reason code should be included in calculations of key performance indicators (KPIs) for the asset.</span></span> <span data-ttu-id="91ef2-115">In genere, le interruzioni di produzione pianificate non devono essere incluse nei calcoli KPI perché non influenzano le prestazioni previste.</span><span class="sxs-lookup"><span data-stu-id="91ef2-115">In general, planned production stops should not be included in KPI calculations, because they don't affect expected performance.</span></span>

6. <span data-ttu-id="91ef2-116">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-116">Select **Save**.</span></span>

<span data-ttu-id="91ef2-117">Nella figura seguente è illustrato un esempio della pagina **Codici motivo dei tempi di fermo per la manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-117">The illustration below shows an example of the **Maintenance downtime reason codes** page.</span></span>

![Figura 1](media/15-work-orders.png)

<span data-ttu-id="91ef2-119">Dopo aver creato i codici motivo dei tempi di fermo per la manutenzione che si desidera utilizzare, è possibile creare registrazioni di tempi di fermo per la manutenzione per ordini di lavoro e cespiti.</span><span class="sxs-lookup"><span data-stu-id="91ef2-119">After you've created the maintenance downtime reason codes that you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="91ef2-120">Creare registrazioni di tempi di fermo per la manutenzione</span><span class="sxs-lookup"><span data-stu-id="91ef2-120">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="91ef2-121">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-121">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="91ef2-122">Selezionare l'ordine di lavoro, quindi nella scheda **Ordine di lavoro**, nel gruppo **Cespite**, selezionare **Tempi di fermo per la manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-122">Select the work order, and then, on the **Work order** tab, in the **Asset** group, select **Maintenance downtime**.</span></span>

3. <span data-ttu-id="91ef2-123">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-123">Select **New**.</span></span>

4. <span data-ttu-id="91ef2-124">Nei campi **Dal** e **Al**, definire la data e l'intervallo di tempo per la registrazione dei tempi di inattività per la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="91ef2-124">In the **From** and **To** fields, define the date and time interval for the maintenance downtime registration.</span></span>

>[!NOTE]
><span data-ttu-id="91ef2-125">Quando si lascia vuoto il campo **A**, la durata in ore viene immessa automaticamente nel campo **Durata**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-125">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

5. <span data-ttu-id="91ef2-126">Selezionare un codice motivo nel campo **Codice motivo dei tempi di fermo per la manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-126">In the **maintenance downtime reason code** field, select a reason code.</span></span>

6. <span data-ttu-id="91ef2-127">Ripetere i passaggi da 3 a 5 per aggiungere ulteriori registrazioni.</span><span class="sxs-lookup"><span data-stu-id="91ef2-127">Repeat steps 3 through 5 to add more registrations.</span></span>

7. <span data-ttu-id="91ef2-128">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-128">Select **Save**.</span></span>

<span data-ttu-id="91ef2-129">Nella figura seguente viene illustrato un esempio di una registrazione dei tempi di fermo per la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="91ef2-129">The illustration below shows an example of maintenance downtime registration.</span></span>

![Figura 2](media/16-work-orders.png)

<span data-ttu-id="91ef2-131">Il calendario utilizzato per calcolare una registrazione di tempi di fermo per la manutenzione dipende dalla selezione nell'impostazione dei cespiti e dei parametri.</span><span class="sxs-lookup"><span data-stu-id="91ef2-131">The calendar that is used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="91ef2-132">Se una risorsa è selezionata in un cespite nel campo **Risorsa** della scheda dettaglio **Cespite** della pagina **Tutti i cespiti**, viene utilizzata l'impostazione del calendario per il gruppo di risorse associato, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="91ef2-132">If a resource is selected on an asset in the **Resource** field on the **Fixed asset** FastTab of the **All assets** page, the calendar that is set up for the associated resource group is used, as shown in the following illustration.</span></span>

![Figura 3](media/17-work-orders.png)

<span data-ttu-id="91ef2-134">Se non si seleziona una risorsa nel cespite, viene utilizzato il calendario standard selezionato nella pagina **Parametri di gestione cespiti**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="91ef2-134">If no resource is selected on the asset, the standard calendar that is selected on the **Asset management parameters** page is used, as shown in the following illustration.</span></span>

![Figura 4](media/18-work-orders.png)

<span data-ttu-id="91ef2-136">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Tempi di fermo per la manutenzione** per visualizzare una panoramica di tutte le registrazioni di tempi di fermo per la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="91ef2-136">To see an overview of all maintenance downtime registrations, click **Asset management** > **Inquiries** > **Maintenance downtime**.</span></span>

>[!NOTE]
><span data-ttu-id="91ef2-137">Tutti i calendari utilizzati nel modulo **Gestione cespiti** sono impostati in **Amministrazione organizzazione** > **Impostazione** > **Calendari** > **Calendari**.</span><span class="sxs-lookup"><span data-stu-id="91ef2-137">All calendars that are used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]