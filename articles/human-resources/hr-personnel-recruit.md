---
title: Selezionare i candidati a una posizione
description: Questo argomento mostra come selezionare i candidati in Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6aca285133495dfe023dfd18bdeb050aabcafee6
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478286"
---
# <a name="recruit-job-candidates"></a><span data-ttu-id="f50e3-103">Selezionare i candidati a una posizione</span><span class="sxs-lookup"><span data-stu-id="f50e3-103">Recruit job candidates</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f50e3-104">Dynamics 365 Human Resources aiuta a gestire le richieste di selezione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-104">Dynamics 365 Human Resources helps you to manage recruiting requests.</span></span> <span data-ttu-id="f50e3-105">Aiuta anche a passare senza problemi i candidati a una posizione come dipendenti.</span><span class="sxs-lookup"><span data-stu-id="f50e3-105">It also helps you seamlessly transition job candidates to employees.</span></span> <span data-ttu-id="f50e3-106">Se l'organizzazione utilizza un'applicazione di selezione separata, il processo di selezione potrebbe includere i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="f50e3-106">If your organization uses a separate recruiting application, your recruiting process might include the following steps:</span></span>

- <span data-ttu-id="f50e3-107">Immettere la richiesta di selezione in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f50e3-107">Enter your recruiting request in Human Resources.</span></span>
- <span data-ttu-id="f50e3-108">Ricevere le referenze dei candidati in Human Resources dall'applicazione di selezione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-108">Receive candidate referrals in Human Resources from the recruiting application.</span></span>
- <span data-ttu-id="f50e3-109">Completare il processo di approvazione del candidato in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f50e3-109">Complete the candidate approval process in Human Resources.</span></span>

