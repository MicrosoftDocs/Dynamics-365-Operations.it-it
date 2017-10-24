--- 
title: Impostare criteri per le gerarchie di categorie di approvvigionamento
description: Utilizzare questa procedura per impostare le regole per ordinare prodotti in una categoria.
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 50764f99be04d27e04047824f870e724336cb452
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a><span data-ttu-id="04e2e-103">Impostare criteri per le gerarchie di categorie di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="04e2e-103">Set up policies for procurement category hierarchies</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="04e2e-104">Utilizzare questa procedura per impostare le regole per ordinare prodotti in una categoria.</span><span class="sxs-lookup"><span data-stu-id="04e2e-104">Use this procedure to set up rules for ordering products in a category.</span></span> <span data-ttu-id="04e2e-105">Le regole vengono definite per criteri di acquisto specifici.</span><span class="sxs-lookup"><span data-stu-id="04e2e-105">The rules are defined for a specific purchasing policy.</span></span> <span data-ttu-id="04e2e-106">La regola di accesso alle categorie determina le categorie di approvvigionamento a cui i dipendenti hanno accesso quando creano una richiesta.</span><span class="sxs-lookup"><span data-stu-id="04e2e-106">The category access rule controls which procurement categories employees have access to when they create a requisition.</span></span> <span data-ttu-id="04e2e-107">Quando viene creata una richiesta, i criteri di acquisto e la regola di accesso alle categorie da applicare vengono determinati dalla persona giuridica e dall'unità operativa a cui il dipendente appartiene.</span><span class="sxs-lookup"><span data-stu-id="04e2e-107">When a requisition is being created, the purchasing policy and category access rule that should be applied are determined by the legal entity and the operational unit that the employee belongs to.</span></span> <span data-ttu-id="04e2e-108">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="04e2e-108">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="04e2e-109">In genere questa attività sarà svolta da un responsabile acquisti.</span><span class="sxs-lookup"><span data-stu-id="04e2e-109">This task would typically be carried out by a purchasing manager.</span></span>


## <a name="find-the-procurement-policy"></a><span data-ttu-id="04e2e-110">Trovare i criteri di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="04e2e-110">Find the procurement policy</span></span>
1. <span data-ttu-id="04e2e-111">Andare a Approvvigionamento > Impostazioni > Criteri > Criteri di acquisto.</span><span class="sxs-lookup"><span data-stu-id="04e2e-111">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="04e2e-112">Fare clic sul collegamento sui criteri di approvvigionamento USMF.</span><span class="sxs-lookup"><span data-stu-id="04e2e-112">Click the link on the Procurement Policy USMF policy.</span></span>
    * <span data-ttu-id="04e2e-113">Questi sono i criteri a cui aggiungerete una regola.</span><span class="sxs-lookup"><span data-stu-id="04e2e-113">This is the policy that you’ll add a rule to.</span></span> <span data-ttu-id="04e2e-114">Devono essere criteri attivi.</span><span class="sxs-lookup"><span data-stu-id="04e2e-114">It must be an Active policy.</span></span>  

## <a name="create-a-category-access-rule"></a><span data-ttu-id="04e2e-115">Creare una regola di accesso alla categoria</span><span class="sxs-lookup"><span data-stu-id="04e2e-115">Create a category access rule</span></span>
1. <span data-ttu-id="04e2e-116">Selezionare la regola dei criteri di accesso alle categorie.</span><span class="sxs-lookup"><span data-stu-id="04e2e-116">Select the Category access policy rule.</span></span>
    * <span data-ttu-id="04e2e-117">Se il pulsante Crea regola dei criteri è disattivato, è perché c'è già una regola dei criteri attiva per l'accesso alle categorie.</span><span class="sxs-lookup"><span data-stu-id="04e2e-117">If the Create policy rule button is dimmed, it’s because there’s already an active policy rule for Category access.</span></span> <span data-ttu-id="04e2e-118">Controllare i campi Data di validità e Data di scadenza per determinare quale è, quindi selezionarla e fare clic su Ritira regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="04e2e-118">Check the Effective and Expiration date fields to determine which it is, then select it, and click Retire policy rule.</span></span> <span data-ttu-id="04e2e-119">Se il pulsante Crea regola dei criteri è disponibile, non dovete fare nulla.</span><span class="sxs-lookup"><span data-stu-id="04e2e-119">If the Create policy rule button is available, you don’t need to do anything.</span></span>  
