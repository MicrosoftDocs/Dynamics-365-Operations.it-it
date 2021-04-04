---
title: Componenti di amministrazione del componente aggiuntivo per la fatturazione elettronica
description: In questo argomento vengono fornite informazioni sui componenti correlati all'amministrazione del componente aggiuntivo Fatturazione elettronica.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 70ef47dd45200a14c9d780f3c280c554d0e52ac3
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592576"
---
# <a name="electronic-invoicing-add-on-administration-components"></a><span data-ttu-id="13b57-103">Componenti di amministrazione del componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="13b57-103">Electronic invoicing add-on administration components</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="13b57-104">In questo argomento vengono fornite informazioni sui componenti correlati all'amministrazione del componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-104">This topic provides information about the components that are related to administration of the Electronic invoicing add-on.</span></span> <span data-ttu-id="13b57-105">Fornisce inoltre informazioni su come configurare il servizio componente aggiuntivo per la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-105">It also provides information about how to configure the Electronic invoicing add-on service.</span></span>

## <a name="azure"></a><span data-ttu-id="13b57-106">Azure</span><span class="sxs-lookup"><span data-stu-id="13b57-106">Azure</span></span>

<span data-ttu-id="13b57-107">Usa Microsoft Azure per creare i segreti per l'insieme di credenziali delle chiavi e l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="13b57-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="13b57-108">Quindi utilizza i segreti nella configurazione del componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-108">Then use the secrets in the configuration of the Electronic invoicing add-on.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="13b57-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="13b57-109">Lifecycle Services</span></span>

<span data-ttu-id="13b57-110">Usa Microsoft Dynamics Lifecycle Services (LCS) per abilitare il componente aggiuntivo per i microservizi per il progetto di distribuzione LCS.</span><span class="sxs-lookup"><span data-stu-id="13b57-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the add-on for the microservices for your LCS deployment project.</span></span>

