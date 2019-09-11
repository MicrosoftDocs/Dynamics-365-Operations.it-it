---
title: Tempi di fermo per la manutenzione
description: In questo argomento vengono descritti i tempi di fermo per la manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918246"
---
# <a name="maintenance-downtime"></a><span data-ttu-id="c8f7a-103">Tempi di fermo per la manutenzione</span><span class="sxs-lookup"><span data-stu-id="c8f7a-103">Maintenance downtime</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="c8f7a-104">È possibile creare registrazioni di tempi di fermo per la manutenzione nel cespite selezionato in un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-104">You can create maintenance downtime registrations on the asset selected on a work order.</span></span> <span data-ttu-id="c8f7a-105">Ciò è utile se si desidera registrare i tempi di fermo per la manutenzione in una o più macchine nell'area di produzione.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-105">This is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="c8f7a-106">Innanzitutto, creare i codici motivo dei tempi di fermo per la manutenzione che si desidera utilizzare, ad esempio, guasti e interruzione pianificate.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-106">First, you create the maintenance downtime reason codes that you want to use, for example, breakdown and planned stop.</span></span> <span data-ttu-id="c8f7a-107">Questa operazione viene eseguita in **Codici motivo dei tempi di fermo per la manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-107">This is done in **Maintenance downtime reason codes**.</span></span> <span data-ttu-id="c8f7a-108">Successivamente, è possibile creare registrazioni di tempi di fermo per la manutenzione in **Tempi di fermo per la manutenzione** e aggiungere i codici motivo pertinenti.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-108">Next, you can create maintenance downtime registrations in **Maintenance downtime** and add the relevant reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="c8f7a-109">Creare codici motivo dei tempi di fermo per la manutenzione</span><span class="sxs-lookup"><span data-stu-id="c8f7a-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="c8f7a-110">Fare clic **Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Codici motivo dei tempi di fermo per la manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-110">Click **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="c8f7a-111">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-111">Click **New**.</span></span>

3. <span data-ttu-id="c8f7a-112">Inserire un ID nel campo **Codici motivo dei tempi di fermo per la manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-112">Insert an ID in the **Maintenance downtime reason code** field.</span></span>

4. <span data-ttu-id="c8f7a-113">Nel campo **Nome** immettere un nome per il codice motivo.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-113">Insert a name for the reason code in the **Name** field.</span></span>

5. <span data-ttu-id="c8f7a-114">Selezionare la casella di controllo **Includi in KPI** se il codice motivo deve essere incluso nei calcoli KPI dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-114">Select the **KPI include** check box if the reason code should be included in asset KPI calculations.</span></span> <span data-ttu-id="c8f7a-115">In genere, le interruzioni di produzione pianificate non devono essere incluse nei calcoli KPI poiché non influenzano le prestazioni previste.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-115">Generally, planned production stops should not be included in KPI calculations as they do not impact expected performance.</span></span>

6. <span data-ttu-id="c8f7a-116">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-116">Click **Save**.</span></span>

![Figura 1](media/15-work-orders.png)


<span data-ttu-id="c8f7a-118">Dopo aver creato i codici motivo dei tempi di fermo per la manutenzione che si desidera utilizzare, è possibile creare registrazioni di tempi di fermo per la manutenzione per ordini di lavoro e cespiti.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-118">When you have created the maintenance downtime reason codes you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="c8f7a-119">Creare registrazioni di tempi di fermo per la manutenzione</span><span class="sxs-lookup"><span data-stu-id="c8f7a-119">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="c8f7a-120">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-120">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="c8f7a-121">Selezionare l'ordine di lavoro e fare clic su **Tempi di fermo per la manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-121">Select the work order and click **Maintenance downtime**.</span></span>

3. <span data-ttu-id="c8f7a-122">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-122">Click **New**.</span></span>

4. <span data-ttu-id="c8f7a-123">Immettere la data e l'intervallo di tempo per la registrazione di tempi di fermo per la manutenzione nei campi **Da** e **A**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-123">Insert date and time interval for the maintenance downtime registration in the **From** and **To** fields.</span></span>

5. <span data-ttu-id="c8f7a-124">Quando si lascia vuoto il campo **A**, la durata in ore viene immessa automaticamente nel campo **Durata**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-124">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

6. <span data-ttu-id="c8f7a-125">Selezionare un codice motivo nel campo **Codice motivo dei tempi di fermo per la manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-125">Select a reason code in the **maintenance downtime reason code** field.</span></span>

7. <span data-ttu-id="c8f7a-126">Ripetere i passaggi da 3 a 6 per aggiungere più registrazioni.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-126">Repeat steps 3-6 if you want to add more registrations.</span></span>

8. <span data-ttu-id="c8f7a-127">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-127">Click **Save**.</span></span>


![Figura 2](media/16-work-orders.png)


<span data-ttu-id="c8f7a-129">Il calendario utilizzato per calcolare una registrazione di tempi di fermo per la manutenzione dipende dalla selezione nell'impostazione dei cespiti e dei parametri.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-129">The calendar used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="c8f7a-130">Se una risorsa è selezionata in un cespite in **Tutti i cespiti** > Scheda dettaglio **Cespite** > campo **Risorsa**, viene utilizzata l'impostazione del calendario per il gruppo di risorse associato, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-130">If a resource is selected on an asset in **All assets** > **Fixed asset** FastTab > **Resource** field, the calendar set up for the associated resource group is used, as shown in the following figure.</span></span>

![Figura 3](media/17-work-orders.png)


<span data-ttu-id="c8f7a-132">Se non si seleziona una risorsa nel cespite, viene utilizzato il calendario standard selezionato in **Parametri di gestione cespiti**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-132">If no resource is selected on the asset, the standard calendar selected in **Asset management parameters** is used, as shown in the following figure.</span></span>

![Figura 4](media/18-work-orders.png)


<span data-ttu-id="c8f7a-134">Fare clic su **Gestione cespiti aziendali** > **Richieste di informazioni** > **Tempi di fermo per la manutenzione** per visualizzare una panoramica di tutte le registrazioni di tempi di fermo per la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-134">Click **Enterprise asset management** > **Inquiries** > **Maintenance downtime** to see an overview of all maintenance downtime registrations.</span></span>

>[!NOTE]
><span data-ttu-id="c8f7a-135">Tutti i calendari utilizzati nel modulo **Gestione cespiti** sono impostati in **Amministrazione organizzazione** > **Impostazione** > **Calendari** > **Calendari**.</span><span class="sxs-lookup"><span data-stu-id="c8f7a-135">All calendars used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

