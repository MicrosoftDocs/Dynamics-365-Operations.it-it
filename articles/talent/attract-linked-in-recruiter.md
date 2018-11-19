---
title: Cercare candidati con LinkedIn Recruiter
description: In questo argomento vengono fornite informazioni sull'uso dell'apprendimento automatico per ottenere suggerimenti su mansioni e candidati.
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2fc6bf25d303d7d8de8002a923a080b90dcfbeab
ms.openlocfilehash: 106103e2c3d8f3d89aac5140174e5794da22536f
ms.contentlocale: it-it
ms.lasthandoff: 10/24/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a><span data-ttu-id="05300-103">Cercare candidati con LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="05300-103">Sourcing with LinkedIn Recruiter</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="05300-104">LinkedIn è il più grande database di talenti del mondo e spesso il sistema primario che utilizzano i selezionatori per trovare e comunicare con i candidati per le posizioni che devono coprire.</span><span class="sxs-lookup"><span data-stu-id="05300-104">LinkedIn is the world’s largest talent database and often the primary system that recruiters use to find, communicate with, and source candidates for the jobs that recruiters are looking to fill.</span></span> <span data-ttu-id="05300-105">L'integrazione di LinkedIn Recruiter con Dynamics 365 for Talent: Attract  facilita le assunzioni e il mantenimento della sincronizzazione dei dati tra i due sistemi.</span><span class="sxs-lookup"><span data-stu-id="05300-105">LinkedIn Recruiter integration with Dynamics 365 for Talent: Attract makes it easier for users to hire, and to keep the data in sync between the two systems.</span></span>

> [!NOTE]
> <span data-ttu-id="05300-106">È necessario disporre del componente aggiuntivo per l'assunzione a livello globale e postazioni di LinkedIn Recruiter per poter utilizzare l'integrazione di LinkedIn Recruiter con Attract.</span><span class="sxs-lookup"><span data-stu-id="05300-106">You need the Comprehensive hiring add-on and LinkedIn Recruiter seats to be able to use LinkedIn Recruiter integration with Attract.</span></span>

## <a name="set-up-linkedin-recruiter-with-attract"></a><span data-ttu-id="05300-107">Impostare LinkedIn Recruiter con Attract</span><span class="sxs-lookup"><span data-stu-id="05300-107">Set up LinkedIn Recruiter with Attract</span></span> 

<span data-ttu-id="05300-108">Prima di utilizzare le funzioni di LinkedIn Recruiter, è necessario configurare l'accesso a livello di contratto o a livello di società con l'istanza di Attract.</span><span class="sxs-lookup"><span data-stu-id="05300-108">Before you can use the LinkedIn Recruiter capabilities, you must configure contract-level or company-level access with your Attract instance.</span></span> <span data-ttu-id="05300-109">Per completare il processo di configurazione, è necessario utilizzare l'utente che è l'amministratore nel contratto LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="05300-109">To complete the configuration process, you must work with the user who is an Admin on your LinkedIn Recruiter contract.</span></span> <span data-ttu-id="05300-110">Completare i passaggi seguenti per configurare LinkedIn Recruiter con Attract.</span><span class="sxs-lookup"><span data-stu-id="05300-110">Complete the following steps to configure LinkedIn Recruiter with Attract.</span></span>

1.  <span data-ttu-id="05300-111">Accedere ad Attract come amministratore e passare a **Impostazioni di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="05300-111">Sign in to Attract as an Admin and go to **Admin Settings**.</span></span>

2.  <span data-ttu-id="05300-112">Nel riquadro sinistro, fare clic sulla scheda **Integrazione di LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="05300-112">On the left pane, click the **LinkedIn Integration** tab.</span></span>

