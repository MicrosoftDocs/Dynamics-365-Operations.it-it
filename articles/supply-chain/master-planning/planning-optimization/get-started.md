---
title: Introduzione all'ottimizzazione di pianificazione
description: Questo argomento illustra come iniziare a utilizzare la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: AnnBe
ms.date: 02/10/2020
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
ms.openlocfilehash: 3e64699005387adcc92e2e7c9fefad68a9de85c0
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076134"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="735e6-103">Introduzione all'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="735e6-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="735e6-104">La funzionalità di ottimizzazione di pianificazione non supporta attualmente tutte le funzionalità disponibili nel motore di pianificazione incorporato in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="735e6-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="735e6-105">Pertanto, è importante valutare se il set di funzionalità attualmente disponibile nell'ottimizzazione di pianificazione soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="735e6-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="735e6-106">Per impostazione predefinita, la funzionalità di ottimizzazione di pianificazione non è abilitata in Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="735e6-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="735e6-107">Pertanto, è possibile effettuare la valutazione prima che venga attivata.</span><span class="sxs-lookup"><span data-stu-id="735e6-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="735e6-108">Alla fine, l'ottimizzazione di pianificazione sostituirà l'attuale motore di pianificazione integrato Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="735e6-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="735e6-109">Prima di attivare l'ottimizzazione di pianificazione, si consiglia vivamente di valutare i risultati dell'analisi di adeguatezza dell'ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="735e6-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="735e6-110">Per ulteriori informazioni, vedere [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="735e6-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="735e6-111">Licenze</span><span class="sxs-lookup"><span data-stu-id="735e6-111">Licensing</span></span>

<span data-ttu-id="735e6-112">Se è possibile eseguire la pianificazione generale utilizzando la licenza corrente, non è necessario acquistare una licenza aggiuntiva per iniziare a utilizzare l'ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="735e6-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="735e6-113">Installare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="735e6-113">Install the add-in</span></span>

<span data-ttu-id="735e6-114">Per utilizzare l'ottimizzazione di pianificazione, installare il componente aggiuntivo Ottimizzazione di pianificazione per Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="735e6-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="735e6-115">È possibile accedere al componente aggiuntivo dal progetto LCS e attivare la funzionalità di ottimizzazione di pianificazione dall'interfaccia utente (UI) di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="735e6-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="735e6-116">Il requisito per l'ottimizzazione della pianificazione è un ambiente ad alta disponibilità abilitato per LCS (non un ambiente OneBox), con Dynamics 365 Supply Chain Management versione 10.0.7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="735e6-116">The requirement for Planning Optimization is an LCS enabled high-availability environment (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span>

1. <span data-ttu-id="735e6-117">Accedere a LCS e aprire l'ambiente desiderato.</span><span class="sxs-lookup"><span data-stu-id="735e6-117">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="735e6-118">Andare a **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="735e6-118">Go to **Full details**.</span></span>
1. <span data-ttu-id="735e6-119">Scorrere verso il basso fino alla scheda dettaglio **Componenti aggiuntivi dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="735e6-119">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="735e6-120">Selezionare **Installare un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="735e6-120">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="735e6-121">Selezionare **Pianificazione di ottimizzazione**.</span><span class="sxs-lookup"><span data-stu-id="735e6-121">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="735e6-122">Seguire la guida all'installazione e accettare le condizioni.</span><span class="sxs-lookup"><span data-stu-id="735e6-122">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="735e6-123">Selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="735e6-123">Select **Install**.</span></span>
1. <span data-ttu-id="735e6-124">Nella scheda dettaglio **Componenti aggiuntivi dell'ambiente** dovrebbe essere visualizzato che Ottimizzazione pianificazione è in fase di installazione.</span><span class="sxs-lookup"><span data-stu-id="735e6-124">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="735e6-125">Dopo pochi minuti **Installazione in corso** dovrebbe cambiare in **Installato** (è possibile che sia necessario aggiornare la pagina).</span><span class="sxs-lookup"><span data-stu-id="735e6-125">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="735e6-126">Una volta installato, è possibile attivare Ottimizzazione pianificazione in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="735e6-126">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="735e6-127">Integrazione di ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="735e6-127">Planning Optimization integration</span></span>

<span data-ttu-id="735e6-128">Per configurare se il componente aggiuntivo Ottimizzazione pianificazione deve essere utilizzato per la pianificazione generale, andare a **Pianificazione generale** \> **Impostazione** \> **Parametri di Ottimizzazione pianificazione**.</span><span class="sxs-lookup"><span data-stu-id="735e6-128">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="735e6-129">Stato connessione</span><span class="sxs-lookup"><span data-stu-id="735e6-129">Connection status</span></span>

<span data-ttu-id="735e6-130">Lo stato della connessione indica lo stato corrente della connessione tra Supply Chain Management e il servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="735e6-130">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="735e6-131">Nella seguente tabella vengono illustrati i possibili valori.</span><span class="sxs-lookup"><span data-stu-id="735e6-131">The following table shows the possible values.</span></span>

| <span data-ttu-id="735e6-132">Stato connessione</span><span class="sxs-lookup"><span data-stu-id="735e6-132">Connection status</span></span> | <span data-ttu-id="735e6-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="735e6-133">Description</span></span> | <span data-ttu-id="735e6-134">Può l'ottimizzazione di pianificazione essere utilizzata?</span><span class="sxs-lookup"><span data-stu-id="735e6-134">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="735e6-135">Connesso</span><span class="sxs-lookup"><span data-stu-id="735e6-135">Connected</span></span> | <span data-ttu-id="735e6-136">È stata stabilita una connessione tra il servizio di ottimizzazione di pianificazione e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="735e6-136">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="735e6-137">Sì</span><span class="sxs-lookup"><span data-stu-id="735e6-137">Yes</span></span> |
| <span data-ttu-id="735e6-138">Abilitazione connessione</span><span class="sxs-lookup"><span data-stu-id="735e6-138">Enabling connection</span></span> | <span data-ttu-id="735e6-139">È attualmente in corso una richiesta di attivazione della connessione al servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="735e6-139">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="735e6-140">Nessuno</span><span class="sxs-lookup"><span data-stu-id="735e6-140">No</span></span> |
| <span data-ttu-id="735e6-141">Disconnesso</span><span class="sxs-lookup"><span data-stu-id="735e6-141">Disconnected</span></span> | <span data-ttu-id="735e6-142">Non esiste alcuna connessione al servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="735e6-142">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="735e6-143">La connessione può essere attivata da LCS, come descritto in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="735e6-143">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="735e6-144">Nessuno</span><span class="sxs-lookup"><span data-stu-id="735e6-144">No</span></span> |
| <span data-ttu-id="735e6-145">Disabilitazione della connessione</span><span class="sxs-lookup"><span data-stu-id="735e6-145">Disabling connection</span></span> | <span data-ttu-id="735e6-146">È attualmente in corso una richiesta di disattivazione della connessione al servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="735e6-146">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="735e6-147">Nessuno</span><span class="sxs-lookup"><span data-stu-id="735e6-147">No</span></span> |
| <span data-ttu-id="735e6-148">Recupero stato</span><span class="sxs-lookup"><span data-stu-id="735e6-148">Getting status</span></span> | <span data-ttu-id="735e6-149">Il sistema è in attesa delle informazioni sullo stato dal servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="735e6-149">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="735e6-150">Nessuno</span><span class="sxs-lookup"><span data-stu-id="735e6-150">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="735e6-151">L'opzione Usa ottimizzazione di progettazione</span><span class="sxs-lookup"><span data-stu-id="735e6-151">The Use Planning Optimization option</span></span>

<span data-ttu-id="735e6-152">L'impostazione dell'opzione **Usa ottimizzazione di pianificazione** determina il motore di pianificazione utilizzato per la pianificazione generale:</span><span class="sxs-lookup"><span data-stu-id="735e6-152">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="735e6-153">**Sì** - L'ottimizzazione di pianificazione viene utilizzata per la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="735e6-153">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="735e6-154">**No** - Il motore di pianificazione incorporato Supply Chain Management viene utilizzato per la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="735e6-154">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="735e6-155">Se vengono attivati processi batch di pianificazione esistenti creati per il motore di pianificazione integrato Supply Chain Management mentre l'opzione **Usa ottimizzazione di pianificazione** è impostata su **Sì**, i processi verranno completati.</span><span class="sxs-lookup"><span data-stu-id="735e6-155">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="735e6-156">Integrazione con l'impostazione</span><span class="sxs-lookup"><span data-stu-id="735e6-156">Integration with the setup</span></span>

<span data-ttu-id="735e6-157">Se l'anteprima di ottimizzazione di pianificazione è attivata, la pianificazione generale viene eseguita utilizzando il componente aggiuntivo ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="735e6-157">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="735e6-158">In questo caso, i risultati e le funzionalità della pianificazione generale sono interessati.</span><span class="sxs-lookup"><span data-stu-id="735e6-158">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="735e6-159">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="735e6-159">Related resources</span></span>

[<span data-ttu-id="735e6-160">Condizioni per l'anteprima</span><span class="sxs-lookup"><span data-stu-id="735e6-160">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="735e6-161">Panoramica dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="735e6-161">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="735e6-162">Analisi di adeguatezza dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="735e6-162">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="735e6-163">Visualizzare la cronologia del piano e i log di pianificazione</span><span class="sxs-lookup"><span data-stu-id="735e6-163">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="735e6-164">Applicare i filtri a un piano</span><span class="sxs-lookup"><span data-stu-id="735e6-164">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="735e6-165">Annullare un processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="735e6-165">Cancel a planning job</span></span>](cancel-planning-job.md)
