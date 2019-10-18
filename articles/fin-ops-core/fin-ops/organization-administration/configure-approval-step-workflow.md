---
title: Configurare i passaggi di approvazione in un flusso di lavoro
description: In questo argomento viene descritto come configurare le proprietà per un passaggio del processo di approvazione.
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5bd5300a061e12ccabdea83c20863c95e15fe19
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178565"
---
# <a name="configure-approval-steps-in-a-workflow"></a><span data-ttu-id="5ee50-103">Configurare i passaggi di approvazione in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="5ee50-103">Configure approval steps in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ee50-104">In questo argomento viene descritto come configurare le proprietà per un passaggio del processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-104">This topic explains how to configure the properties of an approval step.</span></span>

<span data-ttu-id="5ee50-105">Per configurare un passaggio di approvazione, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sul passaggio di approvazione, quindi scegliere **Proprietà** per aprire la pagina **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-105">To configure an approval step in the workflow editor, right-click the approval step, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="5ee50-106">Per configurare le proprietà del passaggio di approvazione, attenersi alle procedure indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5ee50-106">Then use the following procedures to configure the properties of the approval step.</span></span>

## <a name="name-the-step"></a><span data-ttu-id="5ee50-107">Assegnare un nome al passaggio</span><span class="sxs-lookup"><span data-stu-id="5ee50-107">Name the step</span></span>
<span data-ttu-id="5ee50-108">Per immettere un nome per il passaggio di approvazione, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5ee50-108">Follow these steps to enter a name for the approval step.</span></span>

1. <span data-ttu-id="5ee50-109">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="5ee50-110">Nel campo **Nome** immettere un nome univoco per il passaggio del processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-110">In the **Name** field, enter a unique name for the approval step.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="5ee50-111">Immettere una riga di argomento e le istruzioni</span><span class="sxs-lookup"><span data-stu-id="5ee50-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="5ee50-112">La riga di argomento e le istruzioni sono necessarie agli utenti assegnati al passaggio di approvazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-112">You must provide a subject line and instructions to users who are assigned to the approval step.</span></span> <span data-ttu-id="5ee50-113">Se ad esempio si configura un passaggio di approvazione per richieste di acquisto, l'utente assegnato al passaggio visualizzerà la riga di argomento e le istruzioni nel modulo **Richieste di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-113">For example, if you're configuring an approval step for purchase requisitions, the user who is assigned to the step sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="5ee50-114">La riga di argomento si trova nella barra dei messaggi della pagina.</span><span class="sxs-lookup"><span data-stu-id="5ee50-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="5ee50-115">L'utente può fare clic sull'icona nella barra per visualizzare le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="5ee50-115">The user can then click the icon in the message bar to see the instructions.</span></span> <span data-ttu-id="5ee50-116">Per immettere una riga di argomento e le istruzioni, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5ee50-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="5ee50-117">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="5ee50-118">Nel campo **Argomento elemento di lavoro** immettere la riga di argomento.</span><span class="sxs-lookup"><span data-stu-id="5ee50-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="5ee50-119">Per personalizzare la riga di argomento, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="5ee50-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="5ee50-120">I segnaposto verranno sostituiti con i dati appropriati al momento della riga di argomento.</span><span class="sxs-lookup"><span data-stu-id="5ee50-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="5ee50-121">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ee50-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="5ee50-122">Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="5ee50-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="5ee50-123">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="5ee50-124">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="5ee50-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="5ee50-125">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-125">Click **Insert**.</span></span>

4. <span data-ttu-id="5ee50-126">Per aggiungere traduzioni della riga di argomento, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ee50-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="5ee50-127">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="5ee50-128">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="5ee50-129">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="5ee50-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="5ee50-130">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="5ee50-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="5ee50-131">Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="5ee50-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="5ee50-132">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-132">Click **Close**.</span></span>

5. <span data-ttu-id="5ee50-133">Nel campo **Istruzioni elemento di lavoro** immettere le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="5ee50-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="5ee50-134">Per personalizzare le istruzioni, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="5ee50-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="5ee50-135">I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="5ee50-136">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ee50-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="5ee50-137">Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="5ee50-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="5ee50-138">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="5ee50-139">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="5ee50-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="5ee50-140">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-140">Click **Insert**.</span></span>

