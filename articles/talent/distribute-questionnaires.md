---
title: Distribuire e programmare questionari
description: In questo argomento viene illustrato come distribuire i questionari che si progettano, in modo che siano disponibili alla persona o al gruppo di persone che li dovranno completare.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc392c965a0d3bc308e0396263e84ecf1e713491
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898365"
---
# <a name="distribute-and-schedule-questionnaires"></a><span data-ttu-id="ee7e7-103">Distribuire e programmare questionari</span><span class="sxs-lookup"><span data-stu-id="ee7e7-103">Distribute and schedule questionnaires</span></span>

<span data-ttu-id="ee7e7-104">In questo argomento viene illustrato come distribuire i questionari che si progettano, in modo che siano disponibili alla persona o al gruppo di persone che li dovranno completare.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-104">This topic explains how distribute the questionnaires that you design, so that they are available to the person or group of people who will complete them.</span></span> 

<span data-ttu-id="ee7e7-105">Sono disponibili più metodi per distribuire un questionario:</span><span class="sxs-lookup"><span data-stu-id="ee7e7-105">There are multiple ways to distribute a questionnaire:</span></span>

-   <span data-ttu-id="ee7e7-106">Contrassegnare il questionario come attivo.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-106">Mark the questionnaire as active.</span></span> <span data-ttu-id="ee7e7-107">Il questionario è così attivo e disponibile per tutti i dipendenti a meno che un gruppo di questionari non venga impostato per limitare l'accesso al questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-107">The questionnaire is then available to all employees, unless a questionnaire group is set up to restrict access to it.</span></span>
-   <span data-ttu-id="ee7e7-108">Assegnare i diritti a un gruppo di questionari.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-108">Assign rights to a questionnaire group.</span></span> <span data-ttu-id="ee7e7-109">Il questionario è quindi disponibile per tutti i membri del gruppo selezionato.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-109">The questionnaire is then available to all members of the selected group.</span></span>
-   <span data-ttu-id="ee7e7-110">Creare sessioni di risposte pianificate.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-110">Create planned answer sessions.</span></span> <span data-ttu-id="ee7e7-111">Il questionario è quindi disponibile solo per una persona specifica.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-111">The questionnaire is then available only to a particular person.</span></span>
-   <span data-ttu-id="ee7e7-112">Crea una programmazione.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-112">Create a schedule.</span></span> <span data-ttu-id="ee7e7-113">Il questionario può quindi essere disponibile per più persone.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-113">The questionnaire can then be available to multiple people.</span></span>

## <a name="marking-a-questionnaire-as-active"></a><span data-ttu-id="ee7e7-114">Contrassegnare il questionario come attivo</span><span class="sxs-lookup"><span data-stu-id="ee7e7-114">Marking a questionnaire as active</span></span>
<span data-ttu-id="ee7e7-115">Se si imposta il campo **Attivo** su **Sì** nella pagina **Questionari**, si rende il questionario disponibile a tutti i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-115">By setting the **Active** field to **Yes** on the **Questionnaires** page, you make the questionnaire available for all employees to complete.</span></span> <span data-ttu-id="ee7e7-116">Gli intervistati possono completare il questionario più volte.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-116">Respondents can complete the questionnaire multiple times.</span></span> <span data-ttu-id="ee7e7-117">Questa funzionalità è utile se si desidera raccogliere costantemente commenti nell'arco dell'anno.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-117">This functionality is useful if you want to gather continual feedback throughout the year.</span></span> <span data-ttu-id="ee7e7-118">Ad esempio, è possibile effettuare un questionario che i dipendenti utilizzano per fornire un riscontro sul servizio mensa nel self-service.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-118">For example, you can make a questionnaire that employees use to give feedback about the lunch service in the cafeteria.</span></span>

## <a name="questionnaire-groups"></a><span data-ttu-id="ee7e7-119">Gruppi di questionari</span><span class="sxs-lookup"><span data-stu-id="ee7e7-119">Questionnaire groups</span></span>
<span data-ttu-id="ee7e7-120">È possibile impostare gruppi di questionari e quindi includere gli intervistati a cui un questionario deve essere distribuito.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-120">You can set up questionnaire groups and then include the respondents that a questionnaire should be distributed to.</span></span> 

<span data-ttu-id="ee7e7-121">È possibile creare gruppi di questionari dalle seguenti pagine:</span><span class="sxs-lookup"><span data-stu-id="ee7e7-121">You can create questionnaire groups from the following pages:</span></span>

