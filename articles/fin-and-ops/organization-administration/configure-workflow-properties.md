---
title: "Configurare le proprietà del flusso di lavoro"
description: "In questo argomento viene descritto come configurare le proprietà per un flusso di lavoro."
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
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 19cc8f92b5bb6d9ddfdc77785e48de17ed005703
ms.openlocfilehash: 7ea35d851613a19889392400e31cf8492d5dc799
ms.contentlocale: it-it
ms.lasthandoff: 03/23/2018

---

# <a name="configure-workflow-properties"></a><span data-ttu-id="cf344-103">Configurare le proprietà del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cf344-103">Configure workflow properties</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cf344-104">In questo argomento viene descritto come configurare le proprietà per un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf344-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="cf344-105">Per configurare le proprietà di un flusso di lavoro, aprirlo nell'editor flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf344-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="cf344-106">Fare clic sulla canvas dell'editor flusso di lavoro, quindi scegliere **Proprietà** per aprire la pagina **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cf344-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="cf344-107">Per configurare le diverse proprietà del flusso di lavoro, attenersi alle procedure indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="cf344-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="cf344-108">Assegnare un nome al flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cf344-108">Name the workflow</span></span>
<span data-ttu-id="cf344-109">Per immettere un nome per il flusso di lavoro, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="cf344-109">Follow these steps to enter a name for the workflow.</span></span>

1.  <span data-ttu-id="cf344-110">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="cf344-110">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="cf344-111">Nel campo **Nome** immettere un nome univoco per il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf344-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="cf344-112">Se ad esempio si creano flussi di lavoro relativi alle richieste di acquisto per ciascun paese in cui opera una società, è possibile assegnare a uno di questi flussi di lavoro il nome **Richieste di acquisto Danimarca** o **Richieste di acquisto Spagna**.</span><span class="sxs-lookup"><span data-stu-id="cf344-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="cf344-113">Specificare il proprietario del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cf344-113">Specify the workflow owner</span></span>
<span data-ttu-id="cf344-114">Il proprietario del flusso di lavoro è la persona che si occuperà della gestione e della manutenzione del flusso.</span><span class="sxs-lookup"><span data-stu-id="cf344-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="cf344-115">Per specificare il proprietario del flusso di lavoro, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="cf344-115">Follow these steps to specify the workflow owner.</span></span>

1.  <span data-ttu-id="cf344-116">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="cf344-116">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="cf344-117">Nell'elenco **Proprietario** selezionare il nome della persona che gestirà il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf344-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="cf344-118">Selezionare un modello di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="cf344-118">Select an email template</span></span>
<span data-ttu-id="cf344-119">Per selezionare il modello di messaggio di posta elettronica che verrà utilizzato per generare notifiche per il flusso di lavoro, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="cf344-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1.  <span data-ttu-id="cf344-120">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="cf344-120">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="cf344-121">Nell'elenco **Modelli di messaggio di posta elettronica per le notifiche del flusso di lavoro** selezionare il modello.</span><span class="sxs-lookup"><span data-stu-id="cf344-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="cf344-122">Immettere istruzioni per gli utenti</span><span class="sxs-lookup"><span data-stu-id="cf344-122">Enter instructions for users</span></span>
<span data-ttu-id="cf344-123">È possibile fornire istruzioni agli utenti che invieranno documenti per l'elaborazione e l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="cf344-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="cf344-124">Questi utenti vengono indicati come *iniziatori*.</span><span class="sxs-lookup"><span data-stu-id="cf344-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="cf344-125">Si supponga ad esempio di dover creare un flusso di lavoro relativo alle richieste di acquisto e di immettere le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="cf344-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="cf344-126">Tali istruzioni possono essere visualizzate dagli utenti che immettono richieste di acquisto nella pagina **Richieste di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="cf344-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="cf344-127">Per visualizzare le istruzioni, l'iniziatore dovrà fare clic sull'icona nell barra dei messaggi del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf344-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="cf344-128">Per immettere istruzioni per gli utenti, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="cf344-128">Follow these steps to enter instructions for users.</span></span>

1.  <span data-ttu-id="cf344-129">Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.</span><span class="sxs-lookup"><span data-stu-id="cf344-129">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="cf344-130">Nel campo **Istruzioni di invio** immettere le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="cf344-130">In the **Submission instructions** field, enter the instructions.</span></span>
3.  <span data-ttu-id="cf344-131">Per personalizzare le istruzioni, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="cf344-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="cf344-132">I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf344-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="cf344-133">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf344-133">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="cf344-134">Fare clic sul campo **Istruzioni di invio** per specificare il punto in cui deve essere inserito il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="cf344-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="cf344-135">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="cf344-135">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="cf344-136">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="cf344-136">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="cf344-137">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="cf344-137">Click **Insert**.</span></span>