<span data-ttu-id="f50e3-110">Se non si sta utilizzando un'applicazione di selezione separata, è possibile anche gestire manualmente i candidati in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f50e3-110">If you aren't using a separate recruiting application, you can also manually manage candidates in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="f50e3-111">Se si è un amministratore o uno sviluppatore e si desidera integrare Human Resources con un'applicazione di selezione di terze parti, vedi [Configurare l'integrazione di Dataverse](hr-admin-integration-common-data-service.md) e [Configurare le tabelle virtuali di Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)</span><span class="sxs-lookup"><span data-stu-id="f50e3-111">If you're an admin or developer and want to integrate Human Resources with a third-party recruiting application, see [Configure Dataverse integration](hr-admin-integration-common-data-service.md) and [Configure Dataverse virtual tables](hr-admin-integration-common-data-service-virtual-entities.md)</span></span>
>
> <span data-ttu-id="f50e3-112">È anche possibile trovare app di integrazione di selezione in [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span><span class="sxs-lookup"><span data-stu-id="f50e3-112">You can also find recruiting integration apps on [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span></span>
>
> <span data-ttu-id="f50e3-113">Per provare la nostra funzione di anteprima per l'integrazione con LinkedIn Talent Hub, vedere [Integrazione con LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="f50e3-113">To try out our preview feature for integrating with LinkedIn Talent Hub, see [Integrate with LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span></span>

## <a name="enable-recruiting-requests"></a><span data-ttu-id="f50e3-114">Abilita richieste di selezione</span><span class="sxs-lookup"><span data-stu-id="f50e3-114">Enable recruiting requests</span></span>

<span data-ttu-id="f50e3-115">Se si desidera inviare richieste di selezione in Human Resources, è necessario prima abilitare la funzionalità in **Parametri condivisi delle risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-115">If you want to submit recruiting requests in Human Resources, you must first enable the functionality in **Human resources shared parameters**.</span></span>

1. <span data-ttu-id="f50e3-116">Nell'area di lavoro **Gestione personale** selezionare **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-116">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="f50e3-117">Sotto **Impostazione**, selezionare **Parametri condivisi di risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-117">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="f50e3-118">Nella scheda **Selezione** sotto **RECLUTAMENTO**, impostare **Abilita richieste di selezione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-118">On the **Recruitment** tab, under **RECRUITING**, set **Enable recruiting requests** to **Yes**.</span></span>

## <a name="add-a-recruiting-request-location"></a><span data-ttu-id="f50e3-119">Aggiungere una posizione per la richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="f50e3-119">Add a recruiting request location</span></span>

<span data-ttu-id="f50e3-120">Se l'organizzazione ha più sedi, è possibile aggiungerle in modo che i richiedenti possano selezionare una posizione in cui lavorerà la nuova recluta.</span><span class="sxs-lookup"><span data-stu-id="f50e3-120">If your organization has multiple locations, you can add them so requestors can select a location where the new recruit will be working.</span></span> <span data-ttu-id="f50e3-121">La posizione sarà inclusa nell'offerta di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f50e3-121">The location will be included in the job posting.</span></span>

1. <span data-ttu-id="f50e3-122">Nella barra di ricerca, inserire **posizione della richiesta di selezione**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-122">In the search bar, enter **recruiting request location**.</span></span>

2. <span data-ttu-id="f50e3-123">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-123">Select **New**.</span></span>

3. <span data-ttu-id="f50e3-124">Nel campo **Posizione della richiesta di selezione** immettere il nome della posizione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-124">In the **Recruiting request location** field, enter the location name.</span></span>

   ![Aggiungere una posizione per la richiesta di selezione](./media/hr-recruit-0a-add-location.png)

4. <span data-ttu-id="f50e3-126">Nel campo **Descrizione** immettere una descrizione per la posizione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-126">In the **Description**, enter a description for the location.</span></span>

5. <span data-ttu-id="f50e3-127">Sotto **Posizione**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-127">Under **Location**, select **Add**.</span></span> <span data-ttu-id="f50e3-128">Se il popout **Nuovo indirizzo** viene visualizzato, immettere l'indirizzo della posizione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-128">If the **New address** popout appears, enter the address for the location.</span></span>

   ![Immettere indirizzo](./media/hr-recruit-0b-address.png)

6. <span data-ttu-id="f50e3-130">In **Informazioni sui contatti**, inserire le informazioni per il contatto della posizione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-130">Under **Contact information**, enter the information for the location's contact.</span></span>

7. <span data-ttu-id="f50e3-131">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-131">Select **Save**.</span></span>

## <a name="add-a-recruiting-request"></a><span data-ttu-id="f50e3-132">Aggiungere una richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="f50e3-132">Add a recruiting request</span></span>

<span data-ttu-id="f50e3-133">I responsabili possono inviare richieste di selezione in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f50e3-133">Managers can submit recruiting requests in Human Resources.</span></span> <span data-ttu-id="f50e3-134">Se si utilizza un'applicazione di selezione separata, il completamento di questi passaggi invierà una richiesta di selezione e avvierà il processo di selezione in tale applicazione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-134">If you use a separate recruiting application, completing these steps will send a recruiting request and start the recruiting process in that application.</span></span> <span data-ttu-id="f50e3-135">Altrimenti, completare questa procedura per iniziare il flusso di lavoro per il processo di selezione interno.</span><span class="sxs-lookup"><span data-stu-id="f50e3-135">Otherwise, complete this procedure to begin the workflow for your own internal recruiting process.</span></span>

1. <span data-ttu-id="f50e3-136">Selezionare **Self-service dipendenti**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-136">Select **Employee self service**.</span></span>

2. <span data-ttu-id="f50e3-137">Selezionare la scheda **Team personale**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-137">Select the **My team** tab.</span></span>

3. <span data-ttu-id="f50e3-138">Selezionare **Richiesta di selezione**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-138">Select  **Request to recruit**.</span></span>

   ![Avviare una richiesta di selezione](./media/hr-recruit-1-request-to-recruit.png)

4. <span data-ttu-id="f50e3-140">Completare i campi **Descrizione**, **Lavoro** e **Data di inizio stimata**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-140">Complete the **Description**, **Job**, and **Estimated start date** fields.</span></span>

   ![Completare la richiesta di selezione](./media/hr-recruit-2-request-to-recruit.png)

5. <span data-ttu-id="f50e3-142">Selezionare **Continua**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-142">Select **Continue**.</span></span> <span data-ttu-id="f50e3-143">Viene visualizzata la richiesta di selezione per la posizione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-143">The recruiting request for your position appears.</span></span>

6. <span data-ttu-id="f50e3-144">In **Generale**, selezionare un responsabile assunzioni dal menu a discesa **Responsabile assunzioni** quindi selezionare una posizione nel menu a discesa **Posizione richiesta di selezione**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-144">Under **General**, select a recruiter from the **Recruiter** dropdown, and then select a location from the **Recruiting request location** dropdown.</span></span>

7. <span data-ttu-id="f50e3-145">In **Lavoro**, modificare le informazioni in base alle esigenze, quindi selezionare **Crea dettagli dal lavoro**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-145">Under **Job**, change any information as needed, and then select **Create details from job**.</span></span>

   ![Crea dettagli dalla mansione](./media/hr-recruit-3-create-details-from-job.png)

   <span data-ttu-id="f50e3-147">Il resto della richiesta di selezione verrà compilato con le informazioni predefinite per il lavoro inserito.</span><span class="sxs-lookup"><span data-stu-id="f50e3-147">The rest of the recruiting request will populate with the default information for the job you entered.</span></span>

8. <span data-ttu-id="f50e3-148">In **Descrizione esterna**, inserire una descrizione del lavoro per l'esterno.</span><span class="sxs-lookup"><span data-stu-id="f50e3-148">Under **External description**, enter an external-facing job description.</span></span>

9. <span data-ttu-id="f50e3-149">In **Posizioni**, selezionare **Aggiungi**, quindi selezionare una posizione per questa richiesta di selezione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-149">Under **Positions**, select **Add**, and then select a position for this recruiting request.</span></span>

   ![Aggiungere una posizione](./media/hr-recruit-4-select-position.png)

10. <span data-ttu-id="f50e3-151">In **Competenze**, selezionare **Aggiungi**, quindi selezionare una competenza.</span><span class="sxs-lookup"><span data-stu-id="f50e3-151">Under **Skills**, select **Add**, and then select a skill.</span></span>

11. <span data-ttu-id="f50e3-152">In **Requisiti di istruzione**, selezionare **Aggiungi**, quindi selezionare i valori dai menu a discesa **Istruzione** e **Livello di istruzione**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-152">Under **Educational requirements**, select **Add**, and then select values from the **Education** and **Level of education** dropdowns.</span></span>

   ![Aggiungere i requisiti di istruzione](./media/hr-recruit-5-select-educational-requirements.png)

12. <span data-ttu-id="f50e3-154">In **Commento**, aggiungere commenti se necessario.</span><span class="sxs-lookup"><span data-stu-id="f50e3-154">Under **Comment**, add comments as necessary.</span></span>

13. <span data-ttu-id="f50e3-155">In **Compensazione**, selezionare un livello dal menu a discesa **Livello** e quindi regolare **Soglia bassa**, **Punto di controllo**, e **Soglia alta** come necessario.</span><span class="sxs-lookup"><span data-stu-id="f50e3-155">Under **Compensation**, select a level from the **Level** dropdown, and then adjust **Low threshold**, **Control point**, and **High threshold** as necessary.</span></span>

14. <span data-ttu-id="f50e3-156">Quando la richiesta di selezione è completa e si è pronti per iniziare il processo di selezione, selezionare **Attiva** nella barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="f50e3-156">When your recruiting request is complete and you're ready to start the recruiting process, select **Activate** in the menu bar.</span></span>

   ![Attivare la richiesta di selezione](./media/hr-recruit-6-activate-recruit-request.png)

15. <span data-ttu-id="f50e3-158">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-158">Select **Save**.</span></span>

## <a name="view-and-edit-your-recruiting-requests"></a><span data-ttu-id="f50e3-159">Visualizzare e modificare le richieste di selezione</span><span class="sxs-lookup"><span data-stu-id="f50e3-159">View and edit your recruiting requests</span></span>

<span data-ttu-id="f50e3-160">Se si è un responsabile e si desidera visualizzare le richieste:</span><span class="sxs-lookup"><span data-stu-id="f50e3-160">If you're a manager and want to view your own requests:</span></span>

1. <span data-ttu-id="f50e3-161">Selezionare **Self-service dipendenti**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-161">Select **Employee self service**.</span></span>

2. <span data-ttu-id="f50e3-162">Selezionare la scheda **Team personale**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-162">Select the **My team** tab.</span></span>

3. <span data-ttu-id="f50e3-163">In **Informazioni team personale**, selezionare la scheda **Richieste di selezione**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-163">Under **My team information**, select the **Recruiting requests** tab.</span></span>

   ![Selezionare la scheda Richieste di selezione](./media/hr-recruit-7-recruiting-requests.png)

4. <span data-ttu-id="f50e3-165">Per visualizzare o modificare una richiesta di selezione, selezionarla nella griglia.</span><span class="sxs-lookup"><span data-stu-id="f50e3-165">To view or edit a recruiting request, select it in the grid.</span></span>

<span data-ttu-id="f50e3-166">Se si è un professionista delle risorse umane e si desidera visualizzare tutte le richieste di selezione:</span><span class="sxs-lookup"><span data-stu-id="f50e3-166">If you're an HR pro and want to view all recruiting requests:</span></span>

1. <span data-ttu-id="f50e3-167">Selezionare **Gestione personale**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-167">Select **Personnel management**.</span></span>

2. <span data-ttu-id="f50e3-168">Selezionare **Richieste di selezione**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-168">Select **Recruiting requests**.</span></span>

   ![Visualizzare le richieste di selezione in Gestione personale](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. <span data-ttu-id="f50e3-170">Per visualizzare o modificare una richiesta di selezione, selezionarla nella griglia.</span><span class="sxs-lookup"><span data-stu-id="f50e3-170">To view or edit a recruiting request, select it in the grid.</span></span>

## <a name="add-or-edit-a-candidate-profile"></a><span data-ttu-id="f50e3-171">Aggiungere o modificare un profilo candidato</span><span class="sxs-lookup"><span data-stu-id="f50e3-171">Add or edit a candidate profile</span></span>

<span data-ttu-id="f50e3-172">Se l'organizzazione è integrata con un'altra applicazione per gestire le richieste di selezione, le richieste di selezione vengono inoltrate a tale applicazione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-172">If your organization has integrated with another application to manage recruiting requests, recruiting requests are forwarded to that application.</span></span> <span data-ttu-id="f50e3-173">L'applicazione di selezione invia quindi le informazioni sul candidato a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f50e3-173">The recruiting application then sends candidate information back to Human Resources.</span></span> <span data-ttu-id="f50e3-174">Altrimenti, è possibile seguire i processi interni di selezione e inserire manualmente le informazioni sui candidati.</span><span class="sxs-lookup"><span data-stu-id="f50e3-174">Otherwise, you can follow your own internal recruiting processes and enter candidate information manually.</span></span>

1. <span data-ttu-id="f50e3-175">Selezionare **Gestione personale**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-175">Select **Personnel management**.</span></span>

2. <span data-ttu-id="f50e3-176">Selezionare **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-176">Select **Links**.</span></span>

3. <span data-ttu-id="f50e3-177">Sotto **Selezione**, selezionare **Candidati**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-177">Under **Recruiting**, select **Candidates**.</span></span>

   ![Visualizzare i candidati](./media/hr-recruit-9-candidates.png)

4. <span data-ttu-id="f50e3-179">Per aggiungere un candidato, selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-179">To add a candidate, select **New**.</span></span> <span data-ttu-id="f50e3-180">Per modificare un candidato esistente, selezionare il candidato dall'elenco, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-180">To edit an existing candidate, select the candidate from the list and then select **Edit**.</span></span> <span data-ttu-id="f50e3-181">Viene visualizzato il profilo del candidato.</span><span class="sxs-lookup"><span data-stu-id="f50e3-181">The candidate profile appears.</span></span>

5. <span data-ttu-id="f50e3-182">Sotto **Riepilogo candidato**, immettere o modificare le informazioni sul candidato secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="f50e3-182">Under **Candidate summary**, enter or edit the candidate information as necessary.</span></span>

6. <span data-ttu-id="f50e3-183">Sotto **Richiesta di selezione**, selezionare una richiesta di selezione a cui collegare il candidato.</span><span class="sxs-lookup"><span data-stu-id="f50e3-183">Under **Recruiting request**, select a recruiting request to link the candidate to.</span></span> <span data-ttu-id="f50e3-184">Quindi completare i campi **Data di inizio stimata**, **Responsabile assunzioni**, **Posizione** e **Descrizione** come appropriato.</span><span class="sxs-lookup"><span data-stu-id="f50e3-184">Then complete the **Estimated start date**, **Hiring manager**, **Position**, and **Description fields** as appropriate.</span></span>

   ![Collegare una richiesta di selezione](./media/hr-recruit-10-link-to-recruiting-request.png)

7. <span data-ttu-id="f50e3-186">Completare tutte le informazioni nelle seguenti aree che si desidera includere nel record del candidato:</span><span class="sxs-lookup"><span data-stu-id="f50e3-186">Complete all the information in the following areas that you want to include in the candidate's record:</span></span>
   - <span data-ttu-id="f50e3-187">**Commenti**</span><span class="sxs-lookup"><span data-stu-id="f50e3-187">**Comments**</span></span>
   - <span data-ttu-id="f50e3-188">**Esperienza professionale**</span><span class="sxs-lookup"><span data-stu-id="f50e3-188">**Professional experience**</span></span>
   - <span data-ttu-id="f50e3-189">**Informazioni contatto**</span><span class="sxs-lookup"><span data-stu-id="f50e3-189">**Contact information**</span></span>
   - <span data-ttu-id="f50e3-190">**Percorso formativo**</span><span class="sxs-lookup"><span data-stu-id="f50e3-190">**Education**</span></span>
   - <span data-ttu-id="f50e3-191">**Competenze**</span><span class="sxs-lookup"><span data-stu-id="f50e3-191">**Skills**</span></span>
   - <span data-ttu-id="f50e3-192">**Attestati**</span><span class="sxs-lookup"><span data-stu-id="f50e3-192">**Certificates**</span></span>
   - <span data-ttu-id="f50e3-193">**Screening**</span><span class="sxs-lookup"><span data-stu-id="f50e3-193">**Screenings**</span></span>

8. <span data-ttu-id="f50e3-194">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-194">Select **Save**.</span></span>

## <a name="hire-a-candidate"></a><span data-ttu-id="f50e3-195">Assumere un candidato</span><span class="sxs-lookup"><span data-stu-id="f50e3-195">Hire a candidate</span></span>

<span data-ttu-id="f50e3-196">Quando si è pronti per assumere un candidato, seguire questa procedura per passare il candidato a dipendente.</span><span class="sxs-lookup"><span data-stu-id="f50e3-196">When you're ready to hire a candidate, follow this procedure to transition the candidate to an employee.</span></span>

1. <span data-ttu-id="f50e3-197">Nel modulo del candidato, selezionare **Assumi**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-197">On the candidate form, select **Hire**.</span></span>

   ![Assumere un candidato](./media/hr-recruit-11-hire.png)

2. <span data-ttu-id="f50e3-199">Nel modulo **Assumi nuovo lavoratore** sotto **Dettagli**, completare tutti i campi.</span><span class="sxs-lookup"><span data-stu-id="f50e3-199">On the **Hire new worker** form, under **Details**, complete all the fields.</span></span>

   ![Inserire i dettagli della nuova assunzione](./media/hr-recruit-12-hire-new-worker.png)

3. <span data-ttu-id="f50e3-201">Sotto **Dettagli posizione**, verificare e modificare le informazioni secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="f50e3-201">Under **Position details**, verify and change information as necessary.</span></span>

4. <span data-ttu-id="f50e3-202">Sotto **Elenchi di controllo per l'integrazione**, selezionare gli elenchi di controllo per l'integrazione pertinenti per questo dipendente.</span><span class="sxs-lookup"><span data-stu-id="f50e3-202">Under **Onboarding checklists**, select the relevant onboarding checklists for this employee.</span></span>

5. <span data-ttu-id="f50e3-203">Selezionare **Continua** per creare il record del dipendente.</span><span class="sxs-lookup"><span data-stu-id="f50e3-203">Select **Continue** to create the employee record.</span></span>

   >[!NOTE]
   ><span data-ttu-id="f50e3-204">A seconda dei flussi di lavoro dell'organizzazione, il record del candidato può essere sottoposto a ulteriori passaggi di approvazione prima di diventare un record del dipendente.</span><span class="sxs-lookup"><span data-stu-id="f50e3-204">Depending on your organization's workflows, the candidate record may go through additional approval steps before becoming an employee record.</span></span>

## <a name="decide-not-to-hire-a-candidate"></a><span data-ttu-id="f50e3-205">Decidere di non assumere un candidato</span><span class="sxs-lookup"><span data-stu-id="f50e3-205">Decide not to hire a candidate</span></span>

<span data-ttu-id="f50e3-206">Se si decide di non assumere un candidato, seguire questa procedura per rimuoverlo dal processo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="f50e3-206">If you decide not to hire a candidate, follow this procedure to remove them from the vetting process.</span></span> 

1. <span data-ttu-id="f50e3-207">Nel modulo del candidato, selezionare **Non assumere**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-207">On the candidate form, select **Do not hire**.</span></span>

   ![Non assumere un candidato](./media/hr-recruit-13-do-not-hire.png)

2. <span data-ttu-id="f50e3-209">Selezionare un **Codice motivo** e includere eventuali commenti.</span><span class="sxs-lookup"><span data-stu-id="f50e3-209">Select a **Reason code** and include any comments.</span></span>

3. <span data-ttu-id="f50e3-210">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-210">Select **OK**.</span></span>

## <a name="dismiss-a-candidate"></a><span data-ttu-id="f50e3-211">Licenziare un candidato</span><span class="sxs-lookup"><span data-stu-id="f50e3-211">Dismiss a candidate</span></span>

<span data-ttu-id="f50e3-212">Se necessario, è possibile licenziare un candidato dopo averlo assunto.</span><span class="sxs-lookup"><span data-stu-id="f50e3-212">If needed, you can dismiss a candidate after hiring them.</span></span> <span data-ttu-id="f50e3-213">Ad esempio, un candidato potrebbe rifiutare l'offerta o non presentarsi il primo giorno.</span><span class="sxs-lookup"><span data-stu-id="f50e3-213">For example, a candidate might reject your offer or not show up on their first day.</span></span>

- <span data-ttu-id="f50e3-214">Nel modulo del candidato, selezionare **Licenzia candidato**.</span><span class="sxs-lookup"><span data-stu-id="f50e3-214">On the candidate form, select **Dismiss candidate**.</span></span>

  ![Chiudi il candidato](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a><span data-ttu-id="f50e3-216">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f50e3-216">See also</span></span>

[<span data-ttu-id="f50e3-217">Configurare tabelle virtuali in Dataverse</span><span class="sxs-lookup"><span data-stu-id="f50e3-217">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="f50e3-218">Organizzare la forza lavoro</span><span class="sxs-lookup"><span data-stu-id="f50e3-218">Organize your workforce</span></span>](hr-personnel-departments-jobs-positions.md)<br>
[<span data-ttu-id="f50e3-219">Impostare i componenti di una mansione</span><span class="sxs-lookup"><span data-stu-id="f50e3-219">Set up the components of a job</span></span>](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
