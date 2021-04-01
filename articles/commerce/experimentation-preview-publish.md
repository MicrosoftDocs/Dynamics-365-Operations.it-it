---
title: Visualizzare un esperimento in anteprima e pubblicarlo
description: In questo argomento viene descritto come visualizzare in anteprima e pubblicare un esperimento in Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7b35af35f5d0347192ed94bed51dfd2484cfa481
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238584"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="bc3a8-103">Visualizzare un esperimento in anteprima e pubblicarlo</span><span class="sxs-lookup"><span data-stu-id="bc3a8-103">Preview and publish an experiment</span></span>

<span data-ttu-id="bc3a8-104">Questo argomento descrive come visualizzare in anteprima e pubblicare un esperimento in Dynamics 365 Commerce dopo che hai [collegato l'esperimento e modificato le varianti](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="bc3a8-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="bc3a8-105">Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="bc3a8-106">I passaggi aggiuntivi sono esposti in argomenti separati.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="bc3a8-107">[ ![Percorso utente per sperimentazione - Anteprime e pubblicazione](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="bc3a8-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="bc3a8-108">Visualizzare un'anteprima delle varianti dell'esperimento</span><span class="sxs-lookup"><span data-stu-id="bc3a8-108">Preview your experiment variations</span></span>
<span data-ttu-id="bc3a8-109">Puoi visualizzare in anteprima le varianti e continuare a modificarle finché non hanno l'aspetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

<span data-ttu-id="bc3a8-110">Per visualizzare in anteprima le varianti dell'esperimento in Creazione di siti Web di Commerce seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-110">To preview your experiment variations in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="bc3a8-111">Nel menu a discesa delle varianti sotto la barra dei comandi selezionare il contenuto che si desidera visualizzare in anteprima.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-111">From the variations drop-down menu below the command bar, select the content you want to preview.</span></span> 
1. <span data-ttu-id="bc3a8-112">Nella barra dei comandi, selezionare **Anteprima**.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-112">On the command bar, select **Preview**.</span></span> <span data-ttu-id="bc3a8-113">Viene visualizzata un'anteprima di come apparirà il contenuto una volta pubblicato.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-113">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="bc3a8-114">Per visualizzare in anteprima una variante diversa, selezionarla dal menu a discesa delle varianti e selezionare di nuovo **Anteprima**.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-114">To preview a different variation, select it from the variation drop-down menu and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="bc3a8-115">Pubblicare l'esperimento</span><span class="sxs-lookup"><span data-stu-id="bc3a8-115">Publish your experiment</span></span>
<span data-ttu-id="bc3a8-116">Se non stai utilizzando un gruppo di pubblicazione per pianificare il momento in cui l'esperimento verrà pubblicato e desideri pubblicarlo immediatamente, seleziona **Pubblica** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-116">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="bc3a8-117">Verranno pubblicate tutte le varianti che appartengono all'esperimento.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-117">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="bc3a8-118">Se la pagina ha un URL non pubblicato, devi prima pubblicare l'URL o non sarà visibile agli utenti del tuo sito web.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-118">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="bc3a8-119">Per informazioni dettagliate, vedi [Salvare, visualizzare in anteprima e pubblicare una pagina](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="bc3a8-119">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="bc3a8-120">Utilizzare gruppi di pubblicazione per pianificare quando l'esperimento verrà pubblicato</span><span class="sxs-lookup"><span data-stu-id="bc3a8-120">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="bc3a8-121">Le varianti create in Creazione in siti Web possono essere pianificate per la pubblicazione utilizzando un gruppo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-121">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="bc3a8-122">All'interno di un gruppo di pubblicazione, è possibile collegare una pagina o un frammento all'esperimento selezionando **Esperimenti** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-122">Within a publish group, you can connect a page or fragment to your experiment by selecting **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="bc3a8-123">È possibile eseguire questa operazione anche selezionando **Pagine** o **Frammenti** e seguendo le istruzioni in [Connettere un esperimento e modificare le varianti](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="bc3a8-123">You can also do this by selecting **Pages** or **Fragments** and following the instructions in [Connect an experiment and edit variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="bc3a8-124">Per informazioni sui gruppi di pubblicazione, vedi [Utilizzare i gruppi di pubblicazione](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="bc3a8-124">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="bc3a8-125">Quando si utilizzano gruppi di pubblicazione con esperimenti, è necessario tenere presente alcune considerazioni importanti.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-125">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="bc3a8-126">Quando aggiungi una pagina o un frammento per la quale è in esecuzione un esperimento a un gruppo di pubblicazione, l'esperimento verrà rimosso dalla pagina o dal frammento nel gruppo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-126">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="bc3a8-127">Gli esperimenti collegati alle pagine di un sito live non sono disponibili per le pagine in gruppi di pubblicazione e viceversa.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-127">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="bc3a8-128">Allo stesso modo, le pagine per le quali sono in esecuzione esperimenti in un sito live non sono disponibili per altri esperimenti nei gruppi di pubblicazione e viceversa.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-128">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="bc3a8-129">Quando pubblichi o pianifichi un gruppo di pubblicazione, tutto il contenuto nel gruppo di pubblicazione viene pubblicato, indipendentemente dal fatto che esista un esperimento associato al gruppo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-129">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="bc3a8-130">Poiché un gruppo di pubblicazione continua a persistere dopo essere stato pubblicato su un sito live, verranno mantenuti anche gli esperimenti nel gruppo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-130">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="bc3a8-131">Pertanto, non potrai associare altri esperimenti alla stessa pagina o frammento.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-131">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="bc3a8-132">Per evitare questa limitazione, elimina tutti i gruppi di pubblicazione con esperimenti persistenti.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-132">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="bc3a8-133">Allo stesso modo, se desideri eliminare un esperimento in un sito live che esiste anche in un gruppo di pubblicazione, eliminalo prima dal gruppo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="bc3a8-133">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="bc3a8-134">Passaggio precedente</span><span class="sxs-lookup"><span data-stu-id="bc3a8-134">Previous step</span></span>
[<span data-ttu-id="bc3a8-135">Collegare e modificare un esperimento</span><span class="sxs-lookup"><span data-stu-id="bc3a8-135">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="bc3a8-136">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="bc3a8-136">Next step</span></span>
[<span data-ttu-id="bc3a8-137">Eseguire e monitorare un esperimento</span><span class="sxs-lookup"><span data-stu-id="bc3a8-137">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]