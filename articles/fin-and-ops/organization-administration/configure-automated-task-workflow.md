---
title: "Configurare le attività automatiche in un flusso di lavoro"
description: "In questo argomento viene descritto come configurare le proprietà per un'attività automatica."
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
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 047abbf297b3514c7f97d2baa6c0f5cab6696cde
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="configure-automated-tasks-in-a-workflow"></a><span data-ttu-id="842df-103">Configurare le attività automatiche in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="842df-103">Configure automated tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="842df-104">In questo argomento viene descritto come configurare le proprietà per un'attività automatica.</span><span class="sxs-lookup"><span data-stu-id="842df-104">This topic explains how to configure the properties for an automated task.</span></span>

<span data-ttu-id="842df-105">Per configurare un'attività automatica, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'attività e scegliere **Proprietà** per aprire la pagina **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="842df-105">To configure an automated task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="842df-106">Per configurare le proprietà dell'attività automatica, attenersi alle procedure indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="842df-106">Then use the following procedures to configure the properties for the automated task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="842df-107">Assegnare un nome all'attività</span><span class="sxs-lookup"><span data-stu-id="842df-107">Name the task</span></span>
<span data-ttu-id="842df-108">Per immettere un nome per l'attività automatica, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="842df-108">Follow these steps to enter a name for the automated task.</span></span>

1.  <span data-ttu-id="842df-109">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="842df-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="842df-110">Nel campo **Nome** immettere un nome univoco per l'attività.</span><span class="sxs-lookup"><span data-stu-id="842df-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="842df-111">Specificare quando verranno inviate le notifiche</span><span class="sxs-lookup"><span data-stu-id="842df-111">Specify when notifications are sent</span></span>
<span data-ttu-id="842df-112">È possibile inviare notifiche agli utenti quando è stata eseguita o annullata un'attività automatica.</span><span class="sxs-lookup"><span data-stu-id="842df-112">You can send notifications to people when an automated task has been run or canceled.</span></span> <span data-ttu-id="842df-113">Per specificare quando e a chi verranno inviate le notifiche, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="842df-113">Follow these steps to specify when notifications are sent, and who they are sent to.</span></span>

1.  <span data-ttu-id="842df-114">Nel riquadro sinistro fare clic su **Notifiche**.</span><span class="sxs-lookup"><span data-stu-id="842df-114">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="842df-115">Selezionare la casella di controllo accanto agli eventi per cui inviare notifiche:</span><span class="sxs-lookup"><span data-stu-id="842df-115">Select the check box next to the events to send notifications for:</span></span>
    -   <span data-ttu-id="842df-116">**Esecuzione**: le notifiche vengono inviate all'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="842df-116">**Execution** – Notifications are sent when the task has been run.</span></span>
    -   <span data-ttu-id="842df-117">**Annullato**: le notifiche vengono inviate se l'attività viene annullata.</span><span class="sxs-lookup"><span data-stu-id="842df-117">**Canceled** – Notifications are sent when the task has been canceled.</span></span>

3.  <span data-ttu-id="842df-118">Scegliere la riga per un evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="842df-118">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="842df-119">Nella scheda **Testo notifiche** immettere il testo della notifica nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="842df-119">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5.  <span data-ttu-id="842df-120">Per personalizzare la notifica, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="842df-120">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="842df-121">I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione della notifica.</span><span class="sxs-lookup"><span data-stu-id="842df-121">Placeholders are replaced with appropriate data when the notification is shown to users.</span></span> <span data-ttu-id="842df-122">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="842df-122">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="842df-123">Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="842df-123">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="842df-124">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="842df-124">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="842df-125">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="842df-125">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="842df-126">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="842df-126">Click **Insert**.</span></span>

6.  <span data-ttu-id="842df-127">Per aggiungere traduzioni della notifica, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="842df-127">To add translations of the notification, follow these steps:</span></span>
    1.  <span data-ttu-id="842df-128">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="842df-128">Click **Translations**.</span></span>
    2.  <span data-ttu-id="842df-129">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="842df-129">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="842df-130">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="842df-130">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="842df-131">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="842df-131">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="842df-132">Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="842df-132">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6.  <span data-ttu-id="842df-133">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="842df-133">Click **Close**.</span></span>

7.  <span data-ttu-id="842df-134">Nella scheda **Destinatario** specificare il destinatario cui inviare le notifiche.</span><span class="sxs-lookup"><span data-stu-id="842df-134">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="842df-135">Selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 8.</span><span class="sxs-lookup"><span data-stu-id="842df-135">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="842df-136">Opzione</span><span class="sxs-lookup"><span data-stu-id="842df-136">Option</span></span></th>
    <th><span data-ttu-id="842df-137">Destinatari delle notifiche</span><span class="sxs-lookup"><span data-stu-id="842df-137">Notification recipients</span></span></th>
    <th><span data-ttu-id="842df-138">Passaggi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="842df-138">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="842df-139">Partecipante</span><span class="sxs-lookup"><span data-stu-id="842df-139">Participant</span></span></td>
    <td><span data-ttu-id="842df-140">Utenti assegnati a un ruolo o un gruppo specifico</span><span class="sxs-lookup"><span data-stu-id="842df-140">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="842df-141">Dopo aver selezionato <strong>Partecipante</strong>, nella scheda <strong>Basato sui ruoli</strong> selezionare il tipo di gruppo o il ruolo a cui inviare le notifiche nell'elenco <strong>Tipo di partecipante</strong>.</span><span class="sxs-lookup"><span data-stu-id="842df-141">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="842df-142">Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui inviare notifiche.</span><span class="sxs-lookup"><span data-stu-id="842df-142">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="842df-143">Utente del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="842df-143">Workflow user</span></span></td>
    <td><span data-ttu-id="842df-144">Utenti che partecipano al flusso di lavoro corrente</span><span class="sxs-lookup"><span data-stu-id="842df-144">Users who participate in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="842df-145">Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="842df-145">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="842df-146">Utente</span><span class="sxs-lookup"><span data-stu-id="842df-146">User</span></span></td>
    <td><span data-ttu-id="842df-147">Utenti specifici di Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="842df-147">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="842df-148">Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</span><span class="sxs-lookup"><span data-stu-id="842df-148">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="842df-149">Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="842df-149">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="842df-150">Selezionare gli utenti a cui inviare notifiche, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</span><span class="sxs-lookup"><span data-stu-id="842df-150">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  <span data-ttu-id="842df-151">Ripetere i passaggi dal 3 al 7 per ciascun evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="842df-151">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>