4.  <span data-ttu-id="cf344-138">Per aggiungere traduzioni delle istruzioni, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf344-138">To add translations of the instructions, follow these steps:</span></span>
    1.  <span data-ttu-id="cf344-139">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="cf344-139">Click **Translations**.</span></span>
    2.  <span data-ttu-id="cf344-140">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cf344-140">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="cf344-141">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="cf344-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4.  <span data-ttu-id="cf344-142">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="cf344-142">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="cf344-143">Per personalizzare il testo, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="cf344-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="cf344-144">Per istruzioni su come immettere un segnaposto, vedere il passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="cf344-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6.  <span data-ttu-id="cf344-145">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cf344-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used"></a><span data-ttu-id="cf344-146">Specificare quando verrà utilizzato il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cf344-146">Specify when this workflow is used</span></span>
<span data-ttu-id="cf344-147">È possibile creare più flussi di lavoro basati sullo stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="cf344-147">You can create multiple workflows that are based on the same type.</span></span> <span data-ttu-id="cf344-148">Una società può creare ad esempio flussi di lavoro relativi alle richieste di acquisto per ciascun paese in cui opera, ad esempio Richieste di acquisto Danimarca e Richieste di acquisto Spagna.</span><span class="sxs-lookup"><span data-stu-id="cf344-148">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain.</span></span> <span data-ttu-id="cf344-149">Se sono presenti più flussi di lavoro basati sullo stesso tipo, è necessario specificare quando verrà utilizzato ciascun flusso.</span><span class="sxs-lookup"><span data-stu-id="cf344-149">When you have multiple workflows that are based on the same type, you must specify when each workflow is used.</span></span> <span data-ttu-id="cf344-150">In base all'esempio precedente, è necessario specificare le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf344-150">For the preceding example, you specify the following conditions:</span></span>

-   <span data-ttu-id="cf344-151">Richieste di acquisto Danimarca: questo flusso di lavoro viene utilizzato quando sussiste la condizione paese = DK.</span><span class="sxs-lookup"><span data-stu-id="cf344-151">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
-   <span data-ttu-id="cf344-152">Richieste di acquisto Spagna: questo flusso di lavoro viene utilizzato quando sussiste la condizione paese = ES.</span><span class="sxs-lookup"><span data-stu-id="cf344-152">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="cf344-153">Per specificare quando verrà utilizzato il flusso di lavoro che si sta configurando, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="cf344-153">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1.  <span data-ttu-id="cf344-154">Nel riquadro sinistro fare clic su **Attivazione**.</span><span class="sxs-lookup"><span data-stu-id="cf344-154">In the left pane, click **Activation**.</span></span>
2.  <span data-ttu-id="cf344-155">Selezionare la casella di controllo **Imposta le condizioni per eseguire il flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="cf344-155">Select the **Set the conditions for running this workflow** check box.</span></span>
3.  <span data-ttu-id="cf344-156">Fare clic su **Aggiungi condizione**.</span><span class="sxs-lookup"><span data-stu-id="cf344-156">Click **Add condition**.</span></span>
4.  <span data-ttu-id="cf344-157">Immettere una condizione.</span><span class="sxs-lookup"><span data-stu-id="cf344-157">Enter a condition.</span></span>
5.  <span data-ttu-id="cf344-158">Immettere altre condizioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="cf344-158">Enter any additional conditions that are required.</span></span>
6.  <span data-ttu-id="cf344-159">Per verificare la correttezza della configurazione delle condizioni immesse, eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf344-159">To verify that the conditions that you entered are set correctly, follow these steps:</span></span>
    1.  <span data-ttu-id="cf344-160">Fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="cf344-160">Click **Test**.</span></span>
    2.  <span data-ttu-id="cf344-161">Nella pagina **Test condizione flusso di lavoro**, nell'area **Convalida condizione**, selezionare un record.</span><span class="sxs-lookup"><span data-stu-id="cf344-161">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3.  <span data-ttu-id="cf344-162">Fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="cf344-162">Click **Test**.</span></span> <span data-ttu-id="cf344-163">Il sistema valuta il record per determinare se soddisfa le condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="cf344-163">The system evaluates the record to determine whether it meets the conditions that you specified.</span></span> <span data-ttu-id="cf344-164">Se ad esempio si crea un flusso di lavoro relativo alle richieste di acquisto per la Spagna, nell'area della pagina **Convalida condizione** viene visualizzato un elenco delle richieste di acquisto.</span><span class="sxs-lookup"><span data-stu-id="cf344-164">For example, if you're creating a purchase requisition workflow for Spain, the **Validate condition** area of the page shows a list of purchase requisitions.</span></span> <span data-ttu-id="cf344-165">Se si fa clic su **Test**, la richiesta di acquisto selezionata verrà automaticamente valutata per determinare se sussiste la condizione paese = ES.</span><span class="sxs-lookup"><span data-stu-id="cf344-165">When you click **Test**, the system evaluates the selected purchase requisition to determine whether the country/region is ES.</span></span>
    4.  <span data-ttu-id="cf344-166">Fare clic su **OK** o su **Annulla** per tornare alla pagina **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cf344-166">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="cf344-167">Specificare quando verranno inviate le notifiche</span><span class="sxs-lookup"><span data-stu-id="cf344-167">Specify when notifications are sent</span></span>
