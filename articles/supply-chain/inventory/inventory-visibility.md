---
title: Componente aggiuntivo Inventory Visibility
description: Questo argomento descrive come installare e configurare il componente aggiuntivo Inventory Visibility per Dynamics 365 Supply Chain Management.
author: chuzheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2976153a6a7e4b4130e8f7673ed128945aeabf65
ms.sourcegitcommit: 03c2e1717b31e4c17ee7bb9004d2ba8cf379a036
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/24/2020
ms.locfileid: "4625067"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="cf747-103">Componente aggiuntivo Inventory Visibility</span><span class="sxs-lookup"><span data-stu-id="cf747-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="cf747-104">Il componente aggiuntivo Inventory Visibility è un microservizio indipendente e altamente scalabile che consente il monitoraggio dell'inventario disponibile in tempo reale, fornendo così una visione globale della visibilità dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="cf747-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="cf747-105">Tutte le informazioni relative alle scorte disponibili vengono esportate nel servizio quasi in tempo reale tramite l'integrazione SQL di basso livello.</span><span class="sxs-lookup"><span data-stu-id="cf747-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="cf747-106">I sistemi esterni accedono al servizio tramite API RESTful per interrogare le informazioni sulle scorte disponibili su determinati set di dimensioni, recuperando così un elenco di posizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="cf747-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="cf747-107">Inventory Visibility è un microservizio basato su Common Data Service, il che significa che è possibile estenderlo creando Power Apps e applicando Power BI per fornire funzionalità personalizzate per soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="cf747-107">Inventory Visibility is a microservice built on the Common Data Service, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="cf747-108">È anche possibile aggiornare l'indice per eseguire query sull'inventario.</span><span class="sxs-lookup"><span data-stu-id="cf747-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="cf747-109">Inventory Visibility fornisce opzioni di configurazione che consentono l'integrazione con più sistemi di terze parti.</span><span class="sxs-lookup"><span data-stu-id="cf747-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="cf747-110">Supporta la dimensione dell'inventario standardizzata, l'estensibilità personalizzata e le quantità calcolate standardizzate e configurabili.</span><span class="sxs-lookup"><span data-stu-id="cf747-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="cf747-111">Questo argomento descrive come installare e configurare il componente aggiuntivo Inventory Visibility per Dynamics 365 Supply Chain Management e come utilizzare l'API.</span><span class="sxs-lookup"><span data-stu-id="cf747-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="cf747-112">Installare il componente aggiuntivo Inventory Visibility</span><span class="sxs-lookup"><span data-stu-id="cf747-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="cf747-113">È necessario installare il componente aggiuntivo Inventory Visibility utilizzando Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="cf747-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="cf747-114">LCS è un portale di collaborazione che fornisce un ambiente e una serie di servizi regolarmente aggiornati che aiutano a gestire il ciclo di vita dell'applicazione delle app Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cf747-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="cf747-115">Per ulteriori informazioni, vedere [Risorse Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="cf747-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="cf747-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cf747-116">Prerequisites</span></span>

<span data-ttu-id="cf747-117">Prima di poter installare il componente aggiuntivo Inventory Visibility è necessario effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cf747-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="cf747-118">Ottenere un progetto di implementazione LCS con almeno un ambiente distribuito.</span><span class="sxs-lookup"><span data-stu-id="cf747-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="cf747-119">Generare le chiavi beta per l'offerta in LCS.</span><span class="sxs-lookup"><span data-stu-id="cf747-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="cf747-120">Abilitare le chiavi beta per l'offerta per l'utente in LCS.</span><span class="sxs-lookup"><span data-stu-id="cf747-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="cf747-121">Contattare il team del prodotto Microsoft Inventory Visibility e fornire un ID ambiente in cui si desidera distribuire il componente aggiuntivo Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="cf747-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="cf747-122">In caso di domande su questi prerequisiti, contattare il team del prodotto Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="cf747-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="cf747-123">Installare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="cf747-123">Install the add-in</span></span>

<span data-ttu-id="cf747-124">Per installare il componente aggiuntivo Inventory Visibility effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cf747-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="cf747-125">Accedere al portale [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="cf747-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="cf747-126">Nella home page, selezionare il progetto in cui è distribuito l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="cf747-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="cf747-127">Nella pagina del progetto, selezionare l'ambiente in cui si desidera installare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="cf747-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="cf747-128">Nella pagina dell'ambiente, scorrere verso il basso fino a visualizzare la sezione **Componenti aggiuntivi per l'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="cf747-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="cf747-129">Se la sezione non è visibile, assicurarsi che le chiavi beta dei prerequisiti siano state completamente elaborate.</span><span class="sxs-lookup"><span data-stu-id="cf747-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="cf747-130">Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="cf747-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="cf747-131">![La pagina dell'ambiente in LCS](media/inventory-visibility-environment.png "La pagina dell'ambiente in LCS")</span><span class="sxs-lookup"><span data-stu-id="cf747-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="cf747-132">Selezionare il collegamento **Installare un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="cf747-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="cf747-133">Si apre un elenco di componenti aggiuntivi disponibili.</span><span class="sxs-lookup"><span data-stu-id="cf747-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="cf747-134">Selezionare il servizio **Inventory** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="cf747-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="cf747-135">Nota: potrebbe ora essere elencato come **Componente aggiuntivo Inventory Visibility per Dynamics 365 Supply Chain Management**.</span><span class="sxs-lookup"><span data-stu-id="cf747-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="cf747-136">Immettere i valori per i seguenti campi per il proprio ambiente:</span><span class="sxs-lookup"><span data-stu-id="cf747-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="cf747-137">**ID applicazione AAD**</span><span class="sxs-lookup"><span data-stu-id="cf747-137">**AAD application ID**</span></span>
    - <span data-ttu-id="cf747-138">**ID tenant AAD**</span><span class="sxs-lookup"><span data-stu-id="cf747-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="cf747-139">![Pagina Impostazione del componente aggiuntivo](media/inventory-visibility-setup.png "Pagina Impostazione del componente aggiuntivo")</span><span class="sxs-lookup"><span data-stu-id="cf747-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="cf747-140">Accettare le condizioni selezionando la casella di controllo **Condizioni**.</span><span class="sxs-lookup"><span data-stu-id="cf747-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="cf747-141">Seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="cf747-141">Select **Install**.</span></span> <span data-ttu-id="cf747-142">Lo stato del componente aggiuntivo verrà visualizzato com e **Installazione**.</span><span class="sxs-lookup"><span data-stu-id="cf747-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="cf747-143">Al termine, aggiornare la pagina per vedere lo stato cambiare in **Installato**.</span><span class="sxs-lookup"><span data-stu-id="cf747-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="cf747-144">Ottenere un token per il servizio di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cf747-144">Get a security service token</span></span>

<span data-ttu-id="cf747-145">Per ottenere un token del servizio di sicurezza, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="cf747-145">To get a security service token, do the following:</span></span>

1. <span data-ttu-id="cf747-146">Recuperare `aadToken` e chiamare l'endpoint: https://securityservice.operations365.dynamics.com/token.</span><span class="sxs-lookup"><span data-stu-id="cf747-146">Get your `aadToken` and call the endpoint: https://securityservice.operations365.dynamics.com/token.</span></span>
1. <span data-ttu-id="cf747-147">Sostituire `client_assertion` nel corpo con `aadToken`.</span><span class="sxs-lookup"><span data-stu-id="cf747-147">Replace the `client_assertion` in the body with your `aadToken`.</span></span>
1. <span data-ttu-id="cf747-148">Sostituire il contesto nel corpo con l'ambiente in cui si desidera distribuire il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="cf747-148">Replace the context in the body with the environment where you want to deploy the add-in.</span></span>
1. <span data-ttu-id="cf747-149">Sostituire l'ambito nel corpo con il seguente:</span><span class="sxs-lookup"><span data-stu-id="cf747-149">Replace the scope in the body with the following:</span></span>

    - <span data-ttu-id="cf747-150">Ambito per MCK - "https://inventoryservice.operations365.dynamics.cn/.default"</span><span class="sxs-lookup"><span data-stu-id="cf747-150">Scope for MCK - "https://inventoryservice.operations365.dynamics.cn/.default"</span></span>  
    <span data-ttu-id="cf747-151">L'ID applicazione e l'ID tenant Azure Active Directory sono disponibili in `appsettings.mck.json`.</span><span class="sxs-lookup"><span data-stu-id="cf747-151">(You can find the Azure Active Directory application ID and tenant ID for MCK in `appsettings.mck.json`.)</span></span>
    - <span data-ttu-id="cf747-152">Ambito per PROD - "https://inventoryservice.operations365.dynamics.com/.default"</span><span class="sxs-lookup"><span data-stu-id="cf747-152">Scope for PROD - "https://inventoryservice.operations365.dynamics.com/.default"</span></span>  
    <span data-ttu-id="cf747-153">L'ID applicazione e l'ID tenant Azure Active Directory sono disponibili in `appsettings.prod.json`.</span><span class="sxs-lookup"><span data-stu-id="cf747-153">(You can find the Azure Active Directory application ID and tenant ID for PROD in `appsettings.prod.json`.)</span></span>

    <span data-ttu-id="cf747-154">Il risultato sarà simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cf747-154">The result should resemble the following example.</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{**Your_AADToken**}",
        "scope":"**https://inventoryservice.operations365.dynamics.com/.default**",
        "context": "**5dbf6cc8-255e-4de2-8a25-2101cd5649b4**",
        "context_type": "finops-env"
    }
    ```

1. <span data-ttu-id="cf747-155">Viene restituito un `access_token` in risposta.</span><span class="sxs-lookup"><span data-stu-id="cf747-155">You will get an `access_token` in response.</span></span> <span data-ttu-id="cf747-156">Questo è ciò di cui si ha bisogno come token di connessione per chiamare l'API di Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="cf747-156">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="cf747-157">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="cf747-157">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="cf747-158">Disinstallare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="cf747-158">Uninstall the add-in</span></span>

<span data-ttu-id="cf747-159">Per disinstallare il componente aggiuntivo, selezionar e **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="cf747-159">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="cf747-160">Aggiornare LCS e il componente aggiuntivo Inventory Visibility verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="cf747-160">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="cf747-161">Il processo di disinstallazione rimuoverà la registrazione del componente aggiuntivo e avvierà anche un processo per pulire tutti i dati aziendali archiviati nel servizio.</span><span class="sxs-lookup"><span data-stu-id="cf747-161">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="cf747-162">API pubblica del componente aggiuntivo Inventory Visibility</span><span class="sxs-lookup"><span data-stu-id="cf747-162">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="cf747-163">L'API REST pubblica del componente aggiuntivo Inventory Visibility presenta diversi endpoint specifici di integrazione.</span><span class="sxs-lookup"><span data-stu-id="cf747-163">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="cf747-164">Supporta tre principali tipi di interazione:</span><span class="sxs-lookup"><span data-stu-id="cf747-164">It supports three main interaction types:</span></span>

- <span data-ttu-id="cf747-165">Inserimento delle modifiche delle scorte disponibili al componente aggiuntivo da un sistema esterno.</span><span class="sxs-lookup"><span data-stu-id="cf747-165">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="cf747-166">Interrogazione delle quantità disponibili correnti da un sistema esterno.</span><span class="sxs-lookup"><span data-stu-id="cf747-166">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="cf747-167">Sincronizzazione automatica con le scorte disponibili di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cf747-167">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="cf747-168">La sincronizzazione automatica non fa parte dell'API pubblica ma viene invece gestita in background per gli ambienti che hanno abilitato il componente aggiuntivo Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="cf747-168">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="cf747-169">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="cf747-169">Authentication</span></span>

<span data-ttu-id="cf747-170">Il token di sicurezza della piattaforma viene utilizzato per chiamare il componente aggiuntivo Inventory Visibility, quindi è necessario generare un token Azure Active Directory utilizzando l'applicazione Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cf747-170">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="cf747-171">Per ulteriori informazioni su come ottenere il token di sicurezza, vedere [Installare il componente aggiuntivo Inventory Visibility](#install-add-in).</span><span class="sxs-lookup"><span data-stu-id="cf747-171">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="cf747-172">Configurare l'API di Inventory Visibility</span><span class="sxs-lookup"><span data-stu-id="cf747-172">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="cf747-173">Prima di utilizzare il servizio, è necessario completare le configurazioni descritte nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="cf747-173">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="cf747-174">La configurazione può variare in base ai dettagli del proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="cf747-174">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="cf747-175">Comprende principalmente quattro parti:</span><span class="sxs-lookup"><span data-stu-id="cf747-175">It primarily includes four parts:</span></span>

- [<span data-ttu-id="cf747-176">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="cf747-176">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="cf747-177">Configurazioni delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="cf747-177">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="cf747-178">Indicizzazione</span><span class="sxs-lookup"><span data-stu-id="cf747-178">Indexing</span></span>](#indexing)
- [<span data-ttu-id="cf747-179">Misura personalizzata</span><span class="sxs-lookup"><span data-stu-id="cf747-179">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="cf747-180">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="cf747-180">Partitioning</span></span>

<span data-ttu-id="cf747-181">Il partizionamento può influenzare in modo significativo le prestazioni dell'API di Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="cf747-181">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="cf747-182">È una buona idea definire uno schema che consenta piccoli raggruppamenti di dati pur consentendo query di dati significative.</span><span class="sxs-lookup"><span data-stu-id="cf747-182">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="cf747-183">L'elemento `organizationId` (`dataAreaId` in Supply Chain Management) farà sempre parte del partizionamento e, per impostazione predefinita, Inventory Visibility è impostato su partizionamento per dimensioni come *Sito + Posizione*.</span><span class="sxs-lookup"><span data-stu-id="cf747-183">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="cf747-184">Ciò significa che il servizio deve essere sempre interrogato con queste dimensioni definite sui filtri.</span><span class="sxs-lookup"><span data-stu-id="cf747-184">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="cf747-185">*Sito* e *Posizione* sono due dimensioni predefinite generali in Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="cf747-185">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="cf747-186">In Supply Chain Management, queste dimensioni vengono chiamate *Sito* (`InventSiteId`) e *Magazzino* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="cf747-186">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="cf747-187">Configurazioni delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="cf747-187">Dimension configurations</span></span>

<span data-ttu-id="cf747-188">Inventory Visibility fornirà un elenco di dimensioni predefinite generali per abilitare l'integrazione di più sistemi di origine.</span><span class="sxs-lookup"><span data-stu-id="cf747-188">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="cf747-189">La tabella seguente elenca le dimensioni dell'inventario che saranno i nomi delle dimensioni predefinite in Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="cf747-189">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="cf747-190">Tipo di dimensione</span><span class="sxs-lookup"><span data-stu-id="cf747-190">Dimension type</span></span> | <span data-ttu-id="cf747-191">Nome dimensione</span><span class="sxs-lookup"><span data-stu-id="cf747-191">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="cf747-192">Prodotto</span><span class="sxs-lookup"><span data-stu-id="cf747-192">Product</span></span> | `ColorId` |
| <span data-ttu-id="cf747-193">Prodotto</span><span class="sxs-lookup"><span data-stu-id="cf747-193">Product</span></span> | `SizeId` |
| <span data-ttu-id="cf747-194">Prodotto</span><span class="sxs-lookup"><span data-stu-id="cf747-194">Product</span></span> | `StyleId` |
| <span data-ttu-id="cf747-195">Prodotto</span><span class="sxs-lookup"><span data-stu-id="cf747-195">Product</span></span> | `ConfigId` |
| <span data-ttu-id="cf747-196">Tracciabilità</span><span class="sxs-lookup"><span data-stu-id="cf747-196">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="cf747-197">Tracciabilità</span><span class="sxs-lookup"><span data-stu-id="cf747-197">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="cf747-198">Posizione</span><span class="sxs-lookup"><span data-stu-id="cf747-198">Location</span></span> | `LocationId` |
| <span data-ttu-id="cf747-199">Posizione</span><span class="sxs-lookup"><span data-stu-id="cf747-199">Location</span></span> | `SiteId` |
| <span data-ttu-id="cf747-200">Stato inventario</span><span class="sxs-lookup"><span data-stu-id="cf747-200">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="cf747-201">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="cf747-201">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="cf747-202">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="cf747-202">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="cf747-203">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="cf747-203">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="cf747-204">Il tipo di dimensione elencato nella tabella precedente è solo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="cf747-204">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="cf747-205">Non è necessario definire il tipo di dimensione in Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="cf747-205">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="cf747-206">Se esiste una dimensione personalizzata che diventare un valore predefinito quando viene utilizzata da Inventory Visibility, è possibile configurare il nome **Dimensione personalizzata** in Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="cf747-206">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="cf747-207">I sistemi esterni accedono a Inventory Visibility tramite le API RESTful che consentono di interrogare le informazioni disponibili su determinati set di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="cf747-207">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="cf747-208">Per l'integrazione, Inventory Visibility consente di configurare l'*origine dati del canale esterno* e la dimensione di origine sulle *dimensioni di destinazione* in Inventory Visibility.</span><span class="sxs-lookup"><span data-stu-id="cf747-208">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="cf747-209">Le dimensioni di destinazione deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf747-209">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="cf747-210">Dimensioni predefinite in Inventory Visibility</span><span class="sxs-lookup"><span data-stu-id="cf747-210">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="cf747-211">Dimensioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="cf747-211">Custom dimensions</span></span>

<span data-ttu-id="cf747-212">Lo scopo della configurazione delle dimensioni è standardizzare l'integrazione multi-sistema per la query sulle dimensioni e l'evento di registrazione con le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="cf747-212">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="cf747-213">Indicizzazione</span><span class="sxs-lookup"><span data-stu-id="cf747-213">Indexing</span></span>

<span data-ttu-id="cf747-214">La maggior parte delle volte, la query delle scorte disponibili non sarà solo sul livello "totale" più alto, ma si potrebbe voler vedere i risultati aggregati in base alle dimensioni dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="cf747-214">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="cf747-215">Inventory Visibility offre flessibilità consentendo di impostare gli indici, che si basano sulla dimensione o sulla combinazione delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="cf747-215">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="cf747-216">Al momento, è possibile configurare solo fino a un massimo di cinque indici.</span><span class="sxs-lookup"><span data-stu-id="cf747-216">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="cf747-217">È necessario considerare attentamente quale dimensione o combinazione di dimensioni si utilizzerà prima dell'implementazione per assicurarsi che soddisfi le esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="cf747-217">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="cf747-218">Ad esempio, se si desidera eseguire query sui prodotti come segue:</span><span class="sxs-lookup"><span data-stu-id="cf747-218">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="cf747-219">Query delle scorte del prodotto aggregato per dimensioni *Colore* e *Dimensione*.</span><span class="sxs-lookup"><span data-stu-id="cf747-219">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="cf747-220">In alcuni casi, si desidera solo eseguire una query sul prodotto in totale.</span><span class="sxs-lookup"><span data-stu-id="cf747-220">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="cf747-221">Sarebbero disponibili due indici definiti come segue:</span><span class="sxs-lookup"><span data-stu-id="cf747-221">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="cf747-222">La parentesi vuota si aggregherà in base all'ID del prodotto all'interno della partizione.</span><span class="sxs-lookup"><span data-stu-id="cf747-222">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="cf747-223">L'indicizzazione definisce come raggruppare i risultati in base all'impostazione della query `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="cf747-223">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="cf747-224">In questo caso se non si definiscono valori `groupBy` si ottengono i totali per `productid`.</span><span class="sxs-lookup"><span data-stu-id="cf747-224">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="cf747-225">Altrimenti se si definisce `groupBy` come `groupBy=ColorId&groupBy=SizeId`, verranno restituite più righe, in base alle diverse combinazioni di colori e dimensioni nel sistema.</span><span class="sxs-lookup"><span data-stu-id="cf747-225">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="cf747-226">È possibile inserire i criteri della query nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="cf747-226">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="cf747-227">Ecco una query di esempio sul prodotto con combinazione di colore e dimensione.</span><span class="sxs-lookup"><span data-stu-id="cf747-227">Here is a sample query on the product with color and size combination.</span></span>

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