7. <span data-ttu-id="5ee50-141">Per aggiungere traduzioni delle istruzioni, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ee50-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="5ee50-142">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="5ee50-143">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="5ee50-144">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="5ee50-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="5ee50-145">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="5ee50-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="5ee50-146">Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="5ee50-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="5ee50-147">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-147">Click **Close**.</span></span>

## <a name="assign-the-approval-step"></a><span data-ttu-id="5ee50-148">Assegnare il passaggio di approvazione</span><span class="sxs-lookup"><span data-stu-id="5ee50-148">Assign the approval step</span></span>

<span data-ttu-id="5ee50-149">Per specificare gli utenti a cui assegnare il passaggio del processo di approvazione, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5ee50-149">Follow these steps to specify who the approval step should be assigned to.</span></span>

1. <span data-ttu-id="5ee50-150">Nel riquadro sinistro, fare clic sull'icona **Assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="5ee50-151">Nella scheda **Tipo di assegnazione** selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="5ee50-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="5ee50-152">Opzione</span><span class="sxs-lookup"><span data-stu-id="5ee50-152">Option</span></span></th>
    <th><span data-ttu-id="5ee50-153">Utenti a cui viene assegnato il passaggio del processo di approvazione</span><span class="sxs-lookup"><span data-stu-id="5ee50-153">Users that the approval step is assigned to</span></span></th>
    <th><span data-ttu-id="5ee50-154">Passaggi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="5ee50-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="5ee50-155">Partecipante</span><span class="sxs-lookup"><span data-stu-id="5ee50-155">Participant</span></span></td>
    <td><span data-ttu-id="5ee50-156">Utenti assegnati a un ruolo o un gruppo specifico</span><span class="sxs-lookup"><span data-stu-id="5ee50-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5ee50-157">Dopo aver selezionato <strong>Partecipante</strong>, nella scheda <strong>Basato sui ruoli</strong> selezionare il tipo di gruppo o il ruolo a cui assegnare il passaggio nell'elenco <strong>Tipo di partecipante</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the step to.</span></span></li>
    <li><span data-ttu-id="5ee50-158">Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui assegnare il passaggio.</span><span class="sxs-lookup"><span data-stu-id="5ee50-158">In the <strong>Participant</strong> list, select the group or role to assign the step to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5ee50-159">Gerarchia</span><span class="sxs-lookup"><span data-stu-id="5ee50-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="5ee50-160">Utenti in una specifica gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="5ee50-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5ee50-161">Dopo aver selezionato <strong>Gerarchia</strong>, nella scheda <strong>Selezione gerarchia</strong> selezionare il tipo di gerarchia cui assegnare il passaggio nell'elenco <strong>Tipo di gerarchia</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the step to.</span></span></li>
    <li><span data-ttu-id="5ee50-162">Il sistema dovrà recuperare un intervallo di nomi utente dalla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="5ee50-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="5ee50-163">Questi nomi rappresentano gli utenti a cui può essere assegnato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="5ee50-163">These names represent users that the step can be assigned to.</span></span> <span data-ttu-id="5ee50-164">Attenersi alla procedura indicata di seguito per specificare il punto di inizio e il punto finale dell'intervallo di nomi utente recuperati dal sistema:</span><span class="sxs-lookup"><span data-stu-id="5ee50-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="5ee50-165">Per specificare il punto di inizio, selezionare una persona dall'elenco <strong>Inizia da</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="5ee50-166">Per specificare il punto finale, fare clic su <strong>Aggiungi condizione</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="5ee50-167">Immettere quindi una condizione per determinare il punto della gerarchia in cui verrà arrestato il recupero dei nomi da parte del sistema.</span><span class="sxs-lookup"><span data-stu-id="5ee50-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="5ee50-168">Nella scheda <strong>Opzioni gerarchia</strong> specificare a quali utenti nell'intervallo il passaggio deve essere assegnato:</span><span class="sxs-lookup"><span data-stu-id="5ee50-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the step should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="5ee50-169"><strong>Assegna a tutti gli utenti recuperati</strong> - Il passaggio viene assegnato a tutti gli utenti nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="5ee50-169"><strong>Assign to all users retrieved</strong> – The step is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="5ee50-170"><strong>Assegna solo all'ultimo utente recuperato</strong> - Il passaggio viene assegnato solo all'ultimo utente dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="5ee50-170"><strong>Assign only to last user retrieved</strong> – The step is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="5ee50-171"><strong>Escludi utenti con la seguente condizione:</strong> - Il passaggio non viene assegnato ad alcun utente nell'intervallo che soddisfa una specifica condizione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-171"><strong>Exclude users with the following condition</strong> – The step isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="5ee50-172">Fare clic su <strong>Aggiungi condizione</strong> per specificare la condizione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5ee50-173">Utente del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="5ee50-173">Workflow user</span></span></td>
    <td><span data-ttu-id="5ee50-174">Utenti nel flusso di lavoro corrente</span><span class="sxs-lookup"><span data-stu-id="5ee50-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="5ee50-175">Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5ee50-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5ee50-176">Utente</span><span class="sxs-lookup"><span data-stu-id="5ee50-176">User</span></span></td>
    <td><span data-ttu-id="5ee50-177">Utenti specifici</span><span class="sxs-lookup"><span data-stu-id="5ee50-177">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5ee50-178">Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="5ee50-179">Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti del sistema.</span><span class="sxs-lookup"><span data-stu-id="5ee50-179">The <strong>Available users</strong> list includes all system users.</span></span> <span data-ttu-id="5ee50-180">Selezionare gli utenti a cui assegnare il passaggio, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-180">Select the users to assign the step to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="5ee50-181">Nella scheda **Limite di tempo**, nel campo **Durata** specificare il periodo di tempo entro cui un utente deve eseguire un'azione o inviare una risposta per i documenti che giungono al passaggio di approvazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-181">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents that reach the approval step.</span></span> <span data-ttu-id="5ee50-182">Consente di selezionare una delle opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5ee50-182">Select one of the following options:</span></span>

    - <span data-ttu-id="5ee50-183">**Ore**: immettere il numero di ore entro cui l'utente deve inviare una risposta.</span><span class="sxs-lookup"><span data-stu-id="5ee50-183">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="5ee50-184">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-184">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="5ee50-185">**Giorni**: immettere il numero di giorni entro cui l'utente deve inviare una risposta.</span><span class="sxs-lookup"><span data-stu-id="5ee50-185">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="5ee50-186">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-186">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="5ee50-187">**Settimane**: immettere il numero di settimane entro cui l'utente deve inviare una risposta.</span><span class="sxs-lookup"><span data-stu-id="5ee50-187">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="5ee50-188">**Mesi**: selezionare il giorno e la settimana entro cui l'utente deve inviare una risposta.</span><span class="sxs-lookup"><span data-stu-id="5ee50-188">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="5ee50-189">È ad esempio possibile scegliere che l'utente invii una risposta entro il venerdì della terza settimana del mese.</span><span class="sxs-lookup"><span data-stu-id="5ee50-189">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="5ee50-190">**Anni**: selezionare il giorno, la settimana e il mese entro cui l'utente deve inviare una risposta.</span><span class="sxs-lookup"><span data-stu-id="5ee50-190">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="5ee50-191">È ad esempio possibile scegliere che l'utente invii una risposta entro il venerdì della terza settimana di dicembre.</span><span class="sxs-lookup"><span data-stu-id="5ee50-191">For example, you might want the user to respond by Friday of the third week of December.</span></span>

    <span data-ttu-id="5ee50-192">Se l'utente non esegue un'azione sul documento nel tempo prestabilito, il documento scadrà.</span><span class="sxs-lookup"><span data-stu-id="5ee50-192">If the user doesn't take action on the document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="5ee50-193">Un documento scaduto viene riassegnato in base alle opzioni selezionate nell'area **Riassegnazione** della pagina.</span><span class="sxs-lookup"><span data-stu-id="5ee50-193">A document that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

