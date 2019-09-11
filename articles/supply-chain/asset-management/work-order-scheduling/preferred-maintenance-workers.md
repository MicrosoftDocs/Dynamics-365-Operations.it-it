---
title: Impostare gli addetti alla manutenzione preferiti
description: In questo argomento viene illustrato come impostare gli addetti alla manutenzione preferiti in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887413"
---
# <a name="preferred-maintenance-workers"></a><span data-ttu-id="66836-103">Addetti alla manutenzione preferiti</span><span class="sxs-lookup"><span data-stu-id="66836-103">Preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="66836-104">È possibile indicare una preferenza riguardo agli addetti alla manutenzione da allocare per completare gli ordini di lavoro durante la programmazione degli stessi.</span><span class="sxs-lookup"><span data-stu-id="66836-104">You can make a preference regarding which maintenance workers are allocated to complete work orders during work order scheduling.</span></span> <span data-ttu-id="66836-105">L'utilizzo di questa funzionalità è facoltativa, ma può consentire la scelta dell'addetto alla manutenzione più qualificato per completare un processo, in base alle competenze del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="66836-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="66836-106">Pertanto, durante la programmazione degli ordini di lavoro, l'impostazione in **Addetti alla manutenzione preferiti** viene utilizzata per determinare se uno specifico addetto alla manutenzione o gruppo di addetti alla manutenzione deve essere programmato per un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="66836-106">Therefore, during work order scheduling, the setup in **Preferred maintenance workers** is used to determine if a specific maintenance worker or worker group should be scheduled for a work order.</span></span> <span data-ttu-id="66836-107">Solo gli addetti alla manutenzione disponibili all'ora della programmazione verranno programmati.</span><span class="sxs-lookup"><span data-stu-id="66836-107">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="66836-108">Se l'impostazione di un addetto alla manutenzione preferito corrisponde a un ordine di lavoro durante la programmazione, ma tale addetto è allocato ad altri processi, l'ordine di lavoro verrà programmato per un altro addetto alla manutenzione disponibile.</span><span class="sxs-lookup"><span data-stu-id="66836-108">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another, available, maintenance worker.</span></span>

<span data-ttu-id="66836-109">Prima di poter impostare gli addetti alla manutenzione preferiti, è necessario dapprima impostare gli addetti e i gruppi di addetti alla manutenzione che devono essere disponibili per la selezione.</span><span class="sxs-lookup"><span data-stu-id="66836-109">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups that should be available for selection.</span></span> <span data-ttu-id="66836-110">Per una descrizione su come impostare i gruppi di addetti e gli addetti alla manutenzione, vedere [Addetti e gruppi di addetti alla manutenzione](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="66836-110">Refer to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md) for a description on how to set up maintenance workers and worker groups.</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="66836-111">Impostare i lavoratori preferiti</span><span class="sxs-lookup"><span data-stu-id="66836-111">Set up preferred workers</span></span>

<span data-ttu-id="66836-112">Un addetto o un gruppo di addetti alla manutenzione preferito può essere associato in modo specifico a</span><span class="sxs-lookup"><span data-stu-id="66836-112">A preferred maintenance worker or worker group can be related to a specific</span></span>

- <span data-ttu-id="66836-113">settore</span><span class="sxs-lookup"><span data-stu-id="66836-113">trade</span></span>  
- <span data-ttu-id="66836-114">variante di tipi di processo di manutenzione</span><span class="sxs-lookup"><span data-stu-id="66836-114">maintenance job type variant</span></span>  
- <span data-ttu-id="66836-115">tipo di processo di manutenzione</span><span class="sxs-lookup"><span data-stu-id="66836-115">maintenance job type</span></span>  
- <span data-ttu-id="66836-116">categoria di tipi di processo di manutenzione</span><span class="sxs-lookup"><span data-stu-id="66836-116">maintenance job type category</span></span>  
- <span data-ttu-id="66836-117">cespite</span><span class="sxs-lookup"><span data-stu-id="66836-117">asset</span></span>  
- <span data-ttu-id="66836-118">tipo di cespite</span><span class="sxs-lookup"><span data-stu-id="66836-118">asset type</span></span>  

