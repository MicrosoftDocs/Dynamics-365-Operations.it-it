---
title: Configurare i processi di approvazione in un flusso di lavoro
description: "Per configurare le proprietà del processo di approvazione, attenersi alla procedura indicata di seguito."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 212e9c32c7bb22b0ee0450e04b4090c540df7b54
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="configure-approval-processes-in-a-workflow"></a><span data-ttu-id="78be0-103">Configurare i processi di approvazione in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="78be0-103">Configure approval processes in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78be0-104">Per configurare le proprietà del processo di approvazione, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="78be0-104">Use the following procedure to configure the properties of the approval process.</span></span>

<span data-ttu-id="78be0-105">Per configurare un processo di approvazione, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'elemento di approvazione e scegliere **Proprietà** per aprire il modulo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="78be0-105">To configure an approval process, in the workflow editor, right-click the approval element, and then click **Properties** to open the **Properties** form.</span></span>
<span data-ttu-id="78be0-106">Assegnare un nome al processo di approvazione</span><span class="sxs-lookup"><span data-stu-id="78be0-106">Name the approval process</span></span>
-------------------------

<span data-ttu-id="78be0-107">Per immettere un nome per il processo di approvazione, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="78be0-107">Follow these steps to enter a name for the approval process.</span></span>
1.  <span data-ttu-id="78be0-108">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="78be0-108">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="78be0-109">Nel campo **Nome** immettere un nome univoco per il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-109">In the **Name** field, enter a unique name for the approval process.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a><span data-ttu-id="78be0-110">Specificare se il sistema esegue automaticamente un'azione sul documento</span><span class="sxs-lookup"><span data-stu-id="78be0-110">Specify when the system automatically acts on the document</span></span>
<span data-ttu-id="78be0-111">È possibile configurare il sistema in modo che venga automaticamente eseguita un'azione sul documento, se vengono soddisfatte determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="78be0-111">You can configure the system to automatically act on the document if specific conditions are met.</span></span> <span data-ttu-id="78be0-112">Il sistema può ad esempio approvare le note spese con importi totali inferiori a USD 100.</span><span class="sxs-lookup"><span data-stu-id="78be0-112">For example, the system can approve expense reports that have total amounts that are less than USD 100.</span></span> <span data-ttu-id="78be0-113">Per specificare se il sistema esegue automaticamente un'azione sul documento, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="78be0-113">Follow these steps to specify when the system acts on the document.</span></span>
1.  <span data-ttu-id="78be0-114">Nel riquadro sinistro fare clic su **Azioni automatiche**.</span><span class="sxs-lookup"><span data-stu-id="78be0-114">In the left pane, click **Automatic actions**.</span></span>
2.  <span data-ttu-id="78be0-115">Selezionare la casella di controllo **Attiva azioni automatiche**.</span><span class="sxs-lookup"><span data-stu-id="78be0-115">Select the **Enable automatic actions** check box.</span></span>
3.  <span data-ttu-id="78be0-116">Fare clic su **Aggiungi condizione**.</span><span class="sxs-lookup"><span data-stu-id="78be0-116">Click **Add condition**.</span></span>
4.  <span data-ttu-id="78be0-117">Immettere una condizione.</span><span class="sxs-lookup"><span data-stu-id="78be0-117">Enter a condition.</span></span>
5.  <span data-ttu-id="78be0-118">Se necessario, immettere condizioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="78be0-118">Enter additional conditions, if necessary.</span></span>
6.  <span data-ttu-id="78be0-119">Per verificare la correttezza della configurazione delle condizioni immesse, eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="78be0-119">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>
    1.  <span data-ttu-id="78be0-120">Fare clic su **Test** per aprire il modulo **Test condizione flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="78be0-120">Click **Test** to open the **Test workflow condition** form.</span></span>
    2.  <span data-ttu-id="78be0-121">Selezionare un record nell'area **Convalida condizione** del modulo.</span><span class="sxs-lookup"><span data-stu-id="78be0-121">Select a record in the **Validate condition** area of the form.</span></span>
    3.  <span data-ttu-id="78be0-122">Fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="78be0-122">Click **Test**.</span></span> <span data-ttu-id="78be0-123">Il sistema valuta il record per determinare se soddisfa le condizioni definite.</span><span class="sxs-lookup"><span data-stu-id="78be0-123">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4.  <span data-ttu-id="78be0-124">Fare clic su **OK** o **Annulla** per tornare al modulo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="78be0-124">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>

