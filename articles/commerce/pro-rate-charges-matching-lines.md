---
title: Spese intestazione con ripartizione proporzionale in righe di vendita corrispondenti
description: In questo argomento vengono descritte le funzionalità aggiuntive per calcolare e applicare le spese automatiche per gli ordini dei canali di commercio utilizzando le funzionalità di addebito automatico avanzato.
author: hhaines
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 22939e8fd63a355effecf0c16fecd20377faa3a6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791056"
---
# <a name="prorate-header-charges-to-matching-sales-lines"></a>Spese intestazione con ripartizione proporzionale in righe di vendita corrispondenti


[!include [banner](includes/banner.md)]

In questo argomento vengono descritte le funzionalità per il raggruppamento delle spese automatiche a livello di intestazione e la ripartizione proporzionale delle stesse nelle righe di vendita di commercio. Questa funzionalità è disponibile per le transazioni create nel POS in Retail versione 10.0.1 e le vendite create in una call center in Retail versione 10.0.2.

Questa funzionalità è disponibile solo se le funzionalità di [addebito automatico avanzato](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges) sono abilitate utilizzando l'opzione nella pagina **Parametri di commercio**. Inoltre, il metodo di calcolo aggiornato per le spese automatiche può essere applicato solo agli ordini cliente creati tramite i canali di commercio (il POS, un call center e la piattaforma e-commerce di Dynamics).

Questa nuova funzionalità fornisce alle organizzazioni una maggiore flessibilità nel modo in cui le spese automatiche a livello di intestazione vengono calcolate e applicate per le transazioni di vendita.

Nelle versioni dell'app precedenti alla versione 10.0.1, gli addebiti automatici a livello di intestazione con una modalità di relazione di consegna specifica vengono calcolati solo quando esiste una corrispondenza con la modalità di consegna definita nell'intestazione dell'ordini cliente.

Ad esempio, le spese automatiche a livello di intestazione sono definite per la modalità di consegna **99** e la modalità di consegna **11**. Un ordine cliente viene creato e la modalità di consegna **99** viene definita nell'intestazione dell'ordine. Tuttavia, alcune delle righe di vendita vengono impostate in modo che siano spedite utilizzando la modalità di consegna **11**. In questo caso, solo le spese a livello di intestazione relative alla modalità di consegna **99** vengono considerate e applicate all'ordine cliente.

In Commerce, le spese a livello di intestazione hanno una funzionalità che consente di definire una [configurazione di spese a livelli](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery) basata sul valore dell'ordine. Ad esempio, se il valore dell'ordine è compreso tra $50,00 e $200,00, un'organizzazione potrebbe addebitare delle spese trasporto di $5,00. Tuttavia, se il valore dell'ordine è compreso tra $200,01 e $500,00, le spese di trasporto potrebbero essere di $4,00.

Alcune organizzazioni vogliono usufruire dei vantaggi derivanti dal calcolo delle spese a livelli fornito con le spese a livello di intestazione. Tuttavia, negli scenari che includono modalità di consegna miste, vogliono anche assicurarsi che le spese calcolate siano basate su una corrispondenza con la modalità di consegna definita in ciascuna riga di vendita.

È ora possibile configurare le spese automatiche a livello di intestazione di modo che tutte le modalità di consegna dell'ordine siano considerate quando le spese vengono calcolate. Questa funzionalità richiede una logica di calcolo più complessa per calcolare le spese a livello di intestazione. La logica raggruppa tutti gli articoli che devono essere spediti utilizzando la stessa modalità di consegna e gestisce quel gruppo come gruppo di calcolo per gli articoli quando calcola le spese automatiche a livello di intestazione. Per gli articoli con la stessa modalità di consegna, le spese automatiche vengono calcolate in base al valore di vendita combinato degli articoli. In questo modo, viene determinato il livello di spese automatiche appropriato.

