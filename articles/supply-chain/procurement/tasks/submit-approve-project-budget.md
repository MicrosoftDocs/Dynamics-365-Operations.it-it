---
title: Inviare e approvare un budget di progetto
description: In questa procedura viene illustrato come creare e inviare il budget per un progetto.
author: mkirknel
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14683554c45db72061ecbbf4a528656df3132692
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207451"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="431d0-103">Inviare e approvare un budget di progetto</span><span class="sxs-lookup"><span data-stu-id="431d0-103">Submit and approve project budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="431d0-104">In questa procedura viene illustrato come creare e inviare il budget per un progetto.</span><span class="sxs-lookup"><span data-stu-id="431d0-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="431d0-105">Quando si crea un budget del progetto è possibile immettere i costi e i ricavi stimati per un progetto e di utilizzarli successivamente per controllare le transazioni di progetto effettive.</span><span class="sxs-lookup"><span data-stu-id="431d0-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="431d0-106">Per i budget di progetto, tutti i budget e le revisioni originali devono essere inviati al flusso di lavoro del progetto per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="431d0-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="431d0-107">Il flusso di lavoro consente un controllo maggiore sul processo e consente di creare un record di storico modifiche.</span><span class="sxs-lookup"><span data-stu-id="431d0-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="431d0-108">Questa attività è stata creata utilizzando il set di dati USSI.</span><span class="sxs-lookup"><span data-stu-id="431d0-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="431d0-109">Nel **pannello di navigazione**, andare a **Moduli > Gestione progetti e contabilità > Progetti > Tutti i progetti**.</span><span class="sxs-lookup"><span data-stu-id="431d0-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="431d0-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="431d0-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="431d0-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="431d0-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="431d0-112">Nel **riquadro azioni**, fare clic su **Piano**.</span><span class="sxs-lookup"><span data-stu-id="431d0-112">On the **Action Pane**, click **Plan**.</span></span>
5. <span data-ttu-id="431d0-113">Fare clic su **Budget progetto**.</span><span class="sxs-lookup"><span data-stu-id="431d0-113">Click **Project budget**.</span></span>
6. <span data-ttu-id="431d0-114">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="431d0-114">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="431d0-115">Espandere la Scheda dettaglio **Costo**.</span><span class="sxs-lookup"><span data-stu-id="431d0-115">Expand the **Cost** fastTab.</span></span>
8. <span data-ttu-id="431d0-116">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="431d0-116">Click **New**.</span></span>
9. <span data-ttu-id="431d0-117">Selezionare un'opzione nel campo **Tipo di transazione**.</span><span class="sxs-lookup"><span data-stu-id="431d0-117">In the **Transaction type** field, select an option.</span></span>
10. <span data-ttu-id="431d0-118">Nel campo **Categoria** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="431d0-118">In the **Category** field, enter or select a value.</span></span>
11. <span data-ttu-id="431d0-119">Nel campo **Budget originale** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="431d0-119">In the **Original budget** field, enter a number.</span></span>
12. <span data-ttu-id="431d0-120">Espandere la Scheda dettaglio **Ricavi**.</span><span class="sxs-lookup"><span data-stu-id="431d0-120">Expand the **Revenues** fastTab.</span></span>
13. <span data-ttu-id="431d0-121">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="431d0-121">Click **New**.</span></span>
14. <span data-ttu-id="431d0-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="431d0-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="431d0-123">Selezionare un'opzione nel campo **Tipo di transazione**.</span><span class="sxs-lookup"><span data-stu-id="431d0-123">In the **Transaction type** field, select an option.</span></span>
16. <span data-ttu-id="431d0-124">Nel campo **Categoria** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="431d0-124">In the **Category** field, enter or select a value.</span></span>
17. <span data-ttu-id="431d0-125">Nel campo **Budget originale** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="431d0-125">In the **Original budget** field, enter a number.</span></span>
18. <span data-ttu-id="431d0-126">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="431d0-126">Click **Save**.</span></span>
19. <span data-ttu-id="431d0-127">Fare clic su **Flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="431d0-127">Click **Workflow**.</span></span>
20. <span data-ttu-id="431d0-128">Fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="431d0-128">Click **Submit**.</span></span>
21. <span data-ttu-id="431d0-129">Digitare un valore nel campo **Commento**.</span><span class="sxs-lookup"><span data-stu-id="431d0-129">In the **Comment** field, type a value.</span></span>
22. <span data-ttu-id="431d0-130">Fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="431d0-130">Click **Submit**.</span></span>

