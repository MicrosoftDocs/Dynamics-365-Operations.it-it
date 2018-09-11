--- 
title: Elaborare interessi
description: Questa procedura indica come creare, stampare e registrare le note d'interesse.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 582ebdc6e9481487dcc45b6e212c5d0f8c9f1fc1
ms.contentlocale: it-it
ms.lasthandoff: 09/11/2018

---
# <a name="process-interest"></a><span data-ttu-id="f1a11-103">Elaborare interessi</span><span class="sxs-lookup"><span data-stu-id="f1a11-103">Process interest</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f1a11-104">Questa procedura indica come creare, stampare e registrare le note d'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="f1a11-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="f1a11-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="f1a11-106">Impostare l'interesse nel profilo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f1a11-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="f1a11-107">Andare a Crediti e riscossioni > Impostazioni > Profili di registrazione cliente.</span><span class="sxs-lookup"><span data-stu-id="f1a11-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="f1a11-108">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="f1a11-108">Click Edit.</span></span>
    * <span data-ttu-id="f1a11-109">Selezionare un codice interessi dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="f1a11-109">Select an interest code from the drop-down list.</span></span> <span data-ttu-id="f1a11-110">Se non si desidera che l'interesse venga calcolato per le transazioni utilizzando tale profilo registrazione, lasciare vuoto il campo.</span><span class="sxs-lookup"><span data-stu-id="f1a11-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="f1a11-111">La scheda Restrizioni tabella consente di modificare la modalità di elaborazione dell'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-111">The Table restriction tab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="f1a11-112">Se questo campo è impostato su Sì, l'interesse verrà calcolato per il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="f1a11-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="f1a11-113">Calcola interessi</span><span class="sxs-lookup"><span data-stu-id="f1a11-113">Calculate interest</span></span>
1. <span data-ttu-id="f1a11-114">Andare a Crediti e riscossioni > Interessi > Crea note d'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-114">Go to Credit and collections > Interest > Create interest notes.</span></span>
    * <span data-ttu-id="f1a11-115">È necessario selezionare i tipi di transazione per cui verrà calcolato l'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="f1a11-116">Tutte le transazioni aperte per questi tipi verranno incluse nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="f1a11-116">All of the open transactions for these types will be included in the calculation.</span></span>  
    * <span data-ttu-id="f1a11-117">Se si seleziona Interesse, verrà calcolato l'interesse sull'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-117">If you select Interest, you will calculate interest on interest.</span></span> <span data-ttu-id="f1a11-118">È consigliabile controllare le normative che regolano il calcolo degli interessi sugli interessi prima di includere le transazioni.</span><span class="sxs-lookup"><span data-stu-id="f1a11-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
    * <span data-ttu-id="f1a11-119">Gli interessi verranno calcolati a partire da questa data fino alla "Data finale".</span><span class="sxs-lookup"><span data-stu-id="f1a11-119">Interest will be calculated from this date to the "To date".</span></span> <span data-ttu-id="f1a11-120">Se non si specifica la "Data iniziale" tutte le note d'interesse non registrate verranno annullate e l'interesse verrà ricalcolato a partire dalla data della transazione.</span><span class="sxs-lookup"><span data-stu-id="f1a11-120">If you do not specific a "From date", then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>  
2. <span data-ttu-id="f1a11-121">Immettere la data della nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-121">Enter the date of the interest note.</span></span>
    * <span data-ttu-id="f1a11-122">Sono disponibili tre opzioni di profilo registrazione. Conto: consente di utilizzare il profilo registrazione assegnato al conto cliente per ogni nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-122">There are three posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="f1a11-123">Seleziona: consente di utilizzare il profilo di registrazione selezionato nel campo Profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="f1a11-123">Select – Use the posting profile that you select in the Posting profile field.</span></span>   <span data-ttu-id="f1a11-124">Transazione: consente di utilizzare il singolo profilo di registrazione delle transazioni in cui vengono calcolati gli interessi per ciascuna nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-124">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="f1a11-125">Per le transazioni a cui non è assegnato un profilo di registrazione verrà utilizzato il profilo di registrazione specificato nella Contabilità generale e nell'area IVA del modulo Parametri contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="f1a11-125">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
    * <span data-ttu-id="f1a11-126">Selezionare un profilo registrazione qui se "Utilizza profilo registrazione da" è stato modificato in "Seleziona".</span><span class="sxs-lookup"><span data-stu-id="f1a11-126">Select a posting profile here if you changed "Use posting profile from" to "Select".</span></span>  
