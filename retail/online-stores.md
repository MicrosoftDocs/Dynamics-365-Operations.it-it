---
title: Panoramica sui negozi online
description: Questo articolo fornisce informazioni sui negozi al dettaglio online e su come impostarli in Microsoft Dynamics 365 for Operations.
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16161
ms.assetid: 646d560c-f856-4701-b4ca-44e357ef09b8
ms.search.region: Global
ms.search.industry: Retail
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 40fbf8b4fdfed32dd67013b6b21cc2c8ee3d31e6
ms.lasthandoff: 03/31/2017


---

# <a name="online-store-overview"></a>Panoramica sui negozi online

Questo articolo fornisce informazioni sui negozi al dettaglio online e su come impostarli in Microsoft Dynamics 365 for Operations.

Vendita al dettaglio e commercio in Microsoft Dynamics 365 for Operations supporta più canali di vendita al dettaglio. Questi canali di vendita al dettaglio includono negozi online, call center e punti vendita al dettaglio, definiti anche punti vendita fisici. I negozi online offrono a un rivenditore una presenza online in modo che i clienti possano acquistare i prodotti anche tramite il negozio online, oltre che nei punti vendita fisici. I clienti che acquistano prodotti dal negozio online possono farseli spedire o prelevarli da un punto vendita al dettaglio locale. È possibile creare un negozio online nel client Dynamics 365 for Operations. Il negozio online viene quindi pubblicato in un negozio online di terze parti che è integrato con Dynamics 365 for Operations. Il negozio online di terze parti serve come vetrina (interfaccia utente) per il negozio online e offre una scelta di funzionalità CMS (sistema di gestione clienti) e di interfaccia utente. Diverse integrazioni di questo tipo sono disponibili per Dynamics 365 for Operations. Le proprietà definite per il negozio online determinano il comportamento del negozio online. Ad esempio, è possibile definire la gerarchia di categorie di navigazione in Dynamics 365 for Operations e assegnarla al negozio online. Quando si pubblica il negozio online nel negozio online di terze parti, la gerarchia di categorie di navigazione viene visualizzata nella versione online del punto vendita. Gli acquirenti utilizzano la gerarchia di categorie di navigazione per esplorare il negozio online e per cercare i prodotti. Per creare un negozio online, è necessario impostare i componenti che consentono l'elaborazione delle transazioni per il punto vendita. Ad esempio, è necessario aggiungere assortimenti, applicare attributi e impostare metodi di pagamento e di spedizione. È inoltre possibile definire i prezzi, le promozioni, gli sconti, gli accordi commerciali e le condizioni di spedizione specifici del negozio online. Dopo aver pubblicato il negozio online nel negozio online di terze parti, è possibile creare cataloghi di prodotti al dettaglio per il negozio online. I prodotti del catalogo diventano elenchi di prodotti nel negozio online. Quando un acquirente acquista prodotti dal negozio online, le scorte disponibili vengono aggiornate e sincronizzate nel client. Inoltre, gli ordini cliente vengono generati per gli acquisti e inviati al client per l'esecuzione e l'elaborazione dell'ordine.

## <a name="set-up-an-online-store"></a>Impostare un negozio online
Per impostare un negozio online, è necessario completare le attività indicate di seguito.

1.  Creare il negozio online.
2.  Aggiungere il negozio online alle gerarchie organizzative appropriate.
3.  Aggiungere gli assortimenti che includono i prodotti disponibili nel negozio online.
4.  Assegnare o creare gruppi di prezzi per il negozio online.
5.  Impostare le modalità di consegna disponibili per il negozio online.
6.  Assegnare i metodi di pagamento che vengono accettati dal negozio online.
7.  Se si consente agli acquirenti di ordinare i prodotti online e di prelevarli in un punto vendita locale, assegnare gruppi di localizzatori di punti vendita al negozio online.
8.  Assegnare attributi per canali, prodotti e ordini cliente al negozio online. Gli attributi del canale si applicano all'intero negozio online, gli attributi del prodotto si applicano ai prodotti che vengono offerti nel negozio online e gli attributi degli ordini cliente si applicano agli ordini cliente generati dal negozio online.
9.  Mappare gli attributi per definire le proprietà che determinano il comportamento degli attributi nel negozio online. Ad esempio, è possibile definire gli attributi come obbligatori o ricercabili.
10. Pubblicare il negozio online per generarne la struttura nel negozio online di terze parti di propria scelta. **Importante:** Prima di pubblicare il negozio online, è necessario impostare un percorso di distribuzione per lo stesso.

## <a name="retail-channel-navigation-hierarchies"></a>Gerarchie di navigazione nei canali di vendita al dettaglio
Prima di creare un negozio online, è necessario definire la gerarchia di navigazione nei canali di vendita al dettaglio da utilizzare nel negozio online. La gerarchia di navigazione nei canali di vendita al dettaglio rappresenta la gerarchia di categorie visualizzata nel negozio online dopo la pubblicazione del punto vendita. Quando si pubblicano i cataloghi di prodotti al dettaglio nel negozio online, i prodotti presenti nel catalogo vengono mappati alle categorie della gerarchia di navigazione nei canali di vendita al dettaglio. Gli acquirenti usano quindi la gerarchia per esplorare il negozio online.

## <a name="organization-hierarchies"></a>Gerarchie organizzative
Le gerarchie organizzative vengono utilizzate per strutturare canali di vendita al dettaglio. Le gerarchie organizzative rappresentano i rapporti tra le organizzazioni che fanno parte dell'azienda. Quando si impostano i negozi online, è possibile aggiungerli a una gerarchia organizzativa. I punti vendita, quindi, condividono i dati utilizzati per assortimenti, rifornimento e dichiarazione. Quando si crea una gerarchia organizzativa, è necessario assegnarle uno scopo. Lo scopo indica la modalità con cui viene utilizzata la gerarchia nella struttura aziendale. È possibile creare una gerarchia organizzativa per le operazioni del punto vendita e utilizzare tale gerarchia per assortimenti, rifornimento e reporting. In alternativa, è possibile creare una gerarchia organizzativa separata per ogni scopo. È inoltre possibile creare più gerarchie con lo stesso scopo e assegnare un canale separato a ognuna di esse. Se si intende pubblicare cataloghi di prodotti al dettaglio nel negozio online, è necessario almeno aggiungere il negozio online a una gerarchia organizzativa per gli assortimenti. I prodotti di un catalogo vengono selezionati dagli assortimenti assegnati al negozio online. Quando il catalogo viene pubblicato, il processo di pubblicazione confronta le date di validità per l'assortimento assegnato al negozio online ai prodotti inclusi nel catalogo per determinare i prodotti da rendere disponibili nel negozio online.


