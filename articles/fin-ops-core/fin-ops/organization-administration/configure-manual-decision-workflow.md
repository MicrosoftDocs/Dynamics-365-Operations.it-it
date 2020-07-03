---
title: Configurare le decisioni manuali in un flusso di lavoro
description: In questo argomento viene descritto come configurare le proprietà per una decisione manuale.
author: sericks007
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130cb50369c13bc3478340023c94f169ee5250cf
ms.sourcegitcommit: a5009c8958037afbaa1dd4f1469255b187ced93a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "3455035"
---
# <a name="configure-manual-decisions-in-a-workflow"></a><span data-ttu-id="41e2a-103">Configurare le decisioni manuali in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="41e2a-103">Configure manual decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="41e2a-104">In questo argomento viene descritto come configurare le proprietà per una decisione manuale.</span><span class="sxs-lookup"><span data-stu-id="41e2a-104">This topic explains how to configure the properties of a manual decision.</span></span>

<span data-ttu-id="41e2a-105">Per configurare una decisione manuale, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sulla decisione e scegliere **Proprietà** per aprire la pagina **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-105">To configure a manual decision in the workflow editor, right-click the manual decision, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="41e2a-106">Per configurare le proprietà della decisione manuale, attenersi alle procedure indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="41e2a-106">Then use the following procedures to configure the properties of the manual decision.</span></span>

## <a name="name-the-decision"></a><span data-ttu-id="41e2a-107">Assegnare un nome alla decisione</span><span class="sxs-lookup"><span data-stu-id="41e2a-107">Name the decision</span></span>

<span data-ttu-id="41e2a-108">Per immettere un nome per la decisione manuale, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="41e2a-108">Follow these steps to enter a name for the manual decision.</span></span>

1. <span data-ttu-id="41e2a-109">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="41e2a-110">Nel campo **Nome** immettere un nome univoco per la decisione manuale.</span><span class="sxs-lookup"><span data-stu-id="41e2a-110">In the **Name** field, enter a unique name for the manual decision.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="41e2a-111">Immettere una riga di argomento e le istruzioni</span><span class="sxs-lookup"><span data-stu-id="41e2a-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="41e2a-112">La riga di argomento e le istruzioni sono necessarie agli utenti assegnati alla decisione manuale.</span><span class="sxs-lookup"><span data-stu-id="41e2a-112">You must provide a subject line and instructions to users who are assigned to the manual decision.</span></span> <span data-ttu-id="41e2a-113">Se ad esempio si configura una decisione per richieste di acquisto, l'utente assegnato alla decisione visualizzerà la riga di argomento e le istruzioni nella pagina **Richieste di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-113">For example, if you're configuring a decision for purchase requisitions, the user who is assigned to the decision sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="41e2a-114">La riga di argomento si trova nella barra dei messaggi della pagina.</span><span class="sxs-lookup"><span data-stu-id="41e2a-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="41e2a-115">L'utente può fare clic sull'icona nella barra per visualizzare le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="41e2a-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="41e2a-116">Per immettere una riga di argomento e le istruzioni, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="41e2a-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="41e2a-117">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="41e2a-118">Nella scheda **Istruzioni**, nel campo **Argomento elemento di lavoro** immettere la riga di argomento.</span><span class="sxs-lookup"><span data-stu-id="41e2a-118">On the **Instructions** tab, in the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="41e2a-119">Per personalizzare la riga di argomento, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="41e2a-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="41e2a-120">I segnaposto verranno sostituiti con i dati appropriati al momento della riga di argomento.</span><span class="sxs-lookup"><span data-stu-id="41e2a-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="41e2a-121">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e2a-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="41e2a-122">Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="41e2a-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="41e2a-123">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="41e2a-124">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="41e2a-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="41e2a-125">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-125">Click **Insert**.</span></span>

4. <span data-ttu-id="41e2a-126">Per aggiungere traduzioni della riga di argomento, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e2a-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="41e2a-127">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="41e2a-128">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="41e2a-129">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="41e2a-130">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="41e2a-131">Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="41e2a-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="41e2a-132">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-132">Click **Close**.</span></span>

