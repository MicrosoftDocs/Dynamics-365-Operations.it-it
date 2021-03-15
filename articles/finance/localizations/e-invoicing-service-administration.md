---
title: Componenti di amministrazione del componente aggiuntivo per la fatturazione elettronica
description: In questo argomento vengono fornite informazioni sui componenti correlati all'amministrazione del componente aggiuntivo Fatturazione elettronica.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
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
ms.openlocfilehash: 6f630ebb694217c3bd52378a649933a670c090f2
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104400"
---
# <a name="electronic-invoicing-add-on-administration-components"></a>Componenti di amministrazione del componente aggiuntivo per la fatturazione elettronica

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

In questo argomento vengono fornite informazioni sui componenti correlati all'amministrazione del componente aggiuntivo Fatturazione elettronica. Fornisce inoltre informazioni su come configurare il servizio componente aggiuntivo per la fatturazione elettronica.

## <a name="azure"></a>Azure

Usa Microsoft Azure per creare i segreti per l'insieme di credenziali delle chiavi e l'account di archiviazione. Quindi utilizza i segreti nella configurazione del componente aggiuntivo Fatturazione elettronica.

## <a name="lifecycle-services"></a>Lifecycle Services

Usa Microsoft Dynamics Lifecycle Services (LCS) per abilitare il componente aggiuntivo per i microservizi per il progetto di distribuzione LCS.

In LCS, seleziona il riquadro **Anteprima gestione funzionalità** quindi attiva la funzionalità **Servizio di fatturazione elettronica**.

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

Dynamics 365 Regulatory Configuration Services (RCS) è l'interfaccia utilizzata per configurare il componente aggiuntivo Fatturazione elettronica. Le risorse quali ambienti e funzionalità di fatturazione elettronica vengono create, gestite e ospitate in RCS. Quando le risorse sono pronte, vengono pubblicate nel servizio componente aggiuntivo Fatturazione elettronica.

Per altre informazioni su RCS, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md)

### <a name="integration-with-the-electronic-invoicing-add-on"></a>Integrazione con il componente aggiuntivo per la fatturazione elettronica

Prima di poter utilizzare RCS per configurare le fatture elettroniche, è necessario configurare RCS per consentire la comunicazione con il componente aggiuntivo Fatturazione elettronica. Completa questa configurazione nella scheda **Componente aggiuntivo per la fatturazione elettronica** della pagina **Parametri per la creazione di report elettronici**.

#### <a name="service-endpoint"></a>Endpoint servizio

L'URL dell'endpoint del componente aggiuntivo per la fatturazione elettronica può variare in base all'area geografica del data center di Azure. La tabella seguente elenca la disponibilità per regione:

| Area geografica del data center di Azure | URL endpoint servizio                                                       |
|----------------------------|----------------------------------------------------------------------------|
| Stati Uniti orientali                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
| Stati Uniti occidentali                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
| UE settentrionale                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
| UE occidentale                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

#### <a name="application-id"></a>ID domanda di lavoro

L'ID applicazione è l'ID dell'applicazione componente aggiuntivo per la fatturazione elettronica. In questo caso, il valore è fisso: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

#### <a name="lcs-environment-id"></a>ID ambiente LCS

L'ID ambiente LCS è l'ID dell'abbonamento LCS dell'organizzazione.

### <a name="service-environments"></a>Ambienti di servizio

Gli ambienti del servizio sono partizioni logiche create per supportare l'esecuzione delle funzionalità di fatturazione elettronica nel componente aggiuntivo Fatturazione elettronica. I segreti di sicurezza, i certificati digitali e la governance (ovvero le autorizzazioni di accesso) devono essere configurati a livello di ambiente del servizio.

I clienti possono creare tutti gli ambienti del servizio che desiderano. Tutti gli ambienti del servizio creati da un cliente sono indipendenti l'uno dall'altro.

Gli ambienti del servizio devono essere creati e gestiti in RCS. Quando gli ambienti del servizio sono pronti, devono essere pubblicati nel componente aggiuntivo Fatturazione elettronica.

#### <a name="service-environment-status"></a>Stato dell'ambiente del servizio

Gli ambienti del servizio possono essere gestiti tramite lo stato. Le possibili opzioni sono:

- **Non pubblicato** - L'ambiente è stato creato, ma non è stato ancora pubblicato.
- **Pubblicato** - L'ambiente è stato pubblicato nel componente aggiuntivo Fatturazione elettronica.
- **Modificato** - Gli attributi di un ambiente pubblicato sono stati modificati, ma le modifiche non sono state ancora pubblicate.

