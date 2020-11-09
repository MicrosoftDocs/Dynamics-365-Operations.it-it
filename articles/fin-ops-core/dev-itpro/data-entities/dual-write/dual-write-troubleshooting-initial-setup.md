---
title: Risoluzione dei problemi durante l'impostazione iniziale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi che potrebbero verificarsi durante l'impostazione iniziale dell'integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 6fb71a17d767a1e84511743794d85523db25eba8
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997352"
---
# <a name="troubleshoot-issues-during-initial-setup"></a><span data-ttu-id="59f16-103">Risoluzione dei problemi durante l'impostazione iniziale</span><span class="sxs-lookup"><span data-stu-id="59f16-103">Troubleshoot issues during initial setup</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="59f16-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="59f16-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="59f16-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante l'impostazione iniziale dell'integrazione doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="59f16-105">Specifically, it provides information that can help you fix issues that might occur during the initial setup of dual-write integration.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59f16-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="59f16-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="59f16-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="59f16-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-link-a-finance-and-operations-app-to-common-data-service"></a><span data-ttu-id="59f16-108">Non è possibile collegare un'app Finance and Operations a Common Data Service</span><span class="sxs-lookup"><span data-stu-id="59f16-108">You can't link a Finance and Operations app to Common Data Service</span></span>

<span data-ttu-id="59f16-109">**Ruolo richiesto per impostare la doppia scrittura:** Amministratore di sistema nelle app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="59f16-109">**Required role to set up dual-write:** System administrator in Finance and Operations apps and Common Data Service.</span></span>

<span data-ttu-id="59f16-110">Gli errori nella pagina **Impostazione del collegamento a Common Data Service** sono generalmente causati da problemi di configurazione o permessi incompleti.</span><span class="sxs-lookup"><span data-stu-id="59f16-110">Errors on the **Setup link to Common Data Service** page are usually caused by incomplete setup or permissions issues.</span></span> <span data-ttu-id="59f16-111">Assicurarsi che l'intero controllo dello stato passi nella pagina **Impostazione del collegamento a Common Data Service** , come mostrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="59f16-111">Make sure that the whole health check passes on the **Setup link to Common Data Service** page, as shown in the following illustration.</span></span> <span data-ttu-id="59f16-112">Non è possibile collegare la doppia scrittura a meno che non venga superato l'intero controllo dello stato.</span><span class="sxs-lookup"><span data-stu-id="59f16-112">You can't link dual-write unless the whole health check passes.</span></span>

![Controllo dello stato riuscito](media/health_check.png)

<span data-ttu-id="59f16-114">È necessario avere le credenziali di amministratore del tenant Azure AD per il collegamento degli ambienti Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="59f16-114">You must have Azure AD tenant admin credentials to link the Finance and Operations and Common Data Service environments.</span></span> <span data-ttu-id="59f16-115">Dopo aver collegato gli ambienti, gli utenti possono accedere utilizzando le credenziali del proprio account e aggiornare una mappa di entità esistente.</span><span class="sxs-lookup"><span data-stu-id="59f16-115">After you link the environments, users can sign in by using their account credentials and update an existing entity map.</span></span>

## <a name="error-when-you-open-the-link-to-common-data-service-page"></a><span data-ttu-id="59f16-116">Errore quando si apre la pagina Collegamento a Common Data Service</span><span class="sxs-lookup"><span data-stu-id="59f16-116">Error when you open the Link to Common Data Service page</span></span>

<span data-ttu-id="59f16-117">**Credenziali richieste per risolvere il problema:** amministratore del tenant Azure AD</span><span class="sxs-lookup"><span data-stu-id="59f16-117">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="59f16-118">È possibile che venga visualizzato il seguente messaggio di errore quando si apre la pagina **Collegamento a Common Data Service** in un'app Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="59f16-118">You might receive the following error message when you open the **Link to Common Data Service** page in a Finance and Operations app:</span></span>

<span data-ttu-id="59f16-119">*Il codice dello stato della risposta non indica l'esito positivo: 404 (non trovato).*</span><span class="sxs-lookup"><span data-stu-id="59f16-119">*Response status code does not indicate success: 404 (Not Found).*</span></span>

<span data-ttu-id="59f16-120">Questo errore si verifica quando il passaggio del consenso non è stato completato.</span><span class="sxs-lookup"><span data-stu-id="59f16-120">This error occurs when the consent step hasn't been completed.</span></span> <span data-ttu-id="59f16-121">Per verificare se il passaggio del consenso è stato completato, accedere a portal.Azure.com utilizzando l'account di amministratore del tenant Azure AD e verificare se l'app di terze parti con l'ID **33976c19-1db5-4c02-810e-c243db79efde** appare nell'elenco **Applicazioni aziendali** Azure AD.</span><span class="sxs-lookup"><span data-stu-id="59f16-121">To validate whether the consent step has been completed, sign in to portal.Azure.com by using the Azure AD tenant admin account, and see whether the third-party app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** appears in the Azure AD **Enterprise applications** list.</span></span> <span data-ttu-id="59f16-122">In caso contrario, è necessario fornire il consenso dell'app.</span><span class="sxs-lookup"><span data-stu-id="59f16-122">If it doesn't, you must provide app consent.</span></span>

<span data-ttu-id="59f16-123">Per fornire il consenso all'app, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="59f16-123">To provide app consent, follow these steps.</span></span>