5. <span data-ttu-id="41e2a-133">Nel campo **Istruzioni elemento di lavoro** immettere le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="41e2a-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="41e2a-134">Per personalizzare le istruzioni, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="41e2a-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="41e2a-135">I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="41e2a-136">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e2a-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="41e2a-137">Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="41e2a-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="41e2a-138">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="41e2a-139">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="41e2a-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="41e2a-140">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-140">Click **Insert**.</span></span>

7. <span data-ttu-id="41e2a-141">Per aggiungere traduzioni delle istruzioni, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e2a-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="41e2a-142">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="41e2a-143">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="41e2a-144">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="41e2a-145">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="41e2a-146">Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="41e2a-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="41e2a-147">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-147">Click **Close**.</span></span>

## <a name="specify-the-possible-outcomes-of-a-decision"></a><span data-ttu-id="41e2a-148">Specificare i possibili risultati di una decisione</span><span class="sxs-lookup"><span data-stu-id="41e2a-148">Specify the possible outcomes of a decision</span></span>

<span data-ttu-id="41e2a-149">Se un documento viene assegnato a un decisore, a quest'ultimo viene in genere rivolta una domanda.</span><span class="sxs-lookup"><span data-stu-id="41e2a-149">Typically, when a document is assigned to a decision maker, the decision maker is asked a question.</span></span> <span data-ttu-id="41e2a-150">La risposta tipica a questa domanda è **Sì** o **No** oppure **Vero** o **Falso**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-150">The answer to this question is usually **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="41e2a-151">Per specificare i possibili risultati della decisione manuale, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="41e2a-151">Follow these steps to specify the possible outcomes of the manual decision.</span></span>

1. <span data-ttu-id="41e2a-152">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-152">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="41e2a-153">Nella scheda **Risultati**, nel campo **Risultato 1** immettere il nome del risultato o l'opzione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-153">On the **Outcomes** tab, in the **Outcome 1** field, enter the name of the outcome, or the option.</span></span>
3. <span data-ttu-id="41e2a-154">Per aggiungere traduzioni del risultato, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e2a-154">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="41e2a-155">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-155">Click **Translations**.</span></span>
    2. <span data-ttu-id="41e2a-156">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-156">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="41e2a-157">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-157">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="41e2a-158">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-158">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="41e2a-159">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-159">Click **Close**.</span></span>

4. <span data-ttu-id="41e2a-160">Nel campo **Risultato 2** immettere il nome del risultato oppure l'opzione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-160">In the **Outcome 2** field, enter the name of the outcome, or the option.</span></span>
5. <span data-ttu-id="41e2a-161">Per aggiungere traduzioni del risultato, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e2a-161">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="41e2a-162">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-162">Click **Translations**.</span></span>
    2. <span data-ttu-id="41e2a-163">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-163">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="41e2a-164">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-164">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="41e2a-165">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-165">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="41e2a-166">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-166">Click **Close**.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="41e2a-167">Specificare quando verranno inviate le notifiche</span><span class="sxs-lookup"><span data-stu-id="41e2a-167">Specify when notifications are sent</span></span>

<span data-ttu-id="41e2a-168">È possibile inviare notifiche agli utenti quando è stata presa, delegata o riassegnata una decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-168">You can send notifications to people when a decision has been made, delegated, or escalated.</span></span> <span data-ttu-id="41e2a-169">Per specificare quando e a chi verranno inviate le notifiche, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="41e2a-169">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="41e2a-170">Nel riquadro sinistro fare clic su **Notifiche**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-170">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="41e2a-171">Selezionare la casella di controllo accanto agli eventi per cui inviare notifiche:</span><span class="sxs-lookup"><span data-stu-id="41e2a-171">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="41e2a-172">**\[Prima scelta\]** – L'utente assegnato ha selezionato **\[Prima scelta\]**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-172">**\[Choice 1\]** – The assigned user has selected **\[Choice 1\]**.</span></span>
    - <span data-ttu-id="41e2a-173">**\[Seconda scelta\]** – L'utente assegnato ha selezionato **\[Seconda scelta\]**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-173">**\[Choice 2\]** – The assigned user has selected **\[Choice 2\]**.</span></span>
    - <span data-ttu-id="41e2a-174">**Delega**: se l'utente assegnato ha delegato la decisione a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="41e2a-174">**Delegate** – The assigned user has assigned the decision to another user.</span></span>
    - <span data-ttu-id="41e2a-175">**Riassegna**: se l'utente assegnato non ha preso la decisione nel tempo prestabilito.</span><span class="sxs-lookup"><span data-stu-id="41e2a-175">**Escalate** – The assigned user hasn't made the decision in the allotted time.</span></span>

