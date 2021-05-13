---
title: Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)
description: In questo argomento viene descritto come aggiungere una rete per la distribuzione di contenuti (CDN) all'ambiente di Microsoft Dynamics 365 Commerce.
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 59277323e0995f59d3a451395a038fa3708274eb
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936832"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="9e56c-103">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="9e56c-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9e56c-104">In questo argomento viene descritto come aggiungere una rete per la distribuzione di contenuti (CDN) all'ambiente di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9e56c-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="9e56c-105">Quando si configura un ambiente di e-commerce in Dynamics 365 Commerce, è possibile configurarlo per l'utilizzo con il servizio CDN.</span><span class="sxs-lookup"><span data-stu-id="9e56c-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="9e56c-106">Il dominio personalizzato può essere abilitato durante il processo di provisioning per l'ambiente di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="9e56c-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="9e56c-107">In alternativa, è possibile utilizzare una richiesta di assistenza per configurarlo al termine del processo di provisioning.</span><span class="sxs-lookup"><span data-stu-id="9e56c-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="9e56c-108">Il processo di provisioning per l'ambiente di e-commerce genera un nome host associato all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="9e56c-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="9e56c-109">Questo nome host ha il formato seguente, dove \<*e-commerce-tenant-name*\> è il nome dell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="9e56c-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="9e56c-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="9e56c-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="9e56c-111">Il nome host o l'endpoint generato durante il processo di provisioning supporta un certificato SSL (Secure Sockets Layer) solo per \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="9e56c-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="9e56c-112">Non supporta SSL per domini personalizzati.</span><span class="sxs-lookup"><span data-stu-id="9e56c-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="9e56c-113">Di conseguenza, è necessario terminare SSL per i domini personalizzati in CDN e inoltrare il traffico da CDN al nome host o all'endpoint generato da Commerce.</span><span class="sxs-lookup"><span data-stu-id="9e56c-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="9e56c-114">Inoltre, gli *elementi statici* (file JavaScript o \[CSS\] ) di Commerce vengono serviti dall'endpoint generato da Commerce (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="9e56c-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="9e56c-115">Gli elementi statici possono essere memorizzati nella cache solo se il nome host o l'endpoint generato da Commerce sono posizionati dopo CDN.</span><span class="sxs-lookup"><span data-stu-id="9e56c-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="9e56c-116">Impostare SSL</span><span class="sxs-lookup"><span data-stu-id="9e56c-116">Set up SSL</span></span>

<span data-ttu-id="9e56c-117">Dopo il provisioning dell'ambiente di Commerce con il dominio personalizzato fornito o dopo aver fornito il dominio personalizzato per l'ambiente utilizzando una richiesta di assistenza, è necessario collaborare con il team di onboarding di Commerce per pianificare le modifiche al DNS.</span><span class="sxs-lookup"><span data-stu-id="9e56c-117">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, you need to work with the Commerce onboarding team to plan the DNS changes.</span></span>

<span data-ttu-id="9e56c-118">Come indicato in precedenza, il nome host o l'endpoint generato supporta un certificato SSL solo per \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="9e56c-118">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="9e56c-119">Non supporta SSL per domini personalizzati.</span><span class="sxs-lookup"><span data-stu-id="9e56c-119">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="9e56c-120">Servizi CDN</span><span class="sxs-lookup"><span data-stu-id="9e56c-120">CDN services</span></span>

<span data-ttu-id="9e56c-121">Qulasiasi servizio CDN può essere utilizzato con un ambiente di Commerce.</span><span class="sxs-lookup"><span data-stu-id="9e56c-121">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="9e56c-122">Di seguito sono riportati due esempi:</span><span class="sxs-lookup"><span data-stu-id="9e56c-122">Here are two examples:</span></span>

- <span data-ttu-id="9e56c-123">**Microsoft Azure Front Door Service** - La soluzione CDN di Azure.</span><span class="sxs-lookup"><span data-stu-id="9e56c-123">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="9e56c-124">Per ulteriori informazioni su Azure Front Door Service, vedere la [Documentazione di Azure Front Door Service](/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="9e56c-124">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](/azure/frontdoor/).</span></span>
- <span data-ttu-id="9e56c-125">**Akamai Dynamic Site Accelerator** - Per ulteriori informazioni, vedere [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="9e56c-125">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="9e56c-126">Configurazione di CDN</span><span class="sxs-lookup"><span data-stu-id="9e56c-126">CDN setup</span></span>

<span data-ttu-id="9e56c-127">Il processo di configurazione di CDN comporta i seguenti passaggi generali:</span><span class="sxs-lookup"><span data-stu-id="9e56c-127">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="9e56c-128">Aggiungere un host front-end.</span><span class="sxs-lookup"><span data-stu-id="9e56c-128">Add a front-end host.</span></span>
1. <span data-ttu-id="9e56c-129">Configurare un pool back-end.</span><span class="sxs-lookup"><span data-stu-id="9e56c-129">Configure a backend pool.</span></span>
1. <span data-ttu-id="9e56c-130">Impostazione regole di gestione.</span><span class="sxs-lookup"><span data-stu-id="9e56c-130">Set up rules for routing.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="9e56c-131">Aggiungere un host front-end</span><span class="sxs-lookup"><span data-stu-id="9e56c-131">Add a front-end host</span></span>

<span data-ttu-id="9e56c-132">È possibile utilizzare qualsiasi servizio CDN, ma per l'esempio in questo argomento, viene utilizzato Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="9e56c-132">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="9e56c-133">Per informazioni su come configurare Azure Front Door Service, vedere [Avvio rapido: creare un frontdoor per un'applicazione Web globale altamente disponibile](/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="9e56c-133">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="9e56c-134">Configurare un pool back-end in Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="9e56c-134">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="9e56c-135">Per configurare un pool back-end in Azure Front Door Service, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="9e56c-135">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="9e56c-136">Aggiungi **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** a un pool back-end come host personalizzato che ha un'intestazione host back-end uguale a **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="9e56c-136">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has a backend host header that is the same as **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span></span>
1. <span data-ttu-id="9e56c-137">Sotto **Bilanciamento del carico**, lasciare i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9e56c-137">Under **Load balancing**, leave the default values.</span></span>
1. <span data-ttu-id="9e56c-138">Disabilita i controlli di integrità per il pool back-end.</span><span class="sxs-lookup"><span data-stu-id="9e56c-138">Disable health checks for the backend pool.</span></span>

<span data-ttu-id="9e56c-139">Nella seguente figura è illustrata la finestra di dialogo **Aggiungi un back-end** in Azure Front Door Service con il nome host del back-end immesso.</span><span class="sxs-lookup"><span data-stu-id="9e56c-139">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Finestra di dialogo Aggiungi un pool back-end](./media/CDN_BackendPool.png)

