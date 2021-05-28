---
title: Componente aggiuntivo Visibilità magazzino
description: Questo argomento descrive come installare e configurare il componente aggiuntivo Visibilità magazzino per Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 84f5e949f0c81f840c8a9086d05bbcfc576e42aa
ms.sourcegitcommit: b67665ed689c55df1a67d1a7840947c3977d600c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6017008"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="26d1d-103">Componente aggiuntivo Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="26d1d-104">Il componente aggiuntivo Visibilità magazzino è un microservizio indipendente e altamente scalabile che consente il monitoraggio dell'inventario disponibile in tempo reale, fornendo così una visione globale della visibilità dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="26d1d-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="26d1d-105">Tutte le informazioni relative alle scorte disponibili vengono esportate nel servizio quasi in tempo reale tramite l'integrazione SQL di basso livello.</span><span class="sxs-lookup"><span data-stu-id="26d1d-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="26d1d-106">I sistemi esterni accedono al servizio tramite API RESTful per interrogare le informazioni sulle scorte disponibili su determinati set di dimensioni, recuperando così un elenco di posizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="26d1d-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="26d1d-107">Visibilità magazzino è un microservizio basato su Microsoft Dataverse, il che significa che è possibile estenderlo creando Power Apps e applicando Power BI per fornire funzionalità personalizzate per soddisfare i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="26d1d-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="26d1d-108">È anche possibile aggiornare l'indice per eseguire query sull'inventario.</span><span class="sxs-lookup"><span data-stu-id="26d1d-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="26d1d-109">Visibilità magazzino fornisce opzioni di configurazione che consentono l'integrazione con più sistemi di terze parti.</span><span class="sxs-lookup"><span data-stu-id="26d1d-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="26d1d-110">Supporta la dimensione dell'inventario standardizzata, l'estensibilità personalizzata e le quantità calcolate standardizzate e configurabili.</span><span class="sxs-lookup"><span data-stu-id="26d1d-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="26d1d-111">Questo argomento descrive come installare e configurare il componente aggiuntivo Visibilità magazzino per Dynamics 365 Supply Chain Management e come utilizzare l'API.</span><span class="sxs-lookup"><span data-stu-id="26d1d-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="26d1d-112">Installare il componente aggiuntivo Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="26d1d-113">È necessario installare il componente aggiuntivo Visibilità magazzino utilizzando Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="26d1d-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="26d1d-114">LCS è un portale di collaborazione che fornisce un ambiente e una serie di servizi regolarmente aggiornati che aiutano a gestire il ciclo di vita dell'applicazione delle app Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="26d1d-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="26d1d-115">Per ulteriori informazioni, vedere [Risorse Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span><span class="sxs-lookup"><span data-stu-id="26d1d-115">For more information, see [Lifecycle Services resources](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span></span>

### <a name="inventory-visibility-add-in-prerequisites"></a><span data-ttu-id="26d1d-116">Prerequisiti per il componente aggiuntivo Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-116">Inventory Visibility Add-in prerequisites</span></span>

