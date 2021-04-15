---
title: Aggiornare un budget di manutenzione
description: In questo argomento viene illustrato come aggiornare un budget di manutenzione in Gestione cespiti.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 01620e1cca17d3c2b08b3abcdf9a4482693f0409
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809832"
---
# <a name="update-maintenance-budgets"></a><span data-ttu-id="97b43-103">Aggiornare un budget di manutenzione</span><span class="sxs-lookup"><span data-stu-id="97b43-103">Update maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="97b43-104">La pagina **Righe budget di manutenzione** visualizza tutte le righe di budget create per il budget selezionato nella pagina **Budget di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="97b43-104">The **Maintenance budget lines** page shows all the budget lines that have been created for the budget that is selected on the **Maintenance budgets** page.</span></span> <span data-ttu-id="97b43-105">Per ulteriori informazioni, vedere [Creare budget di manutenzione](create-maintenance-budget.md). È possibile ricalcolare e rettificare le righe del budget di manutenzione fino a che il budget di manutenzione non viene approvato.</span><span class="sxs-lookup"><span data-stu-id="97b43-105">(For more information, see [Create maintenance budgets](create-maintenance-budget.md).) You can recalculate and adjust maintenance budget lines until the maintenance budget is approved.</span></span> <span data-ttu-id="97b43-106">Una volta trascorso il periodo di budget e dopo aver registrato i costi in Gestione cespiti, è possibile aggiornare anche le righe di budget con i costi effettivi.</span><span class="sxs-lookup"><span data-stu-id="97b43-106">After the budget period has passed, and costs have been posted in Asset Management, you can also update the budget lines with actual costs.</span></span>

## <a name="recalculate-a-maintenance-budget"></a><span data-ttu-id="97b43-107">Ricalcolare un budget di manutenzione</span><span class="sxs-lookup"><span data-stu-id="97b43-107">Recalculate a maintenance budget</span></span>

<span data-ttu-id="97b43-108">È possibile ricalcolare un budget di manutenzione nella pagina **Righe budget di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="97b43-108">You can recalculate a maintenance budget on the **Maintenance budget lines** page.</span></span> <span data-ttu-id="97b43-109">Quando si ricalcola un budget di manutenzione, le righe di budget esistenti vengono eliminate e viene eseguito un nuovo calcolo.</span><span class="sxs-lookup"><span data-stu-id="97b43-109">When you recalculate a maintenance budget, the existing budget lines are deleted, and a new calculation is done.</span></span>

1. <span data-ttu-id="97b43-110">Nella pagina **Righe budget di manutenzione**, selezionare **Ricalcola**.</span><span class="sxs-lookup"><span data-stu-id="97b43-110">On the **Maintenance budget lines** page, select **Recalculate**.</span></span>
2. <span data-ttu-id="97b43-111">Nella finestra di dialogo **Ricalcola budget**, apportare le modifiche necessarie per il nuovo calcolo e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="97b43-111">In the **Recalculate budget** dialog box, make the required changes for the new calculation, and then select **OK**.</span></span>

<span data-ttu-id="97b43-112">Le nuove righe di budget vengono create in base ai valori impostati.</span><span class="sxs-lookup"><span data-stu-id="97b43-112">New budget lines are created according to the values that you set.</span></span>

## <a name="adjust-budget-lines"></a><span data-ttu-id="97b43-113">Modificare le righe di budget</span><span class="sxs-lookup"><span data-stu-id="97b43-113">Adjust budget lines</span></span>

<span data-ttu-id="97b43-114">Anziché ricalcolare l'intero budget di manutenzione, è possibile modificare le righe selezionate associate ai costi in budget.</span><span class="sxs-lookup"><span data-stu-id="97b43-114">Instead of recalculating the whole maintenance budget, you can adjust selected lines that are related to budget costs.</span></span>

1. <span data-ttu-id="97b43-115">Nella pagina **Righe budget di manutenzione**, selezionare le righe per le quali aggiornare i costi in budget.</span><span class="sxs-lookup"><span data-stu-id="97b43-115">On the **Maintenance budget lines** page, select the lines to update the budget cost for.</span></span>
2. <span data-ttu-id="97b43-116">Selezionare **Rettifica**.</span><span class="sxs-lookup"><span data-stu-id="97b43-116">Select **Adjust**.</span></span>
3. <span data-ttu-id="97b43-117">Per aggiungere un importo alle righe selezionate, selezionare la casella di controllo **Aggiungi costo** e immettere il valore nel campo **Aggiungi valore**.</span><span class="sxs-lookup"><span data-stu-id="97b43-117">To add an amount to the selected lines, select the **Add cost** check box, and then enter the value in the **Add value** field.</span></span>
4. <span data-ttu-id="97b43-118">Per moltiplicare per un fattore il costo in budget nelle righe di budget selezionate, selezionare la casella di controllo **Moltiplica costo** e immettere il fattore nel campo **Valore di moltiplicazione**.</span><span class="sxs-lookup"><span data-stu-id="97b43-118">To multiply the budget cost on the selected budget lines by a factor, select the **Multiply cost** check box, and enter the factor in the **Multiply value** field.</span></span>

    <span data-ttu-id="97b43-119">Ad esempio, se si immette **1,2** nel campo **Valore di moltiplicazione**, i costi in budget nelle righe selezionate aumentano del 20%.</span><span class="sxs-lookup"><span data-stu-id="97b43-119">For example, if you enter **1.2** in the **Multiply value** field, you increase the budget cost on the selected lines by 20 percent.</span></span> <span data-ttu-id="97b43-120">Se si immette **0,7**, si riducono i costi in budget nelle righe selezionate del 30%.</span><span class="sxs-lookup"><span data-stu-id="97b43-120">If you enter **0.7**, you reduce the budget cost on the selected lines by 30 percent.</span></span>

