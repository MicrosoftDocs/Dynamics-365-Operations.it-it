---
title: Componenti di amministrazione della fatturazione elettronica
description: In questo argomento vengono fornite informazioni sui componenti correlati all'amministrazione della Fatturazione elettronica.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 2e859875e124796e49000cd5ea94cfb75ecd768a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840030"
---
# <a name="electronic-invoicing-administration-components"></a><span data-ttu-id="34623-103">Componenti di amministrazione della fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="34623-103">Electronic invoicing administration components</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="34623-104">In questo argomento vengono fornite informazioni sui componenti correlati all'amministrazione della Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-104">This topic provides information about the components that are related to administration of Electronic invoicing.</span></span> <span data-ttu-id="34623-105">Fornisce inoltre informazioni su come configurare il servizio per la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-105">It also provides information about how to configure the Electronic invoicing service.</span></span>

## <a name="azure"></a><span data-ttu-id="34623-106">Azure</span><span class="sxs-lookup"><span data-stu-id="34623-106">Azure</span></span>

<span data-ttu-id="34623-107">Usa Microsoft Azure per creare i segreti per l'insieme di credenziali delle chiavi e l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="34623-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="34623-108">Quindi utilizza i segreti nella configurazione della Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-108">Then use the secrets in the configuration of Electronic invoicing.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="34623-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="34623-109">Lifecycle Services</span></span>

<span data-ttu-id="34623-110">Usa Microsoft Dynamics Lifecycle Services (LCS) per abilitare i microservizi per il progetto di distribuzione LCS.</span><span class="sxs-lookup"><span data-stu-id="34623-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the microservices for your LCS deployment project.</span></span>

