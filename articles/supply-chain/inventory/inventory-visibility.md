---
title: Componente aggiuntivo Inventory Visibility
description: Questo argomento descrive come installare e configurare il componente aggiuntivo Inventory Visibility per Dynamics 365 Supply Chain Management.
author: sherry-zheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e6f7e0a3978bbf7e520f8cbcfd27c4cfe507777
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114672"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="f3165-103">Componente aggiuntivo Inventory Visibility</span><span class="sxs-lookup"><span data-stu-id="f3165-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f3165-104">Il componente aggiuntivo Inventory Visibility è un microservizio indipendente e altamente scalabile che consente il monitoraggio dell'inventario disponibile in tempo reale, fornendo così una visione globale della visibilità dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="f3165-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="f3165-105">Tutte le informazioni relative alle scorte disponibili vengono esportate nel servizio quasi in tempo reale tramite l'integrazione SQL di basso livello.</span><span class="sxs-lookup"><span data-stu-id="f3165-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="f3165-106">I sistemi esterni accedono al servizio tramite API RESTful per interrogare le informazioni sulle scorte disponibili su determinati set di dimensioni, recuperando così un elenco di posizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3165-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="f3165-107">Inventory Visibility è un microservizio basato su Microsoft Dataverse, il che significa che è possibile estenderlo creando Power Apps e applicando Power BI per fornire funzionalità personalizzate per soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="f3165-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="f3165-108">È anche possibile aggiornare l'indice per eseguire query sull'inventario.</span><span class="sxs-lookup"><span data-stu-id="f3165-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="f3165-109">Inventory Visibility fornisce opzioni di configurazione che consentono l'integrazione con più sistemi di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f3165-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="f3165-110">Supporta la dimensione dell'inventario standardizzata, l'estensibilità personalizzata e le quantità calcolate standardizzate e configurabili.</span><span class="sxs-lookup"><span data-stu-id="f3165-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="f3165-111">Questo argomento descrive come installare e configurare il componente aggiuntivo Inventory Visibility per Dynamics 365 Supply Chain Management e come utilizzare l'API.</span><span class="sxs-lookup"><span data-stu-id="f3165-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="f3165-112">Installare il componente aggiuntivo Inventory Visibility</span><span class="sxs-lookup"><span data-stu-id="f3165-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="f3165-113">È necessario installare il componente aggiuntivo Inventory Visibility utilizzando Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f3165-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="f3165-114">LCS è un portale di collaborazione che fornisce un ambiente e una serie di servizi regolarmente aggiornati che aiutano a gestire il ciclo di vita dell'applicazione delle app Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f3165-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="f3165-115">Per ulteriori informazioni, vedere [Risorse Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="f3165-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="f3165-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f3165-116">Prerequisites</span></span>

<span data-ttu-id="f3165-117">Prima di poter installare il componente aggiuntivo Inventory Visibility è necessario effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f3165-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="f3165-118">Ottenere un progetto di implementazione LCS con almeno un ambiente distribuito.</span><span class="sxs-lookup"><span data-stu-id="f3165-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="f3165-119">Generare le chiavi beta per l'offerta in LCS.</span><span class="sxs-lookup"><span data-stu-id="f3165-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="f3165-120">Abilitare le chiavi beta per l'offerta per l'utente in LCS.</span><span class="sxs-lookup"><span data-stu-id="f3165-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="f3165-121">Contattare il team del prodotto Microsoft Inventory Visibility e fornire un ID ambiente in cui si desidera distribuire il componente aggiuntivo Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="f3165-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="f3165-122">In caso di domande su questi prerequisiti, contattare il team del prodotto Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="f3165-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="f3165-123">Installare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="f3165-123">Install the add-in</span></span>