7.  <span data-ttu-id="78be0-125">Nell'elenco **Azione completamento automatico** selezionare l'azione che dovrà essere eseguita sul documento.</span><span class="sxs-lookup"><span data-stu-id="78be0-125">In the **Auto complete action** list, select the action that the system should take on the document.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="78be0-126">Specificare quando verranno inviate le notifiche</span><span class="sxs-lookup"><span data-stu-id="78be0-126">Specify when notifications are sent</span></span>
<span data-ttu-id="78be0-127">È possibile inviare notifiche agli utenti se un documento è stato approvato, rifiutato, delegato o riassegnato oppure se è stata richiesta una modifica.</span><span class="sxs-lookup"><span data-stu-id="78be0-127">You can send notifications to people when a document has been approved, rejected, delegated, or escalated, or when a change has been requested.</span></span> <span data-ttu-id="78be0-128">Per specificare quando e a chi verranno inviate le notifiche, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="78be0-128">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>
1.  <span data-ttu-id="78be0-129">Nel riquadro sinistro fare clic su **Notifiche**.</span><span class="sxs-lookup"><span data-stu-id="78be0-129">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="78be0-130">Selezionare la casella di controllo accanto agli eventi per cui inviare notifiche:</span><span class="sxs-lookup"><span data-stu-id="78be0-130">Select the check box next to the events to send notifications for:</span></span>
    -   <span data-ttu-id="78be0-131">**Delega**: se un documento è stato assegnato a un altro utente per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-131">**Delegate** – When a document has been assigned to another user for approval.</span></span>
    -   <span data-ttu-id="78be0-132">**Riassegna**: se l'utente assegnato non ha eseguito un'azione sul documento nel tempo prestabilito.</span><span class="sxs-lookup"><span data-stu-id="78be0-132">**Escalate** – When the assigned user has not acted on a document in the allotted time.</span></span>
    -   <span data-ttu-id="78be0-133">**Approva**: se un documento è stato approvato.</span><span class="sxs-lookup"><span data-stu-id="78be0-133">**Approve** – When a document has been approved.</span></span>
    -   <span data-ttu-id="78be0-134">**Rifiuta**: se un documento è stato rifiutato.</span><span class="sxs-lookup"><span data-stu-id="78be0-134">**Reject** – When a document has been rejected.</span></span>
    -   <span data-ttu-id="78be0-135">**Richiedi modifica**: se l'utente assegnato ha richiesto una modifica a un documento inviato.</span><span class="sxs-lookup"><span data-stu-id="78be0-135">**Request change** – When the assigned user has requested a change to a document that was submitted.</span></span>

3.  <span data-ttu-id="78be0-136">Scegliere la riga per un evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="78be0-136">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="78be0-137">Fare clic sulla scheda **Testo notifiche**.</span><span class="sxs-lookup"><span data-stu-id="78be0-137">Click the **Notification text** tab.</span></span>
5.  <span data-ttu-id="78be0-138">Nella casella di testo immettere il testo per la notifica.</span><span class="sxs-lookup"><span data-stu-id="78be0-138">In the text box, enter the text for the notification.</span></span>
6.  <span data-ttu-id="78be0-139">Per personalizzare il testo, è possibile inserire segnaposto che verranno sostituiti con i dati appropriati al momento della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-139">To personalize the text, you can insert placeholders, which are replaced with the appropriate data when they are displayed to users.</span></span> <span data-ttu-id="78be0-140">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="78be0-140">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="78be0-141">Fare clic sulla casella di testo nel punto in cui verrà visualizzato il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="78be0-141">Click in the text box at the location where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="78be0-142">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="78be0-142">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="78be0-143">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="78be0-143">In the list that is displayed, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="78be0-144">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="78be0-144">Click **Insert**.</span></span>

