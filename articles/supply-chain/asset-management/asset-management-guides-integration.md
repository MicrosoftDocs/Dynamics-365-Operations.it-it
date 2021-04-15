---
title: Integrare Dynamics 365 Supply Chain Management (gestione cespiti) con Dynamics 365 Guides
description: Questo argomento spiega come integrare il modulo Gestione cespiti in Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides per trarre vantaggio dalle guide alla realtà mista nei flussi di lavoro quotidiani di assistenza e manutenzione.
author: kamaybac
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 4af14a66c839ccee02008057ad1de8ef5b9d291b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813919"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a><span data-ttu-id="8a848-103">Integrare Dynamics 365 Supply Chain Management (gestione cespiti) con Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="8a848-103">Integrate Dynamics 365 Supply Chain Management (Asset management) with Dynamics 365 Guides</span></span>

<span data-ttu-id="8a848-104">È possibile integrare il modulo **Gestione cespiti** in Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides per trarre vantaggio dalle guide alla realtà mista nei flussi di lavoro quotidiani di assistenza e manutenzione.</span><span class="sxs-lookup"><span data-stu-id="8a848-104">You can integrate the **Asset management** module in Microsoft Dynamics 365 Supply Chain Management with Dynamics 365 Guides to take advantage of mixed-reality guides in your day-to-day service and maintenance workflows.</span></span> <span data-ttu-id="8a848-105">Se una guida è associata a un ordine di lavoro Gestione cespiti, un lavoratore che apre l'elenco di controllo di manutenzione dell'ordine di lavoro nell'app mobile Supply Chain Management (Dynamics 365) vede che è disponibile una guida.</span><span class="sxs-lookup"><span data-stu-id="8a848-105">If a guide is associated with an Asset Management work order, a worker who opens the work order's maintenance checklist in the Supply Chain Management (Dynamics 365) mobile app sees that a guide is available.</span></span> <span data-ttu-id="8a848-106">Il lavoratore può quindi trovare e aprire la guida nell'app Dynamics 365 Guides HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8a848-106">The worker can then find and open the guide in the Dynamics 365 Guides HoloLens app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8a848-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8a848-107">Prerequisites</span></span>

<span data-ttu-id="8a848-108">Prima di poter allegare guide agli ordini di lavoro di Gestione cespiti, è necessario completare questi prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="8a848-108">Before you can attach guides to Asset management work orders, you must complete these prerequisites:</span></span>