<span data-ttu-id="f3165-124">Per installare il componente aggiuntivo Inventory Visibility effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f3165-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="f3165-125">Accedere al portale [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="f3165-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="f3165-126">Nella home page, selezionare il progetto in cui è distribuito l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f3165-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="f3165-127">Nella pagina del progetto, selezionare l'ambiente in cui si desidera installare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="f3165-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="f3165-128">Nella pagina dell'ambiente, scorrere verso il basso fino a visualizzare la sezione **Componenti aggiuntivi per l'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="f3165-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="f3165-129">Se la sezione non è visibile, assicurarsi che le chiavi beta dei prerequisiti siano state completamente elaborate.</span><span class="sxs-lookup"><span data-stu-id="f3165-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="f3165-130">Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="f3165-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="f3165-131">![La pagina dell'ambiente in LCS](media/inventory-visibility-environment.png "La pagina dell'ambiente in LCS")</span><span class="sxs-lookup"><span data-stu-id="f3165-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="f3165-132">Selezionare il collegamento **Installare un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="f3165-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="f3165-133">Si apre un elenco di componenti aggiuntivi disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3165-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="f3165-134">Selezionare il servizio **Inventory** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="f3165-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="f3165-135">Nota: potrebbe ora essere elencato come **Componente aggiuntivo Inventory Visibility per Dynamics 365 Supply Chain Management**.</span><span class="sxs-lookup"><span data-stu-id="f3165-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="f3165-136">Immettere i valori per i seguenti campi per il proprio ambiente:</span><span class="sxs-lookup"><span data-stu-id="f3165-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="f3165-137">**ID applicazione AAD**</span><span class="sxs-lookup"><span data-stu-id="f3165-137">**AAD application ID**</span></span>
    - <span data-ttu-id="f3165-138">**ID tenant AAD**</span><span class="sxs-lookup"><span data-stu-id="f3165-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="f3165-139">![Pagina Impostazione del componente aggiuntivo](media/inventory-visibility-setup.png "Pagina Impostazione del componente aggiuntivo")</span><span class="sxs-lookup"><span data-stu-id="f3165-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="f3165-140">Accettare le condizioni selezionando la casella di controllo **Condizioni**.</span><span class="sxs-lookup"><span data-stu-id="f3165-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="f3165-141">Seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="f3165-141">Select **Install**.</span></span> <span data-ttu-id="f3165-142">Lo stato del componente aggiuntivo verrà visualizzato com e **Installazione**.</span><span class="sxs-lookup"><span data-stu-id="f3165-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="f3165-143">Al termine, aggiornare la pagina per vedere lo stato cambiare in **Installato**.</span><span class="sxs-lookup"><span data-stu-id="f3165-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="f3165-144">Ottenere un token per il servizio di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f3165-144">Get a security service token</span></span>

<span data-ttu-id="f3165-145">Ottieni un token del servizio di sicurezza effettuando le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="f3165-145">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="f3165-146">Accedere al portale di Azure e utilizzarlo per trovare `clientId` e `clientSecret` per la tua applicazione di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f3165-146">Sign in to Azure Portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="f3165-147">Recuperare un token Azure Active Directory (`aadToken`) inviando una richiesta HTTP con le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="f3165-147">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="f3165-148">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="f3165-148">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="f3165-149">**Metodo** - `GET`</span><span class="sxs-lookup"><span data-stu-id="f3165-149">**Method** - `GET`</span></span>
    - <span data-ttu-id="f3165-150">**Contenuto del corpo (dati del modulo)**:</span><span class="sxs-lookup"><span data-stu-id="f3165-150">**Body content (form data)**:</span></span>

        | <span data-ttu-id="f3165-151">chiave</span><span class="sxs-lookup"><span data-stu-id="f3165-151">key</span></span> | <span data-ttu-id="f3165-152">valore</span><span class="sxs-lookup"><span data-stu-id="f3165-152">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="f3165-153">client_id</span><span class="sxs-lookup"><span data-stu-id="f3165-153">client_id</span></span> | <span data-ttu-id="f3165-154">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="f3165-154">${aadAppId}</span></span> |
        | <span data-ttu-id="f3165-155">client_secret</span><span class="sxs-lookup"><span data-stu-id="f3165-155">client_secret</span></span> | <span data-ttu-id="f3165-156">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="f3165-156">${aadAppSecret}</span></span> |
        | <span data-ttu-id="f3165-157">grant_type</span><span class="sxs-lookup"><span data-stu-id="f3165-157">grant_type</span></span> | <span data-ttu-id="f3165-158">client_credentials</span><span class="sxs-lookup"><span data-stu-id="f3165-158">client_credentials</span></span> |
        | <span data-ttu-id="f3165-159">risorsa</span><span class="sxs-lookup"><span data-stu-id="f3165-159">resource</span></span> | <span data-ttu-id="f3165-160">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="f3165-160">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="f3165-161">Dovresti ricevere un `aadToken` in risposta, che assomiglia al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="f3165-161">You should receive an `aadToken` in response, which resembles the following example.</span></span>

    ```json
    {
    "token_type": "Bearer",
    "expires_in": "3599",
    "ext_expires_in": "3599",
    "expires_on": "1610466645",
    "not_before": "1610462745",
    "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
    "access_token": "eyJ0eX...8WQ"
    }
    ```

1. <span data-ttu-id="f3165-162">Formulare una richiesta JSON simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f3165-162">Formulate a JSON request that resembles the following:</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    <span data-ttu-id="f3165-163">Percorso:</span><span class="sxs-lookup"><span data-stu-id="f3165-163">Where:</span></span>
    - <span data-ttu-id="f3165-164">Il valore `client_assertion` deve essere `aadToken` ricevuto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="f3165-164">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="f3165-165">Il valore `context` deve essere l'ID dell'ambiente in cui si desidera distribuire il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="f3165-165">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="f3165-166">Impostare tutti gli altri valori come mostrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="f3165-166">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="f3165-167">Inviare una richiesta HTTP con le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="f3165-167">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="f3165-168">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="f3165-168">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="f3165-169">**Metodo** - `POST`</span><span class="sxs-lookup"><span data-stu-id="f3165-169">**Method** - `POST`</span></span>
    - <span data-ttu-id="f3165-170">**Intestazione HTTP**: includere la versione API (la chiave è `Api-Version` e il valore è `1.0`)</span><span class="sxs-lookup"><span data-stu-id="f3165-170">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="f3165-171">**Contenuto del corpo**: includi la richiesta JSON che hai creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="f3165-171">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="f3165-172">Viene restituito un `access_token` in risposta.</span><span class="sxs-lookup"><span data-stu-id="f3165-172">You will get an `access_token` in response.</span></span> <span data-ttu-id="f3165-173">Questo è ciò di cui si ha bisogno come token di connessione per chiamare l'API di Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="f3165-173">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="f3165-174">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="f3165-174">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="f3165-175">Disinstallare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="f3165-175">Uninstall the add-in</span></span>

<span data-ttu-id="f3165-176">Per disinstallare il componente aggiuntivo, selezionar e **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="f3165-176">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="f3165-177">Aggiornare LCS e il componente aggiuntivo Inventory Visibility verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="f3165-177">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="f3165-178">Il processo di disinstallazione rimuoverà la registrazione del componente aggiuntivo e avvierà anche un processo per pulire tutti i dati aziendali archiviati nel servizio.</span><span class="sxs-lookup"><span data-stu-id="f3165-178">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="f3165-179">API pubblica del componente aggiuntivo Inventory Visibility</span><span class="sxs-lookup"><span data-stu-id="f3165-179">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="f3165-180">L'API REST pubblica del componente aggiuntivo Inventory Visibility presenta diversi endpoint specifici di integrazione.</span><span class="sxs-lookup"><span data-stu-id="f3165-180">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="f3165-181">Supporta tre principali tipi di interazione:</span><span class="sxs-lookup"><span data-stu-id="f3165-181">It supports three main interaction types:</span></span>

- <span data-ttu-id="f3165-182">Inserimento delle modifiche delle scorte disponibili al componente aggiuntivo da un sistema esterno.</span><span class="sxs-lookup"><span data-stu-id="f3165-182">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="f3165-183">Interrogazione delle quantità disponibili correnti da un sistema esterno.</span><span class="sxs-lookup"><span data-stu-id="f3165-183">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="f3165-184">Sincronizzazione automatica con le scorte disponibili di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f3165-184">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="f3165-185">La sincronizzazione automatica non fa parte dell'API pubblica ma viene invece gestita in background per gli ambienti che hanno abilitato il componente aggiuntivo Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="f3165-185">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="f3165-186">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="f3165-186">Authentication</span></span>

<span data-ttu-id="f3165-187">Il token di sicurezza della piattaforma viene utilizzato per chiamare il componente aggiuntivo Inventory Visibility, quindi è necessario generare un token Azure Active Directory utilizzando l'applicazione Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3165-187">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="f3165-188">Per ulteriori informazioni su come ottenere il token di sicurezza, vedere [Installare il componente aggiuntivo Inventory Visibility](#install-add-in).</span><span class="sxs-lookup"><span data-stu-id="f3165-188">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="f3165-189">Configurare l'API di Inventory Visibility</span><span class="sxs-lookup"><span data-stu-id="f3165-189">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="f3165-190">Prima di utilizzare il servizio, è necessario completare le configurazioni descritte nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f3165-190">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="f3165-191">La configurazione può variare in base ai dettagli del proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="f3165-191">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="f3165-192">Comprende principalmente quattro parti:</span><span class="sxs-lookup"><span data-stu-id="f3165-192">It primarily includes four parts:</span></span>

- [<span data-ttu-id="f3165-193">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="f3165-193">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="f3165-194">Configurazioni delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="f3165-194">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="f3165-195">Indicizzazione</span><span class="sxs-lookup"><span data-stu-id="f3165-195">Indexing</span></span>](#indexing)
- [<span data-ttu-id="f3165-196">Misura personalizzata</span><span class="sxs-lookup"><span data-stu-id="f3165-196">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="f3165-197">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="f3165-197">Partitioning</span></span>

<span data-ttu-id="f3165-198">Il partizionamento può influenzare in modo significativo le prestazioni dell'API di Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="f3165-198">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="f3165-199">È una buona idea definire uno schema che consenta piccoli raggruppamenti di dati pur consentendo query di dati significative.</span><span class="sxs-lookup"><span data-stu-id="f3165-199">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="f3165-200">L'elemento `organizationId` (`dataAreaId` in Supply Chain Management) farà sempre parte del partizionamento e, per impostazione predefinita, Inventory Visibility è impostato su partizionamento per dimensioni come *Sito + Posizione*.</span><span class="sxs-lookup"><span data-stu-id="f3165-200">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="f3165-201">Ciò significa che il servizio deve essere sempre interrogato con queste dimensioni definite sui filtri.</span><span class="sxs-lookup"><span data-stu-id="f3165-201">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="f3165-202">*Sito* e *Posizione* sono due dimensioni predefinite generali in Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="f3165-202">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="f3165-203">In Supply Chain Management, queste dimensioni vengono chiamate *Sito* (`InventSiteId`) e *Magazzino* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="f3165-203">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="f3165-204">Configurazioni delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="f3165-204">Dimension configurations</span></span>

<span data-ttu-id="f3165-205">Inventory Visibility fornirà un elenco di dimensioni predefinite generali per abilitare l'integrazione di più sistemi di origine.</span><span class="sxs-lookup"><span data-stu-id="f3165-205">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="f3165-206">La tabella seguente elenca le dimensioni dell'inventario che saranno i nomi delle dimensioni predefinite in Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="f3165-206">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="f3165-207">Tipo di dimensione</span><span class="sxs-lookup"><span data-stu-id="f3165-207">Dimension type</span></span> | <span data-ttu-id="f3165-208">Nome dimensione</span><span class="sxs-lookup"><span data-stu-id="f3165-208">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="f3165-209">Prodotto</span><span class="sxs-lookup"><span data-stu-id="f3165-209">Product</span></span> | `ColorId` |
| <span data-ttu-id="f3165-210">Prodotto</span><span class="sxs-lookup"><span data-stu-id="f3165-210">Product</span></span> | `SizeId` |
| <span data-ttu-id="f3165-211">Prodotto</span><span class="sxs-lookup"><span data-stu-id="f3165-211">Product</span></span> | `StyleId` |
| <span data-ttu-id="f3165-212">Prodotto</span><span class="sxs-lookup"><span data-stu-id="f3165-212">Product</span></span> | `ConfigId` |
| <span data-ttu-id="f3165-213">Tracciabilità</span><span class="sxs-lookup"><span data-stu-id="f3165-213">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="f3165-214">Tracciabilità</span><span class="sxs-lookup"><span data-stu-id="f3165-214">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="f3165-215">Posizione</span><span class="sxs-lookup"><span data-stu-id="f3165-215">Location</span></span> | `LocationId` |
| <span data-ttu-id="f3165-216">Posizione</span><span class="sxs-lookup"><span data-stu-id="f3165-216">Location</span></span> | `SiteId` |
| <span data-ttu-id="f3165-217">Stato inventario</span><span class="sxs-lookup"><span data-stu-id="f3165-217">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="f3165-218">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="f3165-218">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="f3165-219">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="f3165-219">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="f3165-220">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="f3165-220">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="f3165-221">Il tipo di dimensione elencato nella tabella precedente è solo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f3165-221">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="f3165-222">Non è necessario definire il tipo di dimensione in Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="f3165-222">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="f3165-223">Se esiste una dimensione personalizzata che diventare un valore predefinito quando viene utilizzata da Inventory Visibility, è possibile configurare il nome **Dimensione personalizzata** in Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="f3165-223">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="f3165-224">I sistemi esterni accedono a Inventory Visibility tramite le API RESTful che consentono di interrogare le informazioni disponibili su determinati set di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f3165-224">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="f3165-225">Per l'integrazione, Inventory Visibility consente di configurare l'*origine dati del canale esterno* e la dimensione di origine sulle *dimensioni di destinazione* in Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="f3165-225">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="f3165-226">Le dimensioni di destinazione deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3165-226">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="f3165-227">Dimensioni predefinite in Inventory Visibility</span><span class="sxs-lookup"><span data-stu-id="f3165-227">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="f3165-228">Dimensioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="f3165-228">Custom dimensions</span></span>

<span data-ttu-id="f3165-229">Lo scopo della configurazione delle dimensioni è standardizzare l'integrazione multi-sistema per la query sulle dimensioni e l'evento di registrazione con le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f3165-229">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="f3165-230">Indicizzazione</span><span class="sxs-lookup"><span data-stu-id="f3165-230">Indexing</span></span>

<span data-ttu-id="f3165-231">La maggior parte delle volte, la query delle scorte disponibili non sarà solo sul livello "totale" più alto, ma si potrebbe voler vedere i risultati aggregati in base alle dimensioni dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="f3165-231">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="f3165-232">Inventory Visibility offre flessibilità consentendo di impostare gli indici, che si basano sulla dimensione o sulla combinazione delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f3165-232">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="f3165-233">Al momento, è possibile configurare solo fino a un massimo di cinque indici.</span><span class="sxs-lookup"><span data-stu-id="f3165-233">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="f3165-234">È necessario considerare attentamente quale dimensione o combinazione di dimensioni si utilizzerà prima dell'implementazione per assicurarsi che soddisfi le esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="f3165-234">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="f3165-235">Ad esempio, se si desidera eseguire query sui prodotti come segue:</span><span class="sxs-lookup"><span data-stu-id="f3165-235">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="f3165-236">Query delle scorte del prodotto aggregato per dimensioni *Colore* e *Dimensione*.</span><span class="sxs-lookup"><span data-stu-id="f3165-236">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="f3165-237">In alcuni casi, si desidera solo eseguire una query sul prodotto in totale.</span><span class="sxs-lookup"><span data-stu-id="f3165-237">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="f3165-238">Sarebbero disponibili due indici definiti come segue:</span><span class="sxs-lookup"><span data-stu-id="f3165-238">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="f3165-239">La parentesi vuota si aggregherà in base all'ID del prodotto all'interno della partizione.</span><span class="sxs-lookup"><span data-stu-id="f3165-239">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="f3165-240">L'indicizzazione definisce come raggruppare i risultati in base all'impostazione della query `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="f3165-240">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="f3165-241">In questo caso se non si definiscono valori `groupBy` si ottengono i totali per `productid`.</span><span class="sxs-lookup"><span data-stu-id="f3165-241">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="f3165-242">Altrimenti se si definisce `groupBy` come `groupBy=ColorId&groupBy=SizeId`, verranno restituite più righe, in base alle diverse combinazioni di colori e dimensioni nel sistema.</span><span class="sxs-lookup"><span data-stu-id="f3165-242">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="f3165-243">È possibile inserire i criteri della query nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="f3165-243">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="f3165-244">Ecco una query di esempio sul prodotto con combinazione di colore e dimensione.</span><span class="sxs-lookup"><span data-stu-id="f3165-244">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a><span data-ttu-id="f3165-245">Misura personalizzata</span><span class="sxs-lookup"><span data-stu-id="f3165-245">Custom measurement</span></span>

<span data-ttu-id="f3165-246">Le quantità di misura predefinite sono collegate a Supply Chain Management, tuttavia potrebbe essere necessario disporre di una quantità composta da una combinazione delle misure predefinite.</span><span class="sxs-lookup"><span data-stu-id="f3165-246">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="f3165-247">Per fare ciò, è possibile avere una configurazione di quantità personalizzate, che verranno aggiunte all'output delle query disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3165-247">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="f3165-248">La funzionalità consente semplicemente di definire un insieme di misure che verranno aggiunte, e/o un insieme di misure che verranno sottratte, in modo da ottenere dalla misura personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f3165-248">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="f3165-249">Ad esempio, con la seguente condizione di query, si configura la quantità di misura personalizzata come `MyCustomAvailableforReservation` per essere utilizzata dal sistema di consumo.</span><span class="sxs-lookup"><span data-stu-id="f3165-249">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="f3165-250">Sistema di consumo</span><span class="sxs-lookup"><span data-stu-id="f3165-250">Consumption system</span></span> | <span data-ttu-id="f3165-251">Misure calcolate</span><span class="sxs-lookup"><span data-stu-id="f3165-251">Calculated measurers</span></span> | <span data-ttu-id="f3165-252">Origine dati</span><span class="sxs-lookup"><span data-stu-id="f3165-252">Data source</span></span> | <span data-ttu-id="f3165-253">Modificatore</span><span class="sxs-lookup"><span data-stu-id="f3165-253">Modifier</span></span> | <span data-ttu-id="f3165-254">Tipo di calcolo del modificatore</span><span class="sxs-lookup"><span data-stu-id="f3165-254">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="f3165-255">Addizione</span><span class="sxs-lookup"><span data-stu-id="f3165-255">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="f3165-256">Addizione</span><span class="sxs-lookup"><span data-stu-id="f3165-256">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="f3165-257">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="f3165-257">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="f3165-258">Addizione</span><span class="sxs-lookup"><span data-stu-id="f3165-258">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="f3165-259">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="f3165-259">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="f3165-260">Addizione</span><span class="sxs-lookup"><span data-stu-id="f3165-260">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="f3165-261">Addizione</span><span class="sxs-lookup"><span data-stu-id="f3165-261">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="f3165-262">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="f3165-262">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="f3165-263">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="f3165-263">Subtraction</span></span> |

<span data-ttu-id="f3165-264">Con ciò, la query sulla quantità di misura personalizzata restituirà il seguente output.</span><span class="sxs-lookup"><span data-stu-id="f3165-264">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="f3165-265">L'output `MyCustomAvailableforReservation` si basa sull'impostazione del calcolo nelle misure personalizzate come:</span><span class="sxs-lookup"><span data-stu-id="f3165-265">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="f3165-266">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="f3165-266">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="f3165-267">Registrazione delle modifiche delle scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="f3165-267">Posting on-hand changes</span></span>

<span data-ttu-id="f3165-268">L'URL esatto in cui verrà pubblicato l'evento dipenderà dalla regione geografica.</span><span class="sxs-lookup"><span data-stu-id="f3165-268">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="f3165-269">Avrà il formato:</span><span class="sxs-lookup"><span data-stu-id="f3165-269">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="f3165-270">Una volta autenticato, questo URL può essere utilizzato insieme al metodo HTTP `POST` per inviare al servizio eventi di modifica delle scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3165-270">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="f3165-271">Un'intestazione speciale viene utilizzata per comunicare con i servizi Dynamics 365 tramite richieste HTTP, indicando l'ID ambiente dell'istanza di Supply Chain Management a cui sono collegati i dati.</span><span class="sxs-lookup"><span data-stu-id="f3165-271">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="f3165-272">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f3165-272">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="f3165-273">Registrazione delle modifiche delle scorte disponibili - esempio di query 1</span><span class="sxs-lookup"><span data-stu-id="f3165-273">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="f3165-274">Questo esempio mostra uno scenario in cui verrà impostata la configurazione della dimensione in Power Apps.</span><span class="sxs-lookup"><span data-stu-id="f3165-274">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="f3165-275">Utilizzare la seguente query per configurare la mappatura delle dimensioni in Power Apps:</span><span class="sxs-lookup"><span data-stu-id="f3165-275">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="f3165-276">Ora è possibile specificare `dimensionDataSource` e utilizzare le dimensioni personalizzate nelle query.</span><span class="sxs-lookup"><span data-stu-id="f3165-276">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="f3165-277">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="f3165-277">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="f3165-278">Registrazione delle modifiche delle scorte disponibili - esempio di query 2</span><span class="sxs-lookup"><span data-stu-id="f3165-278">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="f3165-279">Questo esempio mostra uno scenario in cui non sono impostate mappature per la configurazione della dimensione in Power Apps, quindi la registrazione deve utilizzare anche le dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="f3165-279">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="f3165-280">Tutte le dimensioni devono essere dimensioni di base quando il campo `dimensionDataSource` è nullo, vuoto o spazio bianco.</span><span class="sxs-lookup"><span data-stu-id="f3165-280">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="f3165-281">Proprietà dei campi del documento JSON</span><span class="sxs-lookup"><span data-stu-id="f3165-281">JSON document field properties</span></span>

<span data-ttu-id="f3165-282">I campi degli esempi di query JSON forniti in precedenza hanno le proprietà elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f3165-282">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="f3165-283">ID campo</span><span class="sxs-lookup"><span data-stu-id="f3165-283">Field ID</span></span> | <span data-ttu-id="f3165-284">descrizione</span><span class="sxs-lookup"><span data-stu-id="f3165-284">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="f3165-285">Un ID univoco per l'evento di modifica specifico.</span><span class="sxs-lookup"><span data-stu-id="f3165-285">A unique ID for the specific change event.</span></span> <span data-ttu-id="f3165-286">Questo ID viene utilizzato per garantire che se la comunicazione con il servizio non riesce durante la registrazione, il reinvio dell'evento non comporta il doppio conteggio dello stesso evento nel sistema.</span><span class="sxs-lookup"><span data-stu-id="f3165-286">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="f3165-287">L'identificatore dell'organizzazione collegata all'evento.</span><span class="sxs-lookup"><span data-stu-id="f3165-287">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="f3165-288">Viene mappato agli ID area dati o alle organizzazioni di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f3165-288">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="f3165-289">L'identificatore del prodotto in questione.</span><span class="sxs-lookup"><span data-stu-id="f3165-289">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="f3165-290">La quantità in base alla quale è necessario modificare la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="f3165-290">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="f3165-291">Se, ad esempio, 10 nuovi bagel venissero aggiunti a uno scaffale, questo valore sarebbe 10.</span><span class="sxs-lookup"><span data-stu-id="f3165-291">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="f3165-292">Se 3 bagel venissero poi rimossi dallo scaffale o venduti, questo valore sarebbe -3.</span><span class="sxs-lookup"><span data-stu-id="f3165-292">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="f3165-293">L'origine dati delle dimensioni utilizzate nella query e nell'evento di modifica della registrazione.</span><span class="sxs-lookup"><span data-stu-id="f3165-293">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="f3165-294">Se si specifica l'origine dati, è possibile utilizzare le dimensioni personalizzate dell'origine dati specificata.</span><span class="sxs-lookup"><span data-stu-id="f3165-294">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="f3165-295">Con la configurazione delle dimensioni, Inventory Visibility può mappare le dimensioni personalizzate alle dimensioni predefinite generali.</span><span class="sxs-lookup"><span data-stu-id="f3165-295">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="f3165-296">Se `dimensionDataSource` non è specificato, è possibile utilizzare solo le dimensioni predefinite generali nelle query.</span><span class="sxs-lookup"><span data-stu-id="f3165-296">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="f3165-297">Un insieme dinamico di coppie chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="f3165-297">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="f3165-298">Questi verranno mappati ad alcune dimensioni in Supply Chain Management, ma è possibile anche aggiungere dimensioni personalizzate (come *origine*) che può indicare se l'evento proveniva da Supply Chain Management o da un sistema esterno.</span><span class="sxs-lookup"><span data-stu-id="f3165-298">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="f3165-299">Interrogazione delle quantità disponibili correnti</span><span class="sxs-lookup"><span data-stu-id="f3165-299">Querying current on-hand</span></span>

<span data-ttu-id="f3165-300">L'endpoint per l'interrogazione delle quantità disponibili correnti avrà un URL simile:</span><span class="sxs-lookup"><span data-stu-id="f3165-300">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="f3165-301">Sarà interrogato con il metodo HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="f3165-301">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="f3165-302">Esempio di query delle quantità disponibili correnti 1</span><span class="sxs-lookup"><span data-stu-id="f3165-302">Current on-hand query example 1</span></span>

<span data-ttu-id="f3165-303">Questo esempio mostra uno scenario in cui è già stata impostata la configurazione della dimensione in Power Apps.</span><span class="sxs-lookup"><span data-stu-id="f3165-303">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="f3165-304">Utilizzare la seguente query per configurare la mappatura delle dimensioni in Power Apps:</span><span class="sxs-lookup"><span data-stu-id="f3165-304">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="f3165-305">Ora è possibile specificare `dimensionDataSource` e utilizzare le dimensioni personalizzate nelle query.</span><span class="sxs-lookup"><span data-stu-id="f3165-305">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="f3165-306">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="f3165-306">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="f3165-307">È possibile specificare `DimensionDataSource` in `filters` e specificare le dimensioni personalizzate in `filters` e `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="f3165-307">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="f3165-308">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="f3165-308">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="f3165-309">Esempio di query delle quantità disponibili correnti 2</span><span class="sxs-lookup"><span data-stu-id="f3165-309">Current on-hand query example 2</span></span>

<span data-ttu-id="f3165-310">Questo esempio mostra uno scenario in cui non sono impostate mappature per la configurazione della dimensione in Power Apps, quindi la registrazione deve utilizzare anche le dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="f3165-310">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="f3165-311">Tutte le dimensioni devono essere dimensioni di base quando il campo `dimensionDataSource` in `filters` è nullo, vuoto o spazio bianco.</span><span class="sxs-lookup"><span data-stu-id="f3165-311">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="f3165-312">Esempio di risultato restituito</span><span class="sxs-lookup"><span data-stu-id="f3165-312">Example return result</span></span>

<span data-ttu-id="f3165-313">Le query mostrate negli esempi precedenti potrebbero restituire un risultato come questo.</span><span class="sxs-lookup"><span data-stu-id="f3165-313">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="f3165-314">Notare che i campi delle quantità sono strutturati come un dizionario di misure e dei valori associati.</span><span class="sxs-lookup"><span data-stu-id="f3165-314">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
