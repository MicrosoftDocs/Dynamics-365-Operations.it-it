---
title: Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)
description: In questo argomento viene descritto come aggiungere una rete per la distribuzione di contenuti (CDN) all'ambiente di Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d653b072eca134c765a5db5659b228648fc13c4a
ms.sourcegitcommit: 3fe4d9a33447aa8a62d704fbbf18aeb9cb667baa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5582721"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="0f491-103">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="0f491-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0f491-104">In questo argomento viene descritto come aggiungere una rete per la distribuzione di contenuti (CDN) all'ambiente di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f491-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="0f491-105">Quando si configura un ambiente di e-commerce in Dynamics 365 Commerce, è possibile configurarlo per l'utilizzo con il servizio CDN.</span><span class="sxs-lookup"><span data-stu-id="0f491-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="0f491-106">Il dominio personalizzato può essere abilitato durante il processo di provisioning per l'ambiente di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="0f491-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="0f491-107">In alternativa, è possibile utilizzare una richiesta di assistenza per configurarlo al termine del processo di provisioning.</span><span class="sxs-lookup"><span data-stu-id="0f491-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="0f491-108">Il processo di provisioning per l'ambiente di e-commerce genera un nome host associato all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="0f491-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="0f491-109">Questo nome host ha il formato seguente, dove \<*e-commerce-tenant-name*\> è il nome dell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="0f491-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="0f491-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="0f491-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="0f491-111">Il nome host o l'endpoint generato durante il processo di provisioning supporta un certificato SSL (Secure Sockets Layer) solo per \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="0f491-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="0f491-112">Non supporta SSL per domini personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0f491-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="0f491-113">Di conseguenza, è necessario terminare SSL per i domini personalizzati in CDN e inoltrare il traffico da CDN al nome host o all'endpoint generato da Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f491-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="0f491-114">Inoltre, gli *elementi statici* (file JavaScript o \[CSS\] ) di Commerce vengono serviti dall'endpoint generato da Commerce (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="0f491-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="0f491-115">Gli elementi statici possono essere memorizzati nella cache solo se il nome host o l'endpoint generato da Commerce sono posizionati dopo CDN.</span><span class="sxs-lookup"><span data-stu-id="0f491-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="0f491-116">Impostare SSL</span><span class="sxs-lookup"><span data-stu-id="0f491-116">Set up SSL</span></span>

<span data-ttu-id="0f491-117">Per garantire la configurazione di SSL e la memorizzazione nella cache degli elementi statici, è necessario configurare CDN di modo che sia associato al nome host generato da Commerce per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="0f491-117">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="0f491-118">È inoltre necessario memorizzare nella cache il criterio seguente solo per gli elementi statici:</span><span class="sxs-lookup"><span data-stu-id="0f491-118">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="0f491-119">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="0f491-119">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="0f491-120">Dopo il provisioning dell'ambiente di Commerce con il dominio personalizzato fornito o dopo aver fornito il dominio personalizzato per l'ambiente utilizzando una richiesta di assistenza, puntare il dominio personalizzato al nome host o all'endpoint generato da Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f491-120">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="0f491-121">Come indicato in precedenza, il nome host o l'endpoint generato supporta un certificato SSL solo per \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="0f491-121">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="0f491-122">Non supporta SSL per domini personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0f491-122">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="0f491-123">Servizi CDN</span><span class="sxs-lookup"><span data-stu-id="0f491-123">CDN services</span></span>

<span data-ttu-id="0f491-124">Qulasiasi servizio CDN può essere utilizzato con un ambiente di Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f491-124">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="0f491-125">Di seguito sono riportati due esempi:</span><span class="sxs-lookup"><span data-stu-id="0f491-125">Here are two examples:</span></span>