3. <span data-ttu-id="f1a11-127">Espandere o comprimere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="f1a11-127">Expand or collapse the Records to include section.</span></span>
4. <span data-ttu-id="f1a11-128">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="f1a11-128">Click Filter.</span></span>
5. <span data-ttu-id="f1a11-129">Nel campo Criteri, immettere un ID cliente.</span><span class="sxs-lookup"><span data-stu-id="f1a11-129">In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="f1a11-130">Ad esempio, immettere "US-001".</span><span class="sxs-lookup"><span data-stu-id="f1a11-130">For example, enter 'US-001'..</span></span>
6. <span data-ttu-id="f1a11-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f1a11-131">Click OK.</span></span>
7. <span data-ttu-id="f1a11-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f1a11-132">Click OK.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="f1a11-133">Stampa le note d'interesse</span><span class="sxs-lookup"><span data-stu-id="f1a11-133">Print interest notes</span></span>
1. <span data-ttu-id="f1a11-134">Andare a Crediti e riscossioni > Interessi > Esamina ed elabora note d'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-134">Go to Credit and collections > Interest > Review and process interest notes.</span></span>
2. <span data-ttu-id="f1a11-135">Nel campo Stato selezionare "Creata".</span><span class="sxs-lookup"><span data-stu-id="f1a11-135">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="f1a11-136">Nel campo Stampata selezionare "Non stampata".</span><span class="sxs-lookup"><span data-stu-id="f1a11-136">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="f1a11-137">Fare clic su Stampa.</span><span class="sxs-lookup"><span data-stu-id="f1a11-137">Click Print.</span></span>
5. <span data-ttu-id="f1a11-138">Espandere o comprimere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="f1a11-138">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="f1a11-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f1a11-139">Click OK.</span></span>
7. <span data-ttu-id="f1a11-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f1a11-140">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="f1a11-141">Registrare la nota d'interesse</span><span class="sxs-lookup"><span data-stu-id="f1a11-141">Post the interest note</span></span>
1. <span data-ttu-id="f1a11-142">Selezionare una nota d'interesse pronta per la registrazione (lo stato è Creata).</span><span class="sxs-lookup"><span data-stu-id="f1a11-142">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="f1a11-143">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="f1a11-143">Click Post.</span></span>
3. <span data-ttu-id="f1a11-144">Immettere la data di registrazione per la nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-144">Enter the posting date for the interest note.</span></span>
    * <span data-ttu-id="f1a11-145">Selezionare Sì per creare una transazione di contabilità generale per ciascuna nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="f1a11-145">Select Yes to create a general ledger transaction for each interest note.</span></span>     <span data-ttu-id="f1a11-146">Se non si seleziona Sì, gli interessi indicati su tutte le note d'interesse destinate al cliente verranno cumulati e registrati nella contabilità generale in un'unica transazione.</span><span class="sxs-lookup"><span data-stu-id="f1a11-146">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="f1a11-147">Espandere o comprimere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="f1a11-147">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="f1a11-148">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f1a11-148">Click OK.</span></span>
6. <span data-ttu-id="f1a11-149">Nel campo Stato selezionare "Registrata".</span><span class="sxs-lookup"><span data-stu-id="f1a11-149">In the Status field, select 'Posted'.</span></span>


