---
title: Distribuire questionari mediante programmazione
description: La programmazione dei questionari consente di pianificare e distribuire i questionari a più intervistati.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0cd101bfe88ae1acb051ba11a676da66ef6a3db6
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115464"
---
# <a name="distribute-questionnaires-using-scheduling"></a><span data-ttu-id="d7403-103">Distribuire questionari mediante programmazione</span><span class="sxs-lookup"><span data-stu-id="d7403-103">Distribute questionnaires using scheduling</span></span>

<span data-ttu-id="d7403-104">La programmazione dei questionari consente di pianificare e distribuire i questionari a più intervistati.</span><span class="sxs-lookup"><span data-stu-id="d7403-104">Questionnaire scheduling allows you to plan and distribute questionnaires to multiple respondents.</span></span> <span data-ttu-id="d7403-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="d7403-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-questionnaire-schedule"></a><span data-ttu-id="d7403-106">Creare una programmazione per il questionario</span><span class="sxs-lookup"><span data-stu-id="d7403-106">Create a questionnaire schedule</span></span>

1. <span data-ttu-id="d7403-107">Andare a Questionario > Distribuisci > Programmazioni questionario.</span><span class="sxs-lookup"><span data-stu-id="d7403-107">Go to Questionnaire > Distribute > Questionnaire schedules.</span></span>

2. <span data-ttu-id="d7403-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d7403-108">Click New.</span></span>

3. <span data-ttu-id="d7403-109">Digitare un valore nel campo Programmazione.</span><span class="sxs-lookup"><span data-stu-id="d7403-109">In the Scheduling field, type a value.</span></span>

4. <span data-ttu-id="d7403-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d7403-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="d7403-111">Impostare la programmazione su Anonimo se le risposte devono essere registrate senza nomi associati alla risposta.</span><span class="sxs-lookup"><span data-stu-id="d7403-111">Set the schedule to Anonymous if the responses should be recorded without names associated to the response.</span></span>  
    * <span data-ttu-id="d7403-112">L'attivazione dei risultati anonimi deve essere impostata prima nei parametri HR.</span><span class="sxs-lookup"><span data-stu-id="d7403-112">Allowing anonymous results must be set up in the HR parameters first.</span></span>  

5. <span data-ttu-id="d7403-113">Nel campo Tipo selezionare il tipo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d7403-113">In the Type field, select the planning type.</span></span>  <span data-ttu-id="d7403-114">In questo esempio useremo il tipo soddisfazione.</span><span class="sxs-lookup"><span data-stu-id="d7403-114">In this example we will use the Satisfaction type.</span></span>

6. <span data-ttu-id="d7403-115">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d7403-115">In the list, find and select the desired record.</span></span>

7. <span data-ttu-id="d7403-116">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d7403-116">In the list, click the link in the selected row.</span></span>

8. <span data-ttu-id="d7403-117">Nel campo Data immettere una data.</span><span class="sxs-lookup"><span data-stu-id="d7403-117">In the Date field, enter a date.</span></span>

9. <span data-ttu-id="d7403-118">Espandere la sezione Posta elettronica per dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="d7403-118">Expand the Email for employee self service section.</span></span>

10. <span data-ttu-id="d7403-119">Digitare un valore nel campo Oggetto.</span><span class="sxs-lookup"><span data-stu-id="d7403-119">In the Subject field, type a value.</span></span>

    * <span data-ttu-id="d7403-120">Esempio: Questionario disponibile</span><span class="sxs-lookup"><span data-stu-id="d7403-120">Example: Questionnaire available</span></span>  

11. <span data-ttu-id="d7403-121">Nel campo Testo digitare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d7403-121">In the Text field, type the body of your email message.</span></span> <span data-ttu-id="d7403-122">Nota, la variabile può essere utilizzata per sostituire valori nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d7403-122">Note, the variable can be used to substitue values in the system.</span></span>

    * <span data-ttu-id="d7403-123">Esempio: Gentile %P%, effettui l'accesso a Dynamics AX, Dipendente self-service per completare il questionario sulla salute della forza lavoro.</span><span class="sxs-lookup"><span data-stu-id="d7403-123">Example: Dear %P%, Please log in to Employee Self Service to complete the Workforce Health questionnaire.</span></span>  <span data-ttu-id="d7403-124">Contoso</span><span class="sxs-lookup"><span data-stu-id="d7403-124">Contoso</span></span>  

12. <span data-ttu-id="d7403-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d7403-125">Click Save.</span></span>

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a><span data-ttu-id="d7403-126">Utilizzare i Dettagli impostazione per selezionare i questionari a cui rispondere nonché eventuali query da utilizzare per selezionare gli intervistati.</span><span class="sxs-lookup"><span data-stu-id="d7403-126">Use the Setup details to select the questionnaire(s) to be answered as well as any queries to use to select respondents.</span></span>

1. <span data-ttu-id="d7403-127">Fare clic su Dettagli impostazione.</span><span class="sxs-lookup"><span data-stu-id="d7403-127">Click Setup details.</span></span>

2. <span data-ttu-id="d7403-128">Nell'elenco selezionare una query da utilizzare per cercare nel sistema gli intervistati per il questionario.</span><span class="sxs-lookup"><span data-stu-id="d7403-128">In the list, select a query to use to search the system for respondents for the questionnaire.</span></span>

    * <span data-ttu-id="d7403-129">Esempio: Lavoratori</span><span class="sxs-lookup"><span data-stu-id="d7403-129">Example: Workers</span></span>  