#### <a name="custom-measurement"></a><span data-ttu-id="cf747-228">Misura personalizzata</span><span class="sxs-lookup"><span data-stu-id="cf747-228">Custom measurement</span></span>

<span data-ttu-id="cf747-229">Le quantità di misura predefinite sono collegate a Supply Chain Management, tuttavia potrebbe essere necessario disporre di una quantità composta da una combinazione delle misure predefinite.</span><span class="sxs-lookup"><span data-stu-id="cf747-229">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="cf747-230">Per fare ciò, è possibile avere una configurazione di quantità personalizzate, che verranno aggiunte all'output delle query disponibili.</span><span class="sxs-lookup"><span data-stu-id="cf747-230">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="cf747-231">La funzionalità consente semplicemente di definire un insieme di misure che verranno aggiunte, e/o un insieme di misure che verranno sottratte, in modo da ottenere dalla misura personalizzata.</span><span class="sxs-lookup"><span data-stu-id="cf747-231">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="cf747-232">Ad esempio, con la seguente condizione di query, si configura la quantità di misura personalizzata come `MyCustomAvailableforReservation` per essere utilizzata dal sistema di consumo.</span><span class="sxs-lookup"><span data-stu-id="cf747-232">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="cf747-233">Sistema di consumo</span><span class="sxs-lookup"><span data-stu-id="cf747-233">Consumption system</span></span> | <span data-ttu-id="cf747-234">Misure calcolate</span><span class="sxs-lookup"><span data-stu-id="cf747-234">Calculated measurers</span></span> | <span data-ttu-id="cf747-235">Origine dati</span><span class="sxs-lookup"><span data-stu-id="cf747-235">Data source</span></span> | <span data-ttu-id="cf747-236">Modificatore</span><span class="sxs-lookup"><span data-stu-id="cf747-236">Modifier</span></span> | <span data-ttu-id="cf747-237">Tipo di calcolo del modificatore</span><span class="sxs-lookup"><span data-stu-id="cf747-237">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="cf747-238">Addizione</span><span class="sxs-lookup"><span data-stu-id="cf747-238">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="cf747-239">Addizione</span><span class="sxs-lookup"><span data-stu-id="cf747-239">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="cf747-240">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="cf747-240">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="cf747-241">Addizione</span><span class="sxs-lookup"><span data-stu-id="cf747-241">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="cf747-242">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="cf747-242">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="cf747-243">Addizione</span><span class="sxs-lookup"><span data-stu-id="cf747-243">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="cf747-244">Addizione</span><span class="sxs-lookup"><span data-stu-id="cf747-244">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="cf747-245">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="cf747-245">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="cf747-246">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="cf747-246">Subtraction</span></span> |

