---
title: Configurare l'area di lavoro per dispositivi mobili Gestione cespiti
description: Questo argomento descrive come configurare Microsoft Dynamics 365 Supply Chain Management e l'app per dispositivi mobili Finance and Operations (Dynamics 365) per eseguire un'area di lavoro per dispositivi mobili Gestione dispositivi che i lavoratori possono utilizzare per eseguire attività di gestione dei cespiti.
author: johanhoffmann
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9c2410c50b5d289792e2cc364674e1e093653590
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033215"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a><span data-ttu-id="2981e-103">Configurare l'area di lavoro per dispositivi mobili Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="2981e-103">Set up the Asset management mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2981e-104">Questo argomento descrive come configurare Microsoft Dynamics 365 Supply Chain Management e l'app per dispositivi mobili Finance and Operations (Dynamics 365) per eseguire un'area di lavoro per dispositivi mobili **Gestione dispositivi** che i lavoratori possono utilizzare per eseguire attività di gestione dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="2981e-104">This topic describes how to set up Microsoft Dynamics 365 Supply Chain Management and the Finance and Operations (Dynamics 365) mobile app to run an **Asset management** mobile workspace that workers can use to perform asset management tasks.</span></span>

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a><span data-ttu-id="2981e-105">Configurare gli utenti addetto alla manutenzione in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2981e-105">Set up maintenance worker users in Supply Chain Management</span></span>

<span data-ttu-id="2981e-106">Per ogni utente che richiede l'accesso all'area di lavoro per dispositivi mobili **Gestione cespiti**, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="2981e-106">For each user that requires access to the **Asset management** mobile workspace, follow these steps.</span></span>

1. <span data-ttu-id="2981e-107">In Supply Chain Management, vai a **Human resources \> Lavoratori** e assicurati che esista un record di lavoro per l'utente che desideri configurare.</span><span class="sxs-lookup"><span data-stu-id="2981e-107">In Supply Chain Management, go to **Human resources \> Workers**, and make sure that a worker record exists for the user that you want to set up.</span></span> <span data-ttu-id="2981e-108">Crea un nuovo record del lavoratore in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="2981e-108">Create a new worker record as required.</span></span>
1. <span data-ttu-id="2981e-109">Vai a **Gestione cespiti \> Imposta \> Lavoratori \> Lavoratori** e assicurati che il record del lavoratore identificato (o creato) nel passaggio precedente sia mappato a un record dell'addetto alla manutenzione.</span><span class="sxs-lookup"><span data-stu-id="2981e-109">Go to **Asset management \> Setup \> Workers \> Workers**, and make sure that the worker record that you identified (or created) in the previous step is mapped to a maintenance worker record.</span></span> <span data-ttu-id="2981e-110">Crea un nuovo record di addetto alla manutenzione come richiesto e imposta il campo **Lavoratore** su record del lavoratore dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="2981e-110">Create a new maintenance worker record as required, and set the **Worker** field to the worker record from the previous step.</span></span>
1. <span data-ttu-id="2981e-111">Vai a **Gestione cespiti \> Imposta \> Lavoratori \> gruppi Addetto alla manutenzione** e assicurati che il record di addetto alla manutenzione identificato (o creato) nel passaggio precedente appartenga a un gruppo addetto alla manutenzione.</span><span class="sxs-lookup"><span data-stu-id="2981e-111">Go to **Asset management \> Setup \> Workers \> Maintenance worker groups**, and make sure that the maintenance worker record that you identified (or created) in the previous step belongs to a maintenance worker group.</span></span>
1. <span data-ttu-id="2981e-112">Vai ad **Amministrazione sistema \> Utenti**.</span><span class="sxs-lookup"><span data-stu-id="2981e-112">Go to **System administration \> Users**.</span></span>
1. <span data-ttu-id="2981e-113">Seleziona il relativo utente nella griglia.</span><span class="sxs-lookup"><span data-stu-id="2981e-113">Select the relevant user in the grid.</span></span>
1. <span data-ttu-id="2981e-114">Nella Scheda dettaglio **Dettagli utente**, imposta il campo **Utente tipo** sull'account del lavoratore che vuoi associare all'account utente corrente.</span><span class="sxs-lookup"><span data-stu-id="2981e-114">On the **User Details** FastTab, set the **Person** field to the worker account that you want to associate with the current user account.</span></span> <span data-ttu-id="2981e-115">Questo account lavoratore dovrebbe essere il record lavoratore identificato (o creato) nel passaggio 1 e mappato a un record addetto alla manutenzione nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="2981e-115">This worker account should be the worker record that you identified (or created) in step 1 and mapped to a maintenance worker record in step 2.</span></span>

