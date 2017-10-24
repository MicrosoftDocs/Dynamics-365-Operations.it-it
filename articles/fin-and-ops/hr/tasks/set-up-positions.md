--- 
title: Impostare le posizioni
description: Le posizioni sono un elemento importante del livello inferiore di una gerarchia organizzativa.
author: DarinKramer
manager: AnnBe
ms.date: 06/22/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c902f532e189753a375d4b48edd9ef0b6d74020e
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-positions"></a><span data-ttu-id="9db14-103">Impostare le posizioni</span><span class="sxs-lookup"><span data-stu-id="9db14-103">Set up positions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9db14-104">Le posizioni sono un elemento importante del livello inferiore di una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="9db14-104">Positions are an important element of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="9db14-105">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="9db14-105">A position is an individual instance of a job.</span></span> <span data-ttu-id="9db14-106">Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite".</span><span class="sxs-lookup"><span data-stu-id="9db14-106">For example, the position, “Sales manager (East),” is one of the positions that is associated with the job, “Sales manager.”</span></span> <span data-ttu-id="9db14-107">Una posizione esiste in un reparto e può avere associato solo un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="9db14-107">A position exists in a department and may have only one worker associated with it.</span></span> <span data-ttu-id="9db14-108">In questa attività eseguiremo i passaggi necessari per creare una posizione.</span><span class="sxs-lookup"><span data-stu-id="9db14-108">In this task we will walk through the steps required to create a position.</span></span> <span data-ttu-id="9db14-109">Questa procedura è destinata agli specialisti delle risorse umane.</span><span class="sxs-lookup"><span data-stu-id="9db14-109">This procedure is intended for Human Resources Specialists.</span></span>

1. <span data-ttu-id="9db14-110">Fare clic su Gestione forza lavoro.</span><span class="sxs-lookup"><span data-stu-id="9db14-110">Click Workforce management.</span></span>
2. <span data-ttu-id="9db14-111">Fare clic su Posizioni aperte.</span><span class="sxs-lookup"><span data-stu-id="9db14-111">Click Open positions.</span></span>
3. <span data-ttu-id="9db14-112">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9db14-112">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="9db14-113">Nel campo Mansione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-113">In the Job field, enter or select a value.</span></span>
    * <span data-ttu-id="9db14-114">La descrizione mansione, il titolo e il fattore di impiego equivalente al tempo pieno verranno automaticamente copiati dalla mansione selezionata alla posizione.</span><span class="sxs-lookup"><span data-stu-id="9db14-114">The Job description, title, and full-time equivalent employment factor are automatically copied from the selected job into the position.</span></span>  
5. <span data-ttu-id="9db14-115">ResolveChanges per il processo.</span><span class="sxs-lookup"><span data-stu-id="9db14-115">ResolveChanges the Job.</span></span>
6. <span data-ttu-id="9db14-116">Fare clic su Crea posizione.</span><span class="sxs-lookup"><span data-stu-id="9db14-116">Click Create position.</span></span>
7. <span data-ttu-id="9db14-117">Nel campo Reparto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-117">In the Department field, enter or select a value.</span></span>
8. <span data-ttu-id="9db14-118">Nel campo Tipo di posizione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-118">In the Position type field, enter or select a value.</span></span>
9. <span data-ttu-id="9db14-119">Nel campo Retribuzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-119">In the Compensation region field, enter or select a value.</span></span>
    * <span data-ttu-id="9db14-120">Il campo Paese di retribuzione determina le regole di idoneità di retribuzione e i budget per incentivi fissi applicabili a un dipendente in quella posizione.</span><span class="sxs-lookup"><span data-stu-id="9db14-120">The Compensation region field determines the compensation eligibility rules and fixed increase budgets that apply to an employee in that position.</span></span>  
10. <span data-ttu-id="9db14-121">Nel campo Disponibile per l'assegnazione immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="9db14-121">In the Available for assignment field, enter a date and time.</span></span>
11. <span data-ttu-id="9db14-122">Espandere la sezione Durata posizione.</span><span class="sxs-lookup"><span data-stu-id="9db14-122">Expand the Position duration section.</span></span>
    * <span data-ttu-id="9db14-123">La durata della posizione viene immessa per impostazione predefinita in base alle date di attivazione e pensionamento immesse in precedenza</span><span class="sxs-lookup"><span data-stu-id="9db14-123">Position duration is entered by default based on activation and retirement dates entered earlier</span></span>  
