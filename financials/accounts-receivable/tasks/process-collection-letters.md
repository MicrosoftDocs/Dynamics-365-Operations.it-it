--- 
title: Elaborare lettere di sollecito
description: Questa procedura indica come creare, stampare e registrare le lettere di sollecito.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: dc837ea6513992a5f94e48baa366e279df297866
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="process-collection-letters"></a><span data-ttu-id="bee58-103">Elaborare lettere di sollecito</span><span class="sxs-lookup"><span data-stu-id="bee58-103">Process collection letters</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bee58-104">Questa procedura indica come creare, stampare e registrare le lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="bee58-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="bee58-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="bee58-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="bee58-106">Impostare una sequenza di lettere di sollecito nel profilo registrazione</span><span class="sxs-lookup"><span data-stu-id="bee58-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="bee58-107">Andare a Crediti e riscossioni > Impostazioni > Profili di registrazione cliente.</span><span class="sxs-lookup"><span data-stu-id="bee58-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="bee58-108">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="bee58-108">Click Edit.</span></span>
    * <span data-ttu-id="bee58-109">Selezionare una sequenza di lettere di sollecito dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bee58-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="bee58-110">Se non si desidera generare lettere di sollecito per le transazioni che utilizzano il profilo registrazione, lasciare vuoto il campo.</span><span class="sxs-lookup"><span data-stu-id="bee58-110">If you do not want generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="bee58-111">La scheda delle restrizioni della tabella consente di modificare la modalità per l'elaborazione delle lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="bee58-111">The table restriction tab allows you to change the way that collection letters are processed.</span></span> <span data-ttu-id="bee58-112">Se questo campo è impostato su Sì, le lettere di sollecito verranno create per il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="bee58-112">If this field is set to Yes, then collection letters will be created for this posting profile.</span></span>  
3. <span data-ttu-id="bee58-113">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bee58-113">Close the page.</span></span>

## <a name="create-collection-letters"></a><span data-ttu-id="bee58-114">Crea lettere di sollecito</span><span class="sxs-lookup"><span data-stu-id="bee58-114">Create collection letters</span></span>
1. <span data-ttu-id="bee58-115">Andare a Crediti e riscossioni > Lettera di sollecito > Crea lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="bee58-115">Go to Credit and collections > Collection letter > Create collection letters.</span></span>
    * <span data-ttu-id="bee58-116">È necessario selezionare i tipi di transazione per cui si raccoglieranno le lettere.</span><span class="sxs-lookup"><span data-stu-id="bee58-116">You must select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="bee58-117">Tutte le transazioni aperte per questi tipi verranno incluse nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="bee58-117">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="bee58-118">Selezionare una opzione nel campo Lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="bee58-118">In the Collection letter field, select an option.</span></span>
3. <span data-ttu-id="bee58-119">Immettere la data della lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="bee58-119">Enter the date of the collection letter.</span></span>
    * <span data-ttu-id="bee58-120">Sono disponibili due opzioni di profilo registrazione. Conto: consente di utilizzare il profilo registrazione assegnato al conto cliente per ogni nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="bee58-120">There are two posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="bee58-121">Seleziona: consente di utilizzare il profilo di registrazione selezionato nel campo Profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="bee58-121">Select – Use the posting profile that you select in the Posting profile field.</span></span>  
    * <span data-ttu-id="bee58-122">Selezionare un profilo registrazione se "Utilizza profilo registrazione da" è stato impostato su "Seleziona".</span><span class="sxs-lookup"><span data-stu-id="bee58-122">Select a posting profile if you changed "Use posting profile from" to "Select".</span></span>  
4. <span data-ttu-id="bee58-123">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="bee58-123">Expand the Records to include section.</span></span>
5. <span data-ttu-id="bee58-124">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="bee58-124">Click Filter.</span></span>
6. <span data-ttu-id="bee58-125">Nel campo Criteri, immettere un ID cliente.</span><span class="sxs-lookup"><span data-stu-id="bee58-125">In the Criteria field, In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="bee58-126">Ad esempio, immettere "US-001".</span><span class="sxs-lookup"><span data-stu-id="bee58-126">For example, enter 'US-001'..</span></span>
7. <span data-ttu-id="bee58-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bee58-127">Click OK.</span></span>
8. <span data-ttu-id="bee58-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bee58-128">Click OK.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="bee58-129">Stampare le lettere di sollecito</span><span class="sxs-lookup"><span data-stu-id="bee58-129">Print collection letters</span></span>
1. <span data-ttu-id="bee58-130">Andare a Crediti e riscossioni > Lettera di sollecito > Esamina ed elabora lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="bee58-130">Go to Credit and collections > Collection letter > Review and process collection letters.</span></span>
2. <span data-ttu-id="bee58-131">Nel campo Stato selezionare "Creata".</span><span class="sxs-lookup"><span data-stu-id="bee58-131">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="bee58-132">Nel campo Stampata selezionare "Non stampata".</span><span class="sxs-lookup"><span data-stu-id="bee58-132">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="bee58-133">Fare clic su Stampa.</span><span class="sxs-lookup"><span data-stu-id="bee58-133">Click Print.</span></span>
5. <span data-ttu-id="bee58-134">Fare clic su Nota lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="bee58-134">Click Collection letter note.</span></span>
6. <span data-ttu-id="bee58-135">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="bee58-135">Expand the Records to include section.</span></span>
7. <span data-ttu-id="bee58-136">Specificare la data limite per le registrazioni</span><span class="sxs-lookup"><span data-stu-id="bee58-136">Enter the cutoff date for postings</span></span>
8. <span data-ttu-id="bee58-137">Fare clic su OK per stampare la lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="bee58-137">Click OK to print the collection letter.</span></span>

## <a name="post-the-collection-letter"></a><span data-ttu-id="bee58-138">Registrare la lettera di sollecito</span><span class="sxs-lookup"><span data-stu-id="bee58-138">Post the collection letter</span></span>
1. <span data-ttu-id="bee58-139">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="bee58-139">Click Post.</span></span>
2. <span data-ttu-id="bee58-140">Immettere la data di registrazione per la lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="bee58-140">Enter the posting date for the collection letter.</span></span>
3. <span data-ttu-id="bee58-141">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="bee58-141">Expand the Records to include section.</span></span>
4. <span data-ttu-id="bee58-142">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bee58-142">Click OK.</span></span>
5. <span data-ttu-id="bee58-143">Nel campo Stato selezionare "Registrata".</span><span class="sxs-lookup"><span data-stu-id="bee58-143">In the Status field, select 'Posted'.</span></span>
6. <span data-ttu-id="bee58-144">Selezionare un'opzione nel campo Stampata.</span><span class="sxs-lookup"><span data-stu-id="bee58-144">In the Printed field, select an option.</span></span>

