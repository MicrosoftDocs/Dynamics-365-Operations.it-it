---
title: Registrare il consumo
description: In questo argomento viene illustrato come registrare il consumo in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 61aea0261a62df9c029b429f33ba7b357621988b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259988"
---
# <a name="register-consumption"></a><span data-ttu-id="aac21-103">Registrare il consumo</span><span class="sxs-lookup"><span data-stu-id="aac21-103">Register consumption</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="aac21-104">Dopo il completamento di un ordine di lavoro, è necessario eseguire le registrazioni del consumo e registrare i giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="aac21-104">When a maintenance job has been completed on a work order, the next step is to make consumption registrations and post the journals.</span></span> <span data-ttu-id="aac21-105">È possibile effettuare registrazioni per i seguenti tipi di consumo: ore, articoli e spese.</span><span class="sxs-lookup"><span data-stu-id="aac21-105">You can make registrations on the following consumption types: Hours, items, and expenses.</span></span> <span data-ttu-id="aac21-106">I differenti tipi di consumo vengono registrati nella pagina **Giornali di registrazione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="aac21-106">The different consumption types are registered and posted on the **Work order journals** page.</span></span> <span data-ttu-id="aac21-107">La configurazione dei giornali di registrazione in **Gestione cespiti** viene utilizzata per creare e registrare giornali di registrazione distinti per ore, articoli e spese nel modulo **Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="aac21-107">The journal setup in **Asset Management** is used for creating and posting separate journals for hours, items, and expenses in the **Project management and accounting** module.</span></span>

<span data-ttu-id="aac21-108">In alcuni casi, esiste la possibilità di aggiungere o eliminare righe di previsione,</span><span class="sxs-lookup"><span data-stu-id="aac21-108">In some cases, you may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="aac21-109">ma ciò dipende dall'impostazione dello stato del ciclo di vita di ordine di lavoro, dal tipo di progetto correlato e dalla regole di fase associate.</span><span class="sxs-lookup"><span data-stu-id="aac21-109">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determine if you are able to add or edit journal lines.</span></span> <span data-ttu-id="aac21-110">Per ulteriori informazioni sugli stati del ciclo di vita di ordine di lavoro e sulle fasi di progetto correlate, vedere [Previsioni, ordini di lavoro e progetti](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="aac21-110">Read more about work order lifecycle states and related project stages in [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

>[!NOTE]
><span data-ttu-id="aac21-111">È possibile impostare la registrazione automatica dei giornali di registrazione in uno stato del ciclo di vita di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aac21-111">It is possible to set up automatic posting of journals on a work order lifecycle state.</span></span> <span data-ttu-id="aac21-112">Per ulteriori informazioni, fare riferimento a [Stati del ciclo di vita ordine di lavoro](../setup-for-work-orders/work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="aac21-112">Refer to [Work order lifecycle states](../setup-for-work-orders/work-order-lifecycle-states.md) for more information.</span></span>

1. <span data-ttu-id="aac21-113">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="aac21-113">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="aac21-114">Selezionare l'ordine di lavoro e fare clic su **Giornali di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="aac21-114">Select the work order, and click **Journals**.</span></span>

3. <span data-ttu-id="aac21-115">Fare clic su **Copia da previsione** per trasferire le eventuali righe di previsione che possono essere associate all'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aac21-115">Click **Copy from forecast** to transfer any forecast lines that may be connected to the work order.</span></span> <span data-ttu-id="aac21-116">È possibile selezionare i tipi di consumo che si desidera trasferire.</span><span class="sxs-lookup"><span data-stu-id="aac21-116">You can select which consumption types you want to transfer.</span></span>

4. <span data-ttu-id="aac21-117">Se necessario, è possibile aggiungere ulteriori righe di consumo nella Scheda dettaglio pertinente facendo clic su **Aggiungi riga** e immettendo i dati nella riga.</span><span class="sxs-lookup"><span data-stu-id="aac21-117">If necessary, you can add more consumption lines on the relevant FastTab by clicking **Add line** and filling out data on the line.</span></span>

5. <span data-ttu-id="aac21-118">Fare clic su **Convalida giornali di registrazione** per convalidare le righe dei giornali di registrazione prima della registrazione.</span><span class="sxs-lookup"><span data-stu-id="aac21-118">Click **Validate journals** to validate the journal lines before posting.</span></span>

