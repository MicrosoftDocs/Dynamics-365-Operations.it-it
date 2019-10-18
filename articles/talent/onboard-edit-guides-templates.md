---
title: Modificare guide e modelli per l'inserimento in Dynamics 365 Talent - Onboard
description: In questo argomento viene descritto come aggiungere attività e altre informazioni nelle guide e nei modelli per l'inserimento in Microsoft Dynamics 365 Talent - Onboard.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
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
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7803c7cd2c58b8544d2c8dd711c295d6882f9fca
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010800"
---
# <a name="edit-onboarding-guides-and-templates"></a><span data-ttu-id="a1385-103">Modificare guide e modelli per l'inserimento</span><span class="sxs-lookup"><span data-stu-id="a1385-103">Edit onboarding guides and templates</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a1385-104">Dopo aver creato una guida o un modello per l'inserimento di nuovi assunti in Microsoft Dynamics 365 Talent: Onboard, è necessario aggiungere un'introduzione, attività, contatti e risorse.</span><span class="sxs-lookup"><span data-stu-id="a1385-104">After you create an onboarding guide or template in Microsoft Dynamics 365 Talent: Onboard, you must add an introduction, activities, contacts, and resources.</span></span> <span data-ttu-id="a1385-105">Onboard consente di includere contenuti dettagliati nelle guide per l'inserimento, tra cui:</span><span class="sxs-lookup"><span data-stu-id="a1385-105">Onboard lets you include rich content in your onboarding guides, including:</span></span>

- <span data-ttu-id="a1385-106">Video di YouTube</span><span class="sxs-lookup"><span data-stu-id="a1385-106">YouTube videos</span></span>
- <span data-ttu-id="a1385-107">Presentazioni di Microsoft Sway</span><span class="sxs-lookup"><span data-stu-id="a1385-107">Microsoft Sway presentations</span></span>
- <span data-ttu-id="a1385-108">App di Microsoft PowerApps</span><span class="sxs-lookup"><span data-stu-id="a1385-108">Microsoft PowerApps apps</span></span>
- <span data-ttu-id="a1385-109">Video di Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="a1385-109">Microsoft Stream videos</span></span>
- <span data-ttu-id="a1385-110">Moduli di Microsoft Forms</span><span class="sxs-lookup"><span data-stu-id="a1385-110">Microsoft Forms forms</span></span>
- <span data-ttu-id="a1385-111">Iframe con contenuto Web</span><span class="sxs-lookup"><span data-stu-id="a1385-111">Iframes that contains web content</span></span>

## <a name="edit-introductions-or-activities-imported-from-a-template"></a><span data-ttu-id="a1385-112">Modificare le introduzioni o le attività importate da un modello</span><span class="sxs-lookup"><span data-stu-id="a1385-112">Edit introductions or activities imported from a template</span></span>

<span data-ttu-id="a1385-113">Se si crea una guida per l'inserimento da un modello o si importano attività da un modello in un altro, si noterà un pulsante **Blocca** sulle attività importate.</span><span class="sxs-lookup"><span data-stu-id="a1385-113">If you create an onboarding guide from a template, or if you import activities from one template into another, you'll notice a **Lock** button on the imported activities.</span></span> <span data-ttu-id="a1385-114">Queste attività sono definite *attività gestite*.</span><span class="sxs-lookup"><span data-stu-id="a1385-114">These are called *managed activities*.</span></span>