<span data-ttu-id="cf344-168">Quando si invia un documento per l'elaborazione, viene creata un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf344-168">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="cf344-169">È possibile inviare notifiche agli utenti quando le istanze basate sul flusso di lavoro corrente vengono avviate, completate, terminate o arrestate a causa di un errore.</span><span class="sxs-lookup"><span data-stu-id="cf344-169">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="cf344-170">Per specificare quando verranno inviate le notifiche, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="cf344-170">Follow these steps to specify when notifications are sent.</span></span>

1.  <span data-ttu-id="cf344-171">Nel riquadro sinistro fare clic su **Notifiche**.</span><span class="sxs-lookup"><span data-stu-id="cf344-171">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="cf344-172">Selezionare la casella di controllo per ogni evento che attiverà notifiche:</span><span class="sxs-lookup"><span data-stu-id="cf344-172">Select the check box for each event that should trigger notifications:</span></span>
    -   <span data-ttu-id="cf344-173">**Avviato**: consente di inviare notifiche quando un'istanza del flusso di lavoro viene avviata.</span><span class="sxs-lookup"><span data-stu-id="cf344-173">**Started** – Send notifications when a workflow instance is started.</span></span>
    -   <span data-ttu-id="cf344-174">**Interrotto**: consente di inviare notifiche quando un'istanza del flusso di lavoro viene interrotta a causa di un errore.</span><span class="sxs-lookup"><span data-stu-id="cf344-174">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    -   <span data-ttu-id="cf344-175">**Completato**: consente di inviare notifiche quando un'istanza del flusso di lavoro viene completata.</span><span class="sxs-lookup"><span data-stu-id="cf344-175">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    -   <span data-ttu-id="cf344-176">**Irreversibile**: consente di inviare notifiche quando un'istanza del flusso di lavoro viene interrotta a causa di un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="cf344-176">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    -   <span data-ttu-id="cf344-177">**Terminato**: consente di inviare notifiche quando un'istanza del flusso di lavoro viene terminata.</span><span class="sxs-lookup"><span data-stu-id="cf344-177">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3.  <span data-ttu-id="cf344-178">Scegliere la riga per un evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="cf344-178">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="cf344-179">Nella scheda **Testo notifiche** immettere il testo della notifica.</span><span class="sxs-lookup"><span data-stu-id="cf344-179">On the **Notification text** tab, enter the text of the notification.</span></span>
5.  <span data-ttu-id="cf344-180">Per personalizzare il testo, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="cf344-180">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="cf344-181">I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione del testo.</span><span class="sxs-lookup"><span data-stu-id="cf344-181">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="cf344-182">Per inserire un segnaposto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf344-182">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="cf344-183">Fare clic sul campo per specificare il punto in cui deve essere inserito il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="cf344-183">Click in the field to specify where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="cf344-184">Fare clic su **Inserisci segnaposto**.</span><span class="sxs-lookup"><span data-stu-id="cf344-184">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="cf344-185">Nell'elenco visualizzato selezionare il segnaposto da inserire.</span><span class="sxs-lookup"><span data-stu-id="cf344-185">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="cf344-186">Fare clic su **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="cf344-186">Click **Insert**.</span></span>

6.  <span data-ttu-id="cf344-187">Per aggiungere traduzioni del testo, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf344-187">To add translations of the text, follow these steps:</span></span>
    1.  <span data-ttu-id="cf344-188">Fare clic su **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="cf344-188">Click **Translations**.</span></span>
    2.  <span data-ttu-id="cf344-189">Nella pagina visualizzata fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cf344-189">On the page that appears, Click **Add**.</span></span>
    3.  <span data-ttu-id="cf344-190">Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="cf344-190">In the list that appears, select the language that you will enter the text in.</span></span>
    4.  <span data-ttu-id="cf344-191">Nel campo **Testo tradotto** immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="cf344-191">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="cf344-192">Per personalizzare il testo, è possibile inserire segnaposto.</span><span class="sxs-lookup"><span data-stu-id="cf344-192">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="cf344-193">Per istruzioni su come immettere un segnaposto, vedere il passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="cf344-193">For instructions about how to enter a placeholder, see step 5.</span></span>
    6.  <span data-ttu-id="cf344-194">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cf344-194">Click **Close**.</span></span>