3. <span data-ttu-id="d7403-130">Fare clic su Visualizza o modifica query per selezionare persone specifiche o modificare la query per cercare le persone che corrispondono ai criteri specifici.</span><span class="sxs-lookup"><span data-stu-id="d7403-130">Click View or modify query to select specific people or adjust the query to find people who match specific criteria.</span></span>

    * <span data-ttu-id="d7403-131">Si noti che tutti gli intervistati devono essere utenti nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d7403-131">Note that all respondents must also be users in the system.</span></span>  

4. <span data-ttu-id="d7403-132">Nell'elenco contrassegnare la riga per Persona</span><span class="sxs-lookup"><span data-stu-id="d7403-132">In the list, mark the row for Person</span></span>

5. <span data-ttu-id="d7403-133">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d7403-133">In the Criteria field, enter or select a value.</span></span>

    * <span data-ttu-id="d7403-134">Selezionare Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="d7403-134">Select Julia Funderburk</span></span>  

6. <span data-ttu-id="d7403-135">Nell'elenco, selezionare Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="d7403-135">In the list, select Julia Funderburk</span></span>

7. <span data-ttu-id="d7403-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d7403-136">Click OK.</span></span>

8. <span data-ttu-id="d7403-137">Fare clic sulla scheda Questionari.</span><span class="sxs-lookup"><span data-stu-id="d7403-137">Click the Questionnaires tab.</span></span>

9. <span data-ttu-id="d7403-138">Nella struttura espandere il nodo per il tipo di questionario sulla soddisfazione.</span><span class="sxs-lookup"><span data-stu-id="d7403-138">In the tree, expand 'the node for the questionnaire type Satisfaction Survey'.</span></span>

10. <span data-ttu-id="d7403-139">Nella struttura, selezionare 'Workforce Health Assessment'.</span><span class="sxs-lookup"><span data-stu-id="d7403-139">In the tree, check 'Workforce Health Assessment'.</span></span>

11. <span data-ttu-id="d7403-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d7403-140">Click OK.</span></span>

12. <span data-ttu-id="d7403-141">Fare clic su Sessione di risposte pianificata.</span><span class="sxs-lookup"><span data-stu-id="d7403-141">Click Planned answer session.</span></span>

    * <span data-ttu-id="d7403-142">Si noti che la Sessione di risposte pianificata è stata creata per ciascun utente selezionato/sottoposto a query.</span><span class="sxs-lookup"><span data-stu-id="d7403-142">Note that Planned answer sessions have been created for each selected/queried user.</span></span>  

13. <span data-ttu-id="d7403-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d7403-143">Close the page.</span></span>

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a><span data-ttu-id="d7403-144">Avviare la programmazione del questionario per rendere disponibile il questionario da completare agli intervistati.</span><span class="sxs-lookup"><span data-stu-id="d7403-144">Start the questionnaire schedule in order to make the questionnaire available for respondents to complete.</span></span>

1. <span data-ttu-id="d7403-145">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="d7403-145">Click Functions.</span></span>

2. <span data-ttu-id="d7403-146">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="d7403-146">Click Start.</span></span>

3. <span data-ttu-id="d7403-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d7403-147">Click OK.</span></span>

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a><span data-ttu-id="d7403-148">Inviare un messaggio di posta elettronica per informare gli intervistati del questionario disponibile.</span><span class="sxs-lookup"><span data-stu-id="d7403-148">Send the email to inform respondents of the available questionnaire.</span></span>

1. <span data-ttu-id="d7403-149">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="d7403-149">Click Functions.</span></span>

2. <span data-ttu-id="d7403-150">Fare clic su Invia posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d7403-150">Click Send email.</span></span>

3. <span data-ttu-id="d7403-151">Scegliere Annulla.</span><span class="sxs-lookup"><span data-stu-id="d7403-151">Click Cancel.</span></span>

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a><span data-ttu-id="d7403-152">Utilizzare Sessioni di risposte pianificate per monitorare chi deve completare il questionario.</span><span class="sxs-lookup"><span data-stu-id="d7403-152">Use Planned answer sessions to monitor who needs to complete the questionnaire.</span></span>

1. <span data-ttu-id="d7403-153">Fare clic su Sessione di risposte pianificata.</span><span class="sxs-lookup"><span data-stu-id="d7403-153">Click Planned answer session.</span></span>

    * <span data-ttu-id="d7403-154">Eliminare qualsiasi sessione di risposte pianificata rimanente quando si è pronti per terminare la sessione programmata.</span><span class="sxs-lookup"><span data-stu-id="d7403-154">Delete any remaining planned answer session when you're ready to end the scheduled session.</span></span>  

2. <span data-ttu-id="d7403-155">Fare clic su Elimina.</span><span class="sxs-lookup"><span data-stu-id="d7403-155">Click Delete.</span></span>

3. <span data-ttu-id="d7403-156">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="d7403-156">Click Yes.</span></span>

4. <span data-ttu-id="d7403-157">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d7403-157">Close the page.</span></span>

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a><span data-ttu-id="d7403-158">Terminare la programmazione quando tutti gli intervistati hanno completato il questionario e/o le sessioni di risposta pianificate sono state eliminate.</span><span class="sxs-lookup"><span data-stu-id="d7403-158">End the schedule when all respondents have completed the questionnaire and/or all remaining Planned answer sessions have been deleted.</span></span>

1. <span data-ttu-id="d7403-159">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="d7403-159">Click Functions.</span></span>
2. <span data-ttu-id="d7403-160">Fare clic su Fine.</span><span class="sxs-lookup"><span data-stu-id="d7403-160">Click End.</span></span>
3. <span data-ttu-id="d7403-161">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d7403-161">Click OK.</span></span>

