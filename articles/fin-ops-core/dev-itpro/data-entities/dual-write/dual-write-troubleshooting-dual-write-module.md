---
title: Risoluzione dei problemi con il modulo doppia scrittura nelle app Finance and Operations
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi al modulo doppia scrittura nelle app Finance and Operations.
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
ms.openlocfilehash: f99f3760e75ec1bbf2ccdea497cf2eec3e28e233
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997376"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="72b76-103">Risoluzione dei problemi con il modulo doppia scrittura nelle app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="72b76-103">Troubleshoot issues with the dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="72b76-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72b76-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="72b76-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi al modulo **doppia scrittura** nelle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="72b76-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72b76-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="72b76-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="72b76-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="72b76-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="72b76-108">Non è possibile caricare il modulo doppia scrittura in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="72b76-108">You can't load the dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="72b76-109">Se non si riesce ad aprire la pagina **Doppia scrittura** selezionando il riquadro **Doppia scrittura** nell'area di lavoro **Gestione dei dati** , il servizio di integrazione dei dati è probabilmente inattivo.</span><span class="sxs-lookup"><span data-stu-id="72b76-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="72b76-110">Creare un ticket di supporto per richiedere il riavvio del servizio di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="72b76-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-map"></a><span data-ttu-id="72b76-111">Errore quando si tenta di creare una nuova mappa di entità</span><span class="sxs-lookup"><span data-stu-id="72b76-111">Error when you try to create a new entity map</span></span>

<span data-ttu-id="72b76-112">**Credenziali richieste per risolvere il problema:** lo stesso utente che ha impostato la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="72b76-112">**Required credentials to fix the issue:** The same user that setup dual-write.</span></span>

<span data-ttu-id="72b76-113">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di configurare una nuova entità per la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="72b76-113">You might receive the following error message when you try to configure a new entity for dual-write.</span></span> <span data-ttu-id="72b76-114">L'unico utente che può creare una mappa è l'utente che imposta la connessione per la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="72b76-114">The only user that can create a map is the user who setup the dual-write connection.</span></span>

<span data-ttu-id="72b76-115">*Il codice dello stato della risposta non indica l'esito positivo: 401 (non autorizzato).*</span><span class="sxs-lookup"><span data-stu-id="72b76-115">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>


## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="72b76-116">Errore quando si apre l'interfaccia utente a doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="72b76-116">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="72b76-117">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di accedere alla doppia scrittura dall'area di lavoro **Gestione dei dati** :</span><span class="sxs-lookup"><span data-stu-id="72b76-117">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="72b76-118">*login.microsoftonline.com ha rifiutato di connettersi.*</span><span class="sxs-lookup"><span data-stu-id="72b76-118">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="72b76-119">Per risolvere il problema, accedere utilizzando una finestra InPrivate in Microsoft Edge, una finestra di navigazione in incognito in Chromium o una finestra di navigazione in incognito in Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="72b76-119">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="72b76-120">È inoltre necessario sbloccare o cancellare i cookie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="72b76-120">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="72b76-121">Errore quando si collega l'ambiente per la doppia scrittura o si aggiunge un nuovo mapping di entità</span><span class="sxs-lookup"><span data-stu-id="72b76-121">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="72b76-122">**Ruolo richiesto per correggere il problema:** amministratore di sistema nelle app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72b76-122">**Required role to fix the issue:** System administrator in both Finance and Operations apps and Common Data Service.</span></span>