> [!NOTE]
> <span data-ttu-id="2981e-116">Le autorizzazioni utente e i ruoli di sicurezza si applicano alle funzionalità dell'area di lavoro per dispositivi mobili **Gestione cespiti** proprio come si applicano alle funzionalità dell'interfaccia utente di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2981e-116">User permissions and security roles apply to the features of the **Asset management** mobile workspace just as they apply to the features of the Supply Chain Management user interface.</span></span> <span data-ttu-id="2981e-117">Pertanto, ogni utente configurato per accedere all'area di lavoro per dispositivi mobili **Gestione cespiti** deve avere i ruoli di sicurezza necessari per eseguire operazioni simili direttamente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2981e-117">Therefore, every user that you set up to access the **Asset management** mobile workspace must have the security roles that are required to perform similar operations directly in Supply Chain Management.</span></span>

## <a name="publish-the-asset-management-mobile-workspace"></a><span data-ttu-id="2981e-118">Pubblicare l'area di lavoro per dispositivi mobili Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="2981e-118">Publish the Asset management mobile workspace</span></span>

<span data-ttu-id="2981e-119">Per rendere disponibili le funzionalità di gestione dei cespiti nell'app per dispositivi mobili Finance and Operations (Dynamics 365), devi pubblicare l'area di lavoro per dispositivi mobili **Gestione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="2981e-119">To make asset management features available in the Finance and Operations (Dynamics 365) mobile app, you must publish the **Asset management** mobile workspace.</span></span>