5. <span data-ttu-id="97b43-121">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="97b43-121">Select **OK**.</span></span>

<span data-ttu-id="97b43-122">Le righe di budget selezionate vengono aggiornate in base al valori impostati nel passaggio 3 o 4.</span><span class="sxs-lookup"><span data-stu-id="97b43-122">The selected budget lines are updated according to the values that you set in step 3 or 4.</span></span>

## <a name="update-actual-costs"></a><span data-ttu-id="97b43-123">Aggiornare i cosit effettivi</span><span class="sxs-lookup"><span data-stu-id="97b43-123">Update actual costs</span></span>

<span data-ttu-id="97b43-124">Una volta trascorse le date nelle righe di budget e dopo aver registrato i costi effettivi in Gestione cespiti, è possibile aggiornare i costi effettivi nel budget di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="97b43-124">After the dates on the budget lines have passed, and actual costs have been posted in Asset Management, you can update the actual costs on the maintenance budget.</span></span>

1. <span data-ttu-id="97b43-125">Nella pagina **Righe budget di manutenzione**, selezionare **Aggiorna costo**.</span><span class="sxs-lookup"><span data-stu-id="97b43-125">On the **Maintenance budget lines** page, select **Update cost**.</span></span>
2. <span data-ttu-id="97b43-126">Nella finestra di dialogo **Calcola costo effettivo**, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="97b43-126">In the **Calculate actual cost** dialog box, select **OK**.</span></span>

<span data-ttu-id="97b43-127">I campi **Costo effettivo** nelle righe di budget vengono aggiornati se i costi effettivi sono stati registrati.</span><span class="sxs-lookup"><span data-stu-id="97b43-127">The **Actual cost** fields on the budget lines are updated if actual costs have been posted.</span></span> <span data-ttu-id="97b43-128">Nuove righe di budget potrebbero essere generate nel caso siano stati creati nuovi tipi di cespite a partire dalla creazione del budget e se questi tipi di cespite sono stati utilizzati nei cespiti per i quali sono stati creati gli ordini di lavoro e sono stati registrati i costi associati.</span><span class="sxs-lookup"><span data-stu-id="97b43-128">New budget lines might be generated if new asset types have been created since you created the budget, and if those asset types have been used on assets that work orders have been created for and related costs have been posted for.</span></span> <span data-ttu-id="97b43-129">Le nuove righe di budget mostrano solo i costi effettivi, poiché pet tali righe non sono stati calcolati costi in budget.</span><span class="sxs-lookup"><span data-stu-id="97b43-129">New budget lines show only actual costs, because no budget costs were calculated for them.</span></span>

> [!NOTE]
> <span data-ttu-id="97b43-130">Per visualizzare una panoramica dei costi effettivi suddivisi in costi preventivi, correttivi e di investimento, è possibile eseguire un calcolo per lo stesso periodo nella pagina **Controllo costi cespiti**.</span><span class="sxs-lookup"><span data-stu-id="97b43-130">To see an overview of actual costs divided into preventive, corrective, and investment costs, you can do a calculation for the same period on the **Asset cost control** page.</span></span> 

## <a name="manually-add-budget-lines"></a><span data-ttu-id="97b43-131">Aggiungere manualmente righe di budget.</span><span class="sxs-lookup"><span data-stu-id="97b43-131">Manually add budget lines</span></span>

<span data-ttu-id="97b43-132">Nella pagina **Righe budget di manutenzione**, è possibile aggiungere manualmente una nuova riga di budget selezionando **Nuova** e quindi effettuando selezioni nella riga.</span><span class="sxs-lookup"><span data-stu-id="97b43-132">On the **Maintenance budget lines** page, you can manually add a new budget line by selecting **New** and then making selections on the line.</span></span> <span data-ttu-id="97b43-133">Di seguito sono riportati alcuni esempi di situazioni in cui tale approccio può risultare utile:</span><span class="sxs-lookup"><span data-stu-id="97b43-133">Here are some examples of situations where this approach might be useful:</span></span>

- <span data-ttu-id="97b43-134">Il rifornimento di alcuni cespiti è in fase di pianificazione, ma i processi correlati non sono ancora stati creati in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="97b43-134">You know that refurbishment of some assets is currently in the planning phase, but related jobs haven't yet been created in Asset Management.</span></span> <span data-ttu-id="97b43-135">Tuttavia, si desidera includere i costi in budget per quei processi nel budget di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="97b43-135">However, you want budget costs for those jobs to be included in the maintenance budget.</span></span>
- <span data-ttu-id="97b43-136">Nuovi cespiti o tipi di cespite sono stati creati a partire dalla creazione del budget di manutenzione, ma i piani di manutenzione non sono ancora stati impostati in tali cespiti o tipi di cespite.</span><span class="sxs-lookup"><span data-stu-id="97b43-136">New assets or asset types have been created since you made the maintenance budget, but maintenance plans haven't yet been set up on those assets or asset types.</span></span> <span data-ttu-id="97b43-137">Tuttavia, si desidera includere i costi in budget per quei tipi di cespite nel budget di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="97b43-137">However, you want budget costs for those asset types to be included in the maintenance budget.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]