4. <span data-ttu-id="5ee50-194">Se il passaggio di approvazione è stato assegnato a più utenti o a un gruppo di utenti, fare clic sulla scheda **Criteri completamento**, quindi selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ee50-194">If you assigned the approval step to multiple users or a group of users, on the **Completion policy** tab, select one of the following options:</span></span>

    - <span data-ttu-id="5ee50-195">**Approvatore singolo**: l'azione applicata al documento viene determinata dalla persona che risponde per prima.</span><span class="sxs-lookup"><span data-stu-id="5ee50-195">**Single approver** – The action that is applied to the document is determined by the first person who responds.</span></span> <span data-ttu-id="5ee50-196">Si supponga ad esempio che Giorgio abbia inviato una nota spese per un importo pari a USD 15.000.</span><span class="sxs-lookup"><span data-stu-id="5ee50-196">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="5ee50-197">La nota spese è attualmente assegnata a Luisa, Raffaella e Davide.</span><span class="sxs-lookup"><span data-stu-id="5ee50-197">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="5ee50-198">Se Luisa risponde per prima, al documento verrà applicata l'azione eseguita da tale utente.</span><span class="sxs-lookup"><span data-stu-id="5ee50-198">If Sue is the first person who responds to the document, the action that she takes is applied to the document.</span></span> <span data-ttu-id="5ee50-199">Se Luisa rifiuta il documento, la nota spese rifiutata viene reinviata a Giorgio.</span><span class="sxs-lookup"><span data-stu-id="5ee50-199">If Sue rejects the document, it's rejected and sent back to Sam.</span></span> <span data-ttu-id="5ee50-200">Dopo che Luisa avrà approvato il documento, verrà inviato a Elena per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-200">If Sue approves the document, it's sent to Ann for approval.</span></span>

        ![Flusso di lavoro con processo di approvazione](./media/workflow_multipleusersinstep.gif)

    - <span data-ttu-id="5ee50-202">**Maggioranza degli approvatori**: l'azione applicata al documento viene determinata dalla maggioranza degli approvatori che rispondono.</span><span class="sxs-lookup"><span data-stu-id="5ee50-202">**Majority of approvers** – The action that is applied to the document is determined when most of the approvers respond.</span></span> <span data-ttu-id="5ee50-203">Si supponga ad esempio che Giorgio abbia inviato una nota spese per un importo pari a USD 15.000.</span><span class="sxs-lookup"><span data-stu-id="5ee50-203">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="5ee50-204">La nota spese è attualmente assegnata a Luisa, Raffaella e Davide.</span><span class="sxs-lookup"><span data-stu-id="5ee50-204">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="5ee50-205">Se Luisa e Raffaella sono i primi due approvatori a rispondere, al documento verrà applicata l'azione eseguita da tali utenti.</span><span class="sxs-lookup"><span data-stu-id="5ee50-205">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document.</span></span>

        - <span data-ttu-id="5ee50-206">Se Luisa approva il documento e Raffaella lo rifiuta, il documento rifiutato verrà reinviato a Giorgio.</span><span class="sxs-lookup"><span data-stu-id="5ee50-206">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="5ee50-207">Se Luisa e Raffaella approvano il documento, quest'ultimo verrà inviato a Elena per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-207">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="5ee50-208">**Percentuale di approvatori**: l'azione applicata al documento viene determinata da una percentuale specifica di approvatori che rispondono.</span><span class="sxs-lookup"><span data-stu-id="5ee50-208">**Percentage of approvers** – The action that is applied to the document is determined when a specific percentage of the approvers respond.</span></span> <span data-ttu-id="5ee50-209">Si supponga ad esempio che Giorgio abbia inviato una nota spese per un importo pari a USD 15.000.</span><span class="sxs-lookup"><span data-stu-id="5ee50-209">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="5ee50-210">La nota spese è attualmente assegnata a Luisa, Raffaella e Davide e la percentuale immessa è **50**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-210">The expense report is currently assigned to Sue, Jo, and Bill, and you entered **50** as the percentage.</span></span> <span data-ttu-id="5ee50-211">Se Luisa e Raffaella sono i primi due approvatori a rispondere, al documento verrà applicata l'azione eseguita da tali utenti, in quanto soddisfano il requisito per il 50% degli approvatori.</span><span class="sxs-lookup"><span data-stu-id="5ee50-211">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document, because they meet the requirement for 50 percent of approvers.</span></span>

        - <span data-ttu-id="5ee50-212">Se Luisa approva il documento e Raffaella lo rifiuta, il documento rifiutato verrà reinviato a Giorgio.</span><span class="sxs-lookup"><span data-stu-id="5ee50-212">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="5ee50-213">Se Luisa e Raffaella approvano il documento, quest'ultimo verrà inviato a Elena per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-213">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="5ee50-214">**Tutti gli approvatori**: tutti gli approvatori dovranno approvare il documento.</span><span class="sxs-lookup"><span data-stu-id="5ee50-214">**All approvers** – All the approvers must approve the document.</span></span> <span data-ttu-id="5ee50-215">In caso contrario il flusso di lavoro non potrà continuare.</span><span class="sxs-lookup"><span data-stu-id="5ee50-215">Otherwise, the workflow can't continue.</span></span> <span data-ttu-id="5ee50-216">Si supponga ad esempio che Giorgio abbia inviato una nota spese per un importo pari a USD 15.000.</span><span class="sxs-lookup"><span data-stu-id="5ee50-216">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="5ee50-217">La nota spese è attualmente assegnata a Luisa, Raffaella e Davide.</span><span class="sxs-lookup"><span data-stu-id="5ee50-217">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="5ee50-218">Se Luisa e Raffaella approvano il documento e Davide lo rifiuta, il documento rifiutato verrà reinviato a Giorgio.</span><span class="sxs-lookup"><span data-stu-id="5ee50-218">If Sue and Joe approve the document, but Bill rejects it, the document is rejected and sent back to Sam.</span></span> <span data-ttu-id="5ee50-219">Se Luisa, Raffaella e Davide approvano il documento, quest'ultimo viene inviato a Elena per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-219">If Sue, Jo, and Bill all approve the document, it's sent to Ann for approval.</span></span>

