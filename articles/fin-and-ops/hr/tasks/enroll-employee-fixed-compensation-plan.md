--- 
title: Iscrivere un dipendente a un piano di retribuzione fisso
description: "Il responsabile di retribuzione e benefit può assegnare i dipendenti a piani di retribuzione fissa per la gestione delle retribuzioni base."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 88630311a4326508fa69a8938fa216f1a45ba089
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="78265-103">Iscrivere un dipendente a un piano di retribuzione fisso</span><span class="sxs-lookup"><span data-stu-id="78265-103">Enroll an employee in a fixed compensation plan</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="78265-104">Il responsabile di retribuzione e benefit può assegnare i dipendenti a piani di retribuzione fissa per la gestione delle retribuzioni base.</span><span class="sxs-lookup"><span data-stu-id="78265-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="78265-105">In questa procedura si presuppone che un piano fisso sia stato creato e sia attivo e che le regole di idoneità sono state impostate per il piano.</span><span class="sxs-lookup"><span data-stu-id="78265-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="78265-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="78265-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="78265-107">Per avviare la procedura, andare a Risorse umane > Lavoratori > Dipendenti > Retribuzione > Piano fisso</span><span class="sxs-lookup"><span data-stu-id="78265-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="78265-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="78265-108">Click New.</span></span>
2. <span data-ttu-id="78265-109">Nel campo Azione selezionare un'azione di retribuzione fissa di tipo Assunzione/Riassunzione per descrivere la modifica della retribuzione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="78265-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="78265-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="78265-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="78265-111">Nel campo Posizione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="78265-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="78265-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="78265-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="78265-113">Il livello visualizzato deriva dal livello retributivo della mansione nella posizione.</span><span class="sxs-lookup"><span data-stu-id="78265-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="78265-114">Il livello deve essere impostato sulla mansione prima che la retribuzione possa essere assegnata al dipendente.</span><span class="sxs-lookup"><span data-stu-id="78265-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="78265-115">Nel campo Piano selezionare il piano di retribuzione fissa per il dipendente.</span><span class="sxs-lookup"><span data-stu-id="78265-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="78265-116">La ricerca del piano viene filtrata per indicare solo i piani per cui il dipendente è idoneo in base alle regole di idoneità.</span><span class="sxs-lookup"><span data-stu-id="78265-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="78265-117">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="78265-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="78265-118">Le date di validità e di scadenza per la retribuzione derivano per impostazione predefinita dalle date di inizio e di fine dell'assegnazione di posizione del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="78265-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="78265-119">È possibile modificare tali date in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="78265-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="78265-120">Se il piano di retribuzione fissa è un piano di tipo Fase, selezionare la fase contenente la tariffa retributiva corretta per il dipendente.</span><span class="sxs-lookup"><span data-stu-id="78265-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="78265-121">Se il piano di retribuzione fissa è un piano di tipo Fascia o Scala, immettere la tariffa retributiva per il dipendente.</span><span class="sxs-lookup"><span data-stu-id="78265-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="78265-122">La tariffa retributiva verrà convalidata rispetto alle impostazioni di tolleranza per il piano e ai punti di riferimento minimo e massimo per il livello retributivo della mansione.</span><span class="sxs-lookup"><span data-stu-id="78265-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="78265-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="78265-123">Click OK.</span></span>