2. <span data-ttu-id="04e2e-120">Fare clic su Crea regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="04e2e-120">Click Create policy rule.</span></span>
3. <span data-ttu-id="04e2e-121">Nel campo Data di validità immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="04e2e-121">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="04e2e-122">Il tempo non deve sovrapporsi con un'altra regola che è già attiva.</span><span class="sxs-lookup"><span data-stu-id="04e2e-122">The time must not overlap with another rule that’s already active.</span></span>  
    * <span data-ttu-id="04e2e-123">Selezionare una categoria a cui la regola si applicherà.</span><span class="sxs-lookup"><span data-stu-id="04e2e-123">Select a category that the rule will apply to.</span></span> <span data-ttu-id="04e2e-124">Prendere nota di quale categoria questa è – l'informazione sarà necessaria successivamente.</span><span class="sxs-lookup"><span data-stu-id="04e2e-124">Make a note of which category this is – you’ll need it later.</span></span> <span data-ttu-id="04e2e-125">Quando si seleziona una categoria, anche le relative categorie padre verranno aggiunte all'elenco Categorie selezionate.</span><span class="sxs-lookup"><span data-stu-id="04e2e-125">When you select a category, its parent category or categories will also be added to the Selected categories list.</span></span>  
    * <span data-ttu-id="04e2e-126">Selezionare la casella di controllo Includi sottocategorie per applicare la regola a tutte le sottocategorie della categoria selezionata.</span><span class="sxs-lookup"><span data-stu-id="04e2e-126">If you want the rule to apply to all subcategories of the selected category, select the Include subcategories check box.</span></span>  
4. <span data-ttu-id="04e2e-127">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="04e2e-127">Click Add.</span></span>
    * <span data-ttu-id="04e2e-128">Se si imposta l'opzione Includi regola padre su Sì, la regola dei criteri definiti per una categoria padre verrà assegnata anche alle categorie figlio se non è stata definita una regola dei criteri per le categorie figlio.</span><span class="sxs-lookup"><span data-stu-id="04e2e-128">If you set the Include parent rule option to Yes, the policy rule that you define for a parent category is also assigned to its child categories, if no policy rule has been defined for the child categories.</span></span>  
5. <span data-ttu-id="04e2e-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="04e2e-129">Click OK.</span></span>

## <a name="create-a-category-policy-rule"></a><span data-ttu-id="04e2e-130">Crea una regola dei criteri categorie</span><span class="sxs-lookup"><span data-stu-id="04e2e-130">Create a category policy rule</span></span>
1. <span data-ttu-id="04e2e-131">Selezionare la regola dei criteri di accesso.</span><span class="sxs-lookup"><span data-stu-id="04e2e-131">Select the Category policy rule</span></span>
    * <span data-ttu-id="04e2e-132">Se il pulsante Crea regola dei criteri è disattivato, selezionare la regola dei criteri attiva e poi fare clic su Ritira regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="04e2e-132">If the Create policy rule button is dimmed, select the active policy rule, and then click Retire policy rule.</span></span>  
2. <span data-ttu-id="04e2e-133">Fare clic su Crea regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="04e2e-133">Click Create policy rule.</span></span>
3. <span data-ttu-id="04e2e-134">Nel campo Data di validità immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="04e2e-134">In the Effective date field, enter a date and time.</span></span>
4. <span data-ttu-id="04e2e-135">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="04e2e-135">Click Add.</span></span>
5. <span data-ttu-id="04e2e-136">Selezionare la stessa categoria che avete usato per la regola di accesso alle categorie.</span><span class="sxs-lookup"><span data-stu-id="04e2e-136">Select the same category that you used for the Category access rule.</span></span>
6. <span data-ttu-id="04e2e-137">Selezionare un'opzione nel campo Selezione fornitore.</span><span class="sxs-lookup"><span data-stu-id="04e2e-137">In the Vendor selection field, select an option.</span></span>
    * <span data-ttu-id="04e2e-138">Selezionare una regola per controllare il tipo di fornitori che può essere selezionato per la categoria quando le richieste vengono create.</span><span class="sxs-lookup"><span data-stu-id="04e2e-138">Select a rule to control which kind of vendors can be selected for the category when requisitions are created.</span></span>  
7. <span data-ttu-id="04e2e-139">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="04e2e-139">Click Close.</span></span>
    * <span data-ttu-id="04e2e-140">Le regole dei criteri definite sono state per le richieste di tipo Consumo.</span><span class="sxs-lookup"><span data-stu-id="04e2e-140">The policy rules that you have defined have been for requisitions of type Consumption.</span></span> <span data-ttu-id="04e2e-141">Se voleste definire criteri per le richieste di tipo Rifornimento, dovreste creare una regola per Tipo di regola dei criteri chiamata "Regola dei criteri di accesso alle categorie di rifornimento".</span><span class="sxs-lookup"><span data-stu-id="04e2e-141">If you wanted to define policies for requisitions of type Replenishment, you would create a rule for the Policy rule type called “Replenishment category access policy rule”.</span></span>  


