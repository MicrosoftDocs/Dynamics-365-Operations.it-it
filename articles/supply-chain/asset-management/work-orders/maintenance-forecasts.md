---
title: Previsioni di manutenzione
description: In questo argomento vengono descritte le previsioni di manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1a416bbb79be3f25998d3c0da8d231d0df808685
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875738"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="a17b2-103">Previsioni di manutenzione</span><span class="sxs-lookup"><span data-stu-id="a17b2-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="a17b2-104">Quando si crea un ordine di lavoro, si creano processi di ordine di lavoro con i relativi cespiti e tipi di processo di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="a17b2-104">When you create a work order, you create work order jobs with related assets and maintenance job types.</span></span> <span data-ttu-id="a17b2-105">Quando si seleziona un tipo di processo di manutenzione contenente previsioni di manutenzione, queste vengono copiate automaticamente nell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a17b2-105">When you select a maintenance job type containing maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="a17b2-106">Esiste la possibilità di aggiungere o eliminare righe di previsione,</span><span class="sxs-lookup"><span data-stu-id="a17b2-106">You may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="a17b2-107">ma ciò dipende dall'impostazione dello stato del ciclo di vita di ordine di lavoro, dal tipo di progetto correlato e dalla regole di fase associate.</span><span class="sxs-lookup"><span data-stu-id="a17b2-107">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determines if you are able to add or edit forecast lines.</span></span> 

1. <span data-ttu-id="a17b2-108">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="a17b2-109">Selezionare l'ordine di lavoro nell'elenco e fare clic su **Previsione**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-109">Select the work order in the list, and click **Forecast**.</span></span> <span data-ttu-id="a17b2-110">In **Previsione di manutenzione ordine di lavoro**, vengono visualizzate le righe di previsione del tipo di processo di manutenzione selezionato nel processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a17b2-110">In **Work order maintenance forecast**, forecast lines from the maintenance job type selected on the work order job are displayed.</span></span>


## <a name="add-hours-forecast-to-a-work-order"></a><span data-ttu-id="a17b2-111">Aggiungere la previsione di ore a un ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="a17b2-111">Add hours forecast to a work order</span></span>

1. <span data-ttu-id="a17b2-112">Selezionare il processo di ordine di lavoro a cui si desidera aggiungere una previsione.</span><span class="sxs-lookup"><span data-stu-id="a17b2-112">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="a17b2-113">Nella Scheda dettaglio **Ore** fare clic su **Aggiungi** per creare una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="a17b2-113">On the **Hours** FastTab, click **Add** to create a new line.</span></span>

3. <span data-ttu-id="a17b2-114">Selezionare una categoria nel campo **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-114">Select a category in the **Category** field.</span></span>

4. <span data-ttu-id="a17b2-115">Immettere il numero di ore previste nel campo **Ore**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-115">Insert number of forecasted hours in the **Hours** field.</span></span>

5. <span data-ttu-id="a17b2-116">Nel campo **Proprietà riga**, selezionare il tipo di spese da utilizzare nella riga.</span><span class="sxs-lookup"><span data-stu-id="a17b2-116">In the **Line property** field, select the charge type to be used on the line.</span></span>


## <a name="add-items-forecast-to-a-work-order"></a><span data-ttu-id="a17b2-117">Aggiungere la previsione di articoli a un ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="a17b2-117">Add items forecast to a work order</span></span>

<span data-ttu-id="a17b2-118">Sono disponibili tre modi per aggiungere articoli a una previsione di manutenzione di ordine di lavoro: creando righe per articoli (pezzi di ricambio) non inclusi nell'elenco dei pezzi di ricambio o nel DBA cespiti, selezionando i pezzi di ricambio dall'elenco dei pezzi di ricambio approvato e selezionando articoli nel DBA cespiti.</span><span class="sxs-lookup"><span data-stu-id="a17b2-118">There are three ways to add items to a work order maintenance forecast: You can create lines for items (spare parts) that are not included in the spare parts list or asset BOM, you can select spare parts from the approved spare parts list, and you can select items from the asset BOM.</span></span>

