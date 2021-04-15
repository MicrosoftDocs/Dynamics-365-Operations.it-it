---
title: Collegare un esperimento e modificare varianti
description: In questo argomento viene descritto come connettere un esperimento in un servizio di terze parti a Dynamics 365 Commerce e come modificare varianti per l'esperimento.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 4c9c9463162f21cdaf40f1c4ed6d5ae51e97cb88
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799086"
---
# <a name="connect-an-experiment-and-edit-variations"></a><span data-ttu-id="476e6-103">Collegare un esperimento e modificare varianti</span><span class="sxs-lookup"><span data-stu-id="476e6-103">Connect an experiment and edit variations</span></span>

<span data-ttu-id="476e6-104">In questo argomento viene descritto come collegare un esperimento in Commerce e apportare modifiche alle varianti in modo che siano in linea con l'ipotesi.</span><span class="sxs-lookup"><span data-stu-id="476e6-104">This topic describes how to connect your experiment in Commerce and make changes to your variations so that they align with your hypothesis.</span></span> 

<span data-ttu-id="476e6-105">Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="476e6-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="476e6-106">I passaggi aggiuntivi sono esposti in argomenti separati.</span><span class="sxs-lookup"><span data-stu-id="476e6-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="476e6-107">[ ![Percorso utente per sperimentazione - Collegamento e modifica](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="476e6-107">[ ![Experimentation user journey - Connect & Edit](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span></span>

<span data-ttu-id="476e6-108">Dopo che hai [configurato l'esperimento](experimentation-setup.md) in un servizio di terze parti, collegherai l'esperimento in Dynamics 365 Commerce e modificherai le varianti dell'esperimento.</span><span class="sxs-lookup"><span data-stu-id="476e6-108">After you've [set up your experiment](experimentation-setup.md) in a third-party service, you'll connect the experiment in Dynamics 365 Commerce and edit the experiment variations.</span></span>

## <a name="planning-considerations"></a><span data-ttu-id="476e6-109">Considerazioni sulla pianificazione</span><span class="sxs-lookup"><span data-stu-id="476e6-109">Planning considerations</span></span>

<span data-ttu-id="476e6-110">Prima di collegare l'esperimento in Commerce, dovrai prendere alcune decisioni che influiscono sul modo in cui Commerce gestisce i contenuti.</span><span class="sxs-lookup"><span data-stu-id="476e6-110">Before you connect your experiment in Commerce, you'll need to make some decisions that impact the way Commerce manages your content.</span></span>

### <a name="determine-the-scope-of-your-experiment"></a><span data-ttu-id="476e6-111">Determinare l'ambito dell'esperimento</span><span class="sxs-lookup"><span data-stu-id="476e6-111">Determine the scope of your experiment</span></span>
<span data-ttu-id="476e6-112">Quando colleghi un esperimento, ti viene chiesto di definire l'ambito dell'esperimento.</span><span class="sxs-lookup"><span data-stu-id="476e6-112">When you connect an experiment, you are prompted to define the scope of the experiment.</span></span> <span data-ttu-id="476e6-113">Gli esperimenti sono definiti come ambito **parziale** o ambito **intero**.</span><span class="sxs-lookup"><span data-stu-id="476e6-113">Experiments are defined as **partial** scope or **entire** scope.</span></span>
- <span data-ttu-id="476e6-114">Scegli **parziale** se desideri condurre un esperimento su una parte specifica di una pagina.</span><span class="sxs-lookup"><span data-stu-id="476e6-114">Choose **partial** if you want to conduct an experiment on a specific portion of a page.</span></span> <span data-ttu-id="476e6-115">Se selezioni questa opzione, devi identificare i moduli inclusi nell'esperimento.</span><span class="sxs-lookup"><span data-stu-id="476e6-115">If you select this option, you must identify which modules are included in the experiment.</span></span> <span data-ttu-id="476e6-116">Le modifiche apportate a parti della pagina o del frammento predefinito non correlate all'esperimento vengono sincronizzate automaticamente tra le varianti.</span><span class="sxs-lookup"><span data-stu-id="476e6-116">Changes that are made to parts of the default page or fragment that aren't related to the experiment are automatically synchronized across variations.</span></span>
- <span data-ttu-id="476e6-117">Scegli **intero** se desideri condurre un esperimento su un'intera pagina o un frammento.</span><span class="sxs-lookup"><span data-stu-id="476e6-117">Choose **entire** if you want to conduct an experiment on an entire page or fragment.</span></span> <span data-ttu-id="476e6-118">Vengono create copie distinte della pagina o del frammento predefinito.</span><span class="sxs-lookup"><span data-stu-id="476e6-118">Separate copies of the default page or fragment are created.</span></span> <span data-ttu-id="476e6-119">Non sarà necessario selezionare quali moduli sono inclusi nell'esperimento perché l'intera superficie di modifica è disponibile per la modifica.</span><span class="sxs-lookup"><span data-stu-id="476e6-119">You won't have to select which modules are included in the experiment because the whole editing surface is available to change.</span></span> <span data-ttu-id="476e6-120">È possibile aggiungere, eliminare o riordinare i moduli come necessario.</span><span class="sxs-lookup"><span data-stu-id="476e6-120">You can add, delete, or re-order modules as needed.</span></span> <span data-ttu-id="476e6-121">Tuttavia, se vengono apportate modifiche alla pagina o al frammento predefinito a cui è associato l'esperimento, tali modifiche devono essere sincronizzate manualmente in tutte le varianti.</span><span class="sxs-lookup"><span data-stu-id="476e6-121">However, if any changes are made to the default page or fragment that the experiment is associated with, those changes have to be manually synchronized across all variations.</span></span>

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> <span data-ttu-id="476e6-122">Se associ l'esperimento a una pagina che utilizza un layout, puoi definire l'ambito dell'esperimento solo come **intero**.</span><span class="sxs-lookup"><span data-stu-id="476e6-122">If you associate your experiment with a page that uses a layout, you can only scope the experiment as **entire**.</span></span>

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a><span data-ttu-id="476e6-123">Decidere se pianificare quando l'esperimento deve essere pubblicato</span><span class="sxs-lookup"><span data-stu-id="476e6-123">Decide if you want to schedule when your experiment is published</span></span>
<span data-ttu-id="476e6-124">Se desideri pianificare quando l'esperimento deve essere pubblicato sul tuo sito live, assicurati che il contenuto che desideri associare all'esperimento sia disponibile in un gruppo di pubblicazione *prima* di collegare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="476e6-124">If you want to schedule when your experiment is published to your live site, make sure the content you want to associate with the experiment is available in a publish group *before* you connect the experiment.</span></span> 

<span data-ttu-id="476e6-125">Per ulteriori informazioni sui gruppi di pubblicazione, fai riferimento a [Utilizzare i gruppi di pubblicazione](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="476e6-125">For more information about publish groups, refer to [Work with publish groups](publish-groups.md).</span></span>


## <a name="connect-your-experiment"></a><span data-ttu-id="476e6-126">Collegare l'esperimento</span><span class="sxs-lookup"><span data-stu-id="476e6-126">Connect your experiment</span></span>
<span data-ttu-id="476e6-127">Per collegare l'esperimento, avvierai la procedura guidata **Collega l'esperimento**.</span><span class="sxs-lookup"><span data-stu-id="476e6-127">To connect your experiment, you'll launch the **Connect experiment** wizard.</span></span> <span data-ttu-id="476e6-128">Questa procedura guidata ti guida attraverso i passaggi necessari per collegare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="476e6-128">The wizard walks you through the steps required to connect your experiment.</span></span> <span data-ttu-id="476e6-129">Al termine della procedura guidata, l'esperimento risulta collegato, le varianti sono state create e sono pronte per essere modificate.</span><span class="sxs-lookup"><span data-stu-id="476e6-129">When you complete the wizard, your experiment is connected and variations are created and ready to be edited.</span></span>

<span data-ttu-id="476e6-130">Per iniziare la connessione dell'esperimento in Creazione di siti Web di Commerce seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="476e6-130">To get started connecting your experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="476e6-131">Per avviare la procedura guidata **Connetti esperimento**, selezionare **Esperimenti** nel riquadro di spostamento a sinistra, quindi selezionare **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="476e6-131">To launch the **Connect experiment** wizard, select **Experiments** in the left navigation pane, and then select **Connect**.</span></span> <span data-ttu-id="476e6-132">In alternativa, è possibile accedere alla procedura guidata da una pagina o da un editor di frammenti modificandolo e selezionando **Connetti esperimento** sulla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="476e6-132">Alternatively, you can access the wizard from a page or fragment editor by editing it and selecting **Connect experiment** on the command bar.</span></span>

    > [!NOTE]
    > <span data-ttu-id="476e6-133">Una pagina può essere collegata solo a un esperimento alla volta.</span><span class="sxs-lookup"><span data-stu-id="476e6-133">A page can only be connected to one experiment at a time.</span></span> <span data-ttu-id="476e6-134">Per collegare una pagina a un altro esperimento, elimina prima l'esperimento a cui la pagina è attualmente collegata.</span><span class="sxs-lookup"><span data-stu-id="476e6-134">To connect a page to a different experiment, first delete the experiment that the page is currently connected to.</span></span>

1. <span data-ttu-id="476e6-135">Scegli la pagina o il frammento su cui desideri eseguire l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="476e6-135">Choose the page or fragment you want to run your experiment on.</span></span>
1. <span data-ttu-id="476e6-136">Imposta l'ambito della sperimentazione su **parziale** o **intero**, in base alla scelta che hai fatto nella sezione [Determinare l'ambito dell'esperimento](#determine-the-scope-of-your-experiment) vista sopra.</span><span class="sxs-lookup"><span data-stu-id="476e6-136">Set the experimentation scope to **partial** or **entire**, based on the choice you made in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>
    > [!NOTE]
    > <span data-ttu-id="476e6-137">Il flag della funzionalità **Sperimenta su pagine o frammenti** deve essere abilitato se desideri sperimentare su una pagina o su un frammento intero.</span><span class="sxs-lookup"><span data-stu-id="476e6-137">The **Experiment on pages or fragments** feature flag must be enabled if you want to experiment on a full page or fragment.</span></span> <span data-ttu-id="476e6-138">Per ulteriori informazioni, fai riferimento all'argomento [Sperimentazione in Dynamics 365 Commerce](experimentation-overview.md):</span><span class="sxs-lookup"><span data-stu-id="476e6-138">Refer to the [Experimentation in Dynamics 365 Commerce](experimentation-overview.md) topic for more information.</span></span>
    
1. <span data-ttu-id="476e6-139">Nel passaggio finale della procedura guidata, seleziona **Genera varianti e chiudi la procedura guidata**.</span><span class="sxs-lookup"><span data-stu-id="476e6-139">In the final step of the wizard, select **Generate variations and exit wizard**.</span></span> <span data-ttu-id="476e6-140">Le varianti vengono create per l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="476e6-140">Variations are created for the experiment.</span></span> 

## <a name="edit-your-variations"></a><span data-ttu-id="476e6-141">Modificare le varianti</span><span class="sxs-lookup"><span data-stu-id="476e6-141">Edit your variations</span></span>
<span data-ttu-id="476e6-142">Quando chiudi la procedura guidata, vengono create le varianti.</span><span class="sxs-lookup"><span data-stu-id="476e6-142">When you exit the wizard, variations are created for you.</span></span> 

<span data-ttu-id="476e6-143">Successivamente, modificherai le varianti in modo che riflettano le scelte che devi verificare nell'ipotesi dell'esperimento.</span><span class="sxs-lookup"><span data-stu-id="476e6-143">Next, you'll edit the variations so they reflect the choices that you need to verify in the experiment hypothesis.</span></span> <span data-ttu-id="476e6-144">Scegli una delle seguenti procedure che corrisponde all'ambito scelto per l'esperimento nella sezione [Determinare l'ambito dell'esperimento](#determine-the-scope-of-your-experiment) vista sopra.</span><span class="sxs-lookup"><span data-stu-id="476e6-144">Choose one of following procedures that corresponds to the scope you chose for your experiment in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>

### <a name="edit-variations-for-experiments-with-partial-scope"></a><span data-ttu-id="476e6-145">Modificare le varianti per esperimenti con ambito parziale</span><span class="sxs-lookup"><span data-stu-id="476e6-145">Edit variations for experiments with partial scope</span></span>
<span data-ttu-id="476e6-146">Segui questi passaggi se hai definito l'ambito dell'esperimento come **parziale** nella procedura guidata **Collega l'esperimento**.</span><span class="sxs-lookup"><span data-stu-id="476e6-146">Follow these steps if you defined the scope of your experiment as **partial** in the **Connect experiment** wizard.</span></span>

1. <span data-ttu-id="476e6-147">Nella visualizzazione dell'editor, utilizza il menu a discesa delle varianti sotto la barra dei comandi per modificare ogni variante in base all'ipotesi originale.</span><span class="sxs-lookup"><span data-stu-id="476e6-147">In editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> <span data-ttu-id="476e6-148">Puoi anche stabilire una variante di base o controllo lasciando invariata una delle varianti.</span><span class="sxs-lookup"><span data-stu-id="476e6-148">You may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>
1. <span data-ttu-id="476e6-149">Seleziona il modulo su cui sperimentare, seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi all'esperimento**.</span><span class="sxs-lookup"><span data-stu-id="476e6-149">Select the module to be experimented on, select the ellipsis (...), and then select **Add to experiment**.</span></span>

### <a name="edit-variations-for-experiments-with-entire-scope"></a><span data-ttu-id="476e6-150">Modificare varianti per esperimenti con ambito intero</span><span class="sxs-lookup"><span data-stu-id="476e6-150">Edit variations for experiments with entire scope</span></span>
<span data-ttu-id="476e6-151">Se hai definito l'ambito dell'esperimento come **intero** nella procedura guidata **Collega l'esperimento**, nella visualizzazione dell'editor utilizza il menu a discesa delle varianti sotto la barra dei comandi per modificare ogni variante in base all'ipotesi originale.</span><span class="sxs-lookup"><span data-stu-id="476e6-151">If you defined the scope of your experiment as **entire** in the **Connect experiment** wizard, while in editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> 

> [!NOTE]
> <span data-ttu-id="476e6-152">In entrambi i casi, puoi anche stabilire una variante di base o controllo lasciando invariata una delle varianti.</span><span class="sxs-lookup"><span data-stu-id="476e6-152">In either case, you may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>

## <a name="previous-step"></a><span data-ttu-id="476e6-153">Passaggio precedente</span><span class="sxs-lookup"><span data-stu-id="476e6-153">Previous step</span></span>
[<span data-ttu-id="476e6-154">Configurare un esperimento</span><span class="sxs-lookup"><span data-stu-id="476e6-154">Set up an experiment</span></span>](experimentation-setup.md) 


## <a name="next-step"></a><span data-ttu-id="476e6-155">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="476e6-155">Next step</span></span>
[<span data-ttu-id="476e6-156">Visualizzare un esperimento in anteprima e pubblicarlo</span><span class="sxs-lookup"><span data-stu-id="476e6-156">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]