<span data-ttu-id="cf747-247">Con ciò, la query sulla quantità di misura personalizzata restituirà il seguente output.</span><span class="sxs-lookup"><span data-stu-id="cf747-247">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="cf747-248">L'output `MyCustomAvailableforReservation` si basa sull'impostazione del calcolo nelle misure personalizzate come:</span><span class="sxs-lookup"><span data-stu-id="cf747-248">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="cf747-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="cf747-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="cf747-250">Registrazione delle modifiche delle scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="cf747-250">Posting on-hand changes</span></span>

<span data-ttu-id="cf747-251">L'URL esatto in cui verrà pubblicato l'evento dipenderà dalla regione geografica.</span><span class="sxs-lookup"><span data-stu-id="cf747-251">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="cf747-252">Avrà il formato:</span><span class="sxs-lookup"><span data-stu-id="cf747-252">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="cf747-253">Una volta autenticato, questo URL può essere utilizzato insieme al metodo HTTP `POST` per inviare al servizio eventi di modifica delle scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="cf747-253">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="cf747-254">Un'intestazione speciale viene utilizzata per comunicare con i servizi Dynamics 365 tramite richieste HTTP, indicando l'ID ambiente dell'istanza di Supply Chain Management a cui sono collegati i dati.</span><span class="sxs-lookup"><span data-stu-id="cf747-254">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="cf747-255">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf747-255">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="cf747-256">Registrazione delle modifiche delle scorte disponibili - esempio di query 1</span><span class="sxs-lookup"><span data-stu-id="cf747-256">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="cf747-257">Questo esempio mostra uno scenario in cui verrà impostata la configurazione della dimensione in Power Apps.</span><span class="sxs-lookup"><span data-stu-id="cf747-257">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="cf747-258">Utilizzare la seguente query per configurare la mappatura delle dimensioni in Power Apps:</span><span class="sxs-lookup"><span data-stu-id="cf747-258">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="cf747-259">Ora è possibile specificare `dimensionDataSource` e utilizzare le dimensioni personalizzate nelle query.</span><span class="sxs-lookup"><span data-stu-id="cf747-259">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="cf747-260">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="cf747-260">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="cf747-261">Registrazione delle modifiche delle scorte disponibili - esempio di query 2</span><span class="sxs-lookup"><span data-stu-id="cf747-261">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="cf747-262">Questo esempio mostra uno scenario in cui non sono impostate mappature per la configurazione della dimensione in Power Apps, quindi la registrazione deve utilizzare anche le dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="cf747-262">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="cf747-263">Tutte le dimensioni devono essere dimensioni di base quando il campo `dimensionDataSource` è nullo, vuoto o spazio bianco.</span><span class="sxs-lookup"><span data-stu-id="cf747-263">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="cf747-264">Proprietà dei campi del documento JSON</span><span class="sxs-lookup"><span data-stu-id="cf747-264">JSON document field properties</span></span>

