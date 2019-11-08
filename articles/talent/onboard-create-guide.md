---
title: Creare e inviare una guida per l'inserimento utilizzando Dynamics 365 Talent - Onboard
description: In questo argomento viene illustrato come utilizzare l'app Microsoft Dynamics 365 Talent - Onboard per creare una guida per l'inserimento dei neoassunti. Questa attività è un primo passaggio fondamentale della strategia di gestione del capitale umano (HCM).
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 3c465c667cbb8a66f301637ca620429b0ddc11c6
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550345"
---
# <a name="create-and-send-an-onboarding-guide-by-using-dynamics-365-talent---onboard"></a><span data-ttu-id="c7c92-104">Creare e inviare una guida per l'inserimento utilizzando Dynamics 365 Talent - Onboard</span><span class="sxs-lookup"><span data-stu-id="c7c92-104">Create and send an onboarding guide by using Dynamics 365 Talent - Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c7c92-105">Microsoft Dynamics 365 Talent: Onboard consente di creare guide per l'inserimento da modelli che si possono creare personalmente, da modelli disponibili in una raccolta o creati da zero.</span><span class="sxs-lookup"><span data-stu-id="c7c92-105">Microsoft Dynamics 365 Talent: Onboard lets you create onboarding guides from templates that you created yourself, from templates that are available in a gallery, or from scratch.</span></span>

<span data-ttu-id="c7c92-106">Dopo aver creato una guida per l'inserimento è possibile inviarla a un nuovo assunto.</span><span class="sxs-lookup"><span data-stu-id="c7c92-106">After you've created an onboarding guide, you can send it to a new hire.</span></span> <span data-ttu-id="c7c92-107">In alternativa, è possibile inviarla a più neoassunti specificati in un file di Microsoft Excel che si scarica dall'app Onboard.</span><span class="sxs-lookup"><span data-stu-id="c7c92-107">Alternatively, you can send it to multiple new hires that you specify in a Microsoft Excel file that you download from the Onboard app.</span></span>

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-a-single-new-hire"></a><span data-ttu-id="c7c92-108">Creare una guida per l'inserimento da un modello e inviarla a un nuovo assunto</span><span class="sxs-lookup"><span data-stu-id="c7c92-108">Create an onboarding guide from a template and send it to a single new hire</span></span>