1. <span data-ttu-id="a17b2-119">Selezionare il processo di ordine di lavoro a cui si desidera aggiungere una previsione.</span><span class="sxs-lookup"><span data-stu-id="a17b2-119">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="a17b2-120">Selezionare la Scheda dettaglio **Articoli**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-120">Select the **Items** FastTab.</span></span>

3. <span data-ttu-id="a17b2-121">Fare clic su **Aggiungi** per creare una nuova riga per un pezzo di ricambio non incluso nell'elenco dei pezzi di ricambio o nel DBA cespiti.</span><span class="sxs-lookup"><span data-stu-id="a17b2-121">Click **Add** to create a new line for a spare part that is not on the spare parts list or the asset BOM list.</span></span>

4. <span data-ttu-id="a17b2-122">Nel campo **Numero articolo**, selezionare l'articolo.</span><span class="sxs-lookup"><span data-stu-id="a17b2-122">Select the item in the **Item number** field.</span></span>

5. <span data-ttu-id="a17b2-123">Inserire la quantità nel campo **Quantità di vendita** e selezionare un'unità di quantità nel campo **Unità**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-123">Insert quantity in the **Sales quantity** field, and select a quantity unit in the **Unit** field.</span></span>

6. <span data-ttu-id="a17b2-124">Immettere la valuta e il prezzo di costo nei campi pertinenti e selezionare una **proprietà riga**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-124">Insert cost price and currency in the relevant fields, and select a **Line property**.</span></span>

7. <span data-ttu-id="a17b2-125">Se si desidera modificare l'elenco delle dimensioni visualizzate nelle righe degli articoli, fare clic su **Inventario** > **Visualizza dimensioni**, selezionare le dimensioni e impostare l'interruttore **Salva impostazione** su "Sì".</span><span class="sxs-lookup"><span data-stu-id="a17b2-125">If you want to change the list of dimensions displayed on the item lines, click **Inventory** > **Display dimensions**, select the dimensions, and select "Yes" on the **Save setup** toggle button.</span></span>

8. <span data-ttu-id="a17b2-126">Se si desidera aggiungere un pezzo di ricambio approvato alla previsione di manutenzione, fare clic su **Aggiungi pezzi di ricambio**, selezionare il pezzo di ricambio, modificare le informazioni correlate se necessario e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-126">If you want to add an approved spare part to the maintenance forecast, click **Add spare parts**, select the spare part, edit related information if required, and click **OK**.</span></span>

9. <span data-ttu-id="a17b2-127">Se si desidera aggiungere articoli del DBA cespiti alla previsione, fare clic su **Aggiungi articoli DBA**, selezionare l'articolo, modificare le informazioni correlate se necessario e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-127">If you want to add asset BOM items to the forecast, click **Add BOM items**, select the item, edit related information if required, and click **OK**.</span></span>

10. <span data-ttu-id="a17b2-128">Per ottenere una panoramica sull'utilizzo dell'articolo nella riga selezionata in Gestione cespiti in relazione a cespiti, valori predefiniti di tipo di processo di manutenzione, pezzi di ricambio e ordini di lavoro, fare clic su **Utilizzo dell'articolo**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-128">Click **Item where used** if you want to get an overview of where the item on the selected line is used in Asset Management in relation to assets, maintenance job type defaults, spare parts, and work orders.</span></span> 



## <a name="add-expense-forecast-to-a-work-order"></a><span data-ttu-id="a17b2-129">Aggiungere la previsione in spese a un ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="a17b2-129">Add expense forecast to a work order</span></span>

1. <span data-ttu-id="a17b2-130">In questo argomento viene descritto come aggiungere una previsione di spesa a un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a17b2-130">This topic explains how to add an expense forecast to a work order.</span></span> <span data-ttu-id="a17b2-131">Nella parte sinistra del modulo, selezionare il processo di ordine di lavoro a cui si desidera aggiungere una previsione.</span><span class="sxs-lookup"><span data-stu-id="a17b2-131">In the left-hand side of the form, select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="a17b2-132">Selezionare la Scheda dettaglio **Spese**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-132">Select the **Expense** FastTab.</span></span>