<span data-ttu-id="cf747-265">I campi degli esempi di query JSON forniti in precedenza hanno le proprietà elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cf747-265">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="cf747-266">ID campo</span><span class="sxs-lookup"><span data-stu-id="cf747-266">Field ID</span></span> | <span data-ttu-id="cf747-267">descrizione</span><span class="sxs-lookup"><span data-stu-id="cf747-267">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="cf747-268">Un ID univoco per l'evento di modifica specifico.</span><span class="sxs-lookup"><span data-stu-id="cf747-268">A unique ID for the specific change event.</span></span> <span data-ttu-id="cf747-269">Questo ID viene utilizzato per garantire che se la comunicazione con il servizio non riesce durante la registrazione, il reinvio dell'evento non comporta il doppio conteggio dello stesso evento nel sistema.</span><span class="sxs-lookup"><span data-stu-id="cf747-269">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="cf747-270">L'identificatore dell'organizzazione collegata all'evento.</span><span class="sxs-lookup"><span data-stu-id="cf747-270">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="cf747-271">Viene mappato agli ID area dati o alle organizzazioni di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cf747-271">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="cf747-272">L'identificatore del prodotto in questione.</span><span class="sxs-lookup"><span data-stu-id="cf747-272">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="cf747-273">La quantità in base alla quale è necessario modificare la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="cf747-273">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="cf747-274">Se, ad esempio, 10 nuovi bagel venissero aggiunti a uno scaffale, questo valore sarebbe 10.</span><span class="sxs-lookup"><span data-stu-id="cf747-274">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="cf747-275">Se 3 bagel venissero poi rimossi dallo scaffale o venduti, questo valore sarebbe -3.</span><span class="sxs-lookup"><span data-stu-id="cf747-275">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="cf747-276">L'origine dati delle dimensioni utilizzate nella query e nell'evento di modifica della registrazione.</span><span class="sxs-lookup"><span data-stu-id="cf747-276">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="cf747-277">Se si specifica l'origine dati, è possibile utilizzare le dimensioni personalizzate dell'origine dati specificata.</span><span class="sxs-lookup"><span data-stu-id="cf747-277">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="cf747-278">Con la configurazione delle dimensioni, Inventory Visibility può mappare le dimensioni personalizzate alle dimensioni predefinite generali.</span><span class="sxs-lookup"><span data-stu-id="cf747-278">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="cf747-279">Se `dimensionDataSource` non è specificato, è possibile utilizzare solo le dimensioni predefinite generali nelle query.</span><span class="sxs-lookup"><span data-stu-id="cf747-279">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="cf747-280">Un insieme dinamico di coppie chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="cf747-280">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="cf747-281">Questi verranno mappati ad alcune dimensioni in Supply Chain Management, ma è possibile anche aggiungere dimensioni personalizzate (come *origine*) che può indicare se l'evento proveniva da Supply Chain Management o da un sistema esterno.</span><span class="sxs-lookup"><span data-stu-id="cf747-281">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="cf747-282">Interrogazione delle quantità disponibili correnti</span><span class="sxs-lookup"><span data-stu-id="cf747-282">Querying current on-hand</span></span>