<span data-ttu-id="9e56c-141">Nella seguente figura è illustrata la finestra di dialogo **Aggiungi un back-end** in Azure Front Door Service con il nome host del back-end immesso.</span><span class="sxs-lookup"><span data-stu-id="9e56c-141">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Finestra di dialogo Aggiungi un pool back-end continua](./media/CDN_BackendPool_2.png)

> [!NOTE]
> <span data-ttu-id="9e56c-143">Assicurati di disabilitare **Probe integrità** quando configuri il tuo servizio Azure Front Door per Commerce.</span><span class="sxs-lookup"><span data-stu-id="9e56c-143">Be sure to disable **Health Probes** when setting up your own Azure Front Door service for Commerce.</span></span>


### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="9e56c-144">Impostare regole in Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="9e56c-144">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="9e56c-145">Per impostare una regola di routing in Azure Front Door Service, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="9e56c-145">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="9e56c-146">Aggiungere una regola di routing.</span><span class="sxs-lookup"><span data-stu-id="9e56c-146">Add a routing rule.</span></span>
1. <span data-ttu-id="9e56c-147">Nel campo **Nome** immettere **default**.</span><span class="sxs-lookup"><span data-stu-id="9e56c-147">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="9e56c-148">Nel campo **Protocollo accettato**, selezionare **HTTP e HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="9e56c-148">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="9e56c-149">Nel campo **Host front-end**, immettere **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="9e56c-149">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="9e56c-150">In **Criteri di corrispondenza**, nel campo più in alto, immettere **/\***.</span><span class="sxs-lookup"><span data-stu-id="9e56c-150">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="9e56c-151">In **Dettagli route**, impostare l'opzione **Tipo di route** su **Inoltra**.</span><span class="sxs-lookup"><span data-stu-id="9e56c-151">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="9e56c-152">Nel campo **Pool back-end**, selezionare **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="9e56c-152">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="9e56c-153">Nel gruppo di campi **Protocollo di inoltro**, selezionare l'opzione **Corrispondenza richiesta**.</span><span class="sxs-lookup"><span data-stu-id="9e56c-153">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="9e56c-154">Impostare **Riscrittura URL** su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="9e56c-154">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="9e56c-155">Impostare l'opzione **Memorizzazione nella cache** su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="9e56c-155">Set the **Caching** option to **Disabled**.</span></span>


> [!WARNING]
> <span data-ttu-id="9e56c-156">Se il dominio che utilizzerai è già attivo e live, crea un ticket di supporto dal riquadro **Supporto** in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) per ottenere assistenza per i tuoi prossimi passaggi.</span><span class="sxs-lookup"><span data-stu-id="9e56c-156">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="9e56c-157">Per altre informazioni, vedere [Ottenere supporto per le app Finance and Operations o Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="9e56c-157">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="9e56c-158">Se il dominio è nuovo e non è un dominio live preesistente, è possibile aggiungere il dominio personalizzato alla configurazione per il servizio Frontdoor di Azure.</span><span class="sxs-lookup"><span data-stu-id="9e56c-158">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="9e56c-159">In questo modo il traffico Web verrà indirizzato verso il tuo sito tramite l'istanza Frontdoor di Azure.</span><span class="sxs-lookup"><span data-stu-id="9e56c-159">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="9e56c-160">Per aggiungere il dominio personalizzato (ad esempio `www.fabrikam.com`), è necessario configurare un nome canonico (CNAME) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="9e56c-160">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="9e56c-161">Nella seguente figura è illustrata la finestra di dialogo **Configurazione CNAME** in Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="9e56c-161">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Finestra di dialogo Configurazione CNAME](./media/CNAME_Configuration.png)

<span data-ttu-id="9e56c-163">È possibile utilizzare Azure Front Door Service per gestire il certificato oppure utilizzare il proprio certificato per il dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9e56c-163">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="9e56c-164">Nella seguente figura è illustrata la finestra di dialogo **HTTPS dominio personalizzato** in Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="9e56c-164">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Finestra di dialogo HTTPS dominio personalizzato](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="9e56c-166">Per istruzioni dettagliate sull'aggiunta di un dominio personalizzato a Frontdoor di Azure, vedere [Aggiungere un dominio personalizzato alla frontdoor](/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="9e56c-166">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="9e56c-167">A questo punto, la rete CDN deve essere configurata correttamente di modo che possa essere utilizzata con il sito di Commerce.</span><span class="sxs-lookup"><span data-stu-id="9e56c-167">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e56c-168">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9e56c-168">Additional resources</span></span>

[<span data-ttu-id="9e56c-169">Opzioni di implementazione della rete per la distribuzione di contenuti</span><span class="sxs-lookup"><span data-stu-id="9e56c-169">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]