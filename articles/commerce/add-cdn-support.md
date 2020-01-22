---
title: Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)
description: In questo argomento viene descritto come aggiungere una rete per la distribuzione di contenuti (CDN) all'ambiente di Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: d2d64f0de5287a764cb2e40b99a08084494bf53c
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945630"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere una rete per la distribuzione di contenuti (CDN) all'ambiente di Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Quando si configura un ambiente di e-Commerce in Dynamics 365 Commerce, è possibile configurarlo per l'utilizzo con il servizio CDN. 

Il dominio personalizzato può essere abilitato durante il processo di provisioning per l'ambiente di e-Commerce. In alternativa, è possibile utilizzare una richiesta di assistenza per configurarlo al termine del processo di provisioning. Il processo di provisioning per l'ambiente di e-Commerce genera un nome host associato all'ambiente. Questo nome host ha il formato seguente, dove *e-commerce-tenant-name* è il nome dell'ambiente:

&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com

Il nome host o l'endpoint generato durante il processo di provisioning supporta un certificato SSL (Secure Sockets Layer) solo per \*.commerce.dynamics.com. Non supporta SSL per domini personalizzati. Di conseguenza, è necessario terminare SSL per i domini personalizzati in CDN e inoltrare il traffico da CDN al nome host o all'endpoint generato da Commerce. 

Inoltre, gli *elementi statici* (file JavaScript o \[CSS\] ) di Commerce vengono serviti dall'endpoint generato da Commerce (\*.commerce.dynamics.com). Gli elementi statici possono essere memorizzati nella cache solo se il nome host o l'endpoint generato da Commerce sono posizionati dopo CDN.

## <a name="set-up-ssl"></a>Impostare SSL

Per garantire la configurazione di SSL e la memorizzazione nella cache degli elementi statici, è necessario configurare CDN di modo che sia associato al nome host generato da Commerce per l'ambiente. È inoltre necessario memorizzare nella cache il criterio seguente solo per gli elementi statici: 

/\_msdyn365/\_scnr/\*

Dopo il provisioning dell'ambiente di Commerce con il dominio personalizzato fornito o dopo aver fornito il dominio personalizzato per l'ambiente utilizzando una richiesta di assistenza, puntare il dominio personalizzato al nome host o all'endpoint generato da Commerce.

Come indicato in precedenza, il nome host o l'endpoint generato supporta un certificato SSL solo per \*.commerce.dynamics.com. Non supporta SSL per domini personalizzati.

## <a name="cdn-services"></a>Servizi CDN

Qulasiasi servizio CDN può essere utilizzato con un ambiente di Commerce. Di seguito sono riportati due esempi:

- **Microsoft Azure Front Door Service** - La soluzione CDN di Azure. Per ulteriori informazioni su Azure Front Door Service, vedere la [Documentazione di Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).
- **Akamai Dynamic Site Accelerator** - Per ulteriori informazioni, vedere [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).

## <a name="cdn-setup"></a>Configurazione di CDN

Il processo di configurazione di CDN comporta i seguenti passaggi generali:

1. Aggiungere un host front-end.
1. Configurare un pool back-end.
1. Impostare le regole per l'instradamento e la memorizzazione nella cache.

### <a name="add-a-front-end-host"></a>Aggiungere un host front-end

È possibile utilizzare qualsiasi servizio CDN, ma per l'esempio in questo argomento, viene utilizzato Azure Front Door Service. 

Per informazioni su come configurare Azure Front Door Service, vedere [Avvio rapido: creare un frontdoor per un'applicazione Web globale altamente disponibile](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a>Configurare un pool back-end in Azure Front Door Service

Per configurare un pool back-end in Azure Front Door Service, procedere come segue.

1. Aggiungere **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** a un pool back-end come host personalizzato che dispone di un'intestazione host back-end vuota.
1. In **Probe integrità**, nel campo **Percorso**, immettere **/keepalive**.
1. Nel campo **Intervalli (secondi)**, immettere **255**.
1. Sotto **Bilanciamento del carico**, lasciare i valori predefiniti.

Nella seguente figura è illustrata la finestra di dialogo **Aggiungi un pool back-end** in Azure Front Door Service.

![Finestra di dialogo Aggiungi un pool back-end](./media/CDN_BackendPool.png)

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

Per impostare una regola di memorizzazione nella cache in Azure Front Door Service, effettuare le seguenti operazioni.

1. Aggiungere una regola di memorizzazione nella cache.
1. Nel campo **Nome** immettere **statics**.
1. Nel campo **Protocollo accettato**, selezionare **HTTP e HTTPS**.
1. Nel campo **Host front-end**, immettere **dynamics-ecom-tenant-name.azurefd.net**.
1. In **Criteri di corrispondenza**, nel campo più in alto, immettere **/\_msdyn365/\_scnr/\***.
1. In **Dettagli route**, impostare l'opzione **Tipo di route** su **Inoltra**.
1. Nel campo **Pool back-end**, selezionare **ecom-backend**.
1. Nel gruppo di campi **Protocollo di inoltro**, selezionare l'opzione **Corrispondenza richiesta**.
1. Impostare **Riscrittura URL** su **Disabilitata**.
1. Impostare l'opzione **Memorizzazione nella cache** su **Disabilitata**.
1. Nel campo **Comportamento di memorizzazione nella cache della stringa di query**, selezionare **Memorizza nella cache tutti gli URL univoci**.
1. Nel gruppo di campi **Compressione dinamica**, selezionare **Abilitata**.

Nella seguente figura è illustrata la finestra di dialogo **Aggiungi una regola** in Azure Front Door Service.

![Finestra di dialogo Aggiungi una regola](./media/CDN_CachingRule.png)

Dopo la distribuzione di questa configurazione iniziale, è necessario aggiungere il dominio personalizzato alla configurazione di Azure Front Door Service. Per aggiungere il dominio personalizzato (ad esempio `www.fabrikam.com`), è necessario configurare un nome canonico (CNAME) per il dominio.

Nella seguente figura è illustrata la finestra di dialogo **Configurazione CNAME** in Azure Front Door Service.

![Finestra di dialogo Configurazione CNAME](./media/CNAME_Configuration.png)

> [!NOTE]
> Se il dominio che verrà utilizzato è già attivo e live, contattare il supporto per abilitare questo dominio con Azure Front Door Service per configurare un test.

È possibile utilizzare Azure Front Door Service per gestire il certificato oppure utilizzare il proprio certificato per il dominio personalizzato.

Nella seguente figura è illustrata la finestra di dialogo **HTTPS dominio personalizzato** in Azure Front Door Service.

![Finestra di dialogo HTTPS dominio personalizzato](./media/Custom_Domain_HTTPS.png)

A questo punto, la rete CDN deve essere configurata correttamente di modo che possa essere utilizzata con il sito di Commerce.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Distribuire un nuovo sito di e-commerce](deploy-ecommerce-site.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Associare un sito online a un canale](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)