3. <span data-ttu-id="41e2a-176">Scegliere la riga per un evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="41e2a-176">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="41e2a-177">Nella scheda **Testo notifiche** immettere il testo della notifica nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-177">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="41e2a-178">Per personalizzare la notifica, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="41e2a-178">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="41e2a-179">I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione della notifica.</span><span class="sxs-lookup"><span data-stu-id="41e2a-179">Placeholders are replaced with appropriate data when the notification is show to users.</span></span> <span data-ttu-id="41e2a-180">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e2a-180">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="41e2a-181">Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="41e2a-181">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="41e2a-182">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-182">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="41e2a-183">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="41e2a-183">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="41e2a-184">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-184">Click **Insert**.</span></span>

6. <span data-ttu-id="41e2a-185">Per aggiungere traduzioni della notifica, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e2a-185">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="41e2a-186">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-186">Click **Translations**.</span></span>
    2. <span data-ttu-id="41e2a-187">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-187">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="41e2a-188">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-188">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="41e2a-189">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-189">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="41e2a-190">Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="41e2a-190">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="41e2a-191">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-191">Click **Close**.</span></span>

7. <span data-ttu-id="41e2a-192">Nella scheda **Destinatario** specificare il destinatario cui inviare le notifiche.</span><span class="sxs-lookup"><span data-stu-id="41e2a-192">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="41e2a-193">Selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 8.</span><span class="sxs-lookup"><span data-stu-id="41e2a-193">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="41e2a-194">Opzione</span><span class="sxs-lookup"><span data-stu-id="41e2a-194">Option</span></span></th>
    <th><span data-ttu-id="41e2a-195">Destinatari delle notifiche</span><span class="sxs-lookup"><span data-stu-id="41e2a-195">Notification recipients</span></span></th>
    <th><span data-ttu-id="41e2a-196">Passaggi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="41e2a-196">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="41e2a-197">Partecipante</span><span class="sxs-lookup"><span data-stu-id="41e2a-197">Participant</span></span></td>
    <td><span data-ttu-id="41e2a-198">Utenti assegnati a un ruolo o un gruppo specifico</span><span class="sxs-lookup"><span data-stu-id="41e2a-198">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="41e2a-199">Dopo aver selezionato <strong>Partecipante</strong>, nella scheda <strong>Basato sui ruoli</strong> selezionare il tipo di gruppo o il ruolo a cui inviare le notifiche nell'elenco <strong>Tipo di partecipante</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-199">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="41e2a-200">Nell'elenco <strong>Partecipante</strong> selezionare il gruppo a cui inviare notifiche.</span><span class="sxs-lookup"><span data-stu-id="41e2a-200">In the <strong>Participant</strong> list, select the group or to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="41e2a-201">Utente del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="41e2a-201">Workflow user</span></span></td>
    <td><span data-ttu-id="41e2a-202">Utenti nel flusso di lavoro corrente</span><span class="sxs-lookup"><span data-stu-id="41e2a-202">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="41e2a-203">Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="41e2a-203">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="41e2a-204">Utente</span><span class="sxs-lookup"><span data-stu-id="41e2a-204">User</span></span></td>
    <td><span data-ttu-id="41e2a-205">Utenti specifici</span><span class="sxs-lookup"><span data-stu-id="41e2a-205">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="41e2a-206">Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-206">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="41e2a-207">Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="41e2a-207">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="41e2a-208">Selezionare gli utenti a cui inviare notifiche, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-208">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="41e2a-209">Ripetere i passaggi dal 3 al 7 per ciascun evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="41e2a-209">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="assign-a-decision"></a><span data-ttu-id="41e2a-210">Assegnare una decisione</span><span class="sxs-lookup"><span data-stu-id="41e2a-210">Assign a decision</span></span>

