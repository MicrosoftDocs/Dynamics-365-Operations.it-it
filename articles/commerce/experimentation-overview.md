---
title: Sperimentazione in Dynamics 365 Commerce
description: La sperimentazione consente la creazione, la modifica e la gestione dei layout di pagina e dei trattamenti di contenuti in Creazione di siti Web. Il supporto per la sperimentazione end-to-end è abilitato per le pagine e le entità di e-commerce in una pagina.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 85eb7a661cc66c42699797cca4fa6820941de7c0
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097141"
---
# <a name="experimentation-in-dynamics-365-commerce"></a><span data-ttu-id="4e827-104">Sperimentazione in Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="4e827-104">Experimentation in Dynamics 365 Commerce</span></span>
<span data-ttu-id="4e827-105">Usa la sperimentazione in Dynamics 365 Commerce per convalidare ipotesi sull'efficacia delle pagine di e-commerce e prendere decisioni con fiducia in base ai dati.</span><span class="sxs-lookup"><span data-stu-id="4e827-105">Use experimentation in Dynamics 365 Commerce to validate hypotheses about the effectiveness of your e-Commerce pages and make decisions with data-driven confidence.</span></span> <span data-ttu-id="4e827-106">Commerce supporta i test A/B su pagine, moduli e frammenti e ti consente di misurare l'impatto delle modifiche proposte sul tuo sito web.</span><span class="sxs-lookup"><span data-stu-id="4e827-106">Commerce supports A/B testing on pages, modules, and fragments and enables you to measure the impact of proposed changes to your website.</span></span>

<span data-ttu-id="4e827-107">È possibile creare, modificare e gestire trattamenti di pagine e contenuti noti come **varianti** in Creazione di siti Web di Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e827-107">You can create, edit, and manage page and content treatments known as **variations** in Commerce site builder.</span></span> <span data-ttu-id="4e827-108">Commerce si integra con servizi di terze parti che puoi utilizzare per creare esperimenti e assegnazioni di trattamenti.</span><span class="sxs-lookup"><span data-stu-id="4e827-108">Commerce integrates with third-party services that you can use to create experiments and treatment assignments.</span></span> <span data-ttu-id="4e827-109">I flussi di eventi in tempo reale acquisiti in Commerce abilitano l'analisi che definisce i risultati dell'esperimento nel servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="4e827-109">Real-time event streams captured in Commerce enable the analytics that define the experiment results in the third-party service.</span></span> <span data-ttu-id="4e827-110">Puoi quindi utilizzare queste analisi per supportare o confutare la tua ipotesi.</span><span class="sxs-lookup"><span data-stu-id="4e827-110">You can then leverage these analytics to help support or refute your hypothesis.</span></span>

