---
title: Eseguire l'aggiornamento al modello di parte e di rubrica globale
description: In questo argomento viene descritto come aggiornare i dati a doppia scrittura al modello di parte e rubrica globale.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 76e64d483e833782733277a64d8dc37cbeba6130
ms.sourcegitcommit: 011468a6cffea8641bebc2922e0676d9f44b36fc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "5857372"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="514cb-103">Eseguire l'aggiornamento al modello di parte e di rubrica globale</span><span class="sxs-lookup"><span data-stu-id="514cb-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="514cb-104">Il [modello di Azure Data Factory](https://aka.ms/dual-write-gab-adf) consente di aggiornare i dati di tabella **Account**, **Contatto** e **Fornitore** in doppia scrittura al modello di parte e rubrica globale.</span><span class="sxs-lookup"><span data-stu-id="514cb-104">The [Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="514cb-105">Il modello riconcilia i dati delle app Finance and Operations e delle applicazioni di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="514cb-105">The template reconciles the data from both Finance and Operations apps and customer engagement applications.</span></span> <span data-ttu-id="514cb-106">Alla fine del processo, i campi **Parte** e **Contatto** per i record **Parte** verranno creati e associati ai record **Account**, **Contatto** e **Fornitore** nelle applicazioni di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="514cb-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="514cb-107">Un file .csv (`FONewParty.csv`) viene generato per creare nuovi record **Parte** nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="514cb-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the Finance and Operations app.</span></span> <span data-ttu-id="514cb-108">In questo argomento vengono fornite istruzioni per utilizzare il modello Data Factory e aggiornare i dati.</span><span class="sxs-lookup"><span data-stu-id="514cb-108">This topic provides the instructions to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="514cb-109">Se non disponi di personalizzazioni, puoi utilizzare il modello così com'è.</span><span class="sxs-lookup"><span data-stu-id="514cb-109">If you don’t have any customizations, you can use the template as-is.</span></span> <span data-ttu-id="514cb-110">Se hai personalizzazioni per **Account**, **Contatto** e **Fornitore** devi modificare il modello utilizzando le seguenti istruzioni.</span><span class="sxs-lookup"><span data-stu-id="514cb-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!Note]
> <span data-ttu-id="514cb-111">Il modello aiuta ad aggiornare solo i dati **Parte**.</span><span class="sxs-lookup"><span data-stu-id="514cb-111">The template helps to upgrade only the **Party** data.</span></span> <span data-ttu-id="514cb-112">In una versione futura verranno inclusi indirizzi postali ed elettronici.</span><span class="sxs-lookup"><span data-stu-id="514cb-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="514cb-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="514cb-113">Prerequisites</span></span>

<span data-ttu-id="514cb-114">Questi prerequisiti sono obbligatori:</span><span class="sxs-lookup"><span data-stu-id="514cb-114">These prerequisites are required:</span></span>