## <a name="specify-when-the-approval-step-is-required"></a><span data-ttu-id="5ee50-220">Specificare quando è necessario il passaggio di approvazione</span><span class="sxs-lookup"><span data-stu-id="5ee50-220">Specify when the approval step is required</span></span>

<span data-ttu-id="5ee50-221">È possibile specificare quando è necessario il passaggio di approvazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-221">You can specify when the approval step is required.</span></span> <span data-ttu-id="5ee50-222">Il passaggio di approvazione può essere necessario sempre o solo se vengono soddisfatte specifiche condizioni.</span><span class="sxs-lookup"><span data-stu-id="5ee50-222">The approval step can always be required, or it can be required only if specific conditions are met.</span></span>

### <a name="the-approval-step-is-always-required"></a><span data-ttu-id="5ee50-223">Passaggio di approvazione sempre necessario</span><span class="sxs-lookup"><span data-stu-id="5ee50-223">The approval step is always required</span></span>

<span data-ttu-id="5ee50-224">Se il passaggio di approvazione è sempre necessario, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ee50-224">Follow these steps if the approval step is always required.</span></span>

1. <span data-ttu-id="5ee50-225">Nel riquadro sinistro fare clic su **Condizione**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-225">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="5ee50-226">Selezionare l'opzione **Esegui sempre questo passaggio**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-226">Select the **Always run this step** option.</span></span>