7.  <span data-ttu-id="78be0-145">Per aggiungere traduzioni della notifica, fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="78be0-145">To add translations of the notification, click **Translations**.</span></span> <span data-ttu-id="78be0-146">Nel modulo visualizzato attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="78be0-146">In the form that is displayed, follow these steps:</span></span>
    1.  <span data-ttu-id="78be0-147">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="78be0-147">Click **Add**.</span></span>
    2.  <span data-ttu-id="78be0-148">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="78be0-148">In the list that is displayed, select the language in which you will enter the text.</span></span>
    3.  <span data-ttu-id="78be0-149">Nella casella di testo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="78be0-149">In the **Translated text** text box, enter the text.</span></span>
    4.  <span data-ttu-id="78be0-150">Per personalizzare il testo, inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="78be0-150">To personalize the text, insert placeholders.</span></span>
    5.  <span data-ttu-id="78be0-151">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="78be0-151">Click **Close**.</span></span>

8.  <span data-ttu-id="78be0-152">Fare clic sulla scheda **Destinatario**.</span><span class="sxs-lookup"><span data-stu-id="78be0-152">Click the **Recipient** tab.</span></span>
9.  <span data-ttu-id="78be0-153">Specificare i destinatari delle notifiche.</span><span class="sxs-lookup"><span data-stu-id="78be0-153">Specify who the notifications are sent to.</span></span> <span data-ttu-id="78be0-154">Selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="78be0-154">Select one of the options in the following table, and then follow the additional steps for the option before you go to step 10.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="78be0-155">Opzione</span><span class="sxs-lookup"><span data-stu-id="78be0-155">Option</span></span></th>
    <th><span data-ttu-id="78be0-156">Destinatari delle notifiche</span><span class="sxs-lookup"><span data-stu-id="78be0-156">Notification recipients</span></span></th>
    <th><span data-ttu-id="78be0-157">Passaggi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="78be0-157">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="78be0-158"><strong>Partecipante</strong></span><span class="sxs-lookup"><span data-stu-id="78be0-158"><strong>Participant</strong></span></span></td>
    <td><span data-ttu-id="78be0-159">Utenti assegnati a un ruolo o un gruppo specifico</span><span class="sxs-lookup"><span data-stu-id="78be0-159">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="78be0-160">Dopo aver selezionato <strong>Partecipante</strong> fare clic sulla scheda <strong>Basato sui ruoli</strong>.</span><span class="sxs-lookup"><span data-stu-id="78be0-160">After you select <strong>Participant</strong>, click the <strong>Role based</strong> tab.</span></span></li>
    <li><span data-ttu-id="78be0-161">Nell'elenco <strong>Tipo di partecipante</strong> selezionare il tipo di gruppo o ruolo a cui si desidera inviare notifiche.</span><span class="sxs-lookup"><span data-stu-id="78be0-161">In the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="78be0-162">Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui inviare notifiche.</span><span class="sxs-lookup"><span data-stu-id="78be0-162">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="78be0-163"><strong>Utente del flusso di lavoro</strong></span><span class="sxs-lookup"><span data-stu-id="78be0-163"><strong>Workflow user</strong></span></span></td>
    <td><span data-ttu-id="78be0-164">Utenti che partecipano al flusso di lavoro corrente</span><span class="sxs-lookup"><span data-stu-id="78be0-164">Users who participate in the current workflow</span></span></td>
    <td><ol>
    <li><span data-ttu-id="78be0-165">Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, fare clic sulla scheda <strong>Utente del flusso di lavoro</strong>.</span><span class="sxs-lookup"><span data-stu-id="78be0-165">After you select <strong>Workflow user</strong>, click the <strong>Workflow user</strong> tab.</span></span></li>
    <li><span data-ttu-id="78be0-166">Nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="78be0-166">In the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="78be0-167"><strong>Utente</strong></span><span class="sxs-lookup"><span data-stu-id="78be0-167"><strong>User</strong></span></span></td>
    <td><span data-ttu-id="78be0-168">Utenti specifici di Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="78be0-168">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="78be0-169">Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</span><span class="sxs-lookup"><span data-stu-id="78be0-169">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="78be0-170">Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti di Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="78be0-170">The <strong>Available users</strong>: list includes all Microsoft Dynamics 365 for Finance and Operations users.</span></span> <span data-ttu-id="78be0-171">Selezionare gli utenti a cui inviare notifiche, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</span><span class="sxs-lookup"><span data-stu-id="78be0-171">Select the users to send notifications to, and then move these users to the <strong>Selected users</strong>: list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

