---
title: Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione
description: Questo argomento spiega come utilizzare Microsoft Regulatory Configuration Services (RCS) e il repository globale per creare e utlizzare le funzionalità di globalizzazione.
author: JaneA07
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: ae46dab5250fbe8096f43e420cb7ef33a5862af0
ms.sourcegitcommit: 97206552616b248f88e516fea08b3f059257e8d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3432049"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a><span data-ttu-id="57d62-103">Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione</span><span class="sxs-lookup"><span data-stu-id="57d62-103">Regulatory Configuration Services (RCS) - Globalization features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57d62-104">È possibile utilizzare Microsoft Regulatory Configuration Services (RCS) per creare una funzionalità di globalizzazione che può essere utilizzata nei servizi di globalizzazione, ad esempio un servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="57d62-104">You can use Microsoft Regulatory Configuration Services (RCS) to create a Globalization feature that can be used in Globalization services, such as an e-invoicing service.</span></span> <span data-ttu-id="57d62-105">RCS consente di eseguire queste attività:</span><span class="sxs-lookup"><span data-stu-id="57d62-105">RCS lets you perform these tasks:</span></span>

- <span data-ttu-id="57d62-106">Definire i componenti correlati di una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-106">Define related components of a feature.</span></span>
- <span data-ttu-id="57d62-107">Gestire il ciclo di vita delle funzionalità attraverso lo stato delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-107">Manage the feature lifecycle through a feature's status.</span></span>
- <span data-ttu-id="57d62-108">Rendere disponibile una funzionalità per ambienti definiti.</span><span class="sxs-lookup"><span data-stu-id="57d62-108">Make a feature available for defined environments.</span></span>
- <span data-ttu-id="57d62-109">Condividere una funzionalità con altre organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="57d62-109">Share a feature with other organizations.</span></span>

<span data-ttu-id="57d62-110">Le seguenti procedure spiegano come un utente in RCS può aggiungere una funzione di globalizzazione e i relativi componenti, aggiornare lo stato della funzionalità e renderla disponibile di modo che possa essere utilizzata nei servizi di globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="57d62-110">The following procedures explain how a user in RCS can add a Globalization feature and related components, update the feature's status, and make the feature available so that it can be used in Globalization services.</span></span>

<span data-ttu-id="57d62-111">Prima di completare le procedure, è necessario completare i passaggi correlati alle seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="57d62-111">Before you complete the procedures, you must complete the steps that are related to the following tasks:</span></span>

- <span data-ttu-id="57d62-112">Accesso a un'istanza RCS.</span><span class="sxs-lookup"><span data-stu-id="57d62-112">Accessing an RCS instance.</span></span>
- <span data-ttu-id="57d62-113">Creazione e attivazione di un provider di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="57d62-113">Creating and activating a configuration provider.</span></span> <span data-ttu-id="57d62-114">Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="57d62-114">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="57d62-115">Nell'istanza delle app Finance and Operations, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="57d62-115">In your Finance and Operations apps instance, follow these steps.</span></span>

1. <span data-ttu-id="57d62-116">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="57d62-116">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="57d62-117">Se non è stato effettuato il provisioning di alcun ambiente RCS per la società, selezionare **Regulatory services - Configurazione** e seguire le istruzioni per il provisioning di un ambiente.</span><span class="sxs-lookup"><span data-stu-id="57d62-117">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration**, and follow the instructions to provision one.</span></span>

> [!NOTE]
> <span data-ttu-id="57d62-118">Se è già stato eseguito il provisioning di un ambiente RCS per la società, utilizzare l'URL della pagina per accedere all'ambiente selezionando l'opzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="57d62-118">If an RCS environment has already been provisioned for your company, use the page URL to access the environment by selecting the sign-in option.</span></span>

## <a name="turn-on-the-globalization-features"></a><span data-ttu-id="57d62-119">Attivare le funzionalità di globalizzazione</span><span class="sxs-lookup"><span data-stu-id="57d62-119">Turn on the Globalization features</span></span>

