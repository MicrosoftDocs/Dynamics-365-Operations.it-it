---
title: Eseguire l'aggiornamento al modello di parte e di rubrica globale
description: In questo argomento viene descritto come aggiornare i dati a doppia scrittura al modello di parte e rubrica globale.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 90ddbe704ab21d62752b581a813601e8986c2103
ms.sourcegitcommit: 180548e3c10459776cf199989d3753e0c1555912
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "6112675"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="d3a4b-103">Eseguire l'aggiornamento al modello di parte e di rubrica globale</span><span class="sxs-lookup"><span data-stu-id="d3a4b-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d3a4b-104">Il [modello di Microsoft Azure Data Factory](https://aka.ms/dual-write-gab-adf) consente di aggiornare i dati di tabella **Account**, **Contatto** e **Fornitore** in doppia scrittura al modello di parte e rubrica globale.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-104">The [Microsoft Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="d3a4b-105">Il modello riconcilia i dati delle app Finance and Operations e delle applicazioni di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-105">The template reconciles the data from both finance and operations apps and customer engagement applications.</span></span> <span data-ttu-id="d3a4b-106">Alla fine del processo, i campi **Parte** e **Contatto** per i record **Parte** verranno creati e associati ai record **Account**, **Contatto** e **Fornitore** nelle applicazioni di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="d3a4b-107">Un file .csv (`FONewParty.csv`) viene generato per creare nuovi record **Parte** nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the finance and operations app.</span></span> <span data-ttu-id="d3a4b-108">In questo argomento vengono fornite istruzioni per utilizzare il modello Data Factory e aggiornare i dati.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-108">This topic provides instructions about how to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="d3a4b-109">Se non disponi di personalizzazioni, puoi utilizzare il modello così com'è.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-109">If you don’t have any customizations, you can use the template as is.</span></span> <span data-ttu-id="d3a4b-110">Se hai personalizzazioni per **Account**, **Contatto** e **Fornitore** devi modificare il modello utilizzando le seguenti istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="d3a4b-111">Il modello aiuta ad aggiornare solo i dati **Parte**.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-111">The template only upgrades the **Party** data.</span></span> <span data-ttu-id="d3a4b-112">In una versione futura verranno inclusi indirizzi postali ed elettronici.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3a4b-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d3a4b-113">Prerequisites</span></span>

<span data-ttu-id="d3a4b-114">I seguenti prerequisiti sono necessari per eseguire l'aggiornamento al modello di rubrica indirizzi globale e del gruppo:</span><span class="sxs-lookup"><span data-stu-id="d3a4b-114">The following prerequisites are required to upgrade to the party and global address book model:</span></span>