<span data-ttu-id="41e2a-211">Per specificare gli utenti a cui assegnare una decisione manuale, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="41e2a-211">Follow these steps to specify who a manual decision should be assigned to.</span></span>

1. <span data-ttu-id="41e2a-212">Nel riquadro sinistro, fare clic sull'icona **Assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-212">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="41e2a-213">Nella scheda **Tipo di assegnazione** selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="41e2a-213">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="41e2a-214">Opzione</span><span class="sxs-lookup"><span data-stu-id="41e2a-214">Option</span></span></th>
    <th><span data-ttu-id="41e2a-215">Utenti a cui viene assegnata la decisione</span><span class="sxs-lookup"><span data-stu-id="41e2a-215">Users that the decision is assigned to</span></span></th>
    <th><span data-ttu-id="41e2a-216">Passaggi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="41e2a-216">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="41e2a-217">Partecipante</span><span class="sxs-lookup"><span data-stu-id="41e2a-217">Participant</span></span></td>
    <td><span data-ttu-id="41e2a-218">Utenti assegnati a un ruolo o un gruppo specifico</span><span class="sxs-lookup"><span data-stu-id="41e2a-218">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="41e2a-219">Dopo aver selezionato <strong>Partecipante</strong>, nella scheda <strong>Basato sui ruoli</strong> selezionare il tipo di gruppo o il ruolo a cui assegnare la decisione nell'elenco <strong>Tipo di partecipante</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-219">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the decision to.</span></span></li>
    <li><span data-ttu-id="41e2a-220">Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui assegnare la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-220">In the <strong>Participant</strong> list, select the group or role to assign the decision to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="41e2a-221">Gerarchia</span><span class="sxs-lookup"><span data-stu-id="41e2a-221">Hierarchy</span></span></td>
    <td><span data-ttu-id="41e2a-222">Utenti in una specifica gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="41e2a-222">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="41e2a-223">Dopo aver selezionato <strong>Gerarchia</strong>, nella scheda <strong>Selezione gerarchia</strong> selezionare il tipo di gerarchia cui assegnare la decisione nell'elenco <strong>Tipo di gerarchia</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-223">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the decision to.</span></span></li>
    <li><span data-ttu-id="41e2a-224">Il sistema dovrà recuperare un intervallo di nomi utente dalla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="41e2a-224">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="41e2a-225">Questi nomi rappresentano gli utenti a cui può essere assegnata la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-225">These names represent users that the decision can be assigned to.</span></span> <span data-ttu-id="41e2a-226">Attenersi alla procedura indicata di seguito per specificare il punto di inizio e il punto finale dell'intervallo di nomi utente recuperati dal sistema:</span><span class="sxs-lookup"><span data-stu-id="41e2a-226">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="41e2a-227">Per specificare il punto di inizio, selezionare una persona dall'elenco <strong>Inizia da</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-227">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="41e2a-228">Per specificare il punto finale, fare clic su <strong>Aggiungi condizione</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-228">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="41e2a-229">Immettere quindi una condizione per determinare il punto della gerarchia in cui verrà arrestato il recupero dei nomi da parte del sistema.</span><span class="sxs-lookup"><span data-stu-id="41e2a-229">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="41e2a-230">Nella scheda <strong>Opzioni gerarchia</strong> specificare a quali utenti nell'intervallo la decisione deve essere assegnata:</span><span class="sxs-lookup"><span data-stu-id="41e2a-230">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="41e2a-231"><strong>Assegna a tutti gli utenti recuperati</strong> - La decisione viene assegnata a tutti gli utenti nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-231"><strong>Assign to all users retrieved</strong> – The decision is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="41e2a-232"><strong>Assegna solo all'ultimo utente recuperato</strong> - La decisione viene assegnata solo all'ultimo utente dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-232"><strong>Assign only to last user retrieved</strong> – The decision is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="41e2a-233"><strong>Escludi utenti con la seguente condizione:</strong> - La decisione non viene assegnata ad alcun utente nell'intervallo che soddisfa una specifica condizione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-233"><strong>Exclude users with the following condition</strong> – The decision isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="41e2a-234">Fare clic su <strong>Aggiungi condizione</strong> per specificare la condizione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-234">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="41e2a-235">Utente del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="41e2a-235">Workflow user</span></span></td>
    <td><span data-ttu-id="41e2a-236">Utenti nel flusso di lavoro corrente</span><span class="sxs-lookup"><span data-stu-id="41e2a-236">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="41e2a-237">Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="41e2a-237">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="41e2a-238">Utente</span><span class="sxs-lookup"><span data-stu-id="41e2a-238">User</span></span></td>
    <td><span data-ttu-id="41e2a-239">Utenti specifici</span><span class="sxs-lookup"><span data-stu-id="41e2a-239">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="41e2a-240">Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-240">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="41e2a-241">Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="41e2a-241">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="41e2a-242">Selezionare gli utenti a cui assegnare la decisione, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-242">Select the users to assign the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="41e2a-243">Nella scheda **Limite di tempo**, nel campo **Durata** specificare il tempo a disposizione di un utente per prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-243">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="41e2a-244">Consente di selezionare una delle opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="41e2a-244">Select one of the following options:</span></span>

    - <span data-ttu-id="41e2a-245">**Ore**: immettere il numero di ore a disposizione dell'utente per prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-245">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="41e2a-246">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-246">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="41e2a-247">**Giorni**: immettere il numero di giorni a disposizione dell'utente per prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-247">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="41e2a-248">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-248">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="41e2a-249">**Settimane**: immettere il numero di settimane a disposizione dell'utente per prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-249">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="41e2a-250">**Mesi**: selezionare il giorno e la settimana entro i quali l'utente deve prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-250">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="41e2a-251">È ad esempio possibile scegliere di far prendere la decisione all'utente entro il venerdì della terza settimana del mese.</span><span class="sxs-lookup"><span data-stu-id="41e2a-251">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="41e2a-252">**Anni**: selezionare il giorno, la settimana e il mese entro i quali l'utente deve prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-252">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="41e2a-253">È ad esempio possibile scegliere di far prendere la decisione all'utente entro il venerdì della terza settimana di dicembre.</span><span class="sxs-lookup"><span data-stu-id="41e2a-253">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

    <span data-ttu-id="41e2a-254">Se l'utente non prende la decisione nel tempo prestabilito, la decisione scadrà.</span><span class="sxs-lookup"><span data-stu-id="41e2a-254">If the user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="41e2a-255">Una decisione scaduta viene riassegnata in base alle opzioni selezionate nell'area **Riassegnazione** della pagina.</span><span class="sxs-lookup"><span data-stu-id="41e2a-255">A decision that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-a-decision-is-overdue"></a><span data-ttu-id="41e2a-256">Specificare l'azione da eseguire se una decisione è scaduta</span><span class="sxs-lookup"><span data-stu-id="41e2a-256">Specify what happens when a decision is overdue</span></span>

