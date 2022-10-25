---
title: Domande frequenti sulla modalità di creazione di clienti asincroni
description: Questo articolo fornisce risposte alle domande frequenti sulla modalità di creazione di clienti asincroni in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 64c895fb9f3e55f7680759fa72626be6660aa67c
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690204"
---
# <a name="asynchronous-customer-creation-mode-faq"></a>Domande frequenti sulla modalità di creazione di clienti asincroni

[!include [banner](includes/banner.md)]

Questo articolo fornisce risposte alle domande frequenti sulla modalità di creazione di clienti asincroni in Microsoft Dynamics 365 Commerce.

### <a name="why-cant-i-enable-the-enable-editing-customers-in-asynchronous-mode-feature"></a>Perché non posso abilitare la funzionalità "Abilita modifica dei clienti in modalità asincrona"?

Prima di abilitare la funzionalità **Abilita modifica dei clienti in modalità asincrona**, devi abilitare le seguenti funzionalità:

- Miglioramenti delle prestazioni per gli ordini cliente e le transazioni cliente
- Abilita creazione avanzata di clienti asincroni
- Abilita creazione asincrona per gli indirizzi cliente

### <a name="why-do-i-still-see-real-time-service-calls-made-to-commerce-headquarters-after-the-enable-editing-customers-in-asynchronous-mode-feature-is-enabled"></a>Perché vedo ancora le chiamate di servizio in tempo reale effettuate a Commerce headquarters dopo che è stata abilitata la funzionalità "Abilita modifica dei clienti in modalità asincrona"?

Questo problema si verifica quando i processi Commerce Data Exchange (CDX) non sono stati eseguiti per garantire la sincronizzazione dello stato della funzionalità e di altri metadati del canale con il canale. Prima di riprovare lo scenario, assicurati che i seguenti processi CDX siano eseguiti in Commerce headquarters:

- 1110 (Configurazione globale)
- 1010 (Clienti)
- 1070 (Configurazione canale)

I dati memorizzati nella cache in Commerce Scale Unit (CSU) potrebbero non essere riflessi immediatamente in Commerce headquarters dopo l'esecuzione dei processi CDX.

### <a name="why-doesnt-commerce-headquarters-show-customer-creation-or-updates-from-the-point-of-sale-pos-or-e-commerce-channel"></a>Perché Commerce headquarters non mostra la creazione del cliente o gli aggiornamenti dal POS o dal canale di e-commerce?

Assicurati che le seguenti azioni siano state eseguite nell'ordine in cui sono elencate qui.

1. Esegui il processo P CDX in Commerce headquarters per assicurarti che i dati dei clienti asincroni archiviati nelle tabelle **RETAILASYNCCUSTOMERV2**, **RETAILASYNCADDRESSV2**, **RETAILASYNCCUSTOMERCONTACT**, **RETAILASYNCCUSTOMERAFFILIATION** e **RETAILASYNCCUSTOMERATTRIBUTEV2**.
1. Esegui il processo batch **Sincronizza richieste di canale e clienti** in Commerce headquarters. Dopo l'esecuzione riuscita del processo batch, tutti i record che sono stati elaborati correttamente a partire dalle tabelle menzionate in precedenza avranno il campo **OnlineOperationCompleted** impostato su **1**.

### <a name="how-do-i-know-which-customer-management-in-asynchronous-mode-operation-has-failed-and-how-do-i-make-changes-if-they-are-required"></a>Come faccio a sapere quale gestione dei clienti in modalità asincrona ha avuto esito negativo e come posso apportare modifiche se sono necessarie?

Per visualizzare tutte le operazioni di sincronizzazione e il relativo stato di sincronizzazion, in Commerce headquarters, vai a **Commerce and Retail \> Clienti \> Stato di sincronizzazione del cliente**. Per apportare modifiche, modificare un'operazione specifica, aggiornare i campi, seleziona **Salva**, quindi seleziona **Sincronizza** per sincronizzare le modifiche.

