---
title: Registrare il consumo
description: In questo argomento viene illustrato come registrare il consumo in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 174c816c7a6442b07e4722c03045293b94c59153
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024662"
---
# <a name="register-consumption"></a><span data-ttu-id="9f3a6-103">Registrare il consumo</span><span class="sxs-lookup"><span data-stu-id="9f3a6-103">Register consumption</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="9f3a6-104">Dopo il completamento di un ordine di lavoro, è necessario eseguire le registrazioni del consumo e registrare i giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-104">When a maintenance job has been completed on a work order, the next step is to make consumption registrations and post the journals.</span></span> <span data-ttu-id="9f3a6-105">È possibile effettuare registrazioni per i seguenti tipi di consumo: ore, articoli e spese.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-105">You can make registrations on the following consumption types: Hours, items, and expenses.</span></span> <span data-ttu-id="9f3a6-106">I differenti tipi di consumo vengono registrati nella pagina **Giornali di registrazione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-106">The different consumption types are registered and posted on the **Work order journals** page.</span></span> <span data-ttu-id="9f3a6-107">La configurazione dei giornali di registrazione in **Gestione cespiti** viene utilizzata per creare e registrare giornali di registrazione distinti per ore, articoli e spese nel modulo **Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-107">The journal setup in **Asset Management** is used for creating and posting separate journals for hours, items, and expenses in the **Project management and accounting** module.</span></span>

<span data-ttu-id="9f3a6-108">Esiste la possibilità di aggiungere o eliminare righe di previsione,</span><span class="sxs-lookup"><span data-stu-id="9f3a6-108">You may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="9f3a6-109">ma ciò dipende dall'impostazione dello stato del ciclo di vita di ordine di lavoro, dal tipo di progetto correlato e dalla regole di fase associate.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-109">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determine if you are able to add or edit journal lines.</span></span> <span data-ttu-id="9f3a6-110">Per ulteriori informazioni sugli stati del ciclo di vita di ordine di lavoro e le relative fasi di progetto, vedere [Integrazione a gestione progetti e contabilità](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="9f3a6-110">Read more about work order lifecycle states and related project stages in [Integration to project management and accounting](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

>[!NOTE]
><span data-ttu-id="9f3a6-111">È possibile impostare la registrazione automatica dei giornali di registrazione in uno stato del ciclo di vita di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-111">It is possible to set up automatic posting of journals on a work order lifecycle state.</span></span> <span data-ttu-id="9f3a6-112">Per ulteriori informazioni, fare riferimento a [Stati del ciclo di vita ordine di lavoro](../setup-for-work-orders/work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="9f3a6-112">Refer to [Work order lifecycle states](../setup-for-work-orders/work-order-lifecycle-states.md) for more information.</span></span>

1. <span data-ttu-id="9f3a6-113">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-113">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="9f3a6-114">Selezionare l'ordine di lavoro e fare clic su **Giornali di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-114">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="9f3a6-115">Fare clic su **Copia da previsione** per trasferire le eventuali righe di previsione che possono essere associate all'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-115">Click **Copy from forecast** to transfer any forecast lines that may be connected to the work order.</span></span> <span data-ttu-id="9f3a6-116">È possibile selezionare i tipi di consumo che si desidera trasferire.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-116">You can select which consumption types you want to transfer.</span></span>

4. <span data-ttu-id="9f3a6-117">Se necessario, è possibile aggiungere ulteriori righe di consumo nella Scheda dettaglio pertinente facendo clic su **Aggiungi riga** e immettendo i dati nella riga.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-117">If necessary, you can add more consumption lines on the relevant FastTab by clicking **Add line** and filling out data on the line.</span></span>

5. <span data-ttu-id="9f3a6-118">Fare clic su **Convalida giornali di registrazione** per convalidare le righe dei giornali di registrazione prima della registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-118">Click **Validate journals** to validate the journal lines before posting.</span></span>

6. <span data-ttu-id="9f3a6-119">Fare clic su **Registra giornali** per registrare le righe dei giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-119">Click **Post journals** to post the journal lines.</span></span>

7. <span data-ttu-id="9f3a6-120">Dopo aver registrato i giornali di registrazione del consumo, è possibile aggiornare lo stato del ciclo di vita di ordine di lavoro, ad esempio a "Finito", per indicare che l'ordine di lavoro è stato completato.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-120">After you've posted the consumption journals, you can update the work order lifecycle state, for example to "Ended", to indicate that the work order has been completed.</span></span>

- <span data-ttu-id="9f3a6-121">Nel campo **Mostra** situato nella parte superiore della pagina **Giornali di registrazione ordine di lavoro**, selezionare le righe dei giornali di registrazione che si desidera visualizzare: Tutto, Non registrato o Registrato.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-121">In the **Show** field placed at the top of the **Work order journals** page, select which journal lines you want to see: All, Not posted, or Posted.</span></span> <span data-ttu-id="9f3a6-122">I giornali di registrazione registrati presentano un segno di spunta nella casella di controllo **Registrato**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-122">Posted journals have a check mark in the **Posted** check box.</span></span>  
- <span data-ttu-id="9f3a6-123">Quando si creano righe articolo nel giornale di registrazione di ordine di lavoro, le dimensioni prodotto e le dimensioni di tracciabilità correlate all'articolo sono trasferite automaticamente alla riga del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-123">When item lines are created in the work order journal, product dimensions and tracking dimensions related to the item are automatically transferred to the journal line.</span></span>  

<span data-ttu-id="9f3a6-124">La schermata seguente mostra un esempio di registrazioni di ore e articoli in un ordine di lavoro in **Giornali di registrazione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-124">The screenshot below shows an example of hour and item registrations on a work order in **Work order journals**.</span></span>