### <a name="the-approval-step-is-required-in-specific-conditions"></a><span data-ttu-id="5ee50-227">Passaggio di approvazione necessario in presenza di condizioni specifiche</span><span class="sxs-lookup"><span data-stu-id="5ee50-227">The approval step is required in specific conditions</span></span>

<span data-ttu-id="5ee50-228">È possibile che il passaggio di approvazione che si sta configurando sia necessario solo se vengono soddisfatte specifiche condizioni.</span><span class="sxs-lookup"><span data-stu-id="5ee50-228">The approval step that you're configuring might be required only if specific conditions are met.</span></span> <span data-ttu-id="5ee50-229">Si supponga ad esempio di dover configurare un passaggio di approvazione per un flusso di lavoro relativo a una richiesta di acquisto e di voler eseguire tale passaggio solo quando l'importo della richiesta di acquisto è maggiore di USD 10.000.</span><span class="sxs-lookup"><span data-stu-id="5ee50-229">For example, if you're configuring an approval step for a purchase requisition workflow, you might want the approval step to occur only if the amount of the purchase requisition is more than USD 10,000.</span></span> <span data-ttu-id="5ee50-230">Per specificare quando è necessario il passaggio di approvazione, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ee50-230">Follow these steps to specify when the approval step is required.</span></span>