10. <span data-ttu-id="78be0-172">Ripetere i passaggi dal 3 al 9 per ciascun evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="78be0-172">Repeat steps 3 through 9 for each event that you selected in step 2.</span></span>

## <a name="specify-a-final-approver"></a><span data-ttu-id="78be0-173">Specificare un approvatore finale</span><span class="sxs-lookup"><span data-stu-id="78be0-173">Specify a final approver</span></span>
<span data-ttu-id="78be0-174">È consigliabile designare un approvatore finale per gli scenari in cui l'approvatore è la persona che ha inviato il documento per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-174">You may want to designate a final approver for scenarios where the approver is the person who submitted the document for approval.</span></span> <span data-ttu-id="78be0-175">Per specificare un approvatore finale, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="78be0-175">Follow these steps to specify a final approver.</span></span>
1.  <span data-ttu-id="78be0-176">Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="78be0-176">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="78be0-177">Selezionare la casella di controllo **Usa approvatore finale**.</span><span class="sxs-lookup"><span data-stu-id="78be0-177">Select the **Use final approver** check box.</span></span>
3.  <span data-ttu-id="78be0-178">Selezionare nell'elenco l'utente che si desidera impostare come approvatore finale.</span><span class="sxs-lookup"><span data-stu-id="78be0-178">In the list, select the user to be the final approver.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="78be0-179">Impostare un limite di tempo</span><span class="sxs-lookup"><span data-stu-id="78be0-179">Set a time limit</span></span>
<span data-ttu-id="78be0-180">Se è necessario completare il processo di approvazione in un periodo di tempo specifico, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="78be0-180">Follow these steps if the approval process must be completed in a specific time.</span></span>

| <span data-ttu-id="78be0-181">**Nota**</span><span class="sxs-lookup"><span data-stu-id="78be0-181">**Note**</span></span>                                                                                                                                                |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="78be0-182">Le opzioni selezionate in questi passaggi prevalgono su quelle selezionate nelle aree **Assegnazione** e **Riassegnazione** di ogni passaggio di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-182">The options that you select in these steps override the options that you selected in the **Assignment** and **Escalation** areas of each approval step.</span></span> |

1.  <span data-ttu-id="78be0-183">Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="78be0-183">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="78be0-184">Selezionare la casella di controllo **Imposta un limite di tempo** per **l'elemento del flusso di lavorol'elemento del flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="78be0-184">Select the **Set a time limit for the workflow** **element** check box.</span></span>
3.  <span data-ttu-id="78be0-185">Nel campo **Durata** specificare il momento in cui completare il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-185">In the **Duration** field, specify when the approval process must be completed.</span></span> <span data-ttu-id="78be0-186">Consente di selezionare una delle opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="78be0-186">Select one of the following options:</span></span>
    -   <span data-ttu-id="78be0-187">**Ore**: immettere il numero di ore entro le quali deve essere completato il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-187">**Hours** – Enter the number of hours in which the approval process must be completed.</span></span> <span data-ttu-id="78be0-188">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-188">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="78be0-189">**Giorni**: immettere il numero di giorni entro i quali deve essere completato il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-189">**Days** – Enter the number of days in which the approval process must be completed.</span></span> <span data-ttu-id="78be0-190">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-190">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="78be0-191">**Settimane**: immettere il numero di settimane entro le quali deve essere completato il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-191">**Weeks** – Enter the number of weeks in which the approval process must be completed.</span></span>
    -   <span data-ttu-id="78be0-192">**Mesi**: selezionare il giorno e la settimana entro i quali deve essere completato il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-192">**Months** – Select the day and week by which the approval process must be completed.</span></span> <span data-ttu-id="78be0-193">È ad esempio possibile scegliere di completare il processo di approvazione entro il venerdì della terza settimana del mese.</span><span class="sxs-lookup"><span data-stu-id="78be0-193">For example, you may want the approval process to be completed by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="78be0-194">**Anni**: selezionare il giorno, la settimana e il mese entro i quali deve essere completato il processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-194">**Years** – Select the day, week, and month by which the approval process must be completed.</span></span> <span data-ttu-id="78be0-195">È ad esempio possibile scegliere di completare il processo di approvazione entro il venerdì della terza settimana di dicembre.</span><span class="sxs-lookup"><span data-stu-id="78be0-195">For example, you may want the approval process to be completed by Friday of the third week of December.</span></span>

