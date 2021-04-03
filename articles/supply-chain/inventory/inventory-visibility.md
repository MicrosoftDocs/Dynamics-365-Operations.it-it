---
title: Componente aggiuntivo Visibilità magazzino
description: Questo argomento descrive come installare e configurare il componente aggiuntivo Visibilità magazzino per Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 4e588be2ac5aae395ca66e3c9a743a67d71db7c0
ms.sourcegitcommit: a3052f76ad71894dbef66566c07c6e2c31505870
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "5574224"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="e61ec-103">Componente aggiuntivo Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e61ec-104">Il componente aggiuntivo Visibilità magazzino è un microservizio indipendente e altamente scalabile che consente il monitoraggio dell'inventario disponibile in tempo reale, fornendo così una visione globale della visibilità dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="e61ec-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="e61ec-105">Tutte le informazioni relative alle scorte disponibili vengono esportate nel servizio quasi in tempo reale tramite l'integrazione SQL di basso livello.</span><span class="sxs-lookup"><span data-stu-id="e61ec-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="e61ec-106">I sistemi esterni accedono al servizio tramite API RESTful per interrogare le informazioni sulle scorte disponibili su determinati set di dimensioni, recuperando così un elenco di posizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="e61ec-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="e61ec-107">Visibilità magazzino è un microservizio basato su Microsoft Dataverse, il che significa che è possibile estenderlo creando Power Apps e applicando Power BI per fornire funzionalità personalizzate per soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="e61ec-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="e61ec-108">È anche possibile aggiornare l'indice per eseguire query sull'inventario.</span><span class="sxs-lookup"><span data-stu-id="e61ec-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="e61ec-109">Visibilità magazzino fornisce opzioni di configurazione che consentono l'integrazione con più sistemi di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e61ec-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="e61ec-110">Supporta la dimensione dell'inventario standardizzata, l'estensibilità personalizzata e le quantità calcolate standardizzate e configurabili.</span><span class="sxs-lookup"><span data-stu-id="e61ec-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="e61ec-111">Questo argomento descrive come installare e configurare il componente aggiuntivo Visibilità magazzino per Dynamics 365 Supply Chain Management e come utilizzare l'API.</span><span class="sxs-lookup"><span data-stu-id="e61ec-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="e61ec-112">Installare il componente aggiuntivo Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="e61ec-113">È necessario installare il componente aggiuntivo Visibilità magazzino utilizzando Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e61ec-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="e61ec-114">LCS è un portale di collaborazione che fornisce un ambiente e una serie di servizi regolarmente aggiornati che aiutano a gestire il ciclo di vita dell'applicazione delle app Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e61ec-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="e61ec-115">Per ulteriori informazioni, vedere [Risorse Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="e61ec-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e61ec-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e61ec-116">Prerequisites</span></span>

