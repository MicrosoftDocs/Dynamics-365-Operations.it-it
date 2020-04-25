---
title: Impostazioni ordine predefinite per le dimensioni e varianti prodotto
description: Le impostazioni ordine predefinite definiscono il sito e il magazzino in cui gli articoli saranno prelevati o archiviati, le quantità minima, massima, multipla e standard che verrà utilizzata per il commercio o la gestione degli articoli, i lead time, il flag di interruzione e il metodo delle promesse ordine.
author: roxanadiaconu
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 46b1efb274c9f54f27c26884dc18fc4a317786be
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211578"
---
# <a name="default-order-settings-for-dimensions-and-product-variants"></a>Impostazioni ordine predefinite per dimensioni e varianti prodotto

[!include [banner](../includes/banner.md)]

Le impostazioni ordine predefinite in Dynamics 365 Supply Chain Management definiscono il sito e il magazzino in cui gli articoli saranno prelevati o archiviati, le quantità minima, massima, multipla e standard che verranno utilizzate per il commercio o la gestione degli articoli, i lead time, il flag di interruzione e il metodo delle promesse ordine. Le impostazioni ordine predefinite vengono utilizzate durante la creazione di ordini fornitore, ordini cliente, ordini di trasferimento, giornali di registrazione magazzino e durante la pianificazione generale per la generazione degli ordini pianificati. Le impostazioni ordine predefinite possono essere specifiche dell'articolo, del sito, della variante prodotto o della dimensioni prodotto.

È possibile definire le impostazioni ordine predefinite nella pagina **Impostazioni ordine predefinite**. Per visualizzare questa pagina, andare a **Gestione informazioni sul prodotto** &gt; **Prodotti** &gt; **Prodotti rilasciati** &gt; **selezionare un prodotto rilasciato** &gt; nel riquadro azioni **Piano** o **Gestione articoli** &gt; **Impostazioni ordine** &gt; **Impostazioni ordine predefinite**.

## <a name="default-order-settings"></a>Impostazioni ordine predefinite
Sono disponibili tre tipi di impostazioni ordine predefinite per acquisti, vendite e scorte. Le impostazioni ordine predefinite per gli acquisti vengono utilizzate durante la creazione di:

-   Righe ordine fornitore
-   Righe contratto di acquisto
-   Righe richiesta di offerta
-   Righe richiesta di acquisto
-   Righe di rifornimento spedizione
-   Ordini fornitore pianificati

Le impostazioni ordine predefinite per le vendite vengono utilizzate durante la creazione di:

-   Righe ordine cliente
-   Righe contratto di vendita
-   Righe di offerta di vendita
-   Righe di ordine di reso e righe di sostituzione articolo
-   Righe di previsione della domanda

Le impostazioni ordine di vendita predefinite vengono utilizzate anche durante la creazione di:

-   Richieste articoli nel progetto
-   Richieste articoli degli ordini di assistenza

Le impostazioni ordine predefinite per le scorte vengono utilizzate durante la creazione di:

-   Giornali di registrazione magazzino
-   Ordini di trasferimento
-   Ordini trasferimento pianificati

Le impostazioni ordine di magazzino predefinite vengono utilizzate anche durante la creazione di:

-   Ordini di quarantena
-   Ordini di controllo qualità
-   Ordini di produzione
-   Righe DBA
-   Ordini di produzione pianificati

## <a name="full-definition-of-a-released-product"></a>Definizione completa di un prodotto rilasciato
Quando si crea una transazione, è necessario specificare la definizione completa di un prodotto rilasciato nella riga affinché Supply Chain Management tenti di identificare le impostazioni ordine predefinite. La definizione completa del prodotto rilasciato significa che il numero di articolo e tutte le dimensioni prodotto attive, ad esempio configurazione, dimensione, stile e colore, vengono specificati per la transazione. Ad esempio, se si crea manualmente una riga di ordine di acquisto per una variante prodotto rilasciato, è necessario specificare tutte le dimensioni prodotto richieste prima che il sito, il magazzino, le quantità e il lead time vengano visualizzati per impostazione predefinita nella riga ordine. 

