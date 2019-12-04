---
title: Introduzione all'ottimizzazione di pianificazione
description: Questo argomento illustra come iniziare a utilizzare la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 37c2acb2397b2a0ad69272c0645bd200a8d7910d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773987"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="f76e9-103">Introduzione all'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="f76e9-103">Get started with Planning Optimization</span></span>

<span data-ttu-id="f76e9-104">La funzionalità di ottimizzazione di pianificazione non supporta attualmente tutte le funzionalità disponibili nel motore di pianificazione incorporato in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f76e9-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="f76e9-105">Pertanto, è importante valutare se il set di funzionalità attualmente disponibile nell'ottimizzazione di pianificazione soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="f76e9-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="f76e9-106">Per impostazione predefinita, la funzionalità di ottimizzazione di pianificazione non è abilitata in Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f76e9-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="f76e9-107">Pertanto, è possibile effettuare la valutazione prima che venga attivata.</span><span class="sxs-lookup"><span data-stu-id="f76e9-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="f76e9-108">Alla fine, l'ottimizzazione di pianificazione sostituirà l'attuale motore di pianificazione integrato Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f76e9-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="f76e9-109">Prima di attivare l'ottimizzazione di pianificazione, si consiglia vivamente di valutare i risultati dell'analisi di adeguatezza dell'ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f76e9-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="f76e9-110">Per ulteriori informazioni, vedere [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="f76e9-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="f76e9-111">Licenze</span><span class="sxs-lookup"><span data-stu-id="f76e9-111">Licensing</span></span>

<span data-ttu-id="f76e9-112">Se è possibile eseguire la pianificazione generale utilizzando la licenza corrente, non è necessario acquistare una licenza aggiuntiva per iniziare a utilizzare l'ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f76e9-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="f76e9-113">Installare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="f76e9-113">Install the add-in</span></span>

<span data-ttu-id="f76e9-114">Per utilizzare l'ottimizzazione di pianificazione, installare il componente aggiuntivo Ottimizzazione di pianificazione per Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f76e9-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="f76e9-115">È possibile accedere al componente aggiuntivo dal progetto LCS e attivare la funzionalità di ottimizzazione di pianificazione dall'interfaccia utente (UI) di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f76e9-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

1. <span data-ttu-id="f76e9-116">Accedere a LCS e aprire l'ambiente desiderato.</span><span class="sxs-lookup"><span data-stu-id="f76e9-116">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="f76e9-117">Andare a **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="f76e9-117">Go to **Full details**.</span></span>
1. <span data-ttu-id="f76e9-118">Selezionare **Gestisci** oppure scorrere verso il basso la scheda dettaglio **Componenti aggiuntivi dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="f76e9-118">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="f76e9-119">Selezionare **Installare un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="f76e9-119">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="f76e9-120">Selezionare **Pianificazione di ottimizzazione**.</span><span class="sxs-lookup"><span data-stu-id="f76e9-120">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="f76e9-121">Seguire la guida all'installazione e accettare le condizioni.</span><span class="sxs-lookup"><span data-stu-id="f76e9-121">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="f76e9-122">Selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="f76e9-122">Select **Install**.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="f76e9-123">Integrazione di ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="f76e9-123">Planning Optimization integration</span></span>

<span data-ttu-id="f76e9-124">Per configurare se il componente aggiuntivo di ottimizzazione di pianificazione deve essere utilizzato per la pianificazione generale, andare a **Pianificazione generale** \> **Impostazione** \> **Integrazione di ottimizzazione di pianificazione** \> **Parametri di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="f76e9-124">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization integration** \> **Integration parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="f76e9-125">Stato connessione</span><span class="sxs-lookup"><span data-stu-id="f76e9-125">Connection status</span></span>

<span data-ttu-id="f76e9-126">Lo stato della connessione indica lo stato corrente della connessione tra Supply Chain Management e il servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f76e9-126">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="f76e9-127">Nella seguente tabella vengono illustrati i possibili valori.</span><span class="sxs-lookup"><span data-stu-id="f76e9-127">The following table shows the possible values.</span></span>

| <span data-ttu-id="f76e9-128">Stato connessione</span><span class="sxs-lookup"><span data-stu-id="f76e9-128">Connection status</span></span> | <span data-ttu-id="f76e9-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f76e9-129">Description</span></span> | <span data-ttu-id="f76e9-130">Può l'ottimizzazione di pianificazione essere utilizzata?</span><span class="sxs-lookup"><span data-stu-id="f76e9-130">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="f76e9-131">Connesso</span><span class="sxs-lookup"><span data-stu-id="f76e9-131">Connected</span></span> | <span data-ttu-id="f76e9-132">È stata stabilita una connessione tra il servizio di ottimizzazione di pianificazione e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f76e9-132">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="f76e9-133">Sì</span><span class="sxs-lookup"><span data-stu-id="f76e9-133">Yes</span></span> |
| <span data-ttu-id="f76e9-134">Abilitazione connessione</span><span class="sxs-lookup"><span data-stu-id="f76e9-134">Enabling connection</span></span> | <span data-ttu-id="f76e9-135">È attualmente in corso una richiesta di attivazione della connessione al servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f76e9-135">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="f76e9-136">Nessuno</span><span class="sxs-lookup"><span data-stu-id="f76e9-136">No</span></span> |
| <span data-ttu-id="f76e9-137">Disconnesso</span><span class="sxs-lookup"><span data-stu-id="f76e9-137">Disconnected</span></span> | <span data-ttu-id="f76e9-138">Non esiste alcuna connessione al servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f76e9-138">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="f76e9-139">La connessione può essere attivata da LCS, come descritto in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f76e9-139">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="f76e9-140">Nessuno</span><span class="sxs-lookup"><span data-stu-id="f76e9-140">No</span></span> |
| <span data-ttu-id="f76e9-141">Disabilitazione della connessione</span><span class="sxs-lookup"><span data-stu-id="f76e9-141">Disabling connection</span></span> | <span data-ttu-id="f76e9-142">È attualmente in corso una richiesta di disattivazione della connessione al servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f76e9-142">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="f76e9-143">Nessuno</span><span class="sxs-lookup"><span data-stu-id="f76e9-143">No</span></span> |
| <span data-ttu-id="f76e9-144">Recupero stato</span><span class="sxs-lookup"><span data-stu-id="f76e9-144">Getting status</span></span> | <span data-ttu-id="f76e9-145">Il sistema è in attesa delle informazioni sullo stato dal servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f76e9-145">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="f76e9-146">Nessuno</span><span class="sxs-lookup"><span data-stu-id="f76e9-146">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="f76e9-147">L'opzione Usa ottimizzazione di progettazione</span><span class="sxs-lookup"><span data-stu-id="f76e9-147">The Use Planning Optimization option</span></span>

<span data-ttu-id="f76e9-148">L'impostazione dell'opzione **Usa ottimizzazione di pianificazione** determina il motore di pianificazione utilizzato per la pianificazione generale:</span><span class="sxs-lookup"><span data-stu-id="f76e9-148">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="f76e9-149">**Sì** - L'ottimizzazione di pianificazione viene utilizzata per la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="f76e9-149">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="f76e9-150">**No** - Il motore di pianificazione incorporato Supply Chain Management viene utilizzato per la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="f76e9-150">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="f76e9-151">Se vengono attivati processi batch di pianificazione esistenti creati per il motore di pianificazione integrato Supply Chain Management mentre l'opzione **Usa ottimizzazione di pianificazione** è impostata su **Sì**, i processi verranno completati.</span><span class="sxs-lookup"><span data-stu-id="f76e9-151">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="f76e9-152">Integrazione con l'impostazione</span><span class="sxs-lookup"><span data-stu-id="f76e9-152">Integration with the setup</span></span>

<span data-ttu-id="f76e9-153">Se l'anteprima di ottimizzazione di pianificazione è attivata, la pianificazione generale viene eseguita utilizzando il componente aggiuntivo ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f76e9-153">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="f76e9-154">In questo caso, i risultati e le funzionalità della pianificazione generale sono interessati.</span><span class="sxs-lookup"><span data-stu-id="f76e9-154">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="f76e9-155">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="f76e9-155">Related resources</span></span>

[<span data-ttu-id="f76e9-156">Condizioni per l'anteprima</span><span class="sxs-lookup"><span data-stu-id="f76e9-156">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="f76e9-157">Panoramica dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="f76e9-157">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="f76e9-158">Analisi di adeguatezza dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="f76e9-158">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="f76e9-159">Visualizzare la cronologia del piano e i log di pianificazione</span><span class="sxs-lookup"><span data-stu-id="f76e9-159">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="f76e9-160">Applicare i filtri a un piano</span><span class="sxs-lookup"><span data-stu-id="f76e9-160">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="f76e9-161">Annullare un processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="f76e9-161">Cancel a planning job</span></span>](cancel-planning-job.md)
