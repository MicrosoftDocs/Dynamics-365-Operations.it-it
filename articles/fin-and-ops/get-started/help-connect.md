---
title: Collegamento alla Guida
description: In questo argomento vengono descritti i componenti della Guida per Microsoft Dynamics 365 for Finance and Operations e vengono forniti una panoramica della connessione e un riepilogo della creazione della guida personalizzata.
author: margoc
manager: AnnBe
ms.date: 09/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c0942b66859da3659be49b19986bfd146ac43130
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="connect-the-help-system"></a><span data-ttu-id="79886-103">Collegamento alla Guida</span><span class="sxs-lookup"><span data-stu-id="79886-103">Connect the Help system</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="79886-104">Vengono descritti i componenti della Guida di Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79886-104">This topic describes the components of the Help system for Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="79886-105">Viene fornita una panoramica della procedura per connettere questi componenti e un riepilogo della creazione della Guida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="79886-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span> 

## <a name="help-architecture"></a><span data-ttu-id="79886-106">Architettura della Guida</span><span class="sxs-lookup"><span data-stu-id="79886-106">Help architecture</span></span>
<span data-ttu-id="79886-107">La figura seguente mostra le parti della Guida di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79886-107">The following illustration shows the parts of the Finance and Operations Help system.</span></span> <span data-ttu-id="79886-108">Nella Guida interna al prodotto vengono visualizzati articoli dal sito di Finance and Operations all'indirizzo https://docs.microsoft.com e le guide attività archiviate nel Modellatore di processi aziendali in Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="79886-108">The in-product Help system pulls articles from the Finance and Operations site on https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span> 
> [!NOTE]
> <span data-ttu-id="79886-109">Le funzionalità elencate nel diagramma con un asterisco (\*) sono pianificate, ma non sono ancora disponibili.</span><span class="sxs-lookup"><span data-stu-id="79886-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span> <span data-ttu-id="79886-110">[![Architettura della Guida](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="79886-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>


## <a name="connecting-the-help-system"></a><span data-ttu-id="79886-111">Connessione della Guida</span><span class="sxs-lookup"><span data-stu-id="79886-111">Connecting the Help system</span></span>
> [!NOTE]
> <span data-ttu-id="79886-112">La scheda **Guide attività** non è attualmente disponibile in Microsoft Dynamics 365 for Talent e Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="79886-112">The **Task guides** tab is currently not available in Microsoft Dynamics 365 for Talent and Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="79886-113">Attualmente si lavora per abilitare questa funzionalità in una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="79886-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="79886-114">Le Guide attività nell'esperienza Attività iniziali in Talent rimangono disponibili per coprire le funzionalità di base.</span><span class="sxs-lookup"><span data-stu-id="79886-114">The Task guides in the Getting Started experience in Talent remain available to cover basic functionality.</span></span> <span data-ttu-id="79886-115">La Guida sulle procedure è inoltre disponibile nel sito docs.microsoft.com ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) per Retail e Talent.</span><span class="sxs-lookup"><span data-stu-id="79886-115">Procedural help is also available on the docs.microsoft.com site ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) for both Retail and Talent.</span></span>
 

<span data-ttu-id="79886-116">Utilizzando la pagina **Parametri di sistema**, gli amministratori di sistema collegano le parti della Guida per un'implementazione.</span><span class="sxs-lookup"><span data-stu-id="79886-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span> <span data-ttu-id="79886-117">[![Modulo Parametri di sistema con impostazioni della Guida](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Nella pagina **Parametri di sistema** effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="79886-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79886-118">La prima volta che si apre la scheda della **Guida**, è necessario connettersi a Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="79886-118">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="79886-119">Assicurarsi di fare clic sul collegamento al centro del modulo, attendere la connessione, chiudere la finestra di dialogo quindi scegliere **OK** per ottenere la pagina **Parametri di sistema**.[![Connetti a LCS](./media/connect-to-lcs-crop-1024x365.png "Connetti a LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="79886-119">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1.  <span data-ttu-id="79886-120">Selezionare il progetto Lifecycle Services a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="79886-120">Select the Lifecycle Services project to connect to.</span></span>
2.  <span data-ttu-id="79886-121">Selezionare le librerie BPM (nel progetto selezionato) da cui recuperare le registrazioni attività.</span><span class="sxs-lookup"><span data-stu-id="79886-121">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
    - <span data-ttu-id="79886-122">Per Finance and Operations, per il contenuto Microsoft, selezionare la raccolta unificata APQC più recente per Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79886-122">For Finance and Operations, for Microsoft content, select the most recent APQC Unified Library for Finance and Operations.</span></span> 
    - <span data-ttu-id="79886-123">Per Retail, una raccolta verrà rilasciata nell'immediato futuro.</span><span class="sxs-lookup"><span data-stu-id="79886-123">For Retail, we will be releasing a library in the near future.</span></span> 
    - <span data-ttu-id="79886-124">Non è necessario selezionare una raccolta per Talent, in quanto la connessione alla raccolta corretta viene stabilita per l'utente.</span><span class="sxs-lookup"><span data-stu-id="79886-124">You do not need to select a library for Talent—the connection to the correct library is established for you.</span></span> 