1. <span data-ttu-id="c7c92-109">Nel menu a sinistra, selezionare **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-109">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="c7c92-110">In **Modelli personali**, selezionare il modello che si desidera impostare come guida di inserimento per il nuovo assunto.</span><span class="sxs-lookup"><span data-stu-id="c7c92-110">Under **My templates**, select the template that you want to set up as an onboarding guide for the new hire.</span></span>
3. <span data-ttu-id="c7c92-111">Modificare il modello in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c7c92-111">Edit the template as you desire.</span></span> <span data-ttu-id="c7c92-112">Ricordarsi di salvare il lavoro di tanto in tanto.</span><span class="sxs-lookup"><span data-stu-id="c7c92-112">Be sure to save your work as you go.</span></span>
4. <span data-ttu-id="c7c92-113">Dopo aver modificato il modello, selezionare **Crea guida**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-113">When you've finished editing the template, select **Create guide**.</span></span>

    <span data-ttu-id="c7c92-114">[![Creazione di una guida per l'inserimento da un modello](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)</span><span class="sxs-lookup"><span data-stu-id="c7c92-114">[![Creating an onboarding guide from a template](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)</span></span>

5. <span data-ttu-id="c7c92-115">Nella finestra **Crea guida**, in **A chi è destinato l'onboarding**, immettere il nome o l'indirizzo di posta elettronica del nuovo assunto.</span><span class="sxs-lookup"><span data-stu-id="c7c92-115">In the **Create a guide** window, under **Who are you onboarding**, enter the new hire's name or email address.</span></span> <span data-ttu-id="c7c92-116">Se il nuovo assunto non è ancora presente nel sistema, selezionare **Aggiungi ora** e immettere le informazioni del dipendente.</span><span class="sxs-lookup"><span data-stu-id="c7c92-116">If the new hire isn't in the system yet, select **Add now**, and enter the employee's information.</span></span>

    ![[<span data-ttu-id="c7c92-117">Inserimento delle informazioni per la guida per l'inserimento</span><span class="sxs-lookup"><span data-stu-id="c7c92-117">Entering information for the onboarding guide</span></span>](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

6. <span data-ttu-id="c7c92-118">In **Quando devono iniziare**, selezionare una data di inizio.</span><span class="sxs-lookup"><span data-stu-id="c7c92-118">Under **When do they start**, select a start date.</span></span>
7. <span data-ttu-id="c7c92-119">Se la guida per l'inserimento deve essere inviata automaticamente al nuovo assunto in una data specifica, assicurarsi che l'opzione **Programma una data di invio automatica** sia attivata e quindi selezionare la data di invio automatica.</span><span class="sxs-lookup"><span data-stu-id="c7c92-119">If the onboarding guide should be sent automatically to the new hire on a specific date, make sure that the **Schedule an automatic send date** option is turned on, and then select the automatic send date.</span></span> <span data-ttu-id="c7c92-120">Per inviare la guida immediatamente, disattivare l'opzione **Programma una data di invio automatica**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-120">To send the guide immediately, turn off the **Schedule an automatic send date** option.</span></span>
8. <span data-ttu-id="c7c92-121">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-121">Select **Done**.</span></span>
9. <span data-ttu-id="c7c92-122">Al termine della modifica della guida per l'inserimento, selezionare **Invia** nell'angolo superiore destro.</span><span class="sxs-lookup"><span data-stu-id="c7c92-122">When you've finished editing the onboarding guide, select **Send** in the upper-right corner.</span></span> <span data-ttu-id="c7c92-123">Eseguire quindi uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7c92-123">Then follow one of these steps:</span></span>

    - <span data-ttu-id="c7c92-124">Per inviare al nuovo assunto un collegamento alla guida per l'inserimento, selezionare **copia un link** e selezionare **Copia**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-124">To send the new hire a link to the onboarding guide, select **copy a link**, and then select **Copy**.</span></span>
    - <span data-ttu-id="c7c92-125">Per personalizzare l'e-mail per la guida per l'inserimento prima di inviarla, selezionare **Personalizzare il messaggio di posta elettronica prima di inviare**, selezionare **Avanti**, personalizzare il messaggio in base alle proprie esigenze e quindi selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-125">To customize the email for the onboarding guide before you send it, select **Customize the email before sending**, select **Next**, customize the email as you desire, and then select **Send**.</span></span>
    - <span data-ttu-id="c7c92-126">Per inviare l'e-mail senza personalizzarlo, selezionare **Avanti**, quindi selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-126">To send the email without customizing it, select **Next**, and then select **Send**.</span></span>

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-multiple-new-hires"></a><span data-ttu-id="c7c92-127">Creare una guida per l'inserimento da un modello e inviarla a più nuovi assunti</span><span class="sxs-lookup"><span data-stu-id="c7c92-127">Create an onboarding guide from a template and send it to multiple new hires</span></span>

<span data-ttu-id="c7c92-128">Onboard consente di inviare una guida per l'inserimento a più nuovi assunti nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="c7c92-128">Onboard lets you send an onboarding guide to multiple new hires at the same time.</span></span>

1. <span data-ttu-id="c7c92-129">Nel menu a sinistra, selezionare **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-129">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="c7c92-130">In **Modelli personali**, selezionare il modello che si desidera impostare come guida di inserimento per i nuovi assunti.</span><span class="sxs-lookup"><span data-stu-id="c7c92-130">Under **My templates**, select the template that you want to set up as an onboarding guide for the new hires.</span></span>
3. <span data-ttu-id="c7c92-131">Modificare il modello in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c7c92-131">Edit the template as you desire.</span></span> <span data-ttu-id="c7c92-132">Ricordarsi di salvare il lavoro di tanto in tanto.</span><span class="sxs-lookup"><span data-stu-id="c7c92-132">Be sure to save your work as you go.</span></span>
4. <span data-ttu-id="c7c92-133">Dopo aver modificato il modello, selezionare **Crea guida**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-133">When you've finished editing the template, select **Create guide**.</span></span>
5. <span data-ttu-id="c7c92-134">Nella finestra **Crea una guida** selezionare **È necessario effettuare l'onboarding di più utenti contemporaneamente**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-134">In the **Create a guide** window, select **Need to onboard multiple people at once**.</span></span>

    <span data-ttu-id="c7c92-135">[![Creazione di una guida per l'inserimento per più nuovi assunti](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)</span><span class="sxs-lookup"><span data-stu-id="c7c92-135">[![Creating an onboarding guide for multiple new hires](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)</span></span>

6. <span data-ttu-id="c7c92-136">Selezionare **modello della nuova assunzione**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-136">Select **new hire template**.</span></span>
7. <span data-ttu-id="c7c92-137">Dopo aver scaricato il file con estensione xlsx, selezionare **Apri**, immettere le informazioni sui dipendenti nella cartella di Excel e salvare e salvare la cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c7c92-137">After the .xlsx file is downloaded, select **Open**, enter the employees' information in the Excel workbook, and save the workbook.</span></span>

    <span data-ttu-id="c7c92-138">[![Scaricamento del modello di Excel per l'invio della guida per l'inserimento a più nuovi assunti](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)</span><span class="sxs-lookup"><span data-stu-id="c7c92-138">[![Downloading the Excel template for sending the onboarding guide to multiple new hires](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7c92-139">Prima di poter modificare la cartella di lavoro, è necessario selezionare **Abilita modifica** in Excel.</span><span class="sxs-lookup"><span data-stu-id="c7c92-139">Before you can edit the workbook, you must select **Enable editing** in Excel.</span></span>
    > 
    > <span data-ttu-id="c7c92-140">[![Attivazione della funzione di modifica](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)</span><span class="sxs-lookup"><span data-stu-id="c7c92-140">[![Enabling editing](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)</span></span>

8. <span data-ttu-id="c7c92-141">Trascinare la cartella di lavoro di Excel nell'area designata nella finestra **Crea più guide** oppure fare clic in un punto qualsiasi nell'area per cercare il file nel computer.</span><span class="sxs-lookup"><span data-stu-id="c7c92-141">Drag the Excel workbook to the designated area in the **Create multiple guides** window, or click anywhere in that area to browse for the file on your computer.</span></span>

    <span data-ttu-id="c7c92-142">[![Trascinamento della cartella di lavoro modificata](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)</span><span class="sxs-lookup"><span data-stu-id="c7c92-142">[![Dragging the edited workbook](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)</span></span>

9. <span data-ttu-id="c7c92-143">Al termine della modifica della guida per l'inserimento, selezionare **Invia** nell'angolo superiore destro.</span><span class="sxs-lookup"><span data-stu-id="c7c92-143">When you've finished editing the onboarding guide, select **Send** in the upper-right corner.</span></span> <span data-ttu-id="c7c92-144">Eseguire quindi uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7c92-144">Then follow one of these steps:</span></span>

    - <span data-ttu-id="c7c92-145">Per inviare ai nuovi assunti un collegamento alla guida per l'inserimento, selezionare **copia un link** e selezionare **Copia**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-145">To send the new hires a link to the onboarding guide, select **copy a link**, and then select **Copy**.</span></span>
    - <span data-ttu-id="c7c92-146">Per personalizzare l'e-mail per la guida per l'inserimento prima di inviarla, selezionare **Personalizzare il messaggio di posta elettronica prima di inviare**, selezionare **Avanti**, personalizzare il messaggio in base alle proprie esigenze e quindi selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-146">To customize the email for the onboarding guide before you send it, select **Customize the email before sending**, select **Next**, customize the email as you desire, and then select **Send**.</span></span>
    - <span data-ttu-id="c7c92-147">Per inviare l'e-mail senza personalizzarlo, selezionare **Avanti**, quindi selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-147">To send the email without customizing it, select **Next**, and then select **Send**.</span></span>

## <a name="create-a-guide-without-using-a-template"></a><span data-ttu-id="c7c92-148">Creare una guida senza utilizzare un modello</span><span class="sxs-lookup"><span data-stu-id="c7c92-148">Create a guide without using a template</span></span>

<span data-ttu-id="c7c92-149">Non è necessario creare una guida sempre da un modello.</span><span class="sxs-lookup"><span data-stu-id="c7c92-149">You don't always have to create a guide from a template.</span></span> <span data-ttu-id="c7c92-150">Se si preferisce, è possibile crearla da zero.</span><span class="sxs-lookup"><span data-stu-id="c7c92-150">If you prefer, you can create a guide from scratch instead.</span></span>

1. <span data-ttu-id="c7c92-151">Nel menu a sinistra, selezionare **Guides** e quindi selezionare il pulsante **Aggiunti** (il segno più \[**+**\]).</span><span class="sxs-lookup"><span data-stu-id="c7c92-151">On the left menu, select **Guides**, and then select the **Add** button (the plus sign \[**+**\]).</span></span>
2. <span data-ttu-id="c7c92-152">Nella finestra **Crea guida**, in **A chi è destinato l'onboarding**, immettere il nome o l'indirizzo di posta elettronica del nuovo assunto.</span><span class="sxs-lookup"><span data-stu-id="c7c92-152">In the **Create a guide** window, under **Who are you onboarding**, enter the new hire's name or email address.</span></span> <span data-ttu-id="c7c92-153">Se il nuovo assunto non è ancora presente nel sistema, selezionare **Aggiungi ora** e immettere le informazioni del dipendente.</span><span class="sxs-lookup"><span data-stu-id="c7c92-153">If the new hire isn't in the system yet, select **Add now**, and enter the employee's information.</span></span>

    ![[<span data-ttu-id="c7c92-154">Inserimento delle informazioni per la guida per l'inserimento</span><span class="sxs-lookup"><span data-stu-id="c7c92-154">Entering information for the onboarding guide</span></span>](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

3. <span data-ttu-id="c7c92-155">In **Quando devono iniziare**, selezionare una data di inizio.</span><span class="sxs-lookup"><span data-stu-id="c7c92-155">Under **When do they start**, select a start date.</span></span>
4. <span data-ttu-id="c7c92-156">Se la guida per l'inserimento deve essere inviata automaticamente al nuovo assunto in una data specifica, assicurarsi che l'opzione **Programma una data di invio automatica** sia attivata e quindi selezionare la data di invio automatica.</span><span class="sxs-lookup"><span data-stu-id="c7c92-156">If the onboarding guide should be sent automatically to the new hire on a specific date, make sure that the **Schedule an automatic send date** option is turned on, and then select the automatic send date.</span></span> <span data-ttu-id="c7c92-157">Per inviare la guida immediatamente, disattivare l'opzione **Programma una data di invio automatica**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-157">To send the guide immediately, turn off the **Schedule an automatic send date** option.</span></span>
5. <span data-ttu-id="c7c92-158">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-158">Select **Done**.</span></span>

## <a name="save-a-guide-as-a-template"></a><span data-ttu-id="c7c92-159">Salvare una guida come modello</span><span class="sxs-lookup"><span data-stu-id="c7c92-159">Save a guide as a template</span></span>

<span data-ttu-id="c7c92-160">È possibile salvare una guida per l'inserimento come modello.</span><span class="sxs-lookup"><span data-stu-id="c7c92-160">You can save an onboarding guide as a template.</span></span> <span data-ttu-id="c7c92-161">In questo modo, è possibile risparmiare tempo quando si devono creare più guide.</span><span class="sxs-lookup"><span data-stu-id="c7c92-161">In this way, you can save time when you must create more onboarding guides later.</span></span>

1. <span data-ttu-id="c7c92-162">Nel menu a sinistra, selezionare **Guides**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-162">On the left menu, select **Guides**.</span></span>
2. <span data-ttu-id="c7c92-163">Selezionare il pulsante **Altro** (punti di sospensione \[**...**\]) per la guida da cui si desidera creare un modello, quindi selezionare **Salva come modello**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-163">Select the **More** button (the ellipsis \[**...**\]) for the guide that you want to create a template from, and then select **Save as template**.</span></span>

    ![[<span data-ttu-id="c7c92-164">Salvataggio di una guida per l'inserimento come modello</span><span class="sxs-lookup"><span data-stu-id="c7c92-164">Saving an onboarding guide as a template</span></span>](./media/onboard-save-guide-as-template.png)](./media/onboard-save-guide-as-template.png)

3. <span data-ttu-id="c7c92-165">Nella finestra **Salva come nuovo modello**, immettere un nome per il nuovo modello e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c7c92-165">In the **Save as a new template** window, enter a name for your new template, and then select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c7c92-166">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c7c92-166">Next steps</span></span>

- [<span data-ttu-id="c7c92-167">Modificare guide e modelli per l'inserimento</span><span class="sxs-lookup"><span data-stu-id="c7c92-167">Edit onboarding guides and templates</span></span>](./onboard-edit-guides-templates.md)
- [<span data-ttu-id="c7c92-168">Condividere il contenuto con altri collaboratori</span><span class="sxs-lookup"><span data-stu-id="c7c92-168">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="c7c92-169">Visualizzare lo stato di attività e di dipendenti in fase di inserimento</span><span class="sxs-lookup"><span data-stu-id="c7c92-169">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="c7c92-170">Creare team di assunzione in Onboard</span><span class="sxs-lookup"><span data-stu-id="c7c92-170">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="c7c92-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7c92-171">See also</span></span>

- [<span data-ttu-id="c7c92-172">Provare o acquistare l'app Onboard</span><span class="sxs-lookup"><span data-stu-id="c7c92-172">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="c7c92-173">Novità</span><span class="sxs-lookup"><span data-stu-id="c7c92-173">What's new</span></span>](./whats-new.md)
- [<span data-ttu-id="c7c92-174">Note sulla versione</span><span class="sxs-lookup"><span data-stu-id="c7c92-174">Release notes</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="c7c92-175">Ottenere supporto</span><span class="sxs-lookup"><span data-stu-id="c7c92-175">Get support</span></span>](./talent-support.md)
