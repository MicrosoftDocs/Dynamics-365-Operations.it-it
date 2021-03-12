---
title: Elaborare interessi
description: Questa procedura indica come creare, stampare e registrare le note d'interesse.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad30984f55017ee275af15ddb4f1a46c6a50db69
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992941"
---
# <a name="process-interest"></a><span data-ttu-id="38bde-103">Elaborare interessi</span><span class="sxs-lookup"><span data-stu-id="38bde-103">Process interest</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="38bde-104">Questa procedura indica come creare, stampare e registrare le note d'interesse.</span><span class="sxs-lookup"><span data-stu-id="38bde-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="38bde-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="38bde-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="38bde-106">Impostare l'interesse nel profilo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="38bde-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="38bde-107">Nel **pannello di navigazione**, andare a **Moduli > Crediti e riscossioni > Impostazione > Profili di registrazione cliente**.</span><span class="sxs-lookup"><span data-stu-id="38bde-107">In the **Navigation pane**, go to **Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="38bde-108">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="38bde-108">Click **Edit**.</span></span>
3. <span data-ttu-id="38bde-109">Nella **Scheda dettaglio Impostazione**, nel campo **Codice interessi**, selezionare un codice interessi dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="38bde-109">In the **Setup fastTab**, in the **Interest code** field, select an interest code from the drop-down list.</span></span> <span data-ttu-id="38bde-110">Se non si desidera che l'interesse venga calcolato per le transazioni utilizzando tale profilo registrazione, lasciare vuoto il campo.</span><span class="sxs-lookup"><span data-stu-id="38bde-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span> <span data-ttu-id="38bde-111">La Scheda dettaglio **Restrizioni tabella** consente di modificare la modalità di elaborazione dell'interesse.</span><span class="sxs-lookup"><span data-stu-id="38bde-111">The **Table restriction** fastTab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="38bde-112">Se questo campo è impostato su Sì, l'interesse verrà calcolato per il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="38bde-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="38bde-113">Calcola interessi</span><span class="sxs-lookup"><span data-stu-id="38bde-113">Calculate interest</span></span>
1. <span data-ttu-id="38bde-114">Nel **pannello di navigazione**, andare a **Moduli > Crediti e riscossioni > Interessi > Crea note d'interesse**.</span><span class="sxs-lookup"><span data-stu-id="38bde-114">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Create interest notes**.</span></span>
2. <span data-ttu-id="38bde-115">È necessario selezionare i tipi di transazione per cui verrà calcolato l'interesse.</span><span class="sxs-lookup"><span data-stu-id="38bde-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="38bde-116">Tutte le transazioni aperte per questi tipi verranno incluse nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="38bde-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="38bde-117">Se si imposta **Interesse** su "Sì", verrà calcolato l'interesse sull'interesse.</span><span class="sxs-lookup"><span data-stu-id="38bde-117">If you set **Interest** to 'Yes', you will calculate interest on interest.</span></span> <span data-ttu-id="38bde-118">È consigliabile controllare le normative che regolano il calcolo degli interessi sugli interessi prima di includere le transazioni.</span><span class="sxs-lookup"><span data-stu-id="38bde-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
4. <span data-ttu-id="38bde-119">Nel campo **Dal** immettere una data di inizio per il calcolo degli interessi.</span><span class="sxs-lookup"><span data-stu-id="38bde-119">In the **From date** field, enter a date from which the interest will be calculated.</span></span> <span data-ttu-id="38bde-120">Se non si specifica **Dal**, tutte le note d'interesse non registrate verranno annullate e l'interesse verrà ricalcolato a partire dalla data della transazione.</span><span class="sxs-lookup"><span data-stu-id="38bde-120">If you do not specific a **From date**, then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>
5. <span data-ttu-id="38bde-121">Nel campo **Al** immettere una data di fine per il calcolo degli interessi.</span><span class="sxs-lookup"><span data-stu-id="38bde-121">In the **To date** field, enter a date to which the interest would be calculated.</span></span>
6. <span data-ttu-id="38bde-122">Nel campo **Utilizza profilo registrazione da**, selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="38bde-122">In the **Use posting profile from** field, select an option.</span></span> <span data-ttu-id="38bde-123">Sono disponibili tre opzioni di profilo di registrazione:</span><span class="sxs-lookup"><span data-stu-id="38bde-123">There are three posting profile options:</span></span>
    - <span data-ttu-id="38bde-124">Conto: consente di utilizzare il profilo di registrazione assegnato al conto cliente per ogni nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="38bde-124">Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span> 
    - <span data-ttu-id="38bde-125">Seleziona: consente di utilizzare il profilo di registrazione selezionato nel campo Profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="38bde-125">Select – Use the posting profile that you select in the Posting profile field.</span></span>
    - <span data-ttu-id="38bde-126">Transazione: consente di utilizzare il singolo profilo di registrazione delle transazioni in cui vengono calcolati gli interessi per ciascuna nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="38bde-126">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="38bde-127">Per le transazioni a cui non è assegnato un profilo di registrazione verrà utilizzato il profilo di registrazione specificato nella Contabilità generale e nell'area IVA del modulo Parametri contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="38bde-127">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