12. <span data-ttu-id="9db14-124">Espandere la sezione Subordinato a.</span><span class="sxs-lookup"><span data-stu-id="9db14-124">Expand the Reports to position section.</span></span>
    * <span data-ttu-id="9db14-125">Quando si assegna un lavoratore a una posizione che riporta a un'altra posizione, viene creata una relazione gerarchica diretta tra i lavoratori assegnati alle due posizioni.</span><span class="sxs-lookup"><span data-stu-id="9db14-125">When you assign a worker to a position that reports to another position, you create a direct reporting relationship between the workers who are assigned to the two positions.</span></span>  
13. <span data-ttu-id="9db14-126">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9db14-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="9db14-127">Nel campo Subordinato a immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-127">In the Reports to field, enter or select a value.</span></span>
15. <span data-ttu-id="9db14-128">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="9db14-128">Click Create.</span></span>
16. <span data-ttu-id="9db14-129">Espandere la sezione Assegnazione lavoratore.</span><span class="sxs-lookup"><span data-stu-id="9db14-129">Expand the Worker assignment section.</span></span>
17. <span data-ttu-id="9db14-130">Espandere la sezione Relazioni.</span><span class="sxs-lookup"><span data-stu-id="9db14-130">Expand the Relationships section.</span></span>
    * <span data-ttu-id="9db14-131">Se l'organizzazione utilizza una gerarchia a matrice o un'altra gerarchia personalizzata, è possibile impostare i tipi di gerarchia delle posizioni e aggiungere le relazioni gerarchiche alle posizioni per ogni tipo di gerarchia impostata.</span><span class="sxs-lookup"><span data-stu-id="9db14-131">If your organization uses a matrix hierarchy or another custom hierarchy, you can set up position hierarchy types and then add reporting relationships to positions for each hierarchy type that you set up.</span></span>  
18. <span data-ttu-id="9db14-132">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9db14-132">Click Add.</span></span>
19. <span data-ttu-id="9db14-133">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9db14-133">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="9db14-134">Nel campo Nome gerarchia immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-134">In the Hierarchy name field, enter or select a value.</span></span>
21. <span data-ttu-id="9db14-135">Nel campo Subordinato a immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-135">In the Reports to position field, enter or select a value.</span></span>
22. <span data-ttu-id="9db14-136">Espandere la sezione Retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="9db14-136">Expand the Payroll section.</span></span>
23. <span data-ttu-id="9db14-137">Nel campo Ciclo retributivo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-137">In the Pay cycle field, enter or select a value.</span></span>
24. <span data-ttu-id="9db14-138">Nel campo Pagato da immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-138">In the Paid by field, enter or select a value.</span></span>
25. <span data-ttu-id="9db14-139">Nel campo Ore regolari annuali immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="9db14-139">In the Annual regular hours field, enter a number.</span></span>
    * <span data-ttu-id="9db14-140">Questo è il numero di ore pagate regolarmente che il lavoratore in questa posizione dovrà lavorare ogni anno.</span><span class="sxs-lookup"><span data-stu-id="9db14-140">This is the number of regularly paid hours that the worker in this position is expected to work each year.</span></span>  
26. <span data-ttu-id="9db14-141">Espandere la sezione Sindacato.</span><span class="sxs-lookup"><span data-stu-id="9db14-141">Expand the Labor union section.</span></span>
27. <span data-ttu-id="9db14-142">Comprimere la sezione Sindacato.</span><span class="sxs-lookup"><span data-stu-id="9db14-142">Collapse the Labor union section.</span></span>
28. <span data-ttu-id="9db14-143">Espandere la sezione Dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="9db14-143">Expand the Financial dimensions section.</span></span>
29. <span data-ttu-id="9db14-144">Nel campo Modello di distribuzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-144">In the Distribution template field, enter or select a value.</span></span>
30. <span data-ttu-id="9db14-145">Nel campo Reparto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9db14-145">In the Department field, enter or select a value.</span></span>
31. <span data-ttu-id="9db14-146">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9db14-146">Click Save.</span></span>