<span data-ttu-id="41e2a-257">Se l'utente non prende la decisione nel tempo prestabilito, la decisione scadrà.</span><span class="sxs-lookup"><span data-stu-id="41e2a-257">If a user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="41e2a-258">Una decisione scaduta può essere riassegnata o assegnata automaticamente a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="41e2a-258">A decision that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="41e2a-259">Per riassegnare la decisione scaduta, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e2a-259">Follow these steps to escalate the decision if it's overdue.</span></span>

1. <span data-ttu-id="41e2a-260">Nel riquadro sinistro fare clic su **Riassegnazione**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-260">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="41e2a-261">Selezionare la casella di controllo **Utilizza percorso di riassegnazione** per creare un percorso di riassegnazione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-261">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="41e2a-262">La decisione viene assegnata automaticamente agli utenti elencati nel percorso.</span><span class="sxs-lookup"><span data-stu-id="41e2a-262">The system automatically assigns the decision to the users who are listed in the escalation path.</span></span> <span data-ttu-id="41e2a-263">La tabella indicata di seguito rappresenta un esempio di percorso di riassegnazione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-263">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="41e2a-264">Sequenza</span><span class="sxs-lookup"><span data-stu-id="41e2a-264">Sequence</span></span> | <span data-ttu-id="41e2a-265">Percorso riassegnazione</span><span class="sxs-lookup"><span data-stu-id="41e2a-265">Escalation path</span></span>            |
    |----------|----------------------------|
    | <span data-ttu-id="41e2a-266">1</span><span class="sxs-lookup"><span data-stu-id="41e2a-266">1</span></span>        | <span data-ttu-id="41e2a-267">Assegna a: Maria</span><span class="sxs-lookup"><span data-stu-id="41e2a-267">Assign to: Donna</span></span>           |
    | <span data-ttu-id="41e2a-268">2</span><span class="sxs-lookup"><span data-stu-id="41e2a-268">2</span></span>        | <span data-ttu-id="41e2a-269">Assegna a: Francesca</span><span class="sxs-lookup"><span data-stu-id="41e2a-269">Assign to: Erin</span></span>            |
    | <span data-ttu-id="41e2a-270">3</span><span class="sxs-lookup"><span data-stu-id="41e2a-270">3</span></span>        | <span data-ttu-id="41e2a-271">Azione finale: \[Prima scelta\]</span><span class="sxs-lookup"><span data-stu-id="41e2a-271">Final action: \[Choice 1\]</span></span> |

    <span data-ttu-id="41e2a-272">In questo esempio la decisione scaduta viene assegnata a Maria.</span><span class="sxs-lookup"><span data-stu-id="41e2a-272">In this example, the system assigns the overdue decision to Donna.</span></span> <span data-ttu-id="41e2a-273">Se Maria non prende la decisione nel tempo prestabilito, la decisione verrà assegnata a Francesca.</span><span class="sxs-lookup"><span data-stu-id="41e2a-273">If Donna doesn't make the decision in the allotted time, the system assigns the decision to Erin.</span></span> <span data-ttu-id="41e2a-274">Se Francesca non prende la decisione nel tempo prestabilito, verrà selezionato  **\[Prima scelta\]** come decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-274">If Erin doesn't make the decision in the allotted time, the system selects **\[Choice 1\]** as the decision.</span></span>

