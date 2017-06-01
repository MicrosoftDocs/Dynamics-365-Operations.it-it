---
title: Definire le comunicazioni del canale di vendita al dettaglio (Commerce Data Exchange)
description: Questo articolo fornisce una panoramica di Commerce Data Exchange e dei relativi componenti. Descrive il ruolo di ciascun componente nel trasferimento dei dati tra Microsoft Dynamics 365 for Operations e i canali di vendita al dettaglio.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: ba1bb54a29250a2bb59622ee4391b64ac455af33
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Definire le comunicazioni del canale di vendita al dettaglio (Commerce Data Exchange)

[!include[banner](../includes/banner.md)]


Questo articolo fornisce una panoramica di Commerce Data Exchange e dei relativi componenti. Descrive il ruolo di ciascun componente nel trasferimento dei dati tra Microsoft Dynamics 365 for Operations e i canali di vendita al dettaglio.

<a name="overview"></a>Panoramica
--------

Commerce Data Exchange è un sistema che trasferisce i dati tra Microsoft Dynamics 365 for Operations e canali di vendita al dettaglio, ad esempio i negozi online o i punti vendita fisici. Il database in cui vengono archiviati i dati per un canale di vendita al dettaglio è separato dal database di Microsoft Dynamics 365 for Operations. Il database del canale contiene solo i dati necessari per le transazioni al dettaglio. I dati master sono configurati in Dynamics 365 for Operations e vengono distribuiti ai canali. I dati transazionali vengono creati nel POS o nel negozio online e quindi vengono caricati in Dynamics 365 for Operations. La distribuzione di dati è asincrona. Ovvero il processo di raccolta e pacchettizzazione dei dati all'origine viene effettuata separatamente dal processo di ricezione e applicazione dei dati alla destinazione. Per alcuni scenari, quali la ricerca di prezzi e scorte, i dati devono essere recuperati in tempo reale. Per supportare questi scenari, Commerce Data Exchange include inoltre un servizio che abilita la comunicazione in tempo reale tra Dynamics 365 for Operations e un canale. 

[![updated-retail-graphic](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## <a name="async-service"></a>Async Service
Il rilevamento modifiche di Microsoft SQL Server nel database di Dynamics 365 for Operations viene utilizzato per determinare le modifiche di dati che devono essere inviate ai canali. In base alla programmazione di distribuzione, Dynamics 365 for Operations inserisce questi dati in pacchetti e li salva nello spazio di archiviazione centrale (archiviazione BLOB di Azure). Un processo batch separato utilizza la libreria Commerce Data Exchange: Async Client per inserire il pacchetto dati nel database del canale. 

[![Async Service](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Retail scheduler

I processi Retail scheduler sono il meccanismo per la distribuzione dei dati dalle e alle ubicazioni. I processi sono costituiti da processi secondari, che specificano le tabelle e i campi di tabella che contengono i dati da distribuire. Dynamics 365 for Operations include processi e processi secondari di Retail scheduler predefiniti che soddisfano i requisiti di replica della maggior parte delle organizzazioni. Vengono creati i seguenti tipi di processi predefiniti:

-   **Processi di download**: i processi di download inviano i dati modificati da Dynamics 365 for Operations ai database di canale. Le modifiche ai record vengono tracciate tramite il rilevamento delle modifiche di SQL Server.
-   **Processi di caricamento (processi P)**: i processi di caricamento effettuano il pull delle transazioni di vendita da un canale nel database di Dynamics 365 for Operations. I processi P caricano i dati in modo incrementale. Quando viene eseguito un processo P, la libreria Async Client controlla il contatore di replica per i record che sono già stati ricevuti da un'ubicazione. Un record viene caricato solo se il relativo contatore di replica è maggiore del valore più grande trovato. I processi P non aggiornano i dati caricati in precedenza.

La programmazione di distribuzione viene utilizzata per eseguire il trasferimento dei dati, manualmente o tramite la programmazione di un processo batch in Dynamics 365 for Operations. La programmazione di distribuzione può contenere uno o più gruppi di dati del canale e uno o più processi Retail scheduler.

## <a name="realtime-service"></a>Real-time Service
Commerce Data Exchange: Real-time Service è un servizio integrato che consente la comunicazione in tempo reale tra Dynamics 365 for Operations e i canali di vendita al dettaglio. Real-time Service consente ai singoli computer POS e ai negozi online di recuperare dati specifici da Dynamics 365 for Operations in tempo reale. Sebbene la maggior parte delle operazioni principali possa essere eseguita nel database del canale locale, i seguenti scenari richiedono l'accesso diretto ai dati archiviati in Dynamics 365 for Operations:

-   Emissione e riscatto di gift card.
-   Riscatto di fedeltà punti programma fedeltà.
-   Emissione e riscatto di note di credito.
-   Creazione o aggiornamento di record cliente.
-   Creazione, aggiornamento e completamento di ordini cliente.
-   Ricezione di scorte a fronte di un ordine fornitore o un ordine di trasferimento.
-   Esecuzione di conteggi scorte.
-   Recupero di transazioni di vendita tra gli archivi e completamento delle transazioni di reso.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Viene creato un profilo Real-time Service predefinito.