> [!NOTE]
> <span data-ttu-id="13b57-111">L'installazione del componente aggiuntivo per microservizi in LCS richiede almeno una macchina virtuale di livello 2.</span><span class="sxs-lookup"><span data-stu-id="13b57-111">The installation of the microservice add-on in LCS requires at least a Tier 2 virtual machine.</span></span> <span data-ttu-id="13b57-112">Per ulteriori informazioni sulla pianificazione dell'ambiente, vedere [Pianificazione ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="13b57-112">For more information about environment planning, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
 

## <a name="regulatory-configuration-services"></a><span data-ttu-id="13b57-113">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="13b57-113">Regulatory Configuration Services</span></span>

<span data-ttu-id="13b57-114">Dynamics 365 Regulatory Configuration Services (RCS) è l'interfaccia utilizzata per configurare il componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-114">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure the Electronic invoicing add-on.</span></span> <span data-ttu-id="13b57-115">Le risorse quali ambienti e funzionalità di fatturazione elettronica vengono create, gestite e ospitate in RCS.</span><span class="sxs-lookup"><span data-stu-id="13b57-115">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="13b57-116">Quando le risorse sono pronte, vengono pubblicate nel servizio componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-116">When the resources are ready, they are published to the Electronic invoicing add-on service.</span></span>

<span data-ttu-id="13b57-117">Per l'iscrizione a RCS, vedere [Regulatory services](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="13b57-117">For RCS sign-up, see [Regulatory services](https://marketing.configure.global.dynamics.com/).</span></span>

<span data-ttu-id="13b57-118">Per altre informazioni su RCS, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="13b57-118">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="13b57-119">Integrazione con il componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="13b57-119">Integration with the Electronic invoicing add-on</span></span>

<span data-ttu-id="13b57-120">Prima di poter utilizzare RCS per configurare le fatture elettroniche, è necessario configurare RCS per consentire la comunicazione con il componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-120">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with the Electronic invoicing add-on.</span></span> <span data-ttu-id="13b57-121">Completa questa configurazione nella scheda **Componente aggiuntivo per la fatturazione elettronica** della pagina **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="13b57-121">You complete this configuration on the **Electronic invoicing add-on** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="13b57-122">Endpoint servizio</span><span class="sxs-lookup"><span data-stu-id="13b57-122">Service endpoint</span></span>

<span data-ttu-id="13b57-123">Il componente aggiuntivo per la fatturazione elettronica è disponibile in varie aree geografiche del data center di Azure:</span><span class="sxs-lookup"><span data-stu-id="13b57-123">The Electronic invoicing add-on is available in several Azure datacenter geographies.</span></span> <span data-ttu-id="13b57-124">La tabella seguente elenca la disponibilità per regione.</span><span class="sxs-lookup"><span data-stu-id="13b57-124">The following table lists the availability per region.</span></span>

| <span data-ttu-id="13b57-125">Area geografica del data center di Azure</span><span class="sxs-lookup"><span data-stu-id="13b57-125">Azure datacenter geography</span></span> |
|----------------------------|
| <span data-ttu-id="13b57-126">Stati Uniti orientali</span><span class="sxs-lookup"><span data-stu-id="13b57-126">East US</span></span>                    |
| <span data-ttu-id="13b57-127">Stati Uniti occidentali</span><span class="sxs-lookup"><span data-stu-id="13b57-127">West US</span></span>                    |
| <span data-ttu-id="13b57-128">UE settentrionale</span><span class="sxs-lookup"><span data-stu-id="13b57-128">North EU</span></span>                   |
| <span data-ttu-id="13b57-129">UE occidentale</span><span class="sxs-lookup"><span data-stu-id="13b57-129">West EU</span></span>                    |

### <a name="service-environments"></a><span data-ttu-id="13b57-130">Ambienti di servizio</span><span class="sxs-lookup"><span data-stu-id="13b57-130">Service environments</span></span>

<span data-ttu-id="13b57-131">Gli ambienti del servizio sono partizioni logiche create per supportare l'esecuzione delle funzionalità di fatturazione elettronica nel componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-131">Service environments are logical partitions that are created to support execution of the electronic invoicing features in the Electronic invoicing add-on.</span></span> <span data-ttu-id="13b57-132">I segreti di sicurezza, i certificati digitali e la governance (ovvero le autorizzazioni di accesso) devono essere configurati a livello di ambiente del servizio.</span><span class="sxs-lookup"><span data-stu-id="13b57-132">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="13b57-133">I clienti possono creare tutti gli ambienti del servizio che desiderano.</span><span class="sxs-lookup"><span data-stu-id="13b57-133">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="13b57-134">Tutti gli ambienti del servizio creati da un cliente sono indipendenti l'uno dall'altro.</span><span class="sxs-lookup"><span data-stu-id="13b57-134">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="13b57-135">Gli ambienti del servizio devono essere creati e gestiti in RCS.</span><span class="sxs-lookup"><span data-stu-id="13b57-135">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="13b57-136">Quando gli ambienti del servizio sono pronti, devono essere pubblicati nel componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-136">When the service environments are ready, they must be published to the Electronic invoicing add-on.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="13b57-137">Stato dell'ambiente del servizio</span><span class="sxs-lookup"><span data-stu-id="13b57-137">Service environment status</span></span>

<span data-ttu-id="13b57-138">Gli ambienti del servizio possono essere gestiti tramite lo stato.</span><span class="sxs-lookup"><span data-stu-id="13b57-138">Service environments can be managed through status.</span></span> <span data-ttu-id="13b57-139">Le possibili opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="13b57-139">The possible options are:</span></span>

- <span data-ttu-id="13b57-140">**Non pubblicato** - L'ambiente è stato creato, ma non è stato ancora pubblicato.</span><span class="sxs-lookup"><span data-stu-id="13b57-140">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="13b57-141">**Pubblicato** - L'ambiente è stato pubblicato nel componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-141">**Published** – The environment has been published to the Electronic invoicing add-on.</span></span>
- <span data-ttu-id="13b57-142">**Modificato** - Gli attributi di un ambiente pubblicato sono stati modificati, ma le modifiche non sono state ancora pubblicate.</span><span class="sxs-lookup"><span data-stu-id="13b57-142">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="13b57-143">Segreti del cliente</span><span class="sxs-lookup"><span data-stu-id="13b57-143">Customer secrets</span></span>

<span data-ttu-id="13b57-144">Il servizio del componente aggiuntivo per la fatturazione elettronica è responsabile dell'archiviazione di tutti i dati aziendali nelle risorse di Azure di proprietà della tua azienda.</span><span class="sxs-lookup"><span data-stu-id="13b57-144">The Electronic invoicing add-on service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="13b57-145">Per garantire che il servizio funzioni correttamente e che tutti i dati aziendali richiesti e generati dal componente aggiuntivo per la fatturazione elettronica siano accessibili solo dal componente aggiuntivo, è necessario creare due risorse principali di Azure:</span><span class="sxs-lookup"><span data-stu-id="13b57-145">To ensure that the service works correctly, and that all the business data that is required for and generated by the Electronic invoicing add-on is accessed only by the add-on, you must create two main Azure resources:</span></span>

- <span data-ttu-id="13b57-146">Un account di Archiviazione di Azure (Archiviazione BLOB) che archivia le fatture elettroniche</span><span class="sxs-lookup"><span data-stu-id="13b57-146">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="13b57-147">Un Azure Key Vault che archivia i certificati e l'URI (Uniform Resource Identifier) dell'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="13b57-147">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="13b57-148">Un insieme di credenziali delle chiavi dedicato e un account di archiviazione del cliente devono essere allocati specificamente per l'utilizzo con il componente aggiuntivo per la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-148">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing add-on.</span></span>

<span data-ttu-id="13b57-149">Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="13b57-149">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="13b57-150">Utenti</span><span class="sxs-lookup"><span data-stu-id="13b57-150">Users</span></span>

<span data-ttu-id="13b57-151">Ogni ambiente del servizio deve elencare gli utenti che possono connettersi da Dynamics 365 Finance e Dynamics 365 Supply Chain Management nel componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-151">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in the Electronic invoicing add-on.</span></span>

#### <a name="publication"></a><span data-ttu-id="13b57-152">Pubblicazione</span><span class="sxs-lookup"><span data-stu-id="13b57-152">Publication</span></span>

<span data-ttu-id="13b57-153">Gli ambienti del servizio devono essere pubblicati nel componente aggiuntivo Fatturazione elettronica prima di poter essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="13b57-153">Service environments must be published to the Electronic invoicing add-on before they can be used.</span></span> <span data-ttu-id="13b57-154">Solo gli ambienti pubblicati sono accessibili da Finance e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="13b57-154">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="13b57-155">Inoltre, un ambiente del servizio deve essere pubblicato prima che qualsiasi aggiornamento degli attributi abbia effetto sul servizio di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-155">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="13b57-156">Applicazioni connesse</span><span class="sxs-lookup"><span data-stu-id="13b57-156">Connected applications</span></span>

<span data-ttu-id="13b57-157">Le applicazioni connesse sono le istanze di Finance e Supply Chain Management che potresti voler raggiungere tramite RCS.</span><span class="sxs-lookup"><span data-stu-id="13b57-157">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="13b57-158">Oltre all'URL dell'applicazione e al suo tenant, un'applicazione connessa contiene le credenziali che consentono a RCS di connettersi all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="13b57-158">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="13b57-159">Tramite le applicazioni connesse, puoi configurare parte della funzione di fatturazione elettronica in Finance e Supply Chain Management per far funzionare l'intera funzione di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-159">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="13b57-160">Finance e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="13b57-160">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing-add-on"></a><span data-ttu-id="13b57-161">Integrazione con il componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="13b57-161">Integration with Electronic invoicing add-on</span></span>

<span data-ttu-id="13b57-162">Prima di poter utilizzare Finance e Supply Chain Management per emettere fatture elettroniche tramite il componente aggiuntivo Fatturazione elettronica, è necessario configurare il componente aggiuntivo per consentire la comunicazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="13b57-162">Before you can use Finance and Supply Chain Management to issue electronic invoices through the Electronic invoicing add-on, the add-on must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="13b57-163">Funzionalità di integrazione del componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="13b57-163">Electronic invoicing add-on integration feature</span></span>

<span data-ttu-id="13b57-164">Per abilitare la comunicazione tra Finance e Supply Chain Management e il componente aggiuntivo Fatturazione elettronica, è necessario attivare la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica** nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="13b57-164">To enable communication between Finance and Supply Chain Management and the Electronic invoicing add-on, you must turn on the **Electronic Invoicing add-on integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="13b57-165">Endpoint servizio</span><span class="sxs-lookup"><span data-stu-id="13b57-165">Service endpoint</span></span>

<span data-ttu-id="13b57-166">L'endpoint del servizio è l'URL in cui si trova il componente aggiuntivo per la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-166">The service endpoint is the URL where the Electronic invoicing add-on is located.</span></span> <span data-ttu-id="13b57-167">Prima di poter emettere fatture elettroniche, l'endpoint del servizio deve essere configurato in Finance e Supply Chain Management per consentire la comunicazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="13b57-167">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="13b57-168">Per configurare l'endpoint del servizio, vai a **Amministrazione organizzazione \> Impostazione \> Parametro documento elettronico** e quindi nella scheda **Servizi di invio**, nel campo **URL componente aggiuntivo per la fatturazione elettronica**, immetti l'URL come descritto nella tabella della sezione **Endpoint del servizio**.</span><span class="sxs-lookup"><span data-stu-id="13b57-168">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing add-on URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="13b57-169">Ambienti</span><span class="sxs-lookup"><span data-stu-id="13b57-169">Environments</span></span>

<span data-ttu-id="13b57-170">Il nome dell'ambiente immesso in Finance e Supply Chain Management fa riferimento al nome dell'ambiente creato in RCS e pubblicato nel componente aggiuntivo Fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="13b57-170">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to the Electronic invoicing add-on.</span></span>

<span data-ttu-id="13b57-171">L'ambiente deve essere configurato nella scheda **Servizi di invio** della pagina **Parametro documento elettronico** in modo che ogni richiesta di emissione di fatture elettroniche contenga l'ambiente in cui il componente aggiuntivo Fatturazione elettronica può determinare quale funzione di fatturazione elettronica deve elaborare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="13b57-171">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where the Electronic invoicing add-on can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="13b57-172">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="13b57-172">Additional resources</span></span>

- [<span data-ttu-id="13b57-173">Configurare le fattura elettroniche in RCS</span><span class="sxs-lookup"><span data-stu-id="13b57-173">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="13b57-174">Emissione di fatture elettroniche in Finance e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="13b57-174">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