4.  <span data-ttu-id="78be0-196">Se viene superato il limite di tempo, l'azione verrà eseguita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="78be0-196">If the time limit is exceeded, the system acts on the document.</span></span> <span data-ttu-id="78be0-197">Nell'elenco **Azione** selezionare l'azione che dovrà essere eseguita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="78be0-197">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="78be0-198">Specificare le azioni disponibili per l'utente</span><span class="sxs-lookup"><span data-stu-id="78be0-198">Specify which actions are available to the user</span></span>
<span data-ttu-id="78be0-199">Quando un documento viene assegnato per l'approvazione a un utente, quest'ultimo deve eseguire un'azione su di esso.</span><span class="sxs-lookup"><span data-stu-id="78be0-199">When a document is assigned to a user for approval, the user must act on the document.</span></span> <span data-ttu-id="78be0-200">Per specificare le azioni che l'utente può eseguire sul documento inviato, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="78be0-200">Follows these steps to specify which actions the user can take on the document that was submitted.</span></span>
1.  <span data-ttu-id="78be0-201">Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="78be0-201">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="78be0-202">Selezionare la casella di controllo **Approva** se l'utente può approvare il documento.</span><span class="sxs-lookup"><span data-stu-id="78be0-202">Select the **Approve** check box if the user can approve the document.</span></span>
3.  <span data-ttu-id="78be0-203">Selezionare la casella di controllo **Rifiuta** se l'utente può rifiutare il documento.</span><span class="sxs-lookup"><span data-stu-id="78be0-203">Select the **Reject** check box the user can reject the document.</span></span>
4.  <span data-ttu-id="78be0-204">Selezionare la casella di controllo **Richiedi modifica** se l'utente può richiedere modifiche al documento.</span><span class="sxs-lookup"><span data-stu-id="78be0-204">Select the **Request change** check box the user can request changes to the document.</span></span>
5.  <span data-ttu-id="78be0-205">Selezionare la casella di controllo **Delega** se l'utente può assegnare il documento a un altro utente per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-205">Select the **Delegate** check box if the user can assign the document to another user for approval.</span></span>

<span data-ttu-id="78be0-206">**Nota**: la casella di controllo **Attiva azioni dall'elenco di lavoro in Enterprise Portal** è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="78be0-206">**Note**: The **Enable actions from the work list in Enterprise Portal** check box has been deprecated.</span></span>

## <a name="configure-the-approval-steps"></a><span data-ttu-id="78be0-207"> Configurare i passaggi di approvazione</span><span class="sxs-lookup"><span data-stu-id="78be0-207">Configure the approval steps</span></span>
<span data-ttu-id="78be0-208">Un processo di approvazione è costituito da passaggi di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-208">An approval process consists of approval steps.</span></span> <span data-ttu-id="78be0-209">Per aggiungere passaggi al processo e configurarli, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="78be0-209">Complete the following procedure to add steps the approval process and configure the steps.</span></span>
1.  <span data-ttu-id="78be0-210">Nell'editor flusso di lavoro fare doppio clic sul processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-210">In the workflow editor, double-click the approval process.</span></span> <span data-ttu-id="78be0-211">Verranno visualizzati i passaggi del processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="78be0-211">The workflow editor displays the steps of the approval process.</span></span>
2.  <span data-ttu-id="78be0-212">Per aggiungere un passaggio di approvazione, trascinarlo dall'area **Elementi flusso di lavoro** nella canvas.</span><span class="sxs-lookup"><span data-stu-id="78be0-212">To add an approval step, drag the step from the **Workflow elements** area to the canvas.</span></span>
3.  <span data-ttu-id="78be0-213">Per configurare un passaggio di approvazione, vedere [Configurare un passaggio di approvazione](configure-approval-step-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="78be0-213">To configure an approval step, see [Configure an approval step](configure-approval-step-workflow.md).</span></span>