-   <span data-ttu-id="ee7e7-122">**Gruppi di questionari**: solo gli utenti inclusi in un gruppo di questionari possono compilare un questionario selezionato.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-122">**Questionnaire groups** – Only individuals in a questionnaire group can complete a selected questionnaire.</span></span> <span data-ttu-id="ee7e7-123">Ad esempio, se il gruppo di destinatari desiderato è quello dei terzisti, è possibile creare un gruppo di questionari specifico di tali intervistati.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-123">For example, your intended audience is contractors, so you create a questionnaire group that is specific to those respondents.</span></span>
-   <span data-ttu-id="ee7e7-124">**Membri gruppo di questionari**: è possibile aggiungere le persone ai gruppi di questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-124">**Questionnaire group members** – You can add people to the questionnaire groups.</span></span>

<span data-ttu-id="ee7e7-125">Per assegnare un gruppo di questionari a un questionario, nella pagina **Questionari** fare clic su **Diritti dell'utente**.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-125">To assign a questionnaire group to a questionnaire, on the **Questionnaires** page, click **User rights**.</span></span> <span data-ttu-id="ee7e7-126">Dopo che il questionario è stato salvato come attivo, i membri del gruppo di questionari possono completarlo.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-126">After the questionnaire is saved as active, the members of the questionnaire group can complete the questionnaire.</span></span> <span data-ttu-id="ee7e7-127">Questa funzionalità è utile se si desidera verificare un questionario su un gruppo di persone prima di distribuirlo a un gruppo più ampio o se si desidera dedicare un questionario a un pubblico molto specifico.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-127">This functionality is helpful if you want to test a questionnaire on a select group of people before you roll it out to a larger group, or if you want to target a questionnaire to a very specific audience.</span></span>

## <a name="planned-answer-sessions-in-a-questionnaire"></a><span data-ttu-id="ee7e7-128">Sessioni di risposte pianificate in un questionario</span><span class="sxs-lookup"><span data-stu-id="ee7e7-128">Planned answer sessions in a questionnaire</span></span>
<span data-ttu-id="ee7e7-129">Le sessioni di risposte pianificate sono questionari progettati e selezionati per gli intervistati.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-129">Planned answer sessions are questionnaires that you've designed and selected the respondents for.</span></span> 

> [!NOTE]
>   <span data-ttu-id="ee7e7-130">Prima di impostare le sessioni di risposte pianificate, è necessario progettare un questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-130">Before you can set up planned answer sessions, you must design a questionnaire.</span></span> 

<span data-ttu-id="ee7e7-131">Nella pagina **Sessione di risposte pianificata** è possibile creare una sessione di risposte pianificata per un singolo dipendente.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-131">On the **Planned answer session** page, you can create a planned answer session for an individual employee.</span></span> <span data-ttu-id="ee7e7-132">Nell'elenco della pagina sono visualizzati tutti i questionari pianificati.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-132">The list on the page displays all planned questionnaires.</span></span> 

<span data-ttu-id="ee7e7-133">Le sessioni di risposte pianificate vengono inoltre utilizzate nella pagina **Programmazioni questionari**, dove è possibile pianificare questionari per più persone:</span><span class="sxs-lookup"><span data-stu-id="ee7e7-133">Planned answer sessions are also used on the **Questionnaire schedules** page, where you can plan questionnaires for multiple people:</span></span>

-   <span data-ttu-id="ee7e7-134">Dipendenti</span><span class="sxs-lookup"><span data-stu-id="ee7e7-134">Employees</span></span>
-   <span data-ttu-id="ee7e7-135">Partecipanti al corso</span><span class="sxs-lookup"><span data-stu-id="ee7e7-135">Course participants</span></span>
-   <span data-ttu-id="ee7e7-136">Unità organizzative</span><span class="sxs-lookup"><span data-stu-id="ee7e7-136">Organizational units</span></span>

<span data-ttu-id="ee7e7-137">Ogni persona può rispondere al questionario una sola volta.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-137">Each person can answer the questionnaire only one time.</span></span>

## <a name="scheduling-a-questionnaire"></a><span data-ttu-id="ee7e7-138">Programmazione di un questionario</span><span class="sxs-lookup"><span data-stu-id="ee7e7-138">Scheduling a questionnaire</span></span>
<span data-ttu-id="ee7e7-139">Se si desidera è possibile programmare un questionario per più intervistati.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-139">You can optionally schedule a questionnaire for multiple respondents.</span></span>