<span data-ttu-id="05300-113">[![Visualizzazione amministratore di Attract per avviare l'integrazione di LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span><span class="sxs-lookup"><span data-stu-id="05300-113">[![Attract Admin view to start LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span></span>

3.  <span data-ttu-id="05300-114">Scegliere **Connetti** per avviare la configurazione ed essere guidati nel processo di accesso a LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="05300-114">Click **Connect** to start the setup and be guided through the LinkedIn sign-in process.</span></span>

4.  <span data-ttu-id="05300-115">Se si dispone di postazioni in più contratti LinkedIn, selezionare il contratto da connettere al sistema Attract.</span><span class="sxs-lookup"><span data-stu-id="05300-115">If you have seats on multiple LinkedIn contracts, select the contract that you would like to connect to the Attract system.</span></span> <span data-ttu-id="05300-116">Se si dispone di una postazione in un solo contratto LinkedIn, questo passaggio non sarà necessario.</span><span class="sxs-lookup"><span data-stu-id="05300-116">If you have a seat on only one LinkedIn contract, this step will not be needed.</span></span>

5.  <span data-ttu-id="05300-117">Il widget LinkedIn ora si caricherà nelle impostazioni di amministrazione con l'elenco delle integrazioni mostrato.</span><span class="sxs-lookup"><span data-stu-id="05300-117">The LinkedIn widget will now load in your Admin settings with the list of integrations shown.</span></span> <span data-ttu-id="05300-118">In **Recruiter System Connect**, fare clic su **Richiesta**.</span><span class="sxs-lookup"><span data-stu-id="05300-118">Under **Recruiter System connect**, click **Request**.</span></span>

<span data-ttu-id="05300-119">[![Visualizzazione amministratore di Attract per richiedere l'integrazione di LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span><span class="sxs-lookup"><span data-stu-id="05300-119">[![Attract Admin view to Request LinkedIn Recruiter integration](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span></span>

6.  <span data-ttu-id="05300-120">Dopo che l'integrazione è richiesta da Attract, verrà visualizzato come **Pronto per partner** ed è pronta per essere attivata da **Impostazioni amministratore Recruiter**.</span><span class="sxs-lookup"><span data-stu-id="05300-120">After the integration is requested from Attract, it will show as **Partner ready** and is ready to be turned on from **Recruiter Admin settings**.</span></span> <span data-ttu-id="05300-121">Se viene visualizzato **Notifica partner** in questa pagina, attendere alcuni secondi, fare clic su **Notifica partner**, quindi aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="05300-121">If you see **Notify partner** on this page, wait a few seconds, click **Notify partner**, and then refresh the page.</span></span> <span data-ttu-id="05300-122">Deve ora visualizzare **Pronto per partner**.</span><span class="sxs-lookup"><span data-stu-id="05300-122">It should now show as **Partner ready**.</span></span>

<span data-ttu-id="05300-123">[![Visualizzazione amministratore di Attract per indicare che il lato Attract delle richieste è stato completato](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span><span class="sxs-lookup"><span data-stu-id="05300-123">[![Attract Admin view to indicate Attract side of requests have been completed](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span></span>

<span data-ttu-id="05300-124">Per completare il passaggio successivo, è necessario disporre di un privilegio di amministrazione per il contratto LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="05300-124">To complete the next step, you need to have an Admin privilege on your LinkedIn Recruiter Contract.</span></span>

7.  <span data-ttu-id="05300-125">Accedere a LinkedIn utilizzando l'account amministratore e passare a LinkedIn Recruiter in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="05300-125">Sign in to LinkedIn using the Admin account and go to LinkedIn Recruiter on the top right.</span></span> 

8. <span data-ttu-id="05300-126">Nel menu **Altro** nella parte superiore della schermata, fare clic su **Impostazioni amministratore** e quindi sulla scheda **ATS**.</span><span class="sxs-lookup"><span data-stu-id="05300-126">On the **More** menu at the top of the screen, click **Admin Settings**, and then click the **ATS** Tab.</span></span>

<span data-ttu-id="05300-127">Il sistema Attract verrà visualizzato con una coppia di opzioni che è possibile attivare.</span><span class="sxs-lookup"><span data-stu-id="05300-127">The Attract system will be listed with a couple of options that can be turned on.</span></span>

9. <span data-ttu-id="05300-128">Se si desidera consentire solo l'esportazione con 1 clic per **Indicatore In-ATS** e **Widget profilo In-ATS**, selezionare **Accesso a livello di società**.</span><span class="sxs-lookup"><span data-stu-id="05300-128">If you want to enable only 1-Click export for the **In-ATS indicator** and the **In-ATS Profile Widget**, select **Company-level access**.</span></span> <span data-ttu-id="05300-129">Se si desidera abilitare tutte le funzionalità di accesso a livello di società più l'accesso allo storico di InMail, allo storico di Note e al profilo stub di InMail, selezionare **Accesso a livello di società**.</span><span class="sxs-lookup"><span data-stu-id="05300-129">If you want to enable all of Company-level access features plus InMail history, Notes history, and the InMail stub profile access, select **Contract-level access**.</span></span>

10. <span data-ttu-id="05300-130">Attivare il livello di accesso desiderato dalle impostazioni **Admin-ATS** di LinkedIn Rectuiter.</span><span class="sxs-lookup"><span data-stu-id="05300-130">Turn on the desired access level from your LinkedIn Recruiter **Admin-ATS** settings.</span></span>

<span data-ttu-id="05300-131">[![Attivare l'integrazione di Attract dalla visualizzazione amministratore di LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)</span><span class="sxs-lookup"><span data-stu-id="05300-131">[![Turn on Attract integration from LinkedIn Recruiter Admin view](./media/EnableRSC.png)](./media/EnableRSC.png)</span></span>

12. <span data-ttu-id="05300-132">Tornare alle impostazioni di amministrazione di Attract come AttractAdmin e selezionare la scheda **Integrazione di LinkedIn**. È ora possibile visualizzare il carico del widget LinkedIn che mostra **Abilitato** con il livello selezionato abilitato.</span><span class="sxs-lookup"><span data-stu-id="05300-132">Go back to Attract Admin Settings as an AttractAdmin and select the **LinkedIn integration** tab. You should now see the LinkedIn widget load showing **Enabled** with the selected access level turned on.</span></span>

<span data-ttu-id="05300-133">[![Integrazione di LinkedIn Recruiter completata](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span><span class="sxs-lookup"><span data-stu-id="05300-133">[![LinkedIn Recruiter integration complete](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span></span>

## <a name="using-linkedin-recruiter-capabilities"></a><span data-ttu-id="05300-134">Utilizzo delle funzionalità di LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="05300-134">Using LinkedIn Recruiter capabilities</span></span>

<span data-ttu-id="05300-135">Dopo che le funzionalità di LinkedIn Recruiter è stato attivato dall'amministratore di Attract, sono disponibili all'accesso da parte dei selezionatori e i responsabili delle assunzioni.</span><span class="sxs-lookup"><span data-stu-id="05300-135">After LinkedIn Recruiter capabilities has been enabled by the Attract Admin it is available for hiring managers and recruiters to access.</span></span> <span data-ttu-id="05300-136">Per utilizzare queste funzionalità, connettere l'account LinkedIn in **Impostazioni utenti**.</span><span class="sxs-lookup"><span data-stu-id="05300-136">To use these capabilities, connect your LinkedIn account under **User Settings**.</span></span> <span data-ttu-id="05300-137">Diverse funzionalità saranno disponibili anche dopo che le impostazioni amministratore e utente sono state connesse.</span><span class="sxs-lookup"><span data-stu-id="05300-137">Several capabilities will be available after both the Admin and User settings have been connected.</span></span>

### <a name="in-ats-profile-widget"></a><span data-ttu-id="05300-138">Widget del profilo In-ATS</span><span class="sxs-lookup"><span data-stu-id="05300-138">In-ATS profile widget</span></span>

<span data-ttu-id="05300-139">È possibile visualizzare il profilo LinkedIn del candidato in Attract.</span><span class="sxs-lookup"><span data-stu-id="05300-139">You can view the candidate’s LinkedIn profile in Attract.</span></span> <span data-ttu-id="05300-140">Il widget LinkedIn visualizzerà il profilo del candidato quando le informazioni ATS corrispondono alle informazioni LinkedIn degli utenti.</span><span class="sxs-lookup"><span data-stu-id="05300-140">The LinkedIn widget will display the candidate profile when the ATS information matches the LinkedIn information of its users.</span></span>

<span data-ttu-id="05300-141">Per visualizzare un profilo, andare al profilo del candidato da una posizione lavorativa o un pool di talenti.</span><span class="sxs-lookup"><span data-stu-id="05300-141">To view a profile, go the candidate profile either from a job or talent pool.</span></span> <span data-ttu-id="05300-142">Nel profilo del candidato, selezionare la scheda **LinkedIn** e il widget del profilo verrà caricato.</span><span class="sxs-lookup"><span data-stu-id="05300-142">In the candidate profile, select the **LinkedIn** tab and the profile widget will load.</span></span> <span data-ttu-id="05300-143">Utilizzando il widget del profilo, indicare se si tratta della corrispondenza corretta.</span><span class="sxs-lookup"><span data-stu-id="05300-143">Using the profile widget, indicate if this is the correct match.</span></span> <span data-ttu-id="05300-144">In caso contrario, individuare la persona corretta.</span><span class="sxs-lookup"><span data-stu-id="05300-144">If it is not, find the correct person.</span></span> <span data-ttu-id="05300-145">È inoltre possibile salvare il candidato nei progetti di LinkedIn Recruiter da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="05300-145">You can also save the candidate to your LinkedIn Recruiter projects from this page.</span></span>

### <a name="1-click-export"></a><span data-ttu-id="05300-146">Esportazione con 1 clic</span><span class="sxs-lookup"><span data-stu-id="05300-146">1-click export</span></span> 

<span data-ttu-id="05300-147">Durante la selezione dei candidati in LinkedIn è possibile esportare con 1 clic il candidato nelle mansioni attualmente aperte.</span><span class="sxs-lookup"><span data-stu-id="05300-147">While sourcing candidates in LinkedIn, you can 1-click export the candidate to the jobs that you currently have open.</span></span> <span data-ttu-id="05300-148">Completare i passaggi seguenti per una esportazione con 1 clic.</span><span class="sxs-lookup"><span data-stu-id="05300-148">Complete the following steps for a 1-click export.</span></span> <span data-ttu-id="05300-149">Prima di completare questi passaggi, verificare di disporre del ruolo di responsabile assunzioni o selezionatore per la mansione e che la fase della mansione sia **Candidato**.</span><span class="sxs-lookup"><span data-stu-id="05300-149">Before you complete these steps, verify that you are a assigned the role of Hiring manager or Recruiter for the job and that the job has a **Prospect** stage.</span></span>

1.  <span data-ttu-id="05300-150">Creare la mansione, assegnare i ruoli appropriati e attivare la mansione.</span><span class="sxs-lookup"><span data-stu-id="05300-150">Create the job, assign the appropriate roles, and activate the job.</span></span>

2.  <span data-ttu-id="05300-151">Quando la mansione viene attivato, passare a LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="05300-151">When the job is activated, navigate to LinkedIn Recruiter.</span></span>

3.  <span data-ttu-id="05300-152">Individuare il candidato che si desidera trovare e passare al profilo.</span><span class="sxs-lookup"><span data-stu-id="05300-152">Find the candidate that you are looking for and go to their profile.</span></span>

4.  <span data-ttu-id="05300-153">Utilizzando la casella di ricerca mansioni nella scheda contatto, trovare la mansione mediante il titolo o l'ID mansione che è stato attivato in Attract.</span><span class="sxs-lookup"><span data-stu-id="05300-153">Using the job search box in the contact card, find the job using the title or the Job ID that was activated in Attract.</span></span> <span data-ttu-id="05300-154">Se non viene individuata la mansione, fare clic su **Cambia ATS** per individuare la corretta istanza di Attract.</span><span class="sxs-lookup"><span data-stu-id="05300-154">If you don’t find the job, click **Change ATS** to find the correct Attract instance.</span></span>

5. <span data-ttu-id="05300-155">Dopo che la mansione è selezionata, fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="05300-155">After the job is selected, click **Export**.</span></span> <span data-ttu-id="05300-156">Il candidato viene ora recuperato da Attract.</span><span class="sxs-lookup"><span data-stu-id="05300-156">The candidate is now fetched by Attract.</span></span>

6.  <span data-ttu-id="05300-157">Passare ad Attract e aprire la rispettiva mansione.</span><span class="sxs-lookup"><span data-stu-id="05300-157">Go to Attract and open the respective job.</span></span> <span data-ttu-id="05300-158">Il candidato appena esportato si troverà nella fase **Candidato** del processo.</span><span class="sxs-lookup"><span data-stu-id="05300-158">You will find the candidate that you just exported in the **Prospect** stage of the job.</span></span>

### <a name="in-ats-indicator"></a><span data-ttu-id="05300-159">Indicatore In-ATS</span><span class="sxs-lookup"><span data-stu-id="05300-159">In-ATS indicator</span></span> 

<span data-ttu-id="05300-160">Utilizzando LinkedIn Recruiter, è possibile tenere traccia se un candidato ha fatto domanda per altre mansioni nell'organizzazione, vedere le fasi in cui si trova nelle domande di lavoro e visualizzare il riscontro e i commenti da Attract in LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="05300-160">Using LinkedIn recruiter, you can track whether a candidate has applied to other jobs in your organization, look at where they are in different stages of job applications, and view the feedback and comments from Attract in LinkedIn Recruiter.</span></span>

1.  <span data-ttu-id="05300-161">Aprire LinkedIn Recruiter e individuare il profilo del candidato richiesto.</span><span class="sxs-lookup"><span data-stu-id="05300-161">Open LinkedIn Recruiter and locate the candidate profile that you are looking for.</span></span>

2.  <span data-ttu-id="05300-162">Scorrere fino a visualizzare la sezione **In-ATS** del profilo del candidato.</span><span class="sxs-lookup"><span data-stu-id="05300-162">Scroll down to view the **In-ATS** section on the candidate’s profile.</span></span>

3.  <span data-ttu-id="05300-163">È possibile utilizzare questo widget per visualizzare tutte le informazioni sul candidato che sono presenti in Attract dalla visualizzazione di LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="05300-163">You can use this widget to view all of the information about the candidate that’s present in Attract from within the LinkedIn Recruiter view.</span></span>

4.  <span data-ttu-id="05300-164">Selezionare la scheda **Posizioni e stati** per visualizzare le mansioni di cui fa parte, l'ultimo stato e lo spostamento rispetto a ciascuna mansione.</span><span class="sxs-lookup"><span data-stu-id="05300-164">Select the **Jobs & Statuses** tab to see jobs they are part of, the latest status, and how they have been moving against each job.</span></span>

5.  <span data-ttu-id="05300-165">Selezionare la scheda **Feedback colloquio** per visualizzare i commenti che i responsabili del colloquio hanno inviato in Attract.</span><span class="sxs-lookup"><span data-stu-id="05300-165">Select the **Interview Feedback** tab to see feedback that the interviewers have submitted in Attract.</span></span>

6.  <span data-ttu-id="05300-166">Selezionare la scheda **Note** per visualizzare le note che sono state acquisite per il candidato in Attract.</span><span class="sxs-lookup"><span data-stu-id="05300-166">Select the **Notes** tab to see notes that have been captured for this applicant in Attract.</span></span>

### <a name="inmail-history"></a><span data-ttu-id="05300-167">Storico InMail</span><span class="sxs-lookup"><span data-stu-id="05300-167">InMail history</span></span>

<span data-ttu-id="05300-168">Lo storico InMail LinkedIn è disponibile con l'accesso a livello di contratto con LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="05300-168">The LinkedIn InMail history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="05300-169">Quando è abilitato, sarà possibile visualizzare l'intero storico InMail con il candidato.</span><span class="sxs-lookup"><span data-stu-id="05300-169">When it is enabled, you can view your entire InMail history with the candidate.</span></span> <span data-ttu-id="05300-170">È inoltre possibile visualizzare chi altro dell'organizzazione ha scambiato InMail con il candidato, ma non è possibile visualizzare i messaggi scambiati.</span><span class="sxs-lookup"><span data-stu-id="05300-170">You can also see who else from your organization has exchanged InMail with the candidate, however you can't view the messages between them.</span></span>

<span data-ttu-id="05300-171">Per visualizzare lo storico di InMail, passare al profilo di un candidato, passare alla scheda **LinkedIn** e scorrere fini alla parte inferiore della pagina per visualizzare lo storico.</span><span class="sxs-lookup"><span data-stu-id="05300-171">To view InMail history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="05300-172">È possibile visualizzare lo storico di InMail solo se il candidato ha risposto alla richiesta e ha scelto di condividere il proprio profilo con te in LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="05300-172">You can view the InMail history only if the candidate has responded to your request and chosen to share their profile with you in LinkedIn.</span></span> <span data-ttu-id="05300-173">I messaggi da InMail vengono sincronizzati con Attract ogni paio d'ore.</span><span class="sxs-lookup"><span data-stu-id="05300-173">The messages from InMail sync with Attract every couple of hours.</span></span>

### <a name="notes-history"></a><span data-ttu-id="05300-174">Storico delle note</span><span class="sxs-lookup"><span data-stu-id="05300-174">Notes history</span></span> 

<span data-ttu-id="05300-175">Lo storico delle note LinkedIn è disponibile con l'accesso a livello di contratto con LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="05300-175">The LinkedIn notes history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="05300-176">Quando è abilitato, è possibile visualizzare le note che sono state acquisite sul candidato dai singoli selezionatori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="05300-176">When it is enabled, you can view the notes that have been captured about the candidate by different recruiters from your organization.</span></span>

<span data-ttu-id="05300-177">Per visualizzare lo storico delle note, passare al profilo di un candidato, passare alla scheda **LinkedIn** e scorrere fini alla parte inferiore della pagina per visualizzare lo storico.</span><span class="sxs-lookup"><span data-stu-id="05300-177">To view Notes history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="05300-178">È possibile visualizzare tutte le note sul candidato da LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="05300-178">You can view all the notes about the candidate from LinkedIn Recruiter.</span></span>

### <a name="inmail-stub-profile"></a><span data-ttu-id="05300-179">Profilo stub di InMail</span><span class="sxs-lookup"><span data-stu-id="05300-179">InMail stub profile</span></span>

<span data-ttu-id="05300-180">Il profilo stub di InMail è disponibile con l'accesso a livello di contratto con LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="05300-180">The InMail stub profile is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="05300-181">Se i candidati accettano di condividere i propri profili di LinkedIn con qualsiasi utente dell'organizzazione, è possibile tenere traccia dei candidati in Attract e un nuovo record candidato verrà creato per ciascun candidato.</span><span class="sxs-lookup"><span data-stu-id="05300-181">If candidates agree to share their LinkedIn profiles with any user in your organization, you can track the candidates in Attract and a new candidate record will be created for each candidate.</span></span>

<span data-ttu-id="05300-182">Per visualizzare l'elenco dei candidati, andare a **Pool di talenti** per visualizzare un pool di talenti LinkedIn creato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="05300-182">To view the list of candidates, go to **Talent pools** to see a system-created LinkedIn talent pool.</span></span> <span data-ttu-id="05300-183">Questo pool di talenti contiene l'elenco di candidati e i relativi profili stub come ricevuti da LinkedIn, mostrando il nome e cognome del candidato.</span><span class="sxs-lookup"><span data-stu-id="05300-183">This talent pool contains the list candidates and their stub profiles as received from LinkedIn, showing the candidate's first name and last name.</span></span> <span data-ttu-id="05300-184">L'ID di posta elettronica del candidato viene visualizzato nel caso in cui il candidato ha scelto di condividere il proprio indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="05300-184">The candidate’s email ID will be displayed if the candidate had chosen to share their email address.</span></span>

