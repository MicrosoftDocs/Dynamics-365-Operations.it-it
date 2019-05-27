---
title: Creare ed elaborare una conformità
description: Utilizzare questa procedura per eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente.
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16ed11bce92920fe8240fc85f706a2ac6ab0a04b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572813"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="cfb94-103">Creare ed elaborare una conformità</span><span class="sxs-lookup"><span data-stu-id="cfb94-103">Create and process a conformance</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cfb94-104">Utilizzare questa procedura per eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente.</span><span class="sxs-lookup"><span data-stu-id="cfb94-104">Use this procedure to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="cfb94-105">È possibile eseguire questa registrazione nella società dimostrativa USMF e utilizzare i valori suggeriti.</span><span class="sxs-lookup"><span data-stu-id="cfb94-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="cfb94-106">In genere, questa procedura viene eseguita da un addetto al controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="cfb94-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="cfb94-107">Come prerequisito, eseguire la registrazione attività "Verificare la qualità delle merci".</span><span class="sxs-lookup"><span data-stu-id="cfb94-107">As a prerequisite, run the “Inspect the quality of goods” task recording.</span></span> <span data-ttu-id="cfb94-108">Per elaborare l'approvazione di una non conformità, l'utente che esegue la registrazione attività deve avere un valore "Nome" assegnato alla pagina Utenti.</span><span class="sxs-lookup"><span data-stu-id="cfb94-108">To process the approval of a nonconformance, the user who runs the task recording must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="cfb94-109">Per utilizzare le note del documento, l'utente deve inoltre avere Gestione documenti attivata nelle opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="cfb94-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="cfb94-110">Selezionare un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="cfb94-110">Select a quality order</span></span>
1. <span data-ttu-id="cfb94-111">Scegliere Ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="cfb94-111">Go to Quality orders.</span></span>
2. <span data-ttu-id="cfb94-112">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cfb94-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="cfb94-113">Selezionare l'ordine di controllo qualità creato tramite la registrazione attività "Verificare la qualità delle merci".</span><span class="sxs-lookup"><span data-stu-id="cfb94-113">Select the quality order that was created from the "Inspect the quality of goods" task recording.</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="cfb94-114">Creare una non conformità</span><span class="sxs-lookup"><span data-stu-id="cfb94-114">Create a nonconformance</span></span>
1. <span data-ttu-id="cfb94-115">Fare clic su Richieste di informazioni.</span><span class="sxs-lookup"><span data-stu-id="cfb94-115">Click Inquiries.</span></span>
2. <span data-ttu-id="cfb94-116">Fare clic su Non conformità.</span><span class="sxs-lookup"><span data-stu-id="cfb94-116">Click Non conformances.</span></span>
3. <span data-ttu-id="cfb94-117">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cfb94-117">Click New.</span></span>
4. <span data-ttu-id="cfb94-118">Nel campo Tipo di problema fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="cfb94-118">In the Problem type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="cfb94-119">Selezionare il problema che è stato rilevato durante il processo di ispezione.</span><span class="sxs-lookup"><span data-stu-id="cfb94-119">Select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="cfb94-120">Nel campo Tipo di problema fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="cfb94-120">In the Problem type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="cfb94-121">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="cfb94-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="cfb94-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cfb94-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="cfb94-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cfb94-123">Click OK.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="cfb94-124">Approvare/respingere una non conformità</span><span class="sxs-lookup"><span data-stu-id="cfb94-124">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="cfb94-125">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="cfb94-125">Click Functions.</span></span>
2. <span data-ttu-id="cfb94-126">Fare clic su Approva non conformità.</span><span class="sxs-lookup"><span data-stu-id="cfb94-126">Click Approve non conformance.</span></span>
    * <span data-ttu-id="cfb94-127">Per questo esempio, approvare la non conformità.</span><span class="sxs-lookup"><span data-stu-id="cfb94-127">For this example, approve the nonconformance.</span></span> <span data-ttu-id="cfb94-128">Le non conformità approvate possono essere associate alle operazioni correlate per la registrazione del lavoro che viene eseguito nell'ambito della gestione di non conformità e, come in questa registrazione di attività, l'elaborazione della gestione della correzione.</span><span class="sxs-lookup"><span data-stu-id="cfb94-128">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this task recording, the processing of correction handling.</span></span>  
3. <span data-ttu-id="cfb94-129">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="cfb94-129">Click Yes.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="cfb94-130">Creare un'azione correttiva</span><span class="sxs-lookup"><span data-stu-id="cfb94-130">Create a correction action</span></span>
1. <span data-ttu-id="cfb94-131">Fare clic su Correzioni.</span><span class="sxs-lookup"><span data-stu-id="cfb94-131">Click Corrections.</span></span>
2. <span data-ttu-id="cfb94-132">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cfb94-132">Click New.</span></span>
3. <span data-ttu-id="cfb94-133">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cfb94-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="cfb94-134">Nel campo Numero dipendente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="cfb94-134">In the Personnel number field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="cfb94-135">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cfb94-135">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="cfb94-136">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="cfb94-136">Click Select.</span></span>
7. <span data-ttu-id="cfb94-137">Fare clic su Allega.</span><span class="sxs-lookup"><span data-stu-id="cfb94-137">Click Attach.</span></span>
    * <span data-ttu-id="cfb94-138">Creare una nota sulla correzione.</span><span class="sxs-lookup"><span data-stu-id="cfb94-138">Create a note about the correction.</span></span> <span data-ttu-id="cfb94-139">Per questo esempio l'azione è di contattare il fornitore per discutere il caso di non conformità.</span><span class="sxs-lookup"><span data-stu-id="cfb94-139">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
8. <span data-ttu-id="cfb94-140">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cfb94-140">Click New.</span></span>
9. <span data-ttu-id="cfb94-141">Fare clic su Nota.</span><span class="sxs-lookup"><span data-stu-id="cfb94-141">Click Note.</span></span>
    * <span data-ttu-id="cfb94-142">A seconda dell'impostazione del report, i tipi di documento possono essere stampati nei report correlati alla gestione di non conformità.</span><span class="sxs-lookup"><span data-stu-id="cfb94-142">Note that, depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
10. <span data-ttu-id="cfb94-143">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="cfb94-143">In the Description field, type a value.</span></span>
11. <span data-ttu-id="cfb94-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cfb94-144">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="cfb94-145">Gestire una correzione</span><span class="sxs-lookup"><span data-stu-id="cfb94-145">Maintain a correction</span></span>
1. <span data-ttu-id="cfb94-146">Fare clic su Contrassegna come completata.</span><span class="sxs-lookup"><span data-stu-id="cfb94-146">Click Mark complete.</span></span>
2. <span data-ttu-id="cfb94-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cfb94-147">Click OK.</span></span>
3. <span data-ttu-id="cfb94-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cfb94-148">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="cfb94-149">Chiudere una non conformità</span><span class="sxs-lookup"><span data-stu-id="cfb94-149">Close a nonconformance</span></span>
1. <span data-ttu-id="cfb94-150">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="cfb94-150">Click Functions.</span></span>
2. <span data-ttu-id="cfb94-151">Fare clic su Chiudi non conformità.</span><span class="sxs-lookup"><span data-stu-id="cfb94-151">Click Close non conformance.</span></span>
3. <span data-ttu-id="cfb94-152">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="cfb94-152">Click Yes.</span></span>
4. <span data-ttu-id="cfb94-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cfb94-153">Close the page.</span></span>
5. <span data-ttu-id="cfb94-154">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cfb94-154">Close the page.</span></span>