## <a name="set-up-prerequisites"></a><span data-ttu-id="4e827-111"> Prerequisiti per l'impostazione</span><span class="sxs-lookup"><span data-stu-id="4e827-111">Set up prerequisites</span></span>
1. <span data-ttu-id="4e827-112">**Ottenere la versione corretta di Commerce** - Aggiornare la libreria dei moduli, il kit SDK per l'estendibilità del canale online e Commerce Scale Unit a Commerce versione 10.0.13 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="4e827-112">**Get the correct version of Commerce** - Upgrade your module library, online channel extensibility software development kit (SDK), and Commerce Scale Unit to Commerce version 10.0.13 or later.</span></span>
1. <span data-ttu-id="4e827-113">**Configurare un connettore di sperimentazione** - Un connettore di sperimentazione consente a Commerce di connettersi a servizi di terze parti per recuperare l'elenco di esperimenti e determinare quando mostrare un esperimento a un utente.</span><span class="sxs-lookup"><span data-stu-id="4e827-113">**Set up an experimentation connector** - An experimentation connector allows Commerce to connect with third-party services to retrieve the list of experiments and determine when to show an experiment to a user.</span></span> <span data-ttu-id="4e827-114">Puoi acquistare un connettore di terze parti in [AppSource](https://appsource.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4e827-114">You can purchase a third-party connector from [AppSource](https://appsource.microsoft.com).</span></span> <span data-ttu-id="4e827-115">Segui le istruzioni di configurazione fornite dall'editore.</span><span class="sxs-lookup"><span data-stu-id="4e827-115">Follow the setup instructions provided by the publisher.</span></span> <span data-ttu-id="4e827-116">In alternativa, puoi utilizzare il connettore di prova di esempio di Commerce per testare il flusso di lavoro di sperimentazione senza dover configurare un servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="4e827-116">You can alternatively use the sample test connector from Commerce to test the experimentation workflow without needing to configure an external service.</span></span> <span data-ttu-id="4e827-117">Per ulteriori informazioni, vedi [Configurare e abilitare i connettori](e-commerce-extensibility/connectors.md).</span><span class="sxs-lookup"><span data-stu-id="4e827-117">For more information, see [Configure and enable connectors](e-commerce-extensibility/connectors.md).</span></span> 
1. <span data-ttu-id="4e827-118">**Attivare i flag della funzionalità di sperimentazione in Commerce** - Puoi abilitare la sperimentazione a livello di tenant o di sito selezionando rispettivamente **Impostazioni tenant > Funzionalità** o **Impostazioni sito > Funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="4e827-118">**Turn on the experimentation feature flags in Commerce** - You can enable experimentation at the tenant level by going to **Tenant Settings > Features** or at the site level at **Site Settings > Features**.</span></span>
    - <span data-ttu-id="4e827-119">Abilita il flag **Sperimentazione** per creare varianti dell'esperimento dei moduli in una pagina senza alterare o copiare altri contenuti che non fanno parte dell'esperimento.</span><span class="sxs-lookup"><span data-stu-id="4e827-119">Enable the **Experimentation** flag to create experiment variations of modules within a page without affecting or copying other content that isn't part of the experiment.</span></span> <span data-ttu-id="4e827-120">Ciò garantisce che gli aggiornamenti in corso dei contenuti al di fuori dell'esperimento rimangano sincronizzati durante il ciclo di vita dell'esperimento.</span><span class="sxs-lookup"><span data-stu-id="4e827-120">This ensures that ongoing content updates outside the experiment stay in sync during the experiment lifecycle.</span></span> <span data-ttu-id="4e827-121">La disabilitazione di questo flag impedisce agli utenti di vedere tutti gli esperimenti e rimuove tutte le funzioni di modifica in Creazione di siti Web.</span><span class="sxs-lookup"><span data-stu-id="4e827-121">Disabling this flag stops all experiments from being shown to users and removes all editing functions within site builder.</span></span>
    - <span data-ttu-id="4e827-122">Abilita il flag **Sperimenta su pagine o frammenti** per eseguire esperimenti su una pagina o un frammento.</span><span class="sxs-lookup"><span data-stu-id="4e827-122">Enable the **Experiment on pages or fragments** flag to run experiments on a page or fragment.</span></span> <span data-ttu-id="4e827-123">In questo modo, viene creata una copia completa dell'istanza dell'intera pagina o frammento per tutti i moduli nella pagina o nel frammento.</span><span class="sxs-lookup"><span data-stu-id="4e827-123">This creates a full instance copy of the entire page or fragment for all modules within the page or fragment.</span></span> <span data-ttu-id="4e827-124">Utilizza questa modalità quando desideri testare modifiche complete al contenuto o quando la sincronizzazione delle modifiche in corso al contenuto nelle istanze non è un problema.</span><span class="sxs-lookup"><span data-stu-id="4e827-124">Use this mode when you want to test comprehensive content changes, or where synchronizing ongoing content changes across instances isn't a concern.</span></span> <span data-ttu-id="4e827-125">La disabilitazione di questo flag impedisce la creazione e la modifica di nuovi esperimenti su pagine e frammenti.</span><span class="sxs-lookup"><span data-stu-id="4e827-125">Disabling this flag prevents creation and editing of new experiments on pages and fragments.</span></span>
    > [!NOTE]
    > <span data-ttu-id="4e827-126">Il flag **Sperimentazione** deve essere abilitato anche per la funzionalità **Sperimenta su pagine o frammenti** per funzionare.</span><span class="sxs-lookup"><span data-stu-id="4e827-126">The **Experimentation** flag must also be enabled for the **Experiment on pages or fragments** functionality to work.</span></span>
    
