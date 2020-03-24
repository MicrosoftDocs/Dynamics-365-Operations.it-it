---
title: Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)
description: In questo argomento viene descritto come aggiungere una rete per la distribuzione di contenuti (CDN) all'ambiente di Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 23ac9d8844c2a8ae20bd316c40078319601a3a4d
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096727"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="d6d0e-103">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="d6d0e-103">Add support for a content delivery network (CDN)</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d6d0e-104">In questo argomento viene descritto come aggiungere una rete per la distribuzione di contenuti (CDN) all'ambiente di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

## <a name="overview"></a><span data-ttu-id="d6d0e-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d6d0e-105">Overview</span></span>

<span data-ttu-id="d6d0e-106">Quando si configura un ambiente di e-Commerce in Dynamics 365 Commerce, è possibile configurarlo per l'utilizzo con il servizio CDN.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-106">When you set up an e-Commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="d6d0e-107">Il dominio personalizzato può essere abilitato durante il processo di provisioning per l'ambiente di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-107">Your custom domain can be enabled during the provisioning process for your e-Commerce environment.</span></span> <span data-ttu-id="d6d0e-108">In alternativa, è possibile utilizzare una richiesta di assistenza per configurarlo al termine del processo di provisioning.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-108">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="d6d0e-109">Il processo di provisioning per l'ambiente di e-Commerce genera un nome host associato all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-109">The provisioning process for the e-Commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="d6d0e-110">Questo nome host ha il formato seguente, dove *e-commerce-tenant-name* è il nome dell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="d6d0e-110">This host name has the following format, where *e-commerce-tenant-name* is the name of your environment:</span></span>

<span data-ttu-id="d6d0e-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="d6d0e-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="d6d0e-112">Il nome host o l'endpoint generato durante il processo di provisioning supporta un certificato SSL (Secure Sockets Layer) solo per \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-112">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="d6d0e-113">Non supporta SSL per domini personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-113">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="d6d0e-114">Di conseguenza, è necessario terminare SSL per i domini personalizzati in CDN e inoltrare il traffico da CDN al nome host o all'endpoint generato da Commerce.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-114">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="d6d0e-115">Inoltre, gli *elementi statici* (file JavaScript o \[CSS\] ) di Commerce vengono serviti dall'endpoint generato da Commerce (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="d6d0e-115">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="d6d0e-116">Gli elementi statici possono essere memorizzati nella cache solo se il nome host o l'endpoint generato da Commerce sono posizionati dopo CDN.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-116">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="d6d0e-117">Impostare SSL</span><span class="sxs-lookup"><span data-stu-id="d6d0e-117">Set up SSL</span></span>

<span data-ttu-id="d6d0e-118">Per garantire la configurazione di SSL e la memorizzazione nella cache degli elementi statici, è necessario configurare CDN di modo che sia associato al nome host generato da Commerce per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-118">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="d6d0e-119">È inoltre necessario memorizzare nella cache il criterio seguente solo per gli elementi statici:</span><span class="sxs-lookup"><span data-stu-id="d6d0e-119">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="d6d0e-120">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="d6d0e-120">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="d6d0e-121">Dopo il provisioning dell'ambiente di Commerce con il dominio personalizzato fornito o dopo aver fornito il dominio personalizzato per l'ambiente utilizzando una richiesta di assistenza, puntare il dominio personalizzato al nome host o all'endpoint generato da Commerce.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-121">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="d6d0e-122">Come indicato in precedenza, il nome host o l'endpoint generato supporta un certificato SSL solo per \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-122">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="d6d0e-123">Non supporta SSL per domini personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-123">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="d6d0e-124">Servizi CDN</span><span class="sxs-lookup"><span data-stu-id="d6d0e-124">CDN services</span></span>

<span data-ttu-id="d6d0e-125">Qulasiasi servizio CDN può essere utilizzato con un ambiente di Commerce.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-125">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="d6d0e-126">Di seguito sono riportati due esempi:</span><span class="sxs-lookup"><span data-stu-id="d6d0e-126">Here are two examples:</span></span>

