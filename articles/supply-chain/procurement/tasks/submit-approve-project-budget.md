---
title: Inviare e approvare un budget di progetto
description: In questa procedura viene illustrato come creare e inviare il budget per un progetto.
author: mkirknel
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7aa7c301946b92b956f4b1b0f92985451ffe917e
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149437"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="5e44a-103">Inviare e approvare un budget di progetto</span><span class="sxs-lookup"><span data-stu-id="5e44a-103">Submit and approve project budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5e44a-104">In questa procedura viene illustrato come creare e inviare il budget per un progetto.</span><span class="sxs-lookup"><span data-stu-id="5e44a-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="5e44a-105">Quando si crea un budget del progetto è possibile immettere i costi e i ricavi stimati per un progetto e di utilizzarli successivamente per controllare le transazioni di progetto effettive.</span><span class="sxs-lookup"><span data-stu-id="5e44a-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="5e44a-106">Per i budget di progetto, tutti i budget e le revisioni originali devono essere inviati al flusso di lavoro del progetto per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="5e44a-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="5e44a-107">Il flusso di lavoro consente un controllo maggiore sul processo e consente di creare un record di storico modifiche.</span><span class="sxs-lookup"><span data-stu-id="5e44a-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="5e44a-108">Questa attività è stata creata utilizzando il set di dati USSI.</span><span class="sxs-lookup"><span data-stu-id="5e44a-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="5e44a-109">Nel **pannello di navigazione**, andare a **Moduli > Gestione progetti e contabilità > Progetti > Tutti i progetti**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="5e44a-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5e44a-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5e44a-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e44a-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="5e44a-112">Nel **riquadro azioni**, fare clic su **Piano**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-112">On the **Action Pane**, click **Plan**.</span></span>
5. <span data-ttu-id="5e44a-113">Fare clic su **Budget progetto**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-113">Click **Project budget**.</span></span>
6. <span data-ttu-id="5e44a-114">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5e44a-114">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="5e44a-115">Espandere la Scheda dettaglio **Costo**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-115">Expand the **Cost** fastTab.</span></span>
8. <span data-ttu-id="5e44a-116">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-116">Click **New**.</span></span>
9. <span data-ttu-id="5e44a-117">Selezionare un'opzione nel campo **Tipo di transazione**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-117">In the **Transaction type** field, select an option.</span></span>
10. <span data-ttu-id="5e44a-118">Nel campo **Categoria** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e44a-118">In the **Category** field, enter or select a value.</span></span>
11. <span data-ttu-id="5e44a-119">Nel campo **Budget originale** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5e44a-119">In the **Original budget** field, enter a number.</span></span>
12. <span data-ttu-id="5e44a-120">Espandere la Scheda dettaglio **Ricavi**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-120">Expand the **Revenues** fastTab.</span></span>
13. <span data-ttu-id="5e44a-121">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-121">Click **New**.</span></span>
14. <span data-ttu-id="5e44a-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e44a-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="5e44a-123">Selezionare un'opzione nel campo **Tipo di transazione**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-123">In the **Transaction type** field, select an option.</span></span>
16. <span data-ttu-id="5e44a-124">Nel campo **Categoria** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e44a-124">In the **Category** field, enter or select a value.</span></span>
17. <span data-ttu-id="5e44a-125">Nel campo **Budget originale** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5e44a-125">In the **Original budget** field, enter a number.</span></span>
18. <span data-ttu-id="5e44a-126">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-126">Click **Save**.</span></span>
19. <span data-ttu-id="5e44a-127">Fare clic su **Flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-127">Click **Workflow**.</span></span>
20. <span data-ttu-id="5e44a-128">Fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-128">Click **Submit**.</span></span>
21. <span data-ttu-id="5e44a-129">Digitare un valore nel campo **Commento**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-129">In the **Comment** field, type a value.</span></span>
22. <span data-ttu-id="5e44a-130">Fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-130">Click **Submit**.</span></span>