#### <a name="customer-secrets"></a>Segreti del cliente

Il servizio del componente aggiuntivo per la fatturazione elettronica è responsabile dell'archiviazione di tutti i dati aziendali nelle risorse di Azure di proprietà della tua azienda. Per garantire che il servizio funzioni correttamente e che tutti i dati aziendali richiesti e generati dal componente aggiuntivo per la fatturazione elettronica siano accessibili solo dal componente aggiuntivo, è necessario creare due risorse principali di Azure:

- Un account di Archiviazione di Azure (Archiviazione BLOB) che archivia le fatture elettroniche
- Un Azure Key Vault che archivia i certificati e l'URI (Uniform Resource Identifier) dell'account di archiviazione

> [!NOTE]
> Un insieme di credenziali delle chiavi dedicato e un account di archiviazione del cliente devono essere allocati specificamente per l'utilizzo con il componente aggiuntivo per la fatturazione elettronica.

Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

#### <a name="users"></a>Utenti

Ogni ambiente del servizio deve elencare gli utenti che possono connettersi da Dynamics 365 Finance e Dynamics 365 Supply Chain Management nel componente aggiuntivo Fatturazione elettronica.

#### <a name="publication"></a>Pubblicazione

Gli ambienti del servizio devono essere pubblicati nel componente aggiuntivo Fatturazione elettronica prima di poter essere utilizzati. Solo gli ambienti pubblicati sono accessibili da Finance e Supply Chain Management. Inoltre, un ambiente del servizio deve essere pubblicato prima che qualsiasi aggiornamento degli attributi abbia effetto sul servizio di fatturazione elettronica.

### <a name="connected-applications"></a>Applicazioni connesse

Le applicazioni connesse sono le istanze di Finance e Supply Chain Management che potresti voler raggiungere tramite RCS. Oltre all'URL dell'applicazione e al suo tenant, un'applicazione connessa contiene le credenziali che consentono a RCS di connettersi all'ambiente.

Tramite le applicazioni connesse, puoi configurare parte della funzione di fatturazione elettronica in Finance e Supply Chain Management per far funzionare l'intera funzione di fatturazione elettronica.

## <a name="finance-and-supply-chain-management"></a>Finance e Supply Chain Management

### <a name="integration-with-electronic-invoicing-add-on"></a>Integrazione con il componente aggiuntivo per la fatturazione elettronica

Prima di poter utilizzare Finance e Supply Chain Management per emettere fatture elettroniche tramite il componente aggiuntivo Fatturazione elettronica, è necessario configurare il componente aggiuntivo per consentire la comunicazione con il servizio.

#### <a name="electronic-invoicing-add-on-integration-feature"></a>Funzionalità di integrazione del componente aggiuntivo per la fatturazione elettronica

Per abilitare la comunicazione tra Finance e Supply Chain Management e il componente aggiuntivo Fatturazione elettronica, è necessario attivare la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica** nell'area di lavoro **Gestione funzionalità**.

#### <a name="service-endpoint"></a>Endpoint servizio

L'endpoint del servizio è l'URL in cui si trova il componente aggiuntivo per la fatturazione elettronica. Prima di poter emettere fatture elettroniche, l'endpoint del servizio deve essere configurato in Finance e Supply Chain Management per consentire la comunicazione con il servizio.

Per configurare l'endpoint del servizio, vai a **Amministrazione organizzazione \> Impostazione \> Parametro documento elettronico** e quindi nella scheda **Servizi di invio**, nel campo **URL componente aggiuntivo per la fatturazione elettronica**, immetti l'URL come descritto nella tabella della sezione **Endpoint del servizio**.

#### <a name="environments"></a>Ambienti

Il nome dell'ambiente immesso in Finance e Supply Chain Management fa riferimento al nome dell'ambiente creato in RCS e pubblicato nel componente aggiuntivo Fatturazione elettronica.

L'ambiente deve essere configurato nella scheda **Servizi di invio** della pagina **Parametro documento elettronico** in modo che ogni richiesta di emissione di fatture elettroniche contenga l'ambiente in cui il componente aggiuntivo Fatturazione elettronica può determinare quale funzione di fatturazione elettronica deve elaborare la richiesta.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Configurare le fattura elettroniche in RCS](e-invoicing-configuration-rcs.md)
- [Emissione di fatture elettroniche in Finance e Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]