<span data-ttu-id="66836-119">o una combinazione di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="66836-119">or a combination of those selections.</span></span> <span data-ttu-id="66836-120">Più selezioni vengono effettuate per lo stesso record, più specifica sarà l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="66836-120">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="66836-121">Fare clic su **Gestione cespiti** > **Impostazione** > **Lavoratori** > **Addetti alla manutenzione preferiti**.</span><span class="sxs-lookup"><span data-stu-id="66836-121">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="66836-122">Fare clic su **Nuovo** per creare un nuovo record.</span><span class="sxs-lookup"><span data-stu-id="66836-122">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="66836-123">Iniziare creando un'impostazione di addetto o gruppo di addetti alla manutenzione predefinita che non presenta selezioni nei campi visualizzati nell'elenco precedente.</span><span class="sxs-lookup"><span data-stu-id="66836-123">Start by creating a "default" maintenance worker or worker group setup that has no selections in the fields shown in the bullet list above.</span></span> <span data-ttu-id="66836-124">Ciò significa che si esegue una selezione solo nel campo **Gruppo di addetti alla manutenzione preferito** o nel campo **Addetto alla manutenzione preferito**.</span><span class="sxs-lookup"><span data-stu-id="66836-124">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="66836-125">Nella figura seguente, viene visualizzato un esempio del primo record in cui "Richieste" è selezionato come gruppo di addetti alla manutenzione preferito.</span><span class="sxs-lookup"><span data-stu-id="66836-125">In the figure below, you see an example in the first record in which "Requests" is selected as preferred maintenance worker group.</span></span>

>[!NOTE]
><span data-ttu-id="66836-126">L'impostazione predefinita verrà utilizzata durante la programmazione degli ordini di lavoro se nessun'altra combinazione più specifica corrisponde al contenuto dell'ordine di lavoro durante la programmazione dello stesso.</span><span class="sxs-lookup"><span data-stu-id="66836-126">The default setup will be used during work order scheduling in case no other, more specific, combination matches the contents of the work order during work order scheduling.</span></span>

4. <span data-ttu-id="66836-127">Ripetere il passaggio 2 per creare un nuovo record.</span><span class="sxs-lookup"><span data-stu-id="66836-127">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="66836-128">Effettuare le selezioni necessarie, a seconda del livello di dettagli per l'addetto o il gruppo di addetti preferito.</span><span class="sxs-lookup"><span data-stu-id="66836-128">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> <span data-ttu-id="66836-129">*Esempio:* nella figura seguente, nel sesto record, l'addetto alla manutenzione Shawn Richardson è selezionato come lavoratore preferito.</span><span class="sxs-lookup"><span data-stu-id="66836-129">*Example:* In the figure below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="66836-130">Shawn sarà selezionato automaticamente durante la programmazione di un ordine di lavoro che include il cespite "CH-BP1-03-02" e il tipo di processo di manutenzione "Valutazione struttura", se è disponibile al momento della programmazione.</span><span class="sxs-lookup"><span data-stu-id="66836-130">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintennace job type "Facility assessment", if he is available at the scheduled time.</span></span>

>[!NOTE]
><span data-ttu-id="66836-131">In genere, quando un addetto alla manutenzione preferito è selezionato durante la programmazione di un ordine di lavoro, Gestione cespiti esamina tutti i record **Addetti alla manutenzione preferiti** per determinare una corrispondenza possibile, sempre verificando dapprima la combinazione più specifica.</span><span class="sxs-lookup"><span data-stu-id="66836-131">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="66836-132">Se non viene trovata alcuna corrispondenza, viene utilizzato il record "predefinito" con una selezione nel campo **Gruppo di addetti alla manutenzione preferito** o nel campo **Addetto alla manutenzione preferito**.</span><span class="sxs-lookup"><span data-stu-id="66836-132">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>


![Figura 1](media/02-work-order-scheduling.png)

<span data-ttu-id="66836-134">È anche possibile impostare addetti alla manutenzione responsabili che possono essere selezionati quando viene creata una richiesta di intervento di manutenzione o un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="66836-134">You can also set up responsible maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="66836-135">In **Tutti gli ordini di lavoro** e **Tutte le richieste di intervento di manutenzione**, è possibile modificare la selezione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="66836-135">In **All work orders** and **All maintenance requests**, you can edit the selection, if required.</span></span> <span data-ttu-id="66836-136">Per ulteriori informazioni, vedere [Addetti alla manutenzione responsabili](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="66836-136">Refer to [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md) for more information.</span></span>

<span data-ttu-id="66836-137">Durante la programmazione degli ordini di lavoro, vengono calcolati vari punteggi per determinare quali lavoratori devono completare i processi relativi a un ordine di lavoro (tali punteggi sono impostati in **Parametri di gestione cespiti** >  collegamento **Programmazione dell'ordine di lavoro**).</span><span class="sxs-lookup"><span data-stu-id="66836-137">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="66836-138">Se due o più addetti alla manutenzione preferiti o addetti alla manutenzione responsabili ottengono lo stesso punteggio durante la programmazione dell'ordine di lavoro, un lavoratore viene selezionato in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="66836-138">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="66836-139">In caso contrario, è sempre il lavoratore con il punteggio massimo che viene scelto per completare un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="66836-139">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