Dopo aver ottenuto le spese automatiche a livello di intestazione per le righe di vendita spedite utilizzando la stessa modalità di consegna, le spese calcolate vengono ripartite proporzionalmente a livello delle righe di vendita. Poiché queste spese sono a livello di riga e non sono mantenute a livello di intestazione, un collegamento più specifico viene creato tra l'articolo e il valore spese calcolato per lo stesso. Questo comportamento può risultare utile in scenari di reso parziale, dove un'organizzazione desidera rimborsare solo parte delle spese quando solo alcuni articoli vengono restituiti.

## <a name="scenarios"></a>Scenari

I due seguenti scenari di esempio illustrano come tali spese vengono calcolate quando la nuova funzionalità è utilizzata e quando non è utilizzata.

### <a name="scenario-1"></a>Scenario 1

Questo scenario illustra il comportamento quando l'opzione **Ripartisci automaticamente in righe di vendita corrispondenti** è impostata su **No** nell'impostazione delle spese automatiche (il comportamento è equivalente al comportamento delle spese a livello di intestazione nelle versioni dell'app antecedenti alla versione 10.0.1).

In questo scenario, l'organizzazione ha definito le spese a livello di intestazione per la relazione tra modalità di consegna **99** e la relazione tra modalità di consegna **11**. Nessuna spesa automatica è configurata per la modalità di consegna **21**.

![Spese automatiche per la modalità di consegna 99 quando la ripartizione automatica nelle righe corrispondenti è disattivata](media/99_disabled.png)

![Spese automatiche per la modalità di consegna 11 quando la ripartizione automatica nelle righe corrispondenti è disattivata](media/11_disabled.png)

Un ordine cliente viene creato nel call center e la modalità di consegna è impostata su **99**. Questo ordine contiene cinque articoli. Due righe dell'ordine sono state configurate per utilizzare la modalità di consegna **99**, due righe sono state configurate per utilizzare la modalità di consegna **11** e una riga è stata configurata per l'utilizzo della modalità di consegna **21**, come illustrato nella seguente tabella.

| Articolo  | Quantità riga | Modalità di consegna | Prezzo unitario |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | $10            |
| 81332 | 1             | 99            | $50            |
| 81333 | 2             | 11            | $30            |
| 81334 | 3             | 99            | $10            |
| 81334 | 3             | 21            | $5             |

In questo scenario, l'intero ordine viene valutato rispetto alla tabella delle spese automatiche per la modalità di consegna **99**. Il totale complessivo di tutte le righe di vendita viene utilizzato per determinare un livello corrispondente nella configurazione delle spese automatiche e queste spese vengono applicate a livello di intestazione dell'ordine. In questo esempio, il totale dell'ordine è $165,00 e le spese di trasporto di $15,00 sono applicate all'intestazione dell'ordine. Le spese automatiche configurate per la modalità di consegna **11** non sono applicate o non esiste nessun riferimento alle stesse.

In questo scenario, se un cliente restituisce alcuni degli articoli nell'ordine e se il [codice spese è stato configurato di modo che venga eseguito un rimborso](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges#setup-and-configuration-2), le spese totali a livello di intestazione vengono sistematicamente applicate al rimborso, anche se solo alcuni degli articoli vengono restituiti.

### <a name="scenario-2"></a>Scenario 2

In questo scenario, le spese a livello di intestazione sono definite per la relazione tra modalità di consegna **99** e la relazione tra modalità di consegna **11**. Tuttavia, l'opzione **Ripartisci automaticamente in righe di vendita corrispondenti** è impostata su **Sì** per queste tabelle di spese automatiche.

![Spese automatiche per la modalità di consegna 99 quando la ripartizione automatica nelle righe corrispondenti è attivata](media/99_enabled.png)

![Spese automatiche per la modalità di consegna 11 quando la ripartizione automatica nelle righe corrispondenti è attivata](media/11_enabled.png)

Questo scenario utilizza lo stesso ordine cliente contenente cinque righe. La modalità di consegna nell'intestazione dell'ordine è impostata su **99**, ma la modalità di consegna per ogni articolo dell'ordine cliente è configurata come illustrato nella seguente tabella.

| Articolo  | Quantità riga | Modalità di consegna | Prezzo unitario |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | $10            |
| 81332 | 1             | 99            | $50            |
| 81333 | 2             | 11            | $30            |
| 81334 | 3             | 99            | $10            |
| 81334 | 3             | 21            | $5             |

Poiché la configurazione delle spese automatiche è impostata per una ripartizione proporzionale nelle righe di vendita corrispondenti, il sistema esegue le seguenti operazioni di calcolo.

1. Tutti gli articoli con la stessa modalità di consegna vengono raggruppati e il sistema calcola il valore prodotto totale degli articoli nel gruppo.

    **Modalità di consegna 11**

    - Articolo 81331, quantità 1 = $10
    - Articolo 81333, quantità 2 = $60 netto ($30 unitario)
    - **Valore prodotto totale per modalità di consegna 11 = $70**

    **Modalità di consegna 99**

    - Articolo 81332, quantità 1 = $50
    - Articolo 81334, quantità 3 = $30 netto
    - **Valore prodotto totale per modalità di consegna 99 = $80**

    **Modalità di consegna 21**

    - Articolo 81334, quantità 3 = $15 netto
    - **Valore prodotto totale per modalità di consegna 21 = $15**

2. Il sistema cerca la configurazione delle spese automatiche a livello di intestazione che corrispondono alle impostazioni relative al cliente e alla modalità di consegna per ciascun gruppo di articoli. Se la configurazione viene trovata, il sistema esamina la configurazione a livelli per trovare le spese che devono essere applicate, in base al valore prodotto totale degli articoli nel gruppo di modalità di consegna.

    **Modalità di consegna 11**

    - Valore prodotto totale = $70
    - **Valore spese = $7**

    **Modalità di consegna 99**

    - Valore prodotto totale = $80
    - **Valore spese = $15**

    **Modalità di consegna 21**

    - Valore prodotto totale = $15
    - **Valore spese = $0** (nessuna spesa automatica è stata configurata per questa combinazione di un cliente e di una modalità di consegna).

    ![Spese della modalità di consegna 11 nel livello evidenziato](media/step2mode11.png)

    ![Spese della modalità di consegna 99 nel livello evidenziato](media/step2mode99.png)

3. Il sistema calcola il valore spese da applicare a ogni riga, in base alla logica di ripartizione che considera il valore proporzionale della riga in relazione al valore prodotto totale del gruppo.

    **Modalità di consegna 11**

    - Valore spese = $7
    - Valore prodotto gruppo = $70
    - Valore riga 1 = $10 (= 14,2857 percento del valore gruppo)
    - Valore riga 3 = $60 (= 85,7143 percento del valore gruppo)
    - **Spese riga per riga 1 = $1**
    - **Spese riga per riga 3 = $6**

    **Modalità di consegna 99**

    - Valore spese = $15
    - Valore prodotto gruppo = $80
    - Valore riga 2 = $50 (= 62,5 percento del valore gruppo)
    - Valore riga 4 = $30 (= 37,5 percento del valore gruppo)
    - **Spese riga per riga 2 = $9,38**
    - **Spese riga per riga 4 = $5,62**

    **Modalità di consegna 21**

    - Valore spese = $0
    - Valore prodotto gruppo = $15
    - Valore riga 5 = $15 (= 100 percento del valore gruppo)
    - **Spese riga per riga 5 = $0**

Pertanto, per questo esempio, all'articolo 81334 verranno assegnate delle spese di trasporto di $5,62. È possibile visualizzare tali spese nella pagina **Gestisci spese** per la riga di vendita. L'illustrazione seguente mostra questa pagina per l'articolo 81334.

![Spese ripartite proporzionalmente nella riga di vendita per l'articolo 81334](media/proratedlinecharge.png)

Quando questo metodo di calcolo viene utilizzato in uno scenario di reso parziale, se il codice spese è rimborsabile, solo la parte delle spese assegnata a tale riga verrà rimborsata quando l'articolo viene restituito.

## <a name="additional-resources"></a>Risorse aggiuntive

[Addebiti automatici avanzati omnicanale](omni-auto-charges.md)

[Abilitare e configurare addebiti automatici per canale](auto-charges-by-channel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]