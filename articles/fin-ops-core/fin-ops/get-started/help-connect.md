---
title: Configurare l'esperienza della Guida per le app Finance and Operations
description: Questo argomento fornisce informazioni sui componenti del sistema della Guida per alcune app Microsoft Dynamics 365.
author: margoc
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 82bb9a09e6d302b0d453ceb5131da039769b58fb
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745691"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a><span data-ttu-id="8296d-103">Configurare l'esperienza della Guida per le app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8296d-103">Configure the Help experience for Finance and Operations apps</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8296d-104">In questo argomento, troverai una panoramica dei componenti del sistema della Guida per le app Finance and Operations, come Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8296d-104">In this topic, you will find an overview of the components of the Help system for Finance and Operations apps, such as Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources.</span></span> <span data-ttu-id="8296d-105">L'argomento spiega inoltre come collegare tali componenti e fornisce un riepilogo del processo per la creazione di una Guida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8296d-105">The topic also explains how to connect these components and provides a summary of the process for creating custom Help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="8296d-106">Architettura della Guida</span><span class="sxs-lookup"><span data-stu-id="8296d-106">Help architecture</span></span>

<span data-ttu-id="8296d-107">Le app Finance and Operations includono panoramiche concettuali e altri argomenti pubblicati sul sito [https://docs.microsoft.com/dynamics365](/dynamics365/).</span><span class="sxs-lookup"><span data-stu-id="8296d-107">Finance and Operations apps include conceptual overviews and other topics that are published to the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span> <span data-ttu-id="8296d-108">È possibile accedere a questo contenuto dal riquadro della **Guida** interno al prodotto.</span><span class="sxs-lookup"><span data-stu-id="8296d-108">This content can then be accessed from the in-product **Help** pane.</span></span> <span data-ttu-id="8296d-109">La figura seguente mostra le parti della Guida.</span><span class="sxs-lookup"><span data-stu-id="8296d-109">The following illustration shows the parts of the Help system.</span></span>

<span data-ttu-id="8296d-110">[![Architettura della Guida](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="8296d-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

<span data-ttu-id="8296d-111">Il sistema della Guida interno al prodotto estrae articoli da docs.microsoft.com e altri siti Web collegati.</span><span class="sxs-lookup"><span data-stu-id="8296d-111">The in-product Help system pulls articles from docs.microsoft.com and other connected websites.</span></span> <span data-ttu-id="8296d-112">Inserisce anche le guide attività archiviate in Business process modeler (BPM) in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8296d-112">It also pulls in task guides that are stored in Business process modeler (BPM) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="adding-task-guides"></a><span data-ttu-id="8296d-113">Aggiunta di guide per le attività</span><span class="sxs-lookup"><span data-stu-id="8296d-113">Adding task guides</span></span>

> [!NOTE]
> <span data-ttu-id="8296d-114">La scheda **Guide attività** non è attualmente disponibile in Human Resources o Commerce.</span><span class="sxs-lookup"><span data-stu-id="8296d-114">The **Task guides** tab isn't currently available in Human Resources or Commerce.</span></span> <!--We are currently working to enable this functionality in a future release.--> <span data-ttu-id="8296d-115">Tuttavia, le guide attività nell'esperienza Attività iniziali in Human Resources rimangono disponibili per coprire le funzionalità di base.</span><span class="sxs-lookup"><span data-stu-id="8296d-115">However, the task guides in the Getting Started experience in Human Resources remain available to cover basic functionality.</span></span> <span data-ttu-id="8296d-116">La Guida sulle procedure è disponibile nel sito [https://docs.microsoft.com/dynamics365](/dynamics365/) per Human Resources e Commerce.</span><span class="sxs-lookup"><span data-stu-id="8296d-116">For both Human Resources and Commerce, procedural Help is available on the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span>

<span data-ttu-id="8296d-117">Nella pagina **Parametri di sistema**, gli amministratori di sistema possono configurare l'accesso alle librerie della guida attività pertinenti per un'implementazione.</span><span class="sxs-lookup"><span data-stu-id="8296d-117">On the **System parameters** page, system admins can configure access to the relevant task guide libraries for an implementation.</span></span>

> [!NOTE]
> - <span data-ttu-id="8296d-118">Per configurare la Guida, devi eseguire l'accesso utilizzando con un account nello stesso tenant di distribuzione dell'app.</span><span class="sxs-lookup"><span data-stu-id="8296d-118">To configure Help, you must sign in by using an account in the same tenant as the tenant where the app is deployed.</span></span>
> - <span data-ttu-id="8296d-119">Non è possibile connettere una libreria LCS da un'istanza dell'app in esecuzione su un'unità disco rigido virtuale (VHD) locale.</span><span class="sxs-lookup"><span data-stu-id="8296d-119">An LCS library can't be connected from an instance of the app that is running on a local virtual hard drive (VHD).</span></span>

<span data-ttu-id="8296d-120">[![Modulo Parametri di sistema con impostazioni per la Guida](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="8296d-120">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="8296d-121&quot;>Per configurare le guide attività per una soluzione, attieniti alla seguente procedura nella pagina **Parametri di sistema**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8296d-121&quot;>To configure task guides for a solution, follow these steps on the **System parameters** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id=&quot;8296d-122&quot;>La prima volta che si apre la scheda della **Guida**, è necessario connettersi a Lifecycle Services.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8296d-122&quot;>The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id=&quot;8296d-123&quot;>Assicurati di selezionare il collegamento al centro del modulo, attendi la connessione, chiudi la finestra di dialogo quindi seleziona **OK** per accedere alla pagina **Parametri di sistema**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8296d-123&quot;>Be sure to select the link in the middle of the form, wait for the connection, close the dialog box, and then select **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id=&quot;8296d-124&quot;>[![Connetti a LCS](./media/connect-to-lcs-crop-1024x365.png &quot;Connetti a LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="8296d-124">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="8296d-125">Selezionare il progetto Lifecycle Services a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8296d-125">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="8296d-126">Selezionare le librerie BPM (nel progetto selezionato) da cui recuperare le registrazioni attività.</span><span class="sxs-lookup"><span data-stu-id="8296d-126">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
3. <span data-ttu-id="8296d-127">Impostare l'ordine di visualizzazione delle librerie BPM.</span><span class="sxs-lookup"><span data-stu-id="8296d-127">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="8296d-128">L'ordine di visualizzazione definisce l'ordine in cui le registrazioni attività delle librerie verranno visualizzate nel riquadro **Guida**.</span><span class="sxs-lookup"><span data-stu-id="8296d-128">The display order defines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="8296d-129">Dopo aver completato questi passaggi, puoi aprire il riquadro **Guida** e selezionare la scheda **Guide attività**. Vengono visualizzate le guide attività applicabili alla pagina attualmente aperta nelle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8296d-129">After you complete these steps, you can open the **Help** pane and select the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations apps.</span></span> <span data-ttu-id="8296d-130">Se non viene trovata alcuna guida attività, è possibile immettere le parole chiave per ridefinire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8296d-130">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="8296d-131">Visualizzazione delle guide attività tradotte</span><span class="sxs-lookup"><span data-stu-id="8296d-131">Showing translated task guides</span></span>

<span data-ttu-id="8296d-132">Le guide attività tradotte sono state rilasciate per la prima volta nella libreria unificata APQC di maggio 2016 e nella libreria di introduzione.</span><span class="sxs-lookup"><span data-stu-id="8296d-132">Translated task guides were first released in the May 2016 APQC Unified Library and in the Getting Started library.</span></span> <span data-ttu-id="8296d-133">Per visualizzare la Guida della guida attività localizzata, assicurati che la tua soluzione Dynamics 365 sia connessa alla libreria di maggio 2016.</span><span class="sxs-lookup"><span data-stu-id="8296d-133">To view localized task guide Help, make sure that your Dynamics 365 solution is connected to the May 2016 library.</span></span> <span data-ttu-id="8296d-134">Gli utenti possono modificare la lingua in cui viene visualizzata una guida attività modificando le impostazioni relative alla lingua in **Opzioni** &gt; **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="8296d-134">Users can change the language that a task guide appears in by changing the language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="8296d-135">Sebbene molte guide attività sono state tradotte, al momento il client non visualizza i nomi delle guide attività tradotte.</span><span class="sxs-lookup"><span data-stu-id="8296d-135">Although many task guides have been translated, the client doesn't currently show the translated task guide names.</span></span> <span data-ttu-id="8296d-136">Inoltre, solo le guide di attività che sono state rilasciate nel mese di febbraio 2016 sono disponibili in versione tradotta nella libreria di maggio 2016.</span><span class="sxs-lookup"><span data-stu-id="8296d-136">Additionally, in the May 2016 library, translations are available only for the task guides that were released in February 2016.</span></span> <span data-ttu-id="8296d-137">Microsoft rilascerà una libreria aggiornata con traduzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="8296d-137">Microsoft will release an updated library that includes additional translations.</span></span>
>
> - <span data-ttu-id="8296d-138">Se è stata tradotta una Guida attività, quando si apre la Guida attività tutto il testo apparirà nella lingua selezionata.</span><span class="sxs-lookup"><span data-stu-id="8296d-138">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="8296d-139">Se una Guida attività non è stata ancora tradotta, quando si apre solo parte del testo (quello dei controlli) apparirà nella lingua selezionata.</span><span class="sxs-lookup"><span data-stu-id="8296d-139">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="adding-custom-help"></a><span data-ttu-id="8296d-140">Aggiunta della Guida personalizzata</span><span class="sxs-lookup"><span data-stu-id="8296d-140">Adding custom Help</span></span>

<span data-ttu-id="8296d-141">Puoi utilizzare guide attività per creare una Guida personalizzata oppure puoi collegare un sito Web della Guida personalizzata al riquadro **Guida**.</span><span class="sxs-lookup"><span data-stu-id="8296d-141">You can use task guides to create custom Help, or you can connect a custom Help website to the **Help** pane.</span></span>

### <a name="create-custom-help-by-using-task-guides"></a><span data-ttu-id="8296d-142">Creare una Guida personalizzata con guide attività</span><span class="sxs-lookup"><span data-stu-id="8296d-142">Create custom Help by using task guides</span></span>

<span data-ttu-id="8296d-143">Puoi creare la Guida personalizzata per le app supportate creando registrazioni attività che riflettono l'implementazione e salvarle in una libreria di processi aziendali in LCS successivamente.</span><span class="sxs-lookup"><span data-stu-id="8296d-143">You can create custom Help for the supported apps by creating task recordings that reflect your implementation and then saving them to a Business process library in LCS.</span></span> <span data-ttu-id="8296d-144">Non è possibile creare guide attività personalizzate per Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8296d-144">You can't create custom task guides for Human Resources.</span></span>

<span data-ttu-id="8296d-145">Per i partner, se promuovi una libreria a libreria aziendale e la includi in una soluzione, sarà disponibile per i clienti.</span><span class="sxs-lookup"><span data-stu-id="8296d-145">If you're a partner, and you promote a library to a corporate library and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="8296d-146">Puoi inoltre effettuare una copia della libreria globale unificata APQC e quindi aprire i file di Registrazione attività nella copia, modificarli e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8296d-146">You can also make a copy of the APQC Unified Library, and then open the task recordings in the copy, edit them, and save your changes.</span></span> <span data-ttu-id="8296d-147">Per ulteriori informazioni, vedere [Risorse registrazione attività](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="8296d-147">For more information, see [Task recorder resources](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-help-site"></a><span data-ttu-id="8296d-148">Collega un sito della Guida personalizzato</span><span class="sxs-lookup"><span data-stu-id="8296d-148">Connect a custom Help site</span></span>

<span data-ttu-id="8296d-149">Le app Finance and Operations vengono utilizzate raramente nella loro forma predefinita.</span><span class="sxs-lookup"><span data-stu-id="8296d-149">Finance and Operations apps are rarely used in their out-of-box form.</span></span> <span data-ttu-id="8296d-150">Invece, la soluzione è personalizzata ed estesa per soddisfare le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8296d-150">Instead, the solution is customized and extended to fit the organization's needs.</span></span> <span data-ttu-id="8296d-151">È inoltre possibile personalizzare ed estendere l'esperienza della Guida.</span><span class="sxs-lookup"><span data-stu-id="8296d-151">You can also customize and extend the Help experience.</span></span> <span data-ttu-id="8296d-152">Ad esempio, puoi aggiungere una Guida personalizzata al riquadro interno **Guida** del prodotto.</span><span class="sxs-lookup"><span data-stu-id="8296d-152">For example, you can add custom Help to the in-product **Help** pane.</span></span>

<span data-ttu-id="8296d-153">Microsoft ha fornito un toolkit per aiutarti a distribuire e connettere la Guida personalizzata al riquadro **Guida**.</span><span class="sxs-lookup"><span data-stu-id="8296d-153">Microsoft has provided a toolkit to help you deploy and connect custom Help to the **Help** pane.</span></span> <span data-ttu-id="8296d-154">Per informazioni su come impostare una soluzione della Guida personalizzata connessa al riquadro **Guida**, vedi [Panoramica della Guida personalizzata](../../dev-itpro/help/custom-help-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8296d-154">For information about how you can set up a custom Help solution that is connected to the **Help** pane, see [Custom Help overview](../../dev-itpro/help/custom-help-overview.md).</span></span>

<span data-ttu-id="8296d-155">Se desideri collaborare con Microsoft su strumenti e processi per la personalizzazione della Guida, compila il modulo all'indirizzo [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span><span class="sxs-lookup"><span data-stu-id="8296d-155">If you want to collaborate with Microsoft on tools and processes for customizing Help, fill in the form at [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span></span>

## <a name="see-also"></a><span data-ttu-id="8296d-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8296d-156">See also</span></span>

[<span data-ttu-id="8296d-157">Guida</span><span class="sxs-lookup"><span data-stu-id="8296d-157">Help system</span></span>](help-overview.md)  
[<span data-ttu-id="8296d-158">Panoramica della Guida personalizzata</span><span class="sxs-lookup"><span data-stu-id="8296d-158">Custom Help overview</span></span>](../../dev-itpro/help/custom-help-overview.md)  
[<span data-ttu-id="8296d-159">Risorse registrazione attività</span><span class="sxs-lookup"><span data-stu-id="8296d-159">Task recorder resources</span></span>](../../dev-itpro/user-interface/task-recorder.md)  
[<span data-ttu-id="8296d-160">Creare la documentazione o la formazione con Registrazione attività</span><span class="sxs-lookup"><span data-stu-id="8296d-160">Create documentation or training with Task Recorder</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[<span data-ttu-id="8296d-161">Archivio GitHub per una Guida personalizzata</span><span class="sxs-lookup"><span data-stu-id="8296d-161">Custom Help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]