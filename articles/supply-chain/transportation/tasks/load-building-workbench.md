---
title: Workbench di allestimento del carico
description: Questo argomento descrive come lavorare con il workbench allestimento del carico.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7b8633adbab43c95366d42cf409f5e508771c906
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809040"
---
# <a name="load-building-workbench"></a><span data-ttu-id="7f5b8-103">Workbench di allestimento del carico</span><span class="sxs-lookup"><span data-stu-id="7f5b8-103">Load building workbench</span></span>

<span data-ttu-id="7f5b8-104">Il workbench allestimento del carico consente di applicare strategie di allestimento del carico durante la creazione dei carichi.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-104">The load building workbench lets you apply load building strategies when you create loads.</span></span>

## <a name="create-a-load-building-strategy"></a><span data-ttu-id="7f5b8-105">Creare una strategia di allestimento del carico</span><span class="sxs-lookup"><span data-stu-id="7f5b8-105">Create a load building strategy</span></span>

<span data-ttu-id="7f5b8-106">Si utilizzano le strategie di allestimento del carico per allestire automaticamente i carichi.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-106">You use load building strategies to automatically build loads.</span></span> <span data-ttu-id="7f5b8-107">Questa capacità può essere utile nelle seguenti situazioni:</span><span class="sxs-lookup"><span data-stu-id="7f5b8-107">This capability can be beneficial in the following situations:</span></span>

- <span data-ttu-id="7f5b8-108">Se si spedisce regolarmente un set specifico di prodotti, le strategie di carico aiutano a risparmiare tempo, perché non si deve creare lo stesso carico ogni volta.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-108">If you regularly ship a specific set of products, load strategies help save time, because you don't have to build the same load every time.</span></span>
- <span data-ttu-id="7f5b8-109">Se si desidera evitare carichi mezzi pieni per massimizzare l'efficienza, le strategie di carico possono aiutare a riempire ogni carico il più possibile.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-109">If you want to avoid half-full loads to maximize efficiency, load strategies can help fill each load as much as possible.</span></span>

<span data-ttu-id="7f5b8-110">Una classe di strategia di allestimento del carico denominata `TMSLoadBuildingVolumeStrategy` fornisce una strategia di allestimento del carico denominata *Strategia di allestimento del carico basata sul volume*.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-110">A load building strategy class that is named `TMSLoadBuildingVolumeStrategy` provides a load building strategy that is named *Volume-based load building strategy*.</span></span> <span data-ttu-id="7f5b8-111">Questa strategia consente di utilizzare i valori massimi specificati per l'altezza e il peso nel modello di carico o di sostituire le impostazioni con nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-111">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="7f5b8-112">Questa strategia è l'unica strategia inclusa per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-112">This strategy is the only strategy that is included out of the box.</span></span> <span data-ttu-id="7f5b8-113">Tuttavia, è possibile avere strategie personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-113">(However, you might have some custom strategies.)</span></span>

<span data-ttu-id="7f5b8-114">Per utilizzare la *Strategia di allestimento del carico basata sul volume* predefinita selezionarla nel campo **Strategia di allestimento del carico** della pagina **Workbench di allestimento del carico** (**Gestione trasporto &gt; Pianificazione &gt; Workbench di allestimento del carico**).</span><span class="sxs-lookup"><span data-stu-id="7f5b8-114">To use the out-of-box *Volume-based load building strategy* strategy, select it in the **Load building strategy** field on the **Load building workbench** page (**Transportation management &gt; Planning &gt; Load building workbench**).</span></span>

<span data-ttu-id="7f5b8-115">Per creare una strategia di allestimento del carico, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-115">To create a load building strategy, follow these steps.</span></span>

1. <span data-ttu-id="7f5b8-116">Andare a **Gestione trasporti &gt; Impostazione &gt; Allestimento del carico &gt; Strategie di allestimento del carico**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-116">Go to **Transportation management &gt; Setup &gt; Load building &gt; Load building strategies**.</span></span>
1. <span data-ttu-id="7f5b8-117">Nel riquadro azioni selezionare **Genera elenco di classi** per assicurarsi di avere le ultime versioni di tutte le classi disponibili.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-117">On the Action Pane, select **Generate class list** to make sure that you have the latest versions of all available classes.</span></span>
1. <span data-ttu-id="7f5b8-118">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-118">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7f5b8-119">Immettere un nome univoco per la strategia, selezionare la classe della strategia di generazione del carico e immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-119">Enter a unique name for the strategy, select the load building strategy class for it, and enter a description.</span></span>
1. <span data-ttu-id="7f5b8-120">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-120">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="7f5b8-121">Nel riquadro azioni, seleziona **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-121">On the Action Pane, select **Parameters**.</span></span>
1. <span data-ttu-id="7f5b8-122">Nella pagina **Parametri strategia di allestimento del carico** selezionare **Capacità volume** nell'elenco e quindi nel campo **Valore** immettere la percentuale della capacità di volume totale del carico da applicare per la nuova strategia di allestimento del carico.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-122">On the **Load building strategy parameters** page, select **Volume capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total volume capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="7f5b8-123">Selezionare **Capacità peso** nell'elenco e quindi nel campo **Valore** immettere la percentuale della capacità di peso totale del carico da applicare per la nuova strategia di allestimento del carico.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-123">Select **Weight capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total weight capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="7f5b8-124">Chiudere la pagina **Parametri strategia di allestimento del carico**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-124">Close the **Load building strategy parameters** page.</span></span>
1. <span data-ttu-id="7f5b8-125">Chiudere la pagina **Strategie di allestimento del carico**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-125">Close the **Load building strategies** page.</span></span>