<span data-ttu-id="72b76-123">È possibile che si verifichi il seguente errore durante il collegamento o la creazione di mappe:</span><span class="sxs-lookup"><span data-stu-id="72b76-123">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="72b76-124">*Il codice dello stato della risposta non indica l'esito positivo: 403 (tokenexchange).<br> ID sessione: \<your session id\><br> ID attività radice: \<your root activity id\>*</span><span class="sxs-lookup"><span data-stu-id="72b76-124">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="72b76-125">Questo errore può verificarsi se non si dispone di autorizzazioni sufficienti per collegare la doppia scrittura o creare mappe.</span><span class="sxs-lookup"><span data-stu-id="72b76-125">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="72b76-126">Questo errore può verificarsi anche se l'ambiente Common Data Service è stato ripristinato senza scollegare la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="72b76-126">This error can also occur if the Common Data Service environment was reset without unlinking dual-write.</span></span> <span data-ttu-id="72b76-127">Qualsiasi utente con ruolo di amministratore di sistema nelle app Finance and Operations e Common Data Service può collegare gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="72b76-127">Any user with system administrator role in both Finance and Operations apps and Common Data Service can link the environments.</span></span> <span data-ttu-id="72b76-128">Solo l'utente che imposta la connessione per la doppia scrittura può aggiungere nuove mappe di entità.</span><span class="sxs-lookup"><span data-stu-id="72b76-128">Only the user who setup the dual-write connection can add new entity maps.</span></span> <span data-ttu-id="72b76-129">Dopo l'impostazione, qualsiasi utente con ruolo di amministratore di sistema può monitorare lo stato e modificare i mapping.</span><span class="sxs-lookup"><span data-stu-id="72b76-129">After setup, any user with system administrator role can monitor the status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="72b76-130">Errore quando si interrompe il mapping dell'entità</span><span class="sxs-lookup"><span data-stu-id="72b76-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="72b76-131">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di interrompere i mapping di entità:</span><span class="sxs-lookup"><span data-stu-id="72b76-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="72b76-132">*\[Accesso negato\], \[{"stato": 403,"origine":"","messaggio":"Errore dello scambio di token: l'utente non è autorizzato ad accedere alla connessione dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Il server remoto ha restituito un errore: (403) Accesso negato.*</span><span class="sxs-lookup"><span data-stu-id="72b76-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="72b76-133">Questo errore si verifica quando l'ambiente Common Data Service collegato non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="72b76-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="72b76-134">Per risolvere il problema, creare un ticket per il team di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="72b76-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="72b76-135">Collegare la traccia di rete in modo che il team di integrazione dei dati possa contrassegnare le mappe come **Non in esecuzione** nel back-end.</span><span class="sxs-lookup"><span data-stu-id="72b76-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>

## <a name="error-while-trying-to-start-an-entity-mapping"></a><span data-ttu-id="72b76-136">Errore durante il tentativo di avviare un mapping di entità</span><span class="sxs-lookup"><span data-stu-id="72b76-136">Error while trying to start an entity mapping</span></span>

<span data-ttu-id="72b76-137">È possibile che venga visualizzato un errore simile al seguente quando si tenta di impostare lo stato di un mapping su **In esecuzione** :</span><span class="sxs-lookup"><span data-stu-id="72b76-137">You might receive an error like the following when you try to set that state of a mapping to **Running** :</span></span>

<span data-ttu-id="72b76-138">*Impossibile completare la sincronizzazione iniziale dei dati. Errore: errore di doppia scrittura - registrazione del plug-in non riuscita: impossibile creare metadati di ricerca per la doppia scrittura. Errore di riferimento oggetto non impostato sull'istanza di un oggetto.*</span><span class="sxs-lookup"><span data-stu-id="72b76-138">*Unable to complete initial data sync. Error: dual-write failure - plugin registration failed: Unable to build dual-write lookup metadata. Error object reference not set to an instance of an object.*</span></span>

<span data-ttu-id="72b76-139">La correzione di questo errore dipende dalla causa dell'errore:</span><span class="sxs-lookup"><span data-stu-id="72b76-139">The fix for this error depends on the cause of the error:</span></span>

+ <span data-ttu-id="72b76-140">Se il mapping prevede mapping dipendenti, assicurarsi di abilitare i mapping dipendenti di questo mapping di entità.</span><span class="sxs-lookup"><span data-stu-id="72b76-140">If the mapping has dependent mappings, then make sure to enable the dependent mappings of this entity mapping.</span></span>
+ <span data-ttu-id="72b76-141">Nel mapping potrebbero mancare i campi di origine o destinazione.</span><span class="sxs-lookup"><span data-stu-id="72b76-141">The mapping might be missing source or destination fields.</span></span> <span data-ttu-id="72b76-142">Se manca un campo nell'app Finance and Operations, seguire i passaggi nella sezione [Problema dei campi di entità mancanti sulle mappe](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps).</span><span class="sxs-lookup"><span data-stu-id="72b76-142">If a field in the Finance and Operations app is missing, then follow the steps in the section [Missing entity fields issue on maps](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps).</span></span> <span data-ttu-id="72b76-143">Se manca un campo in Common Data Service, fare clic sul pulsante **Aggiorna entità** sul mapping in modo che i campi vengano automaticamente compilati nuovamente nel mapping.</span><span class="sxs-lookup"><span data-stu-id="72b76-143">If a field in Common Data Service is missing, then click **Refresh entities** button on the mapping so that the fields are automatically populated back into the mapping.</span></span>
