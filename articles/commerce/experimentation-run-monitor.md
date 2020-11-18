---
title: Eseguire e monitorare un esperimento
description: In questo argomento viene descritto come eseguire e monitorare un esperimento in un servizio di terze parti. Descrive inoltre come apportare modifiche alle varianti dopo l'inizio dell'esperimento.
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
ms.openlocfilehash: ee86a6761b27f3c08a65a2e250659cdcfd71db44
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097024"
---
# <a name="run-and-monitor-an-experiment"></a><span data-ttu-id="55ca2-104">Eseguire e monitorare un esperimento</span><span class="sxs-lookup"><span data-stu-id="55ca2-104">Run and monitor an experiment</span></span>

<span data-ttu-id="55ca2-105">In questo argomento viene descritto come eseguire e monitorare un esperimento in un app di terze parti e modificare le variazioni se necessario.</span><span class="sxs-lookup"><span data-stu-id="55ca2-105">This topic describes how to run and monitor your experiment in a third-party app, and change variations if needed.</span></span> <span data-ttu-id="55ca2-106">Prima di completare i passaggi in questo argomento, è necessario [pubblicare](experimentation-preview-publish.md) l'esperimento in Commerce.</span><span class="sxs-lookup"><span data-stu-id="55ca2-106">Before you complete the steps in this topic, you'll first need to [publish](experimentation-preview-publish.md) your experiment in Commerce.</span></span> 

<span data-ttu-id="55ca2-107">Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55ca2-107">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="55ca2-108">I passaggi aggiuntivi sono esposti in argomenti separati.</span><span class="sxs-lookup"><span data-stu-id="55ca2-108">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="55ca2-109">[ ![Percorso utente per sperimentazione - Esecuzione e monitoraggio](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="55ca2-109">[ ![Experimentation user journey - Run & Monitor](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span></span>

<span data-ttu-id="55ca2-110">Dopo aver pubblicato le varianti, vengono eseguiti tutti i passaggi necessari in Commerce per completare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="55ca2-110">After you publish your variations, all of the steps you need to do in Commerce to run your experiment are complete.</span></span> <span data-ttu-id="55ca2-111">Il passaggio successivo consiste nel determinare quale variante mostrare agli utenti quando richiedono una pagina.</span><span class="sxs-lookup"><span data-stu-id="55ca2-111">The next step is determining which variation to show to each user when they request a page.</span></span> <span data-ttu-id="55ca2-112">Il servizio di terze parti prende questa decisione, ma prima devi attivare l'esperimento nel servizio.</span><span class="sxs-lookup"><span data-stu-id="55ca2-112">The third-party service makes that determination, but first you have to activate the experiment within the service.</span></span> <span data-ttu-id="55ca2-113">Poiché i passaggi per l'attivazione di un esperimento variano da servizio a servizio, dovrai seguire le istruzioni fornite dal servizio o dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="55ca2-113">Since the steps for activating an experiment vary from service to service, you'll need to follow the instructions included with your service or provider.</span></span> <span data-ttu-id="55ca2-114">Se l'esperimento non viene attivato, gli utenti vedranno solo la versione predefinita della pagina e non verranno visualizzate le varianti.</span><span class="sxs-lookup"><span data-stu-id="55ca2-114">If the experiment is not activated, users will only see the default version of the page (no variations will be displayed).</span></span>

<span data-ttu-id="55ca2-115">Dovrai continuare a eseguire l'esperimento per un periodo sufficiente per raccogliere dati per risultati statisticamente validi.</span><span class="sxs-lookup"><span data-stu-id="55ca2-115">You'll need to keep the experiment running long enough to gather data for statistically valid results.</span></span> <span data-ttu-id="55ca2-116">Utilizza il servizio di terze parti per monitorare i dati e le analisi relativi all'esperimento mentre l'esperimento è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="55ca2-116">Use the third-party service to monitor the experiment-related data and analytics while the experiment is running.</span></span>

## <a name="adjust-your-variations"></a><span data-ttu-id="55ca2-117">Regolare le varianti</span><span class="sxs-lookup"><span data-stu-id="55ca2-117">Adjust your variations</span></span>
<span data-ttu-id="55ca2-118">Se per un qualsiasi motivo devi modificare le varianti, segui i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="55ca2-118">If for any reason you need to modify your variations, follow the steps below.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55ca2-119">Se apporti modifiche a un esperimento live in Commerce o nel servizio di terze parti, i risultati potrebbero essere modificati in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="55ca2-119">If you make changes to a live experiment in Commerce or the third-party service, your results may be significantly impacted.</span></span> <span data-ttu-id="55ca2-120">Valuta la possibilità di completare l'esperimento e quindi di creare un nuovo esperimento per le modifiche più importanti.</span><span class="sxs-lookup"><span data-stu-id="55ca2-120">Consider letting the experiment run its course and then creating a new experiment for major changes.</span></span>

1. <span data-ttu-id="55ca2-121">In Creazione di siti Web di Commerce selezionare **Esperimenti** nel riquadro di spostamento a sinistra e selezionare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="55ca2-121">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
1. <span data-ttu-id="55ca2-122">Seleziona la variante che desideri aggiornare dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="55ca2-122">Select the variation you want to update from the drop-down menu.</span></span>
1. <span data-ttu-id="55ca2-123">Apportare le modifiche necessarie e visualizzare l'anteprima delle varianti e pubblicarle.</span><span class="sxs-lookup"><span data-stu-id="55ca2-123">Make any needed changes, and then preview and publish the variations.</span></span> <span data-ttu-id="55ca2-124">Per ulteriori informazioni, vedi [Visualizzare un esperimento in anteprima e pubblicarlo](experimentation-preview-publish.md).</span><span class="sxs-lookup"><span data-stu-id="55ca2-124">For more information, see [Preview and publish an experiment](experimentation-preview-publish.md).</span></span>
1. <span data-ttu-id="55ca2-125">Vai al servizio di terze parti per apportare eventuali modifiche relative alla configurazione dell'esperimento.</span><span class="sxs-lookup"><span data-stu-id="55ca2-125">Go to the third-party service to make any experiment setup-related changes.</span></span>
    
## <a name="previous-step"></a><span data-ttu-id="55ca2-126">Passaggio precedente</span><span class="sxs-lookup"><span data-stu-id="55ca2-126">Previous step</span></span>
[<span data-ttu-id="55ca2-127">Visualizzare un esperimento in anteprima e pubblicarlo</span><span class="sxs-lookup"><span data-stu-id="55ca2-127">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)

## <a name="next-step"></a><span data-ttu-id="55ca2-128">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="55ca2-128">Next step</span></span>
[<span data-ttu-id="55ca2-129">Promuovere una variante e completare un esperimento</span><span class="sxs-lookup"><span data-stu-id="55ca2-129">Promote a variation and complete an experiment</span></span>](experimentation-review-complete.md)