<span data-ttu-id="7f5b8-126">È ora possibile assegnare la strategia di allestimento del carico a un modello di allestimento del carico.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-126">You can now assign the load building strategy to a load building template.</span></span> <span data-ttu-id="7f5b8-127">In alternativa, è possibile utilizzarla direttamente nel workbench di allestimento del carico.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-127">Alternatively, you can use it directly in the load planning workbench.</span></span>

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a><span data-ttu-id="7f5b8-128">Utilizzare una strategia di allestimento del carico nel workbench di allestimento del carico</span><span class="sxs-lookup"><span data-stu-id="7f5b8-128">Use a load building strategy in the load building workbench</span></span>

1. <span data-ttu-id="7f5b8-129">Andare a **Gestione trasporto &gt; Pianificazione &gt; Workbench allestimento carico**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-129">Go to **Transportation management &gt; Planning &gt; Load building workbench**.</span></span>
1. <span data-ttu-id="7f5b8-130">Eseguire uno dei passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-130">Follow one of these steps:</span></span>

    - <span data-ttu-id="7f5b8-131">Selezionare una strategia nel campo **Strategia di allestimento del carico**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-131">Select a strategy in the **Load building strategy** field.</span></span>
    - <span data-ttu-id="7f5b8-132">Se è stato definito un modello di allestimento del carico e gli è stata assegnata la strategia di allestimento del carico, nel riquadro azioni, nella scheda **Gestisci modelli** selezionare **Applica modello**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-132">If you've defined a load building template and assigned the load building strategy to it, on the Action Pane, on the **Manage templates** tab, select **Apply template**.</span></span> <span data-ttu-id="7f5b8-133">Quindi, nella finestra di dialogo a discesa **Applica modello di allestimento del carico** selezionare un modello nel campo **Nome modello di allestimento del carico**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-133">Then, in the **Apply load building template** drop-down dialog box, select a template in the **Load building template name** field.</span></span>

1. <span data-ttu-id="7f5b8-134">Nella scheda dettaglio **Sequenza modelli di carico** selezionare uno o più [modelli di carico](load-template.md).</span><span class="sxs-lookup"><span data-stu-id="7f5b8-134">On the **Load templates sequence** FastTab, select one or more [load templates](load-template.md).</span></span> <span data-ttu-id="7f5b8-135">Il workbench cercherà di adattare il carico a questi tipi di contenitori, nella sequenza qui specificata.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-135">The workbench will try to fit the load into these types of containers, in the sequence that is specified here.</span></span> <span data-ttu-id="7f5b8-136">In genere, è necessario inserire i contenitori più piccoli all'inizio dell'elenco per assicurarsi che venga selezionato per primo il contenitore più piccolo possibile.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-136">Typically, you should put the smallest containers at the top of the list to ensure that the smallest possible container is selected first.</span></span>
1. <span data-ttu-id="7f5b8-137">Nel riquadro azioni selezionare **Proponi carichi**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-137">On the Action Pane, select **Propose loads**.</span></span>
1. <span data-ttu-id="7f5b8-138">Rivedere i carichi proposti e le righe di carico proposte.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-138">Review the proposed loads and proposed load lines.</span></span>
1. <span data-ttu-id="7f5b8-139">Nel riquadro azioni selezionare **Crea carichi** per creare carichi basati sulle righe del documento di origine nella scheda dettaglio **Righe carico proposte**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-139">On the Action Pane, select **Create loads** to create loads that are based on the source document lines on the **Proposed load lines** FastTab.</span></span>
1. <span data-ttu-id="7f5b8-140">Chiudere la pagina **Workbench di allestimento del carico**.</span><span class="sxs-lookup"><span data-stu-id="7f5b8-140">Close the **Load building workbench** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]