<span data-ttu-id="a1385-115">[![Attività gestite](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span><span class="sxs-lookup"><span data-stu-id="a1385-115">[![Managed activities](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span></span>

<span data-ttu-id="a1385-116">Quando si seleziona un'attività gestita, è possibile vedere il modello di origine in cima all'attività.</span><span class="sxs-lookup"><span data-stu-id="a1385-116">When you select a managed activity, you can see the source template at the top of the activity.</span></span>

<span data-ttu-id="a1385-117">[![Origine di un'attività gestita](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span><span class="sxs-lookup"><span data-stu-id="a1385-117">[![Managed activity source](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span></span>

<span data-ttu-id="a1385-118">Se si modifica un'attività in un modello, Onboard distribuisce le modifiche a tutti i modelli e alle guide non ancora inviate che si basano di quel modello.</span><span class="sxs-lookup"><span data-stu-id="a1385-118">If you edit an activity in a template, Onboard will push the changes to all templates and unsent guides that are based on that template.</span></span> <span data-ttu-id="a1385-119">Se si seleziona una guida non inviata basata su un modello modificato e si seleziona la scheda **Attività** nella guida, verrà visualizzato un avviso indicante che la guida è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="a1385-119">If you select an unsent guide based on a template you edited and then select the **Activities** tab in the guide, you will see a notice that your guide has changed.</span></span> <span data-ttu-id="a1385-120">Per chiudere la notifica, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1385-120">To dismiss the notification, select **OK**.</span></span> 

<span data-ttu-id="a1385-121">[![Notifica di modifica](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span><span class="sxs-lookup"><span data-stu-id="a1385-121">[![Change notification](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span></span>

<span data-ttu-id="a1385-122">Accanto alle attività aggiornate verrà visualizzato un punto nero.</span><span class="sxs-lookup"><span data-stu-id="a1385-122">You'll see a black dot next to the updated activities.</span></span>

<span data-ttu-id="a1385-123">[![Attività modifica](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span><span class="sxs-lookup"><span data-stu-id="a1385-123">[![Changed activity](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span></span>

<span data-ttu-id="a1385-124">Non è possibile modificare attività gestite al di fuori del modello originale, eccetto per aggiungere un assegnatario, una data di scadenza o altre informazioni nella sezione di destra dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a1385-124">You can't edit managed activities outside of the original template, except to add an assignee, due date, or other information in the right-hand section of the activity.</span></span>

<span data-ttu-id="a1385-125">Se si desidera modificare un'attività gestita o se non si desidera che un'attività riceva gli aggiornamenti dal modello di origine, selezionare il pulsante **Blocca** per l'attività in questione.</span><span class="sxs-lookup"><span data-stu-id="a1385-125">If you want to edit a managed activity, or if you don't want an activity to receive updates from the template it came from, select the **Lock** button for that activity.</span></span> <span data-ttu-id="a1385-126">Il pulsante **Blocca** non verrà più visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a1385-126">The **Lock** button will disappear.</span></span> <span data-ttu-id="a1385-127">L'attività non sarà più gestita dal modello originale e non riceverà più gli aggiornamenti dal modello.</span><span class="sxs-lookup"><span data-stu-id="a1385-127">The activity will no longer be managed by the original template, and it will no longer receive updates from that template.</span></span> <span data-ttu-id="a1385-128">Gli aggiornamenti che si apportano a un'attività non influiscono sul modello originale.</span><span class="sxs-lookup"><span data-stu-id="a1385-128">Updates you make to an activity do not affect the original template.</span></span>

<span data-ttu-id="a1385-129">Se si elimina un'attività da una guida e si distribuiscono le modifiche dal modello della guida, l'attività resterà eliminata nella guida.</span><span class="sxs-lookup"><span data-stu-id="a1385-129">If you delete an activity from a guide and push changes from that guide's template, the activity will remain deleted in the guide.</span></span>

> [!NOTE]
> <span data-ttu-id="a1385-130">I contatti e le risorse non vengono gestiti dai modelli.</span><span class="sxs-lookup"><span data-stu-id="a1385-130">Contacts and resources aren't managed by templates.</span></span> <span data-ttu-id="a1385-131">Anche le sezioni non vengono gestite, pertanto se si aggiunge o si modifica una sezione in un modello, le modifiche non verranno distribuite a tutte le altre guide o agli altri modelli che utilizzano il modello modificato.</span><span class="sxs-lookup"><span data-stu-id="a1385-131">In addition, sections aren't managed, so if you add or edit a section in a template, the changes won't be pushed to any guides or templates that use that template.</span></span>
> 
> <span data-ttu-id="a1385-132">Se si aggiungono nuove attività a un modello, le nuove attività vengono distribuite alle guide e ai modelli basati su tale modello e le nuove attività vengono visualizzate nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="a1385-132">If you add new activities to a template, the new activities are pushed to guides and templates based on that template, and the new activities display at the top.</span></span>

## <a name="import-activities-from-another-template"></a><span data-ttu-id="a1385-133">Importare attività da un altro modello</span><span class="sxs-lookup"><span data-stu-id="a1385-133">Import activities from another template</span></span>

<span data-ttu-id="a1385-134">È possibile importare le attività da uno o più modelli in una guida o un modello.</span><span class="sxs-lookup"><span data-stu-id="a1385-134">You can import activities from one or more templates into a guide or template.</span></span>

1. <span data-ttu-id="a1385-135">Selezionare la guida o il modello che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="a1385-135">Select the guide or template you want to edit.</span></span>

2. <span data-ttu-id="a1385-136">Selezionare la scheda **Attività**.</span><span class="sxs-lookup"><span data-stu-id="a1385-136">Select the **Activities** tab.</span></span>

3. <span data-ttu-id="a1385-137">Selezionare la scheda **Importa** nella sezione a destra.</span><span class="sxs-lookup"><span data-stu-id="a1385-137">Select the **Import** tab in the section on the right.</span></span>

   <span data-ttu-id="a1385-138">[![Importare le attività](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span><span class="sxs-lookup"><span data-stu-id="a1385-138">[![Import activities](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span></span>

4. <span data-ttu-id="a1385-139">Per visualizzare in anteprima le attività in una nuova scheda del browser in uso, selezionare il pulsante **Apri in una nuova scheda** in un template qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="a1385-139">To preview the tasks in a new tab in your browser, select the **Open in new tab** button on any template.</span></span>

   <span data-ttu-id="a1385-140">[![Importare le attività](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span><span class="sxs-lookup"><span data-stu-id="a1385-140">[![Import activities](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span></span>

5. <span data-ttu-id="a1385-141">Trascinare il modello desiderato nella posizione nel modello della guida in cui si desidera visualizzare le attività.</span><span class="sxs-lookup"><span data-stu-id="a1385-141">Drag and drop the desired template to the place in your guide template where you want the activities to appear.</span></span> <span data-ttu-id="a1385-142">Continuare a modificare la guida o il modello.</span><span class="sxs-lookup"><span data-stu-id="a1385-142">Continue editing your guide or template.</span></span>

<span data-ttu-id="a1385-143">Le attività importate conterranno un pulsante **Blocca**, che indica che sono gestite dal modello da cui sono state importate.</span><span class="sxs-lookup"><span data-stu-id="a1385-143">The imported activities will contain a **Lock** button, which indicates those activities are managed by the template you imported from.</span></span> <span data-ttu-id="a1385-144">Quando si apportano modifiche al modello importato, verranno aggiornate le attività nel modello in cui sono state importate.</span><span class="sxs-lookup"><span data-stu-id="a1385-144">When you make changes to the template you imported, those activities will update in the template you imported them to.</span></span> <span data-ttu-id="a1385-145">Tuttavia, le modifiche non verranno distribuite automaticamente alle altre guide create dal modello originale.</span><span class="sxs-lookup"><span data-stu-id="a1385-145">However, the changes will not be pushed automatically to any guides created from the template you imported to.</span></span>

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a><span data-ttu-id="a1385-146">Distribuire le modifiche da un modello ad altri modelli o altre guide</span><span class="sxs-lookup"><span data-stu-id="a1385-146">Push changes from a template to other templates or guides</span></span>

<span data-ttu-id="a1385-147">Se si modifica un modello contenente attività utilizzate in altri modelli o altre guide, è necessario distribuire le modifiche se si desidera che vengano visualizzare negli altri modelli o nelle altre guide.</span><span class="sxs-lookup"><span data-stu-id="a1385-147">If you edit a template that contains activities that are used in other templates or guides, you must push the changes if you want them to appear in the other templates or guides.</span></span>

<span data-ttu-id="a1385-148">Se non si è certi se le attività del modello vengono utilizzate in altri modelli o guide, selezionare la scheda **Utilizzata in** per vedere dove appaiono tali attività.</span><span class="sxs-lookup"><span data-stu-id="a1385-148">If you're not sure whether your template's activities are used in other templates or guides, select the **Used in** tab to view where those activities appear.</span></span>

   <span data-ttu-id="a1385-149">[![Visualizzare le guide e i modelli in cui sono utilizzate le attività](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span><span class="sxs-lookup"><span data-stu-id="a1385-149">[![View guides and templates activities are used in](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span></span>

<span data-ttu-id="a1385-150">Per distribuire le modifiche:</span><span class="sxs-lookup"><span data-stu-id="a1385-150">To push your changes:</span></span>

1. <span data-ttu-id="a1385-151">Salvare le modifiche facendo clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a1385-151">Save your changes by selecting the **Save** button.</span></span> <span data-ttu-id="a1385-152">In caso contrario, verrà chiesto di salvare le modifiche nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="a1385-152">If you don't do this, you'll be prompted to save your changes in the next step.</span></span>

2. <span data-ttu-id="a1385-153">Selezionare **Esegui push delle modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a1385-153">Select **Push these changes**.</span></span>

   
## <a name="add-or-edit-an-introduction"></a><span data-ttu-id="a1385-154">Aggiungere o modificare un'introduzione</span><span class="sxs-lookup"><span data-stu-id="a1385-154">Add or edit an introduction</span></span>

1. <span data-ttu-id="a1385-155">Nella scheda **Introduzione**, immettere un titolo per la guida e un messaggio di apertura.</span><span class="sxs-lookup"><span data-stu-id="a1385-155">On the **Introduction** tab, enter a title for your guide and an opening message.</span></span> <span data-ttu-id="a1385-156">Per utilizzare il testo di esempio, selezionare **Usa questo messaggio**.</span><span class="sxs-lookup"><span data-stu-id="a1385-156">To use the sample text, select **Use this message**.</span></span>

    <span data-ttu-id="a1385-157">[![Scheda Introduzione in un modello di Onboard](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span><span class="sxs-lookup"><span data-stu-id="a1385-157">[![Introduction tab in an Onboard template](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span></span>

2. <span data-ttu-id="a1385-158">Utilizzare i pulsanti di formattazione per formattare i test in base alle proprie esigenze o per aggiungere immagini o collegamenti.</span><span class="sxs-lookup"><span data-stu-id="a1385-158">Use the formatting buttons to call out text as you require, or to add images or links.</span></span>
3. <span data-ttu-id="a1385-159">Selezionare **Salva** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="a1385-159">Select **Save** to save your work.</span></span>

## <a name="add-or-edit-activities"></a><span data-ttu-id="a1385-160">Aggiungere o modificare attività</span><span class="sxs-lookup"><span data-stu-id="a1385-160">Add or edit activities</span></span>

1. <span data-ttu-id="a1385-161">Nella scheda **Attività**, trascinare gli elementi da destra nell'area di modifica.</span><span class="sxs-lookup"><span data-stu-id="a1385-161">On the **Activities** tab, drag items from the right to the editing area.</span></span>
2. <span data-ttu-id="a1385-162">Per organizzare la guida in sezioni, trascinare l'elemento **Nuova sezione** nell'area di modifica e immettere un nome e una descrizione facoltativa per la sezione.</span><span class="sxs-lookup"><span data-stu-id="a1385-162">To organize your guide into sections, drag the **New section** item to the editing area, and enter a name and an optional description for the section.</span></span>

    ![[<span data-ttu-id="a1385-163">Aggiunta di una nuova sezione a una guida o a un modello per l'inserimento</span><span class="sxs-lookup"><span data-stu-id="a1385-163">Adding a new section to an onboarding guide or template</span></span>](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. <span data-ttu-id="a1385-164">Per aggiungere attività che il nuovo assunto deve completare, trascinare l'elemento **Nuova attività** nell'area di modifica, quindi immettere un nome e una descrizione per l'attività.</span><span class="sxs-lookup"><span data-stu-id="a1385-164">To add activities for your new hire to complete, drag the **New activity** item to the editing area, and enter a name and description for the activity.</span></span>

    ![[<span data-ttu-id="a1385-165">Aggiunta di una nuova attività a una guida o a un modello per l'inserimento</span><span class="sxs-lookup"><span data-stu-id="a1385-165">Adding a new activity to an onboarding guide or template</span></span>](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. <span data-ttu-id="a1385-166">Aggiungere contenuto dettagliato alla guida per l'inserimento:</span><span class="sxs-lookup"><span data-stu-id="a1385-166">Add rich content to your onboarding guide:</span></span>

    - <span data-ttu-id="a1385-167">Per aggiungere un video di YouTube, trascinare l'elemento **YouTube** nell'area di modifica, immettere un nome e una descrizione per l'attività e immettere l'URL del video di YouTube.</span><span class="sxs-lookup"><span data-stu-id="a1385-167">To add a YouTube video, drag the **YouTube** item to the editing area, enter a name and description for the activity, and enter the URL for the YouTube video.</span></span>
    - <span data-ttu-id="a1385-168">Per aggiungere una presentazione o una newsletter di Sway, trascinare l'elemento **Sway** nell'area di modifica, immettere un nome e una descrizione per l'attività, quindi immettere l'URL incorporato per la presentazione o la newsletter di Sway.</span><span class="sxs-lookup"><span data-stu-id="a1385-168">To add a Sway presentation or newsletter, drag the **Sway** item to the editing area, enter a name and description for the activity, and enter the embedded URL for the Sway presentation or newsletter.</span></span>
    - <span data-ttu-id="a1385-169">Per aggiungere un'app di PowerApps, trascinare l'elemento **PowerApps** nell'area di modifica, immettere un nome e una descrizione per l'attività, quindi selezionare l'app di PowerApps desiderata o immettere l'ID dell'app di PowerApps.</span><span class="sxs-lookup"><span data-stu-id="a1385-169">To add a PowerApps app, drag the **PowerApps** item to the editing area, enter a name and description for the activity, and either select the PowerApps app or enter the PowerApps app ID.</span></span>
    - <span data-ttu-id="a1385-170">Per aggiungere un video di Microsoft Stream, trascinare l'elemento **Microsoft Stream** nell'area di modifica, immettere un nome e una descrizione per l'attività e immettere l'URL del video di Microsoft Stream.</span><span class="sxs-lookup"><span data-stu-id="a1385-170">To add a Microsoft Stream video, drag the **Microsoft Stream** item to the editing area, enter a name and description for the activity, and enter the URL for the Microsoft Stream video.</span></span>
    - <span data-ttu-id="a1385-171">Per aggiungere un modulo di Microsoft Forms, trascinare l'elemento **Microsoft Forms** nell'area di modifica, immettere un nome e una descrizione per l'attività, immettere l'URL del modulo di Microsoft Forms e specificare le dimensioni dell'area della schermata.</span><span class="sxs-lookup"><span data-stu-id="a1385-171">To add a Microsoft Forms form, drag the **Microsoft Forms** item to the editing area, enter a name and description for the activity, enter the URL for the Microsoft Forms form, and specify the size of the screen area.</span></span>
    - <span data-ttu-id="a1385-172">Per aggiungere un iframe con contenuto Web, trascinare l'elemento **Contenuto Web (iframe)** nell'area di modifica, immettere un nome e una descrizione per l'attività, immettere l'URL del contenuto Web e specificare le dimensioni dell'area della schermata.</span><span class="sxs-lookup"><span data-stu-id="a1385-172">To add an iframe that contains web content, drag the **Web Content (iframe)** item to the editing area, enter a name and description for the activity, enter the URL for the web content, and specify the size of the screen area.</span></span>

    ![[<span data-ttu-id="a1385-173">Aggiunta di contenuto dettagliato a una guida o a un modello per l'inserimento</span><span class="sxs-lookup"><span data-stu-id="a1385-173">Adding rich content to an onboarding guide or template</span></span>](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. <span data-ttu-id="a1385-174">Facoltativo: nell'area a destra di ogni attività, assegnare l'attività a una persona o a un ruolo specifico, aggiungere una data di scadenza e un contatto e assegnare un colore per la categoria.</span><span class="sxs-lookup"><span data-stu-id="a1385-174">Optional: In the area on the right of each activity, assign the activity to a specific person or role, add a due date and contact person, and assign a category color.</span></span> <span data-ttu-id="a1385-175">Quando si assegna un'attività a una persona o a un ruolo, viene creata un'attività per ciascun individuo.</span><span class="sxs-lookup"><span data-stu-id="a1385-175">When you assign an activity to a person or role, a task is created for each individual.</span></span> <span data-ttu-id="a1385-176">Questa attività appare nel menu **Attività** in Onboard.</span><span class="sxs-lookup"><span data-stu-id="a1385-176">This task appears on the **Tasks** menu in Onboard.</span></span>

    <span data-ttu-id="a1385-177">[![Assegnare un'attività in una guida o in un modello per l'inserimento](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span><span class="sxs-lookup"><span data-stu-id="a1385-177">[![Assigning an activity in an onboarding guide or template](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span></span>

3. <span data-ttu-id="a1385-178">Selezionare **Salva** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="a1385-178">Select **Save** to save your work.</span></span>

<span data-ttu-id="a1385-179">Per eliminare un'attività o una sezione, selezionare il pulsante **Elimina** (il simbolo del cestino) nell'angolo superiore destro dell'attività o della sezione.</span><span class="sxs-lookup"><span data-stu-id="a1385-179">To delete an activity or section, select the **Delete** button (the trash can symbol) in the upper-right corner of the activity or section.</span></span>

<span data-ttu-id="a1385-180">Per ridisporre le attività e le sezioni, trascinarle in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="a1385-180">To rearrange activities and sections, drag them to a new location.</span></span>

## <a name="add-or-edit-contacts"></a><span data-ttu-id="a1385-181">Aggiungere o modificare i contatti</span><span class="sxs-lookup"><span data-stu-id="a1385-181">Add or edit contacts</span></span>

<span data-ttu-id="a1385-182">È possibile aggiungere contatti che possano essere utili al nuovo assunto nell'inserimento nell'ambiente lavorativo dal primo giorno.</span><span class="sxs-lookup"><span data-stu-id="a1385-182">You can add contact people who can help your new hire succeed from day one.</span></span> <span data-ttu-id="a1385-183">Tali contatti possono essere selezionatori, colleghi di team, altri neoassunti, mentori, amministratori e personale del supporto IT.</span><span class="sxs-lookup"><span data-stu-id="a1385-183">These contacts can be recruiters, teammates, onboarding buddies, mentors, admins, and IT support staff.</span></span>

1. <span data-ttu-id="a1385-184">Nella scheda **Contatti**, selezionare **Nuovo contatto**.</span><span class="sxs-lookup"><span data-stu-id="a1385-184">On the **Contacts** tab, select **New contact**.</span></span>
2. <span data-ttu-id="a1385-185">Nella finestra di dialogo **Aggiungi membro del team**, immettere il nome della persona o l'indirizzo e-mail, immettere una breve descrizione che indichi in che modo il contatto può aiutare il nuovo assunto, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a1385-185">In the **Add team member** dialog box, enter the contact person's name or email address, enter a short description that explains how the contact person can help the new hire, and then select **Add**.</span></span> 

    ![[<span data-ttu-id="a1385-186">Aggiunta di contatti a una guida o a un modello per l'inserimento</span><span class="sxs-lookup"><span data-stu-id="a1385-186">Adding contacts to an onboarding guide or template</span></span>](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    <span data-ttu-id="a1385-187">In alternativa, è possibile selezionare uno o più contatti in **Suggerimenti**.</span><span class="sxs-lookup"><span data-stu-id="a1385-187">Alternately, you can select one or more contacts under **Suggestions**.</span></span>

3. <span data-ttu-id="a1385-188">Selezionare **Salva** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="a1385-188">Select **Save** to save your work.</span></span>

<span data-ttu-id="a1385-189">Per eliminare un contatto, fare clic su **Elimina** (il simbolo del cestino) a destra del contatto.</span><span class="sxs-lookup"><span data-stu-id="a1385-189">To delete a contact, select the **Delete** button (the trash can symbol) to the right of the contact.</span></span>

<span data-ttu-id="a1385-190">Per modificare un contatto, fare clic su **Modifica** (il simbolo della matita) a destra del contatto.</span><span class="sxs-lookup"><span data-stu-id="a1385-190">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the contact.</span></span>

## <a name="add-or-edit-resources"></a><span data-ttu-id="a1385-191">Aggiungere o modificare le risorse</span><span class="sxs-lookup"><span data-stu-id="a1385-191">Add or edit resources</span></span>

<span data-ttu-id="a1385-192">È possibile aggiungere file, mappe e collegamenti utili nella sezione **Risorse** della guida per l'inserimento.</span><span class="sxs-lookup"><span data-stu-id="a1385-192">You can add useful files, maps, and links to the **Resources** section of your onboarding guide.</span></span>

1. <span data-ttu-id="a1385-193">Nella scheda **Risorse**, selezionare **Nuova risorsa**.</span><span class="sxs-lookup"><span data-stu-id="a1385-193">On the **Resources** tab, select **New resource**.</span></span>
2. <span data-ttu-id="a1385-194">Eseguire uno dei passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="a1385-194">Follow one of these steps:</span></span>

    - <span data-ttu-id="a1385-195">Per aggiungere un file, selezionare la scheda **File** e trascinare il file nell'area designata.</span><span class="sxs-lookup"><span data-stu-id="a1385-195">To add a file, select the **File** tab, and drag the file into the designated area.</span></span> <span data-ttu-id="a1385-196">(In alternativa, fare clic in un punto qualsiasi dell'area per cercare il file nel computer oppure selezionare **Sfoglia OneDrive**). Immettere un nome per il file e selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a1385-196">(Alternatively, click anywhere in that area to browse for the file on your computer, or select **Browse OneDrive**.) Enter a name for the file, and then select **Add**.</span></span>
    - <span data-ttu-id="a1385-197">Per aggiungere un collegamento, selezionare la scheda **Collegamento**, immettere un nome e un indirizzo per il collegamento, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a1385-197">To add a link, select the **Link** tab, enter a name and address for the link, and then select **Add**.</span></span>
    - <span data-ttu-id="a1385-198">Per aggiungere una mappa, selezionare la scheda **Mappa**, immettere un nome e un indirizzo per la mappa, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a1385-198">To add a map, select the **Map** tab, enter a name and address for the map, and then select **Add**.</span></span> <span data-ttu-id="a1385-199">Onboard includerà una mappa dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="a1385-199">Onboard will include a map of the address that you specify.</span></span>

    ![[<span data-ttu-id="a1385-200">Aggiunta di una risorsa a una guida o a un modello per l'inserimento</span><span class="sxs-lookup"><span data-stu-id="a1385-200">Adding a resource to an onboarding guide or template</span></span>](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. <span data-ttu-id="a1385-201">Selezionare **Salva** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="a1385-201">Select **Save** to save your work.</span></span>

<span data-ttu-id="a1385-202">Per eliminare una risorsa, fare clic su **Elimina** (il simbolo del cestino) a destra della risorsa.</span><span class="sxs-lookup"><span data-stu-id="a1385-202">To delete a resource, select the **Delete** button (the trash can symbol) to the right of the resource.</span></span>

<span data-ttu-id="a1385-203">Per modificare una risorsa, fare clic su **Modifica** (il simbolo della matita) a destra della risorsa.</span><span class="sxs-lookup"><span data-stu-id="a1385-203">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the resource.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a1385-204">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a1385-204">Next steps</span></span>

- [<span data-ttu-id="a1385-205">Condividere il contenuto con altri collaboratori</span><span class="sxs-lookup"><span data-stu-id="a1385-205">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="a1385-206">Visualizzare lo stato di attività e di dipendenti in fase di inserimento</span><span class="sxs-lookup"><span data-stu-id="a1385-206">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="a1385-207">Creare team di assunzione in Onboard</span><span class="sxs-lookup"><span data-stu-id="a1385-207">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="a1385-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1385-208">See also</span></span>

- [<span data-ttu-id="a1385-209">Provare o acquistare l'app Onboard</span><span class="sxs-lookup"><span data-stu-id="a1385-209">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="a1385-210">Novità</span><span class="sxs-lookup"><span data-stu-id="a1385-210">What's new</span></span>](./whats-new.md)
- [<span data-ttu-id="a1385-211">Note sulla versione</span><span class="sxs-lookup"><span data-stu-id="a1385-211">Release notes</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="a1385-212">Ottenere supporto</span><span class="sxs-lookup"><span data-stu-id="a1385-212">Get support</span></span>](./talent-support.md)