3.  <span data-ttu-id="79886-125">Impostare l'ordine di visualizzazione delle librerie BPM.</span><span class="sxs-lookup"><span data-stu-id="79886-125">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="79886-126">Ciò determina l'ordine in cui le registrazioni attività delle librerie verranno visualizzate nel riquadro **Guida**.</span><span class="sxs-lookup"><span data-stu-id="79886-126">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="79886-127">Dopo aver completato questi passaggi, è possibile aprire il riquadro **Guida** e fare clic sulla scheda **Guide attività**. Vengono visualizzate le guide attività applicabili alla pagina attualmente aperta in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79886-127">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you’re currently on in Finance and Operations.</span></span> <span data-ttu-id="79886-128">Se non viene trovata alcuna guida attività, è possibile immettere le parole chiave per ridefinire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="79886-128">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="79886-129">Visualizzazione delle guide attività tradotte</span><span class="sxs-lookup"><span data-stu-id="79886-129">Showing translated task guides</span></span>

<span data-ttu-id="79886-130">Le guide attività tradotte sono state fornite per la prima volta nella libreria unificata APQC di maggio 2016 e nella libreria di introduzione.</span><span class="sxs-lookup"><span data-stu-id="79886-130">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="79886-131">In Finance and Operations, per visualizzare la Guida attività localizzata, assicurarsi di essere connessi alla libreria di maggio.</span><span class="sxs-lookup"><span data-stu-id="79886-131">In Finance and Operations, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="79886-132">La lingua in cui viene visualizzata una guida attività è determinata per ogni utente dalle impostazioni di lingua in **Opzioni** &gt; **Preferenze**.</span><span class="sxs-lookup"><span data-stu-id="79886-132">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span> 

> [!NOTE]
> <span data-ttu-id="79886-133">Anche se molte guide attività sono state tradotte, al momento il client Finance and Operations non visualizza i nomi delle guide attività tradotte.</span><span class="sxs-lookup"><span data-stu-id="79886-133">Even though many task guides have been translated, right now the Finance and Operations client is not showing the translated task guide names.</span></span> <span data-ttu-id="79886-134">Inoltre, solo le guide di attività che sono state rilasciate nel mese di febbraio 2016 sono disponibili in versione tradotta nella libreria di maggio.</span><span class="sxs-lookup"><span data-stu-id="79886-134">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="79886-135">Si rilascerà una libreria aggiornata con traduzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="79886-135">We will release an updated library with additional translations.</span></span>
> -   <span data-ttu-id="79886-136">Se è stata tradotta una Guida attività, quando si apre la Guida attività tutto il testo apparirà nella lingua selezionata.</span><span class="sxs-lookup"><span data-stu-id="79886-136">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> -   <span data-ttu-id="79886-137">Se una Guida attività non è stata ancora tradotta, quando si apre solo parte del testo (quello dei controlli) apparirà nella lingua selezionata.</span><span class="sxs-lookup"><span data-stu-id="79886-137">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="79886-138">Creazione di una Guida personalizzata</span><span class="sxs-lookup"><span data-stu-id="79886-138">Creating custom help</span></span>
<span data-ttu-id="79886-139">È possibile creare la Guida personalizzata per Finance and Operations e Retail per creare registrazioni attività che riflettono l'implementazione e salvarle in una libreria di processi aziendali LCS.</span><span class="sxs-lookup"><span data-stu-id="79886-139">You can create custom help for Finance and Operations, and for Retail by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="79886-140">Non è possibile creare Guide attività personalizzate per Talent.</span><span class="sxs-lookup"><span data-stu-id="79886-140">You cannot create custom task guides for Talent.</span></span> 

<span data-ttu-id="79886-141">Per i partner, se si promuove una libreria a libreria aziendale e si include in una soluzione, sarà disponibile per i clienti.</span><span class="sxs-lookup"><span data-stu-id="79886-141">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="79886-142">È inoltre possibile effettuare una copia della libreria globale unificata APQC e quindi aprire la copia, aprire le registrazioni attività dalla copia, modificarle e salvare le registrazioni con le modifiche.</span><span class="sxs-lookup"><span data-stu-id="79886-142">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="79886-143">Per ulteriori informazioni, vedere [Come creare una registrazione attività da utilizzare come documentazione o formazione](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="79886-143">For more information, see [How to create a task recording to use as documentation or training](../../dev-itpro/user-interface/task-recorder.md).</span></span>

<a name="see-also"></a><span data-ttu-id="79886-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79886-144">See also</span></span>
--------

[<span data-ttu-id="79886-145">Panoramica della Guida</span><span class="sxs-lookup"><span data-stu-id="79886-145">Help overview</span></span>](help-overview.md)

[<span data-ttu-id="79886-146">Panoramica sulla registrazione attività</span><span class="sxs-lookup"><span data-stu-id="79886-146">Task recorder overview</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="79886-147">Come creare una registrazione di attività da utilizzare per documentazione o formazione</span><span class="sxs-lookup"><span data-stu-id="79886-147">How to create a task recording to use as documentation or training</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)





