---
title: Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)
description: In questo articolo viene descritto come aggiungere una rete per la distribuzione di contenuti (CDN) all'ambiente di Microsoft Dynamics 365 Commerce.
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 84839c1e370dccd19462de5c4a3dc120df15df09
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275814"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come aggiungere una rete per la distribuzione di contenuti (CDN) all'ambiente di Microsoft Dynamics 365 Commerce.

Quando si configura un ambiente di e-commerce in Dynamics 365 Commerce, è possibile configurarlo per l'utilizzo con il servizio CDN. 

Il dominio personalizzato può essere abilitato durante il processo di provisioning per l'ambiente di e-commerce. In alternativa, è possibile utilizzare una richiesta di assistenza per configurarlo al termine del processo di provisioning. Il processo di provisioning per l'ambiente di e-commerce genera un nome host associato all'ambiente. Questo nome host ha il formato seguente, dove \<*e-commerce-tenant-name*\> è il nome dell'ambiente:

&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com

Il nome host o l'endpoint generato durante il processo di provisioning supporta un certificato SSL (Secure Sockets Layer) solo per \*.commerce.dynamics.com. Non supporta SSL per domini personalizzati. Di conseguenza, è necessario terminare SSL per i domini personalizzati in CDN e inoltrare il traffico da CDN al nome host o all'endpoint generato da Commerce. 

Inoltre, gli *elementi statici* (file JavaScript o \[CSS\] ) di Commerce vengono serviti dall'endpoint generato da Commerce (\*.commerce.dynamics.com). Gli elementi statici possono essere memorizzati nella cache solo se il nome host o l'endpoint generato da Commerce sono posizionati dopo CDN.

## <a name="set-up-ssl"></a>Impostare SSL

Dopo il provisioning dell'ambiente di Commerce con il dominio personalizzato fornito o dopo aver fornito il dominio personalizzato per l'ambiente utilizzando una richiesta di assistenza, è necessario collaborare con il team di onboarding di Commerce per pianificare le modifiche al DNS.

Come indicato in precedenza, il nome host o l'endpoint generato supporta un certificato SSL solo per \*.commerce.dynamics.com. Non supporta SSL per domini personalizzati.

## <a name="cdn-services"></a>Servizi CDN

Qulasiasi servizio CDN può essere utilizzato con un ambiente di Commerce. Di seguito sono riportati due esempi:

- **Microsoft Azure Front Door Service** - La soluzione CDN di Azure. Per ulteriori informazioni su Azure Front Door Service, vedere la [Documentazione di Azure Front Door Service](/azure/frontdoor/).
- **Akamai Dynamic Site Accelerator** - Per ulteriori informazioni, vedere [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).

## <a name="cdn-setup"></a>Configurazione di CDN

Il processo di configurazione di CDN comporta i seguenti passaggi generali:

1. Aggiungere un host front-end.
1. Configurare un pool back-end.
1. Impostazione regole di gestione.

### <a name="add-a-front-end-host"></a>Aggiungere un host front-end

È possibile utilizzare qualsiasi servizio CDN, ma per l'esempio in questo articolo, viene utilizzato Azure Front Door Service. 

Per informazioni su come configurare Azure Front Door Service, vedere [Avvio rapido: creare un frontdoor per un'applicazione Web globale altamente disponibile](/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a>Configurare un pool back-end in Azure Front Door Service

Per configurare un pool back-end in Azure Front Door Service, procedere come segue.

1. Aggiungi **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** a un pool back-end come host personalizzato che ha un'intestazione host back-end uguale a **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.
1. Sotto **Bilanciamento del carico**, lasciare i valori predefiniti.
1. Disabilita i controlli di integrità per il pool back-end.

Nella seguente figura è illustrata la finestra di dialogo **Aggiungi un back-end** in Azure Front Door Service con il nome host del back-end immesso.

![Finestra di dialogo Aggiungi un pool back-end.](./media/CDN_BackendPool.png)

Nella seguente figura è illustrata la finestra di dialogo **Aggiungi un back-end** in Azure Front Door Service con il nome host del back-end immesso.

![Finestra di dialogo Aggiungi un pool back-end continua.](./media/CDN_BackendPool_2.png)

> [!NOTE]
> Assicurati di disabilitare **Probe integrità** quando configuri il tuo servizio Azure Front Door per Commerce.


### <a name="set-up-rules-in-azure-front-door-service"></a>Impostare regole in Azure Front Door Service

Per impostare una regola di routing in Azure Front Door Service, effettuare le seguenti operazioni.

1. Aggiungere una regola di routing.
1. Nel campo **Nome** immettere **default**.
1. Nel campo **Protocollo accettato**, selezionare **HTTP e HTTPS**.
1. Nel campo **Host front-end**, immettere **dynamics-ecom-tenant-name.azurefd.net**.
1. In **Criteri di corrispondenza**, nel campo più in alto, immettere **/\***.
1. In **Dettagli route**, impostare l'opzione **Tipo di route** su **Inoltra**.
1. Nel campo **Pool back-end**, selezionare **ecom-backend**.
1. Nel gruppo di campi **Protocollo di inoltro**, selezionare l'opzione **Corrispondenza richiesta**. 
1. Impostare **Riscrittura URL** su **Disabilitata**.
1. Impostare l'opzione **Memorizzazione nella cache** su **Disabilitata**.


> [!WARNING]
> Se il dominio che utilizzerai è già attivo e live, crea un ticket di supporto dal riquadro **Supporto** in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) per ottenere assistenza per i tuoi prossimi passaggi. Per altre informazioni, vedere [Ottenere supporto per le app per la finanza e le operazioni o Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

Se il dominio è nuovo e non è un dominio live preesistente, è possibile aggiungere il dominio personalizzato alla configurazione per il servizio Frontdoor di Azure. In questo modo il traffico Web verrà indirizzato verso il tuo sito tramite l'istanza Frontdoor di Azure. Per aggiungere il dominio personalizzato (ad esempio `www.fabrikam.com`), è necessario configurare un nome canonico (CNAME) per il dominio.

Nella seguente figura è illustrata la finestra di dialogo **Configurazione CNAME** in Azure Front Door Service.

![Finestra di dialogo Configurazione CNAME.](./media/CNAME_Configuration.png)

È possibile utilizzare Azure Front Door Service per gestire il certificato oppure utilizzare il proprio certificato per il dominio personalizzato.

Nella seguente figura è illustrata la finestra di dialogo **HTTPS dominio personalizzato** in Azure Front Door Service.

![Finestra di dialogo HTTPS dominio personalizzato.](./media/Custom_Domain_HTTPS.png)

Per istruzioni dettagliate sull'aggiunta di un dominio personalizzato a Frontdoor di Azure, vedere [Aggiungere un dominio personalizzato alla frontdoor](/azure/frontdoor/front-door-custom-domain).

A questo punto, la rete CDN deve essere configurata correttamente di modo che possa essere utilizzata con il sito di Commerce.

## <a name="additional-resources"></a>Risorse aggiuntive

[Opzioni di implementazione della rete per la distribuzione di contenuti](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