1. <span data-ttu-id="59f16-124">Aprire il seguente URL usando le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="59f16-124">Open the following URL by using your admin credentials.</span></span> <span data-ttu-id="59f16-125">Viene richiesto di confermare il consenso.</span><span class="sxs-lookup"><span data-stu-id="59f16-125">You should be prompted for consent.</span></span>

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. <span data-ttu-id="59f16-126">Selezionare **Accetto** per indicare che si sta fornendo il consenso all'installazione dell'app con l'ID **33976c19-1db5-4c02-810e-c243db79efde** nel tenant.</span><span class="sxs-lookup"><span data-stu-id="59f16-126">Select **Accept** to indicate that you're giving your consent to install the app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** in your tenant.</span></span>

    > [!TIP]
    > <span data-ttu-id="59f16-127">Questa app è necessaria per il collegamento di Common Data Service e delle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="59f16-127">This app is required to link Common Data Service and Finance and Operations apps.</span></span> <span data-ttu-id="59f16-128">In caso di problemi con questo passaggio, aprire il browser in modalità di navigazione in incognito (in Google Chrome) o InPrivate (in Microsoft Edge).</span><span class="sxs-lookup"><span data-stu-id="59f16-128">If you have trouble with this step, open your browser in incognito mode (in Google Chrome) or InPrivate mode (in Microsoft Edge).</span></span>

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a><span data-ttu-id="59f16-129">Verificare che i dati dell'azienda e i team di doppia scrittura siano impostati correttamente durante il collegamento</span><span class="sxs-lookup"><span data-stu-id="59f16-129">Verify that company data and dual-write teams are set up correctly during linking</span></span>

<span data-ttu-id="59f16-130">Per garantire che la doppia scrittura funzioni correttamente, le società selezionate durante la configurazione vengono create nell'ambiente Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="59f16-130">To ensure that dual-write works correctly, the companies that you select during configuration are created in the Common Data Service environment.</span></span> <span data-ttu-id="59f16-131">Per impostazione predefinita, queste società sono di sola lettura e la proprietà **IsDualWriteEnable** è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="59f16-131">By default, these companies are read-only, and the **IsDualWriteEnable** property is set to **True**.</span></span> <span data-ttu-id="59f16-132">Inoltre, vengono creati il proprietario e il team della Business Unit proprietaria predefinita e viene incluso il nome dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="59f16-132">In addition, the default owning business unit owner and team are created and include the company name.</span></span> <span data-ttu-id="59f16-133">Prima di abilitare le mappe, verificare che sia specificato il proprietario del team predefinito.</span><span class="sxs-lookup"><span data-stu-id="59f16-133">Before you enable the maps, verify that the default team owner is specified.</span></span> <span data-ttu-id="59f16-134">Per trovare l'entità **Companies (CDM\_Company)** , attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="59f16-134">To find the **Companies (CDM\_Company)** entity, follow these steps.</span></span>

1. <span data-ttu-id="59f16-135">Nell'app basata su modello in Dynamics 365, selezionare il filtro nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="59f16-135">In the model-driven app in Dynamics 365, select the filter in the upper-right corner.</span></span>
2. <span data-ttu-id="59f16-136">Nell'elenco a discesa selezionare **Società**.</span><span class="sxs-lookup"><span data-stu-id="59f16-136">In the drop-down list, select **Company**.</span></span>
3. <span data-ttu-id="59f16-137">Selezionare **Esegui** per vedere i risultati.</span><span class="sxs-lookup"><span data-stu-id="59f16-137">Select **Run** to see the results.</span></span>
4. <span data-ttu-id="59f16-138">Selezionare la società che è stata collegata quando è stata configurata la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="59f16-138">Select the company that was linked when you configured dual-write.</span></span>
5. <span data-ttu-id="59f16-139">Verificare che il campo **Team proprietario predefinito** abbia un valore.</span><span class="sxs-lookup"><span data-stu-id="59f16-139">Verify that the **Default owning team** field has a value.</span></span> <span data-ttu-id="59f16-140">Nell'illustrazione seguente, il campo **Team proprietario predefinito** è impostato su **Doppia scrittura USMF**.</span><span class="sxs-lookup"><span data-stu-id="59f16-140">In the following illustration, the **Default owning team** field is set to **USMF Dual Write**.</span></span>

    ![Verifica del team proprietario predefinito](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-entities-or-companies-that-can-be-linked-for-dual-write"></a><span data-ttu-id="59f16-142">Trovare il limite del numero di persone giuridiche o società che possono essere collegate per la doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="59f16-142">Find the limit on the number of legal entities or companies that can be linked for dual-write</span></span>

<span data-ttu-id="59f16-143">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di abilitare le mappe:</span><span class="sxs-lookup"><span data-stu-id="59f16-143">You might receive the following error message when you try to enable maps:</span></span>

<span data-ttu-id="59f16-144">*Doppia scrittura non riuscita - Registrazione plug-in non riuscita: \[(Impossibile ottenere la mappa della partizione per il progetto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Errore: il numero massimo di partizioni consentite è stato superato per il mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\]. Si sono verificati uno o più errori.*</span><span class="sxs-lookup"><span data-stu-id="59f16-144">*Dual write failure - Plugin registration failed: \[(Unable to get partition map for project DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Error Exceeds the maximum partitions allowed for mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], One or more errors occurred.*</span></span>

<span data-ttu-id="59f16-145">Il limite attuale quando si collegano gli ambienti è di circa 40 persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="59f16-145">The current limit when you link the environments is approximately 40 legal entities.</span></span> <span data-ttu-id="59f16-146">Questo errore si verifica se si tenta di abilitare le mappe e più di 40 persone giuridiche sono collegate tra gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="59f16-146">This error occurs if you try to enable maps, and more than 40 legal entities are linked between the environments.</span></span>