7. <span data-ttu-id="38bde-128">Espandere la Scheda dettaglio **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="38bde-128">Expand the **Records to include** fastTab.</span></span>
8. <span data-ttu-id="38bde-129">Fare clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="38bde-129">Click **Filter**.</span></span>
9. <span data-ttu-id="38bde-130">Nel campo **Criteri**, immettere un ID cliente.</span><span class="sxs-lookup"><span data-stu-id="38bde-130">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="38bde-131">Ad esempio, immettere "US-001".</span><span class="sxs-lookup"><span data-stu-id="38bde-131">For example, enter 'US-001'.</span></span>
6. <span data-ttu-id="38bde-132">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="38bde-132">Click **OK**.</span></span>
7. <span data-ttu-id="38bde-133">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="38bde-133">Click **OK**.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="38bde-134">Stampa le note d'interesse</span><span class="sxs-lookup"><span data-stu-id="38bde-134">Print interest notes</span></span>
1. <span data-ttu-id="38bde-135">Nel **pannello di navigazione**, andare a **Moduli > Crediti e riscossioni > Interessi > Esamina ed elabora note d'interesse**.</span><span class="sxs-lookup"><span data-stu-id="38bde-135">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Review and process interest notes**.</span></span>
2. <span data-ttu-id="38bde-136">Nel campo **Stato** selezionare "Creata".</span><span class="sxs-lookup"><span data-stu-id="38bde-136">In the **Status** field, select 'Created'.</span></span>
3. <span data-ttu-id="38bde-137">Nel campo **Stampata** selezionare "Non stampata".</span><span class="sxs-lookup"><span data-stu-id="38bde-137">In the **Printed** field, select 'Not printed'.</span></span>
4. <span data-ttu-id="38bde-138">Fare clic su **Stampa**.</span><span class="sxs-lookup"><span data-stu-id="38bde-138">Click **Print**.</span></span>
5. <span data-ttu-id="38bde-139">Espandere la Scheda dettaglio **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="38bde-139">Expand the **Records to include** fastTab.</span></span>
6. <span data-ttu-id="38bde-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="38bde-140">Click **OK**.</span></span>
7. <span data-ttu-id="38bde-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="38bde-141">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="38bde-142">Registrare la nota d'interesse</span><span class="sxs-lookup"><span data-stu-id="38bde-142">Post the interest note</span></span>
1. <span data-ttu-id="38bde-143">Selezionare una nota d'interesse pronta per la registrazione (lo stato è Creata).</span><span class="sxs-lookup"><span data-stu-id="38bde-143">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="38bde-144">Fare clic su **Registra**.</span><span class="sxs-lookup"><span data-stu-id="38bde-144">Click **Post**.</span></span>
3. <span data-ttu-id="38bde-145">Immettere la data di registrazione per la nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="38bde-145">Enter the posting date for the interest note.</span></span> <span data-ttu-id="38bde-146">Selezionare Sì per creare una transazione di contabilità generale per ciascuna nota d'interesse.</span><span class="sxs-lookup"><span data-stu-id="38bde-146">Select Yes to create a general ledger transaction for each interest note.</span></span> <span data-ttu-id="38bde-147">Se non si seleziona Sì, gli interessi indicati su tutte le note d'interesse destinate al cliente verranno cumulati e registrati nella contabilità generale in un'unica transazione.</span><span class="sxs-lookup"><span data-stu-id="38bde-147">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="38bde-148">Espandere la Scheda dettaglio **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="38bde-148">Expand the **Records to include** fastTab.</span></span>
5. <span data-ttu-id="38bde-149">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="38bde-149">Click **OK**.</span></span>
6. <span data-ttu-id="38bde-150">Nel campo **Stato** selezionare "Registrata".</span><span class="sxs-lookup"><span data-stu-id="38bde-150">In the **Status** field, select 'Posted'.</span></span>

