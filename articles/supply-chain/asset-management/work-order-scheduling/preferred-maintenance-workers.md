---
title: Impostare gli addetti alla manutenzione preferiti
description: In questo argomento viene illustrato come impostare gli addetti alla manutenzione preferiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ab36d9fde0cc6e864f21f9ebd09834f5098c1913
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021406"
---
# <a name="set-up-preferred-maintenance-workers"></a><span data-ttu-id="0af78-103">Imposta gli addetti alla manutenzione preferiti</span><span class="sxs-lookup"><span data-stu-id="0af78-103">Set up preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0af78-104">Durante la programmazione degli ordini di lavoro, è possibile indicare una preferenza riguardo all'addetto alla manutenzione o al gruppo di addetti da allocare per completare l'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0af78-104">During work order scheduling, you can make a preference regarding which maintenance worker or worker group is allocated to complete the work order.</span></span> <span data-ttu-id="0af78-105">L'utilizzo di questa funzionalità è facoltativa, ma può consentire la scelta dell'addetto alla manutenzione più qualificato per completare un processo, in base alle competenze del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="0af78-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="0af78-106">Solo gli addetti alla manutenzione disponibili all'ora della programmazione verranno programmati.</span><span class="sxs-lookup"><span data-stu-id="0af78-106">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="0af78-107">Se l'impostazione di un addetto alla manutenzione preferito corrisponde a un ordine di lavoro durante la programmazione, ma tale addetto è allocato ad altri processi, l'ordine di lavoro verrà programmato per un altro addetto alla manutenzione disponibile.</span><span class="sxs-lookup"><span data-stu-id="0af78-107">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another available maintenance worker.</span></span>

<span data-ttu-id="0af78-108">Prima di impostare gli addetti alla manutenzione preferiti, è innanzitutto necessario impostare gli addetti alla manutenzione e i gruppi di addetti.</span><span class="sxs-lookup"><span data-stu-id="0af78-108">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups.</span></span> <span data-ttu-id="0af78-109">Per una descrizione su come impostare i gruppi di addetti e gli addetti alla manutenzione, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0af78-109">For a description about how to set up maintenance workers and worker groups, see to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="0af78-110">Impostare i lavoratori preferiti</span><span class="sxs-lookup"><span data-stu-id="0af78-110">Set up preferred workers</span></span>

<span data-ttu-id="0af78-111">Un addetto o un gruppo di addetti alla manutenzione preferito può essere associato uno o più dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="0af78-111">A preferred maintenance worker or worker group can be related to one or more of the following:</span></span>

- <span data-ttu-id="0af78-112">settore</span><span class="sxs-lookup"><span data-stu-id="0af78-112">trade</span></span>  
- <span data-ttu-id="0af78-113">variante di tipi di processo di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0af78-113">maintenance job type variant</span></span>  
- <span data-ttu-id="0af78-114">tipo di processo di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0af78-114">maintenance job type</span></span>  
- <span data-ttu-id="0af78-115">categoria di tipi di processo di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0af78-115">maintenance job type category</span></span>  
- <span data-ttu-id="0af78-116">cespite</span><span class="sxs-lookup"><span data-stu-id="0af78-116">asset</span></span>  
- <span data-ttu-id="0af78-117">tipo di cespite</span><span class="sxs-lookup"><span data-stu-id="0af78-117">asset type</span></span>  

<span data-ttu-id="0af78-118">Più selezioni vengono effettuate per lo stesso record, più specifica sarà l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="0af78-118">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="0af78-119">Fare clic su **Gestione cespiti** > **Impostazione** > **Lavoratori** > **Addetti alla manutenzione preferiti**.</span><span class="sxs-lookup"><span data-stu-id="0af78-119">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="0af78-120">Fare clic su **Nuovo** per creare un nuovo record.</span><span class="sxs-lookup"><span data-stu-id="0af78-120">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="0af78-121">Iniziare creando un addetto alla manutenzione o un gruppo di lavoratori "predefinito".</span><span class="sxs-lookup"><span data-stu-id="0af78-121">Start by creating a "default" maintenance worker or worker group.</span></span> <span data-ttu-id="0af78-122">Ciò significa che si esegue una selezione solo nel campo **Gruppo di addetti alla manutenzione preferito** o nel campo **Addetto alla manutenzione preferito**.</span><span class="sxs-lookup"><span data-stu-id="0af78-122">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="0af78-123">Nella schermata seguente, viene visualizzato un esempio del primo record in cui "Richieste" è selezionato come **gruppo di addetti alla manutenzione preferito**.</span><span class="sxs-lookup"><span data-stu-id="0af78-123">In the screenshot below, you see an example in the first record in which "Requests" is selected as **Preferred maintenance worker group**.</span></span>

    [!NOTE] <span data-ttu-id="0af78-124">L'impostazione predefinita verrà utilizzata durante la programmazione degli ordini di lavoro se nessun'altra combinazione più specifica corrisponde al contenuto dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0af78-124">The default setup will be used during work order scheduling if no other, more specific, combination matches the contents of the work order.</span></span>

