---
title: Promuovere una variante e completare un esperimento
description: Questo argomento descrive come promuovere una variante appropriata e completare un esperimento in Dynamics 365 Commerce.
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
ms.openlocfilehash: 0ea0fc8d50c25312b184ec1d3bd613695870d121
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792561"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="eba50-103">Promuovere una variante e completare un esperimento</span><span class="sxs-lookup"><span data-stu-id="eba50-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="eba50-104">Questo argomento descrive come promuovere la variante che ha prodotto i migliori risultati nell'esperimento e come completare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="eba50-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="eba50-105">Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="eba50-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="eba50-106">I passaggi aggiuntivi sono esposti in argomenti separati.</span><span class="sxs-lookup"><span data-stu-id="eba50-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="eba50-107">[![Percorso utente per sperimentazione - Analisi e completamento](./media/experimentation_review_complete.svg)](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="eba50-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="eba50-108">Dopo aver [eseguito l'esperimento](experimentation-run-monitor.md) e raccolto dati sufficienti per determinare quale variante desideri utilizzare sul tuo sito live, promuoverai la variante e terminerai l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="eba50-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="eba50-109">Promuovere una variante</span><span class="sxs-lookup"><span data-stu-id="eba50-109">Promote a variation</span></span>
<span data-ttu-id="eba50-110">Utilizza i dati e le analisi relative all'esperimento nel servizio di terze parti per decidere quale variante ha prodotto i risultati migliori.</span><span class="sxs-lookup"><span data-stu-id="eba50-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="eba50-111">È possibile promuoverla sostituendo il contenuto corrente sul sito live con la variante migliore di modo che sia disponibile a tutti gli utenti del sito web.</span><span class="sxs-lookup"><span data-stu-id="eba50-111">You can then promote it by replacing the current content on the live site with the winning variation so that it's available to all users of your website.</span></span>

<span data-ttu-id="eba50-112">Per promuovere la variante migliore, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="eba50-112">To promote the winning variation, follow these steps.</span></span> 

1. <span data-ttu-id="eba50-113">In Creazione di siti Web di Commerce selezionare **Esperimenti** nel riquadro di spostamento a sinistra e selezionare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="eba50-113">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span>
1. <span data-ttu-id="eba50-114">Selezionare **Completa esperimento** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="eba50-114">On the command bar, select **Complete experiment**.</span></span>
1. <span data-ttu-id="eba50-115">Nella casella di dialogo **Completa l'esperimento**, selezionare **Esamina dati dell'esperimento**.</span><span class="sxs-lookup"><span data-stu-id="eba50-115">In the **Complete the experiment** dialog box, select **Review the experiment data**.</span></span> <span data-ttu-id="eba50-116">Si apre il servizio di terze parti in cui è possibile convalidare le metriche e determinare quale variante ha avuto il rendimento migliore.</span><span class="sxs-lookup"><span data-stu-id="eba50-116">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="eba50-117">Nella casella di dialogo **Completa l'esperimento** selezionare la variante migliore e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="eba50-117">In the **Complete the experiment** dialog box, select the winning variation, and then select **Next**.</span></span>
1. <span data-ttu-id="eba50-118">Apri il servizio di terze parti e interrompi l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="eba50-118">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="eba50-119">In Creazione di siti Web, seleziona **Completa** per sovrascrivere la pagina live originale e pubblicare la variante migliore di modo che sia disponibile a tutti gli utenti del sito web.</span><span class="sxs-lookup"><span data-stu-id="eba50-119">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="eba50-120">Se scegli di mantenere la pagina live corrente e di non pubblicare una variante, seleziona **Ripubblica la pagina originale**.</span><span class="sxs-lookup"><span data-stu-id="eba50-120">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="eba50-121">Eliminare l'esperimento</span><span class="sxs-lookup"><span data-stu-id="eba50-121">Delete your experiment</span></span>
<span data-ttu-id="eba50-122">Sebbene non sia necessario eliminare un esperimento completato in Commerce, puoi scegliere di eliminarlo per risparmiare spazio o pulire l'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="eba50-122">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> 

<span data-ttu-id="eba50-123">Per eliminare un esperimento in Creazione di siti Web di Commerce seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="eba50-123">To delete an experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="eba50-124">Selezionare **Esperimenti** nel riquadro di spostamento a sinistra e selezionare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="eba50-124">Select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="eba50-125">Se l'esperimento è ancora attivo, arrestalo l'esperimento nel servizio di terze parti prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="eba50-125">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="eba50-126">Selezionare **Annulla pubblicazione** nella barra dei comandi per rimuovere il contenuto della variante dal sito live.</span><span class="sxs-lookup"><span data-stu-id="eba50-126">On the command bar, select **Unpublish**  to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="eba50-127">Selezionare **Elimina** per eliminare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="eba50-127">Select **Delete** to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="eba50-128">Passaggio precedente</span><span class="sxs-lookup"><span data-stu-id="eba50-128">Previous step</span></span>
[<span data-ttu-id="eba50-129">Eseguire e monitorare un esperimento</span><span class="sxs-lookup"><span data-stu-id="eba50-129">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]