1. <span data-ttu-id="5ee50-231">Nel riquadro sinistro fare clic su **Condizione**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-231">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="5ee50-232">Selezionare l'opzione **Esegui questo passaggio solo quando è soddisfatta la seguente condizione**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-232">Select the **Run this step only when the following condition is met** option.</span></span>
3. <span data-ttu-id="5ee50-233">Immettere una condizione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-233">Enter a condition.</span></span>
4. <span data-ttu-id="5ee50-234">Immettere altre condizioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5ee50-234">Enter any additional conditions that are required.</span></span>
5. <span data-ttu-id="5ee50-235">Per verificare la correttezza della configurazione delle condizioni immesse, eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ee50-235">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="5ee50-236">Fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-236">Click **Test**.</span></span>
    2. <span data-ttu-id="5ee50-237">Nella pagina **Test condizione flusso di lavoro**, nell'area **Convalida condizione**, selezionare un record.</span><span class="sxs-lookup"><span data-stu-id="5ee50-237">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="5ee50-238">Fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-238">Click **Test**.</span></span> <span data-ttu-id="5ee50-239">Il sistema valuta il record per determinare se soddisfa le condizioni definite.</span><span class="sxs-lookup"><span data-stu-id="5ee50-239">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="5ee50-240">Fare clic su **OK** o su **Annulla** per tornare alla pagina **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-240">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-what-happens-when-the-document-is-overdue"></a><span data-ttu-id="5ee50-241">Specificare l'azione da eseguire quando il documento è scaduto</span><span class="sxs-lookup"><span data-stu-id="5ee50-241">Specify what happens when the document is overdue</span></span>

<span data-ttu-id="5ee50-242">Se un utente non esegue un'azione su un documento nel tempo prestabilito, il documento scadrà.</span><span class="sxs-lookup"><span data-stu-id="5ee50-242">If a user doesn't take action on a document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="5ee50-243">Un documento scaduto può essere riassegnato o assegnato automaticamente a un altro utente per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-243">A document that is overdue can be escalated, or automatically assigned to another user for approval.</span></span> <span data-ttu-id="5ee50-244">Per riassegnare il documento scaduto, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ee50-244">Follow these steps to escalate the document if it's overdue.</span></span>

1. <span data-ttu-id="5ee50-245">Nel riquadro sinistro fare clic su **Riassegnazione**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-245">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="5ee50-246">Selezionare la casella di controllo **Utilizza percorso di riassegnazione** per creare un percorso di riassegnazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-246">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="5ee50-247">Il documento verrà assegnato automaticamente agli utenti elencati nel percorso.</span><span class="sxs-lookup"><span data-stu-id="5ee50-247">The system automatically assigns the document to the users who are listed in the escalation path.</span></span> <span data-ttu-id="5ee50-248">La tabella indicata di seguito rappresenta un esempio di percorso di riassegnazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-248">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="5ee50-249">Sequenza</span><span class="sxs-lookup"><span data-stu-id="5ee50-249">Sequence</span></span> | <span data-ttu-id="5ee50-250">Percorso di riassegnazione</span><span class="sxs-lookup"><span data-stu-id="5ee50-250">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="5ee50-251">1</span><span class="sxs-lookup"><span data-stu-id="5ee50-251">1</span></span>        | <span data-ttu-id="5ee50-252">Assegna a: Maria</span><span class="sxs-lookup"><span data-stu-id="5ee50-252">Assign to: Donna</span></span>     |
    | <span data-ttu-id="5ee50-253">2</span><span class="sxs-lookup"><span data-stu-id="5ee50-253">2</span></span>        | <span data-ttu-id="5ee50-254">Assegna a: Francesca</span><span class="sxs-lookup"><span data-stu-id="5ee50-254">Assign to: Erin</span></span>      |
    | <span data-ttu-id="5ee50-255">3</span><span class="sxs-lookup"><span data-stu-id="5ee50-255">3</span></span>        | <span data-ttu-id="5ee50-256">Azione finale: Rifiuta</span><span class="sxs-lookup"><span data-stu-id="5ee50-256">Final action: Reject</span></span> |

    <span data-ttu-id="5ee50-257">In questo esempio il documento scaduto viene assegnato a Maria.</span><span class="sxs-lookup"><span data-stu-id="5ee50-257">In this example, the system assigns the overdue document to Donna.</span></span> <span data-ttu-id="5ee50-258">Se Maria non invia una risposta nel tempo prestabilito, il documento verrà assegnato a Francesca.</span><span class="sxs-lookup"><span data-stu-id="5ee50-258">If Donna doesn't respond in the allotted time, the system assigns the document to Erin.</span></span> <span data-ttu-id="5ee50-259">Se Francesca non invia una risposta nel tempo prestabilito, il documento verrà rifiutato.</span><span class="sxs-lookup"><span data-stu-id="5ee50-259">If Erin doesn't respond in the allotted time, the system rejects the document.</span></span>

