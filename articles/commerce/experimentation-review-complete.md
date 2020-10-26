---
title: Promuovere una variante e completare un esperimento
description: Questo argomento descrive come promuovere una variante appropriata e completare un esperimento in Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930224"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="00dd2-103">Promuovere una variante e completare un esperimento</span><span class="sxs-lookup"><span data-stu-id="00dd2-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="00dd2-104">Questo argomento descrive come promuovere la variante che ha prodotto i migliori risultati nell'esperimento e come completare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="00dd2-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="00dd2-105">Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="00dd2-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="00dd2-106">I passaggi aggiuntivi sono esposti in argomenti separati.</span><span class="sxs-lookup"><span data-stu-id="00dd2-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="00dd2-107">[![Percorso utente per sperimentazione - Analisi e completamento](./media/experimentation_review_complete.svg)](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="00dd2-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="00dd2-108">Dopo aver [eseguito l'esperimento](experimentation-run-monitor.md) e raccolto dati sufficienti per determinare quale variante desideri utilizzare sul tuo sito live, promuoverai la variante e terminerai l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="00dd2-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="00dd2-109">Promuovere una variante</span><span class="sxs-lookup"><span data-stu-id="00dd2-109">Promote a variation</span></span>
<span data-ttu-id="00dd2-110">Utilizza i dati e le analisi relative all'esperimento nel servizio di terze parti per decidere quale variante ha prodotto i risultati migliori.</span><span class="sxs-lookup"><span data-stu-id="00dd2-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="00dd2-111">Per sostituire il contenuto corrente sul sito live con la variante migliore di modo che sia disponibile a tutti gli utenti del sito web, procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="00dd2-111">To replace the current content on the live site with the winning variation so that it's available to all users of your website, do the following.</span></span> 

1. <span data-ttu-id="00dd2-112">Vai alla scheda **Esperimenti** in Creazione di siti Web e seleziona l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="00dd2-112">Go to the **Experiments** tab in site builder and select the experiment.</span></span>
1. <span data-ttu-id="00dd2-113">Seleziona **Completa esperimento** nella barra in alto.</span><span class="sxs-lookup"><span data-stu-id="00dd2-113">Select **Complete experiment** on the top bar.</span></span>
1. <span data-ttu-id="00dd2-114">Nel menu della finestra di dialogo **Completa l'esperimento**, seleziona **Esamina dati dell'esperimento**.</span><span class="sxs-lookup"><span data-stu-id="00dd2-114">In the **Complete the experiment** dialog menu, select **Review the experiment data**.</span></span> <span data-ttu-id="00dd2-115">Si apre il servizio di terze parti in cui è possibile convalidare le metriche e determinare quale variante ha avuto il rendimento migliore.</span><span class="sxs-lookup"><span data-stu-id="00dd2-115">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="00dd2-116">Nel menu di dialogo **Completa l'esperimento** in Creazione di siti Web, seleziona la variante migliore e quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="00dd2-116">In the **Complete the experiment** dialog menu in site builder, select the winning variation and then select **Next**.</span></span>
1. <span data-ttu-id="00dd2-117">Apri il servizio di terze parti e interrompi l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="00dd2-117">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="00dd2-118">In Creazione di siti Web, seleziona**Completa** per sovrascrivere la pagina live originale e pubblicare la variante migliore di modo che sia disponibile a tutti gli utenti del sito web.</span><span class="sxs-lookup"><span data-stu-id="00dd2-118">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="00dd2-119">Se scegli di mantenere la pagina live corrente e di non pubblicare una variante, seleziona **Ripubblica la pagina originale**.</span><span class="sxs-lookup"><span data-stu-id="00dd2-119">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="00dd2-120">Eliminare l'esperimento</span><span class="sxs-lookup"><span data-stu-id="00dd2-120">Delete your experiment</span></span>
<span data-ttu-id="00dd2-121">Sebbene non sia necessario eliminare un esperimento completato in Commerce, puoi scegliere di eliminarlo per risparmiare spazio o pulire l'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="00dd2-121">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> <span data-ttu-id="00dd2-122">Per eliminare un esperimento, procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="00dd2-122">To delete an experiment, do the following.</span></span>

1. <span data-ttu-id="00dd2-123">Vai alla scheda **Esperimenti** in Creazione di siti Web e seleziona l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="00dd2-123">Go to the **Experiments** tab in site builder and select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="00dd2-124">Se l'esperimento è ancora attivo, arrestalo l'esperimento nel servizio di terze parti prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="00dd2-124">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="00dd2-125">Seleziona **Annulla pubblicazione** nella barra dei comandi per rimuovere il contenuto della variante dal sito live.</span><span class="sxs-lookup"><span data-stu-id="00dd2-125">Select **Unpublish** in the command bar to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="00dd2-126">Seleziona **Elimina** nella barra dei comandi per eliminare l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="00dd2-126">Select **Delete** in the command bar to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="00dd2-127">Passaggio precedente</span><span class="sxs-lookup"><span data-stu-id="00dd2-127">Previous step</span></span>
[<span data-ttu-id="00dd2-128">Eseguire e monitorare un esperimento</span><span class="sxs-lookup"><span data-stu-id="00dd2-128">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
