---
title: Opzioni di implementazione della rete per la distribuzione di contenuti
description: In questo argomento vengono esaminate le diverse opzioni per l'implementazione della rete per la distribuzione di contenuti (CDN) che possono essere utilizzate con gli ambienti Microsoft Dynamics 365 Commerce. Queste opzioni includono istanze native fornite da Commerce di Azure Front Door e istanze di proprietà del cliente di Azure Front Door.
author: BrianShook
ms.date: 03/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: eec18dbffe33bc6366b4282d05189b31620616d6
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351251"
---
# <a name="content-delivery-network-implementation-options"></a>Opzioni di implementazione della rete per la distribuzione di contenuti

[!include [banner](includes/banner.md)]

In questo argomento vengono esaminate le diverse opzioni per l'implementazione della rete per la distribuzione di contenuti (CDN) che possono essere utilizzate con gli ambienti Microsoft Dynamics 365 Commerce. Queste opzioni includono istanze native fornite da Commerce di Azure Front Door e istanze di proprietà del cliente di Azure Front Door.

I clienti di Commerce hanno diverse opzioni quando valutano il servizio CDN da utilizzare con il loro ambiente Commerce. Commerce viene rilasciato con il supporto di base di Azure Front Door che copre i requisiti di dominio personalizzato e hosting di base. Per le aziende che desiderano un maggiore controllo e funzionalità di sicurezza più specifiche, come un web application firewall (WAF), l'opzione migliore potrebbe essere quella di utilizzare un'istanza di Azure Front Door di proprietà del cliente o un servizio CDN esterno.

Le seguenti tre opzioni di implementazione CDN possono essere utilizzate con ambienti Commerce:

- L'istanza di Azure Front Door fornita da Commerce
- Un'istanza di Azure Front Door di proprietà del cliente (per un maggiore controllo e funzionalità di sicurezza aggiuntive)
- Un servizio CDN esterno

Tutte e tre le opzioni di implementazione della rete CDN forniscono solo contenuto HTML dinamico di domini personalizzati. Commerce gestisce automaticamente JavaScript, Cascading Style Sheets (CSS), immagini, video e altro contenuto statico tramite le reti CDN gestite da Microsoft. L'opzione scelta determina le funzionalità operative, di controllo e di sicurezza aggiuntive disponibili.

Nell'illustrazione riportata di seguito viene mostrata una panoramica dell'architettura di Commerce.

![Panoramica dell'architettura di Commerce.](media/Commerce_CDN-Option_ComparisonModels.png)

Per ulteriori informazioni su come configurare un'istanza di Azure Front Door per il sito di Commerce, vedere [Aggiungere supporto CDN](add-cdn-support.md).

## <a name="use-the-commerce-provided-azure-front-door-instance"></a>Utilizzare l'istanza di Azure Front Door fornita da Commerce

La tabella seguente elenca i pro e i contro inerenti all'uso dell'istanza di Azure Front Door fornita da Commerce per gestire gli endpoint del contenuto.

| Pro | Contro |
|------|------|
| <ul><li>L'istanza è inclusa nel costo di Commerce.</li><li>Poiché l'istanza è gestita dal team di Commerce, è necessaria una minore manutenzione e sono presenti passaggi di configurazione condivisi.</li><li>L'infrastruttura ospitata in Azure è scalabile, sicura e affidabile.</li><li>Il certificato Secure Sockets Layer (SSL) richiede una configurazione una tantum e viene rinnovato automaticamente.</li><li>L'istanza viene monitorata dal team di Commerce per rilevare la presenza di errori e anomalie.</li></ul> | <ul><li>Un WAF non è supportato.</li><li>Non vi sono rettifiche delle impostazioni o personalizzazioni specifiche.</li><li>L'istanza dipende dal team di Commerce per gli aggiornamenti o le modifiche.</li><li>Un'istanza di Azure Front Door distinta è necessaria per i domini Apex e lavoro aggiuntivo è necessario per integrare domini Apex con DNS di Azure.</li><li>Al cliente non viene fornita alcuna telemetria sulle risposte al secondo o sulla percentuale di errore.</li></ul> |

L'illustrazione seguente mostra l'architettura dell'istanza di Azure Front Door fornita da Commerce.

![Istanza di Azure Front Door fornita da Commerce.](media/Commerce_CDN-Option_CommerceFrontDoor.png)

## <a name="use-a-customer-owned-azure-front-door-instance"></a>Usare un'istanza di Azure Front Door di proprietà del cliente

La tabella seguente elenca i pro e i contro inerenti all'uso di un'istanza di Azure Front Door di proprietà del cliente per gestire gli endpoint del contenuto.

| Pro | Contro |
|------|------|
| <ul><li>La configurazione è sicura e facile da gestire.</li><li>L'infrastruttura ospitata in Azure è scalabile, sicura e affidabile.</li><li>L'istanza consente l'integrazione del WAF e controlli granulari delle regole per una sicurezza di livello superiore ottimizzata specificamente per il sito.</li><li>L'istanza consente un controllo più preciso dei certificati SSL (sia di proprietà del cliente che gestiti da Azure Front Door) e del collegamento al dominio.</li><li>L'istanza offre una soluzione di dominio Apex se è associata direttamente a DNS di Azure.</li><li>Vengono forniti telemetria e avvisi.</li><li>Il certificato SSL richiede una configurazione una tantum e viene rinnovato automaticamente.</li></ul> | <ul><li>L'istanza è autogestita.</li><li>È richiesto un aumento della conoscenza iniziale.</li></ul> |

L'illustrazione seguente mostra un'infrastruttura di Commerce che include un'istanza di Azure Front Door di proprietà del cliente.

![Infrastruttura di Commerce che include un'istanza di Azure Front Door di proprietà del cliente.](media/Commerce_CDN-Option_CustomerOwnedAzureFrontDoor.png)

## <a name="use-an-external-cdn-service"></a>Utilizzare un servizio CDN esterno

La tabella seguente elenca i pro e i contro dell'utilizzo di un servizio CDN esterno per gestire gli endpoint del contenuto.

| Pro | Contro |
|------|------|
| <ul><li>Questa opzione è utile quando il dominio esistente è già ospitato su una rete CDN esterna.</li><li>Le reti CDN concorrenti (ad esempio, Akamai) potrebbero avere più funzionalità WAF.</li></ul> | <ul><li>Sono necessari un contratto distinto e costi aggiuntivi.</li><li>Il protocollo SSL potrebbe comportare costi aggiuntivi.</li><li>Poiché il servizio è separato dalla struttura cloud di Azure, è necessario gestire un'infrastruttura aggiuntiva.</li><li>Il servizio potrebbe richiedere investimenti più estesi per l'endpoint e la configurazione della sicurezza.</li><li>Il servizio è autogestito.</li><li>Il servizio comporta un monitoraggio automatico.</li></ul> |

L'illustrazione seguente mostra un'infrastruttura di Commerce che include un servizio CDN esterno.

![Infrastruttura di Commerce che include un servizio CDN esterno.](media/Commerce_CDN-Option_ExternalFrontDoor.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)
