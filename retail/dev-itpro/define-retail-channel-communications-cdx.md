---
title: Definire le comunicazioni del canale di vendita al dettaglio (Commerce Data Exchange)
description: Questo articolo fornisce una panoramica di Commerce Data Exchange e dei relativi componenti. Descrive la parte ciascun componente che esegue il trasferimento dei dati tra Microsoft Dynamics 365 per le operazioni e i canali al dettaglio.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 29938d962db42a521dd8dc03b8e45e0e34410e4d
ms.openlocfilehash: d3b36ec2a3f859215d93dd7ebf1f1ecfb2731c59
ms.lasthandoff: 03/31/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Definire le comunicazioni del canale di vendita al dettaglio (Commerce Data Exchange)

Questo articolo fornisce una panoramica di Commerce Data Exchange e dei relativi componenti. Descrive la parte ciascun componente che esegue il trasferimento dei dati tra Microsoft Dynamics 365 per le operazioni e i canali al dettaglio.

<a name="overview"></a>Panoramica
--------

Global Trade Data Exchange) è un sistema di trasferire i dati tra Dynamics 365 per le operazioni e i canali al dettaglio, ad esempio i punti vendita in linea o i punti vendita del mattone-e- mortaio. Il database in cui vengono archiviati i dati di un canale al dettaglio viene esclusa da Dynamics 365 per il database delle operazioni. Il database del canale contiene solo i dati necessari per le transazioni al dettaglio. I dati master sono configurati in Dynamics 365 per le operazioni e vengono distribuiti ai canali. I dati transazionali vengono creati nel sistema di (POS) del POS o nel punto vendita in linea e vengono poi caricati in Dynamics 365 per le operazioni. La distribuzione di dati è asincrona. Ovvero il processo di raccolta e pacchettizzazione dei dati all'origine viene effettuata separatamente dal processo di ricezione e applicazione dei dati alla destinazione. Per alcuni scenari, quali la ricerca di prezzi e scorte, i dati devono essere recuperati in tempo reale. Per supportare questi scenari, il commercio Data Exchange) include inoltre un servizio che abilita la comunicazione in tempo reale tra Dynamics 365 per le operazioni e un canale. 

[aggiornato-vendita al dettaglio grafico![(]. /media/updated-retail-graphic.png)](. /media/updated-retail-graphic.png)  

## <a name="async-service"></a>Async Service
La modifica di Microsoft SQL Server nella scheda Dynamics 365 per il database delle operazioni viene utilizzata per determinare le modifiche ai dati che devono essere inviati ai canali. In base a una programmazione di distribuzione, Dynamics 365 per i colli di operazioni che dati e lo consente al punto vendita (archivio centrale azzurrata di chiazza). Un processo batch separato utilizza la libreria Commerce Data Exchange: Async Client per inserire il pacchetto dati nel database del canale. 

[![Async Service](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Retail Scheduler

I processi Retail Scheduler sono il meccanismo per la distribuzione dei dati dalle e alle ubicazioni. I processi sono costituiti da processi secondari, che specificano le tabelle e i campi di tabella che contengono i dati da distribuire. Dynamics 365 per le operazioni include i processi e i processi secondari predefiniti Retail Scheduler che soddisfino i requisiti a livello della maggior parte delle organizzazioni. Vengono creati i seguenti tipi di processi predefiniti:

-   ** I processi di download ** - Processi di download inviare i dati che sono cambiati Dynamics 365 per le operazioni nei database del canale. Le modifiche ai record vengono tracciate tramite il rilevamento delle modifiche di SQL Server.
-   ** Caricare i processi (processi P) - ** l'impostazione delle transazioni di vendita di pull di processi da un canale in Dynamics 365 per il database delle operazioni. I processi P caricano i dati in modo incrementale. Quando viene eseguito un processo P, la libreria Async Client controlla il contatore di replica per i record che sono già stati ricevuti da un'ubicazione. Un record viene caricato solo se il relativo contatore di replica è maggiore del valore più grande trovato. I processi P non aggiornano i dati caricati in precedenza.

La programmazione di distribuzione viene utilizzata per eseguire il trasferimento dei dati, manualmente o di un processo batch in Dynamics 365 per le operazioni. La programmazione di distribuzione può contenere uno o più gruppi di dati del canale e uno o più processi Retail Scheduler.

## <a name="realtime-service"></a>Servizio in tempo reale
Commercio Data Exchange): Il servizio in tempo reale è un servizio integrato che fornisce la comunicazione in tempo reale tra Dynamics 365 per le operazioni e i canali al dettaglio. Il servizio in tempo reale consente ai singoli computer di Retail POS e ai punti vendita nel recupero dei dati specifici da Dynamics 365 per le operazioni in tempo reale. Nella maggior parte delle operazioni chiave possano essere eseguite nel database dei canali locale, gli scenari richiedono l'accesso diretto ai dati archiviati in Dynamics 365 per le operazioni:

-   Emissione e riscatto di gift card.
-   Riscatto di fedeltà punti programma fedeltà.
-   Emissione e riscatto di note di credito.
-   Creazione o aggiornamento di record cliente.
-   Creazione, aggiornamento e completamento di ordini cliente.
-   Ricezione di scorte a fronte di un ordine fornitore o un ordine di trasferimento.
-   Esecuzione di conteggi scorte.
-   Recupero di transazioni di vendita tra gli archivi e completamento delle transazioni di reso.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Un profilo in tempo reale predefinito di assistenza viene creato.


