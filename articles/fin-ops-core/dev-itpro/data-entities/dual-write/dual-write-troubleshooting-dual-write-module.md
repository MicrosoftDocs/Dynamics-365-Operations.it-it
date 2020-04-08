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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172762"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="6efc4-103">Risoluzione dei problemi con il modulo doppia scrittura nelle app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6efc4-103">Troubleshoot issues with the Dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="6efc4-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6efc4-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="6efc4-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi al modulo **doppia scrittura** nelle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6efc4-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6efc4-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="6efc4-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="6efc4-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="6efc4-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="6efc4-108">Non è possibile caricare il modulo doppia scrittura in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6efc4-108">You can't load the Dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="6efc4-109">Se non si riesce ad aprire la pagina **Doppia scrittura** selezionando il riquadro **Doppia scrittura** nell'area di lavoro **Gestione dei dati**, il servizio di integrazione dei dati è probabilmente inattivo.</span><span class="sxs-lookup"><span data-stu-id="6efc4-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="6efc4-110">Creare un ticket di supporto per richiedere il riavvio del servizio di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="6efc4-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a><span data-ttu-id="6efc4-111">Errore quando si tenta di creare un nuovo mapping di entità</span><span class="sxs-lookup"><span data-stu-id="6efc4-111">Error when you try to create a new entity mapping</span></span>

<span data-ttu-id="6efc4-112">**Credenziali richieste per risolvere il problema:** amministratore del tenant Azure AD</span><span class="sxs-lookup"><span data-stu-id="6efc4-112">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="6efc4-113">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di configurare una nuova entità per la doppia scrittura:</span><span class="sxs-lookup"><span data-stu-id="6efc4-113">You might receive the following error message when you try to configure a new entity for dual-write:</span></span>

<span data-ttu-id="6efc4-114">*Il codice dello stato della risposta non indica l'esito positivo: 401 (non autorizzato).*</span><span class="sxs-lookup"><span data-stu-id="6efc4-114">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>

<span data-ttu-id="6efc4-115">Questo errore si verifica perché solo un amministratore del tenant Azure AD può aggiungere un nuovo mapping di entità.</span><span class="sxs-lookup"><span data-stu-id="6efc4-115">This error occurs because only an Azure AD tenant admin can add a new entity mapping.</span></span>

<span data-ttu-id="6efc4-116">Per risolvere il problema, accedere all'app Finance and Operations come amministratore del tenant Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6efc4-116">To fix the issue, sign in to the Finance and Operations app as an Azure AD admin tenant.</span></span> <span data-ttu-id="6efc4-117">È necessario anche andare in web.PowerApps.com e riconvalidare la tua connessione.</span><span class="sxs-lookup"><span data-stu-id="6efc4-117">You must also go to web.PowerApps.com and revalidate your connection.</span></span>

## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="6efc4-118">Errore quando si apre l'interfaccia utente a doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="6efc4-118">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="6efc4-119">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di accedere alla doppia scrittura dall'area di lavoro **Gestione dei dati**:</span><span class="sxs-lookup"><span data-stu-id="6efc4-119">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="6efc4-120">*login.microsoftonline.com ha rifiutato di connettersi.*</span><span class="sxs-lookup"><span data-stu-id="6efc4-120">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="6efc4-121">Per risolvere il problema, accedere utilizzando una finestra InPrivate in Microsoft Edge, una finestra di navigazione in incognito in Chromium o una finestra di navigazione in incognito in Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="6efc4-121">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="6efc4-122">È inoltre necessario sbloccare o cancellare i cookie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6efc4-122">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="6efc4-123">Errore quando si collega l'ambiente per la doppia scrittura o si aggiunge un nuovo mapping di entità</span><span class="sxs-lookup"><span data-stu-id="6efc4-123">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="6efc4-124">**Credenziali richieste per risolvere il problema:** amministratore del tenant Azure AD</span><span class="sxs-lookup"><span data-stu-id="6efc4-124">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="6efc4-125">È possibile che si verifichi il seguente errore durante il collegamento o la creazione di mappe:</span><span class="sxs-lookup"><span data-stu-id="6efc4-125">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="6efc4-126">*Il codice dello stato della risposta non indica l'esito positivo: 403 (tokenexchange).<br> ID sessione: \<ID sessione\><br> ID attività radice: \<ID attività radice\>*</span><span class="sxs-lookup"><span data-stu-id="6efc4-126">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="6efc4-127">Questo errore può verificarsi se non si dispone di autorizzazioni sufficienti per collegare la doppia scrittura o creare mappe.</span><span class="sxs-lookup"><span data-stu-id="6efc4-127">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="6efc4-128">È necessario usare un account amministratore del tenant Azure AD per collegare ambienti e aggiungere nuovi mapping di entità.</span><span class="sxs-lookup"><span data-stu-id="6efc4-128">You must use an Azure AD tenant admin account to link environments and add new entity mappings.</span></span> <span data-ttu-id="6efc4-129">Tuttavia, dopo l'impostazione, è possibile utilizzare un account non amministratore per monitorare lo stato e modificare i mapping.</span><span class="sxs-lookup"><span data-stu-id="6efc4-129">However, after setup, you can use a non-admin account to monitor status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="6efc4-130">Errore quando si interrompe il mapping dell'entità</span><span class="sxs-lookup"><span data-stu-id="6efc4-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="6efc4-131">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di interrompere i mapping di entità:</span><span class="sxs-lookup"><span data-stu-id="6efc4-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="6efc4-132">*\[Accesso negato\], \[{"stato": 403,"origine":"","messaggio":"Errore dello scambio di token: l'utente non è autorizzato ad accedere alla connessione dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Il server remoto ha restituito un errore: (403) Accesso negato.*</span><span class="sxs-lookup"><span data-stu-id="6efc4-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="6efc4-133">Questo errore si verifica quando l'ambiente Common Data Service collegato non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="6efc4-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="6efc4-134">Per risolvere il problema, creare un ticket per il team di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="6efc4-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="6efc4-135">Collegare la traccia di rete in modo che il team di integrazione dei dati possa contrassegnare le mappe come **Non in esecuzione** nel back-end.</span><span class="sxs-lookup"><span data-stu-id="6efc4-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>