4. <span data-ttu-id="0af78-125">Ripetere il passaggio 2 per creare un nuovo record.</span><span class="sxs-lookup"><span data-stu-id="0af78-125">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="0af78-126">Effettuare le selezioni necessarie, a seconda del livello di dettagli per l'addetto o il gruppo di addetti preferito.</span><span class="sxs-lookup"><span data-stu-id="0af78-126">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> 

    <span data-ttu-id="0af78-127">*Esempio:* nella schermata seguente, nel sesto record, l'addetto alla manutenzione Shawn Richardson è selezionato come lavoratore preferito.</span><span class="sxs-lookup"><span data-stu-id="0af78-127">*Example:* In the screenshot below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="0af78-128">Shawn sarà selezionato automaticamente durante la programmazione di un ordine di lavoro che include il cespite "CH-BP1-03-02" e il tipo di processo di manutenzione "Valutazione struttura", se è disponibile al momento della programmazione.</span><span class="sxs-lookup"><span data-stu-id="0af78-128">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintenance job type "Facility assessment", if he is available at the scheduled time.</span></span>

    [!NOTE] <span data-ttu-id="0af78-129">In genere, quando un addetto alla manutenzione preferito è selezionato durante la programmazione di un ordine di lavoro, Gestione cespiti esamina tutti i record **Addetti alla manutenzione preferiti** per determinare una corrispondenza possibile, sempre verificando dapprima la combinazione più specifica.</span><span class="sxs-lookup"><span data-stu-id="0af78-129">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="0af78-130">Se non viene trovata alcuna corrispondenza, viene utilizzato il record "predefinito" con una selezione nel campo **Gruppo di addetti alla manutenzione preferito** o nel campo **Addetto alla manutenzione preferito**.</span><span class="sxs-lookup"><span data-stu-id="0af78-130">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>

![Figura 1](media/02-work-order-scheduling.png)

<span data-ttu-id="0af78-132">È anche possibile impostare addetti alla manutenzione *responsabili* che possono essere selezionati quando viene creata una richiesta di intervento di manutenzione o un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0af78-132">You can also set up *responsible* maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="0af78-133">È possibile modificare la selezione in **Tutti gli ordini di lavoro** e **Tutte le richieste di intervento di manutenzione**, se necessario.</span><span class="sxs-lookup"><span data-stu-id="0af78-133">You can edit the selection in **All work orders** and **All maintenance requests**, if required.</span></span> <span data-ttu-id="0af78-134">Per ulteriori informazioni, vedere [Addetti alla manutenzione responsabili](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="0af78-134">For more information, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

<span data-ttu-id="0af78-135">Durante la programmazione degli ordini di lavoro, vengono calcolati vari punteggi per determinare quali lavoratori devono completare i processi relativi a un ordine di lavoro (tali punteggi sono impostati in **Parametri di gestione cespiti** >  collegamento **Programmazione dell'ordine di lavoro**).</span><span class="sxs-lookup"><span data-stu-id="0af78-135">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="0af78-136">Se due o più addetti alla manutenzione preferiti o addetti alla manutenzione responsabili ottengono lo stesso punteggio durante la programmazione dell'ordine di lavoro, un lavoratore viene selezionato in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="0af78-136">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="0af78-137">In caso contrario, è sempre il lavoratore con il punteggio massimo che viene scelto per completare un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0af78-137">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