3. <span data-ttu-id="a17b2-133">Per creare una nuova riga, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-133">Click **Add** to create a new line.</span></span>

4. <span data-ttu-id="a17b2-134">Selezionare una categoria nel campo **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-134">Select a category in the **Category** field.</span></span>

5. <span data-ttu-id="a17b2-135">Nel campo **Quantità** immettere la quantità.</span><span class="sxs-lookup"><span data-stu-id="a17b2-135">Insert quantity in the **Quantity** field.</span></span>

6. <span data-ttu-id="a17b2-136">Immettere il prezzo di costo, la valuta di vendita e il prezzo di vendita nei campi pertinenti.</span><span class="sxs-lookup"><span data-stu-id="a17b2-136">Insert cost price, sales currency, and sales price in the relevant fields.</span></span>

7. <span data-ttu-id="a17b2-137">Nel campo **Proprietà riga**, selezionare il tipo di spese da utilizzare nella riga.</span><span class="sxs-lookup"><span data-stu-id="a17b2-137">In the **Line property** field, select the charge type to be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="a17b2-138">Nella Scheda dettaglio **Totali previsione di manutenzione**, è possibile visualizzare una panoramica del numero di righe create in ogni scheda per il processo di ordine di lavoro selezionato e per l'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a17b2-138">On the **Maintenance forecast totals** FastTab, you can see an overview of the number of lines created on each tab, for the selected work order job and for the work order.</span></span> <span data-ttu-id="a17b2-139">Inoltre, è possibile visualizzare una somma delle ore lavorative previste per l'ordine di lavoro e il processo di ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a17b2-139">Also, you can see a sum of forecasted work hours for the work order job and for the work order.</span></span>

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="a17b2-141">Aggiornamento automatico delle previsioni dell'ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="a17b2-141">Automatic update of work order forecasts</span></span>

<span data-ttu-id="a17b2-142">In Gestione cespiti, è possibile aggiornare automaticamente qualsiasi modifica alle previsioni dell'ordine di lavoro relative a costi orari, costi degli articoli e spese, che sono state aggiornati in altri moduli di Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a17b2-142">In Asset Management, you can automatically update any changes in work order forecasts regarding hour costs, item costs, and expenses, which have been updated in other modules in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="a17b2-143">Ciò garantisce l'utilizzo degli ultimi prezzi di costo nelle previsioni dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a17b2-143">This is done to ensure that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="a17b2-144">È inoltre possibile effettuare aggiornamenti simili per le [previsioni del tipo di processo di manutenzione](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="a17b2-144">It is also possible to make similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="a17b2-145">Fare clic su **Gestione cespiti** > **Periodico** > **Previsione** > **Aggiorna previsione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-145">Click **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="a17b2-146">Nella finestra di dialogo a discesa **Aggiorna previsione ordine di lavoro**, è possibile aggiungere selezioni relative a specifici ordini di lavoro o processi di ordine di lavoro se necessario.</span><span class="sxs-lookup"><span data-stu-id="a17b2-146">In the **Update work order forecast** drop-down dialog, you can add selections regarding specific work orders or work order jobs, if required.</span></span> <span data-ttu-id="a17b2-147">Fare clic su **Filtro** per eseguire tali selezioni.</span><span class="sxs-lookup"><span data-stu-id="a17b2-147">Click **Filter** to make those selections.</span></span>

3. <span data-ttu-id="a17b2-148">Se necessario, è possibile impostare l'aggiornamento automatico come processo batch nella Scheda dettaglio **Esecuzione in background**.</span><span class="sxs-lookup"><span data-stu-id="a17b2-148">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

4. <span data-ttu-id="a17b2-149">Fare clic su **OK** per avviare l'aggiornamento delle previsioni.</span><span class="sxs-lookup"><span data-stu-id="a17b2-149">Click **OK** to start the forecast update.</span></span>


![Figura 2](media/07-work-orders.png)