> [!NOTE]
> <span data-ttu-id="34623-111">L'installazione dei microservizi in LCS richiede almeno una macchina virtuale di livello 2.</span><span class="sxs-lookup"><span data-stu-id="34623-111">The installation of the microservice in LCS requires at least a Tier 2 virtual machine.</span></span> <span data-ttu-id="34623-112">Per ulteriori informazioni sulla pianificazione dell'ambiente, vedere [Pianificazione ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="34623-112">For more information about environment planning, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
 

## <a name="regulatory-configuration-services"></a><span data-ttu-id="34623-113">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="34623-113">Regulatory Configuration Services</span></span>

<span data-ttu-id="34623-114">Dynamics 365 Regulatory Configuration Services (RCS) è l'interfaccia utilizzata per configurare la Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-114">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure Electronic invoicing.</span></span> <span data-ttu-id="34623-115">Le risorse quali ambienti e funzionalità di fatturazione elettronica vengono create, gestite e ospitate in RCS.</span><span class="sxs-lookup"><span data-stu-id="34623-115">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="34623-116">Quando le risorse sono pronte, vengono pubblicate nel servizio Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-116">When the resources are ready, they are published to Electronic invoicing service.</span></span>

<span data-ttu-id="34623-117">Per l'iscrizione a RCS, vedere [Regulatory services](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="34623-117">For RCS sign-up, see [Regulatory services](https://marketing.configure.global.dynamics.com/).</span></span>

<span data-ttu-id="34623-118">Per altre informazioni su RCS, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="34623-118">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="34623-119">Integrazione con la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="34623-119">Integration with Electronic invoicing</span></span> 

<span data-ttu-id="34623-120">Prima di poter utilizzare RCS per configurare le fatture elettroniche, è necessario configurare RCS per consentire la comunicazione con la Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-120">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with Electronic invoicing.</span></span> <span data-ttu-id="34623-121">Completa questa configurazione nella scheda **Fatturazione elettronica** della pagina **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="34623-121">You complete this configuration on the **Electronic invoicing** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="34623-122">Endpoint servizio</span><span class="sxs-lookup"><span data-stu-id="34623-122">Service endpoint</span></span>

<span data-ttu-id="34623-123">La fatturazione elettronica è disponibile in varie aree geografiche del data center di Azure:</span><span class="sxs-lookup"><span data-stu-id="34623-123">Electronic invoicing is available in several Azure datacenter geographies.</span></span> <span data-ttu-id="34623-124">La tabella seguente elenca la disponibilità per regione.</span><span class="sxs-lookup"><span data-stu-id="34623-124">The following table lists the availability per region.</span></span>

| <span data-ttu-id="34623-125">Area geografica del data center di Azure</span><span class="sxs-lookup"><span data-stu-id="34623-125">Azure datacenter geography</span></span> |
|----------------------------|
| <span data-ttu-id="34623-126">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="34623-126">East US</span></span>                    |
| <span data-ttu-id="34623-127">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="34623-127">West US</span></span>                    |
| <span data-ttu-id="34623-128">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="34623-128">North EU</span></span>                   |
| <span data-ttu-id="34623-129">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="34623-129">West EU</span></span>                    |

### <a name="service-environments"></a><span data-ttu-id="34623-130">Ambienti di servizio</span><span class="sxs-lookup"><span data-stu-id="34623-130">Service environments</span></span>

<span data-ttu-id="34623-131">Gli ambienti del servizio sono partizioni logiche create per supportare l'esecuzione delle funzionalità di fatturazione elettronica nella Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-131">Service environments are logical partitions that are created to support execution of the electronic invoicing features in Electronic invoicing.</span></span> <span data-ttu-id="34623-132">I segreti di sicurezza, i certificati digitali e la governance (ovvero le autorizzazioni di accesso) devono essere configurati a livello di ambiente del servizio.</span><span class="sxs-lookup"><span data-stu-id="34623-132">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="34623-133">I clienti possono creare tutti gli ambienti del servizio che desiderano.</span><span class="sxs-lookup"><span data-stu-id="34623-133">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="34623-134">Tutti gli ambienti del servizio creati da un cliente sono indipendenti l'uno dall'altro.</span><span class="sxs-lookup"><span data-stu-id="34623-134">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="34623-135">Gli ambienti del servizio devono essere creati e gestiti in RCS.</span><span class="sxs-lookup"><span data-stu-id="34623-135">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="34623-136">Quando gli ambienti del servizio sono pronti, devono essere pubblicati nella Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-136">When the service environments are ready, they must be published to Electronic invoicing.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="34623-137">Stato dell'ambiente del servizio</span><span class="sxs-lookup"><span data-stu-id="34623-137">Service environment status</span></span>

<span data-ttu-id="34623-138">Gli ambienti del servizio possono essere gestiti tramite lo stato.</span><span class="sxs-lookup"><span data-stu-id="34623-138">Service environments can be managed through status.</span></span> <span data-ttu-id="34623-139">Le possibili opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="34623-139">The possible options are:</span></span>

- <span data-ttu-id="34623-140">**Non pubblicato** - L'ambiente è stato creato, ma non è stato ancora pubblicato.</span><span class="sxs-lookup"><span data-stu-id="34623-140">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="34623-141">**Pubblicato** - L'ambiente è stato pubblicato nella Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-141">**Published** – The environment has been published to Electronic invoicing .</span></span>
- <span data-ttu-id="34623-142">**Modificato** - Gli attributi di un ambiente pubblicato sono stati modificati, ma le modifiche non sono state ancora pubblicate.</span><span class="sxs-lookup"><span data-stu-id="34623-142">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="34623-143">Segreti del cliente</span><span class="sxs-lookup"><span data-stu-id="34623-143">Customer secrets</span></span>

<span data-ttu-id="34623-144">Il servizio Fatturazione elettronica è responsabile dell'archiviazione di tutti i dati aziendali nelle risorse di Azure di proprietà della tua azienda.</span><span class="sxs-lookup"><span data-stu-id="34623-144">The Electronic invoicing service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="34623-145">Per garantire che il servizio funzioni correttamente e che tutti i dati aziendali necessari e generati dalla fatturazione elettronica siano accessibili, è necessario creare due risorse principali di Azure:</span><span class="sxs-lookup"><span data-stu-id="34623-145">To ensure that the service works correctly, and that all the business data that is required for and generated by Electronic invoicing is accessed appropriately, you must create two main Azure resources:</span></span>

- <span data-ttu-id="34623-146">Un account di Archiviazione di Azure (Archiviazione BLOB) che archivia le fatture elettroniche</span><span class="sxs-lookup"><span data-stu-id="34623-146">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="34623-147">Un Azure Key Vault che archivia i certificati e l'URI (Uniform Resource Identifier) dell'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="34623-147">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="34623-148">Un insieme di credenziali delle chiavi dedicato e un account di archiviazione del cliente devono essere allocati specificamente per l'utilizzo con la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-148">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing .</span></span>

<span data-ttu-id="34623-149">Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="34623-149">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="34623-150">Utenti</span><span class="sxs-lookup"><span data-stu-id="34623-150">Users</span></span>

<span data-ttu-id="34623-151">Ogni ambiente del servizio deve elencare gli utenti che possono connettersi da Dynamics 365 Finance e Dynamics 365 Supply Chain Management nella Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-151">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in Electronic invoicing.</span></span>

#### <a name="publication"></a><span data-ttu-id="34623-152">Pubblicazione</span><span class="sxs-lookup"><span data-stu-id="34623-152">Publication</span></span>

<span data-ttu-id="34623-153">Gli ambienti del servizio devono essere pubblicati nella Fatturazione elettronica prima di poter essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="34623-153">Service environments must be published to Electronic invoicing before they can be used.</span></span> <span data-ttu-id="34623-154">Solo gli ambienti pubblicati sono accessibili da Finance e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="34623-154">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="34623-155">Inoltre, un ambiente del servizio deve essere pubblicato prima che qualsiasi aggiornamento degli attributi abbia effetto sul servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-155">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="34623-156">Applicazioni connesse</span><span class="sxs-lookup"><span data-stu-id="34623-156">Connected applications</span></span>

<span data-ttu-id="34623-157">Le applicazioni connesse sono le istanze di Finance e Supply Chain Management che potresti voler raggiungere tramite RCS.</span><span class="sxs-lookup"><span data-stu-id="34623-157">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="34623-158">Oltre all'URL dell'applicazione e al suo tenant, un'applicazione connessa contiene le credenziali che consentono a RCS di connettersi all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="34623-158">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="34623-159">Tramite le applicazioni connesse, puoi configurare parte della funzione di fatturazione elettronica in Finance e Supply Chain Management per far funzionare l'intera funzione di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-159">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="34623-160">Finance e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="34623-160">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="34623-161">Integrazione con la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="34623-161">Integration with Electronic invoicing</span></span>

<span data-ttu-id="34623-162">Prima di poter utilizzare Finance e Supply Chain Management per emettere fatture elettroniche tramite la Fatturazione elettronica, è necessario configurarla per consentire la comunicazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="34623-162">Before you can use Finance and Supply Chain Management to issue electronic invoices through Electronic invoicing, it must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-integration-feature"></a><span data-ttu-id="34623-163">Funzionalità di integrazione della fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="34623-163">Electronic invoicing integration feature</span></span>

<span data-ttu-id="34623-164">Per abilitare la comunicazione tra Finance e Supply Chain Management e la Fatturazione elettronica, è necessario attivare la funzionalità **Integrazione della fatturazione elettronica** nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="34623-164">To enable communication between Finance and Supply Chain Management and Electronic invoicing, you must turn on the **Electronic Invoicing integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="34623-165">Endpoint servizio</span><span class="sxs-lookup"><span data-stu-id="34623-165">Service endpoint</span></span>

<span data-ttu-id="34623-166">L'endpoint del servizio è l'URL in cui si trova la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-166">The service endpoint is the URL where Electronic invoicing is located.</span></span> <span data-ttu-id="34623-167">Prima di poter emettere fatture elettroniche, l'endpoint del servizio deve essere configurato in Finance e Supply Chain Management per consentire la comunicazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="34623-167">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="34623-168">Per configurare l'endpoint del servizio, vai a **Amministrazione organizzazione \> Impostazione \> Parametro documento elettronico** e quindi nella scheda **Servizi di invio**, nel campo **URL fatturazione elettronica**, immetti l'URL come descritto nella tabella della sezione **Endpoint del servizio**.</span><span class="sxs-lookup"><span data-stu-id="34623-168">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="34623-169">Ambienti</span><span class="sxs-lookup"><span data-stu-id="34623-169">Environments</span></span>

<span data-ttu-id="34623-170">Il nome dell'ambiente immesso in Finance e Supply Chain Management fa riferimento al nome dell'ambiente creato in RCS e pubblicato nella Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="34623-170">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to Electronic invoicing.</span></span>

<span data-ttu-id="34623-171">L'ambiente deve essere configurato nella scheda **Servizi di invio** della pagina **Parametro documento elettronico** in modo che ogni richiesta di emissione di fatture elettroniche contenga l'ambiente in cui la Fatturazione elettronica può determinare quale funzione di fatturazione elettronica deve elaborare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="34623-171">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where Electronic invoicing can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="34623-172">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="34623-172">Additional resources</span></span>

- [<span data-ttu-id="34623-173">Configurare le fattura elettroniche in RCS</span><span class="sxs-lookup"><span data-stu-id="34623-173">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="34623-174">Emissione di fatture elettroniche in Finance e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="34623-174">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