![Figura 1](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a><span data-ttu-id="9f3a6-126">Suddividere le ore negli ordini di lavoro con più processi di ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="9f3a6-126">Split hours on work orders with several work order jobs</span></span>

<span data-ttu-id="9f3a6-127">Se un ordine di lavoro contiene più processi di ordine di lavoro, è possibile registrare le ore lavorative utilizzando la funzionalità **Suddividi ore**, nel senso che la riga di registrazione di 1 ora può essere distribuita in modo uniforme in ogni processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-127">If a work order contains several work order jobs, you can register work hours using the **Split hours** functionality, meaning one hour registration line can be distributed evenly on each work order job.</span></span>

1. <span data-ttu-id="9f3a6-128">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-128">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="9f3a6-129">Selezionare l'ordine di lavoro e fare clic su **Giornali di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-129">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="9f3a6-130">Selezionare la riga di registrazione ore che si desidera suddividere e fare clic su **Suddividi ore**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-130">Select the hour registration line you want to split, and click **Split hours**.</span></span>

4. <span data-ttu-id="9f3a6-131">Nella finestra di dialogo **Suddividi ore in processi di manutenzione ordine di lavoro**, il nome del lavoratore che ha effettuato l'accesso viene visualizzato automaticamente nel campo **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-131">In the **Split hours on work order maintenance jobs** dialog, the name of the worker who is logged in is automatically shown in the **Worker** field.</span></span> <span data-ttu-id="9f3a6-132">Se necessario, è possibile selezionare un altro lavoratore.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-132">If required, you can select another worker.</span></span>

5. <span data-ttu-id="9f3a6-133">Selezionare una categoria per la registrazione ore nel campo **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-133">Select a category for the hour registration in the **Category** field.</span></span>

6. <span data-ttu-id="9f3a6-134">Nel campo **Ore** inserire il numero di ore da suddividere.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-134">Insert number of work hours to be split in the **Hours** field.</span></span>

![Figura 2](media/02-consumption.png)

7. <span data-ttu-id="9f3a6-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-136">Click **OK**.</span></span>

<span data-ttu-id="9f3a6-137">*Esempio:* nella schermata seguente sono visualizzate le righe del giornale di registrazione per un ordine di lavoro contenente tre processi di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-137">*Example:* In the screenshot below, journal lines for a work order containing three work order jobs are shown.</span></span> <span data-ttu-id="9f3a6-138">La prima riga, contenente tre ore lavorative, è stata suddivisa e un'ora lavorativa è registrata in ciascun processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-138">The first line, containing three work hours, has been split, and one work hour is registered on each work order job.</span></span> <span data-ttu-id="9f3a6-139">Dopo la creazione della registrazione delle tre ore, è necessario decidere cosa fare con la riga di registrazione ore originale (la prima riga nell'esempio).</span><span class="sxs-lookup"><span data-stu-id="9f3a6-139">After the three hour registration lines have been created, you decide what to do with the original hour registration line (the first line in the example).</span></span> <span data-ttu-id="9f3a6-140">È possibile tenerla così com'è oppure eliminarla.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-140">You can keep it as is or delete it.</span></span> 

![Figura 3](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a><span data-ttu-id="9f3a6-142">Dimensioni finanziarie nelle registrazioni del consumo</span><span class="sxs-lookup"><span data-stu-id="9f3a6-142">Financial dimensions on consumption registrations</span></span>

<span data-ttu-id="9f3a6-143">Quando si eseguono registrazioni del consumo, le dimensioni finanziarie relative ai differenti tipi di registrazione vengono aggiunte alle registrazioni in una sequenza specifica.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-143">When you make consumption registrations, financial dimensions related to the different registration types are added to the registrations in a specific sequence.</span></span> 

<span data-ttu-id="9f3a6-144">*Registrazioni ore e spese:* innanzi tutto, vengono aggiunte le eventuali dimensioni finanziarie dall'intestazione del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-144">*Hour and Expense registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="9f3a6-145">Successivamente, vengono aggiunte le dimensioni finanziarie dal progetto di ordine di lavoro correlato.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-145">Next, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="9f3a6-146">Infine, vengono aggiunte le dimensioni finanziarie dalla risorsa (lavoratore).</span><span class="sxs-lookup"><span data-stu-id="9f3a6-146">Finally, financial dimensions from the resource (worker) are added.</span></span>

<span data-ttu-id="9f3a6-147">*Registrazioni articoli:* innanzi tutto, vengono aggiunte le eventuali dimensioni finanziarie dall'intestazione del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-147">*Item registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="9f3a6-148">Vengono quindi aggiunte le dimensioni finanziarie dal progetto di ordine di lavoro correlato.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-148">Then, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="9f3a6-149">Successivamente, vengono aggiunte le dimensioni finanziarie dal sito.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-149">Next, financial dimensions from the site are added.</span></span> <span data-ttu-id="9f3a6-150">Infine, vengono aggiunte le dimensioni finanziarie dall'articolo.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-150">Finally, financial dimensions from the item are added.</span></span>

>[!NOTE]
><span data-ttu-id="9f3a6-151">Per tutti e tre i tipi di registrazione, viene convalidata la combinazione di dimensioni finanziarie e le combinazioni non valide vengono lasciate vuote.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-151">For all three registration types, the financial dimension combination is validated, and invalid combinations are blanked.</span></span> <span data-ttu-id="9f3a6-152">Questa è una configurazione standard in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9f3a6-152">This is standard setup in Finance and Operations.</span></span>