Non tutti i parametri delle impostazioni ordine predefinite vengono applicati quando si creano le righe giornale di registrazione o ordine. Le quantità e i lead time vengono visualizzati per impostazione predefinita solo al momento opportuno. Ad esempio quando si conteggia una riga giornale di registrazione, solo il sito e il magazzino vengono visualizzati per impostazione predefinita quando la riga viene creata. Ovviamente non viene eseguita nessuna impostazione predefinita di quantità né vengono eseguiti i controlli su multipli e minimi durante la creazione della riga o la registrazione del giornale. 

Il sistema tenta sempre di individuare un sito e un magazzino predefiniti quando viene creata una riga giornale di registrazione o ordine. Il sito non viene sempre visualizzato per impostazione predefinita dalle impostazioni ordine. Se ad esempio si crea un ordine cliente o un ordine fornitore, il sito indicato nell'intestazione dell'ordine viene utilizzato automaticamente nelle righe ordine. Quando si crea una riga DBA, viene utilizzato il sito indicato nell'intestazione della DBA. Dopo avere determinato il sito, questo verrà utilizzato per trovare le impostazioni ordine specifiche del sito che potranno essere utilizzate come impostazioni predefinite per il magazzino. 

Il tipo di ordine predefinito, i lead time di acquisto e di magazzino possono essere ignorati dalle regole di copertura articoli nella pagina **Copertura articoli**. Mentre le impostazioni ordine predefinite non consentono la distinzione tra il lead time di produzione e di trasferimento, le regole di copertura articoli la consentono. Tuttavia, l'impostazione della copertura articoli verrà utilizzata solo da MRP per la creazione di ordini di trasferimento pianificati e di produzione pianificati e non si applica al momento della creazione manuale degli ordini di trasferimento e di produzione. 

## <a name="default-order-settings-rules"></a>Regole delle impostazioni ordine predefinite
È possibile definire le impostazioni ordine predefinite generali e qualsiasi numero di regole delle impostazioni ordine predefinite valide solo per determinati contesti, ad esempio un sito o una specifica dimensione prodotto o una combinazione di dimensioni prodotto. Non è possibile definire le impostazioni ordine specifiche del magazzino.

### <a name="rank-in-default-order-settings"></a>Classificazione delle impostazioni ordine predefinite

Le regole delle impostazioni ordine predefinite vengono classificate. Più alta è la classifica, più importante è la regola, ovvero avrà priorità più alta e verrà utilizzata prima delle regole con classificazioni inferiori. La classificazione delle impostazioni ordine predefinite generali è zero e non può essere modificata. È consentita una sola regola con classificazione zero. Le regole possono avere la stessa classificazione purché le dimensioni applicate siano diverse. Questa opzione è utile per la modellazione delle impostazioni ordine specifiche del sito. Quando una nuova regola di impostazioni ordine predefinite viene creata, i valori relativi ai valori dell'ordine, al flag di interruzione e così via vengono ereditati dalla regola con la classificazione zero, ma possono essere ignorati.

### <a name="default-order-settings-for-released-products"></a>Impostazioni ordine predefinite per prodotti rilasciati

Per prodotti rilasciati specifici, è possibile definire le impostazioni ordine generali o le impostazioni ordine specifiche del sito. Le impostazioni ordine generale hanno sempre la classificazione zero. Se si impostano nuove impostazioni ordine di vendita, acquisto e magazzino insieme contemporaneamente, si consiglia di utilizzare **Visualizzazione dettagli** nella pagina **Impostazioni ordine predefinite**. Per passare alla visualizzazione dettagli, passare al riquadro azioni **Opzioni** &gt; **Opzioni pagina** &gt; **Cambia visualizzazione** &gt; **Visualizzazione dettagli**.

### <a name="site-specific-order-settings"></a>Impostazioni ordine specifiche del sito