+ [<span data-ttu-id="514cb-115">Sottoscrizione di Azure</span><span class="sxs-lookup"><span data-stu-id="514cb-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="514cb-116">Accesso al modello</span><span class="sxs-lookup"><span data-stu-id="514cb-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="514cb-117">Sei un cliente esistente che utilizza la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="514cb-117">You are an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="514cb-118">Preparazione per l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="514cb-118">Prepare for the upgrade</span></span>

+ <span data-ttu-id="514cb-119">**Completamente sincronizzato**: entrambi gli ambienti sono completamente sincronizzati per **Account (cliente)**, **Contatto** e **Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="514cb-119">**Fully synched**: Both environments are fully synched state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="514cb-120">**Chiavi di integrazione**: le tabelle **Account (cliente)**, **Contatto** e **Fornitore** nelle app di interazione con i clienti utilizzano le chiavi di integrazione fornite immediatamente.</span><span class="sxs-lookup"><span data-stu-id="514cb-120">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="514cb-121">Se hai personalizzato le chiavi di integrazione, devi personalizzare il modello.</span><span class="sxs-lookup"><span data-stu-id="514cb-121">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="514cb-122">**Numero parte**: tutti i record **Account (cliente)**, **Contatto** e **Fornitore** che verranno aggiornati hanno un numero **Parte**.</span><span class="sxs-lookup"><span data-stu-id="514cb-122">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="514cb-123">I record senza un numero **Parte** verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="514cb-123">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="514cb-124">Se desideri aggiornare questi record, aggiungici un numero **Parte** prima di iniziare il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="514cb-124">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="514cb-125">**Interruzione del sistema**: durante il processo di aggiornamento, Finance and Operations e ambienti di interazione con i clienti devono essere offline.</span><span class="sxs-lookup"><span data-stu-id="514cb-125">**System outage**: During the upgrade process, you will have to take both the Finance and Operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="514cb-126">**Snapshot**: prendi snapshot di Finance and Operations e delle app di interazione dei clienti.</span><span class="sxs-lookup"><span data-stu-id="514cb-126">**Snapshot**: Take snapshots of both the Finance and Operations and customer engagement apps.</span></span> <span data-ttu-id="514cb-127">Usa le snapshot per ripristinare lo stato precedente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="514cb-127">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="514cb-128">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="514cb-128">Deployment</span></span>

1. <span data-ttu-id="514cb-129">Scarica il modello da [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span><span class="sxs-lookup"><span data-stu-id="514cb-129">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="514cb-130">Accedi a [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="514cb-130">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="514cb-131">Crea un [gruppo di risorse](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="514cb-131">Create a [resource group](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="514cb-132">Crea un [account di archiviazione](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal) nel gruppo di risorse che hai creato.</span><span class="sxs-lookup"><span data-stu-id="514cb-132">Create a [storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="514cb-133">Crea un [data factory](https://docs.microsoft.com/azure/data-factory/quickstart-create-data-factory-portal) nel gruppo di risorse sopra che hai creato.</span><span class="sxs-lookup"><span data-stu-id="514cb-133">Create a [data factory](https://docs.microsoft.com/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="514cb-134">Apri il data factory e seleziona il riquadro **Creare e monitorare**.</span><span class="sxs-lookup"><span data-stu-id="514cb-134">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="514cb-135">Nella scheda **Gestisci**, seleziona **Modello ARM**.</span><span class="sxs-lookup"><span data-stu-id="514cb-135">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="514cb-136">Seleziona **Importa modello ARM** per importare il modello **Parte**.</span><span class="sxs-lookup"><span data-stu-id="514cb-136">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="514cb-137">Importa il modello nel data factory.</span><span class="sxs-lookup"><span data-stu-id="514cb-137">Import the template into the data factory.</span></span> <span data-ttu-id="514cb-138">Immettere i seguenti valori per **Dettagli del progetto** e **Dettagli dell'istanza**.</span><span class="sxs-lookup"><span data-stu-id="514cb-138">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="514cb-139">Campo</span><span class="sxs-lookup"><span data-stu-id="514cb-139">Field</span></span> | <span data-ttu-id="514cb-140">Valore</span><span class="sxs-lookup"><span data-stu-id="514cb-140">Value</span></span>
    ---|---
    <span data-ttu-id="514cb-141">Abbonamento</span><span class="sxs-lookup"><span data-stu-id="514cb-141">Subscription</span></span> | <span data-ttu-id="514cb-142">Sottoscrizione di Azure</span><span class="sxs-lookup"><span data-stu-id="514cb-142">Azure subscription</span></span>
    <span data-ttu-id="514cb-143">Gruppo di risorse</span><span class="sxs-lookup"><span data-stu-id="514cb-143">Resource group</span></span> | <span data-ttu-id="514cb-144">Fornire la stessa risorsa in cui viene creato l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="514cb-144">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="514cb-145">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="514cb-145">Region</span></span> | <span data-ttu-id="514cb-146">Specifica l'area geografica.</span><span class="sxs-lookup"><span data-stu-id="514cb-146">Specify region.</span></span>
    <span data-ttu-id="514cb-147">Nome factory</span><span class="sxs-lookup"><span data-stu-id="514cb-147">Factory Name</span></span> | <span data-ttu-id="514cb-148">Specifica il nome della factory.</span><span class="sxs-lookup"><span data-stu-id="514cb-148">Specify factory name.</span></span>
    <span data-ttu-id="514cb-149">FO Linked Service_service Principal Key</span><span class="sxs-lookup"><span data-stu-id="514cb-149">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="514cb-150">Specifica la chiave dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="514cb-150">Specify the application's key.</span></span>
    <span data-ttu-id="514cb-151">Azure Blob Storage_connection String</span><span class="sxs-lookup"><span data-stu-id="514cb-151">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="514cb-152">Stringa di connessione di Archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="514cb-152">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="514cb-153">Dynamics Crm Linked Service_password</span><span class="sxs-lookup"><span data-stu-id="514cb-153">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="514cb-154">La password per l'account utente specificato come nome utente.</span><span class="sxs-lookup"><span data-stu-id="514cb-154">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="514cb-155">FO Linked Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="514cb-155">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="514cb-156">FO Linked Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="514cb-156">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="514cb-157">Specifica le informazioni sul tenant (nome di dominio o ID tenant) in cui risiede l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="514cb-157">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="514cb-158">FO Linked Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="514cb-158">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="514cb-159">FO Linked Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="514cb-159">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="514cb-160">Specifica l'ID client dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="514cb-160">Specify the application's client ID.</span></span>
    <span data-ttu-id="514cb-161">Dynamics Crm Linked Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="514cb-161">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="514cb-162">Il nome utente per la connessione a Dynamics.</span><span class="sxs-lookup"><span data-stu-id="514cb-162">The username to connect to Dynamics.</span></span>

    <span data-ttu-id="514cb-163">Per ulteriori informazioni, vedi [Promuovere manualmente un modello di Resource Manager per ogni ambiente](https://docs.microsoft.com/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Proprietà del servizio collegato](https://docs.microsoft.com/azure/data-factory/connector-dynamics-ax#linked-service-properties) e [Copiare dati usando Azure Data Factory](https://docs.microsoft.com/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span><span class="sxs-lookup"><span data-stu-id="514cb-163">For more information, see [Manually promote a Resource Manager template for each environment](https://docs.microsoft.com/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Linked service properties](https://docs.microsoft.com/azure/data-factory/connector-dynamics-ax#linked-service-properties), and [Copy data using Azure Data Factory](https://docs.microsoft.com/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span></span>

10. <span data-ttu-id="514cb-164">Dopo la distribuzione, convalidare i set di dati, il flusso di dati e il servizio collegato del data factory.</span><span class="sxs-lookup"><span data-stu-id="514cb-164">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Set di dati, flusso di dati e servizio collegato](media/data-factory-validate.png)

11. <span data-ttu-id="514cb-166">Vai a **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="514cb-166">Navigate to **Manage**.</span></span> <span data-ttu-id="514cb-167">Sotto **Connessioni**, seleziona **Servizio collegato**.</span><span class="sxs-lookup"><span data-stu-id="514cb-167">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="514cb-168">Seleziona **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="514cb-168">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="514cb-169">Nel modulo **Modifica servizio collegato (Dynamics CRM)**, inserisci i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="514cb-169">In the **Edit linked service (Dynamics CRM)** form, enter the following values:</span></span>

    <span data-ttu-id="514cb-170">Campo</span><span class="sxs-lookup"><span data-stu-id="514cb-170">Field</span></span> | <span data-ttu-id="514cb-171">Valore</span><span class="sxs-lookup"><span data-stu-id="514cb-171">Value</span></span>
    ---|---
    <span data-ttu-id="514cb-172">Nome</span><span class="sxs-lookup"><span data-stu-id="514cb-172">Name</span></span> | <span data-ttu-id="514cb-173">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="514cb-173">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="514cb-174">descrizione</span><span class="sxs-lookup"><span data-stu-id="514cb-174">Description</span></span> | <span data-ttu-id="514cb-175">I servizi collegati per connettersi con l'istanza CRM per recuperare i dati delle entità</span><span class="sxs-lookup"><span data-stu-id="514cb-175">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="514cb-176">Connetti via runtime di integrazione</span><span class="sxs-lookup"><span data-stu-id="514cb-176">Connect via integration runtime</span></span> | <span data-ttu-id="514cb-177">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="514cb-177">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="514cb-178">Tipo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="514cb-178">Deployment type</span></span> | <span data-ttu-id="514cb-179">In linea</span><span class="sxs-lookup"><span data-stu-id="514cb-179">Online</span></span>
    <span data-ttu-id="514cb-180">Uri servizio</span><span class="sxs-lookup"><span data-stu-id="514cb-180">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="514cb-181">Tipo di autenticazione</span><span class="sxs-lookup"><span data-stu-id="514cb-181">Authentication type</span></span> | <span data-ttu-id="514cb-182">Office365</span><span class="sxs-lookup"><span data-stu-id="514cb-182">Office365</span></span>
    <span data-ttu-id="514cb-183">Nome utente</span><span class="sxs-lookup"><span data-stu-id="514cb-183">User name</span></span> |
    <span data-ttu-id="514cb-184">Password o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="514cb-184">Password or Azure Key Vault</span></span> | <span data-ttu-id="514cb-185">Password</span><span class="sxs-lookup"><span data-stu-id="514cb-185">Password</span></span>
    <span data-ttu-id="514cb-186">Password</span><span class="sxs-lookup"><span data-stu-id="514cb-186">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="514cb-187">Eseguire il modello</span><span class="sxs-lookup"><span data-stu-id="514cb-187">Run the template</span></span>

1. <span data-ttu-id="514cb-188">Interrompi la doppia scrittura seguente di **Account**, **Contatto** e **Fornitore** utilizzando l'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="514cb-188">Stop the following **Account**, **Contact**, and **Vendor** dual-write using the Finance and Operations app.</span></span>

    + <span data-ttu-id="514cb-189">Clienti V3 (conti)</span><span class="sxs-lookup"><span data-stu-id="514cb-189">Customers V3(accounts)</span></span>
    + <span data-ttu-id="514cb-190">Clienti V3(contacts)</span><span class="sxs-lookup"><span data-stu-id="514cb-190">Customers V3(contacts)</span></span>
    + <span data-ttu-id="514cb-191">Contatti CDS V2(contacts)</span><span class="sxs-lookup"><span data-stu-id="514cb-191">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="514cb-192">Contatti CDS V2(contacts)</span><span class="sxs-lookup"><span data-stu-id="514cb-192">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="514cb-193">Fornitore V2 (msdyn_vendor)</span><span class="sxs-lookup"><span data-stu-id="514cb-193">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="514cb-194">Assicurati che le mappe vengano rimosse dalla tabella `msdy_dualwriteruntimeconfig` in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="514cb-194">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="514cb-195">Installa le [soluzioni di doppia scrittura per parte e rubrica globale](https://aka.ms/dual-write-gab) da AppSource.</span><span class="sxs-lookup"><span data-stu-id="514cb-195">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="514cb-196">Nell'app Finance and Operations, se le seguenti tabelle contengono dati, allora esegui **Sincronizzazione iniziale** per le stesse.</span><span class="sxs-lookup"><span data-stu-id="514cb-196">In the Finance and Operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="514cb-197">Formule di apertura</span><span class="sxs-lookup"><span data-stu-id="514cb-197">Salutations</span></span>
    + <span data-ttu-id="514cb-198">Tipi di carattere personale</span><span class="sxs-lookup"><span data-stu-id="514cb-198">Personal character types</span></span>
    + <span data-ttu-id="514cb-199">Formula di chiusura</span><span class="sxs-lookup"><span data-stu-id="514cb-199">Complimentary closing</span></span>
    + <span data-ttu-id="514cb-200">Titoli contatti</span><span class="sxs-lookup"><span data-stu-id="514cb-200">Contact person titles</span></span>
    + <span data-ttu-id="514cb-201">Ruoli nel processo decisionale</span><span class="sxs-lookup"><span data-stu-id="514cb-201">Decision making roles</span></span>
    + <span data-ttu-id="514cb-202">Livelli fedeltà</span><span class="sxs-lookup"><span data-stu-id="514cb-202">Loyalty levels</span></span>

5. <span data-ttu-id="514cb-203">Nell'app di interazione con i clienti, disabilita i seguenti passaggi del plug-in.</span><span class="sxs-lookup"><span data-stu-id="514cb-203">In the customer engagement app, disable the following plugin steps.</span></span>

    + <span data-ttu-id="514cb-204">Aggiornamento dell'account</span><span class="sxs-lookup"><span data-stu-id="514cb-204">Account Update</span></span>
         + <span data-ttu-id="514cb-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aggiornamento dell'account</span><span class="sxs-lookup"><span data-stu-id="514cb-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="514cb-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aggiornamento dell'account</span><span class="sxs-lookup"><span data-stu-id="514cb-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="514cb-207">Aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="514cb-207">Contact Update</span></span>
         + <span data-ttu-id="514cb-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="514cb-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="514cb-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="514cb-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="514cb-210">Aggiornamento di msdyn_party</span><span class="sxs-lookup"><span data-stu-id="514cb-210">msdyn_party Update</span></span>
         + <span data-ttu-id="514cb-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aggiornamento di msdyn_party</span><span class="sxs-lookup"><span data-stu-id="514cb-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="514cb-212">Aggiornamento di msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="514cb-212">msdyn_vendor Update</span></span>
         + <span data-ttu-id="514cb-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aggiornamento di msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="514cb-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="514cb-214">Nell'app di interazione con i clienti, disabilita i seguenti flussi di lavoro:</span><span class="sxs-lookup"><span data-stu-id="514cb-214">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="514cb-215">Creare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="514cb-215">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="514cb-216">Creare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="514cb-216">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="514cb-217">Creare fornitori di tipo Persona nella tabella Contatti</span><span class="sxs-lookup"><span data-stu-id="514cb-217">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="514cb-218">Creare fornitori di tipo Persona nella tabella fornitori</span><span class="sxs-lookup"><span data-stu-id="514cb-218">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="514cb-219">Aggiornare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="514cb-219">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="514cb-220">Aggiornare fornitori nella tabella Fornitori</span><span class="sxs-lookup"><span data-stu-id="514cb-220">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="514cb-221">Aggiornare fornitori di tipo Persona nella tabella Contatti</span><span class="sxs-lookup"><span data-stu-id="514cb-221">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="514cb-222">Aggiornare fornitori di tipo Persona nella tabella fornitori</span><span class="sxs-lookup"><span data-stu-id="514cb-222">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="514cb-223">Nel data factory, esegui il modello selezionando **Attiva ora** come mostrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="514cb-223">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="514cb-224">Il completamento di questo processo potrebbe richiedere alcune ore in base al volume di dati.</span><span class="sxs-lookup"><span data-stu-id="514cb-224">This process might take a few hours to complete based on the data volume.</span></span>

    ![Attiva ora](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="514cb-226">Se hai personalizzazioni per **Account**, **Contatto** e **Fornitore** devi modificare il modello.</span><span class="sxs-lookup"><span data-stu-id="514cb-226">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template.</span></span>

8. <span data-ttu-id="514cb-227">Importa i nuovi record **Parte** nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="514cb-227">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="514cb-228">Scarica il file `FONewParty.csv` da archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="514cb-228">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="514cb-229">Il percorso è `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="514cb-229">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="514cb-230">Converti il file `FONewParty.csv` in un file Excel e importa il file Excel nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="514cb-230">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the Finance and Operations app.</span></span>  <span data-ttu-id="514cb-231">Se l'importazione del file CSV funziona, puoi importare direttamente il file CSV.</span><span class="sxs-lookup"><span data-stu-id="514cb-231">If the csv import works for you, you can import csv file directly.</span></span> <span data-ttu-id="514cb-232">L'esecuzione dell'importazione potrebbe richiedere alcune ore, a seconda del volume di dati.</span><span class="sxs-lookup"><span data-stu-id="514cb-232">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="514cb-233">Per ulteriori informazioni, vedere [Panoramica dei processi di importazione ed esportazione dei dati](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job).</span><span class="sxs-lookup"><span data-stu-id="514cb-233">For more information, see [Data import and export jobs overview](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job).</span></span>

    ![Importare i record Parte di Datavers](media/data-factory-import-party.png)

9. <span data-ttu-id="514cb-235">Nell'app di interazione con i clienti, abilita i seguenti passaggi del plug-in:</span><span class="sxs-lookup"><span data-stu-id="514cb-235">In the customer engagement apps, enable the following plugin steps:</span></span>

    + <span data-ttu-id="514cb-236">Aggiornamento dell'account</span><span class="sxs-lookup"><span data-stu-id="514cb-236">Account Update</span></span>
         + <span data-ttu-id="514cb-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aggiornamento dell'account</span><span class="sxs-lookup"><span data-stu-id="514cb-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="514cb-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aggiornamento dell'account</span><span class="sxs-lookup"><span data-stu-id="514cb-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="514cb-239">Aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="514cb-239">Contact Update</span></span>
         + <span data-ttu-id="514cb-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="514cb-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="514cb-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aggiornamento del contatto</span><span class="sxs-lookup"><span data-stu-id="514cb-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="514cb-242">Aggiornamento di msdyn_party</span><span class="sxs-lookup"><span data-stu-id="514cb-242">msdyn_party Update</span></span>
         + <span data-ttu-id="514cb-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aggiornamento di msdyn_party</span><span class="sxs-lookup"><span data-stu-id="514cb-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="514cb-244">Aggiornamento di msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="514cb-244">msdyn_vendor Update</span></span>
         + <span data-ttu-id="514cb-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aggiornamento di msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="514cb-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="514cb-246">Nelle app di interazione con i clienti, attiva i seguenti flussi di lavoro se li hai disattivati nei passaggi precedenti:</span><span class="sxs-lookup"><span data-stu-id="514cb-246">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="514cb-247">Creare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="514cb-247">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="514cb-248">Creare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="514cb-248">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="514cb-249">Creare fornitori di tipo Persona nella tabella Contatti</span><span class="sxs-lookup"><span data-stu-id="514cb-249">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="514cb-250">Creare fornitori di tipo Persona nella tabella fornitori</span><span class="sxs-lookup"><span data-stu-id="514cb-250">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="514cb-251">Aggiornare fornitori nella tabella Conto</span><span class="sxs-lookup"><span data-stu-id="514cb-251">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="514cb-252">Aggiornare fornitori nella tabella Fornitori</span><span class="sxs-lookup"><span data-stu-id="514cb-252">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="514cb-253">Aggiornare fornitori di tipo Persona nella tabella Contatti</span><span class="sxs-lookup"><span data-stu-id="514cb-253">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="514cb-254">Aggiornare fornitori di tipo Persona nella tabella fornitori</span><span class="sxs-lookup"><span data-stu-id="514cb-254">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="514cb-255">Esegui le mappe correlate a **Parte** come indicato in [Parte e rubrica globale](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="514cb-255">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="514cb-256">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="514cb-256">Troubleshooting</span></span>

1. <span data-ttu-id="514cb-257">Se il processo non riesce, esegui nuovamente il data factory a partire dall'attività non riuscita.</span><span class="sxs-lookup"><span data-stu-id="514cb-257">In the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="514cb-258">Alcuni file vengono generati dal data factory utilizzabile per la convalida dei dati.</span><span class="sxs-lookup"><span data-stu-id="514cb-258">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="514cb-259">Il data factory viene eseguito in base ai file CSV delimitati da virgole.</span><span class="sxs-lookup"><span data-stu-id="514cb-259">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="514cb-260">Se è presente un valore di campo con una virgola, potrebbe interferire con i risultati.</span><span class="sxs-lookup"><span data-stu-id="514cb-260">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="514cb-261">Devi rimuovere le virgole.</span><span class="sxs-lookup"><span data-stu-id="514cb-261">You need to remove the commas.</span></span>
4. <span data-ttu-id="514cb-262">La scheda **Monitoraggio** fornisce informazioni su tutti i passaggi e i dati elaborati.</span><span class="sxs-lookup"><span data-stu-id="514cb-262">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="514cb-263">Seleziona un passaggio specifico per eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="514cb-263">Select a specific step to debug it.</span></span>

    ![Scheda Monitoraggio](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="514cb-265">Ulteriori informazioni sul modello</span><span class="sxs-lookup"><span data-stu-id="514cb-265">Learn more about the template</span></span>

<span data-ttu-id="514cb-266">Puoi trovare commenti relativi al modello nel file [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="514cb-266">You can find comments for the template the [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md) file.</span></span>