<span data-ttu-id="cf747-283">L'endpoint per l'interrogazione delle quantità disponibili correnti avrà un URL simile:</span><span class="sxs-lookup"><span data-stu-id="cf747-283">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="cf747-284">Sarà interrogato con il metodo HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="cf747-284">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="cf747-285">Esempio di query delle quantità disponibili correnti 1</span><span class="sxs-lookup"><span data-stu-id="cf747-285">Current on-hand query example 1</span></span>

<span data-ttu-id="cf747-286">Questo esempio mostra uno scenario in cui è già stata impostata la configurazione della dimensione in Power Apps.</span><span class="sxs-lookup"><span data-stu-id="cf747-286">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="cf747-287">Utilizzare la seguente query per configurare la mappatura delle dimensioni in Power Apps:</span><span class="sxs-lookup"><span data-stu-id="cf747-287">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="cf747-288">Ora è possibile specificare `dimensionDataSource` e utilizzare le dimensioni personalizzate nelle query.</span><span class="sxs-lookup"><span data-stu-id="cf747-288">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="cf747-289">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="cf747-289">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="cf747-290">È possibile specificare `DimensionDataSource` in `filters` e specificare le dimensioni personalizzate in `filters` e `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="cf747-290">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="cf747-291">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="cf747-291">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="cf747-292">Esempio di query delle quantità disponibili correnti 2</span><span class="sxs-lookup"><span data-stu-id="cf747-292">Current on-hand query example 2</span></span>

<span data-ttu-id="cf747-293">Questo esempio mostra uno scenario in cui non sono impostate mappature per la configurazione della dimensione in Power Apps, quindi la registrazione deve utilizzare anche le dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="cf747-293">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="cf747-294">Tutte le dimensioni devono essere dimensioni di base quando il campo `dimensionDataSource` in `filters` è nullo, vuoto o spazio bianco.</span><span class="sxs-lookup"><span data-stu-id="cf747-294">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="cf747-295">Esempio di risultato restituito</span><span class="sxs-lookup"><span data-stu-id="cf747-295">Example return result</span></span>

<span data-ttu-id="cf747-296">Le query mostrate negli esempi precedenti potrebbero restituire un risultato come questo.</span><span class="sxs-lookup"><span data-stu-id="cf747-296">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="cf747-297">Notare che i campi delle quantità sono strutturati come un dizionario di misure e dei valori associati.</span><span class="sxs-lookup"><span data-stu-id="cf747-297">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
