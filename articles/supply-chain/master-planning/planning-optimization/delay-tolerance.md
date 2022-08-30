---
title: Tolleranza di ritardo (giorni negativi)
description: Questo articolo fornisce informazioni sul calcolo della tolleranza di ritardo e su come influisce sulla creazione degli ordini pianificati in Ottimizzazione pianificazione.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: fa4d2d1506546cacf5f9a7ec936f17601c5727d2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335377"
---
# <a name="delay-tolerance-negative-days"></a>Tolleranza di ritardo (giorni negativi)

[!include [banner](../../includes/banner.md)]

La funzionalità di tolleranza di ritardo consente a Ottimizzazione pianificazione di considerare il valore **Giorni negativi** impostato per i gruppi di copertura, la copertura degli articoli e/o i piani generali. Viene utilizzata per estendere il periodo di tolleranza di ritardo applicato durante la pianificazione generale. In questo modo, è possibile evitare di creare nuovi ordini di fornitura se la fornitura esistente è in grado di coprire la domanda con un breve ritardo. Lo scopo della funzionalità è determinare se ha senso creare un nuovo ordine di fornitura per una determinata domanda.

## <a name="turn-delay-tolerance-features-on-or-off"></a>Attivare o disattivare le funzionalità di tolleranza di ritardo

Per rendere disponibile la funzionalità di tolleranza di ritardo nel sistema, vai a [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attiva le seguenti funzionalità:

- *Giorni negativi per l'ottimizzazione della pianificazione*: questa funzionalità abilita le impostazioni dei giorni negativi per i gruppi di copertura e la copertura degli articoli. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è obbligatoria e non può essere disattivata.
- *Automazione dell'offerta Produzione su ordine*: questa funzionalità abilita le impostazioni dei giorni negativi per i piani generali (per ulteriori informazioni, vedi [Automazione dell'offerta Produzione su ordine](../make-to-order-supply-automation.md)).

## <a name="delay-tolerance-in-planning-optimization"></a>Tolleranza di ritardo nell'ottimizzazione della pianificazione

La tolleranza di ritardo rappresenta il numero di giorni oltre il lead time che si è disposti ad aspettare prima di ordinare un nuovo rifornimento quando la fornitura esistente è già pianificata. La tolleranza di ritardo viene definita utilizzando i giorni di calendario, non i giorni lavorativi.

Al momento della pianificazione generale, quando il sistema calcola la tolleranza di ritardo, considera l'impostazione **Giorni negativi**. Puoi impostare il valore **Giorni negativi** nella pagina **Gruppi di copertura**, **Copertura articoli** o **Piani generali**. Se i giorni negativi vengono assegnati a più livelli, il sistema applica la seguente gerarchia per decidere quale impostazione utilizzare:

- Se i giorni negativi sono abilitati nella pagina **Piani generali**, tale impostazione ha la precedenza su tutte le altre impostazioni dei giorni negativi quando viene eseguito il piano.
- Se i giorni negativi sono configurati nella pagina **Copertura articoli**, tale impostazione ha la precedenza sull'impostazione del gruppo di copertura.
- I giorni negativi configurati nella pagina **Gruppi di copertura** si applicano solo se non sono stati configurati giorni negativi per un articolo o un piano pertinente.

Il sistema collega il calcolo della tolleranza di ritardo alla *prima data di rifornimento*, che equivale alla data corrente più il lead time. La tolleranza di ritardo viene calcolata utilizzando la seguente formula, dove *max()* trova il maggiore tra due valori:

*max(prima data di rifornimento, data di scadenza della domanda)* – *Data di scadenza della domanda* + *Giorni negativi*

Questa formula garantisce che la pianificazione generale non crei nuovi ordini di fornitura quando esiste una fornitura sufficiente durante il lead time del prodotto.

> [!NOTE]
> Il calcolo della tolleranza di ritardo in Ottimizzazione pianificazione utilizza sempre il calcolo dinamico dei giorni negativi dalla pianificazione generale incorporata. L'impostazione **Usa giorni negativi dinamici** nella pagina **Parametri di pianificazione generale** non ha alcun effetto su questo comportamento.

Se la fornitura esistente implica un ritardo della domanda inferiore o uguale alla tolleranza di ritardo calcolata, l'ottimizzazione della pianificazione associa la fornitura esistente alla domanda. In alcuni casi, è meglio ritardare la domanda piuttosto che finire con un eccesso di offerta.

Le seguenti sottosezioni forniscono esempi che mostrano come la tolleranza di ritardo influisca sulla creazione di ordini pianificati in Ottimizzazione pianificazione.

### <a name="example-1"></a>Esempio 1

Un prodotto ha la seguente configurazione:

- **Lead time:** *10*
- **Giorni negativi:** *2*

Per il prodotto esistono la domanda e l'offerta seguenti:

- **Domanda per oggi:** Un ordine di vendita per una quantità di 10
- **Fornitura in 12 giorni:** Un ordine di acquisto per una quantità di 10

La fornitura esistente può coprire la domanda entro 12 giorni e tale periodo equivale alla tolleranza di ritardo. Pertanto, quando viene eseguita la pianificazione generale, non vengono creati ordini pianificati.

### <a name="example-2"></a>Esempio 2

Un prodotto ha la seguente configurazione:

- **Lead time:** *10*
- **Giorni negativi:** *0*

Per il prodotto esistono la domanda e l'offerta seguenti:

- **Domanda per oggi:** Un ordine di vendita per una quantità di 10
- **Fornitura in 12 giorni:** Un ordine di acquisto per una quantità di 10

L'offerta esistente può coprire la domanda solo dopo 12 giorni. Tuttavia, la tolleranza di ritardo è di 10 giorni. Pertanto, quando viene eseguita la pianificazione generale, viene creato un ordine pianificato per una quantità pari a 10.

### <a name="example-3"></a>Esempio 3

Un prodotto ha la seguente configurazione:

- **Lead time:** *10*
- **Giorni negativi:** *2*

Per il prodotto esistono la domanda e l'offerta seguenti:

- **Domanda tra 11 giorni oggi:** Un ordine di vendita per una quantità di 10
- **Fornitura in 14 giorni:** Un ordine di acquisto per una quantità di 10

L'offerta esistente può coprire la domanda solo dopo tre giorni. Tuttavia, la tolleranza di ritardo è di due giorni. In questo caso, la tolleranza di ritardo include solo i due giorni negativi. La data della domanda non è inclusa perché è successiva al lead time del prodotto. Pertanto, quando viene eseguita la pianificazione generale, viene creato un ordine pianificato per una quantità pari a 10.