3. <span data-ttu-id="41e2a-275">Per aggiungere un utente al percorso di riassegnazione, fare clic su **Aggiungi riassegnazione**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-275">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="41e2a-276">Selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="41e2a-276">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="41e2a-277">Opzione</span><span class="sxs-lookup"><span data-stu-id="41e2a-277">Option</span></span></th>
    <th><span data-ttu-id="41e2a-278">Utenti a cui viene riassegnata la decisione</span><span class="sxs-lookup"><span data-stu-id="41e2a-278">Users that the decision is escalated to</span></span></th>
    <th><span data-ttu-id="41e2a-279">Passaggi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="41e2a-279">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="41e2a-280">Gerarchia</span><span class="sxs-lookup"><span data-stu-id="41e2a-280">Hierarchy</span></span></td>
    <td><span data-ttu-id="41e2a-281">Utenti in una specifica gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="41e2a-281">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="41e2a-282">Dopo aver selezionato <strong>Gerarchia</strong>, nella scheda <strong>Selezione gerarchia</strong> selezionare il tipo di gerarchia cui riassegnare la decisione nell'elenco <strong>Tipo di gerarchia</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-282">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the decision to.</span></span></li>
    <li><span data-ttu-id="41e2a-283">Il sistema dovrà recuperare un intervallo di nomi utente dalla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="41e2a-283">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="41e2a-284">Questi nomi rappresentano gli utenti a cui può essere riassegnata la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-284">These names represent users that the decision can be escalated to.</span></span> <span data-ttu-id="41e2a-285">Attenersi alla procedura indicata di seguito per specificare il punto di inizio e il punto finale dell'intervallo di nomi utente recuperati dal sistema:</span><span class="sxs-lookup"><span data-stu-id="41e2a-285">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="41e2a-286">Per specificare il punto di inizio, selezionare una persona dall'elenco <strong>Inizia da</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-286">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="41e2a-287">Per specificare il punto finale, fare clic su <strong>Aggiungi condizione</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-287">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="41e2a-288">Immettere quindi una condizione per determinare il punto della gerarchia in cui verrà arrestato il recupero dei nomi da parte del sistema.</span><span class="sxs-lookup"><span data-stu-id="41e2a-288">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="41e2a-289">Nella scheda <strong>Opzioni gerarchia</strong> specificare a quali utenti nell'intervallo la decisione deve essere riassegnata:</span><span class="sxs-lookup"><span data-stu-id="41e2a-289">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="41e2a-290"><strong>Assegna a tutti gli utenti recuperati</strong> - La decisione viene riassegnata a tutti gli utenti nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-290"><strong>Assign to all users retrieved</strong> – The decision is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="41e2a-291"><strong>Assegna solo all'ultimo utente recuperato</strong> - La decisione viene riassegnata solo all'ultimo utente dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="41e2a-291"><strong>Assign only to last user retrieved</strong> – The decision is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="41e2a-292"><strong>Escludi utenti con la seguente condizione:</strong> - La decisione non viene riassegnata ad alcun utente nell'intervallo che soddisfa una specifica condizione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-292"><strong>Exclude users with the following condition:</strong> – The decision isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="41e2a-293">Fare clic su <strong>Aggiungi condizione</strong> per specificare la condizione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-293">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="41e2a-294">Utente del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="41e2a-294">Workflow user</span></span></td>
    <td><span data-ttu-id="41e2a-295">Utenti nel flusso di lavoro corrente</span><span class="sxs-lookup"><span data-stu-id="41e2a-295">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="41e2a-296">Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="41e2a-296">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="41e2a-297">Utente</span><span class="sxs-lookup"><span data-stu-id="41e2a-297">User</span></span></td>
    <td><span data-ttu-id="41e2a-298">Utenti specifici</span><span class="sxs-lookup"><span data-stu-id="41e2a-298">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="41e2a-299">Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-299">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="41e2a-300">Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="41e2a-300">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="41e2a-301">Selezionare gli utenti a cui riassegnare la decisione, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</span><span class="sxs-lookup"><span data-stu-id="41e2a-301">Select the users to escalate the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="41e2a-302">Nella scheda **Limite di tempo**, nel campo **Durata** specificare il tempo a disposizione di un utente per prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-302">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="41e2a-303">Consente di selezionare una delle opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="41e2a-303">Select one of the following options:</span></span>

    - <span data-ttu-id="41e2a-304">**Ore**: immettere il numero di ore a disposizione dell'utente per prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-304">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="41e2a-305">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-305">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="41e2a-306">**Giorni**: immettere il numero di giorni a disposizione dell'utente per prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-306">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="41e2a-307">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-307">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="41e2a-308">**Settimane**: immettere il numero di settimane a disposizione dell'utente per prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-308">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="41e2a-309">**Mesi**: selezionare il giorno e la settimana entro i quali l'utente deve prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-309">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="41e2a-310">È ad esempio possibile scegliere di far prendere la decisione all'utente entro il venerdì della terza settimana del mese.</span><span class="sxs-lookup"><span data-stu-id="41e2a-310">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="41e2a-311">**Anni**: selezionare il giorno, la settimana e il mese entro i quali l'utente deve prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-311">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="41e2a-312">È ad esempio possibile scegliere di far prendere la decisione all'utente entro il venerdì della terza settimana di dicembre.</span><span class="sxs-lookup"><span data-stu-id="41e2a-312">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