- <span data-ttu-id="d6d0e-127">**Microsoft Azure Front Door Service** - La soluzione CDN di Azure.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-127">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="d6d0e-128">Per ulteriori informazioni su Azure Front Door Service, vedere la [Documentazione di Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="d6d0e-128">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="d6d0e-129">**Akamai Dynamic Site Accelerator** - Per ulteriori informazioni, vedere [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="d6d0e-129">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="d6d0e-130">Configurazione di CDN</span><span class="sxs-lookup"><span data-stu-id="d6d0e-130">CDN setup</span></span>

<span data-ttu-id="d6d0e-131">Il processo di configurazione di CDN comporta i seguenti passaggi generali:</span><span class="sxs-lookup"><span data-stu-id="d6d0e-131">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="d6d0e-132">Aggiungere un host front-end.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-132">Add a front-end host.</span></span>
1. <span data-ttu-id="d6d0e-133">Configurare un pool back-end.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-133">Configure a back-end pool.</span></span>
1. <span data-ttu-id="d6d0e-134">Impostare le regole per l'instradamento e la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-134">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="d6d0e-135">Aggiungere un host front-end</span><span class="sxs-lookup"><span data-stu-id="d6d0e-135">Add a front-end host</span></span>

<span data-ttu-id="d6d0e-136">È possibile utilizzare qualsiasi servizio CDN, ma per l'esempio in questo argomento, viene utilizzato Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-136">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="d6d0e-137">Per informazioni su come configurare Azure Front Door Service, vedere [Avvio rapido: creare un frontdoor per un'applicazione Web globale altamente disponibile](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="d6d0e-137">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a><span data-ttu-id="d6d0e-138">Configurare un pool back-end in Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="d6d0e-138">Configure a back-end pool in Azure Front Door Service</span></span>

<span data-ttu-id="d6d0e-139">Per configurare un pool back-end in Azure Front Door Service, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-139">To configure a back-end pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="d6d0e-140">Aggiungere **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** a un pool back-end come host personalizzato che dispone di un'intestazione host back-end vuota.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-140">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a back-end pool as a custom host that has an empty back-end host header.</span></span>
1. <span data-ttu-id="d6d0e-141">In **Probe integrità**, nel campo **Percorso**, immettere **/keepalive**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-141">Under **Health probes**, in the **Path** field, enter **/keepalive**.</span></span>
1. <span data-ttu-id="d6d0e-142">Nel campo **Intervalli (secondi)**, immettere **255**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-142">In the **Intervals (seconds)** field, enter **255**.</span></span>
1. <span data-ttu-id="d6d0e-143">Sotto **Bilanciamento del carico**, lasciare i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-143">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="d6d0e-144">Nella seguente figura è illustrata la finestra di dialogo **Aggiungi un pool back-end** in Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-144">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service.</span></span>

![Finestra di dialogo Aggiungi un pool back-end](./media/CDN_BackendPool.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="d6d0e-146">Impostare regole in Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="d6d0e-146">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="d6d0e-147">Per impostare una regola di routing in Azure Front Door Service, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-147">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="d6d0e-148">Aggiungere una regola di routing.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-148">Add a routing rule.</span></span>
1. <span data-ttu-id="d6d0e-149">Nel campo **Nome** immettere **default**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-149">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="d6d0e-150">Nel campo **Protocollo accettato**, selezionare **HTTP e HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-150">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="d6d0e-151">Nel campo **Host front-end**, immettere **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-151">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="d6d0e-152">In **Criteri di corrispondenza**, nel campo più in alto, immettere **/\***.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-152">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="d6d0e-153">In **Dettagli route**, impostare l'opzione **Tipo di route** su **Inoltra**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-153">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="d6d0e-154">Nel campo **Pool back-end**, selezionare **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-154">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="d6d0e-155">Nel gruppo di campi **Protocollo di inoltro**, selezionare l'opzione **Corrispondenza richiesta**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-155">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="d6d0e-156">Impostare **Riscrittura URL** su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-156">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="d6d0e-157">Impostare l'opzione **Memorizzazione nella cache** su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-157">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="d6d0e-158">Per impostare una regola di memorizzazione nella cache in Azure Front Door Service, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-158">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="d6d0e-159">Aggiungere una regola di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-159">Add a caching rule.</span></span>
1. <span data-ttu-id="d6d0e-160">Nel campo **Nome** immettere **statics**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-160">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="d6d0e-161">Nel campo **Protocollo accettato**, selezionare **HTTP e HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-161">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="d6d0e-162">Nel campo **Host front-end**, immettere **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-162">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="d6d0e-163">In **Criteri di corrispondenza**, nel campo più in alto, immettere **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-163">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="d6d0e-164">In **Dettagli route**, impostare l'opzione **Tipo di route** su **Inoltra**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-164">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="d6d0e-165">Nel campo **Pool back-end**, selezionare **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-165">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="d6d0e-166">Nel gruppo di campi **Protocollo di inoltro**, selezionare l'opzione **Corrispondenza richiesta**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-166">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="d6d0e-167">Impostare **Riscrittura URL** su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-167">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="d6d0e-168">Impostare l'opzione **Memorizzazione nella cache** su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-168">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="d6d0e-169">Nel campo **Comportamento di memorizzazione nella cache della stringa di query**, selezionare **Memorizza nella cache tutti gli URL univoci**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-169">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="d6d0e-170">Nel gruppo di campi **Compressione dinamica**, selezionare **Abilitata**.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-170">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="d6d0e-171">Nella seguente figura è illustrata la finestra di dialogo **Aggiungi una regola** in Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-171">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Finestra di dialogo Aggiungi una regola](./media/CDN_CachingRule.png)

<span data-ttu-id="d6d0e-173">Dopo la distribuzione di questa configurazione iniziale, è necessario aggiungere il dominio personalizzato alla configurazione di Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-173">After this initial configuration is deployed, you must add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="d6d0e-174">Per aggiungere il dominio personalizzato (ad esempio `www.fabrikam.com`), è necessario configurare un nome canonico (CNAME) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-174">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="d6d0e-175">Nella seguente figura è illustrata la finestra di dialogo **Configurazione CNAME** in Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-175">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Finestra di dialogo Configurazione CNAME](./media/CNAME_Configuration.png)

> [!NOTE]
> <span data-ttu-id="d6d0e-177">Se il dominio che verrà utilizzato è già attivo e live, contattare il supporto per abilitare questo dominio con Azure Front Door Service per configurare un test.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-177">If the domain that you will use is already active and live, contact support to enable this domain with Azure Front Door Service to set up a test.</span></span>

<span data-ttu-id="d6d0e-178">È possibile utilizzare Azure Front Door Service per gestire il certificato oppure utilizzare il proprio certificato per il dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-178">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="d6d0e-179">Nella seguente figura è illustrata la finestra di dialogo **HTTPS dominio personalizzato** in Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-179">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Finestra di dialogo HTTPS dominio personalizzato](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="d6d0e-181">A questo punto, la rete CDN deve essere configurata correttamente di modo che possa essere utilizzata con il sito di Commerce.</span><span class="sxs-lookup"><span data-stu-id="d6d0e-181">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d6d0e-182">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d6d0e-182">Additional resources</span></span>

[<span data-ttu-id="d6d0e-183">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="d6d0e-183">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="d6d0e-184">Distribuire un nuovo sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="d6d0e-184">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="d6d0e-185">Impostare un canale punto vendita online</span><span class="sxs-lookup"><span data-stu-id="d6d0e-185">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="d6d0e-186">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="d6d0e-186">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="d6d0e-187">Associare un sito online a un canale</span><span class="sxs-lookup"><span data-stu-id="d6d0e-187">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="d6d0e-188">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="d6d0e-188">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="d6d0e-189">Caricare reindirizzamenti di URL in blocco</span><span class="sxs-lookup"><span data-stu-id="d6d0e-189">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="d6d0e-190">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="d6d0e-190">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="d6d0e-191">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="d6d0e-191">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="d6d0e-192">Configurare più tenant B2C in un ambiente Commerce</span><span class="sxs-lookup"><span data-stu-id="d6d0e-192">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="d6d0e-193">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="d6d0e-193">Enable location-based store detection</span></span>](enable-store-detection.md)