Per creare impostazioni ordine specifiche del sito, fare clic su **Nuovo**. In **Visualizzazione dettagli** specificare il sito nel campo **Impostazioni applicabili per** &gt; **Sito**. In **Visualizzazione griglia**, inserire il sito nella colonna **Sito**. La nuova regola ottiene automaticamente un nuovo valore di classificazione maggiore di zero. È possibile creare tutte le regole specifiche del sito necessarie ed è possibile assegnare tutte le regole specifiche del sito alla stessa classificazione per modellarle su un'uguale importanza. 

Nella **Visualizzazione dettagli** non è possibile ottenere la panoramica delle regole create per l'articolo. Attivare il pulsante **Mostra/nascondi elenco** per visualizzare le informazioni generali. Quando una riga di ordine di qualsiasi tipo viene creata e non viene fornito alcun sito, Supply Chain Management cerca una regola senza sito specificato. Questa azione potrebbe aiutare a determinare un sito predefinito nella riga ordine. Questo sito verrà utilizzato per cercare una regola specifica del sito in cui un magazzino predefinito potrebbe essere stato impostato. Il magazzino viene applicato alla riga ordine.

### <a name="specific-order-settings-for-product-dimension"></a>Impostazioni ordine specifiche per la dimensione prodotto

È possibile definire le regole delle impostazioni ordine per qualsiasi dimensione prodotto attiva o combinazione di dimensioni prodotto attive. Se un campo di dimensione prodotto viene lasciato vuoto, la regola viene applicata a tutti i valori della dimensione prodotto. 

Considerare il prodotto di esempio riportato di seguito.

|                                                     |                                         |
|-----------------------------------------------------|-----------------------------------------|
| **Nome prodotto**                                    | Sensore fotoelettrico                    |
| **Numero articolo**                                     | XW56                                    |
| **Configurazione** (utilizzato per definire il tipo di illuminazione) | Luce rossa visibile C1, luce a infrarossi C2 |
| **Stile** (utilizzato per definire la revisione di progettazione)  | R1, R2, R3                              |

Per questo esempio, si supponga che il prodotto venga approvvigionato e non prodotto. Si supponga inoltre che la configurazione C1 sia utilizzata più comunemente, pertanto i lead time sono più brevi. 

Creare le seguenti impostazioni ordine predefinite per modellare questo scenario.

| Classificazione | Sito | Configurazione | Stile | Acquisto - Ignora impostazioni predefinite | Lead time acquisto | Acquisto - Interrotto | Vendita - Ignora impostazioni predefinite | Vendita - Interrotta |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | S1            |       | Sì                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Quando una riga di ordine fornitore o un ordine fornitore pianificato viene creato per XW56, la configurazione C1 indipendentemente dalla revisione o dal sito in cui si trova la riga, il lead time viene considerato 2. Si supponga di tutte le revisioni eccetto R3 vengano interrotte.

È possibile creare le seguenti regole delle impostazioni ordine predefinite.

| Classificazione | Sito | Configurazione | Stile | Acquisto - Ignora impostazioni predefinite | Lead time acquisto | Acquisto - Interrotto | Vendita - Ignora impostazioni predefinite | Vendita - Interrotta |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 20   |      |               | R2    | Sì                                  |                    | Sì                | Sì                               | Sì             |
| 20   |      |               | R1    | Sì                                  |                    | Sì                | Sì                               | Sì             |
| 10   |      | S1            |       | Sì                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Le due regole per l'interruzione delle revisioni precedenti hanno la stessa classificazione nel senso che sono ugualmente importanti. Entrambe hanno una classificazione più alta della regola della configurazione C1 nel senso che hanno priorità sulla regola della configurazione C1. 

In questo esempio viene illustrata la necessità della classificazione. Se si crea un ordine fornitore per la configurazione C1 e la revisione R2, in assenza di classificazione, le due regole definite per R2 e C1 sarebbero ambigue. Per risolvere l'ambiguità, Supply Chain Management cerca tra le regole in ordine decrescente di classificazione e applica la regola prima applicabile. Nell'esempio corrente, se una riga di ordine fornitore viene creata per la configurazione C1 e la revisione R2, l'utente otterrà un messaggio di avviso indicante che l'articolo è in attesa a causa del valore di revisione. Se la classificazione della regola della configurazione fosse stata più alta di quella della revisione, la creazione di una riga ordine fornitore per la configurazione C1 e la revisione R2 avrebbe avuto esito positivo e nessun messaggio di "articolo in attesa" sarebbe stato restituito all'utente. 