1. <span data-ttu-id="2981e-120">In Supply Chain Management, seleziona il pulsante **Impostazioni** (il simbolo dell'ingranaggio nell'angolo in alto a destra), quindi seleziona **App per dispositivi mobili** sul menu.</span><span class="sxs-lookup"><span data-stu-id="2981e-120">In Supply Chain Management, select the **Settings** button (the gear symbol in upper-right corner), and then select **Mobile app** on the menu.</span></span>
1. <span data-ttu-id="2981e-121">Nella finestra di dialogo **Gestisci app per dispositivi mobili**, trova il riquadro **Gestione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="2981e-121">In the **Manage mobile app** dialog box, find the **Asset Management** tile.</span></span> <span data-ttu-id="2981e-122">Se contiene il testo "Nei metadati - non pubblicato", l'area di lavoro non è stata ancora pubblicata.</span><span class="sxs-lookup"><span data-stu-id="2981e-122">If it contains the text "In metadata - not published," the workspace hasn't yet been published.</span></span> <span data-ttu-id="2981e-123">Se contiene il testo "Nei metadata - pubblicato", l'area di lavoro è già stata pubblicata e puoi saltare il resto di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="2981e-123">If it contains the text "In metadata - published," the workspace has already been published, and you can skip the rest of this procedure.</span></span>

    <span data-ttu-id="2981e-124">![Gestire la finestra di dialogo dell'app per dispositivi mobili](media/mobile-workspaces.png "Gestire la finestra di dialogo dell'app per dispositivi mobili")</span><span class="sxs-lookup"><span data-stu-id="2981e-124">![Manage mobile app dialog box](media/mobile-workspaces.png "Manage mobile app dialog box")</span></span>

1. <span data-ttu-id="2981e-125">Seleziona il riquadro **Gestione cespiti**, quindi seleziona **Pubblica** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="2981e-125">Select the **Asset Management** tile, and then select **Publish** on the toolbar.</span></span> <span data-ttu-id="2981e-126">Dopo alcuni secondi, dovresti ricevere una notifica che informa che l'area di lavoro è stata pubblicata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2981e-126">After a few seconds, you should receive a notification that states that the workspace has been successfully published.</span></span> <span data-ttu-id="2981e-127">Inoltre, il testo sul riquadro dovrebbe cambiare in "Nei metadati - pubblicato".</span><span class="sxs-lookup"><span data-stu-id="2981e-127">Additionally, the text on the tile should change to "In metadata - published."</span></span>

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a><span data-ttu-id="2981e-128">Installare e configurare l'app per dispositivi mobili Finance and Operations (Dynamics 365)</span><span class="sxs-lookup"><span data-stu-id="2981e-128">Install and set up the Finance and Operations (Dynamics 365) mobile app</span></span>

1. <span data-ttu-id="2981e-129">Vai a uno dei seguenti app store per installare l'app **Microsoft Finance and Operations (Dynamics 365)** sul tuo dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="2981e-129">Go to one of the following app stores to install the **Microsoft Finance and Operations (Dynamics 365)** app on your mobile device:</span></span>

    - [<span data-ttu-id="2981e-130">Per dispositivi Google Android</span><span class="sxs-lookup"><span data-stu-id="2981e-130">For Google Android devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
    - [<span data-ttu-id="2981e-131">Per dispositivi Apple iOS</span><span class="sxs-lookup"><span data-stu-id="2981e-131">For Apple iOS devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

1. <span data-ttu-id="2981e-132">Apri l'app Finance and Operations (Dynamics 365).</span><span class="sxs-lookup"><span data-stu-id="2981e-132">Open the Finance and Operations (Dynamics 365) app.</span></span> <span data-ttu-id="2981e-133">Dovrebbe essere visualizzata la pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="2981e-133">The sign-in page should appear.</span></span> <span data-ttu-id="2981e-134">Nel campo **Accedi**, immetti il tuo URL di Supply Chain Management o seleziona un URL recente nell'elenco **Ambienti recenti**, quindi tocca **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="2981e-134">In the **Sign in** field, enter your Supply Chain Management URL, or select a recent URL in the **Recent environments** list, and then tap **Connect**.</span></span>

    <span data-ttu-id="2981e-135">![Pagina di accesso](media/mobile-app-sign-in.png "Pagina di accesso")</span><span class="sxs-lookup"><span data-stu-id="2981e-135">![Sign-in page](media/mobile-app-sign-in.png "Sign-in page")</span></span>

1. <span data-ttu-id="2981e-136">Se viene richiesto di confermare la connessione, seleziona la casella di controllo **Ho capito**, quindi tocca **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="2981e-136">If you're prompted to confirm the connection, select the **I understand** check box, and then tap **Connect**.</span></span>
1. <span data-ttu-id="2981e-137">Nella pagina **Scegli un account**, usa il tuo account Microsoft per accedere all'applicazione per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="2981e-137">On the **Pick an account** page, use your Microsoft account to sign in to the mobile application.</span></span>

    <span data-ttu-id="2981e-138">Viene visualizzata la pagina **Aree di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="2981e-138">The **Workspaces** page appears.</span></span> <span data-ttu-id="2981e-139">Elenca ogni area di lavoro per dispositivi mobili che è stata pubblicata dall'istanza di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2981e-139">It lists every mobile workspace that has been published by your Supply Chain Management instance.</span></span>

    <span data-ttu-id="2981e-140">![Elenco delle aree di lavoro](media/mobile-app-workspaces.png "Elenco delle aree di lavoro")</span><span class="sxs-lookup"><span data-stu-id="2981e-140">![List of workspaces](media/mobile-app-workspaces.png "List of workspaces")</span></span>

1. <span data-ttu-id="2981e-141">Se è necessario modificare la persona giuridica (azienda), toccar il pulsante Menu (a volte indicato come hamburger o pulsante hamburger) nell'angolo in alto a sinistra, quindi tocca **Cambia azienda**.</span><span class="sxs-lookup"><span data-stu-id="2981e-141">If you must change the legal entity (company), tap the Menu button (sometimes referred to as the hamburger or the hamburger button) in the upper-left corner, and then tap **Change company**.</span></span>

    <span data-ttu-id="2981e-142">![Modifica della persona giuridica.](media/mobile-app-change-comp.png "Modifica della persona giuridica")</span><span class="sxs-lookup"><span data-stu-id="2981e-142">![Changing the legal entity](media/mobile-app-change-comp.png "Changing the legal entity")</span></span>

1. <span data-ttu-id="2981e-143">Nella pagina **Aree di lavoro**, seleziona l'area di lavoro con cui desideri lavorare per aprirla.</span><span class="sxs-lookup"><span data-stu-id="2981e-143">On the **Workspaces** page, select the workspace that you want to work with to open it.</span></span>

    <span data-ttu-id="2981e-144">![Area di lavoro mobile di gestione cespiti](media/mobile-app-asset-workspace.png "Area di lavoro mobile di gestione cespiti")</span><span class="sxs-lookup"><span data-stu-id="2981e-144">![Asset management mobile workspace](media/mobile-app-asset-workspace.png "Asset management mobile workspace")</span></span>

## <a name="work-with-the-asset-management-mobile-workspace"></a><span data-ttu-id="2981e-145">Utilizzare l'area di lavoro per dispositivi mobili Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="2981e-145">Work with the Asset management mobile workspace</span></span>

<span data-ttu-id="2981e-146">Per ulteriori informazioni su come lavorare con l'area di lavoro per dispositivi mobili **Gestione cespiti**, vedi [Utilizzare l'area di lavoro per dispositivi mobili per la gestione dei cespiti](asset-management-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="2981e-146">For more information about how to work with the **Asset management** mobile workspace, see [Use the Asset management mobile workspace](asset-management-mobile-workspace.md).</span></span>

<span data-ttu-id="2981e-147">Per ulteriori informazioni sull'app per dispositivi mobili Finance and Operations (Dynamics 365), vedi la [Home page dell'app per dispositivi mobili](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="2981e-147">For more information about the Finance and Operations (Dynamics 365) mobile app, see the [Mobile app home page](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span></span>