6. <span data-ttu-id="aac21-119">Fare clic su **Registra giornali** per registrare le righe dei giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="aac21-119">Click **Post journals** to post the journal lines.</span></span>

7. <span data-ttu-id="aac21-120">Dopo aver registrato i giornali di registrazione consumo, è possibile aggiornare lo stato del ciclo di vita dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aac21-120">After you've posted the consumption journals, you can update the work order lifecycle state.</span></span> <span data-ttu-id="aac21-121">Ad esempio, per indicare che l'ordine di lavoro è completato, è possibile aggiornare lo stato del ciclo di vita in "Finito".</span><span class="sxs-lookup"><span data-stu-id="aac21-121">For example, to indicate that the work order has been completed, you can update the lifecycle state to "Ended".</span></span>

    - <span data-ttu-id="aac21-122">Nel campo **Mostra** nella parte superiore della pagina **Giornali di registrazione ordine di lavoro**, selezionare le righe dei giornali di registrazione che si desidera visualizzare: **Tutto**, **Non registrato** o **Registrato**.</span><span class="sxs-lookup"><span data-stu-id="aac21-122">In the **Show** field at the top of the **Work order journals** page, select which journal lines you want to see: **All**, **Not posted**, or **Posted**.</span></span> <span data-ttu-id="aac21-123">I giornali di registrazione registrati presentano un segno di spunta nella casella di controllo **Registrato**.</span><span class="sxs-lookup"><span data-stu-id="aac21-123">Posted journals have a check mark in the **Posted** check box.</span></span>  
    - <span data-ttu-id="aac21-124">Quando si creano righe articolo nel giornale di registrazione di ordine di lavoro, le dimensioni prodotto e le dimensioni di tracciabilità correlate all'articolo sono trasferite automaticamente alla riga del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="aac21-124">When item lines are created in the work order journal, product dimensions and tracking dimensions related to the item are automatically transferred to the journal line.</span></span>  

<span data-ttu-id="aac21-125">La schermata seguente mostra un esempio di registrazioni di ore e articoli in un ordine di lavoro in **Giornali di registrazione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="aac21-125">The screenshot below shows an example of hour and item registrations on a work order in **Work order journals**.</span></span>