<span data-ttu-id="26d1d-117">Prima di poter installare il componente aggiuntivo Visibilità magazzino è necessario effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="26d1d-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="26d1d-118">Ottenere un progetto di implementazione LCS con almeno un ambiente distribuito.</span><span class="sxs-lookup"><span data-stu-id="26d1d-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="26d1d-119">Assicurati che i prerequisiti per la configurazione dei componenti aggiuntivi forniti in [Panoramica dei componenti aggiuntivi](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) siano stati soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="26d1d-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="26d1d-120">Visibilità magazzino non richiede un collegamento a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="26d1d-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="26d1d-121">Contattare il team di Visibilità magazzino all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) per ottenere i seguenti tre file:</span><span class="sxs-lookup"><span data-stu-id="26d1d-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - <span data-ttu-id="26d1d-122">`Inventory Visibility Integration.zip` (se la versione di Supply Chain Management in esecuzione è precedente alla versione 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="26d1d-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>
- <span data-ttu-id="26d1d-123">In alternativa, contattare il team di Visibilità magazzino all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) per ottenere i pacchetti Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="26d1d-123">Alternatively, contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package deployer packages.</span></span> <span data-ttu-id="26d1d-124">Questi pacchetti possono essere utilizzati da uno strumento Package Deployer ufficiale.</span><span class="sxs-lookup"><span data-stu-id="26d1d-124">These packages can be used by an official package deployer tool.</span></span>
  - `InventoryServiceBase.PackageDeployer.zip`
  - <span data-ttu-id="26d1d-125">`InventoryServiceApplication.PackageDeployer.zip` (questo pacchetto contiene tutte le modifiche nel pacchetto `InventoryServiceBase` e ulteriori componenti applicativi dell'interfaccia utente)</span><span class="sxs-lookup"><span data-stu-id="26d1d-125">`InventoryServiceApplication.PackageDeployer.zip` (this package contains all of the changes in the `InventoryServiceBase` package, plus additional UI application components)</span></span>
- <span data-ttu-id="26d1d-126">Segui le istruzioni fornite in [Avvio rapido: registrare un'applicazione con la piattaforma di identità Microsoft](/azure/active-directory/develop/quickstart-register-app) per registrare un'applicazione e aggiungere un segreto client ad AAD nella sottoscrizione di Azure.</span><span class="sxs-lookup"><span data-stu-id="26d1d-126">Follow the instructions given in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register an application and add a client secret to AAD under your azure subscription.</span></span>
  - [<span data-ttu-id="26d1d-127">Registrare un'applicazione</span><span class="sxs-lookup"><span data-stu-id="26d1d-127">Register an application</span></span>](/azure/active-directory/develop/quickstart-register-app)
  - [<span data-ttu-id="26d1d-128">Aggiungere un segreto cliente</span><span class="sxs-lookup"><span data-stu-id="26d1d-128">Add a client secret</span></span>](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - <span data-ttu-id="26d1d-129">**ID applicazione (client)**, **Segreto cliente** e **ID tenant** verranno utilizzati nei seguenti passaggi.</span><span class="sxs-lookup"><span data-stu-id="26d1d-129">The **Application(Client) Id**, **Client Secret**, and **Tenant ID** will be used in the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="26d1d-130">I paesi e le regioni attualmente supportati includono Canada, Stati Uniti e Unione europea (UE).</span><span class="sxs-lookup"><span data-stu-id="26d1d-130">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="26d1d-131">In caso di domande su questi prerequisiti, contattare il team del prodotto Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-131">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="26d1d-132">Configurare Dataverse</span><span class="sxs-lookup"><span data-stu-id="26d1d-132">Set up Dataverse</span></span>

<span data-ttu-id="26d1d-133">Per configurare Dataverse per l'utilizzo con Visibilità magazzino, è necessario dapprima preparare i prerequisiti e quindi decidere se eseguire la configurazione di Dataverse utilizzando lo strumento Package Deployer o importando manualmente le soluzioni (non è necessario eseguire entrambe le operazioni).</span><span class="sxs-lookup"><span data-stu-id="26d1d-133">To set up Dataverse for use with Inventory Visibility, you must first prepare the prerequisites and then decide whether to set up Dataverse using either the package deployer tool or by manually importing the solutions (you don't have to do both).</span></span> <span data-ttu-id="26d1d-134">Installare quindi il componente aggiuntivo Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-134">Then install the Inventory Visibility Add-in.</span></span> <span data-ttu-id="26d1d-135">Nelle sottosezioni seguenti viene descritto come completare ognuna di queste attività.</span><span class="sxs-lookup"><span data-stu-id="26d1d-135">The following subsections describe how to complete each of these tasks.</span></span>

#### <a name="prepare-dataverse-prerequisites"></a><span data-ttu-id="26d1d-136">Preparare i prerequisiti di Dataverse</span><span class="sxs-lookup"><span data-stu-id="26d1d-136">Prepare Dataverse prerequisites</span></span>

<span data-ttu-id="26d1d-137">Prima di iniziare la configurazione di Dataverse, aggiungere un principio di servizio al tenant effettuando le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="26d1d-137">Before you start to set up Dataverse, add a service principle to your tenant by doing the following:</span></span>

1. <span data-ttu-id="26d1d-138">Installare Azure AD PowerShell Module v2 come descritto in [Installare Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="26d1d-138">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>

1. <span data-ttu-id="26d1d-139">Eseguire il comando PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="26d1d-139">Run the following PowerShell command:</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a><span data-ttu-id="26d1d-140">Configurare Dataverse utilizzando lo strumento Package Deployer</span><span class="sxs-lookup"><span data-stu-id="26d1d-140">Set up Dataverse using the package deployer tool</span></span>

<span data-ttu-id="26d1d-141">Dopo aver soddisfatto i prerequisiti, utilizzare la procedura seguente se si preferisce eseguire la configurazione di Dataverse utilizzando lo strumento Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="26d1d-141">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse using the package deployer tool.</span></span> <span data-ttu-id="26d1d-142">Vedere la sezione successiva per dettagli su come importare le soluzioni manualmente (non fare entrambe le cose).</span><span class="sxs-lookup"><span data-stu-id="26d1d-142">See the next section for details about how to import the solutions manually instead (don't do both).</span></span>

1. <span data-ttu-id="26d1d-143">Installare gli strumenti di sviluppo come descritto in [Scaricare strumenti da NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span><span class="sxs-lookup"><span data-stu-id="26d1d-143">Install developer tools as described in [Download tools from NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span></span>

1. <span data-ttu-id="26d1d-144">In base alle esigenze aziendali, scegliere il pacchetto `InventoryServiceBase` o `InventoryServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="26d1d-144">Based on your business requirements, choose the `InventoryServiceBase` or `InventoryServiceApplication` package.</span></span>

1. <span data-ttu-id="26d1d-145">Importare le soluzioni:</span><span class="sxs-lookup"><span data-stu-id="26d1d-145">Import the solutions:</span></span>
    1. <span data-ttu-id="26d1d-146">Per il pacchetto `InventoryServiceBase`:</span><span class="sxs-lookup"><span data-stu-id="26d1d-146">For the `InventoryServiceBase` package:</span></span>
        - <span data-ttu-id="26d1d-147">Decomprimere `InventoryServiceBase.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="26d1d-147">Unzip `InventoryServiceBase.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="26d1d-148">Trovare la cartella `InventoryServiceBase`, il file `[Content_Types].xml`, il file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, il file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config` e il file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="26d1d-148">Find folder `InventoryServiceBase`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span></span> 
        - <span data-ttu-id="26d1d-149">Copiare ognuno di questi file e cartelle nella directory `.\Tools\PackageDeployment`, che è stata creata durante l'installazione degli strumenti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="26d1d-149">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="26d1d-150">Per il pacchetto `InventoryServiceApplication`:</span><span class="sxs-lookup"><span data-stu-id="26d1d-150">For the `InventoryServiceApplication` package:</span></span>
        - <span data-ttu-id="26d1d-151">Decomprimere `InventoryServiceApplication.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="26d1d-151">Unzip `InventoryServiceApplication.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="26d1d-152">Trovare la cartella `InventoryServiceApplication`, il file `[Content_Types].xml`, il file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, il file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config` e il file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="26d1d-152">Find folder `InventoryServiceApplication`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span></span>
        - <span data-ttu-id="26d1d-153">Copiare ognuno di questi file e cartelle nella directory `.\Tools\PackageDeployment`, che è stata creata durante l'installazione degli strumenti di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="26d1d-153">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="26d1d-154">Eseguire `.\Tools\PackageDeployment\PackageDeployer.exe`.</span><span class="sxs-lookup"><span data-stu-id="26d1d-154">Execute `.\Tools\PackageDeployment\PackageDeployer.exe`.</span></span> <span data-ttu-id="26d1d-155">Seguire le istruzioni sullo schermo per importare le soluzioni.</span><span class="sxs-lookup"><span data-stu-id="26d1d-155">Follow the instructions on your screen to import the solutions.</span></span>

1. <span data-ttu-id="26d1d-156">Assegnare ruoli di sicurezza all'utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26d1d-156">Assign security roles to the application user.</span></span>
    1. <span data-ttu-id="26d1d-157">Aprire l'URL del proprio ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="26d1d-157">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="26d1d-158">Selezionare **Impostazioni avanzate \> Sistema \> Sicurezza \> Utenti** e trovare l'utente denominato **# InventoryVisibility**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-158">Go to **Advanced Setting \> System \> Security \> Users**, and find user the named **# InventoryVisibility**.</span></span>
    1. <span data-ttu-id="26d1d-159">Selezionare **Assegna ruolo** e quindi selezionare **Amministratore di sistema**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-159">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="26d1d-160">Se è presente un ruolo denominato **Utente Common Data Service**, selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="26d1d-160">If there is a role that is named **Common Data Service User**, select it as well.</span></span>

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a><span data-ttu-id="26d1d-161">Configurare Dataverse manualmente importando le soluzioni</span><span class="sxs-lookup"><span data-stu-id="26d1d-161">Set up Dataverse manually by importing solutions</span></span>

<span data-ttu-id="26d1d-162">Dopo aver soddisfatto i prerequisiti, utilizzare la procedura seguente se si preferisce eseguire la configurazione di Dataverse importando manualmente le soluzioni.</span><span class="sxs-lookup"><span data-stu-id="26d1d-162">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse by manually importing solutions.</span></span> <span data-ttu-id="26d1d-163">Vedere la sezione precedente per dettagli su come utilizzare lo strumento Package Deployer (non fare entrambe le cose).</span><span class="sxs-lookup"><span data-stu-id="26d1d-163">See the previous section for details about how to use the package deployer tool instead (don't do both).</span></span>

1. <span data-ttu-id="26d1d-164">Creare un utente applicazione per Visibilità magazzino in Dataverse:</span><span class="sxs-lookup"><span data-stu-id="26d1d-164">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="26d1d-165">Aprire l'URL del proprio ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="26d1d-165">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="26d1d-166">Selezionare **Impostazioni avanzate \> Sistema \> Sicurezza \> Utenti** e creare un utente applicazione.</span><span class="sxs-lookup"><span data-stu-id="26d1d-166">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="26d1d-167">Utilizzare il menu Visualizza per cambiare la visualizzazione della pagina in **Utenti applicazione**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-167">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="26d1d-168">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-168">Select **New**.</span></span> <span data-ttu-id="26d1d-169">Impostare l'ID applicazione su *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*</span><span class="sxs-lookup"><span data-stu-id="26d1d-169">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="26d1d-170">(l'ID oggetto verrà caricato automaticamente quando si salvano le modifiche). È possibile personalizzare il nome.</span><span class="sxs-lookup"><span data-stu-id="26d1d-170">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="26d1d-171">Ad esempio, è possibile modificarlo in *Visibilità magazzino*.</span><span class="sxs-lookup"><span data-stu-id="26d1d-171">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="26d1d-172">Al termine, selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-172">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="26d1d-173">Selezionare **Assegna ruolo** e quindi selezionare **Amministratore di sistema**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-173">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="26d1d-174">Se è presente un ruolo denominato **Utente Common Data Service**, selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="26d1d-174">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="26d1d-175">Per ulteriori informazioni, vedere [Creare un utente applicazione](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="26d1d-175">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="26d1d-176">Se la lingua predefinita di Dataverse non è **inglese**:</span><span class="sxs-lookup"><span data-stu-id="26d1d-176">If the default language of your Dataverse is not **English**:</span></span>

    1. <span data-ttu-id="26d1d-177">Vai a **Impostazioni avanzate \> Amministrazione \> Lingue**,</span><span class="sxs-lookup"><span data-stu-id="26d1d-177">Go to **Advanced Setting \> Administration \> Languages**,</span></span>
    1. <span data-ttu-id="26d1d-178">Seleziona **Inglese (LanguageCode = 1033)** e seleziona **Applica**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-178">Select **English (LanguageCode=1033)** and select **Apply**.</span></span>

1. <span data-ttu-id="26d1d-179">Importare il file `Inventory Visibility Dataverse Solution.zip`, che include entità relative alla configurazione di Dataverse e Power Apps:</span><span class="sxs-lookup"><span data-stu-id="26d1d-179">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="26d1d-180">Accedere alla pagina **Soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-180">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="26d1d-181">Selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-181">Select **Import**.</span></span>

1. <span data-ttu-id="26d1d-182">Importare il flusso di attivazione dell'aggiornamento della configurazione:</span><span class="sxs-lookup"><span data-stu-id="26d1d-182">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="26d1d-183">Accedere alla pagina di Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="26d1d-183">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="26d1d-184">Assicurarsi che la connessione denominata *Dataverse (legacy)* esista</span><span class="sxs-lookup"><span data-stu-id="26d1d-184">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="26d1d-185">(in caso contrario, crearla).</span><span class="sxs-lookup"><span data-stu-id="26d1d-185">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="26d1d-186">Importare il file `Inventory Visibility Configuration Trigger.zip`.</span><span class="sxs-lookup"><span data-stu-id="26d1d-186">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="26d1d-187">Dopo l'importazione, il trigger apparirà sotto **Flussi personali**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-187">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="26d1d-188">Inizializzare le seguenti quattro variabili, in base alle informazioni sull'ambiente:</span><span class="sxs-lookup"><span data-stu-id="26d1d-188">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="26d1d-189">ID tenant di Azure</span><span class="sxs-lookup"><span data-stu-id="26d1d-189">Azure Tenant ID</span></span>
        - <span data-ttu-id="26d1d-190">ID client applicazione Azure</span><span class="sxs-lookup"><span data-stu-id="26d1d-190">Azure Application Client ID</span></span>
        - <span data-ttu-id="26d1d-191">Segreto client applicazione Azure</span><span class="sxs-lookup"><span data-stu-id="26d1d-191">Azure Application Client Secret</span></span>
        - <span data-ttu-id="26d1d-192">Endpoint Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-192">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="26d1d-193">Per ulteriori informazioni su questa variabile, vedere la sezione [Impostare l'integrazione di Visibilità magazzino](#setup-inventory-visibility-integration) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="26d1d-193">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="26d1d-194">![Trigger di configurazione](media/configuration-trigger.png "Trigger di configurazione")</span><span class="sxs-lookup"><span data-stu-id="26d1d-194">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="26d1d-195">Selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-195">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="26d1d-196">Installare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="26d1d-196">Install the add-in</span></span>

<span data-ttu-id="26d1d-197">Per installare il componente aggiuntivo Visibilità magazzino effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="26d1d-197">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="26d1d-198">Accedere al portale [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="26d1d-198">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="26d1d-199">Nella home page, selezionare il progetto in cui è distribuito l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="26d1d-199">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="26d1d-200">Nella pagina del progetto, selezionare l'ambiente in cui si desidera installare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="26d1d-200">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="26d1d-201">Nella pagina dell'ambiente, scorrere verso il basso fino a visualizzare la sezione **Componenti aggiuntivi dell'ambiente** in **Integrazione di Power Platform**, dove è possibile trovare il nome dell'ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="26d1d-201">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="26d1d-202">Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-202">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="26d1d-203">![La pagina dell'ambiente in LCS](media/inventory-visibility-environment.png "La pagina dell'ambiente in LCS")</span><span class="sxs-lookup"><span data-stu-id="26d1d-203">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="26d1d-204">Selezionare il collegamento **Installare un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-204">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="26d1d-205">Si apre un elenco di componenti aggiuntivi disponibili.</span><span class="sxs-lookup"><span data-stu-id="26d1d-205">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="26d1d-206">Selezionare **Visibilità magazzino** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="26d1d-206">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="26d1d-207">Immettere i valori per i seguenti campi per il proprio ambiente:</span><span class="sxs-lookup"><span data-stu-id="26d1d-207">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="26d1d-208">**ID (client) applicazione AAD**</span><span class="sxs-lookup"><span data-stu-id="26d1d-208">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="26d1d-209">**ID tenant AAD**</span><span class="sxs-lookup"><span data-stu-id="26d1d-209">**AAD tenant ID**</span></span>

    <span data-ttu-id="26d1d-210">![Pagina Impostazione del componente aggiuntivo](media/inventory-visibility-setup.png "Pagina Impostazione del componente aggiuntivo")</span><span class="sxs-lookup"><span data-stu-id="26d1d-210">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="26d1d-211">Accettare le condizioni selezionando la casella di controllo **Condizioni**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-211">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="26d1d-212">Seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-212">Select **Install**.</span></span> <span data-ttu-id="26d1d-213">Lo stato del componente aggiuntivo verrà visualizzato com e **Installazione**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-213">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="26d1d-214">Al termine, aggiornare la pagina per vedere lo stato cambiare in **Installato**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-214">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="26d1d-215">Disinstallare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="26d1d-215">Uninstall the add-in</span></span>

<span data-ttu-id="26d1d-216">Per disinstallare il componente aggiuntivo, selezionar e **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-216">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="26d1d-217">Quando si aggiorna LCS, il componente aggiuntivo Visibilità magazzino verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="26d1d-217">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="26d1d-218">Il processo di disinstallazione rimuove la registrazione del componente aggiuntivo e avvia anche un processo per pulire tutti i dati aziendali archiviati nel servizio.</span><span class="sxs-lookup"><span data-stu-id="26d1d-218">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="26d1d-219">Utilizzare i dati delle scorte disponibili di Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="26d1d-219">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="26d1d-220">Distribuire il pacchetto di integrazione di Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-220">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="26d1d-221">Se si utilizza Supply Chain Management versione 10.0.17 o versione precedente, contattare il team di supporto di Visibilità magazzino all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) per ottenere il file del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="26d1d-221">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="26d1d-222">Distribuire quindi il pacchetto in LCS.</span><span class="sxs-lookup"><span data-stu-id="26d1d-222">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="26d1d-223">Se durante la distribuzione si verifica un errore di mancata corrispondenza della versione, è necessario importare manualmente il progetto X++ nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="26d1d-223">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="26d1d-224">Creare quindi il pacchetto distribuibile nell'ambiente di sviluppo e distribuirlo nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="26d1d-224">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="26d1d-225">Il codice è incluso con Supply Chain Management versione 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="26d1d-225">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="26d1d-226">Se si esegue quella versione o una versione successiva, la distribuzione non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="26d1d-226">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="26d1d-227">Assicurarsi che le seguenti funzionalità siano attivate nell'ambiente Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="26d1d-227">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="26d1d-228">(per impostazione predefinita, sono attivate).</span><span class="sxs-lookup"><span data-stu-id="26d1d-228">(By default, they are turned on.)</span></span>

| <span data-ttu-id="26d1d-229">Descrizione delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="26d1d-229">Feature description</span></span> | <span data-ttu-id="26d1d-230">Versione codice</span><span class="sxs-lookup"><span data-stu-id="26d1d-230">Code version</span></span> | <span data-ttu-id="26d1d-231">Alterna classe</span><span class="sxs-lookup"><span data-stu-id="26d1d-231">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="26d1d-232">Abilitare o disabilitare l'utilizzo delle dimensioni inventariali nella tabella InventSum</span><span class="sxs-lookup"><span data-stu-id="26d1d-232">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="26d1d-233">10.0.11</span><span class="sxs-lookup"><span data-stu-id="26d1d-233">10.0.11</span></span> | <span data-ttu-id="26d1d-234">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="26d1d-234">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="26d1d-235">Abilitare o disabilitare l'utilizzo delle dimensioni inventariali nella tabella InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="26d1d-235">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="26d1d-236">10.0.12</span><span class="sxs-lookup"><span data-stu-id="26d1d-236">10.0.12</span></span> | <span data-ttu-id="26d1d-237">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="26d1d-237">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="26d1d-238">Impostare l'integrazione di Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-238">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="26d1d-239">In Supply Chain Management, aprire l'area di lavoro **[Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e attivare la funzionalità **Integrazione di Visibilità magazzino**.</span><span class="sxs-lookup"><span data-stu-id="26d1d-239">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="26d1d-240">Selezionare **Gestione articoli \> Impostazioni \> Parametri di integrazione di Visibilità magazzino** e immettere l'URL dell'ambiente in cui si esegue Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-240">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="26d1d-241">Trovare l'area di Azure dell'ambiente LCS e quindi immettere l'URL.</span><span class="sxs-lookup"><span data-stu-id="26d1d-241">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="26d1d-242">Il formato dell'URL è come segue:</span><span class="sxs-lookup"><span data-stu-id="26d1d-242">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="26d1d-243">Ad esempio, se si è in Europa, l'ambiente avrà uno dei seguenti URL:</span><span class="sxs-lookup"><span data-stu-id="26d1d-243">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="26d1d-244">Sono attualmente disponibili le seguenti regioni:</span><span class="sxs-lookup"><span data-stu-id="26d1d-244">The following regions are currently available.</span></span>

    | <span data-ttu-id="26d1d-245">Regione Azure</span><span class="sxs-lookup"><span data-stu-id="26d1d-245">Azure region</span></span> | <span data-ttu-id="26d1d-246">Nome breve della regione</span><span class="sxs-lookup"><span data-stu-id="26d1d-246">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="26d1d-247">Australia orientale</span><span class="sxs-lookup"><span data-stu-id="26d1d-247">Australia east</span></span> | <span data-ttu-id="26d1d-248">eau</span><span class="sxs-lookup"><span data-stu-id="26d1d-248">eau</span></span> |
    | <span data-ttu-id="26d1d-249">Australia sud-orientale</span><span class="sxs-lookup"><span data-stu-id="26d1d-249">Australia southeast</span></span> | <span data-ttu-id="26d1d-250">seau</span><span class="sxs-lookup"><span data-stu-id="26d1d-250">seau</span></span> |
    | <span data-ttu-id="26d1d-251">Canada centrale</span><span class="sxs-lookup"><span data-stu-id="26d1d-251">Canada central</span></span> | <span data-ttu-id="26d1d-252">cca</span><span class="sxs-lookup"><span data-stu-id="26d1d-252">cca</span></span> |
    | <span data-ttu-id="26d1d-253">Canada orientale</span><span class="sxs-lookup"><span data-stu-id="26d1d-253">Canada east</span></span> | <span data-ttu-id="26d1d-254">eca</span><span class="sxs-lookup"><span data-stu-id="26d1d-254">eca</span></span> |
    | <span data-ttu-id="26d1d-255">Europa settentrionale</span><span class="sxs-lookup"><span data-stu-id="26d1d-255">North Europe</span></span> | <span data-ttu-id="26d1d-256">neu</span><span class="sxs-lookup"><span data-stu-id="26d1d-256">neu</span></span> |
    | <span data-ttu-id="26d1d-257">Europa occidentale</span><span class="sxs-lookup"><span data-stu-id="26d1d-257">West Europe</span></span> | <span data-ttu-id="26d1d-258">weu</span><span class="sxs-lookup"><span data-stu-id="26d1d-258">weu</span></span> |
    | <span data-ttu-id="26d1d-259">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="26d1d-259">East US</span></span> | <span data-ttu-id="26d1d-260">eus</span><span class="sxs-lookup"><span data-stu-id="26d1d-260">eus</span></span> |
    | <span data-ttu-id="26d1d-261">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="26d1d-261">West US</span></span> | <span data-ttu-id="26d1d-262">wus</span><span class="sxs-lookup"><span data-stu-id="26d1d-262">wus</span></span> |

1. <span data-ttu-id="26d1d-263">Selezionare **Gestione articoli \> Periodico \> Integrazione di Visibilità magazzino** e abilitare il processo.</span><span class="sxs-lookup"><span data-stu-id="26d1d-263">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="26d1d-264">Tutti gli eventi di modifica delle scorte di Supply Chain Management verranno ora registrati in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-264">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="26d1d-265">API pubblica del componente aggiuntivo Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-265">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="26d1d-266">L'API REST pubblica del componente aggiuntivo Visibilità magazzino presenta diversi endpoint specifici per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="26d1d-266">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="26d1d-267">Supporta tre principali tipi di interazione:</span><span class="sxs-lookup"><span data-stu-id="26d1d-267">It supports three main interaction types:</span></span>

- <span data-ttu-id="26d1d-268">Registrazione delle modifiche delle scorte disponibili nel componente aggiuntivo da un sistema esterno</span><span class="sxs-lookup"><span data-stu-id="26d1d-268">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="26d1d-269">Interrogazione delle quantità disponibili correnti da un sistema esterno</span><span class="sxs-lookup"><span data-stu-id="26d1d-269">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="26d1d-270">Sincronizzazione automatica con le scorte disponibili di Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="26d1d-270">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="26d1d-271">La sincronizzazione automatica non fa parte dell'API pubblica.</span><span class="sxs-lookup"><span data-stu-id="26d1d-271">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="26d1d-272">È invece gestita in background per gli ambienti in cui è abilitato il componente aggiuntivo Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-272">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="26d1d-273">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="26d1d-273">Authentication</span></span>

<span data-ttu-id="26d1d-274">Il token di sicurezza della piattaforma viene utilizzato per chiamare il componente aggiuntivo Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-274">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="26d1d-275">Pertanto, è necessario generare un token *Azure Active Directory (Azure AD)* usando l'applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26d1d-275">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="26d1d-276">È quindi necessario utilizzare il token Azure AD per ottenere il *token di accesso* dal servizio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="26d1d-276">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="26d1d-277">Ottenere un token del servizio di sicurezza effettuando le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="26d1d-277">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="26d1d-278">Accedere al portale di Azure e utilizzarlo per trovare `clientId` e `clientSecret` per l'applicazione Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="26d1d-278">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="26d1d-279">Recuperare un token Azure Active Directory (`aadToken`) inviando una richiesta HTTP con le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="26d1d-279">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="26d1d-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="26d1d-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="26d1d-281">**Metodo** - `GET`</span><span class="sxs-lookup"><span data-stu-id="26d1d-281">**Method** - `GET`</span></span>
    - <span data-ttu-id="26d1d-282">**Contenuto del corpo (dati del modulo)**:</span><span class="sxs-lookup"><span data-stu-id="26d1d-282">**Body content (form data)**:</span></span>

        | <span data-ttu-id="26d1d-283">chiave</span><span class="sxs-lookup"><span data-stu-id="26d1d-283">key</span></span> | <span data-ttu-id="26d1d-284">valore</span><span class="sxs-lookup"><span data-stu-id="26d1d-284">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="26d1d-285">client_id</span><span class="sxs-lookup"><span data-stu-id="26d1d-285">client_id</span></span> | <span data-ttu-id="26d1d-286">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="26d1d-286">${aadAppId}</span></span> |
        | <span data-ttu-id="26d1d-287">client_secret</span><span class="sxs-lookup"><span data-stu-id="26d1d-287">client_secret</span></span> | <span data-ttu-id="26d1d-288">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="26d1d-288">${aadAppSecret}</span></span> |
        | <span data-ttu-id="26d1d-289">grant_type</span><span class="sxs-lookup"><span data-stu-id="26d1d-289">grant_type</span></span> | <span data-ttu-id="26d1d-290">client_credentials</span><span class="sxs-lookup"><span data-stu-id="26d1d-290">client_credentials</span></span> |
        | <span data-ttu-id="26d1d-291">risorsa</span><span class="sxs-lookup"><span data-stu-id="26d1d-291">resource</span></span> | <span data-ttu-id="26d1d-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="26d1d-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="26d1d-293">Dovresti ricevere un `aadToken` in risposta, che assomiglia al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="26d1d-293">You should receive an `aadToken` in response, which resembles the following example.</span></span>

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

1. <span data-ttu-id="26d1d-294">Formulare una richiesta JSON simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="26d1d-294">Formulate a JSON request that resembles the following:</span></span>

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

    <span data-ttu-id="26d1d-295">Percorso:</span><span class="sxs-lookup"><span data-stu-id="26d1d-295">Where:</span></span>
    - <span data-ttu-id="26d1d-296">Il valore `client_assertion` deve essere `aadToken` ricevuto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="26d1d-296">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="26d1d-297">Il valore `context` deve essere l'ID dell'ambiente in cui si desidera distribuire il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="26d1d-297">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="26d1d-298">Impostare tutti gli altri valori come mostrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="26d1d-298">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="26d1d-299">Inviare una richiesta HTTP con le seguenti proprietà:</span><span class="sxs-lookup"><span data-stu-id="26d1d-299">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="26d1d-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="26d1d-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="26d1d-301">**Metodo** - `POST`</span><span class="sxs-lookup"><span data-stu-id="26d1d-301">**Method** - `POST`</span></span>
    - <span data-ttu-id="26d1d-302">**Intestazione HTTP**: includere la versione API (la chiave è `Api-Version` e il valore è `1.0`)</span><span class="sxs-lookup"><span data-stu-id="26d1d-302">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="26d1d-303">**Contenuto del corpo**: includi la richiesta JSON che hai creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="26d1d-303">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="26d1d-304">Viene restituito un `access_token` in risposta.</span><span class="sxs-lookup"><span data-stu-id="26d1d-304">You will get an `access_token` in response.</span></span> <span data-ttu-id="26d1d-305">Questo è ciò di cui si ha bisogno come token di connessione per chiamare l'API di Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-305">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="26d1d-306">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="26d1d-306">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a><span data-ttu-id="26d1d-307">Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="26d1d-307">Sample Request</span></span>

<span data-ttu-id="26d1d-308">Per riferimento, di seguito è illustrata una richiesta http di esempio; puoi utilizzare qualsiasi strumento o linguaggio di codifica per inviare questa richiesta, ad esempio ``Postman``.</span><span class="sxs-lookup"><span data-stu-id="26d1d-308">For your reference, here is a sample http request, you can use any tools or coding language to send this request, such as  ``Postman``.</span></span>

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="26d1d-309">Configurare l'API di Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-309">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="26d1d-310">Prima di utilizzare il servizio, è necessario completare le configurazioni descritte nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="26d1d-310">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="26d1d-311">La configurazione può variare in base ai dettagli del proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="26d1d-311">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="26d1d-312">Comprende principalmente quattro parti:</span><span class="sxs-lookup"><span data-stu-id="26d1d-312">It primarily includes four parts:</span></span>

- [<span data-ttu-id="26d1d-313">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="26d1d-313">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="26d1d-314">Configurazioni delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="26d1d-314">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="26d1d-315">Indicizzazione</span><span class="sxs-lookup"><span data-stu-id="26d1d-315">Indexing</span></span>](#indexing)
- [<span data-ttu-id="26d1d-316">Misura personalizzata</span><span class="sxs-lookup"><span data-stu-id="26d1d-316">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="26d1d-317">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="26d1d-317">Partitioning</span></span>

<span data-ttu-id="26d1d-318">Il partizionamento può influenzare in modo significativo le prestazioni dell'API di Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-318">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="26d1d-319">È una buona idea definire uno schema che consenta piccoli raggruppamenti di dati pur consentendo query di dati significative.</span><span class="sxs-lookup"><span data-stu-id="26d1d-319">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="26d1d-320">L'elemento `organizationId` (`dataAreaId` in Supply Chain Management) farà sempre parte del partizionamento e, per impostazione predefinita, Visibilità magazzino è impostato su partizionamento per dimensioni come *Sito + Posizione*.</span><span class="sxs-lookup"><span data-stu-id="26d1d-320">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="26d1d-321">Ciò significa che il servizio deve essere sempre interrogato con queste dimensioni definite sui filtri.</span><span class="sxs-lookup"><span data-stu-id="26d1d-321">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="26d1d-322">*Sito* e *Posizione* sono due dimensioni predefinite generali in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-322">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="26d1d-323">In Supply Chain Management, queste dimensioni vengono chiamate *Sito* (`InventSiteId`) e *Magazzino* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="26d1d-323">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="26d1d-324">Configurazioni delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="26d1d-324">Dimension configurations</span></span>

<span data-ttu-id="26d1d-325">Visibilità magazzino fornirà un elenco di dimensioni predefinite generali per abilitare l'integrazione di più sistemi di origine.</span><span class="sxs-lookup"><span data-stu-id="26d1d-325">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="26d1d-326">La tabella seguente elenca le dimensioni dell'inventario che saranno i nomi delle dimensioni predefinite in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-326">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="26d1d-327">Tipo di dimensione</span><span class="sxs-lookup"><span data-stu-id="26d1d-327">Dimension type</span></span> | <span data-ttu-id="26d1d-328">Nome dimensione</span><span class="sxs-lookup"><span data-stu-id="26d1d-328">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="26d1d-329">Prodotto</span><span class="sxs-lookup"><span data-stu-id="26d1d-329">Product</span></span> | `ColorId` |
| <span data-ttu-id="26d1d-330">Prodotto</span><span class="sxs-lookup"><span data-stu-id="26d1d-330">Product</span></span> | `SizeId` |
| <span data-ttu-id="26d1d-331">Prodotto</span><span class="sxs-lookup"><span data-stu-id="26d1d-331">Product</span></span> | `StyleId` |
| <span data-ttu-id="26d1d-332">Prodotto</span><span class="sxs-lookup"><span data-stu-id="26d1d-332">Product</span></span> | `ConfigId` |
| <span data-ttu-id="26d1d-333">Tracciabilità</span><span class="sxs-lookup"><span data-stu-id="26d1d-333">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="26d1d-334">Tracciabilità</span><span class="sxs-lookup"><span data-stu-id="26d1d-334">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="26d1d-335">Posizione</span><span class="sxs-lookup"><span data-stu-id="26d1d-335">Location</span></span> | `LocationId` |
| <span data-ttu-id="26d1d-336">Posizione</span><span class="sxs-lookup"><span data-stu-id="26d1d-336">Location</span></span> | `SiteId` |
| <span data-ttu-id="26d1d-337">Stato inventario</span><span class="sxs-lookup"><span data-stu-id="26d1d-337">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="26d1d-338">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-338">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="26d1d-339">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-339">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="26d1d-340">Specifico del magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-340">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="26d1d-341">Il tipo di dimensione elencato nella tabella precedente è solo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="26d1d-341">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="26d1d-342">Non è necessario definire il tipo di dimensione in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-342">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="26d1d-343">Se esiste una dimensione personalizzata che diventare un valore predefinito quando viene utilizzata da Visibilità magazzino, è possibile configurare il nome **Dimensione personalizzata** in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-343">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="26d1d-344">I sistemi esterni accedono a Visibilità magazzino tramite le API RESTful che consentono di interrogare le informazioni disponibili su determinati set di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="26d1d-344">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="26d1d-345">Per l'integrazione, Visibilità magazzino consente di configurare l'*origine dati del canale esterno* e la dimensione di origine sulle *dimensioni di destinazione* in Visibilità magazzino.</span><span class="sxs-lookup"><span data-stu-id="26d1d-345">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="26d1d-346">Le dimensioni di destinazione deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="26d1d-346">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="26d1d-347">Dimensioni predefinite in Visibilità magazzino</span><span class="sxs-lookup"><span data-stu-id="26d1d-347">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="26d1d-348">Dimensioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="26d1d-348">Custom dimensions</span></span>

<span data-ttu-id="26d1d-349">Lo scopo della configurazione delle dimensioni è standardizzare l'integrazione multi-sistema per la query sulle dimensioni e l'evento di registrazione con le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="26d1d-349">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="26d1d-350">Indicizzazione</span><span class="sxs-lookup"><span data-stu-id="26d1d-350">Indexing</span></span>

<span data-ttu-id="26d1d-351">La maggior parte delle volte, la query delle scorte disponibili non sarà solo sul livello "totale" più alto, ma si potrebbe voler vedere i risultati aggregati in base alle dimensioni dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="26d1d-351">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="26d1d-352">Visibilità magazzino offre flessibilità consentendo di impostare gli indici, che si basano sulla dimensione o sulla combinazione delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="26d1d-352">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="26d1d-353">Al momento, è possibile configurare solo fino a un massimo di cinque indici.</span><span class="sxs-lookup"><span data-stu-id="26d1d-353">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="26d1d-354">È necessario considerare attentamente quale dimensione o combinazione di dimensioni si utilizzerà prima dell'implementazione per assicurarsi che soddisfi le esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="26d1d-354">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="26d1d-355">Ad esempio, se si desidera eseguire query sui prodotti come segue:</span><span class="sxs-lookup"><span data-stu-id="26d1d-355">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="26d1d-356">Query delle scorte del prodotto aggregato per dimensioni *Colore* e *Dimensione*.</span><span class="sxs-lookup"><span data-stu-id="26d1d-356">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="26d1d-357">In alcuni casi, si desidera solo eseguire una query sul prodotto in totale.</span><span class="sxs-lookup"><span data-stu-id="26d1d-357">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="26d1d-358">Sarebbero disponibili due indici definiti come segue:</span><span class="sxs-lookup"><span data-stu-id="26d1d-358">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="26d1d-359">La parentesi vuota si aggregherà in base all'ID del prodotto all'interno della partizione.</span><span class="sxs-lookup"><span data-stu-id="26d1d-359">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="26d1d-360">L'indicizzazione definisce come raggruppare i risultati in base all'impostazione della query `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="26d1d-360">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="26d1d-361">In questo caso se non si definiscono valori `groupBy` si ottengono i totali per `productid`.</span><span class="sxs-lookup"><span data-stu-id="26d1d-361">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="26d1d-362">Altrimenti se si definisce `groupBy` come `groupBy=ColorId&groupBy=SizeId`, verranno restituite più righe, in base alle diverse combinazioni di colori e dimensioni nel sistema.</span><span class="sxs-lookup"><span data-stu-id="26d1d-362">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="26d1d-363">È possibile inserire i criteri della query nel corpo della richiesta.</span><span class="sxs-lookup"><span data-stu-id="26d1d-363">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="26d1d-364">Ecco una query di esempio sul prodotto con combinazione di colore e dimensione.</span><span class="sxs-lookup"><span data-stu-id="26d1d-364">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
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

<span data-ttu-id="26d1d-365">Per il campo `filters`, attualmente solo `ProductId` supporta più valori.</span><span class="sxs-lookup"><span data-stu-id="26d1d-365">For the `filters` field, currently only `ProductId` supports multiple values.</span></span> <span data-ttu-id="26d1d-366">Se `ProductId` è un array vuoto, verrà eseguita una query su tutti i prodotti.</span><span class="sxs-lookup"><span data-stu-id="26d1d-366">If the `ProductId` is an empty array, all products will be queried.</span></span>

#### <a name="custom-measurement"></a><span data-ttu-id="26d1d-367">Misura personalizzata</span><span class="sxs-lookup"><span data-stu-id="26d1d-367">Custom measurement</span></span>

<span data-ttu-id="26d1d-368">Le quantità di misura predefinite sono collegate a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="26d1d-368">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="26d1d-369">Tuttavia, potrebbe essere necessario disporre di una quantità composta da una combinazione delle misure predefinite.</span><span class="sxs-lookup"><span data-stu-id="26d1d-369">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="26d1d-370">Per fare ciò, è possibile avere una configurazione di quantità personalizzate, che verranno aggiunte all'output delle query disponibili.</span><span class="sxs-lookup"><span data-stu-id="26d1d-370">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="26d1d-371">La funzionalità consente semplicemente di definire un insieme di misure che verranno aggiunte, e/o un insieme di misure che verranno sottratte, in modo da ottenere dalla misura personalizzata.</span><span class="sxs-lookup"><span data-stu-id="26d1d-371">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="26d1d-372">Ad esempio, con la seguente condizione di query, si configura la quantità di misura personalizzata come `MyCustomAvailableforReservation` per essere utilizzata dal sistema di consumo.</span><span class="sxs-lookup"><span data-stu-id="26d1d-372">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="26d1d-373">Sistema di consumo</span><span class="sxs-lookup"><span data-stu-id="26d1d-373">Consumption system</span></span> | <span data-ttu-id="26d1d-374">Misure calcolate</span><span class="sxs-lookup"><span data-stu-id="26d1d-374">Calculated measurers</span></span> | <span data-ttu-id="26d1d-375">Origine dati</span><span class="sxs-lookup"><span data-stu-id="26d1d-375">Data source</span></span> | <span data-ttu-id="26d1d-376">Modificatore</span><span class="sxs-lookup"><span data-stu-id="26d1d-376">Modifier</span></span> | <span data-ttu-id="26d1d-377">Tipo di calcolo del modificatore</span><span class="sxs-lookup"><span data-stu-id="26d1d-377">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="26d1d-378">Addizione</span><span class="sxs-lookup"><span data-stu-id="26d1d-378">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="26d1d-379">Addizione</span><span class="sxs-lookup"><span data-stu-id="26d1d-379">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="26d1d-380">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="26d1d-380">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="26d1d-381">Addizione</span><span class="sxs-lookup"><span data-stu-id="26d1d-381">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="26d1d-382">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="26d1d-382">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="26d1d-383">Addizione</span><span class="sxs-lookup"><span data-stu-id="26d1d-383">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="26d1d-384">Addizione</span><span class="sxs-lookup"><span data-stu-id="26d1d-384">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="26d1d-385">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="26d1d-385">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="26d1d-386">Sottrazione</span><span class="sxs-lookup"><span data-stu-id="26d1d-386">Subtraction</span></span> |

<span data-ttu-id="26d1d-387">Con ciò, la query sulla quantità di misura personalizzata restituirà il seguente output.</span><span class="sxs-lookup"><span data-stu-id="26d1d-387">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="26d1d-388">L'output `MyCustomAvailableforReservation` si basa sull'impostazione del calcolo nelle misure personalizzate come:</span><span class="sxs-lookup"><span data-stu-id="26d1d-388">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="26d1d-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="26d1d-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="26d1d-390">Registrazione delle modifiche delle scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="26d1d-390">Posting on-hand changes</span></span>

<span data-ttu-id="26d1d-391">L'URL esatto in cui verrà pubblicato l'evento dipenderà dalla regione geografica.</span><span class="sxs-lookup"><span data-stu-id="26d1d-391">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="26d1d-392">Avrà il formato:</span><span class="sxs-lookup"><span data-stu-id="26d1d-392">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="26d1d-393">Una volta autenticato, questo URL può essere utilizzato insieme al metodo HTTP `POST` per inviare al servizio eventi di modifica delle scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="26d1d-393">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="26d1d-394">Un'intestazione speciale viene utilizzata per comunicare con i servizi Dynamics 365 tramite richieste HTTP, indicando l'ID ambiente dell'istanza di Supply Chain Management a cui sono collegati i dati.</span><span class="sxs-lookup"><span data-stu-id="26d1d-394">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="26d1d-395">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="26d1d-395">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="26d1d-396">Registrazione delle modifiche delle scorte disponibili - esempio di query 1</span><span class="sxs-lookup"><span data-stu-id="26d1d-396">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="26d1d-397">Questo esempio mostra uno scenario in cui verrà impostata la configurazione della dimensione in Power Apps.</span><span class="sxs-lookup"><span data-stu-id="26d1d-397">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="26d1d-398">Utilizzare la seguente query per configurare la mappatura delle dimensioni in Power Apps:</span><span class="sxs-lookup"><span data-stu-id="26d1d-398">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="26d1d-399">Ora è possibile specificare `dimensionDataSource` e utilizzare le dimensioni personalizzate nelle query.</span><span class="sxs-lookup"><span data-stu-id="26d1d-399">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="26d1d-400">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="26d1d-400">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="26d1d-401">Registrazione delle modifiche delle scorte disponibili - esempio di query 2</span><span class="sxs-lookup"><span data-stu-id="26d1d-401">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="26d1d-402">Questo esempio mostra uno scenario in cui non sono impostate mappature per la configurazione della dimensione in Power Apps, quindi la registrazione deve utilizzare anche le dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="26d1d-402">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="26d1d-403">Tutte le dimensioni devono essere dimensioni di base quando il campo `dimensionDataSource` è nullo, vuoto o spazio bianco.</span><span class="sxs-lookup"><span data-stu-id="26d1d-403">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="26d1d-404">Proprietà dei campi del documento JSON</span><span class="sxs-lookup"><span data-stu-id="26d1d-404">JSON document field properties</span></span>

<span data-ttu-id="26d1d-405">I campi degli esempi di query JSON forniti in precedenza hanno le proprietà elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="26d1d-405">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="26d1d-406">ID campo</span><span class="sxs-lookup"><span data-stu-id="26d1d-406">Field ID</span></span> | <span data-ttu-id="26d1d-407">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26d1d-407">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="26d1d-408">Un ID univoco per l'evento di modifica specifico.</span><span class="sxs-lookup"><span data-stu-id="26d1d-408">A unique ID for the specific change event.</span></span> <span data-ttu-id="26d1d-409">Questo ID viene utilizzato per garantire che se la comunicazione con il servizio non riesce durante la registrazione, il reinvio dell'evento non comporta il doppio conteggio dello stesso evento nel sistema.</span><span class="sxs-lookup"><span data-stu-id="26d1d-409">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="26d1d-410">L'identificatore dell'organizzazione collegata all'evento.</span><span class="sxs-lookup"><span data-stu-id="26d1d-410">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="26d1d-411">Viene mappato agli ID area dati o alle organizzazioni di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="26d1d-411">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="26d1d-412">L'identificatore del prodotto in questione.</span><span class="sxs-lookup"><span data-stu-id="26d1d-412">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="26d1d-413">La quantità in base alla quale è necessario modificare la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="26d1d-413">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="26d1d-414">Se, ad esempio, 10 nuovi bagel venissero aggiunti a uno scaffale, questo valore sarebbe 10.</span><span class="sxs-lookup"><span data-stu-id="26d1d-414">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="26d1d-415">Se 3 bagel venissero poi rimossi dallo scaffale o venduti, questo valore sarebbe -3.</span><span class="sxs-lookup"><span data-stu-id="26d1d-415">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="26d1d-416">L'origine dati delle dimensioni utilizzate nella query e nell'evento di modifica della registrazione.</span><span class="sxs-lookup"><span data-stu-id="26d1d-416">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="26d1d-417">Se si specifica l'origine dati, è possibile utilizzare le dimensioni personalizzate dell'origine dati specificata.</span><span class="sxs-lookup"><span data-stu-id="26d1d-417">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="26d1d-418">Con la configurazione delle dimensioni, Visibilità magazzino può mappare le dimensioni personalizzate alle dimensioni predefinite generali.</span><span class="sxs-lookup"><span data-stu-id="26d1d-418">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="26d1d-419">Se `dimensionDataSource` non è specificato, è possibile utilizzare solo le dimensioni predefinite generali nelle query.</span><span class="sxs-lookup"><span data-stu-id="26d1d-419">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="26d1d-420">Un insieme dinamico di coppie chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="26d1d-420">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="26d1d-421">Questi verranno mappati ad alcune dimensioni in Supply Chain Management, ma è possibile anche aggiungere dimensioni personalizzate (come *origine*) che può indicare se l'evento proveniva da Supply Chain Management o da un sistema esterno.</span><span class="sxs-lookup"><span data-stu-id="26d1d-421">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="26d1d-422">Interrogazione delle quantità disponibili correnti</span><span class="sxs-lookup"><span data-stu-id="26d1d-422">Querying current on-hand</span></span>

<span data-ttu-id="26d1d-423">L'endpoint per l'interrogazione delle quantità disponibili correnti avrà un URL simile:</span><span class="sxs-lookup"><span data-stu-id="26d1d-423">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="26d1d-424">Sarà interrogato con il metodo HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="26d1d-424">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="26d1d-425">Esempio di query delle quantità disponibili correnti 1</span><span class="sxs-lookup"><span data-stu-id="26d1d-425">Current on-hand query example 1</span></span>

<span data-ttu-id="26d1d-426">Questo esempio mostra uno scenario in cui è già stata impostata la configurazione della dimensione in Power Apps.</span><span class="sxs-lookup"><span data-stu-id="26d1d-426">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="26d1d-427">Utilizzare la seguente query per configurare la mappatura delle dimensioni in Power Apps:</span><span class="sxs-lookup"><span data-stu-id="26d1d-427">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="26d1d-428">Ora è possibile specificare `dimensionDataSource` e utilizzare le dimensioni personalizzate nelle query.</span><span class="sxs-lookup"><span data-stu-id="26d1d-428">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="26d1d-429">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="26d1d-429">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="26d1d-430">È possibile specificare `DimensionDataSource` in `filters` e specificare le dimensioni personalizzate in `filters` e `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="26d1d-430">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="26d1d-431">Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="26d1d-431">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="26d1d-432">Esempio di query delle quantità disponibili correnti 2</span><span class="sxs-lookup"><span data-stu-id="26d1d-432">Current on-hand query example 2</span></span>

<span data-ttu-id="26d1d-433">Questo esempio mostra uno scenario in cui non sono impostate mappature per la configurazione della dimensione in Power Apps, quindi la registrazione deve utilizzare anche le dimensioni di base.</span><span class="sxs-lookup"><span data-stu-id="26d1d-433">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="26d1d-434">Tutte le dimensioni devono essere dimensioni di base quando il campo `dimensionDataSource` in `filters` è nullo, vuoto o spazio bianco.</span><span class="sxs-lookup"><span data-stu-id="26d1d-434">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="26d1d-435">Esempio di risultato restituito</span><span class="sxs-lookup"><span data-stu-id="26d1d-435">Example return result</span></span>

<span data-ttu-id="26d1d-436">Le query mostrate negli esempi precedenti potrebbero restituire un risultato come questo.</span><span class="sxs-lookup"><span data-stu-id="26d1d-436">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="26d1d-437">Notare che i campi delle quantità sono strutturati come un dizionario di misure e dei valori associati.</span><span class="sxs-lookup"><span data-stu-id="26d1d-437">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
