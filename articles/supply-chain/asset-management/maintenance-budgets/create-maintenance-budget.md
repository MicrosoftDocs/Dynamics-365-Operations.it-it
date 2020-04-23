---
title: Creare budget di manutenzione
description: In questo argomento viene illustrato come creare un budget di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: aa373a1a15c19154e6c822c3a962c2b43b8d9e10
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205301"
---
# <a name="create-maintenance-budgets"></a><span data-ttu-id="96243-103">Creare budget di manutenzione</span><span class="sxs-lookup"><span data-stu-id="96243-103">Create maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 



<span data-ttu-id="96243-104">I budget di manutenzione sono utilizzati per fornire una panoramica dei costi previsti per la manutenzione preventiva.</span><span class="sxs-lookup"><span data-stu-id="96243-104">Maintenance budgets are used to provide an overview of expected costs for preventive maintenance.</span></span> <span data-ttu-id="96243-105">Le righe di budget vengono calcolate in base alle righe di programma di manutenzione che hanno una data di inizio prevista durante il periodo di budget.</span><span class="sxs-lookup"><span data-stu-id="96243-105">Budget lines are calculated based on maintenance schedule lines that have an expected start date during the budget period.</span></span>

<span data-ttu-id="96243-106">I budget di manutenzione sono basati sui tipi di costo utilizzati in Gestione cespiti: **Preventivo**, **Correttivo** e **Investimento**.</span><span class="sxs-lookup"><span data-stu-id="96243-106">Maintenance budgets are based on the cost types that are used in Asset Management: **Preventive**, **Corrective**, and **Investment**.</span></span> <span data-ttu-id="96243-107">I costi in budget della manutenzione degli investimenti sono inclusi per i cespiti attivi che hanno una data di sostituzione durante il periodo di budget e un valore di sostituzione correlato.</span><span class="sxs-lookup"><span data-stu-id="96243-107">Budget costs for investment maintenance are included for active assets that have a replacement date during the budget period and a related replacement value.</span></span> <span data-ttu-id="96243-108">I costi in budget per la manutenzione correttiva sono inclusi se una data correttiva passata è inclusa nel calcolo del budget.</span><span class="sxs-lookup"><span data-stu-id="96243-108">Budget costs for corrective maintenance are included if a past corrective date is included in the budget calculation.</span></span> <span data-ttu-id="96243-109">In tal caso, i costi correttivi di un periodo precedente vengono calcolati per lo stesso periodo futuro per il quale si calcola il budget di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="96243-109">In that case, corrective costs from an earlier period are calculated for the same future period that you calculate the maintenance budget for.</span></span>

## <a name="create-a-maintenance-budget"></a><span data-ttu-id="96243-110">Creare un budget di manutenzione</span><span class="sxs-lookup"><span data-stu-id="96243-110">Create a maintenance budget</span></span>

