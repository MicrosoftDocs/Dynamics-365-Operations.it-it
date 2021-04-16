---
title: Configurare i processi di approvazione in un flusso di lavoro
description: Per configurare le proprietà del processo di approvazione, attenersi alla procedura indicata di seguito.
author: ChrisGarty
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5738c5993c129f9bb4932180916befaf6f6377a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751802"
---
# <a name="configure-approval-processes-in-a-workflow"></a><span data-ttu-id="b5a0b-103">Configurare i processi di approvazione in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b5a0b-103">Configure approval processes in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5a0b-104">Per configurare le proprietà del processo di approvazione, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-104">Use the following procedure to configure the properties of the approval process.</span></span>

<span data-ttu-id="b5a0b-105">Per configurare un processo di approvazione, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'elemento di approvazione e scegliere **Proprietà** per aprire il modulo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-105">To configure an approval process, in the workflow editor, right-click the approval element, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-the-approval-process"></a><span data-ttu-id="b5a0b-106">Assegnare un nome al processo di approvazione</span><span class="sxs-lookup"><span data-stu-id="b5a0b-106">Name the approval process</span></span>

<span data-ttu-id="b5a0b-107">Per immettere un nome per il processo di approvazione, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-107">Follow these steps to enter a name for the approval process.</span></span>

1. <span data-ttu-id="b5a0b-108">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-108">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="b5a0b-109">Nel campo **Nome** immettere un nome univoco per il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-109">In the **Name** field, enter a unique name for the approval process.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a><span data-ttu-id="b5a0b-110">Specificare se il sistema esegue automaticamente un'azione sul documento</span><span class="sxs-lookup"><span data-stu-id="b5a0b-110">Specify when the system automatically acts on the document</span></span>

<span data-ttu-id="b5a0b-111">È possibile configurare il sistema in modo che venga automaticamente eseguita un'azione sul documento, se vengono soddisfatte determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-111">You can configure the system to automatically act on the document if specific conditions are met.</span></span> <span data-ttu-id="b5a0b-112">Il sistema può ad esempio approvare le note spese con importi totali inferiori a USD 100.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-112">For example, the system can approve expense reports that have total amounts that are less than USD 100.</span></span> <span data-ttu-id="b5a0b-113">Per specificare se il sistema esegue automaticamente un'azione sul documento, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-113">Follow these steps to specify when the system acts on the document.</span></span>

1. <span data-ttu-id="b5a0b-114">Nel riquadro sinistro fare clic su **Azioni automatiche**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-114">In the left pane, click **Automatic actions**.</span></span>
2. <span data-ttu-id="b5a0b-115">Selezionare la casella di controllo **Attiva azioni automatiche**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-115">Select the **Enable automatic actions** check box.</span></span>
3. <span data-ttu-id="b5a0b-116">Fare clic su **Aggiungi condizione**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-116">Click **Add condition**.</span></span>
4. <span data-ttu-id="b5a0b-117">Immettere una condizione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-117">Enter a condition.</span></span>
5. <span data-ttu-id="b5a0b-118">Se necessario, immettere condizioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-118">Enter additional conditions, if necessary.</span></span>
6. <span data-ttu-id="b5a0b-119">Per verificare la correttezza della configurazione delle condizioni immesse, eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5a0b-119">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="b5a0b-120">Fare clic su **Test** per aprire il modulo **Test condizione flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-120">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="b5a0b-121">Selezionare un record nell'area **Convalida condizione** del modulo.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-121">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="b5a0b-122">Fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-122">Click **Test**.</span></span> <span data-ttu-id="b5a0b-123">Il sistema valuta il record per determinare se soddisfa le condizioni definite.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-123">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="b5a0b-124">Fare clic su **OK** o **Annulla** per tornare al modulo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-124">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>

7. <span data-ttu-id="b5a0b-125">Nell'elenco **Azione completamento automatico** selezionare l'azione che dovrà essere eseguita sul documento.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-125">In the **Auto complete action** list, select the action that the system should take on the document.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="b5a0b-126">Specificare quando verranno inviate le notifiche</span><span class="sxs-lookup"><span data-stu-id="b5a0b-126">Specify when notifications are sent</span></span>

