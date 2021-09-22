---
title: Componenti di amministrazione della fatturazione elettronica
description: In questo argomento vengono fornite informazioni sui componenti correlati all'amministrazione della Fatturazione elettronica.
author: gionoder
ms.date: 08/31/2021
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
ms.openlocfilehash: d187e8a03552258099d7021ff056d0726ea60ca1
ms.sourcegitcommit: baf82100f0aa7d5f5f47c7f54bc155d8a07beab5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2021
ms.locfileid: "7463883"
---
# <a name="electronic-invoicing-administration-components"></a>Componenti di amministrazione della fatturazione elettronica

[!include [banner](../includes/banner.md)]


In questo argomento vengono fornite informazioni sui componenti correlati all'amministrazione della Fatturazione elettronica. Fornisce inoltre informazioni su come configurare il servizio per la fatturazione elettronica.

## <a name="azure"></a>Azure

Utilizzare Microsoft Azure per creare i segreti per l'insieme di credenziali delle chiavi e configurare un account di archiviazione. Utilizzare quindi i segreti dell'insieme di credenziali delle chiavi e il token SAS dell'account di archiviazione nella configurazione della fatturazione elettronica.

## <a name="lifecycle-services"></a>Lifecycle Services

Utilizzare Microsoft Dynamics Lifecycle Services (LCS) per abilitare il componente aggiuntivo della fatturazione elettronica per il progetto di distribuzione LCS.

> [!NOTE]
> L'installazione di componenti aggiuntivi in LCS richiede almeno un **Ambiente virtuale di livello 2**. Per ulteriori informazioni sulla pianificazione dell'ambiente, vedere [Pianificazione ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
 

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

Dynamics 365 Regulatory Configuration Services (RCS) è l'interfaccia utilizzata per configurare la Fatturazione elettronica. Le risorse quali ambienti e funzionalità di fatturazione elettronica vengono create, gestite e ospitate in RCS. Quando le risorse sono pronte, vengono pubblicate nel servizio Fatturazione elettronica.

Per l'iscrizione a RCS, vedere [Regulatory services](https://marketing.configure.global.dynamics.com/).

Per altre informazioni su RCS, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md)

### <a name="integration-with-electronic-invoicing"></a>Integrazione con la fatturazione elettronica 

Prima di poter utilizzare RCS per configurare le fatture elettroniche, è necessario configurare RCS per consentire la comunicazione con la Fatturazione elettronica. Completa questa configurazione nella scheda **Fatturazione elettronica** della pagina **Parametri per la creazione di report elettronici**.

#### <a name="service-endpoint"></a><a id='svc-endpoint-uris'></a>Endpoint servizio

La fatturazione elettronica è disponibile in varie aree geografiche del data center di Azure: La tabella seguente elenca la disponibilità per regione.


| Area geografica del data center di Azure | URI endpoint servizio                                                       |
|----------------------------|----------------------------------------------------------------------------|
| Stati Uniti              | <p>https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing</p> |
| Europa                     | <p>https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/</p> |
| Regno Unito             | <p>https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p> |
| Asia                       | <p>https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p> |

### <a name="service-environments"></a>Ambienti di servizio

Gli ambienti del servizio sono partizioni logiche create per supportare l'esecuzione delle funzionalità di globalizzazione nella fatturazione elettronica. I segreti di sicurezza, i certificati digitali e la governance (ovvero le autorizzazioni di accesso) devono essere configurati a livello di ambiente del servizio.

I clienti possono creare tutti gli ambienti del servizio che desiderano. Tutti gli ambienti del servizio creati da un cliente sono indipendenti l'uno dall'altro.

Gli ambienti del servizio devono essere creati e gestiti in RCS. Quando gli ambienti del servizio sono pronti, devono essere pubblicati nella Fatturazione elettronica.

#### <a name="service-environment-status"></a>Stato dell'ambiente del servizio

Gli ambienti del servizio possono essere gestiti tramite lo stato. Le possibili opzioni sono:

- **Non pubblicato** - L'ambiente è stato creato, ma non è stato ancora pubblicato.
- **Pubblicato** - L'ambiente è stato pubblicato nella Fatturazione elettronica.
- **Modificato** - Gli attributi di un ambiente pubblicato sono stati modificati, ma le modifiche non sono state ancora pubblicate.

#### <a name="customer-secrets"></a>Segreti del cliente