- <span data-ttu-id="8a848-109">[Configurare Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) versione 10.0.9 o successiva.</span><span class="sxs-lookup"><span data-stu-id="8a848-109">[Set up Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 or later.</span></span>
- <span data-ttu-id="8a848-110">[Attivare la doppia scrittura per le app Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="8a848-110">[Turn on dual-write for Supply Chain Management apps](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span></span>
- <span data-ttu-id="8a848-111">[Attivare l'anterprima](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) per la funzionalità **MRGuidesFeature**.</span><span class="sxs-lookup"><span data-stu-id="8a848-111">[Turn on flight](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) for the **MRGuidesFeature** feature.</span></span> <span data-ttu-id="8a848-112">Per gli ambienti di produzione, è prima necessario inviare un ticket di supporto affinché un tenant possa essere aggiunto al gruppo di versioni di anteprima.</span><span class="sxs-lookup"><span data-stu-id="8a848-112">(For production environments, you must first submit a support ticket to have your tenant added to the flighting group.)</span></span>
- <span data-ttu-id="8a848-113">[Attivare le seguenti chiavi di configurazione](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) nella pagina **Configurazione licenza**:</span><span class="sxs-lookup"><span data-stu-id="8a848-113">[Turn on the following configuration keys](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) on the **License configuration** page:</span></span>

    - <span data-ttu-id="8a848-114">Gestione cespiti \> Realtà mista gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="8a848-114">Asset management \> Asset management mixed reality</span></span>
    - <span data-ttu-id="8a848-115">Realtà mista \> Guida alla realtà mista</span><span class="sxs-lookup"><span data-stu-id="8a848-115">Mixed reality \> Mixed reality guide</span></span>

- <span data-ttu-id="8a848-116">[Configurare Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) versione 200.0.0.96 o successiva.</span><span class="sxs-lookup"><span data-stu-id="8a848-116">[Set up Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 or later.</span></span>

## <a name="use-dynamics-365-guides-with-asset-management"></a><span data-ttu-id="8a848-117">Utilizzare Dynamics 365 Guides con Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="8a848-117">Use Dynamics 365 Guides with Asset management</span></span>

<span data-ttu-id="8a848-118">Per associare una guida, utilizzare una riga dell'elenco di controllo di manutenzione in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="8a848-118">To associate a guide, you use a maintenance checklist line in Asset management.</span></span> <span data-ttu-id="8a848-119">È possibile creare l'associazione tramite un modello di elenco di controllo di manutenzione, un tipo di processo di manutenzione o un ordine di lavoro, poiché tutti e tre contengono righe dell'elenco di controllo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="8a848-119">You can create the association through a maintenance checklist template, a maintenance job type, or a work order, because all three contain maintenance checklist lines.</span></span> <span data-ttu-id="8a848-120">È possibile risparmiare tempo utilizzando un modello, in quanto può essere associato a tutti i tipi di processi di manutenzione che lo utilizzano.</span><span class="sxs-lookup"><span data-stu-id="8a848-120">You can save time by using a template, because a template can be associated with all the maintenance job types that use it.</span></span> <span data-ttu-id="8a848-121">Ad esempio, una guida associata a un tipo di processo di manutenzione viene automaticamente associata a tutti gli ordini di lavoro che specificano quel tipo di processo.</span><span class="sxs-lookup"><span data-stu-id="8a848-121">For example, a guide that is associated with a maintenance job type is automatically associated with all work orders that specify that job type.</span></span> <span data-ttu-id="8a848-122">D'altra parte, una guida associata direttamente a un ordine di lavoro esiste solo per tale ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a848-122">On the other hand, a guide that is associated directly with a work order exists only for that work order.</span></span>

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a><span data-ttu-id="8a848-123">Associare una guida a un modello di elenco di controllo di manutenzione</span><span class="sxs-lookup"><span data-stu-id="8a848-123">Associate a guide with a maintenance checklist template</span></span>

<span data-ttu-id="8a848-124">Per associare una guida a un modello di elenco di controllo di manutenzione, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="8a848-124">To associate a guide with a maintenance checklist template, follow these steps.</span></span>

1. <span data-ttu-id="8a848-125">Creare una guida usando le app per PC Dynamics 365 Guides e HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8a848-125">Create a guide by using the Dynamics 365 Guides PC and HoloLens apps.</span></span> <span data-ttu-id="8a848-126">Per informazioni sulla creazione di una guida, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a848-126">For information about how to create a guide, see the following topics:</span></span>

    - [<span data-ttu-id="8a848-127">Utilizzare l'app per PC per creare una guida</span><span class="sxs-lookup"><span data-stu-id="8a848-127">Use the PC app to create a guide</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/pc-app-overview)
    - [<span data-ttu-id="8a848-128">Utilizzare l'app HoloLens per posizionare gli ologrammi</span><span class="sxs-lookup"><span data-stu-id="8a848-128">Use the HoloLens app to place your holograms</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-overview)

1. <span data-ttu-id="8a848-129">In Supply Chain Management [creare un modello di elenco di controllo di manutenzione](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span><span class="sxs-lookup"><span data-stu-id="8a848-129">In Supply Chain Management, [create a maintenance checklist template](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span></span>
1. <span data-ttu-id="8a848-130">Associare la guida creata con una riga dell'elenco di controllo di manutenzione nel nuovo modello di elenco di controllo di manutenzione:</span><span class="sxs-lookup"><span data-stu-id="8a848-130">Associate the guide that you created with a maintenance checklist line in the new maintenance checklist template:</span></span>

    1. <span data-ttu-id="8a848-131">Nella Scheda dettaglio **Righe elenco di controllo di manutenzione** selezionare la riga a cui si desidera associare la guida.</span><span class="sxs-lookup"><span data-stu-id="8a848-131">On the **Maintenance checklist lines** FastTab, select the line that you want to associate the guide with.</span></span>
    1. <span data-ttu-id="8a848-132">Nella scheda dettaglio **Guide associate** selezionare **Aggiungi guida**.</span><span class="sxs-lookup"><span data-stu-id="8a848-132">On the **Associated guides** FastTab, select **Add Guide**.</span></span>

        <span data-ttu-id="8a848-133">![Associare una guida a una riga di elenco di controllo di manutenzione](media/am-guides-integration-add-guide.png "Associare una guida a una riga di elenco di controllo di manutenzione")</span><span class="sxs-lookup"><span data-stu-id="8a848-133">![Associate a guide with a maintenance checklist line](media/am-guides-integration-add-guide.png "Associate a guide with a maintenance checklist line")</span></span>

    1. <span data-ttu-id="8a848-134">Nel campo **Nome** selezionare una guida, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8a848-134">In the **Name** field, select a guide, and then select **Save**.</span></span>

        <span data-ttu-id="8a848-135">![Selezionare una guida nel campo Nome](media/am-guides-integration-select-guide.png "Selezionare una guida nel campo Nome")</span><span class="sxs-lookup"><span data-stu-id="8a848-135">![Select a guide in the Name field](media/am-guides-integration-select-guide.png "Select a guide in the Name field")</span></span>

1. <span data-ttu-id="8a848-136">Associare il modello di elenco di controllo di manutenzione a un tipo di processo:</span><span class="sxs-lookup"><span data-stu-id="8a848-136">Associate the maintenance checklist template with a job type:</span></span>

    1. <span data-ttu-id="8a848-137">[Creare un tipo di processo di manutenzione](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) o selezionare un tipo di processo di manutenzione esistente.</span><span class="sxs-lookup"><span data-stu-id="8a848-137">[Create a maintenance job type](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type), or select an existing maintenance job type.</span></span>
    1. <span data-ttu-id="8a848-138">Nel riquadro azioni selezionare **Valori predefiniti tipo di processo di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="8a848-138">On the Action Pane, select **Maintenance job type defaults**.</span></span>

        <span data-ttu-id="8a848-139">![Pulsante Valori predefiniti tipo di processo di manutenzione](media/am-guides-integration-job-defaults.png "Pulsante Valori predefiniti tipo di processo di manutenzione")</span><span class="sxs-lookup"><span data-stu-id="8a848-139">![Maintenance job type defaults button](media/am-guides-integration-job-defaults.png "Maintenance job type defaults button")</span></span>

    1. <span data-ttu-id="8a848-140">Creare una riga, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8a848-140">Create a line, and then select **Save**.</span></span>

        <span data-ttu-id="8a848-141">![Creare una riga](media/am-guides-integration-add-line.png "Creare una riga")</span><span class="sxs-lookup"><span data-stu-id="8a848-141">![Create a line](media/am-guides-integration-add-line.png "Create a line")</span></span>

    1. <span data-ttu-id="8a848-142">Nel riquadro azioni selezionare **Elenco di controllo di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="8a848-142">On the Action Pane, select **Maintenance checklist**.</span></span>

        <span data-ttu-id="8a848-143">![Pulsante Elenco di controllo di manutenzione](media/am-guides-integration-maintenance-checklist.png "Pulsante Elenco di controllo di manutenzione")</span><span class="sxs-lookup"><span data-stu-id="8a848-143">![Maintenance checklist button](media/am-guides-integration-maintenance-checklist.png "Maintenance checklist button")</span></span>

    1. <span data-ttu-id="8a848-144">Nella Scheda dettaglio **Righe elenco di controllo di manutenzione** aggiungere una riga e quindi modificare il valore del campo **Tipo** in **Modello**.</span><span class="sxs-lookup"><span data-stu-id="8a848-144">On the **Maintenance checklist lines** FastTab, add a line, and then change the value of the **Type** field to **Template**.</span></span>

        <span data-ttu-id="8a848-145">![Modificare il valore Tipo](media/am-guides-integration-checklist-lines.png "Modificare il valore Tipo")</span><span class="sxs-lookup"><span data-stu-id="8a848-145">![Change the Type value](media/am-guides-integration-checklist-lines.png "Change the Type value")</span></span>

    1. <span data-ttu-id="8a848-146">Nella Scheda dettaglio **Dettagli riga** selezionare nel campo **Modello** il modello a cui è stata associata la guida, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8a848-146">On the **Line details** FastTab, in the **Template** field, select the template that you associated the guide with, and then select **Save**.</span></span>

        <span data-ttu-id="8a848-147">![Selezionare il modello](media/am-guides-integration-checklist-line-details.png "Selezionare il modello")</span><span class="sxs-lookup"><span data-stu-id="8a848-147">![Select the template](media/am-guides-integration-checklist-line-details.png "Select the template")</span></span>

1. <span data-ttu-id="8a848-148">[Creare un ordine di lavoro](work-orders/manually-created-workorders.md#create-work-order), quindi selezionare il tipo di processo di manutenzione che utilizza il modello di elenco di controllo di manutenzione a cui è stata associata la guida.</span><span class="sxs-lookup"><span data-stu-id="8a848-148">[Create a work order](work-orders/manually-created-workorders.md#create-work-order), and then select the maintenance job type that uses the maintenance checklist template that you associated the guide with.</span></span> <span data-ttu-id="8a848-149">La guida viene automaticamente associata all'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a848-149">The guide is automatically associated with the work order.</span></span>

    <span data-ttu-id="8a848-150">![Selezionare un tipo di processo di manutenzione](media/am-guides-integration-create-work-order.png "Selezionare un tipo di processo di manutenzione")</span><span class="sxs-lookup"><span data-stu-id="8a848-150">![Select a maintenance job type](media/am-guides-integration-create-work-order.png "Select a maintenance job type")</span></span>

1. <span data-ttu-id="8a848-151">Visualizzare la guida associata all'ordine di lavoro e ai lavoratori.</span><span class="sxs-lookup"><span data-stu-id="8a848-151">View the guide that is associated with the work order and workers:</span></span>

    1. <span data-ttu-id="8a848-152">Aprire [Area di lavoro mobile di gestione cespiti](asset-management-mobile-workspace.md) per accedere all'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a848-152">Open the [Asset management mobile workspace](asset-management-mobile-workspace.md) to access the work order.</span></span>
    1. <span data-ttu-id="8a848-153">[Aprire l'elenco di controllo di manutenzione](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) per l'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a848-153">[Open the maintenance checklist](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) for the work order.</span></span>
    1. <span data-ttu-id="8a848-154">Selezionare una riga dell'elenco di controllo per visualizzare la guida associata.</span><span class="sxs-lookup"><span data-stu-id="8a848-154">Select a checklist line to see the associated guide.</span></span>

        <span data-ttu-id="8a848-155">![Guida associata a una riga dell'elenco di controllo](media/am-guides-integration-show-guide.png "Guida associata a una riga dell'elenco di controllo")</span><span class="sxs-lookup"><span data-stu-id="8a848-155">![Guide associated with a checklist line](media/am-guides-integration-show-guide.png "Guide associated with a checklist line")</span></span>

    1. <span data-ttu-id="8a848-156">Aprire la guida in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8a848-156">Open the guide on HoloLens.</span></span>

        <span data-ttu-id="8a848-157">![Aprire la guida in HoloLens](media/am-guides-integration-hololens-select.png "Aprire la guida in HoloLens")</span><span class="sxs-lookup"><span data-stu-id="8a848-157">![Open the guide on HoloLens](media/am-guides-integration-hololens-select.png "Open the guide on HoloLens")</span></span>

> [!NOTE]
> <span data-ttu-id="8a848-158">È inoltre possibile associare una guida direttamente all'elenco di controllo di manutenzione di un ordine di lavoro o di un tipo di processo.</span><span class="sxs-lookup"><span data-stu-id="8a848-158">You can also associate a guide directly in the maintenance checklist of a work order or a job type.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a848-159">Esiste un problema noto a causa del quale quando si associa un modello di elenco di controllo di manutenzione a un tipo di processo di manutenzione predefinito, la guida collegata al modello non viene visualizzata nella Scheda dettaglio **Guide associate** della pagina **Valori predefiniti per il tipo di processo di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="8a848-159">There is a known issue where, when you associate a maintenance checklist template with a default maintenance job type, the guide that is linked to the template doesn't appear on the **Associated guides** FastTab of the **Maintenance job type defaults** page.</span></span> <span data-ttu-id="8a848-160">La guida verrà tuttavia visualizzata dopo l'applicazione del tipo di processo a un ordine di lavoro nella Scheda dettaglio **Guide associate**.</span><span class="sxs-lookup"><span data-stu-id="8a848-160">However, the guide will appear after that job type is applied to a work order on the **Associated guides** FastTab.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a848-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a848-161">See also</span></span>

- [<span data-ttu-id="8a848-162">Panoramica della doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="8a848-162">Dual-write overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [<span data-ttu-id="8a848-163">Panoramica della gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="8a848-163">Asset management overview</span></span>](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]