<span data-ttu-id="b5a0b-127">È possibile inviare notifiche agli utenti se un documento è stato approvato, rifiutato, delegato o riassegnato oppure se è stata richiesta una modifica.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-127">You can send notifications to people when a document has been approved, rejected, delegated, or escalated, or when a change has been requested.</span></span> <span data-ttu-id="b5a0b-128">Per specificare quando e a chi verranno inviate le notifiche, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-128">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="b5a0b-129">Nel riquadro sinistro fare clic su **Notifiche**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-129">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="b5a0b-130">Selezionare la casella di controllo accanto agli eventi per cui inviare notifiche:</span><span class="sxs-lookup"><span data-stu-id="b5a0b-130">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="b5a0b-131">**Delega**: se un documento è stato assegnato a un altro utente per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-131">**Delegate** – When a document has been assigned to another user for approval.</span></span>
    - <span data-ttu-id="b5a0b-132">**Riassegna**: se l'utente assegnato non ha eseguito un'azione sul documento nel tempo prestabilito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-132">**Escalate** – When the assigned user has not acted on a document in the allotted time.</span></span>
    - <span data-ttu-id="b5a0b-133">**Approva**: se un documento è stato approvato.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-133">**Approve** – When a document has been approved.</span></span>
    - <span data-ttu-id="b5a0b-134">**Rifiuta**: se un documento è stato rifiutato.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-134">**Reject** – When a document has been rejected.</span></span>
    - <span data-ttu-id="b5a0b-135">**Richiedi modifica**: se l'utente assegnato ha richiesto una modifica a un documento inviato.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-135">**Request change** – When the assigned user has requested a change to a document that was submitted.</span></span>

3. <span data-ttu-id="b5a0b-136">Scegliere la riga per un evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-136">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="b5a0b-137">Fare clic sulla scheda **Testo notifiche**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-137">Click the **Notification text** tab.</span></span>
5. <span data-ttu-id="b5a0b-138">Nella casella di testo immettere il testo per la notifica.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-138">In the text box, enter the text for the notification.</span></span>
6. <span data-ttu-id="b5a0b-139">Per personalizzare il testo, è possibile inserire segnaposto che verranno sostituiti con i dati appropriati al momento della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-139">To personalize the text, you can insert placeholders, which are replaced with the appropriate data when they are displayed to users.</span></span> <span data-ttu-id="b5a0b-140">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5a0b-140">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="b5a0b-141">Fare clic sulla casella di testo nel punto in cui verrà visualizzato il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-141">Click in the text box at the location where the placeholder should appear.</span></span>
    2. <span data-ttu-id="b5a0b-142">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-142">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="b5a0b-143">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-143">In the list that is displayed, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="b5a0b-144">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-144">Click **Insert**.</span></span>

7. <span data-ttu-id="b5a0b-145">Per aggiungere traduzioni della notifica, fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-145">To add translations of the notification, click **Translations**.</span></span> <span data-ttu-id="b5a0b-146">Nel modulo visualizzato attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-146">In the form that is displayed, follow these steps:</span></span>

    1. <span data-ttu-id="b5a0b-147">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-147">Click **Add**.</span></span>
    2. <span data-ttu-id="b5a0b-148">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-148">In the list that is displayed, select the language in which you will enter the text.</span></span>
    3. <span data-ttu-id="b5a0b-149">Nella casella di testo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-149">In the **Translated text** text box, enter the text.</span></span>
    4. <span data-ttu-id="b5a0b-150">Per personalizzare il testo, inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-150">To personalize the text, insert placeholders.</span></span>
    5. <span data-ttu-id="b5a0b-151">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-151">Click **Close**.</span></span>

8. <span data-ttu-id="b5a0b-152">Fare clic sulla scheda **Destinatario**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-152">Click the **Recipient** tab.</span></span>
9. <span data-ttu-id="b5a0b-153">Specificare i destinatari delle notifiche.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-153">Specify who the notifications are sent to.</span></span> <span data-ttu-id="b5a0b-154">Selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-154">Select one of the options in the following table, and then follow the additional steps for the option before you go to step 10.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="b5a0b-155">Opzione</span><span class="sxs-lookup"><span data-stu-id="b5a0b-155">Option</span></span></th>
    <th><span data-ttu-id="b5a0b-156">Destinatari delle notifiche</span><span class="sxs-lookup"><span data-stu-id="b5a0b-156">Notification recipients</span></span></th>
    <th><span data-ttu-id="b5a0b-157">Passaggi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="b5a0b-157">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="b5a0b-158"><strong>Partecipante</strong></span><span class="sxs-lookup"><span data-stu-id="b5a0b-158"><strong>Participant</strong></span></span></td>
    <td><span data-ttu-id="b5a0b-159">Utenti assegnati a un ruolo o un gruppo specifico</span><span class="sxs-lookup"><span data-stu-id="b5a0b-159">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b5a0b-160">Dopo aver selezionato <strong>Partecipante</strong> fare clic sulla scheda <strong>Basato sui ruoli</strong>.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-160">After you select <strong>Participant</strong>, click the <strong>Role based</strong> tab.</span></span></li>
    <li><span data-ttu-id="b5a0b-161">Nell'elenco <strong>Tipo di partecipante</strong> selezionare il tipo di gruppo o ruolo a cui si desidera inviare notifiche.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-161">In the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="b5a0b-162">Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui inviare notifiche.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-162">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b5a0b-163"><strong>Utente del flusso di lavoro</strong></span><span class="sxs-lookup"><span data-stu-id="b5a0b-163"><strong>Workflow user</strong></span></span></td>
    <td><span data-ttu-id="b5a0b-164">Utenti che partecipano al flusso di lavoro corrente</span><span class="sxs-lookup"><span data-stu-id="b5a0b-164">Users who participate in the current workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b5a0b-165">Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, fare clic sulla scheda <strong>Utente del flusso di lavoro</strong>.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-165">After you select <strong>Workflow user</strong>, click the <strong>Workflow user</strong> tab.</span></span></li>
    <li><span data-ttu-id="b5a0b-166">Nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-166">In the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b5a0b-167"><strong>Utente</strong></span><span class="sxs-lookup"><span data-stu-id="b5a0b-167"><strong>User</strong></span></span></td>
    <td><span data-ttu-id="b5a0b-168">Utenti specifici</span><span class="sxs-lookup"><span data-stu-id="b5a0b-168">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b5a0b-169">Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-169">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="b5a0b-170">Selezionare gli utenti a cui inviare notifiche, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-170">Select the users to send notifications to, and then move these users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. <span data-ttu-id="b5a0b-171">Ripetere i passaggi dal 3 al 9 per ciascun evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-171">Repeat steps 3 through 9 for each event that you selected in step 2.</span></span>