Si considerino le seguenti regole delle impostazioni ordine predefinite.

| Classificazione | Sito | Configurazione | Stile | Sito predefinito | Magazzino predefinito | Acquisto - Ignora dimensioni di immagazzinamento predefinite | Magazzino acquisti |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Sì                                            | 22                 |
| 10   |      | S1            |  R2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

Il sistema attraversa il set di regole due volte per determinare il sito e il magazzino. Quando una riga di ordine fornitore viene creata per la configurazione C1, lo stile R2, il sito viene determinato in base alla regola con il livello 10. Il sistema quindi cerca una regola per il sito 2 per determinare un magazzino. La regola 20 viene rilevata e poiché ha una classificazione più alta, il magazzino nella riga ordine fornitore sarà 22 anziché 21. 

Come indicazione generale, le regole specifiche e le regole per le dimensioni più importanti di altre dimensioni ottengono classificazioni più alte, mentre le regole più generiche ottengono classificazioni inferiori. 

La regola con classificazione zero serve da regola di sicurezza. Se non vengono stabilite altre regole, verranno utilizzate le impostazioni ordine predefinite della regola zero. 

Poiché il numero di classificazione è così importante, nel riquadro azioni **Impostazioni ordine predefinite**, sono presenti le funzioni per spostare in una regola verso l'alto o verso il basso e per rinumerare le regole, in modo che siano sempre in incrementi di 10. 

Il numero di regole create per un prodotto rilasciato può essere notevole. Per ottenere un giovamento da ciò che ogni regola ignora e dal perché è necessaria, è consigliabile utilizzare la **Visualizzazione griglia** nella pagina **Impostazioni ordine predefinite**. È possibile abilitare la visualizzazione griglia passando al riquadro azioni **Opzioni** &gt; **Opzioni pagina** &gt; **Cambia visualizzazione** &gt; **Visualizzazione griglia**. Il numero di colonne nella griglia potrebbe essere significativo, soprattutto per le schede vendite e magazzino. Per limitare il numero di colonne visualizzate nella griglia, i gruppi di colonne possono essere nascosti o visualizzati utilizzando i pulsanti del menu **Impostazioni ordine predefinite** &gt; **Visualizzazione di colonna**.

### <a name="specific-order-settings-for-released-product-variant"></a>Impostazioni ordine specifiche per la variante prodotto rilasciato

Se il sistema della regola per le impostazioni ordine predefinite è troppo complicato, è possibile scegliere semplicemente di definire le impostazioni ordine predefinite per ogni variante prodotto. Negli esempi riportati di seguito viene illustrato come verrà cercato il prodotto e i casi descritti in precedenza.

| Classificazione | Sito | Configurazione | Stile | Acquisto - Ignora impostazioni predefinite | Lead time acquisto | Acquisto - Interrotto | Vendita - Ignora impostazioni predefinite | Vendita - Interrotta |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | S2            | R3    | Sì                                  | 5                  |                    |                                   |                 |
| 10   |      | S2            | R2    | Sì                                  | 5                  | Sì                | Sì                               | Sì             |
| 10   |      | S2            | R1    | Sì                                  | 5                  | Sì                | Sì                               | Sì             |
| 10   |      | S1            | R3    | Sì                                  | 2                  |                    |                                   |                 |
| 10   |      | S1            | R2    | Sì                                  | 2                  | Sì                | Sì                               | Sì             |
| 10   |      | S1            | R1    | Sì                                  | 2                  | Sì                | Sì                               | Sì             |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

La classificazione in questo caso non ha grande importanza pertanto è possibile scegliere di nasconderla. Questa soluzione potenzialmente introduce un problema di gestione. Tuttavia, è possibile considerare di utilizzare questa impostazione se si pensa all'integrazione con sistemi di gestione del ciclo di vita del prodotto.