5. <span data-ttu-id="41e2a-313">Ripetere i passaggi da 3 a 4 per ogni utente che si desidera aggiungere al percorso di riassegnazione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-313">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="41e2a-314">È possibile modificare l'ordine degli utenti.</span><span class="sxs-lookup"><span data-stu-id="41e2a-314">You can change the order of the users.</span></span>
6. <span data-ttu-id="41e2a-315">Se gli utenti nel percorso di riassegnazione non prendono la decisione nel tempo prestabilito, la decisione verrà presa dal sistema.</span><span class="sxs-lookup"><span data-stu-id="41e2a-315">If the users in the escalation path don't make the decision in the allotted time, the system makes the decision.</span></span> <span data-ttu-id="41e2a-316">Per specificare l'opzione selezionata dal sistema, selezionare la riga **Azione**, quindi nella scheda **Termina azione** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-316">To specify the option that the system selects, select the **Action** row, and then, on the **End action** tab, select an option.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="41e2a-317">Impostare un limite di tempo</span><span class="sxs-lookup"><span data-stu-id="41e2a-317">Set a time limit</span></span>

<span data-ttu-id="41e2a-318">Per prendere la decisione in un periodo di tempo specifico, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e2a-318">Follow these steps if the decision must be made in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="41e2a-319">Le opzioni selezionate in questi passaggi prevalgono su quelle selezionate nelle aree **Assegnazione** e **Riassegnazione** della pagina.</span><span class="sxs-lookup"><span data-stu-id="41e2a-319">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="41e2a-320">Nel riquadro sinistro, fare clic sull'icona **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-320">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="41e2a-321">Selezionare la casella di controllo **Imposta un limite di tempo per l'elemento del flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="41e2a-321">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="41e2a-322">Nel campo **Durata** specificare il momento in cui prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-322">In the **Duration** field, specify when the decision must be made.</span></span> <span data-ttu-id="41e2a-323">Consente di selezionare una delle opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="41e2a-323">Select one of the following options:</span></span>

    - <span data-ttu-id="41e2a-324">**Ore**: immettere il numero di ore.</span><span class="sxs-lookup"><span data-stu-id="41e2a-324">**Hours** – Enter the number of hours.</span></span> <span data-ttu-id="41e2a-325">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-325">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="41e2a-326">**Giorni**: immettere il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="41e2a-326">**Days** – Enter the number of days.</span></span> <span data-ttu-id="41e2a-327">Selezionare quindi il calendario utilizzato dall'organizzazione e immettere informazioni sulla settimana lavorativa dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-327">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="41e2a-328">**Settimane**: immettere il numero di settimane.</span><span class="sxs-lookup"><span data-stu-id="41e2a-328">**Weeks** – Enter the number of weeks.</span></span>
    - <span data-ttu-id="41e2a-329">**Mesi**: selezionare il giorno e la settimana entro i quali prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-329">**Months** – Select the day and week that the decision must be made by.</span></span> <span data-ttu-id="41e2a-330">È ad esempio possibile scegliere di far prendere la decisione entro il venerdì della terza settimana del mese.</span><span class="sxs-lookup"><span data-stu-id="41e2a-330">For example, you might want the decision to be made by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="41e2a-331">**Anni**: selezionare il giorno, la settimana e il mese entro i quali prendere la decisione.</span><span class="sxs-lookup"><span data-stu-id="41e2a-331">**Years** – Select the day, week, and month that the decision must be made by.</span></span> <span data-ttu-id="41e2a-332">È ad esempio possibile scegliere di far prendere la decisione entro il venerdì della terza settimana di dicembre.</span><span class="sxs-lookup"><span data-stu-id="41e2a-332">For example, you might want the decision to be made by Friday of the third week of December.</span></span>

4. <span data-ttu-id="41e2a-333">Se viene superato il limite di tempo, la decisione verrà presa dal sistema.</span><span class="sxs-lookup"><span data-stu-id="41e2a-333">If the time limit is exceeded, the system makes the decision.</span></span> <span data-ttu-id="41e2a-334">Nell'elenco **Azione** selezionare l'opzione che dovrà essere selezionata dal sistema.</span><span class="sxs-lookup"><span data-stu-id="41e2a-334">In the **Action** list, select the option that the system should select.</span></span>