## <a name="specify-a-final-approver"></a><span data-ttu-id="b5a0b-172">Specificare un approvatore finale</span><span class="sxs-lookup"><span data-stu-id="b5a0b-172">Specify a final approver</span></span>

<span data-ttu-id="b5a0b-173">È possibile designare un approvatore finale per gli scenari in cui l'approvatore è la persona che ha inviato il documento per l'approvazione e si utilizza "Non consentire l'approvazione da parte dell'autore dell'invio".</span><span class="sxs-lookup"><span data-stu-id="b5a0b-173">You can designate a final approver for scenarios where the approver is the person who submitted the document for approval and the "disallow approval by submitter" is being used.</span></span> <span data-ttu-id="b5a0b-174">Per specificare un approvatore finale, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-174">Follow these steps to specify a final approver.</span></span>

1. <span data-ttu-id="b5a0b-175">Nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'elemento di approvazione e selezionare **Proprietà** per aprire il modulo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-175">In the workflow editor, right-click the approval element, and then select **Properties** to open the **Properties** form.</span></span>
2. <span data-ttu-id="b5a0b-176">Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-176">In the left pane, click **Advanced settings**.</span></span>
3. <span data-ttu-id="b5a0b-177">Selezionare la casella di controllo **Usa approvatore finale**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-177">Select the **Use final approver** check box.</span></span>
4. <span data-ttu-id="b5a0b-178">Selezionare nell'elenco un utente che si desidera impostare come approvatore finale.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-178">In the list, select a user to be the final approver.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="b5a0b-179">Impostare un limite di tempo</span><span class="sxs-lookup"><span data-stu-id="b5a0b-179">Set a time limit</span></span>

<span data-ttu-id="b5a0b-180">Se è necessario completare il processo di approvazione in un periodo di tempo specifico, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-180">Follow these steps if the approval process must be completed in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="b5a0b-181">Le opzioni selezionate in questi passaggi prevalgono su quelle selezionate nelle aree **Assegnazione** e **Riassegnazione** di ogni passaggio di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-181">The options that you select in these steps override the options that you selected in the **Assignment** and **Escalation** areas of each approval step.</span></span>