### <a name="planning-types"></a><span data-ttu-id="ee7e7-140">Tipi di pianificazione</span><span class="sxs-lookup"><span data-stu-id="ee7e7-140">Planning types</span></span>

<span data-ttu-id="ee7e7-141">I tipi di pianificazione sono necessari se si desidera programmare le sessioni di risposte pianificate per più intervistati.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-141">Planning types are required if you want to schedule planned answer sessions for multiple respondents.</span></span> <span data-ttu-id="ee7e7-142">I tipi di pianificazione vengono utilizzati per classificare le programmazioni del questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-142">Planning types are used to classify questionnaire schedules.</span></span> <span data-ttu-id="ee7e7-143">Ad esempio, è possibile programmare i questionari per i seguenti scopi:</span><span class="sxs-lookup"><span data-stu-id="ee7e7-143">For example, you can schedule questionnaires for the following purposes:</span></span>

-   <span data-ttu-id="ee7e7-144">Valutazione</span><span class="sxs-lookup"><span data-stu-id="ee7e7-144">Evaluation</span></span>
-   <span data-ttu-id="ee7e7-145">Rilevamento</span><span class="sxs-lookup"><span data-stu-id="ee7e7-145">Survey</span></span>
-   <span data-ttu-id="ee7e7-146">Test</span><span class="sxs-lookup"><span data-stu-id="ee7e7-146">Testing</span></span>

<span data-ttu-id="ee7e7-147">È possibile specificare i tipi di pianificazione per una programmazione del questionario nella pagina **Programmazioni questionari**.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-147">You can specify planning types for a questionnaire schedule on the **Questionnaire schedules** page.</span></span>

### <a name="reference-types-for-questionnaire"></a><span data-ttu-id="ee7e7-148">Tipi di riferimento per questionario</span><span class="sxs-lookup"><span data-stu-id="ee7e7-148">Reference types for questionnaire</span></span>

<span data-ttu-id="ee7e7-149">È possibile utilizzare i tipi di riferimento per immettere i criteri per gli intervistati che è possibile selezionare quando si programma un questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-149">You can use reference types to enter criteria for the respondents that you might select when you schedule a questionnaire.</span></span> 

<span data-ttu-id="ee7e7-150">Utilizzare la pagina **Tipi di riferimento** per impostare i tipi di riferimento per un questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-150">Use the **Reference types** page to set up reference types for a questionnaire.</span></span> <span data-ttu-id="ee7e7-151">Ogni tipo di riferimento corrisponde a una tabella in Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-151">Each reference type corresponds to a table in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="ee7e7-152">Quando si creano programmazioni questionari, è possibile specificare i singoli record della tabella o un intervallo di record a cui verrà associato il questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-152">When you create questionnaire schedules, you can specify individual records in the table or a range of records that the questionnaire will be associated with.</span></span> 

<span data-ttu-id="ee7e7-153">Ad esempio, se si seleziona la tabella Corsi, è possibile decidere il corso specifico a cui il questionario si riferirà.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-153">For example, if you select the Courses table, you can decide which specific course the questionnaire will be for.</span></span> <span data-ttu-id="ee7e7-154">Se si imposta un riferimento per la tabella Corsi, verranno resi disponibili alcuni campi e pulsanti nel modulo **Corsi**.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-154">When you set up a reference for the Courses table, some fields and buttons on the **Courses** page become available.</span></span>

### <a name="questionnaire-schedules"></a><span data-ttu-id="ee7e7-155">Programmazioni questionari</span><span class="sxs-lookup"><span data-stu-id="ee7e7-155">Questionnaire schedules</span></span>

<span data-ttu-id="ee7e7-156">È possibile utilizzare le programmazioni questionari per generare più sessioni di risposte pianificate per un gruppo di utenti, in base a un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-156">You can use questionnaire schedules to generate multiple planned answer sessions for a group of users, based on a reference type.</span></span> <span data-ttu-id="ee7e7-157">Creare una programmazione nella pagina **Programmazioni questionari**.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-157">Create a schedule on the **Questionnaire schedules** page.</span></span> <span data-ttu-id="ee7e7-158">Selezionare il tipo di pianificazione per classificare la programmazione e selezionare anche il tipo di riferimento da utilizzare per eseguire query nel sistema su utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-158">Select the planning type to categorize the schedule, and also select the reference type that should be used to query the system for specific users.</span></span> <span data-ttu-id="ee7e7-159">Ad esempio, se si imposta il tipo di riferimento sulla tabella Corsi, è possibile selezionare un corso specifico nel campo **Riferimento**.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-159">For example, if you set the reference type to the Courses table, you can select a specific course in the **Reference** field.</span></span> 