+ [<span data-ttu-id="d3a4b-115">Sottoscrizione di Azure</span><span class="sxs-lookup"><span data-stu-id="d3a4b-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="d3a4b-116">Accesso al modello</span><span class="sxs-lookup"><span data-stu-id="d3a4b-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="d3a4b-117">Devi essere un cliente esistente che utilizza la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-117">You must be an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="d3a4b-118">Preparazione per l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d3a4b-118">Prepare for the upgrade</span></span>
<span data-ttu-id="d3a4b-119">Le seguenti attività sono necessarie per preparare l'aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="d3a4b-119">The following activities are needed to prepare for the upgrade:</span></span>

+ <span data-ttu-id="d3a4b-120">**Completamente sincronizzato**: entrambi gli ambienti sono completamente sincronizzati per **Account (cliente)**, **Contatto** e **Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-120">**Fully synced**: Both environments are in a fully synced state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="d3a4b-121">**Chiavi di integrazione**: le tabelle **Account (cliente)**, **Contatto** e **Fornitore** nelle app di interazione con i clienti utilizzano le chiavi di integrazione fornite immediatamente.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-121">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="d3a4b-122">Se hai personalizzato le chiavi di integrazione, devi personalizzare il modello.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-122">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="d3a4b-123">**Numero parte**: tutti i record **Account (cliente)**, **Contatto** e **Fornitore** che verranno aggiornati hanno un numero **Parte**.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-123">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="d3a4b-124">I record senza un numero **Parte** verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-124">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="d3a4b-125">Se desideri aggiornare questi record, aggiungici un numero **Parte** prima di iniziare il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-125">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="d3a4b-126">**Interruzione del sistema**: durante il processo di aggiornamento, Finance and Operations e ambienti di interazione con i clienti devono essere offline.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-126">**System outage**: During the upgrade process, you will have to take both the finance and operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="d3a4b-127">**Snapshot**: prendi snapshot di Finance and Operations e delle app di interazione dei clienti.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-127">**Snapshot**: Take snapshots of both the finance and operations apps and customer engagement apps.</span></span> <span data-ttu-id="d3a4b-128">Usa le snapshot per ripristinare lo stato precedente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-128">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="d3a4b-129">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="d3a4b-129">Deployment</span></span>

1. <span data-ttu-id="d3a4b-130">Scarica il modello da [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span><span class="sxs-lookup"><span data-stu-id="d3a4b-130">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="d3a4b-131">Accedi a [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="d3a4b-131">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="d3a4b-132">Crea un [gruppo di risorse](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="d3a4b-132">Create a [resource group](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="d3a4b-133">Crea un [account di archiviazione](/azure/storage/common/storage-account-create?tabs=azure-portal) nel gruppo di risorse che hai creato.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-133">Create a [storage account](/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="d3a4b-134">Crea un [data factory](/azure/data-factory/quickstart-create-data-factory-portal) nel gruppo di risorse sopra che hai creato.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-134">Create a [data factory](/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="d3a4b-135">Apri il data factory e seleziona il riquadro **Creare e monitorare**.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-135">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="d3a4b-136">Nella scheda **Gestisci**, seleziona **Modello ARM**.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-136">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="d3a4b-137">Seleziona **Importa modello ARM** per importare il modello **Parte**.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-137">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="d3a4b-138">Importa il modello nel data factory.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-138">Import the template into the data factory.</span></span> <span data-ttu-id="d3a4b-139">Immettere i seguenti valori per **Dettagli del progetto** e **Dettagli dell'istanza**.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-139">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="d3a4b-140">Campo</span><span class="sxs-lookup"><span data-stu-id="d3a4b-140">Field</span></span> | <span data-ttu-id="d3a4b-141">Valore</span><span class="sxs-lookup"><span data-stu-id="d3a4b-141">Value</span></span>
    ---|---
    <span data-ttu-id="d3a4b-142">Abbonamento</span><span class="sxs-lookup"><span data-stu-id="d3a4b-142">Subscription</span></span> | <span data-ttu-id="d3a4b-143">Sottoscrizione di Azure</span><span class="sxs-lookup"><span data-stu-id="d3a4b-143">Azure subscription</span></span>
    <span data-ttu-id="d3a4b-144">Gruppo di risorse</span><span class="sxs-lookup"><span data-stu-id="d3a4b-144">Resource group</span></span> | <span data-ttu-id="d3a4b-145">Fornire la stessa risorsa in cui viene creato l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-145">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="d3a4b-146">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="d3a4b-146">Region</span></span> | <span data-ttu-id="d3a4b-147">Specifica l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-147">Specify region.</span></span>
    <span data-ttu-id="d3a4b-148">Nome factory</span><span class="sxs-lookup"><span data-stu-id="d3a4b-148">Factory Name</span></span> | <span data-ttu-id="d3a4b-149">Specifica il nome della factory.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-149">Specify factory name.</span></span>
    <span data-ttu-id="d3a4b-150">FO Linked Service_service Principal Key</span><span class="sxs-lookup"><span data-stu-id="d3a4b-150">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="d3a4b-151">Specifica la chiave dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-151">Specify the application's key.</span></span>
    <span data-ttu-id="d3a4b-152">Azure Blob Storage_connection String</span><span class="sxs-lookup"><span data-stu-id="d3a4b-152">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="d3a4b-153">Stringa di connessione di Archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-153">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="d3a4b-154">Dynamics Crm Linked Service_password</span><span class="sxs-lookup"><span data-stu-id="d3a4b-154">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="d3a4b-155">La password per l'account utente specificato come nome utente.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-155">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="d3a4b-156">FO Linked Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="d3a4b-156">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="d3a4b-157">FO Linked Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="d3a4b-157">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="d3a4b-158">Specifica le informazioni sul tenant (nome di dominio o ID tenant) in cui risiede l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-158">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="d3a4b-159">FO Linked Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="d3a4b-159">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="d3a4b-160">FO Linked Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="d3a4b-160">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="d3a4b-161">Specifica l'ID client dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-161">Specify the application's client ID.</span></span>
    <span data-ttu-id="d3a4b-162">Dynamics Crm Linked Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="d3a4b-162">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="d3a4b-163">Il nome utente per la connessione a Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-163">The username to connect to Dynamics 365.</span></span>

    <span data-ttu-id="d3a4b-164">Per ulteriori informazioni, fare riferimento ai seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="d3a4b-164">For additional information, refer to the following topics:</span></span> 
    
    - [<span data-ttu-id="d3a4b-165">Promuovere manualmente un modello di Resource Manager per ogni ambiente</span><span class="sxs-lookup"><span data-stu-id="d3a4b-165">Manually promote a Resource Manager template for each environment</span></span>](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [<span data-ttu-id="d3a4b-166">Proprietà del servizio collegato</span><span class="sxs-lookup"><span data-stu-id="d3a4b-166">Linked service properties</span></span>](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [<span data-ttu-id="d3a4b-167">Copiare i dati usando Azure Data Factory</span><span class="sxs-lookup"><span data-stu-id="d3a4b-167">Copy data using Azure Data Factory</span></span>](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. <span data-ttu-id="d3a4b-168">Dopo la distribuzione, convalidare i set di dati, il flusso di dati e il servizio collegato del data factory.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-168">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Set di dati, flusso di dati e servizio collegato](media/data-factory-validate.png)

11. <span data-ttu-id="d3a4b-170">Vai a **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-170">Navigate to **Manage**.</span></span> <span data-ttu-id="d3a4b-171">Sotto **Connessioni**, seleziona **Servizio collegato**.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-171">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="d3a4b-172">Seleziona **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-172">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="d3a4b-173">Nel modulo **Modifica servizio collegato (Dynamics CRM)**, inserisci i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-173">In the **Edit linked service (Dynamics CRM)** form, enter the following values.</span></span>

    <span data-ttu-id="d3a4b-174">Campo</span><span class="sxs-lookup"><span data-stu-id="d3a4b-174">Field</span></span> | <span data-ttu-id="d3a4b-175">Valore</span><span class="sxs-lookup"><span data-stu-id="d3a4b-175">Value</span></span>
    ---|---
    <span data-ttu-id="d3a4b-176">Nome</span><span class="sxs-lookup"><span data-stu-id="d3a4b-176">Name</span></span> | <span data-ttu-id="d3a4b-177">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="d3a4b-177">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="d3a4b-178">descrizione</span><span class="sxs-lookup"><span data-stu-id="d3a4b-178">Description</span></span> | <span data-ttu-id="d3a4b-179">I servizi collegati per connettersi con l'istanza CRM per recuperare i dati delle entità</span><span class="sxs-lookup"><span data-stu-id="d3a4b-179">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="d3a4b-180">Connetti via runtime di integrazione</span><span class="sxs-lookup"><span data-stu-id="d3a4b-180">Connect via integration runtime</span></span> | <span data-ttu-id="d3a4b-181">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="d3a4b-181">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="d3a4b-182">Tipo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="d3a4b-182">Deployment type</span></span> | <span data-ttu-id="d3a4b-183">In linea</span><span class="sxs-lookup"><span data-stu-id="d3a4b-183">Online</span></span>
    <span data-ttu-id="d3a4b-184">Uri servizio</span><span class="sxs-lookup"><span data-stu-id="d3a4b-184">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="d3a4b-185">Tipo di autenticazione</span><span class="sxs-lookup"><span data-stu-id="d3a4b-185">Authentication type</span></span> | <span data-ttu-id="d3a4b-186">Office365</span><span class="sxs-lookup"><span data-stu-id="d3a4b-186">Office365</span></span>
    <span data-ttu-id="d3a4b-187">Nome utente</span><span class="sxs-lookup"><span data-stu-id="d3a4b-187">User name</span></span> |
    <span data-ttu-id="d3a4b-188">Password o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="d3a4b-188">Password or Azure Key Vault</span></span> | <span data-ttu-id="d3a4b-189">Password</span><span class="sxs-lookup"><span data-stu-id="d3a4b-189">Password</span></span>
    <span data-ttu-id="d3a4b-190">Password</span><span class="sxs-lookup"><span data-stu-id="d3a4b-190">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="d3a4b-191">Eseguire il modello</span><span class="sxs-lookup"><span data-stu-id="d3a4b-191">Run the template</span></span>

1. <span data-ttu-id="d3a4b-192">Interrompi i mapping a doppia scrittura seguenti di **Account**, **Contatto** e **Fornitore** utilizzando l'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-192">Stop the following **Account**, **Contact**, and **Vendor** dual-write maps using the Finance and Operations app.</span></span>

    + <span data-ttu-id="d3a4b-193">Clienti V3 (conti)</span><span class="sxs-lookup"><span data-stu-id="d3a4b-193">Customers V3(accounts)</span></span>
    + <span data-ttu-id="d3a4b-194">Clienti V3(contacts)</span><span class="sxs-lookup"><span data-stu-id="d3a4b-194">Customers V3(contacts)</span></span>
    + <span data-ttu-id="d3a4b-195">Contatti CDS V2(contacts)</span><span class="sxs-lookup"><span data-stu-id="d3a4b-195">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="d3a4b-196">Contatti CDS V2(contacts)</span><span class="sxs-lookup"><span data-stu-id="d3a4b-196">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="d3a4b-197">Fornitore V2 (msdyn_vendor)</span><span class="sxs-lookup"><span data-stu-id="d3a4b-197">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="d3a4b-198">Assicurati che le mappe vengano rimosse dalla tabella `msdy_dualwriteruntimeconfig` in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-198">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="d3a4b-199">Installa le [soluzioni di doppia scrittura per parte e rubrica globale](https://aka.ms/dual-write-gab) da AppSource.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-199">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="d3a4b-200">Nell'app Finance and Operations, se le seguenti tabelle contengono dati, allora esegui **Sincronizzazione iniziale** per le stesse.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-200">In the finance and operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="d3a4b-201">Formule di apertura</span><span class="sxs-lookup"><span data-stu-id="d3a4b-201">Salutations</span></span>
    + <span data-ttu-id="d3a4b-202">Tipi di carattere personale</span><span class="sxs-lookup"><span data-stu-id="d3a4b-202">Personal character types</span></span>
    + <span data-ttu-id="d3a4b-203">Formula di chiusura</span><span class="sxs-lookup"><span data-stu-id="d3a4b-203">Complimentary closing</span></span>
    + <span data-ttu-id="d3a4b-204">Titoli contatti</span><span class="sxs-lookup"><span data-stu-id="d3a4b-204">Contact person titles</span></span>
    + <span data-ttu-id="d3a4b-205">Ruoli nel processo decisionale</span><span class="sxs-lookup"><span data-stu-id="d3a4b-205">Decision making roles</span></span>
    + <span data-ttu-id="d3a4b-206">Livelli fedeltà</span><span class="sxs-lookup"><span data-stu-id="d3a4b-206">Loyalty levels</span></span>

5. <span data-ttu-id="d3a4b-207">Nell'app di interazione con i clienti, disabilita i seguenti passaggi del plug-in.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-207">In the customer engagement app, disable the following plug-in steps.</span></span>

    + <span data-ttu-id="d3a4b-208">Aggiornamento account</span><span class="sxs-lookup"><span data-stu-id="d3a4b-208">Account Update</span></span>
         + <span data-ttu-id="d3a4b-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aggiornamento dell'account</span><span class="sxs-lookup"><span data-stu-id="d3a4b-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="d3a4b-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aggiornamento dell'account</span><span class="sxs-lookup"><span data-stu-id="d3a4b-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="d3a4b-211">Aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-211">Contact Update</span></span>
         + <span data-ttu-id="d3a4b-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="d3a4b-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="d3a4b-214">Aggiornamento di msdyn_party</span><span class="sxs-lookup"><span data-stu-id="d3a4b-214">msdyn_party Update</span></span>
         + <span data-ttu-id="d3a4b-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aggiornamento di msdyn_party</span><span class="sxs-lookup"><span data-stu-id="d3a4b-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="d3a4b-216">Aggiornamento di msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="d3a4b-216">msdyn_vendor Update</span></span>
         + <span data-ttu-id="d3a4b-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aggiornamento di msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="d3a4b-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="d3a4b-218">Nell'app di interazione con i clienti, disabilita i seguenti flussi di lavoro:</span><span class="sxs-lookup"><span data-stu-id="d3a4b-218">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="d3a4b-219">Creare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-219">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="d3a4b-220">Creare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-220">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="d3a4b-221">Creare fornitori di tipo Persona nella tabella Contatti</span><span class="sxs-lookup"><span data-stu-id="d3a4b-221">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="d3a4b-222">Creare fornitori di tipo Persona nella tabella fornitori</span><span class="sxs-lookup"><span data-stu-id="d3a4b-222">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="d3a4b-223">Aggiornare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-223">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="d3a4b-224">Aggiornare fornitori nella tabella Fornitori</span><span class="sxs-lookup"><span data-stu-id="d3a4b-224">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="d3a4b-225">Aggiornare fornitori di tipo Persona nella tabella Contatti</span><span class="sxs-lookup"><span data-stu-id="d3a4b-225">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="d3a4b-226">Aggiornare fornitori di tipo Persona nella tabella fornitori</span><span class="sxs-lookup"><span data-stu-id="d3a4b-226">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="d3a4b-227">Nel data factory, esegui il modello selezionando **Attiva ora** come mostrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-227">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="d3a4b-228">Il completamento di questo processo potrebbe richiedere alcune ore in base al volume di dati.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-228">This process might take a few hours to complete based on the data volume.</span></span>

    ![Attiva ora](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="d3a4b-230">Se hai personalizzazioni per **Account**, **Contatto** e **Fornitore** devi modificare il modello.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-230">If you have customizations for **Account**, **Contact**, and **Vendor**, then you need to modify the template.</span></span>

8. <span data-ttu-id="d3a4b-231">Importa i nuovi record **Parte** nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-231">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="d3a4b-232">Scarica il file `FONewParty.csv` da archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-232">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="d3a4b-233">Il percorso è `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-233">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="d3a4b-234">Converti il file `FONewParty.csv` in un file Excel e importa il file Excel nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-234">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the finance and operations app.</span></span> <span data-ttu-id="d3a4b-235">Se l'importazione del file CSV funziona, puoi importare direttamente il file CSV.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-235">If the csv import works for you, you can import the csv file directly.</span></span> <span data-ttu-id="d3a4b-236">L'esecuzione dell'importazione potrebbe richiedere alcune ore, a seconda del volume di dati.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-236">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="d3a4b-237">Per ulteriori informazioni, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="d3a4b-237">For more information, see [Data import and export jobs overview](../data-import-export-job.md).</span></span>

    ![Importare i record Parte di Datavers](media/data-factory-import-party.png)

9. <span data-ttu-id="d3a4b-239">Nell'app di interazione con i clienti, abilita i seguenti passaggi del plug-in:</span><span class="sxs-lookup"><span data-stu-id="d3a4b-239">In the customer engagement apps, enable the following plug-in steps:</span></span>

    + <span data-ttu-id="d3a4b-240">Aggiornamento account</span><span class="sxs-lookup"><span data-stu-id="d3a4b-240">Account Update</span></span>
         + <span data-ttu-id="d3a4b-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aggiornamento dell'account</span><span class="sxs-lookup"><span data-stu-id="d3a4b-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="d3a4b-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aggiornamento dell'account</span><span class="sxs-lookup"><span data-stu-id="d3a4b-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="d3a4b-243">Aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-243">Contact Update</span></span>
         + <span data-ttu-id="d3a4b-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="d3a4b-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="d3a4b-246">Aggiornamento di msdyn_party</span><span class="sxs-lookup"><span data-stu-id="d3a4b-246">msdyn_party Update</span></span>
         + <span data-ttu-id="d3a4b-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aggiornamento di msdyn_party</span><span class="sxs-lookup"><span data-stu-id="d3a4b-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="d3a4b-248">Aggiornamento di msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="d3a4b-248">msdyn_vendor Update</span></span>
         + <span data-ttu-id="d3a4b-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aggiornamento di msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="d3a4b-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="d3a4b-250">Nelle app di interazione con i clienti, attiva i seguenti flussi di lavoro se li hai disattivati nei passaggi precedenti:</span><span class="sxs-lookup"><span data-stu-id="d3a4b-250">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="d3a4b-251">Creare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-251">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="d3a4b-252">Creare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-252">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="d3a4b-253">Creare fornitori di tipo Persona nella tabella Contatti</span><span class="sxs-lookup"><span data-stu-id="d3a4b-253">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="d3a4b-254">Creare fornitori di tipo Persona nella tabella fornitori</span><span class="sxs-lookup"><span data-stu-id="d3a4b-254">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="d3a4b-255">Aggiornare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="d3a4b-255">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="d3a4b-256">Aggiornare fornitori nella tabella Fornitori</span><span class="sxs-lookup"><span data-stu-id="d3a4b-256">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="d3a4b-257">Aggiornare fornitori di tipo Persona nella tabella Contatti</span><span class="sxs-lookup"><span data-stu-id="d3a4b-257">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="d3a4b-258">Aggiornare fornitori di tipo Persona nella tabella fornitori</span><span class="sxs-lookup"><span data-stu-id="d3a4b-258">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="d3a4b-259">Esegui le mappe correlate a **Parte** come indicato in [Parte e rubrica globale](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="d3a4b-259">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d3a4b-260">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="d3a4b-260">Troubleshooting</span></span>

1. <span data-ttu-id="d3a4b-261">Se il processo non riesce, esegui nuovamente il data factory a partire dall'attività non riuscita.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-261">If the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="d3a4b-262">Alcuni file vengono generati dal data factory utilizzabile per la convalida dei dati.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-262">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="d3a4b-263">Il data factory viene eseguito in base ai file CSV delimitati da virgole.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-263">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="d3a4b-264">Se è presente un valore di campo con una virgola, potrebbe interferire con i risultati.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-264">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="d3a4b-265">Devi rimuovere le virgole.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-265">You need to remove the commas.</span></span>
4. <span data-ttu-id="d3a4b-266">La scheda **Monitoraggio** fornisce informazioni su tutti i passaggi e i dati elaborati.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-266">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="d3a4b-267">Seleziona un passaggio specifico per eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="d3a4b-267">Select a specific step to debug it.</span></span>

    ![Scheda Monitoraggio](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="d3a4b-269">Ulteriori informazioni sul modello</span><span class="sxs-lookup"><span data-stu-id="d3a4b-269">Learn more about the template</span></span>

<span data-ttu-id="d3a4b-270">Puoi trovare ulteriori informazioni sul modello in [Commenti per il file Leggimi del modello di Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="d3a4b-270">You can find additional information about the template in [Comments for Azure Data Factory template readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span></span>