1. <span data-ttu-id="b5a0b-182">Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-182">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="b5a0b-183">Selezionare la casella di controllo **Imposta un limite di tempo** per **l'elemento del flusso di lavorol'elemento del flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-183">Select the **Set a time limit for the workflow** **element** check box.</span></span>
3. <span data-ttu-id="b5a0b-184">Nel campo **Durata** specificare il momento in cui completare il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-184">In the **Duration** field, specify when the approval process must be completed.</span></span> <span data-ttu-id="b5a0b-185">Consente di selezionare una delle opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-185">Select one of the following options:</span></span>

    - <span data-ttu-id="b5a0b-186">**Ore**: immettere il numero di ore entro le quali deve essere completato il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-186">**Hours** – Enter the number of hours in which the approval process must be completed.</span></span> <span data-ttu-id="b5a0b-187">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-187">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="b5a0b-188">**Giorni**: immettere il numero di giorni entro i quali deve essere completato il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-188">**Days** – Enter the number of days in which the approval process must be completed.</span></span> <span data-ttu-id="b5a0b-189">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-189">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="b5a0b-190">**Settimane**: immettere il numero di settimane entro le quali deve essere completato il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-190">**Weeks** – Enter the number of weeks in which the approval process must be completed.</span></span>
    - <span data-ttu-id="b5a0b-191">**Mesi**: selezionare il giorno e la settimana entro i quali deve essere completato il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-191">**Months** – Select the day and week by which the approval process must be completed.</span></span> <span data-ttu-id="b5a0b-192">È ad esempio possibile scegliere di completare il processo di approvazione entro il venerdì della terza settimana del mese.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-192">For example, you may want the approval process to be completed by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="b5a0b-193">**Anni**: selezionare il giorno, la settimana e il mese entro i quali deve essere completato il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-193">**Years** – Select the day, week, and month by which the approval process must be completed.</span></span> <span data-ttu-id="b5a0b-194">È ad esempio possibile scegliere di completare il processo di approvazione entro il venerdì della terza settimana di dicembre.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-194">For example, you may want the approval process to be completed by Friday of the third week of December.</span></span>

4. <span data-ttu-id="b5a0b-195">Se viene superato il limite di tempo, l'azione verrà eseguita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-195">If the time limit is exceeded, the system acts on the document.</span></span> <span data-ttu-id="b5a0b-196">Nell'elenco **Azione** selezionare l'azione che dovrà essere eseguita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-196">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="b5a0b-197">Specificare le azioni disponibili per l'utente</span><span class="sxs-lookup"><span data-stu-id="b5a0b-197">Specify which actions are available to the user</span></span>

<span data-ttu-id="b5a0b-198">Quando un documento viene assegnato per l'approvazione a un utente, quest'ultimo deve eseguire un'azione su di esso.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-198">When a document is assigned to a user for approval, the user must act on the document.</span></span> <span data-ttu-id="b5a0b-199">Per specificare le azioni che l'utente può eseguire sul documento inviato, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-199">Follows these steps to specify which actions the user can take on the document that was submitted.</span></span>

1. <span data-ttu-id="b5a0b-200">Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-200">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="b5a0b-201">Selezionare la casella di controllo **Approva** se l'utente può approvare il documento.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-201">Select the **Approve** check box if the user can approve the document.</span></span>
3. <span data-ttu-id="b5a0b-202">Selezionare la casella di controllo **Rifiuta** se l'utente può rifiutare il documento.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-202">Select the **Reject** check box the user can reject the document.</span></span>
4. <span data-ttu-id="b5a0b-203">Selezionare la casella di controllo **Richiedi modifica** se l'utente può richiedere modifiche al documento.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-203">Select the **Request change** check box the user can request changes to the document.</span></span>
5. <span data-ttu-id="b5a0b-204">Selezionare la casella di controllo **Delega** se l'utente può assegnare il documento a un altro utente per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-204">Select the **Delegate** check box if the user can assign the document to another user for approval.</span></span>

> [!NOTE]
> <span data-ttu-id="b5a0b-205">La casella di controllo **Attiva azioni dall'elenco di lavoro in Enterprise Portal** è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-205">The **Enable actions from the work list in Enterprise Portal** check box has been deprecated.</span></span>

## <a name="configure-the-approval-steps"></a><span data-ttu-id="b5a0b-206"> Configurare i passaggi di approvazione</span><span class="sxs-lookup"><span data-stu-id="b5a0b-206">Configure the approval steps</span></span>

<span data-ttu-id="b5a0b-207">Un processo di approvazione è costituito da passaggi di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-207">An approval process consists of approval steps.</span></span> <span data-ttu-id="b5a0b-208">Per aggiungere passaggi al processo e configurarli, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-208">Complete the following procedure to add steps the approval process and configure the steps.</span></span>

1. <span data-ttu-id="b5a0b-209">Nell'editor flusso di lavoro fare doppio clic sul processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-209">In the workflow editor, double-click the approval process.</span></span> <span data-ttu-id="b5a0b-210">Verranno visualizzati i passaggi del processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-210">The workflow editor displays the steps of the approval process.</span></span>
2. <span data-ttu-id="b5a0b-211">Per aggiungere un passaggio di approvazione, trascinarlo dall'area **Elementi flusso di lavoro** nella canvas.</span><span class="sxs-lookup"><span data-stu-id="b5a0b-211">To add an approval step, drag the step from the **Workflow elements** area to the canvas.</span></span>
3. <span data-ttu-id="b5a0b-212">Per configurare un passaggio di approvazione, vedere [Configurare i passaggi di approvazione in un flusso di lavoro](configure-approval-step-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="b5a0b-212">To configure an approval step, see [Configure approval steps in a workflow](configure-approval-step-workflow.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]