## <a name="experimentation-lifecycle"></a><span data-ttu-id="4e827-127">Ciclo di vita della sperimentazione</span><span class="sxs-lookup"><span data-stu-id="4e827-127">Experimentation lifecycle</span></span>
<span data-ttu-id="4e827-128">L'impostazione di un esperimento, la creazione di varianti e l'esecuzione di un esperimento è un processo iterativo.</span><span class="sxs-lookup"><span data-stu-id="4e827-128">Setting up an experiment, creating variations, and running an experiment is an iterative process.</span></span> <span data-ttu-id="4e827-129">Il diagramma seguente illustra il ciclo di vita della sperimentazione in Commerce e nel servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="4e827-129">The diagram below illustrates the experimentation lifecycle in Commerce and the third-party service.</span></span> 

<span data-ttu-id="4e827-130">[ ![Ciclo di vita della sperimentazione](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="4e827-130">[ ![Experimentation lifecycle](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)</span></span>

<span data-ttu-id="4e827-131">Per ulteriori informazioni su ciascun passaggio del processo di sperimentazione, fai riferimento ai seguenti argomenti.</span><span class="sxs-lookup"><span data-stu-id="4e827-131">To learn more about each step in the experimentation process, refer to the following topics.</span></span>
- [<span data-ttu-id="4e827-132">Identificare un'ipotesi e determina le metriche per un esperimento</span><span class="sxs-lookup"><span data-stu-id="4e827-132">Identify a hypothesis and determine metrics for an experiment</span></span>](experimentation-identify.md)
- [<span data-ttu-id="4e827-133">Configurare un esperimento</span><span class="sxs-lookup"><span data-stu-id="4e827-133">Set up an experiment</span></span>](experimentation-setup.md)
- [<span data-ttu-id="4e827-134">Connettere e modificare un esperimento</span><span class="sxs-lookup"><span data-stu-id="4e827-134">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)
- [<span data-ttu-id="4e827-135">Visualizzare in anteprima e pubblicare un esperimento</span><span class="sxs-lookup"><span data-stu-id="4e827-135">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)
- [<span data-ttu-id="4e827-136">Eseguire e monitorare un esperimento</span><span class="sxs-lookup"><span data-stu-id="4e827-136">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
- [<span data-ttu-id="4e827-137">Promuovere una variazione e completare un esperimento</span><span class="sxs-lookup"><span data-stu-id="4e827-137">Promote a variation and complete an experiment</span></span>](experimentation-review-complete.md)

> [!NOTE]
> <span data-ttu-id="4e827-138">Per sapere dove si trova un esperimento nel ciclo di vita, selezionare **Esperimenti** nel riquadro di spostamento a sinistra in Creazione di siti Web.</span><span class="sxs-lookup"><span data-stu-id="4e827-138">To learn where an experiment is in the lifecycle, select **Experiments** in the left navigation pane of site builder.</span></span> <span data-ttu-id="4e827-139">Viene visualizzato un elenco di esperimenti con lo stato di ogni esperimento sia in Commerce che nel servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="4e827-139">A list of experiments is displayed with the status of each experiment in both Commerce and the third-party service.</span></span> <span data-ttu-id="4e827-140">Per ulteriori informazioni, vedi [Esaminare lo stato di un esperimento](experimentation-status.md).</span><span class="sxs-lookup"><span data-stu-id="4e827-140">For more information, see [Review the status of an experiment](experimentation-status.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="4e827-141">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="4e827-141">Next step</span></span>
[<span data-ttu-id="4e827-142">Identificare un'ipotesi e determinare le metriche per un esperimento</span><span class="sxs-lookup"><span data-stu-id="4e827-142">Identify a hypothesis and determine success metrics for an experiment</span></span>](experimentation-identify.md) 