- <span data-ttu-id="0f491-126">**Microsoft Azure Front Door Service** - La soluzione CDN di Azure.</span><span class="sxs-lookup"><span data-stu-id="0f491-126">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="0f491-127">Per ulteriori informazioni su Azure Front Door Service, vedere la [Documentazione di Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="0f491-127">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="0f491-128">**Akamai Dynamic Site Accelerator** - Per ulteriori informazioni, vedere [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="0f491-128">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="0f491-129">Configurazione di CDN</span><span class="sxs-lookup"><span data-stu-id="0f491-129">CDN setup</span></span>

<span data-ttu-id="0f491-130">Il processo di configurazione di CDN comporta i seguenti passaggi generali:</span><span class="sxs-lookup"><span data-stu-id="0f491-130">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="0f491-131">Aggiungere un host front-end.</span><span class="sxs-lookup"><span data-stu-id="0f491-131">Add a front-end host.</span></span>
1. <span data-ttu-id="0f491-132">Configurare un pool back-end.</span><span class="sxs-lookup"><span data-stu-id="0f491-132">Configure a backend pool.</span></span>
1. <span data-ttu-id="0f491-133">Impostare le regole per l'instradamento e la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="0f491-133">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="0f491-134">Aggiungere un host front-end</span><span class="sxs-lookup"><span data-stu-id="0f491-134">Add a front-end host</span></span>

<span data-ttu-id="0f491-135">È possibile utilizzare qualsiasi servizio CDN, ma per l'esempio in questo argomento, viene utilizzato Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="0f491-135">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="0f491-136">Per informazioni su come configurare Azure Front Door Service, vedere [Avvio rapido: creare un frontdoor per un'applicazione Web globale altamente disponibile](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="0f491-136">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="0f491-137">Configurare un pool back-end in Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="0f491-137">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="0f491-138">Per configurare un pool back-end in Azure Front Door Service, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="0f491-138">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="0f491-139">Aggiungere **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** a un pool back-end come host personalizzato che dispone di un'intestazione host back-end vuota.</span><span class="sxs-lookup"><span data-stu-id="0f491-139">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has an empty backend host header.</span></span>
1. <span data-ttu-id="0f491-140">Sotto **Bilanciamento del carico**, lasciare i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0f491-140">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="0f491-141">Nella seguente figura è illustrata la finestra di dialogo **Aggiungi un back-end** in Azure Front Door Service con il nome host del back-end immesso.</span><span class="sxs-lookup"><span data-stu-id="0f491-141">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Finestra di dialogo Aggiungi un pool back-end](./media/CDN_BackendPool.png)

<span data-ttu-id="0f491-143">Nella seguente figura è illustrata la finestra di dialogo **Aggiungi un back-end** in Azure Front Door Service con il nome host del back-end immesso.</span><span class="sxs-lookup"><span data-stu-id="0f491-143">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Finestra di dialogo Aggiungi un pool back-end continua](./media/CDN_BackendPool_2.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="0f491-145">Impostare regole in Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="0f491-145">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="0f491-146">Per impostare una regola di routing in Azure Front Door Service, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="0f491-146">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="0f491-147">Aggiungere una regola di routing.</span><span class="sxs-lookup"><span data-stu-id="0f491-147">Add a routing rule.</span></span>
1. <span data-ttu-id="0f491-148">Nel campo **Nome** immettere **default**.</span><span class="sxs-lookup"><span data-stu-id="0f491-148">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="0f491-149">Nel campo **Protocollo accettato**, selezionare **HTTP e HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="0f491-149">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="0f491-150">Nel campo **Host front-end**, immettere **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="0f491-150">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="0f491-151">In **Criteri di corrispondenza**, nel campo più in alto, immettere **/\***.</span><span class="sxs-lookup"><span data-stu-id="0f491-151">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="0f491-152">In **Dettagli route**, impostare l'opzione **Tipo di route** su **Inoltra**.</span><span class="sxs-lookup"><span data-stu-id="0f491-152">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="0f491-153">Nel campo **Pool back-end**, selezionare **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="0f491-153">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="0f491-154">Nel gruppo di campi **Protocollo di inoltro**, selezionare l'opzione **Corrispondenza richiesta**.</span><span class="sxs-lookup"><span data-stu-id="0f491-154">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="0f491-155">Impostare **Riscrittura URL** su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="0f491-155">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="0f491-156">Impostare l'opzione **Memorizzazione nella cache** su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="0f491-156">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="0f491-157">Per impostare una regola di memorizzazione nella cache in Azure Front Door Service, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="0f491-157">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="0f491-158">Aggiungere una regola di memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="0f491-158">Add a caching rule.</span></span>
1. <span data-ttu-id="0f491-159">Nel campo **Nome** immettere **statics**.</span><span class="sxs-lookup"><span data-stu-id="0f491-159">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="0f491-160">Nel campo **Protocollo accettato**, selezionare **HTTP e HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="0f491-160">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="0f491-161">Nel campo **Host front-end**, immettere **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="0f491-161">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="0f491-162">In **Criteri di corrispondenza**, nel campo più in alto, immettere **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="0f491-162">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="0f491-163">In **Dettagli route**, impostare l'opzione **Tipo di route** su **Inoltra**.</span><span class="sxs-lookup"><span data-stu-id="0f491-163">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="0f491-164">Nel campo **Pool back-end**, selezionare **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="0f491-164">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="0f491-165">Nel gruppo di campi **Protocollo di inoltro**, selezionare l'opzione **Corrispondenza richiesta**.</span><span class="sxs-lookup"><span data-stu-id="0f491-165">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="0f491-166">Impostare **Riscrittura URL** su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="0f491-166">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="0f491-167">Impostare l'opzione **Memorizzazione nella cache** su **Disabilitata**.</span><span class="sxs-lookup"><span data-stu-id="0f491-167">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="0f491-168">Nel campo **Comportamento di memorizzazione nella cache della stringa di query**, selezionare **Memorizza nella cache tutti gli URL univoci**.</span><span class="sxs-lookup"><span data-stu-id="0f491-168">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="0f491-169">Nel gruppo di campi **Compressione dinamica**, selezionare **Abilitata**.</span><span class="sxs-lookup"><span data-stu-id="0f491-169">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="0f491-170">Nella seguente figura è illustrata la finestra di dialogo **Aggiungi una regola** in Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="0f491-170">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Finestra di dialogo Aggiungi una regola](./media/CDN_CachingRule.png)

> [!WARNING]
> <span data-ttu-id="0f491-172">Se il dominio che utilizzerai è già attivo e live, crea un ticket di supporto dal riquadro **Supporto** in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) per ottenere assistenza per i tuoi prossimi passaggi.</span><span class="sxs-lookup"><span data-stu-id="0f491-172">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="0f491-173">Per altre informazioni, vedere [Ottenere supporto per le app Finance and Operations o Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="0f491-173">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="0f491-174">Se il dominio è nuovo e non è un dominio live preesistente, è possibile aggiungere il dominio personalizzato alla configurazione per il servizio Frontdoor di Azure.</span><span class="sxs-lookup"><span data-stu-id="0f491-174">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="0f491-175">In questo modo il traffico Web verrà indirizzato verso il tuo sito tramite l'istanza Frontdoor di Azure.</span><span class="sxs-lookup"><span data-stu-id="0f491-175">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="0f491-176">Per aggiungere il dominio personalizzato (ad esempio `www.fabrikam.com`), è necessario configurare un nome canonico (CNAME) per il dominio.</span><span class="sxs-lookup"><span data-stu-id="0f491-176">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="0f491-177">Nella seguente figura è illustrata la finestra di dialogo **Configurazione CNAME** in Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="0f491-177">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Finestra di dialogo Configurazione CNAME](./media/CNAME_Configuration.png)

<span data-ttu-id="0f491-179">È possibile utilizzare Azure Front Door Service per gestire il certificato oppure utilizzare il proprio certificato per il dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0f491-179">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="0f491-180">Nella seguente figura è illustrata la finestra di dialogo **HTTPS dominio personalizzato** in Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="0f491-180">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Finestra di dialogo HTTPS dominio personalizzato](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="0f491-182">Per istruzioni dettagliate sull'aggiunta di un dominio personalizzato a Frontdoor di Azure, vedere [Aggiungere un dominio personalizzato alla frontdoor](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="0f491-182">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="0f491-183">A questo punto, la rete CDN deve essere configurata correttamente di modo che possa essere utilizzata con il sito di Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f491-183">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f491-184">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0f491-184">Additional resources</span></span>

[<span data-ttu-id="0f491-185">Opzioni di implementazione della rete per la distribuzione di contenuti</span><span class="sxs-lookup"><span data-stu-id="0f491-185">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