![Figura 1](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a><span data-ttu-id="aac21-127">Suddividere le ore negli ordini di lavoro con più processi di ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="aac21-127">Split hours on work orders with several work order jobs</span></span>

<span data-ttu-id="aac21-128">Se un ordine di lavoro contiene più processi di ordine di lavoro, è possibile registrare le ore lavorative utilizzando la funzionalità **Suddividi ore**, nel senso che la riga di registrazione di 1 ora può essere distribuita in modo uniforme in ogni processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aac21-128">If a work order contains several work order jobs, you can register work hours using the **Split hours** functionality, meaning one hour registration line can be distributed evenly on each work order job.</span></span>

1. <span data-ttu-id="aac21-129">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="aac21-129">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="aac21-130">Selezionare l'ordine di lavoro e fare clic su **Giornali di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="aac21-130">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="aac21-131">Selezionare la riga di registrazione ore che si desidera suddividere e fare clic su **Suddividi ore**.</span><span class="sxs-lookup"><span data-stu-id="aac21-131">Select the hour registration line you want to split, and click **Split hours**.</span></span>

4. <span data-ttu-id="aac21-132">Nella finestra di dialogo **Suddividi ore in processi di manutenzione ordine di lavoro**, il nome del lavoratore che ha effettuato l'accesso viene visualizzato automaticamente nel campo **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="aac21-132">In the **Split hours on work order maintenance jobs** dialog, the name of the worker who is logged in is automatically shown in the **Worker** field.</span></span> <span data-ttu-id="aac21-133">Se necessario, è possibile selezionare un altro lavoratore.</span><span class="sxs-lookup"><span data-stu-id="aac21-133">If required, you can select another worker.</span></span>

5. <span data-ttu-id="aac21-134">Selezionare una categoria per la registrazione ore nel campo **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="aac21-134">Select a category for the hour registration in the **Category** field.</span></span>

6. <span data-ttu-id="aac21-135">Nel campo **Ore** inserire il numero di ore da suddividere.</span><span class="sxs-lookup"><span data-stu-id="aac21-135">Insert number of work hours to be split in the **Hours** field.</span></span>

    ![Figura 2](media/02-consumption.png)

7. <span data-ttu-id="aac21-137">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aac21-137">Click **OK**.</span></span>

<span data-ttu-id="aac21-138">*Esempio:* nella schermata seguente sono visualizzate le righe del giornale di registrazione per un ordine di lavoro contenente tre processi di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aac21-138">*Example:* In the screenshot below, journal lines for a work order containing three work order jobs are shown.</span></span> <span data-ttu-id="aac21-139">La prima riga, contenente tre ore lavorative, è stata suddivisa e un'ora lavorativa è registrata in ciascun processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aac21-139">The first line, containing three work hours, has been split, and one work hour is registered on each work order job.</span></span> <span data-ttu-id="aac21-140">Dopo la creazione della registrazione delle tre ore, è necessario decidere cosa fare con la riga di registrazione ore originale (la prima riga nell'esempio).</span><span class="sxs-lookup"><span data-stu-id="aac21-140">After the three hour registration lines have been created, you decide what to do with the original hour registration line (the first line in the example).</span></span> <span data-ttu-id="aac21-141">È possibile tenerla così com'è oppure eliminarla.</span><span class="sxs-lookup"><span data-stu-id="aac21-141">You can keep it as is or delete it.</span></span> 

![Figura 3](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a><span data-ttu-id="aac21-143">Dimensioni finanziarie nelle registrazioni del consumo</span><span class="sxs-lookup"><span data-stu-id="aac21-143">Financial dimensions on consumption registrations</span></span>

<span data-ttu-id="aac21-144">Quando si eseguono registrazioni del consumo, le dimensioni finanziarie relative ai differenti tipi di registrazione vengono aggiunte alle registrazioni in una sequenza specifica.</span><span class="sxs-lookup"><span data-stu-id="aac21-144">When you make consumption registrations, financial dimensions related to the different registration types are added to the registrations in a specific sequence.</span></span> 

- <span data-ttu-id="aac21-145">*Registrazioni ore e spese:* innanzi tutto, vengono aggiunte le eventuali dimensioni finanziarie dall'intestazione del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="aac21-145">*Hour and Expense registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="aac21-146">Successivamente, vengono aggiunte le dimensioni finanziarie dal progetto di ordine di lavoro correlato.</span><span class="sxs-lookup"><span data-stu-id="aac21-146">Next, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="aac21-147">Infine, vengono aggiunte le dimensioni finanziarie dalla risorsa (lavoratore).</span><span class="sxs-lookup"><span data-stu-id="aac21-147">Finally, financial dimensions from the resource (worker) are added.</span></span>

- <span data-ttu-id="aac21-148">*Registrazioni articoli:* innanzi tutto, vengono aggiunte le eventuali dimensioni finanziarie dall'intestazione del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="aac21-148">*Item registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="aac21-149">Vengono quindi aggiunte le dimensioni finanziarie dal progetto di ordine di lavoro correlato.</span><span class="sxs-lookup"><span data-stu-id="aac21-149">Then, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="aac21-150">Successivamente, vengono aggiunte le dimensioni finanziarie dal sito.</span><span class="sxs-lookup"><span data-stu-id="aac21-150">Next, financial dimensions from the site are added.</span></span> <span data-ttu-id="aac21-151">Infine, vengono aggiunte le dimensioni finanziarie dall'articolo.</span><span class="sxs-lookup"><span data-stu-id="aac21-151">Finally, financial dimensions from the item are added.</span></span>

>[!NOTE]
><span data-ttu-id="aac21-152">Per tutti e tre i tipi di registrazione, viene convalidata la combinazione di dimensioni finanziarie e le combinazioni non valide vengono lasciate vuote.</span><span class="sxs-lookup"><span data-stu-id="aac21-152">For all three registration types, the financial dimension combination is validated, and invalid combinations are blanked.</span></span> <span data-ttu-id="aac21-153">Questa è la configurazione standard con altre app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="aac21-153">This is standard setup with other Finance and Operations apps.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]