1. <span data-ttu-id="57d62-120">Nell'istanza RCS, selezionare il riquadro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="57d62-120">In your RCS instance, select the **Feature management** tile.</span></span>
2. <span data-ttu-id="57d62-121">Nell'area di lavoro **Gestione funzionalità**, selezionare **Funzionalità di globalizzazione** nell'elenco, quindi selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="57d62-121">In the **Feature management** workspace, select **Globalization features** in the list, and then select **Enable now**.</span></span>

    ![Funzionalità di globalizzazione in Gestione funzionalità](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a><span data-ttu-id="57d62-123">Funzionalità di globalizzazione</span><span class="sxs-lookup"><span data-stu-id="57d62-123">Globalization features</span></span>

<span data-ttu-id="57d62-124">Per utilizzare una funzionalità di globalizzazione, è necessario innanzitutto importarla dal repository globale e crearne una versione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="57d62-124">To use a Globalization feature, you must first import it from the the Global repository and create your own version of it.</span></span> <span data-ttu-id="57d62-125">Esistono due modi per aggiungere funzionalità di globalizzazione:</span><span class="sxs-lookup"><span data-stu-id="57d62-125">There are two ways to add Globalization features:</span></span>

- <span data-ttu-id="57d62-126">Aggiungendo una funzionalità derivata basata su una funzionalità esistente che è stata pubblicata o condivisa.</span><span class="sxs-lookup"><span data-stu-id="57d62-126">Add a derived feature that is based on an existing feature that has been published or shared.</span></span>
- <span data-ttu-id="57d62-127">Aggiungendo una nuova funzionalità creata da zero.</span><span class="sxs-lookup"><span data-stu-id="57d62-127">Add a new feature that you've created from scratch.</span></span>

## <a name="access-globalization-features"></a><span data-ttu-id="57d62-128">Accedere alle funzionalità di globalizzazione</span><span class="sxs-lookup"><span data-stu-id="57d62-128">Access Globalization features</span></span>

1. <span data-ttu-id="57d62-129">Assicurarsi che **Funzionalità di globalizzazione** sia attivata in Gestione funzionalità, come descritto in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="57d62-129">Make sure that the **Globalization features** feature is turned on in Feature management, as described earlier in this topic.</span></span>
2. <span data-ttu-id="57d62-130">Aprire la nuova area di lavoro **Funzionalità di globalizzazione** e quindi sotto **Funzionalità**, selezionare il riquadro **Fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="57d62-130">Open the new **Globalization Features** workspace, and then, under **Features**, select the **e-Invoicing** tile.</span></span>

    ![Area di lavoro Funzionalità di globalizzazione](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    <span data-ttu-id="57d62-132">Viene aperta la pagina **Funzionalità di fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="57d62-132">The **e-Invoicing Features** page is opened.</span></span>

    ![Pagina Funzioni di fatturazione elettronica](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a><span data-ttu-id="57d62-134">Aggiungere una funzionalità di globalizzazione derivata</span><span class="sxs-lookup"><span data-stu-id="57d62-134">Add a derived Globalization feature</span></span>

<span data-ttu-id="57d62-135">È possibile aggiungere una nuova funzionalità di globalizzazione derivandola da una funzionalità esistente che è stata pubblicata o condivisa.</span><span class="sxs-lookup"><span data-stu-id="57d62-135">You can add a new Globalization feature by deriving it from an existing feature that has been published or shared.</span></span>

1. <span data-ttu-id="57d62-136">Selezionare **Importa** per aprire la pagina **Importa funzionalità da repository globale**.</span><span class="sxs-lookup"><span data-stu-id="57d62-136">Select **Import** to open the **Import feature from Global repository** page.</span></span>

    ![Pagina Importa funzionalità da repository globale](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. <span data-ttu-id="57d62-138">Selezionare **Sincronizza** per ottenere le funzionalità più recenti.</span><span class="sxs-lookup"><span data-stu-id="57d62-138">Select **Synchronize** to get the latest features.</span></span>

    <span data-ttu-id="57d62-139">L'elenco sincronizzato include funzionalità che sono disponibili perché sono state pubblicate da Microsoft o perché sono state condivise da un altro provider di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="57d62-139">The synced list includes features that are available to you either because they were published by Microsoft or because they were shared with you by another configuration provider.</span></span>

    ![Elenco di funzionalità sincronizzato](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. <span data-ttu-id="57d62-141">Nell'elenco, selezionare le funzionalità da importare, quindi selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="57d62-141">In the list, select the features to import, and then select **Import**.</span></span> <span data-ttu-id="57d62-142">Se le funzionalità selezionate vengono importate correttamente, viene visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="57d62-142">You receive a message when the selected features have been successfully imported.</span></span>

    ![Messaggio che indica il completamento dell'importazione](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. <span data-ttu-id="57d62-144">Selezionare **Aggiungi**, quindi, nella finestra di dialogo a discesa, selezionare l'opzione **Basato sulla versione esistente**.</span><span class="sxs-lookup"><span data-stu-id="57d62-144">Select **Add**, and then, in the drop-down dialog box, select the **Based on existing version** option.</span></span>
5. <span data-ttu-id="57d62-145">Immettere un nome e una descrizione per la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-145">Enter a name and description for the feature.</span></span>
6. <span data-ttu-id="57d62-146">Nell'elenco di funzionalità disponibili, selezionare la versione di base della funzionalità, quindi selezionare **Crea funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="57d62-146">In the list of available features, select the base version of the feature, and then select **Create feature**.</span></span>

    ![Aggiungere una funzione derivata](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    <span data-ttu-id="57d62-148">La funzionalità aggiunta viene creata e ha lo stato **Bozza**.</span><span class="sxs-lookup"><span data-stu-id="57d62-148">The feature that you added is created and has a status of **Draft**.</span></span>

    ![Funzionalità derivata con stato Bozza](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. <span data-ttu-id="57d62-150">Esaminare i componenti della funzionalità per determinare se sono necessari degli aggiornamenti:</span><span class="sxs-lookup"><span data-stu-id="57d62-150">Review the feature components to determine whether updates are required:</span></span>

    - <span data-ttu-id="57d62-151">Rivedere le configurazioni, nel caso in cui sia necessario personalizzare i formati per la creazione di report elettronici (ER) e la relativa associazione con mapping di formati per la versione della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-151">Review the configurations, in case you need to customize the Electronic reporting (ER) formats and their binding with format mappings for the feature version.</span></span>
    - <span data-ttu-id="57d62-152">Esaminare l'impostazione, nel caso sia necessario personalizzare la scheda **Azioni**, la scheda **Regole di applicabilità** o la scheda **Variabili** per la versione della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-152">Review the setup, in case you need to customize the **Actions** tab, **Applicability rules** tab, or **Variables** tab for the feature version.</span></span>

8. <span data-ttu-id="57d62-153">Nella scheda **Versioni**, selezionare una **Data di inizio validità** e immettere una descrizione se il campo **Descrizione** è vuoto.</span><span class="sxs-lookup"><span data-stu-id="57d62-153">On the **Versions** tab, select an **Effective from** date, and enter a description if the **Description** field is blank.</span></span>
9. <span data-ttu-id="57d62-154">Selezionare **Cambia stato** per completare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-154">Select **Change status** to complete the feature.</span></span> <span data-ttu-id="57d62-155">Le funzionalità completate possono essere rese disponibili per un ambiente specifico di modo che possano essere utilizzate nei servizi di globalizzazione o pubblicate nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="57d62-155">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="57d62-156">Le funzionalità il cui valore **Stato versione funzionalità** è **Pubblicata** possono essere condivise con organizzazioni esterne.</span><span class="sxs-lookup"><span data-stu-id="57d62-156">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="add-a-new-globalization-feature"></a><span data-ttu-id="57d62-157">Aggiungere una nuova funzionalità di globalizzazione</span><span class="sxs-lookup"><span data-stu-id="57d62-157">Add a new Globalization feature</span></span>

<span data-ttu-id="57d62-158">È possibile aggiungere una nuova funzionalità di globalizzazione creandola da zero.</span><span class="sxs-lookup"><span data-stu-id="57d62-158">You can add a new Globalization feature by creating it from scratch.</span></span>

1. <span data-ttu-id="57d62-159">Nella pagina **Importa funzionalità da repository globale**, selezionare **Aggiungi**, quindi, nella finestra di dialogo a discesa, selezionare l'opzione **Nuova funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="57d62-159">On the **Import feature from Global repository** page, select **Add**, and then, in the drop-down dialog box, select the **New feature** option.</span></span>
2. <span data-ttu-id="57d62-160">Immettere un nome e una descrizione per la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-160">Enter a name and description for the feature.</span></span>
3. <span data-ttu-id="57d62-161">Selezionare **Crea funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="57d62-161">Select **Create feature**.</span></span>

    ![Aggiungere una nuova funzionalità](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. <span data-ttu-id="57d62-163">Nella scheda **Versioni**, selezionare una **Data di inizio validità**, quindi selezionare **Cambia stato** per completare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-163">On the **Versions** tab, select an **Effective from** date, and then select **Change status** to complete the feature.</span></span> <span data-ttu-id="57d62-164">Le funzionalità completate possono essere rese disponibili per un ambiente specifico di modo che possano essere utilizzate nei servizi di globalizzazione o pubblicate nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="57d62-164">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="57d62-165">Le funzionalità il cui valore **Stato versione funzionalità** è **Pubblicata** possono essere condivise con organizzazioni esterne.</span><span class="sxs-lookup"><span data-stu-id="57d62-165">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="feature-component-overview"></a><span data-ttu-id="57d62-166">Panoramica dei componenti delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="57d62-166">Feature component overview</span></span>

<span data-ttu-id="57d62-167">Le funzionalità di globalizzazione hanno vari componenti:</span><span class="sxs-lookup"><span data-stu-id="57d62-167">Globalization features have several components:</span></span>

- <span data-ttu-id="57d62-168">**Versione** - Questo componente supporta la gestione del ciclo di vita delle funzionalità e consente agli utenti di gestire lo stato per diverse versioni della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-168">**Version** – This component supports feature lifecycle management and lets users manage the status for different versions of the feature.</span></span>
- <span data-ttu-id="57d62-169">**Configurazioni** - Questo componente consente agli utenti di gestire, visualizzare e modificare i formati ER e i mapping dei formati correlati.</span><span class="sxs-lookup"><span data-stu-id="57d62-169">**Configurations** – This component lets users manage, view, and edit related ER formats and format mappings.</span></span>
- <span data-ttu-id="57d62-170">**Impostazioni** - Questo componente consente agli utenti dei servizi di globalizzazione, come un servizio di fatturazione elettronica, di gestire l'impostazione della versione della funzionalità correlata.</span><span class="sxs-lookup"><span data-stu-id="57d62-170">**Setups** – This component lets users of Globalization services, such as an e-invoicing service, manage the setup of the related feature version.</span></span> <span data-ttu-id="57d62-171">Pertanto, supporta la costruzione flessibile delle regole di comunicazione e risposta.</span><span class="sxs-lookup"><span data-stu-id="57d62-171">Therefore, it supports the flexible construction of communication and responses rules.</span></span>
- <span data-ttu-id="57d62-172">**Ambiente** - Questo componente consente agli utenti dei servizi di globalizzazione, come un servizio di fatturazione elettronica, di gestire l'ambiente in cui viene utilizzata l'impostazione delle versioni della funzionalità e di concedere l'autorizzazione agli utenti che accederanno allo stesso.</span><span class="sxs-lookup"><span data-stu-id="57d62-172">**Environment** – This component lets users of Globalization services, such as an e-invoicing service, manage the environment where the feature version setup is used and grant authorization to the users who will have access to it.</span></span>
- <span data-ttu-id="57d62-173">**Organizzazioni** - Questo componente consente agli utenti di condividere la funzionalità con organizzazioni esterne.</span><span class="sxs-lookup"><span data-stu-id="57d62-173">**Organizations** – This component lets users to share the feature with external organizations.</span></span>

## <a name="configuring-feature-components"></a><span data-ttu-id="57d62-174">Configurazione dei componenti delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="57d62-174">Configuring feature components</span></span>

### <a name="version-and-status"></a><span data-ttu-id="57d62-175">Versione e stato</span><span class="sxs-lookup"><span data-stu-id="57d62-175">Version and status</span></span>

<span data-ttu-id="57d62-176">La versione viene utilizzata per gestire il ciclo di vita della funzionalità di globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="57d62-176">The version is used to manage the Globalization feature lifecycle.</span></span>

<span data-ttu-id="57d62-177">Lo stato può essere modificato nel campo **Stato** nella scheda **Versione**. Sono disponibili i seguenti stati:</span><span class="sxs-lookup"><span data-stu-id="57d62-177">The status can be changed in the **Status** field on the **Version** tab. The following statuses are available:</span></span>

- <span data-ttu-id="57d62-178">**Bozza** - La funzionalità può essere modificata solo quando è in questo stato.</span><span class="sxs-lookup"><span data-stu-id="57d62-178">**Draft** – The feature can be edited only when it's in this status.</span></span>
- <span data-ttu-id="57d62-179">**Completa** - La funzionalità e tutti i componenti correlati sono stati finalizzati (completati) e non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="57d62-179">**Complete** – The feature and all related components have been finalized (completed) and can't be edited.</span></span>
- <span data-ttu-id="57d62-180">**Pubblicata** - La funzionalità e tutti i componenti correlati sono stati pubblicati nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="57d62-180">**Published** – The feature and all related components have been published to the Global repository.</span></span>
- <span data-ttu-id="57d62-181">**Condivisa** - La funzionalità e tutti i componenti correlati sono stati condivisi con organizzazioni esterne.</span><span class="sxs-lookup"><span data-stu-id="57d62-181">**Shared** – The feature and all related components have been shared with external organizations.</span></span>
- <span data-ttu-id="57d62-182">**Abilitata** - La funzionalità e tutti i componenti correlati sono stati abilitati per l'uso in un servizio di globalizzazione, come un servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="57d62-182">**Enabled** – The feature and all related components have been enabled for use in a Globalization service, such as an e-invoicing service.</span></span>

> [!NOTE]
> <span data-ttu-id="57d62-183">Le funzionalità devono passare sequenzialmente ad alcuni di questi stati.</span><span class="sxs-lookup"><span data-stu-id="57d62-183">Features must move sequentially through some of these statuses.</span></span> <span data-ttu-id="57d62-184">Pertanto, non tutti gli stati potrebbero essere disponibili in ogni fase del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="57d62-184">Therefore, not every status might be available at every lifecycle stage.</span></span>

### <a name="configurations"></a><span data-ttu-id="57d62-185">Configurazioni</span><span class="sxs-lookup"><span data-stu-id="57d62-185">Configurations</span></span>

<span data-ttu-id="57d62-186">Le seguenti azioni sono disponibili per le configurazioni:</span><span class="sxs-lookup"><span data-stu-id="57d62-186">The following actions are available for configurations:</span></span>

- <span data-ttu-id="57d62-187">**Visualizza** - Visualizza le configurazioni delle funzionalità sottostanti che non richiedono alcun aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="57d62-187">**View** – View the underlying feature configurations that don't require any update.</span></span>
- <span data-ttu-id="57d62-188">**Modifica** - Crea una versione bozza di una configurazione selezionata in modo da poter modificare il formato o il mapping del formato nella finestra Progettazione formati.</span><span class="sxs-lookup"><span data-stu-id="57d62-188">**Edit** – Create a draft version of a selected configuration so that you can edit the format or format mapping in the Format designer.</span></span>
- <span data-ttu-id="57d62-189">**Elimina** - Elimina una configurazione selezionata dalla funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-189">**Delete** – Delete a selected configuration from the feature.</span></span>
- <span data-ttu-id="57d62-190">**Riassegna** - Riassegna la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-190">**Rebase** – Rebase the feature.</span></span> <span data-ttu-id="57d62-191">Per ulteriori informazioni, vediere la sezione [Riassegnare funzionalità di globalizzazione derivate](#rebase) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="57d62-191">For more information, see the [Rebase derived Globalization features](#rebase) section later in this topic.</span></span>

### <a name="setups"></a><span data-ttu-id="57d62-192">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="57d62-192">Setups</span></span>

<span data-ttu-id="57d62-193">Le azioni seguenti sono disponibili per le impostazioni di funzionalità:</span><span class="sxs-lookup"><span data-stu-id="57d62-193">The following actions are available for feature setups:</span></span>

- <span data-ttu-id="57d62-194">**Aggiungi** - Crea una nuova impostazione di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-194">**Add** – Create a new feature setup.</span></span> <span data-ttu-id="57d62-195">Questa impostazione può essere derivata da un'impostazione esistente o creata da zero.</span><span class="sxs-lookup"><span data-stu-id="57d62-195">This feature setup can be derived from an existing feature setup or created from scratch.</span></span>
- <span data-ttu-id="57d62-196">**Elimina** - Elimina l'impostazione di funzionalità selezionata.</span><span class="sxs-lookup"><span data-stu-id="57d62-196">**Delete** – Delete a selected feature setup.</span></span>
- <span data-ttu-id="57d62-197">**Visualizza** - Visualizza un'impostazione di funzionalità sottostante che non richiede alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="57d62-197">**View** – View an underlying feature setup that doesn't require any changes.</span></span>
- <span data-ttu-id="57d62-198">**Modifica** - Crea, elimina o modifica gli attributi dei tre componenti principali di un'impostazione di funzionalità:</span><span class="sxs-lookup"><span data-stu-id="57d62-198">**Edit** – Create, delete, or modify the attributes of the three main components of a feature setup:</span></span>

    - <span data-ttu-id="57d62-199">Azioni e i relativi parametri</span><span class="sxs-lookup"><span data-stu-id="57d62-199">Actions and their parameters</span></span>
    - <span data-ttu-id="57d62-200">Regole di applicabilità</span><span class="sxs-lookup"><span data-stu-id="57d62-200">Applicability rules</span></span>
    - <span data-ttu-id="57d62-201">Variabili</span><span class="sxs-lookup"><span data-stu-id="57d62-201">Variables</span></span>

![Pagina Impostazione versioni funzionalità](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a><span data-ttu-id="57d62-203">Ambienti</span><span class="sxs-lookup"><span data-stu-id="57d62-203">Environments</span></span>

<span data-ttu-id="57d62-204">Le seguenti azioni sono disponibili per gli ambienti:</span><span class="sxs-lookup"><span data-stu-id="57d62-204">The following actions are available for environments:</span></span>

- <span data-ttu-id="57d62-205">**Abilita** - Per la versione della funzionalità selezionata, selezionare un ambiente pubblicato e una **Data di inizio validità** alla quale dovrebbe essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="57d62-205">**Enable** – For a selected feature version, select a published environment, and select an **Effective from** date when it should be available.</span></span> <span data-ttu-id="57d62-206">Per ulteriori informazioni, vediere la sezione [Configurare ambienti per l'abilitazione](#configureenvironment) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="57d62-206">For more information, see the [Configure environments for enablement](#configureenvironment) section later in this topic.</span></span>
- <span data-ttu-id="57d62-207">**Annulla** - Rimuove un ambiente per un'impostazione di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-207">**Cancel** – Remove an environment for a feature setup.</span></span>

### <a name="organizations"></a><span data-ttu-id="57d62-208">Organizzazioni</span><span class="sxs-lookup"><span data-stu-id="57d62-208">Organizations</span></span>

<span data-ttu-id="57d62-209">Seguire questi passaggi per condividere una funzionalità di globalizzazione con un'organizzazione esterna.</span><span class="sxs-lookup"><span data-stu-id="57d62-209">Follow these steps to share a Globalization feature with an external organization.</span></span>

1. <span data-ttu-id="57d62-210">Nella pagina **Funzionalità di fatturazione elettronica**, selezionare la funzionalità e la versione della funzionalità da condividere.</span><span class="sxs-lookup"><span data-stu-id="57d62-210">On the **e-Invoicing features** page, select the feature and the feature version to share.</span></span>
2. <span data-ttu-id="57d62-211">Nella scheda **Organizzazioni**, selezionare **Condividi con**, quindi, nella finestra di dialogo a discesa, immettere il nome di dominio dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="57d62-211">On the **Organizations** tab, select **Share with**, and then, in the drop-down dialog box, enter the organization's domain name.</span></span>
3. <span data-ttu-id="57d62-212">Selezionare **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="57d62-212">Select **Share**.</span></span>

    ![Condividere una funzionalità con un'organizzazione](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

<span data-ttu-id="57d62-214">La funzionalità è condivisa con l'organizzazione selezionata ed è disponibile per tale organizzazione nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="57d62-214">The feature is shared with the selected organization and is available for that organization in the Global repository.</span></span> <span data-ttu-id="57d62-215">Da lì, la funzionalità può essere importata nell'istanza di RCS o di Dynamics 365 Finance dell'organizzazione in modo che possa essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="57d62-215">From there, the feature can be imported into the organization's instance of RCS or Dynamics 365 Finance so that it can be used.</span></span>

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a><span data-ttu-id="57d62-216">Riassegnare funzionalità di globalizzazione derivate</span><span class="sxs-lookup"><span data-stu-id="57d62-216">Rebase derived Globalization features</span></span>

<span data-ttu-id="57d62-217">È possibile riassegnare una funzionalità di globalizzazione derivata alla versione di base nuova o aggiornata della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-217">You can rebase a derived Globalization feature to the new or updated base feature version.</span></span> <span data-ttu-id="57d62-218">In questo modo, le modifiche alla versione di base possono essere aggiornate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="57d62-218">In this way, changes that have occurred in the base version can be automatically updated.</span></span> <span data-ttu-id="57d62-219">La versione di base aggiornata della funzionalità viene creata dal provider di configurazioni di origine e viene quindi pubblicata o condivisa.</span><span class="sxs-lookup"><span data-stu-id="57d62-219">The updated base feature version is created by the originating configuration provider, and it's then published or shared.</span></span>

![Versione di base aggiornata di una funzionalità](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

<span data-ttu-id="57d62-221">Ad esempio, se si desidera riassegnare la versione derivata di una funzionalità creata, si ottiene innanzitutto la versione più recente della funzionalità importandola dal repository globale.</span><span class="sxs-lookup"><span data-stu-id="57d62-221">For example, if you want to rebase the derived version of a feature that you created, you first get the latest version of the feature by importing it from the Global repository.</span></span>

1. <span data-ttu-id="57d62-222">Nella pagina **Funzionalità di fatturazione elettronica**, selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="57d62-222">On the **e-Invoicing features** page, select **Import**.</span></span>
2. <span data-ttu-id="57d62-223">Selezionare **Sincronizza** per ottenere le funzionalità più recenti.</span><span class="sxs-lookup"><span data-stu-id="57d62-223">Select **Synchronize** to get the latest features.</span></span>
3. <span data-ttu-id="57d62-224">Nell'elenco di funzionalità, selezionare le funzionalità da importare, quindi selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="57d62-224">In the list of features, select the features to import, and then select **Import**.</span></span>

    ![Importazione dell'ultima versione di una funzionalità](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. <span data-ttu-id="57d62-226">Nell'elenco delle funzionalità, selezionare la funzionalità da riassegnare.</span><span class="sxs-lookup"><span data-stu-id="57d62-226">In the list of features, select the feature to rebase.</span></span>
5. <span data-ttu-id="57d62-227">Nella scheda **Versione**, selezionare **Nuova** per creare una versione bozza.</span><span class="sxs-lookup"><span data-stu-id="57d62-227">On the **Version** tab, select **New** to create a draft version.</span></span>

    ![Nuova versione bozza creata](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. <span data-ttu-id="57d62-229">Selezionare **Riassegna**.</span><span class="sxs-lookup"><span data-stu-id="57d62-229">Select **Rebase**.</span></span>
7. <span data-ttu-id="57d62-230">Nella finestra di dialogo **Riassegna**, selezionare la versione più recente a cui riassegnare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="57d62-230">In the **Rebase** dialog box, select the latest version of the feature to rebase to.</span></span>

    ![Finestra di dialogo Riassegna](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. <span data-ttu-id="57d62-232">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="57d62-232">Select **OK**.</span></span>
9. <span data-ttu-id="57d62-233">Esaminare i componenti della funzionalità e apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="57d62-233">Review the feature components, and make any changes that are required.</span></span>
10. <span data-ttu-id="57d62-234">Selezionare **Cambia stato** per completare la funzionalità riassegnata.</span><span class="sxs-lookup"><span data-stu-id="57d62-234">Select **Change status** to complete the rebased feature.</span></span> <span data-ttu-id="57d62-235">Una volta completata la riassegnazione, è possibile eseguire azioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="57d62-235">When the rebase is completed, you can perform additional actions.</span></span> <span data-ttu-id="57d62-236">Ad esempio, è possibile pubblicare la funzionalità e renderla disponibile per l'uso nei servizi di globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="57d62-236">For example, you can publish the feature and make it available for use in Globalization services.</span></span>

    ![Stato della funzionalità aggiornato a Completata](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a><span data-ttu-id="57d62-238">Configurare ambienti per le funzionalità di globalizzazione</span><span class="sxs-lookup"><span data-stu-id="57d62-238">Configure environments for Globalization features</span></span>

<span data-ttu-id="57d62-239">Gli utenti dei servizi di globalizzazione possono gestire l'ambiente per impostare una funzione di globalizzazione e concedere l'autorizzazione ad altri utenti che vi avranno accesso.</span><span class="sxs-lookup"><span data-stu-id="57d62-239">Users of Globalization services can manage the environment to set up a Globalization feature and grant authorization to other users who will have access to it.</span></span>

1. <span data-ttu-id="57d62-240">Aprire la nuova area di lavoro **Funzionalità di globalizzazione** e quindi sotto **Ambienti**, selezionare il riquadro **Fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="57d62-240">In the **Globalization Features** workspace, under **Environments**, select the **e-Invoicing** tile.</span></span>

    ![Area di lavoro Funzionalità di globalizzazione](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. <span data-ttu-id="57d62-242">Selezionare **Parametri insieme di credenziali delle chiavi**, quindi selezionare **Nuovo** per creare un segreto dell'insieme di credenziali delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="57d62-242">Select **Key Vault parameters**, and then select **New** to create an Azure Key Vault secret.</span></span>
3. <span data-ttu-id="57d62-243">Immettere un nome e una descrizione per l'insieme di credenziali delle chiavi, quindi nel campo **URI insieme di credenziali delle chiavi**, immettere l'URL che identifica la risorsa di tale insieme in Azure.</span><span class="sxs-lookup"><span data-stu-id="57d62-243">Enter a name and description for the key vault, and then, in the **Key Vault URI** field, enter the URL that identifies the Key Vault resource in Azure.</span></span>
4. <span data-ttu-id="57d62-244">nella Scheda dettaglio **Certificati**, selezionare **Aggiungi** per aggiungere il certificato e imettere un nome e una descrizione per ogni certificato.</span><span class="sxs-lookup"><span data-stu-id="57d62-244">On the **Certificates** FastTab, select **Add** to add the certificate, and enter a name and description for each certificate.</span></span>

    ![Certificato aggiunto](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. <span data-ttu-id="57d62-246">Selezionare **Nuovo** per creare un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="57d62-246">Select **New** to create a new environment.</span></span>
6. <span data-ttu-id="57d62-247">Immettere un nome, una descrizione e il segreto del token di firme di accesso condiviso necessario per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="57d62-247">Enter a name, a description, and the shared access signature token secret required for the storage.</span></span>
7. <span data-ttu-id="57d62-248">Nella Scheda dettagli **Utenti**, selezionare **Nuovo** per aggiungere un utente che avrà l'autorizzazione di accedere a questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="57d62-248">On the **Users** FastTab, select **New** to add a user who will have permission to access this environment.</span></span>
8. <span data-ttu-id="57d62-249">Immettere l'ID utente e l'indirizzo e-mail dell'utente.</span><span class="sxs-lookup"><span data-stu-id="57d62-249">Enter the user's user ID and email address.</span></span>
9. <span data-ttu-id="57d62-250">Ripetere i passaggi 7 e 8 per aggiungere altri utenti.</span><span class="sxs-lookup"><span data-stu-id="57d62-250">Repeat steps 7 and 8 to add more users.</span></span>
10. <span data-ttu-id="57d62-251">Selezionare **Pubblica** per pubblicare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="57d62-251">Select **Publish** to publish the environment.</span></span>

    ![Ambiente pubblicato](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)
