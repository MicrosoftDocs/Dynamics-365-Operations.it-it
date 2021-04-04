---
title: Configurare le attività automatiche in un flusso di lavoro
description: In questo argomento viene descritto come configurare le proprietà per un'attività automatica.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b63a9a99c442b0fbe971bc2e8f05fc8c09ec3087
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567488"
---
# <a name="configure-automated-tasks-in-a-workflow"></a><span data-ttu-id="52f92-103">Configurare le attività automatiche in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="52f92-103">Configure automated tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52f92-104">In questo argomento viene descritto come configurare le proprietà per un'attività automatica.</span><span class="sxs-lookup"><span data-stu-id="52f92-104">This topic explains how to configure the properties for an automated task.</span></span>

<span data-ttu-id="52f92-105">Per configurare un'attività automatica, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'attività e scegliere **Proprietà** per aprire la pagina **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="52f92-105">To configure an automated task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="52f92-106">Per configurare le proprietà dell'attività automatica, attenersi alle procedure indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="52f92-106">Then use the following procedures to configure the properties for the automated task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="52f92-107">Assegnare un nome all'attività</span><span class="sxs-lookup"><span data-stu-id="52f92-107">Name the task</span></span>

<span data-ttu-id="52f92-108">Per immettere un nome per l'attività automatica, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="52f92-108">Follow these steps to enter a name for the automated task.</span></span>

1. <span data-ttu-id="52f92-109">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="52f92-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="52f92-110">Nel campo **Nome** immettere un nome univoco per l'attività.</span><span class="sxs-lookup"><span data-stu-id="52f92-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="52f92-111">Specificare quando verranno inviate le notifiche</span><span class="sxs-lookup"><span data-stu-id="52f92-111">Specify when notifications are sent</span></span>

<span data-ttu-id="52f92-112">È possibile inviare notifiche agli utenti quando è stata eseguita o annullata un'attività automatica.</span><span class="sxs-lookup"><span data-stu-id="52f92-112">You can send notifications to people when an automated task has been run or canceled.</span></span> <span data-ttu-id="52f92-113">Per specificare quando e a chi verranno inviate le notifiche, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="52f92-113">Follow these steps to specify when notifications are sent, and who they are sent to.</span></span>

1. <span data-ttu-id="52f92-114">Nel riquadro sinistro fare clic su **Notifiche**.</span><span class="sxs-lookup"><span data-stu-id="52f92-114">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="52f92-115">Selezionare la casella di controllo accanto agli eventi per cui inviare notifiche:</span><span class="sxs-lookup"><span data-stu-id="52f92-115">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="52f92-116">**Esecuzione**: le notifiche vengono inviate all'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="52f92-116">**Execution** – Notifications are sent when the task has been run.</span></span>
    - <span data-ttu-id="52f92-117">**Annullato**: le notifiche vengono inviate se l'attività viene annullata.</span><span class="sxs-lookup"><span data-stu-id="52f92-117">**Canceled** – Notifications are sent when the task has been canceled.</span></span>

3. <span data-ttu-id="52f92-118">Scegliere la riga per un evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="52f92-118">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="52f92-119">Nella scheda **Testo notifiche** immettere il testo della notifica nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="52f92-119">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="52f92-120">Per personalizzare la notifica, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="52f92-120">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="52f92-121">I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione della notifica.</span><span class="sxs-lookup"><span data-stu-id="52f92-121">Placeholders are replaced with appropriate data when the notification is shown to users.</span></span> <span data-ttu-id="52f92-122">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52f92-122">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="52f92-123">Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="52f92-123">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="52f92-124">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="52f92-124">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="52f92-125">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="52f92-125">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="52f92-126">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="52f92-126">Click **Insert**.</span></span>

6. <span data-ttu-id="52f92-127">Per aggiungere traduzioni della notifica, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52f92-127">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="52f92-128">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="52f92-128">Click **Translations**.</span></span>
    2. <span data-ttu-id="52f92-129">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="52f92-129">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="52f92-130">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="52f92-130">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="52f92-131">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="52f92-131">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="52f92-132">Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="52f92-132">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="52f92-133">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="52f92-133">Click **Close**.</span></span>

7. <span data-ttu-id="52f92-134">Nella scheda **Destinatario** specificare il destinatario cui inviare le notifiche.</span><span class="sxs-lookup"><span data-stu-id="52f92-134">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="52f92-135">Selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 8.</span><span class="sxs-lookup"><span data-stu-id="52f92-135">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="52f92-136">Opzione</span><span class="sxs-lookup"><span data-stu-id="52f92-136">Option</span></span></th>
    <th><span data-ttu-id="52f92-137">Destinatari delle notifiche</span><span class="sxs-lookup"><span data-stu-id="52f92-137">Notification recipients</span></span></th>
    <th><span data-ttu-id="52f92-138">Passaggi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="52f92-138">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="52f92-139">Partecipante</span><span class="sxs-lookup"><span data-stu-id="52f92-139">Participant</span></span></td>
    <td><span data-ttu-id="52f92-140">Utenti assegnati a un ruolo o un gruppo specifico</span><span class="sxs-lookup"><span data-stu-id="52f92-140">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="52f92-141">Dopo aver selezionato <strong>Partecipante</strong>, nella scheda <strong>Basato sui ruoli</strong> selezionare il tipo di gruppo o il ruolo a cui inviare le notifiche nell'elenco <strong>Tipo di partecipante</strong>.</span><span class="sxs-lookup"><span data-stu-id="52f92-141">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="52f92-142">Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui inviare notifiche.</span><span class="sxs-lookup"><span data-stu-id="52f92-142">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="52f92-143">Utente del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="52f92-143">Workflow user</span></span></td>
    <td><span data-ttu-id="52f92-144">Utenti che partecipano al flusso di lavoro corrente</span><span class="sxs-lookup"><span data-stu-id="52f92-144">Users who participate in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="52f92-145">Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="52f92-145">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="52f92-146">Utente</span><span class="sxs-lookup"><span data-stu-id="52f92-146">User</span></span></td>
    <td><span data-ttu-id="52f92-147">Utenti specifici</span><span class="sxs-lookup"><span data-stu-id="52f92-147">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="52f92-148">Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</span><span class="sxs-lookup"><span data-stu-id="52f92-148">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="52f92-149">Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="52f92-149">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="52f92-150">Selezionare gli utenti a cui inviare notifiche, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</span><span class="sxs-lookup"><span data-stu-id="52f92-150">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="52f92-151">Ripetere i passaggi dal 3 al 7 per ciascun evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="52f92-151">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]