<span data-ttu-id="ee7e7-160">Fare clic su **Dettagli impostazione** per selezionare il questionario e altri criteri.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-160">Click **Setup details** to select the questionnaire and other criteria.</span></span> <span data-ttu-id="ee7e7-161">Specificare, ad esempio, il nome dell'istruttore come criterio se il questionario è una valutazione dell'istruttore.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-161">For example, specify the instructor's name as a criterion if the questionnaire is an evaluation of the instructor.</span></span> <span data-ttu-id="ee7e7-162">Dopo aver immesso i dettagli di impostazione, il sistema genera sessioni di risposte pianificate per gli utenti che sono inclusi nella query.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-162">After you've finished entering the setup details, the system generates planned answer sessions for the users that are included in the query.</span></span> 

<span data-ttu-id="ee7e7-163">Fare clic su **Sessioni di risposte pianificate** per visualizzare le sessioni di risposte per la programmazione.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-163">Click **Planned answer sessions** to view the answer sessions for the schedule.</span></span> <span data-ttu-id="ee7e7-164">È possibile quindi creare manualmente sessioni di risposte pianificate aggiuntive o eliminare le sessioni di risposte pianificate a cui non sono state fornite risposte.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-164">You can then manually create additional planned answer sessions or delete planned answer sessions that haven't been answered.</span></span> 

<span data-ttu-id="ee7e7-165">Fare clic su **Funzioni** &gt; **Inizio** per rendere disponibile il questionario agli utenti nelle sessioni di risposte pianificate correlate.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-165">Click **Functions** &gt; **Start** to make the questionnaire available to the users in related planned answer sessions.</span></span> <span data-ttu-id="ee7e7-166">Fare clic su **Risposte** per visualizzare le risposte completate nel questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-166">Click **Answers** to view the completed responses to the questionnaire.</span></span> <span data-ttu-id="ee7e7-167">Si può scegliere di copiare le impostazioni di programmazione questionario, le sessioni di risposte pianificate e le risposte in una nuova programmazione questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-167">You can optionally copy the questionnaire schedule settings, planned answer sessions, and answers to a new questionnaire schedule.</span></span>

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a><span data-ttu-id="ee7e7-168">Informare gli intervistati dei questionari disponibili</span><span class="sxs-lookup"><span data-stu-id="ee7e7-168">Notifying respondents about questionnaires that are available to them</span></span>
<span data-ttu-id="ee7e7-169">Quando viene distribuito un questionario, è necessario avvisare gli intervistati che i questionari sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-169">When you distribute a questionnaire, you must notify respondents that questionnaires are available to them.</span></span> 

### <a name="notifying-respondents-about-a-planned-answer-session"></a><span data-ttu-id="ee7e7-170">Informare gli intervistati su una sessione di risposte pianificata</span><span class="sxs-lookup"><span data-stu-id="ee7e7-170">Notifying respondents about a planned answer session</span></span>

<span data-ttu-id="ee7e7-171">Se si utilizza una sessione di risposte pianificata, è necessario informare direttamente la persona, ad esempio per telefono o posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-171">If you use a planned answer session, you must notify the person directly, such as by telephone or email.</span></span>

### <a name="notifying-respondents-about-a-scheduling"></a><span data-ttu-id="ee7e7-172">Informare gli intervistati su una programmazione</span><span class="sxs-lookup"><span data-stu-id="ee7e7-172">Notifying respondents about a scheduling</span></span>

<span data-ttu-id="ee7e7-173">Utilizzare la pagina **Programmazioni questionari** per preparare e inviare un messaggio di posta elettronica a tutti gli intervistati a cui è stato assegnato il questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-173">Use the **Questionnaire schedules** page to prepare and send email to all respondents who are assigned to the questionnaire.</span></span> <span data-ttu-id="ee7e7-174">Immettere il testo del messaggio di posta elettronica nella scheda **Posta elettronica per dipendente self-service**. Dopo che la programmazione è stata avviata, fare clic su **Funzioni** &gt; **Invia posta elettronica** per generare e inviare il messaggio di posta elettronica agli intervistati.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-174">Enter the email text on the **E-mail for employee self service** tab. After the schedule has been started, click **Functions** &gt; **Send e-mail** to generate and send the email to the respondents.</span></span> <span data-ttu-id="ee7e7-175">Gli intervistati possono quindi accedere al sito Web e completare il questionario.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-175">Respondents can then sign in to the website and complete the questionnaire.</span></span> 