7.  <span data-ttu-id="cf344-195">Nella scheda **Destinatario** utilizzare le opzioni seguenti per specificare l'utente che deve ricevere le notifiche.</span><span class="sxs-lookup"><span data-stu-id="cf344-195">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="cf344-196">Opzione</span><span class="sxs-lookup"><span data-stu-id="cf344-196">Option</span></span></th>
    <th><span data-ttu-id="cf344-197">Le notifiche vengono inviate a questi utenti</span><span class="sxs-lookup"><span data-stu-id="cf344-197">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="cf344-198">Per inviare notifiche, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="cf344-198">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="cf344-199">Partecipante</span><span class="sxs-lookup"><span data-stu-id="cf344-199">Participant</span></span></td>
    <td><span data-ttu-id="cf344-200">Utenti assegnati a un ruolo o un gruppo specifico</span><span class="sxs-lookup"><span data-stu-id="cf344-200">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="cf344-201">Nella scheda <strong>Destinatario</strong> fare clic su <strong>Partecipante</strong>.</span><span class="sxs-lookup"><span data-stu-id="cf344-201">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="cf344-202">Nella scheda <strong>Basato sui ruoli</strong>, nell'elenco <strong>Tipo di partecipante</strong> selezionare il tipo di gruppo o il ruolo a cui inviare le notifiche.</span><span class="sxs-lookup"><span data-stu-id="cf344-202">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="cf344-203">Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui inviare notifiche.</span><span class="sxs-lookup"><span data-stu-id="cf344-203">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="cf344-204">Utente del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cf344-204">Workflow user</span></span></td>
    <td><span data-ttu-id="cf344-205">Utenti che partecipano al flusso di lavoro corrente</span><span class="sxs-lookup"><span data-stu-id="cf344-205">Users who are participants in this workflow</span></span></td>
    <td><ol>
    <li><span data-ttu-id="cf344-206">Nella scheda <strong>Destinatario</strong>, fare clic su <strong>Utente del flusso di lavoro</strong>.</span><span class="sxs-lookup"><span data-stu-id="cf344-206">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="cf344-207">Nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un partecipante al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf344-207">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="cf344-208">Utente</span><span class="sxs-lookup"><span data-stu-id="cf344-208">User</span></span></td>
    <td><span data-ttu-id="cf344-209">Utenti specifici di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cf344-209">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="cf344-210">Nella scheda <strong>Destinatario</strong>, fare clic su <strong>Utente</strong>.</span><span class="sxs-lookup"><span data-stu-id="cf344-210">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="cf344-211">Nella scheda <strong>Utente</strong>, nell'elenco <strong>Utenti disponibili</strong> sono presenti tutti gli utenti di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cf344-211">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="cf344-212">Selezionare gli utenti a cui inviare notifiche, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</span><span class="sxs-lookup"><span data-stu-id="cf344-212">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  <span data-ttu-id="cf344-213">Ripetere i passaggi dal 3 al 7 per ciascun evento selezionato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="cf344-213">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="cf344-214">Immettere commenti sulle modifiche apportate al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf344-214">Enter comments about the changes that you made to the workflow</span></span>
<span data-ttu-id="cf344-215">Per immettere commenti sulle modifiche apportate al flusso di lavoro, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="cf344-215">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1.  <span data-ttu-id="cf344-216">Nel riquadro sinistro fare clic su **Note**.</span><span class="sxs-lookup"><span data-stu-id="cf344-216">In the left pane, click **Notes**.</span></span>
2.  <span data-ttu-id="cf344-217">Nel campo **Immettere commenti sul flusso di lavoro** immettere i commenti.</span><span class="sxs-lookup"><span data-stu-id="cf344-217">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3.  <span data-ttu-id="cf344-218">Rivedere i commenti.</span><span class="sxs-lookup"><span data-stu-id="cf344-218">Review your comments.</span></span> <span data-ttu-id="cf344-219">Dopo aver aggiunto i commenti, non sarà più possibile modificarli.</span><span class="sxs-lookup"><span data-stu-id="cf344-219">After you add comments, you can't modify them.</span></span>
4.  <span data-ttu-id="cf344-220">Fare clic su **Aggiungi** per aggiungere commenti all'are **Cronologia commenti**.</span><span class="sxs-lookup"><span data-stu-id="cf344-220">Click **Add** to add your comments to the **Comment history** area.</span></span>