3. <span data-ttu-id="5ee50-260">Per aggiungere un utente al percorso di riassegnazione, fare clic su **Aggiungi riassegnazione**.</span><span class="sxs-lookup"><span data-stu-id="5ee50-260">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="5ee50-261">Nella scheda **Tipo di assegnazione** selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="5ee50-261">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="5ee50-262">Opzione</span><span class="sxs-lookup"><span data-stu-id="5ee50-262">Option</span></span></th>
    <th><span data-ttu-id="5ee50-263">Utenti a cui viene riassegnato il documento</span><span class="sxs-lookup"><span data-stu-id="5ee50-263">Users that the document is escalated to</span></span></th>
    <th><span data-ttu-id="5ee50-264">Passaggi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="5ee50-264">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="5ee50-265">Gerarchia</span><span class="sxs-lookup"><span data-stu-id="5ee50-265">Hierarchy</span></span></td>
    <td><span data-ttu-id="5ee50-266">Utenti in una specifica gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="5ee50-266">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5ee50-267">Dopo aver selezionato <strong>Gerarchia</strong>, nella scheda <strong>Selezione gerarchia</strong> selezionare il tipo di gerarchia cui riassegnare il documento nell'elenco <strong>Tipo di gerarchia</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-267">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the document to.</span></span></li>
    <li><span data-ttu-id="5ee50-268">Il sistema dovrà recuperare un intervallo di nomi utente dalla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="5ee50-268">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="5ee50-269">Questi nomi rappresentano gli utenti a cui può essere riassegnato il documento.</span><span class="sxs-lookup"><span data-stu-id="5ee50-269">These names represent users that the document can be escalated to.</span></span> <span data-ttu-id="5ee50-270">Attenersi alla procedura indicata di seguito per specificare il punto di inizio e il punto finale dell'intervallo di nomi utente recuperati dal sistema:</span><span class="sxs-lookup"><span data-stu-id="5ee50-270">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="5ee50-271">Per specificare il punto di inizio, selezionare una persona dall'elenco <strong>Inizia da</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-271">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="5ee50-272">Per specificare il punto finale, fare clic su <strong>Aggiungi condizione</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-272">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="5ee50-273">Immettere quindi una condizione per determinare il punto della gerarchia in cui verrà arrestato il recupero dei nomi da parte del sistema.</span><span class="sxs-lookup"><span data-stu-id="5ee50-273">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="5ee50-274">Nella scheda <strong>Opzioni gerarchia</strong> specificare a quali utenti nell'intervallo il documento deve essere riassegnato:</span><span class="sxs-lookup"><span data-stu-id="5ee50-274">On the <strong>Hierarchy options</strong> tab, specify which users in the range the document should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="5ee50-275"><strong>Assegna a tutti gli utenti recuperati</strong> - Il documento viene riassegnato a tutti gli utenti nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="5ee50-275"><strong>Assign to all users retrieved</strong> – The document is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="5ee50-276"><strong>Assegna solo all'ultimo utente recuperato</strong> - Il documento viene riassegnato solo all'ultimo utente dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="5ee50-276"><strong>Assign only to last user retrieved</strong> – The document is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="5ee50-277"><strong>Escludi utenti con la seguente condizione:</strong> - Il documento non viene riassegnato ad alcun utente nell'intervallo che soddisfa una specifica condizione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-277"><strong>Exclude users with the following condition</strong> – The document isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="5ee50-278">Fare clic su <strong>Aggiungi condizione</strong> per specificare la condizione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-278">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5ee50-279">Utente del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="5ee50-279">Workflow user</span></span></td>
    <td><span data-ttu-id="5ee50-280">Utenti nel flusso di lavoro corrente</span><span class="sxs-lookup"><span data-stu-id="5ee50-280">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="5ee50-281">Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5ee50-281">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5ee50-282">Utente</span><span class="sxs-lookup"><span data-stu-id="5ee50-282">User</span></span></td>
    <td><span data-ttu-id="5ee50-283">Utenti specifici</span><span class="sxs-lookup"><span data-stu-id="5ee50-283">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5ee50-284">Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-284">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="5ee50-285">Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5ee50-285">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="5ee50-286">Selezionare gli utenti a cui riassegnare il documento, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ee50-286">Select the users to escalate the document to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="5ee50-287">Nella scheda **Limite di tempo**, nel campo **Durata** specificare il periodo di tempo entro cui un utente deve eseguire un'azione o inviare una risposta per i documenti.</span><span class="sxs-lookup"><span data-stu-id="5ee50-287">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents.</span></span> <span data-ttu-id="5ee50-288">Consente di selezionare una delle opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5ee50-288">Select one of the following options:</span></span>

    - <span data-ttu-id="5ee50-289">**Ore**: immettere il numero di ore entro cui l'utente deve inviare una risposta.</span><span class="sxs-lookup"><span data-stu-id="5ee50-289">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="5ee50-290">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-290">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="5ee50-291">**Giorni**: immettere il numero di giorni entro cui l'utente deve inviare una risposta.</span><span class="sxs-lookup"><span data-stu-id="5ee50-291">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="5ee50-292">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-292">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="5ee50-293">**Settimane**: immettere il numero di settimane entro cui l'utente deve inviare una risposta.</span><span class="sxs-lookup"><span data-stu-id="5ee50-293">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="5ee50-294">**Mesi**: selezionare il giorno e la settimana entro cui l'utente deve inviare una risposta.</span><span class="sxs-lookup"><span data-stu-id="5ee50-294">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="5ee50-295">È ad esempio possibile scegliere che l'utente invii una risposta entro il venerdì della terza settimana del mese.</span><span class="sxs-lookup"><span data-stu-id="5ee50-295">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="5ee50-296">**Anni**: selezionare il giorno, la settimana e il mese entro cui l'utente deve inviare una risposta.</span><span class="sxs-lookup"><span data-stu-id="5ee50-296">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="5ee50-297">È ad esempio possibile scegliere che l'utente invii una risposta entro il venerdì della terza settimana di dicembre.</span><span class="sxs-lookup"><span data-stu-id="5ee50-297">For example, you might want the user to respond by Friday of the third week of December.</span></span>

5. <span data-ttu-id="5ee50-298">Ripetere i passaggi da 3 a 4 per ogni utente che si desidera aggiungere al percorso di riassegnazione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-298">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="5ee50-299">È possibile modificare l'ordine degli utenti.</span><span class="sxs-lookup"><span data-stu-id="5ee50-299">You can change the order of the users.</span></span>
6. <span data-ttu-id="5ee50-300">Se gli utenti nel percorso di riassegnazione non inviano una risposta nel tempo prestabilito, verrà automaticamente eseguita un'azione sul documento dal sistema.</span><span class="sxs-lookup"><span data-stu-id="5ee50-300">If the users in the escalation path don't respond in the allotted time, the system automatically take action on the document.</span></span> <span data-ttu-id="5ee50-301">Per specificare l'azione presa dal sistema, selezionare la riga **Azione**, quindi nella scheda **Termina azione** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="5ee50-301">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>