> [!NOTE]
>   <span data-ttu-id="ee7e7-176">Affinché si possa utilizzare la funzionalità di posta elettronica, è necessario che l'amministratore IT immetta le impostazioni di posta elettronica nella pagina **Parametri posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-176">Before you can use the email functionality, your IT administrator must enter the email settings on the **E-mail parameters** page.</span></span>

## <a name="ending-a-scheduled-questionnaire"></a><span data-ttu-id="ee7e7-177">Completamento di un questionario programmato</span><span class="sxs-lookup"><span data-stu-id="ee7e7-177">Ending a scheduled questionnaire</span></span>
<span data-ttu-id="ee7e7-178">È possibile concludere un questionario programmato dopo che tutti gli intervistati hanno completato le sessioni di risposte assegnate.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-178">You can end a scheduled questionnaire after all respondents have completed their assigned answer sessions.</span></span> <span data-ttu-id="ee7e7-179">In seguito al completamento di un questionario programmato, non è possibile copiarne le impostazioni in una nuova programmazione.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-179">After a scheduled questionnaire is ended, you can't copy its settings to a new schedule.</span></span> 

> [!NOTE]
>   <span data-ttu-id="ee7e7-180">Se uno o più intervistati non hanno completato il questionario, ma si desidera comunque completare la programmazione, è necessario innanzitutto eliminare gli intervistati in questione dall'elenco presente nella pagina **Sessione di risposte pianificata**.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-180">If one or more respondents haven't completed the questionnaire, but you still want to end the scheduling, you must first delete those respondents from the list on the **Planned answer session** page.</span></span> <span data-ttu-id="ee7e7-181">Sarà quindi possibile completare la programmazione.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-181">You can then end the schedule.</span></span>

## <a name="completing-questionnaires"></a><span data-ttu-id="ee7e7-182">Completamento di questionari</span><span class="sxs-lookup"><span data-stu-id="ee7e7-182">Completing questionnaires</span></span>
<span data-ttu-id="ee7e7-183">Dopo che è stato progettato e distribuito, un questionario può essere completato dagli intervistati selezionati.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-183">After you've designed and distributed a questionnaire, the questionnaire can be completed by selected respondents.</span></span> <span data-ttu-id="ee7e7-184">È possibile completare i questionari disponibili da due posizioni:</span><span class="sxs-lookup"><span data-stu-id="ee7e7-184">You can complete the questionnaires that are available to you from two locations:</span></span>

-   <span data-ttu-id="ee7e7-185">Nel pannello di navigazione fare clic su **Questionari** &gt; **Distribuisci** &gt; **Compilare un questionario**.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-185">In the navigation pane, click **Questionnaires** &gt; **Distribute** &gt; **Complete a questionnaire**.</span></span>
-   <span data-ttu-id="ee7e7-186">In Dipendente self-service, fare clic su **Questionari da completare**.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-186">In Employee self-service, click **Questionnaires to complete**.</span></span>

<span data-ttu-id="ee7e7-187">I questionari possono essere messi a disposizione di utenti o gruppi di utenti specifici o di tutti gli utenti in una rete.</span><span class="sxs-lookup"><span data-stu-id="ee7e7-187">Questionnaires can made be available to specific users or groups of users, or to all users in a network.</span></span>

<a name="additional-resources"></a><span data-ttu-id="ee7e7-188">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ee7e7-188">Additional resources</span></span>
--------

[<span data-ttu-id="ee7e7-189">Progettare questionari</span><span class="sxs-lookup"><span data-stu-id="ee7e7-189">Design questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="ee7e7-190">Questionari</span><span class="sxs-lookup"><span data-stu-id="ee7e7-190">Questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="ee7e7-191">Visualizzare e valutare i risultati dei questionari</span><span class="sxs-lookup"><span data-stu-id="ee7e7-191">View and evaluate the results of questionnaires</span></span>](evaluate-questionnaire-results.md)