Il servizio Fatturazione elettronica è responsabile dell'archiviazione di tutti i dati aziendali nelle risorse di Azure di proprietà della tua azienda. Per garantire che il servizio funzioni correttamente e che tutti i dati aziendali necessari e generati dalla fatturazione elettronica siano accessibili, è necessario creare due risorse principali di Azure:

- Un account di archiviazione di Azure (archiviazione BLOB) che archivierà documenti elettronici, inclusi fatture elettroniche, risultati delle trasformazioni di documenti e risposte da servizi Web esterni.
- Un Azure Key Vault che archivierà i certificati e l'URI (Uniform Resource Identifier) dell'account di archiviazione (token SAS).


Un Key Vault dedicato e un account di archiviazione del cliente devono essere allocati specificamente per l'utilizzo con la fatturazione elettronica. Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

Per monitorare l'integrità di Key Vault e ricevere avvisi, configurare Monitoraggio di Azure per Key Vault. Abilitando la registrazione di Key Vault, è possibile monitorare come, quando e chi accede ai Key Vault. Per ulteriori informazioni, vedere [Monitoraggio e avvisi per Azure Key Vault](/azure/key-vault/general/alert) e [Come abilitare la registrazione di Key Vault](/azure/key-vault/general/howto-logging?tabs=azure-cli).

Come procedura consigliata, ruota periodicamente i segreti. Per ulteriori informazioni, vedere la [documentazione sui segreti](/azure/key-vault/secrets/).

#### <a name="users"></a>Utenti

Ogni ambiente del servizio deve elencare gli utenti che possono connettersi da Dynamics 365 Finance e Dynamics 365 Supply Chain Management nella Fatturazione elettronica.

#### <a name="publication"></a>Pubblicazione

Gli ambienti del servizio devono essere pubblicati nella Fatturazione elettronica prima di poter essere utilizzati. Solo gli ambienti pubblicati sono accessibili da Finance e Supply Chain Management. Inoltre, un ambiente del servizio deve essere pubblicato prima che qualsiasi aggiornamento degli attributi abbia effetto sul servizio di fatturazione elettronica.

### <a name="connected-applications"></a>Applicazioni connesse

Le applicazioni connesse sono le istanze di Finance e Supply Chain Management che potresti voler raggiungere tramite RCS. Oltre all'URL dell'applicazione e al suo tenant, un'applicazione connessa contiene le credenziali che consentono a RCS di connettersi all'ambiente.

Tramite le applicazioni connesse, puoi configurare parte della funzione di fatturazione elettronica in Finance e Supply Chain Management per far funzionare l'intera funzione di fatturazione elettronica.

## <a name="finance-and-supply-chain-management"></a>Finance e Supply Chain Management

### <a name="integration-with-electronic-invoicing"></a>Integrazione con la fatturazione elettronica

Prima di poter utilizzare Finance e Supply Chain Management per emettere fatture elettroniche tramite la Fatturazione elettronica, è necessario configurarla per consentire la comunicazione con il servizio.

#### <a name="electronic-invoicing-integration-feature"></a>Funzionalità di integrazione della fatturazione elettronica

Per abilitare la comunicazione tra Finance e Supply Chain Management e la Fatturazione elettronica, è necessario attivare la funzionalità **Integrazione della fatturazione elettronica** nell'area di lavoro **Gestione funzionalità**.

#### <a name="service-endpoint"></a>Endpoint servizio

L'endpoint del servizio è l'URL in cui si trova la fatturazione elettronica. Prima di poter emettere fatture elettroniche, l'endpoint del servizio deve essere configurato in Finance e Supply Chain Management per consentire la comunicazione con il servizio.

Per configurare l'endpoint del servizio, andare ad **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico** e quindi, sulla scheda **Fatturazione elettronica**, nel campo **URL endpoint**, immettere l'URL appropriato dalla tabella nella sezione [Endpoint del servizio](#svc-endpoint-uris) riportata in precedenza in questo argomento.

#### <a name="environments"></a>Ambienti

Il nome dell'ambiente immesso in Finance e Supply Chain Management fa riferimento al nome dell'ambiente creato in RCS e pubblicato nella Fatturazione elettronica.

L'ambiente deve essere configurato sulla scheda **Fatturazione elettronica** della pagina **Parametri documento elettronico**. In tal modo, ogni richiesta di emissione di fatture elettroniche contiene l'ambiente in cui la fatturazione elettronica può determinare quale funzionalità di fatturazione elettronica deve elaborare la richiesta.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Configurare le fattura elettroniche in RCS](e-invoicing-configuration-rcs.md)
- [Emissione di fatture elettroniche in Finance e Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