<span data-ttu-id="e61ec-117">Prima di poter installare il componente aggiuntivo Visibilità magazzino è necessario effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e61ec-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="e61ec-118">Ottenere un progetto di implementazione LCS con almeno un ambiente distribuito.</span><span class="sxs-lookup"><span data-stu-id="e61ec-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="e61ec-119">Assicurati che i prerequisiti per la configurazione dei componenti aggiuntivi forniti in [Panoramica dei componenti aggiuntivi](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) siano stati soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="e61ec-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="e61ec-120">Visibilità magazzino non richiede un collegamento a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="e61ec-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="e61ec-121">Contattare il team di Visibilità magazzino all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) per ottenere i seguenti tre file:</span><span class="sxs-lookup"><span data-stu-id="e61ec-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>

    - `Inventory Visibility Dataverse Solution.zip`
    - `Inventory Visibility Configuration Trigger.zip`
    - <span data-ttu-id="e61ec-122">`Inventory Visibility Integration.zip` (se la versione di Supply Chain Management in esecuzione è precedente alla versione 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="e61ec-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>

> [!NOTE]
> <span data-ttu-id="e61ec-123">I paesi e le regioni attualmente supportati includono Canada, Stati Uniti e Unione europea (UE).</span><span class="sxs-lookup"><span data-stu-id="e61ec-123">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="e61ec-124">In caso di domande su questi prerequisiti, contattare il team del prodotto Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-124">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="e61ec-125">Configurare Dataverse</span><span class="sxs-lookup"><span data-stu-id="e61ec-125">Set up Dataverse</span></span>

<span data-ttu-id="e61ec-126">Per configurare Dataverse, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e61ec-126">Follow these steps to set up Dataverse.</span></span>

1. <span data-ttu-id="e61ec-127">Aggiungere un principio di servizio al tenant:</span><span class="sxs-lookup"><span data-stu-id="e61ec-127">Add a service principle to your tenant:</span></span>

    1. <span data-ttu-id="e61ec-128">Installare Azure AD PowerShell Module v2 come descritto in [Installare Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="e61ec-128">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
    1. <span data-ttu-id="e61ec-129">Eseguire il comando PowerShell seguente.</span><span class="sxs-lookup"><span data-stu-id="e61ec-129">Run the following PowerShell command.</span></span>

        ```powershell
        Connect-AzureAD # (open a sign in window and sign in as a tenant user)

        New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
        ```

1. <span data-ttu-id="e61ec-130">Creare un utente applicazione per Visibilità magazzino in Dataverse:</span><span class="sxs-lookup"><span data-stu-id="e61ec-130">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="e61ec-131">Aprire l'URL del proprio ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e61ec-131">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="e61ec-132">Selezionare **Impostazioni avanzate \> Sistema \> Sicurezza \> Utenti** e creare un utente applicazione.</span><span class="sxs-lookup"><span data-stu-id="e61ec-132">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="e61ec-133">Utilizzare il menu Visualizza per cambiare la visualizzazione della pagina in **Utenti applicazione**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-133">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="e61ec-134">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-134">Select **New**.</span></span> <span data-ttu-id="e61ec-135">Impostare l'ID applicazione su *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*</span><span class="sxs-lookup"><span data-stu-id="e61ec-135">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="e61ec-136">(l'ID oggetto verrà caricato automaticamente quando si salvano le modifiche). È possibile personalizzare il nome.</span><span class="sxs-lookup"><span data-stu-id="e61ec-136">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="e61ec-137">Ad esempio, è possibile modificarlo in *Visibilità magazzino*.</span><span class="sxs-lookup"><span data-stu-id="e61ec-137">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="e61ec-138">Al termine, selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-138">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="e61ec-139">Selezionare **Assegna ruolo** e quindi selezionare **Amministratore di sistema**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-139">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="e61ec-140">Se è presente un ruolo denominato **Utente Common Data Service**, selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="e61ec-140">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="e61ec-141">Per ulteriori informazioni, vedere [Creare un utente applicazione](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="e61ec-141">For more information, see [Create an application user](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="e61ec-142">Importare il file `Inventory Visibility Dataverse Solution.zip`, che include entità relative alla configurazione di Dataverse e Power Apps:</span><span class="sxs-lookup"><span data-stu-id="e61ec-142">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="e61ec-143">Accedere alla pagina **Soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-143">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="e61ec-144">Selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-144">Select **Import**.</span></span>

1. <span data-ttu-id="e61ec-145">Importare il flusso di attivazione dell'aggiornamento della configurazione:</span><span class="sxs-lookup"><span data-stu-id="e61ec-145">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="e61ec-146">Accedere alla pagina di Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="e61ec-146">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="e61ec-147">Assicurarsi che la connessione denominata *Dataverse (legacy)* esista</span><span class="sxs-lookup"><span data-stu-id="e61ec-147">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="e61ec-148">(in caso contrario, crearla).</span><span class="sxs-lookup"><span data-stu-id="e61ec-148">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="e61ec-149">Importare il file `Inventory Visibility Configuration Trigger.zip`.</span><span class="sxs-lookup"><span data-stu-id="e61ec-149">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="e61ec-150">Dopo l'importazione, il trigger apparirà sotto **Flussi personali**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-150">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="e61ec-151">Inizializzare le seguenti quattro variabili, in base alle informazioni sull'ambiente:</span><span class="sxs-lookup"><span data-stu-id="e61ec-151">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="e61ec-152">ID tenant di Azure</span><span class="sxs-lookup"><span data-stu-id="e61ec-152">Azure Tenant ID</span></span>
        - <span data-ttu-id="e61ec-153">ID client applicazione Azure</span><span class="sxs-lookup"><span data-stu-id="e61ec-153">Azure Application Client ID</span></span>
        - <span data-ttu-id="e61ec-154">Segreto client applicazione Azure</span><span class="sxs-lookup"><span data-stu-id="e61ec-154">Azure Application Client Secret</span></span>
        - <span data-ttu-id="e61ec-155">Endpoint Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-155">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="e61ec-156">Per ulteriori informazioni su questa variabile, vedere la sezione [Impostare l'integrazione di Visibilità magazzino](#setup-inventory-visibility-integration) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e61ec-156">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="e61ec-157">![Trigger di configurazione](media/configuration-trigger.png "Trigger di configurazione")</span><span class="sxs-lookup"><span data-stu-id="e61ec-157">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="e61ec-158">Selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-158">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="e61ec-159">Installare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="e61ec-159">Install the add-in</span></span>

<span data-ttu-id="e61ec-160">Per installare il componente aggiuntivo Visibilità magazzino effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e61ec-160">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="e61ec-161">Accedere al portale [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="e61ec-161">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="e61ec-162">Nella home page, selezionare il progetto in cui è distribuito l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e61ec-162">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="e61ec-163">Nella pagina del progetto, selezionare l'ambiente in cui si desidera installare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e61ec-163">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="e61ec-164">Nella pagina dell'ambiente, scorrere verso il basso fino a visualizzare la sezione **Componenti aggiuntivi dell'ambiente** in **Integrazione di Power Platform**, dove è possibile trovare il nome dell'ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e61ec-164">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="e61ec-165">Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-165">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="e61ec-166">![La pagina dell'ambiente in LCS](media/inventory-visibility-environment.png "La pagina dell'ambiente in LCS")</span><span class="sxs-lookup"><span data-stu-id="e61ec-166">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="e61ec-167">Selezionare il collegamento **Installare un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-167">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="e61ec-168">Si apre un elenco di componenti aggiuntivi disponibili.</span><span class="sxs-lookup"><span data-stu-id="e61ec-168">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="e61ec-169">Selezionare **Visibilità magazzino** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e61ec-169">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="e61ec-170">Immettere i valori per i seguenti campi per il proprio ambiente:</span><span class="sxs-lookup"><span data-stu-id="e61ec-170">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="e61ec-171">**ID (client) applicazione AAD**</span><span class="sxs-lookup"><span data-stu-id="e61ec-171">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="e61ec-172">**ID tenant AAD**</span><span class="sxs-lookup"><span data-stu-id="e61ec-172">**AAD tenant ID**</span></span>

    <span data-ttu-id="e61ec-173">![Pagina Impostazione del componente aggiuntivo](media/inventory-visibility-setup.png "Pagina Impostazione del componente aggiuntivo")</span><span class="sxs-lookup"><span data-stu-id="e61ec-173">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="e61ec-174">Accettare le condizioni selezionando la casella di controllo **Condizioni**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-174">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="e61ec-175">Seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-175">Select **Install**.</span></span> <span data-ttu-id="e61ec-176">Lo stato del componente aggiuntivo verrà visualizzato com e **Installazione**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-176">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="e61ec-177">Al termine, aggiornare la pagina per vedere lo stato cambiare in **Installato**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-177">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="e61ec-178">Disinstallare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="e61ec-178">Uninstall the add-in</span></span>

<span data-ttu-id="e61ec-179">Per disinstallare il componente aggiuntivo, selezionar e **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-179">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="e61ec-180">Quando si aggiorna LCS, il componente aggiuntivo Visibilità magazzino verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="e61ec-180">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="e61ec-181">Il processo di disinstallazione rimuove la registrazione del componente aggiuntivo e avvia anche un processo per pulire tutti i dati aziendali archiviati nel servizio.</span><span class="sxs-lookup"><span data-stu-id="e61ec-181">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="e61ec-182">Utilizzare i dati delle scorte disponibili di Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e61ec-182">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="e61ec-183">Distribuire il pacchetto di integrazione di Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-183">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="e61ec-184">Se si utilizza Supply Chain Management versione 10.0.17 o versione precedente, contattare il team di supporto di Visibilità magazzino all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) per ottenere il file del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e61ec-184">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="e61ec-185">Distribuire quindi il pacchetto in LCS.</span><span class="sxs-lookup"><span data-stu-id="e61ec-185">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="e61ec-186">Se durante la distribuzione si verifica un errore di mancata corrispondenza della versione, è necessario importare manualmente il progetto X++ nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="e61ec-186">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="e61ec-187">Creare quindi il pacchetto distribuibile nell'ambiente di sviluppo e distribuirlo nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="e61ec-187">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="e61ec-188">Il codice è incluso con Supply Chain Management versione 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="e61ec-188">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="e61ec-189">Se si esegue quella versione o una versione successiva, la distribuzione non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="e61ec-189">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="e61ec-190">Assicurarsi che le seguenti funzionalità siano attivate nell'ambiente Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e61ec-190">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="e61ec-191">(per impostazione predefinita, sono attivate).</span><span class="sxs-lookup"><span data-stu-id="e61ec-191">(By default, they are turned on.)</span></span>

| <span data-ttu-id="e61ec-192">Descrizione delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="e61ec-192">Feature description</span></span> | <span data-ttu-id="e61ec-193">Versione codice</span><span class="sxs-lookup"><span data-stu-id="e61ec-193">Code version</span></span> | <span data-ttu-id="e61ec-194">Alterna classe</span><span class="sxs-lookup"><span data-stu-id="e61ec-194">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="e61ec-195">Abilitare o disabilitare l'utilizzo delle dimensioni inventariali nella tabella InventSum</span><span class="sxs-lookup"><span data-stu-id="e61ec-195">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="e61ec-196">10.0.11</span><span class="sxs-lookup"><span data-stu-id="e61ec-196">10.0.11</span></span> | <span data-ttu-id="e61ec-197">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="e61ec-197">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="e61ec-198">Abilitare o disabilitare l'utilizzo delle dimensioni inventariali nella tabella InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="e61ec-198">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="e61ec-199">10.0.12</span><span class="sxs-lookup"><span data-stu-id="e61ec-199">10.0.12</span></span> | <span data-ttu-id="e61ec-200">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="e61ec-200">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="e61ec-201">Impostare l'integrazione di Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-201">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="e61ec-202">In Supply Chain Management, aprire l'area di lavoro **[Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e attivare la funzionalità **Integrazione di Visibilità magazzino**.</span><span class="sxs-lookup"><span data-stu-id="e61ec-202">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="e61ec-203">Selezionare **Gestione articoli \> Impostazioni \> Parametri di integrazione di Visibilità magazzino** e immettere l'URL dell'ambiente in cui si esegue Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-203">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="e61ec-204">Trovare l'area di Azure dell'ambiente LCS e quindi immettere l'URL.</span><span class="sxs-lookup"><span data-stu-id="e61ec-204">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="e61ec-205">Il formato dell'URL è come segue:</span><span class="sxs-lookup"><span data-stu-id="e61ec-205">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com/`

    <span data-ttu-id="e61ec-206">Ad esempio, se si è in Europa, l'ambiente avrà uno dei seguenti URL:</span><span class="sxs-lookup"><span data-stu-id="e61ec-206">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com/`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com/`

    <span data-ttu-id="e61ec-207">Sono attualmente disponibili le seguenti regioni:</span><span class="sxs-lookup"><span data-stu-id="e61ec-207">The following regions are currently available.</span></span>

    | <span data-ttu-id="e61ec-208">Regione Azure</span><span class="sxs-lookup"><span data-stu-id="e61ec-208">Azure region</span></span> | <span data-ttu-id="e61ec-209">Nome breve della regione</span><span class="sxs-lookup"><span data-stu-id="e61ec-209">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="e61ec-210">Australia orientale</span><span class="sxs-lookup"><span data-stu-id="e61ec-210">Australia east</span></span> | <span data-ttu-id="e61ec-211">eau</span><span class="sxs-lookup"><span data-stu-id="e61ec-211">eau</span></span> |
    | <span data-ttu-id="e61ec-212">Australia sud-orientale</span><span class="sxs-lookup"><span data-stu-id="e61ec-212">Australia southeast</span></span> | <span data-ttu-id="e61ec-213">seau</span><span class="sxs-lookup"><span data-stu-id="e61ec-213">seau</span></span> |
    | <span data-ttu-id="e61ec-214">Canada centrale</span><span class="sxs-lookup"><span data-stu-id="e61ec-214">Canada central</span></span> | <span data-ttu-id="e61ec-215">cca</span><span class="sxs-lookup"><span data-stu-id="e61ec-215">cca</span></span> |
    | <span data-ttu-id="e61ec-216">Canada orientale</span><span class="sxs-lookup"><span data-stu-id="e61ec-216">Canada east</span></span> | <span data-ttu-id="e61ec-217">eca</span><span class="sxs-lookup"><span data-stu-id="e61ec-217">eca</span></span> |
    | <span data-ttu-id="e61ec-218">Europa settentrionale</span><span class="sxs-lookup"><span data-stu-id="e61ec-218">North Europe</span></span> | <span data-ttu-id="e61ec-219">neu</span><span class="sxs-lookup"><span data-stu-id="e61ec-219">neu</span></span> |
    | <span data-ttu-id="e61ec-220">Europa occidentale</span><span class="sxs-lookup"><span data-stu-id="e61ec-220">West Europe</span></span> | <span data-ttu-id="e61ec-221">weu</span><span class="sxs-lookup"><span data-stu-id="e61ec-221">weu</span></span> |
    | <span data-ttu-id="e61ec-222">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="e61ec-222">East US</span></span> | <span data-ttu-id="e61ec-223">eus</span><span class="sxs-lookup"><span data-stu-id="e61ec-223">eus</span></span> |
    | <span data-ttu-id="e61ec-224">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="e61ec-224">West US</span></span> | <span data-ttu-id="e61ec-225">wus</span><span class="sxs-lookup"><span data-stu-id="e61ec-225">wus</span></span> |

1. <span data-ttu-id="e61ec-226">Selezionare **Gestione articoli \> Periodico \> Integrazione di Visibilità magazzino** e abilitare il processo.</span><span class="sxs-lookup"><span data-stu-id="e61ec-226">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="e61ec-227">Tutti gli eventi di modifica delle scorte di Supply Chain Management verranno ora registrati in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-227">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="e61ec-228">API pubblica del componente aggiuntivo Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-228">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="e61ec-229">L'API REST pubblica del componente aggiuntivo Visibilità magazzino presenta diversi endpoint specifici per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="e61ec-229">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="e61ec-230">Supporta tre principali tipi di interazione:</span><span class="sxs-lookup"><span data-stu-id="e61ec-230">It supports three main interaction types:</span></span>

- <span data-ttu-id="e61ec-231">Registrazione delle modifiche delle scorte disponibili nel componente aggiuntivo da un sistema esterno</span><span class="sxs-lookup"><span data-stu-id="e61ec-231">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="e61ec-232">Interrogazione delle quantità disponibili correnti da un sistema esterno</span><span class="sxs-lookup"><span data-stu-id="e61ec-232">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="e61ec-233">Sincronizzazione automatica con le scorte disponibili di Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e61ec-233">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="e61ec-234">La sincronizzazione automatica non fa parte dell'API pubblica.</span><span class="sxs-lookup"><span data-stu-id="e61ec-234">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="e61ec-235">È invece gestita in background per gli ambienti in cui è abilitato il componente aggiuntivo Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-235">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="e61ec-236">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="e61ec-236">Authentication</span></span>

<span data-ttu-id="e61ec-237">Il token di sicurezza della piattaforma viene utilizzato per chiamare il componente aggiuntivo Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-237">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="e61ec-238">Pertanto, è necessario generare un token *Azure Active Directory (Azure AD)* usando l'applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e61ec-238">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="e61ec-239">È quindi necessario utilizzare il token Azure AD per ottenere il *token di accesso* dal servizio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e61ec-239">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="e61ec-240">Ottenere un token del servizio di sicurezza effettuando le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="e61ec-240">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="e61ec-241">Accedere al portale di Azure e utilizzarlo per trovare `clientId` e `clientSecret` per l'applicazione Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e61ec-241">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="e61ec-242">Recuperare un token Azure Active Directory (`aadToken`) inviando una richiesta HTTP con le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="e61ec-242">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="e61ec-243">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="e61ec-243">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="e61ec-244">**Metodo** - `GET`</span><span class="sxs-lookup"><span data-stu-id="e61ec-244">**Method** - `GET`</span></span>
    - <span data-ttu-id="e61ec-245">**Contenuto del corpo (dati del modulo)**:</span><span class="sxs-lookup"><span data-stu-id="e61ec-245">**Body content (form data)**:</span></span>

        | <span data-ttu-id="e61ec-246">chiave</span><span class="sxs-lookup"><span data-stu-id="e61ec-246">key</span></span> | <span data-ttu-id="e61ec-247">valore</span><span class="sxs-lookup"><span data-stu-id="e61ec-247">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="e61ec-248">client_id</span><span class="sxs-lookup"><span data-stu-id="e61ec-248">client_id</span></span> | <span data-ttu-id="e61ec-249">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="e61ec-249">${aadAppId}</span></span> |
        | <span data-ttu-id="e61ec-250">client_secret</span><span class="sxs-lookup"><span data-stu-id="e61ec-250">client_secret</span></span> | <span data-ttu-id="e61ec-251">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="e61ec-251">${aadAppSecret}</span></span> |
        | <span data-ttu-id="e61ec-252">grant_type</span><span class="sxs-lookup"><span data-stu-id="e61ec-252">grant_type</span></span> | <span data-ttu-id="e61ec-253">client_credentials</span><span class="sxs-lookup"><span data-stu-id="e61ec-253">client_credentials</span></span> |
        | <span data-ttu-id="e61ec-254">risorsa</span><span class="sxs-lookup"><span data-stu-id="e61ec-254">resource</span></span> | <span data-ttu-id="e61ec-255">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="e61ec-255">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="e61ec-256">Dovresti ricevere un `aadToken` in risposta, che assomiglia al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="e61ec-256">You should receive an `aadToken` in response, which resembles the following example.</span></span>

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

1. <span data-ttu-id="e61ec-257">Formulare una richiesta JSON simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e61ec-257">Formulate a JSON request that resembles the following:</span></span>

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

    <span data-ttu-id="e61ec-258">Percorso:</span><span class="sxs-lookup"><span data-stu-id="e61ec-258">Where:</span></span>
    - <span data-ttu-id="e61ec-259">Il valore `client_assertion` deve essere `aadToken` ricevuto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="e61ec-259">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="e61ec-260">Il valore `context` deve essere l'ID dell'ambiente in cui si desidera distribuire il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e61ec-260">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="e61ec-261">Impostare tutti gli altri valori come mostrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="e61ec-261">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="e61ec-262">Inviare una richiesta HTTP con le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="e61ec-262">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="e61ec-263">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="e61ec-263">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="e61ec-264">**Metodo** - `POST`</span><span class="sxs-lookup"><span data-stu-id="e61ec-264">**Method** - `POST`</span></span>
    - <span data-ttu-id="e61ec-265">**Intestazione HTTP**: includere la versione API (la chiave è `Api-Version` e il valore è `1.0`)</span><span class="sxs-lookup"><span data-stu-id="e61ec-265">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="e61ec-266">**Contenuto del corpo**: includi la richiesta JSON che hai creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="e61ec-266">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="e61ec-267">Viene restituito un `access_token` in risposta.</span><span class="sxs-lookup"><span data-stu-id="e61ec-267">You will get an `access_token` in response.</span></span> <span data-ttu-id="e61ec-268">Questo è ciò di cui si ha bisogno come token di connessione per chiamare l'API di Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-268">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="e61ec-269">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="e61ec-269">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="e61ec-270">Configurare l'API di Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-270">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="e61ec-271">Prima di utilizzare il servizio, è necessario completare le configurazioni descritte nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e61ec-271">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="e61ec-272">La configurazione può variare in base ai dettagli del proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="e61ec-272">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="e61ec-273">Comprende principalmente quattro parti:</span><span class="sxs-lookup"><span data-stu-id="e61ec-273">It primarily includes four parts:</span></span>

- [<span data-ttu-id="e61ec-274">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="e61ec-274">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="e61ec-275">Configurazioni delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="e61ec-275">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="e61ec-276">Indicizzazione</span><span class="sxs-lookup"><span data-stu-id="e61ec-276">Indexing</span></span>](#indexing)
- [<span data-ttu-id="e61ec-277">Misura personalizzata</span><span class="sxs-lookup"><span data-stu-id="e61ec-277">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="e61ec-278">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="e61ec-278">Partitioning</span></span>

<span data-ttu-id="e61ec-279">Il partizionamento può influenzare in modo significativo le prestazioni dell'API di Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-279">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="e61ec-280">È una buona idea definire uno schema che consenta piccoli raggruppamenti di dati pur consentendo query di dati significative.</span><span class="sxs-lookup"><span data-stu-id="e61ec-280">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="e61ec-281">L'elemento `organizationId` (`dataAreaId` in Supply Chain Management) farà sempre parte del partizionamento e, per impostazione predefinita, Visibilità magazzino è impostato su partizionamento per dimensioni come *Sito + Posizione*.</span><span class="sxs-lookup"><span data-stu-id="e61ec-281">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="e61ec-282">Ciò significa che il servizio deve essere sempre interrogato con queste dimensioni definite sui filtri.</span><span class="sxs-lookup"><span data-stu-id="e61ec-282">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="e61ec-283">*Sito* e *Posizione* sono due dimensioni predefinite generali in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-283">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="e61ec-284">In Supply Chain Management, queste dimensioni vengono chiamate *Sito* (`InventSiteId`) e *Magazzino* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="e61ec-284">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="e61ec-285">Configurazioni delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="e61ec-285">Dimension configurations</span></span>

<span data-ttu-id="e61ec-286">Visibilità magazzino fornirà un elenco di dimensioni predefinite generali per abilitare l'integrazione di più sistemi di origine.</span><span class="sxs-lookup"><span data-stu-id="e61ec-286">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="e61ec-287">La tabella seguente elenca le dimensioni dell'inventario che saranno i nomi delle dimensioni predefinite in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-287">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="e61ec-288">Tipo di dimensione</span><span class="sxs-lookup"><span data-stu-id="e61ec-288">Dimension type</span></span> | <span data-ttu-id="e61ec-289">Nome dimensione</span><span class="sxs-lookup"><span data-stu-id="e61ec-289">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="e61ec-290">Prodotto</span><span class="sxs-lookup"><span data-stu-id="e61ec-290">Product</span></span> | `ColorId` |
| <span data-ttu-id="e61ec-291">Prodotto</span><span class="sxs-lookup"><span data-stu-id="e61ec-291">Product</span></span> | `SizeId` |
| <span data-ttu-id="e61ec-292">Prodotto</span><span class="sxs-lookup"><span data-stu-id="e61ec-292">Product</span></span> | `StyleId` |
| <span data-ttu-id="e61ec-293">Prodotto</span><span class="sxs-lookup"><span data-stu-id="e61ec-293">Product</span></span> | `ConfigId` |
| <span data-ttu-id="e61ec-294">Tracciabilità</span><span class="sxs-lookup"><span data-stu-id="e61ec-294">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="e61ec-295">Tracciabilità</span><span class="sxs-lookup"><span data-stu-id="e61ec-295">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="e61ec-296">Posizione</span><span class="sxs-lookup"><span data-stu-id="e61ec-296">Location</span></span> | `LocationId` |
| <span data-ttu-id="e61ec-297">Posizione</span><span class="sxs-lookup"><span data-stu-id="e61ec-297">Location</span></span> | `SiteId` |
| <span data-ttu-id="e61ec-298">Stato inventario</span><span class="sxs-lookup"><span data-stu-id="e61ec-298">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="e61ec-299">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-299">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="e61ec-300">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-300">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="e61ec-301">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-301">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="e61ec-302">Il tipo di dimensione elencato nella tabella precedente è solo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e61ec-302">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="e61ec-303">Non è necessario definire il tipo di dimensione in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-303">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="e61ec-304">Se esiste una dimensione personalizzata che diventare un valore predefinito quando viene utilizzata da Visibilità magazzino, è possibile configurare il nome **Dimensione personalizzata** in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-304">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="e61ec-305">I sistemi esterni accedono a Visibilità magazzino tramite le API RESTful che consentono di interrogare le informazioni disponibili su determinati set di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e61ec-305">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="e61ec-306">Per l'integrazione, Visibilità magazzino consente di configurare l'*origine dati del canale esterno* e la dimensione di origine sulle *dimensioni di destinazione* in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="e61ec-306">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="e61ec-307">Le dimensioni di destinazione deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="e61ec-307">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="e61ec-308">Dimensioni predefinite in Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="e61ec-308">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="e61ec-309">Dimensioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="e61ec-309">Custom dimensions</span></span>

<span data-ttu-id="e61ec-310">Lo scopo della configurazione delle dimensioni è standardizzare l'integrazione multi-sistema per la query sulle dimensioni e l'evento di registrazione con le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e61ec-310">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="e61ec-311">Indicizzazione</span><span class="sxs-lookup"><span data-stu-id="e61ec-311">Indexing</span></span>

<span data-ttu-id="e61ec-312">La maggior parte delle volte, la query delle scorte disponibili non sarà solo sul livello "totale" più alto, ma si potrebbe voler vedere i risultati aggregati in base alle dimensioni dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="e61ec-312">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="e61ec-313">Visibilità magazzino offre flessibilità consentendo di impostare gli indici, che si basano sulla dimensione o sulla combinazione delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e61ec-313">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="e61ec-314">Al momento, è possibile configurare solo fino a un massimo di cinque indici.</span><span class="sxs-lookup"><span data-stu-id="e61ec-314">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="e61ec-315">È necessario considerare attentamente quale dimensione o combinazione di dimensioni si utilizzerà prima dell'implementazione per assicurarsi che soddisfi le esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="e61ec-315">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="e61ec-316">Ad esempio, se si desidera eseguire query sui prodotti come segue:</span><span class="sxs-lookup"><span data-stu-id="e61ec-316">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="e61ec-317">Query delle scorte del prodotto aggregato per dimensioni *Colore* e *Dimensione*.</span><span class="sxs-lookup"><span data-stu-id="e61ec-317">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="e61ec-318">In alcuni casi, si desidera solo eseguire una query sul prodotto in totale.</span><span class="sxs-lookup"><span data-stu-id="e61ec-318">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="e61ec-319">Sarebbero disponibili due indici definiti come segue:</span><span class="sxs-lookup"><span data-stu-id="e61ec-319">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="e61ec-320">La parentesi vuota si aggregherà in base all'ID del prodotto all'interno della partizione.</span><span class="sxs-lookup"><span data-stu-id="e61ec-320">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="e61ec-321">L'indicizzazione definisce come raggruppare i risultati in base all'impostazione della query `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="e61ec-321">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="e61ec-322">In questo caso se non si definiscono valori `groupBy` si ottengono i totali per `productid`.</span><span class="sxs-lookup"><span data-stu-id="e61ec-322">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="e61ec-323">Altrimenti se si definisce `groupBy` come `groupBy=ColorId&groupBy=SizeId`, verranno restituite più righe, in base alle diverse combinazioni di colori e dimensioni nel sistema.</span><span class="sxs-lookup"><span data-stu-id="e61ec-323">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="e61ec-324">È possibile inserire i criteri della query nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="e61ec-324">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="e61ec-325">Ecco una query di esempio sul prodotto con combinazione di colore e dimensione.</span><span class="sxs-lookup"><span data-stu-id="e61ec-325">Here is a sample query on the product with color and size combination.</span></span>

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

#### <a name="custom-measurement"></a><span data-ttu-id="e61ec-326">Misura personalizzata</span><span class="sxs-lookup"><span data-stu-id="e61ec-326">Custom measurement</span></span>

<span data-ttu-id="e61ec-327">Le quantità di misura predefinite sono collegate a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e61ec-327">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="e61ec-328">Tuttavia, potrebbe essere necessario disporre di una quantità composta da una combinazione delle misure predefinite.</span><span class="sxs-lookup"><span data-stu-id="e61ec-328">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="e61ec-329">Per fare ciò, è possibile avere una configurazione di quantità personalizzate, che verranno aggiunte all'output delle query disponibili.</span><span class="sxs-lookup"><span data-stu-id="e61ec-329">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="e61ec-330">La funzionalità consente semplicemente di definire un insieme di misure che verranno aggiunte, e/o un insieme di misure che verranno sottratte, in modo da ottenere dalla misura personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e61ec-330">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="e61ec-331">Ad esempio, con la seguente condizione di query, si configura la quantità di misura personalizzata come `MyCustomAvailableforReservation` per essere utilizzata dal sistema di consumo.</span><span class="sxs-lookup"><span data-stu-id="e61ec-331">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="e61ec-332">Sistema di consumo</span><span class="sxs-lookup"><span data-stu-id="e61ec-332">Consumption system</span></span> | <span data-ttu-id="e61ec-333">Misure calcolate</span><span class="sxs-lookup"><span data-stu-id="e61ec-333">Calculated measurers</span></span> | <span data-ttu-id="e61ec-334">Origine dati</span><span class="sxs-lookup"><span data-stu-id="e61ec-334">Data source</span></span> | <span data-ttu-id="e61ec-335">Modificatore</span><span class="sxs-lookup"><span data-stu-id="e61ec-335">Modifier</span></span> | <span data-ttu-id="e61ec-336">Tipo di calcolo del modificatore</span><span class="sxs-lookup"><span data-stu-id="e61ec-336">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="e61ec-337">Addizione</span><span class="sxs-lookup"><span data-stu-id="e61ec-337">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="e61ec-338">Addizione</span><span class="sxs-lookup"><span data-stu-id="e61ec-338">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="e61ec-339">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="e61ec-339">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="e61ec-340">Addizione</span><span class="sxs-lookup"><span data-stu-id="e61ec-340">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="e61ec-341">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="e61ec-341">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="e61ec-342">Addizione</span><span class="sxs-lookup"><span data-stu-id="e61ec-342">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="e61ec-343">Addizione</span><span class="sxs-lookup"><span data-stu-id="e61ec-343">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="e61ec-344">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="e61ec-344">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="e61ec-345">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="e61ec-345">Subtraction</span></span> |

<span data-ttu-id="e61ec-346">Con ciò, la query sulla quantità di misura personalizzata restituirà il seguente output.</span><span class="sxs-lookup"><span data-stu-id="e61ec-346">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="e61ec-347">L'output `MyCustomAvailableforReservation` si basa sull'impostazione del calcolo nelle misure personalizzate come:</span><span class="sxs-lookup"><span data-stu-id="e61ec-347">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="e61ec-348">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="e61ec-348">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="e61ec-349">Registrazione delle modifiche delle scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="e61ec-349">Posting on-hand changes</span></span>

<span data-ttu-id="e61ec-350">L'URL esatto in cui verrà pubblicato l'evento dipenderà dalla regione geografica.</span><span class="sxs-lookup"><span data-stu-id="e61ec-350">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="e61ec-351">Avrà il formato:</span><span class="sxs-lookup"><span data-stu-id="e61ec-351">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="e61ec-352">Una volta autenticato, questo URL può essere utilizzato insieme al metodo HTTP `POST` per inviare al servizio eventi di modifica delle scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="e61ec-352">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="e61ec-353">Un'intestazione speciale viene utilizzata per comunicare con i servizi Dynamics 365 tramite richieste HTTP, indicando l'ID ambiente dell'istanza di Supply Chain Management a cui sono collegati i dati.</span><span class="sxs-lookup"><span data-stu-id="e61ec-353">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="e61ec-354">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e61ec-354">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="e61ec-355">Registrazione delle modifiche delle scorte disponibili - esempio di query 1</span><span class="sxs-lookup"><span data-stu-id="e61ec-355">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="e61ec-356">Questo esempio mostra uno scenario in cui verrà impostata la configurazione della dimensione in Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e61ec-356">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="e61ec-357">Utilizzare la seguente query per configurare la mappatura delle dimensioni in Power Apps:</span><span class="sxs-lookup"><span data-stu-id="e61ec-357">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="e61ec-358">Ora è possibile specificare `dimensionDataSource` e utilizzare le dimensioni personalizzate nelle query.</span><span class="sxs-lookup"><span data-stu-id="e61ec-358">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="e61ec-359">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="e61ec-359">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="e61ec-360">Registrazione delle modifiche delle scorte disponibili - esempio di query 2</span><span class="sxs-lookup"><span data-stu-id="e61ec-360">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="e61ec-361">Questo esempio mostra uno scenario in cui non sono impostate mappature per la configurazione della dimensione in Power Apps, quindi la registrazione deve utilizzare anche le dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="e61ec-361">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="e61ec-362">Tutte le dimensioni devono essere dimensioni di base quando il campo `dimensionDataSource` è nullo, vuoto o spazio bianco.</span><span class="sxs-lookup"><span data-stu-id="e61ec-362">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="e61ec-363">Proprietà dei campi del documento JSON</span><span class="sxs-lookup"><span data-stu-id="e61ec-363">JSON document field properties</span></span>

<span data-ttu-id="e61ec-364">I campi degli esempi di query JSON forniti in precedenza hanno le proprietà elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e61ec-364">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="e61ec-365">ID campo</span><span class="sxs-lookup"><span data-stu-id="e61ec-365">Field ID</span></span> | <span data-ttu-id="e61ec-366">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e61ec-366">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="e61ec-367">Un ID univoco per l'evento di modifica specifico.</span><span class="sxs-lookup"><span data-stu-id="e61ec-367">A unique ID for the specific change event.</span></span> <span data-ttu-id="e61ec-368">Questo ID viene utilizzato per garantire che se la comunicazione con il servizio non riesce durante la registrazione, il reinvio dell'evento non comporta il doppio conteggio dello stesso evento nel sistema.</span><span class="sxs-lookup"><span data-stu-id="e61ec-368">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="e61ec-369">L'identificatore dell'organizzazione collegata all'evento.</span><span class="sxs-lookup"><span data-stu-id="e61ec-369">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="e61ec-370">Viene mappato agli ID area dati o alle organizzazioni di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e61ec-370">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="e61ec-371">L'identificatore del prodotto in questione.</span><span class="sxs-lookup"><span data-stu-id="e61ec-371">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="e61ec-372">La quantità in base alla quale è necessario modificare la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="e61ec-372">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="e61ec-373">Se, ad esempio, 10 nuovi bagel venissero aggiunti a uno scaffale, questo valore sarebbe 10.</span><span class="sxs-lookup"><span data-stu-id="e61ec-373">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="e61ec-374">Se 3 bagel venissero poi rimossi dallo scaffale o venduti, questo valore sarebbe -3.</span><span class="sxs-lookup"><span data-stu-id="e61ec-374">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="e61ec-375">L'origine dati delle dimensioni utilizzate nella query e nell'evento di modifica della registrazione.</span><span class="sxs-lookup"><span data-stu-id="e61ec-375">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="e61ec-376">Se si specifica l'origine dati, è possibile utilizzare le dimensioni personalizzate dell'origine dati specificata.</span><span class="sxs-lookup"><span data-stu-id="e61ec-376">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="e61ec-377">Con la configurazione delle dimensioni, Visibilità magazzino può mappare le dimensioni personalizzate alle dimensioni predefinite generali.</span><span class="sxs-lookup"><span data-stu-id="e61ec-377">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="e61ec-378">Se `dimensionDataSource` non è specificato, è possibile utilizzare solo le dimensioni predefinite generali nelle query.</span><span class="sxs-lookup"><span data-stu-id="e61ec-378">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="e61ec-379">Un insieme dinamico di coppie chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="e61ec-379">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="e61ec-380">Questi verranno mappati ad alcune dimensioni in Supply Chain Management, ma è possibile anche aggiungere dimensioni personalizzate (come *origine*) che può indicare se l'evento proveniva da Supply Chain Management o da un sistema esterno.</span><span class="sxs-lookup"><span data-stu-id="e61ec-380">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="e61ec-381">Interrogazione delle quantità disponibili correnti</span><span class="sxs-lookup"><span data-stu-id="e61ec-381">Querying current on-hand</span></span>

<span data-ttu-id="e61ec-382">L'endpoint per l'interrogazione delle quantità disponibili correnti avrà un URL simile:</span><span class="sxs-lookup"><span data-stu-id="e61ec-382">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="e61ec-383">Sarà interrogato con il metodo HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="e61ec-383">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="e61ec-384">Esempio di query delle quantità disponibili correnti 1</span><span class="sxs-lookup"><span data-stu-id="e61ec-384">Current on-hand query example 1</span></span>

<span data-ttu-id="e61ec-385">Questo esempio mostra uno scenario in cui è già stata impostata la configurazione della dimensione in Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e61ec-385">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="e61ec-386">Utilizzare la seguente query per configurare la mappatura delle dimensioni in Power Apps:</span><span class="sxs-lookup"><span data-stu-id="e61ec-386">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="e61ec-387">Ora è possibile specificare `dimensionDataSource` e utilizzare le dimensioni personalizzate nelle query.</span><span class="sxs-lookup"><span data-stu-id="e61ec-387">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="e61ec-388">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="e61ec-388">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="e61ec-389">È possibile specificare `DimensionDataSource` in `filters` e specificare le dimensioni personalizzate in `filters` e `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="e61ec-389">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="e61ec-390">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="e61ec-390">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="e61ec-391">Esempio di query delle quantità disponibili correnti 2</span><span class="sxs-lookup"><span data-stu-id="e61ec-391">Current on-hand query example 2</span></span>

<span data-ttu-id="e61ec-392">Questo esempio mostra uno scenario in cui non sono impostate mappature per la configurazione della dimensione in Power Apps, quindi la registrazione deve utilizzare anche le dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="e61ec-392">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="e61ec-393">Tutte le dimensioni devono essere dimensioni di base quando il campo `dimensionDataSource` in `filters` è nullo, vuoto o spazio bianco.</span><span class="sxs-lookup"><span data-stu-id="e61ec-393">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="e61ec-394">Esempio di risultato restituito</span><span class="sxs-lookup"><span data-stu-id="e61ec-394">Example return result</span></span>

<span data-ttu-id="e61ec-395">Le query mostrate negli esempi precedenti potrebbero restituire un risultato come questo.</span><span class="sxs-lookup"><span data-stu-id="e61ec-395">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="e61ec-396">Notare che i campi delle quantità sono strutturati come un dizionario di misure e dei valori associati.</span><span class="sxs-lookup"><span data-stu-id="e61ec-396">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