1. <span data-ttu-id="96243-111">Selezionare **Gestione cespiti** \> **Richieste di informazioni** \> **Budget di manutenzione** \> **Budget**.</span><span class="sxs-lookup"><span data-stu-id="96243-111">Select **Asset management** \> **Inquiries** \> **Maintenance budget** \> **Budget**.</span></span>
2. <span data-ttu-id="96243-112">Selezionare **Crea budget**.</span><span class="sxs-lookup"><span data-stu-id="96243-112">Select **Create budget**.</span></span>
3. <span data-ttu-id="96243-113">Nel campo **Budget di manutenzione** immettere un ID budget.</span><span class="sxs-lookup"><span data-stu-id="96243-113">In the **Maintenance budget** field, enter a budget ID.</span></span>
4. <span data-ttu-id="96243-114">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="96243-114">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="96243-115">Nella Scheda dettaglio **Periodo**, nei campi **Dal** e **Al**, immettere le date di inizio e fine del periodo di budget.</span><span class="sxs-lookup"><span data-stu-id="96243-115">On the **Period** FastTab, in the **From date** and **To date** fields, enter the start and end dates of the budget period.</span></span>
5. <span data-ttu-id="96243-116">Per includere i costi in budget correttivi calcolati in base ai costi effettivi di un periodo precedente, nel campo **Correttivo da data**, immettere la data di inizio del periodo a partire dal quale i costi devono essere inclusi.</span><span class="sxs-lookup"><span data-stu-id="96243-116">To include corrective budget costs that are calculated on the basis of actual costs from a previous period, in the **Corrective from date** field, enter the start date of the period that those costs should be included from.</span></span>
6. <span data-ttu-id="96243-117">A seconda del livello di dettagli necessario nel budget, impostare le opzioni pertinenti nelle cinque Schede dettaglio **Raggruppa per**.</span><span class="sxs-lookup"><span data-stu-id="96243-117">Depending on the level of detail that is required in the budget, set the relevant options on the five **Group by** FastTabs.</span></span>
7. <span data-ttu-id="96243-118">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="96243-118">Select **OK**.</span></span>
8. <span data-ttu-id="96243-119">Selezionare **Righe budget** per aprire la pagina **Righe budget di manutenzione**, in cui è possibile visualizzare tutte le righe di budget create per il periodo.</span><span class="sxs-lookup"><span data-stu-id="96243-119">Select **Budget lines** to open **Maintenance budget lines** page, where you can view all the budget lines that have been created for the period.</span></span>
9. <span data-ttu-id="96243-120">Per approvare il budget, selezionarlo nella pagina **Budget di manutenzione** e quindi selezionare **Approva**.</span><span class="sxs-lookup"><span data-stu-id="96243-120">To approve the budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="96243-121">Quindi, nella finestra di dialogo **Approva budget** selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="96243-121">Then, in the **Approve budget** dialog box, select **OK**.</span></span> <span data-ttu-id="96243-122">Il nome dell'utente viene immesso nel campo **Approvato da** della pagina **Budget di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="96243-122">Your name is entered in the **Approved by** field on the **Maintenance budgets** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="96243-123">Dopo aver approvato un budget di manutenzione, non è possibile ricalcolare o rettificare le righe correlate nella pagina **Righe budget di manutenzione** a meno che non si rimuova dapprima l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="96243-123">After you've approved a maintenance budget, you can't recalculate or adjust the related lines on the **Maintenance budget lines** page unless you first remove the approval.</span></span> <span data-ttu-id="96243-124">Per rimuovere l'approvazione di un budget di manutenzione, selezionarlo nella pagina **Budget di manutenzione** e quindi selezionare **Approva**.</span><span class="sxs-lookup"><span data-stu-id="96243-124">To remove the approval of a maintenance budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="96243-125">Quindi, nella finestra di dialogo **Approva budget** selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="96243-125">Then, in the **Approve budget** dialog box, select **OK**.</span></span>

![Budget di manutenzione](media/01-maintenance-budgets.png)

<span data-ttu-id="96243-127">È anche possibile creare un nuovo budget di manutenzione copiando un budget esistente.</span><span class="sxs-lookup"><span data-stu-id="96243-127">You can also create a new maintenance budget by copying an existing budget.</span></span> <span data-ttu-id="96243-128">Nella pagina **Budget di manutenzione** selezionare il budget da copiare e quindi **Approva**.</span><span class="sxs-lookup"><span data-stu-id="96243-128">On the **Maintenance budgets** page, select the budget to copy, and then select **Copy**.</span></span> <span data-ttu-id="96243-129">Questo approccio è utile se, ad esempio, è stato creato un budget per un mese e si desidera copiarlo in altri mesi.</span><span class="sxs-lookup"><span data-stu-id="96243-129">This approach is useful if, for example, you've created a budget for one month and want to copy it to other months.</span></span>

> [!NOTE]
> <span data-ttu-id="96243-130">Il budget di manutenzione calcola solo i costi in budget basati sulle righe di programma di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="96243-130">The maintenance budget calculates only budget costs based on maintenance schedule lines.</span></span> <span data-ttu-id="96243-131">Per calcolare i costi effettivi per lo stesso periodo, è possibile effettuare tale calcolo nella pagina **Controllo costo dei cespiti**.</span><span class="sxs-lookup"><span data-stu-id="96243-131">To calculate actual costs for the same period, you can do that calculation on the **Asset cost control** page.</span></span> 
