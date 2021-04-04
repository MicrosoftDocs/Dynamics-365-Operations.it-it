---
title: Moduli Costo sbarcato e Gestione trasporto
description: Microsoft Dynamics 365 Supply Chain Management fornisce due diversi moduli per il trasporto, Gestione trasporto (TMS) e Costo sbarcato. Questo argomento riassume le funzionalità che i due moduli hanno in comune e ne evidenzia le differenze.
author: sherry-zheng
manager: tfehr
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9349537754d7e6fd0e278c55d5d762267953800c
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500720"
---
# <a name="landed-cost-vs-transportation-management"></a>Moduli Costo sbarcato e Gestione trasporto

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Microsoft Dynamics 365 Supply Chain Management fornisce due diversi moduli per il trasporto: **Gestione trasporto** (TMS) e **Costo sbarcato**. Questo argomento riassume le funzionalità che i due moduli hanno in comune e ne evidenzia le differenze. È possibile utilizzare queste informazioni per decidere quale modulo è più appropriato per le proprie pratiche aziendali. In effetti, alcune pratiche aziendali funzionano meglio con TMS, mentre altre funzionano meglio con Costo sbarcato. Quindi, a seconda dei requisiti aziendali, potresti scegliere di utilizzare esclusivamente un modulo oppure combinare i due moduli.

Questo argomento non fornisce una recensione completa di tutte le funzionalità di entrambi i moduli. Evidenzia soltanto le funzionalità disponibili relative al trasporto di merci da un fornitore al magazzino della tua azienda, dove possono essere utilizzate.

## <a name="terminology-reference-data-and-reporting-differences"></a>Differenze relative a terminologia, dati di riferimento e report

### <a name="terminology-comparison"></a>Confronto terminologico

TMS e Costo sbarcato utilizzano termini diversi per concetti simili. La tabella seguente riassume questi termini e il loro utilizzo nei due moduli.

| Termine di TMS | Termine di Costo sbarcato | Note |
|----------|------------------|-------|
| **Carico**<p>Un *carico* è una raccolta di spedizioni trasportate simultaneamente sulla stessa unità di trasporto (ad esempio un camion o una nave). I carichi possono essere in entrata o in uscita.</p> | **Viaggio**<p>In genere, un *viaggio* è una singola imbarcazione che viaggia lungo un unico *percorso*. Un viaggio può contenere più *contenitori di spedizione* e può anche includere ordini in entrata di diverse persone giuridiche dell'organizzazione. I viaggi possono essere solo in entrata.</p> | Anche TMS usa il termine *numero di viaggio*, che fa riferimento a un campo di informazioni in cui è possibile inserire un identificatore. Tuttavia, nessuna funzionalità è associata al campo di TMS e non è correlata al concetto di *viaggio* in Costo sbarcato. |
| **Itinerario**<p>Un *itinerario* è il percorso fisico di un trasporto dall'origine alla destinazione.</p> | **Percorso**<p>Un *percorso* è il percorso fisico di un trasporto dall'origine alla destinazione. Ogni viaggio deve essere assegnato a un percorso.</p> | |
| **Segmenti di itinerario**<p>Un itinerario può avere più *segmenti di itinerario*, ognuno dei quali rappresenta una tappa del percorso. Un itinerario può includere più vettori o servizi, ognuno dei quali è considerato un segmento di itinerario.</p> | **Scali**<p>Ogni percorso può avere più *scali*, ognuno dei quali rappresenta una tappa del percorso. Uno scalo può far parte del trasporto, della gestione dei dazi o di un'altra attività.</p> | |
| **Contenitori**<p>Un *contenitore* può essere qualsiasi tipo di confezione o imballaggio utilizzato da TMS.</p> | **Contenitori di spedizione**<p>Un *contenitore di spedizione* è un contenitore di spedizione fisico, come quelli nelle navi portacontainer.</p> | |
| **Codici voce doganale**<p>In TMS (e in altri elementi di Supply Chain Management), i *codici voce doganale* identificano i tipi di voci doganali. Possono avere un impatto su tariffe, manipolazione di materiali pericolosi e così via.</p> | **Codici voce doganale**<p>In Costo sbarcato, i *codici voce doganale* sono stabiliti a livello di persona giuridica. Vengono utilizzati principalmente per i report.</p> | Costo sbarcato può anche utilizzare i codici voce doganale di TMS e altri elementi in Supply Chain Management. Tuttavia, i codici voce doganale di Costo sbarcato vengono utilizzati solo da Costo sbarcato. |

### <a name="some-reference-data-isnt-shared"></a>Alcuni dati di riferimento non sono condivisi

TMS e Costo sbarcato non condividono i dati di riferimento per entità come l'impostazione dei costi, i viaggi e gli scali. Se si utilizzano entrambi i moduli, è necessario ricreare i dati di riferimento non condivisi.

### <a name="intercompany-reports-dont-work-with-goods-in-transit"></a><a name="intercompany-reports"></a>I rapporti interaziendali non funzionano con le merci in transito

I seguenti report non sono utilizzabili insieme alla funzionalità Merci in transito di Costo sbarcato:

- [Report Totali merci in transito interaziendali](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)
- [Report Totali merci in transito interaziendali](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)

Questi report presumono che le merci siano messe in transito non appena si emette un documento di trasporto e che vengano integrate nelle scorte di transito al momento del ricevimento. Tuttavia, le merci in transito non vengono elaborate in questo modo. Pertanto, se si utilizzano le funzionalità Merci in transito e Interaziendale insieme, i risultati per entrambi questi report non saranno corretti.

## <a name="using-the-two-modules-together"></a>Utilizzo combinato dei due moduli

È possibile utilizzare TMS sia per le operazioni in entrata che per quelle in uscita. Il modulo Costo sbarcato fornisce molte delle stesse funzionalità di base di TMS per le operazioni in entrata, ma aggiunge anche alcune funzionalità. Pertanto, si potrebbe prendere in considerazione l'utilizzo di TMS per le operazioni in uscita e Costo sbarcato per le operazioni in entrata.

In genere, si sconsiglia di utilizzare entrambi i moduli insieme per le operazioni in entrata. Si deve utilizzare il modulo che meglio soddisfa le proprie esigenze. Se si utilizzano i due moduli insieme, non è necessario condividere documenti di origine tra di loro. Ad esempio, non utilizzare lo stesso ordine fornitore sia per un carico in TMS e per un viaggio in Costo sbarcato. In particolare, è necessario assicurarsi di non impostare il sistema per creare automaticamente carichi in entrata. Se gli articoli degli ordini fornitore sono inclusi in un viaggio, non possono essere gestiti come parte di un carico.

## <a name="goods-in-transit"></a>Merci in transito

Una delle caratteristiche principali di Costo sbarcato è la possibilità di elaborare le merci in transito. L'elaborazione merci in transito consente di assumere la proprietà finanziaria degli articoli spediti prima che vengano ricevuti fisicamente nel magazzino di destinazione. L'elaborazione merci in transito è spesso richiesta per il commercio internazionale.

### <a name="tms-goods-in-transit-features"></a>Funzionalità Merci in transito di TMS

TMS attualmente non supporta l'elaborazione merci in transito.

### <a name="landed-cost-goods-in-transit-features"></a>Funzionalità Merci in transito di Costo sbarcato

L'elaborazione merci in transito è una funzionalità principale di Costo sbarcato e fornisce le seguenti opzioni:

- **Magazzini merci in transito** - Un magazzino merci in transito può essere associato a ciascun magazzino in Supply Chain Management. Le merci vengono trasferite ai magazzini merci in transito dopo la fatturazione dell'ordine fornitore originale. Gli articoli fisicamente prenotati diventano non disponibili per il consumo fino a quando non arrivano al relativo magazzino fisico. Pertanto, è possibile assumere la proprietà finanziaria delle merci fatturando l'ordine fornitore.
- **Conto CoGe merci in transito** - Costo sbarcato aggiunge un conto di registrazione di contabilità generale specifico al profilo di registrazione dell'ordine fornitore per gestire l'elaborazione merci in transito. Questo conto CoGe merci in transito funge da conto di tipo "merci fatturate non ricevute". Quando l'ordine fornitore originale viene fatturato e l'ordine delle merci in transito viene creato, il costi diretti dell'ordine fornitore vengono registrati nel conto CoGe merci in transito fino a quando le merci non arrivano all'ubicazione fisica finale.
- **Aggiornamenti del controllo della tracciabilità** - Gli ordini delle merci in transito supportano la funzionalità di controllo della tracciabilità in Costo sbarcato. Il controllo della tracciabilità consente di aggiornare la data prevista di arrivo delle merci mentre sono in transito. Il controllo della tracciabilità aggiorna quindi il viaggio e le righe dell'ordine fornitore associate. La data di consegna prevista è quindi disponibile per la pianificazione generale e la logistica.
- **Attivazione delle transazioni in eccesso/in difetto** - In caso di scostamento tra le merci previste su una riga di viaggio e le merci effettive ricevute in magazzino, Costo sbarcato lo risolve creando transazioni in eccesso e/o in difetto. È quindi possibile gestire queste transazioni, in base al modo in cui si desidera elaborarle, tramite un ordine fornitore o un giornale di registrazione movimenti. Le transazioni in eccesso e in difetto forniscono un collegamento al viaggio, all'ordine fornitore originale e al nuovo giornale di registrazione movimenti o ordine fornitore per lo scostamento.
- **Ordini merci in transito** - Costo sbarcato introduce un nuovo documento di origine noto come *Ordine merci in transito*. Un ordine merci in transito consente di fatturare l'ordine fornitore originale per assumere la proprietà finanziaria degli articoli. Quando l'ordine fornitore viene fatturato, il nuovo documento di origine viene creato per ogni riga di ordine fornitore che ha una combinazione di dimensioni inventariali. Le merci vengono quindi spostate fisicamente in un magazzino merci in transito, dove sono fisicamente prenotate per l'ordine merci in transito e non possono essere consumate a meno che non vengano ricevuti ordini merci in transito.

## <a name="miscellaneous-charges-and-shipment-costs"></a>Spese varie e costi di spedizione

Uno degli aspetti più importanti della spedizione e della gestione delle spedizioni per le merci è il riconoscimento dei costi generali associati alle spedizioni. Questi costi generali non sono i costi di inventario diretti associati a un ordine fornitore e a una spedizione o un viaggio. Sono invece costi aggiuntivi introdotti dalla natura del movimento delle merci dal fornitore all'organizzazione. Questi costi possono includere le spese di trasporto associate alla spedizione di merci da un'ubicazione fisica a un'altra o i costi di dazio associati all'importazione di merci da un fornitore straniero.

Costo sbarcato gestisce questi costi creando un nuovo tipo di struttura dei costi denominato *costi automatici*. TMS gestisce questi costi utilizzando la funzionalità Spese varie.

### <a name="tms-charge-and-cost-features"></a>Funzionalità per spese e costi di TMS

TMS utilizza le spese varie per gestire i costi aggiuntivi per carichi allocati alle righe del documento di origine correlate. Queste spese varie possono essere impostate a livello della riga dell'ordine fornitore o dell'intestazione dell'ordine fornitore.

In TMS, le spese varie possono essere ripartite o suddivise per peso, volume o quantità dell'inventario. Le spese possono essere suddivise in spese di trasporto o accessorie. Sarà necessario un ulteriore sviluppo per utilizzare metodi di ripartizione aggiuntivi in TMS.

### <a name="landed-cost-charge-and-cost-features"></a>Funzionalità per spese e costi di Costo sbarcato

Costo sbarcato fornisce una serie di funzioni di costo che gestiscono i costi aggiuntivi associati alla spedizione delle merci. Questi costi sono noti come costi automatici e vengono applicati al momento della fatturazione della spedizione iniziale utilizzando l'importo dei costi stimati. Ogni tipo di costo è gestito nella relativa registrazione. Dopo la registrazione delle fatture effettive per i costi generali, i costi stimati vengono aggiornati automaticamente per riflettere i costi effettivi.

Inoltre, i costi generali associati alla spedizione delle merci possono essere fatturati durante il viaggio dal porto di origine o in qualsiasi momento dopo il ricevimento delle merci. Questa capacità fornisce una maggiore flessibilità per il consumo delle merci.

Il seguente elenco delinea alcuni concetti per le funzionalità di spese e costi in Costo sbarcato:

- **Area di costo** - I costi e le spese possono essere assegnati a diversi livelli, o *aree di costo*, in un viaggio. Il costo può essere applicato a livello di viaggio e suddiviso per ogni elemento del viaggio. Inoltre, i costi possono essere applicati a livello di contenitore, ordine fornitore, articolo o ordine di trasferimento. Ogni spesa può essere gestita separatamente tra le varie aree ed è suddivisa in costi per articolo.
- **Metodi di ripartizione** - Diversi metodi di ripartizione sono disponibili in Costo sbarcato. Le spese possono essere ripartite per quantità, importo in dollari, valore, peso, volume, misura o misura volumetrica definita dall'utente.
- **Controllo compensazione/scostamento** - Le spese vengono impostate come tipo di codice costo proprio in Costo sbarcato. Ogni tipo di codice costo consente di definire un conto di compensazione per le spese dei costi stimati nonché conti di ratei e scostamento dei prezzi di acquisto per gli scostamenti nei costi stimati rispetto ai costi effettivi. Alla registrazione iniziale dei costi stimati, si ha un credito sul conto di compensazione. Dopo la registrazione delle fatture effettive, vengono registrare le spese dei costi effettivi e i costi stimati vengono addebitati dal conto di compensazione.

## <a name="matching-freight-bills-and-invoices"></a>Abbinamento di fatture di trasporto e fatture

### <a name="tms-bill-and-invoice-matching-features"></a>Funzionalità di abbinamento di fatture di trasporto e fatture

TMS può abbinare fatture di trasporto che contengono costi stimati a fatture con il costo effettivo del trasporto. Le fatture possono essere ricevute elettronicamente o su carta. L'abbinamento dello scostamento tra il costo stimato e il costo effettivo non influisce sulla valutazione dell'inventario.

Per ulteriori informazioni, vedere [Riconciliare le spese di trasporto nella gestione del trasporto](../transportation/reconcile-freight-transportation-management.md).

### <a name="landed-cost-bill-and-invoice-matching-features"></a>Funzionalità di abbinamento di fatture di trasporto e fatture di Costo sbarcato

Il modulo Costo sbarcato consente di abbinare le fatture di trasporto alle spese dei costi stimati e di fatturare le spese dei costi effettivi ai costi stimati. Al momento della fatturazione, le spese di trasporto si trovano in un giornale di registrazione fatture e i costi stimati vengono cancellati dal conto di compensazione. Inoltre, le spese dei costi effettivi vengono registrate a fronte del costo del venduto per l'articolo, insieme agli scostamenti tra le spese stimate e quelle effettive. Questo comportamento rende flessibile il processo di fatturazione.

## <a name="tracking"></a>Tracciabilità

Una funzionalità importante dei moduli TMS e Costo sbarcato è la tracciabilità delle merci che consente di identificare la posizione delle stesse durante il viaggio dal punto di origine al magazzino di destinazione finale. La tracciabilità consente di seguire e aggiornare la posizione delle merci e la data di arrivo delle stesse al magazzino. Oltre allo stato delle merci durante il percorso, Costo sbarcato fornisce le date previste ed effettive per ogni tappa del percorso.

### <a name="tms-tracking-features"></a>Funzionalità di tracciabilità di TMS

TMS fornisce funzionalità limitate per la tracciabilità dei carichi in arrivo. Mostra le date e consente di creare un'integrazione per trovare la posizione esatta (ad esempio, nella pagina **Stato trasporto**).

Per ogni segmento di itinerario, è possibile immettere orari stimati e orari di arrivo.

### <a name="landed-cost-tracking-features"></a>Funzionalità di tracciabilità di Costo sbarcato

Costo sbarcato può fornire il controllo di tracciabilità per ogni viaggio, dal porto di origine alla destinazione finale. Il controllo di tracciabilità imposta lo stato del viaggio. Lo stato indica se il viaggio è in corso, alla dogana per l'ispezione o in consegna locale diretta al magazzino finale. Lo stato può essere impostato a livello della riga dell'ordine fornitore, del contenitore e dell'intestazione del viaggio. Pertanto, si ha un controllo più granulare.

Inoltre, una data prevista confermata basata sui lead time specificati è associata a ciascuna tappa di un percorso. Le date di consegna confermate e previste vengono aggiunte alla riga dell'ordine fornitore e agli ordini merci in transito e possono essere utilizzate per la pianificazione generale e la logistica. Oltre alle date previste, è possibile aggiornare le date effettive. Le tappe successive di un percorso verranno quindi aggiornate di conseguenza.

## <a name="multi-leg-journeys"></a>Percorsi con più scali

Il concetto di percorso identifica dove si trovano le merci nel processo e controlla lo stato delle merci mentre sono in transito. Il percorso delle merci può comportare vari scali ed è possibile associare vari costi a uno specifico scalo. Gli esempi includono un costo di trasporto per la navigazione di un'imbarcazione e i costi di trasporto locale per il trasporto di merci dal porto alla destinazione.

### <a name="tms-multi-leg-journey-features"></a>Funzionalità di percorso con più scali di TMS

In TMS, gli itinerari possono essere suddivisi in segmenti di itinerario per rappresentare i percorsi con più scali. TMS può allocare tariffe correnti e spese accessorie a singoli segmenti di itinerario.

Per ulteriori informazioni, vedere [Pianificare percorsi di trasporto di carichi con più fermate](../transportation/plan-freight-transportation-routes-multiple-stops.md).

### <a name="landed-cost-multi-leg-journey-features"></a>Funzionalità di percorso con più scali di Costo sbarcato

Costo sbarcato fornisce un framework per lo spostamento delle merci dal punto di origine alla destinazione attraverso una serie di scali, che sono le fermate o le tappe di un viaggio. Gli scali vengono combinati per creare modelli di percorso, che definiscono il modo in cui le merci vengono spostate dal fornitore all'organizzazione.

In ogni tappa di un percorso, è possibile definire ulteriormente lo stato di ciascuna riga di ordine fornitore e i lead time ad essa associati. Il lead time combinato per tutti gli scali viene utilizzato per identificare la data di consegna stimata. Tuttavia, l'elaborazione merci in transito è richiesta per i percorsi con più scali da applicare. Il percorso delle merci in un viaggio è gestito in una tabella specifica del modulo Costo sbarcato.

## <a name="receiving-by-container"></a>Ricevimento tramite contenitore

Può essere importante gestire il modo in cui le merci vengono suddivise e immagazzinate in un'imbarcazione. In un'imbarcazione, le merci possono essere stoccate in uno o più contenitori. Le merci vengono ricevute in contenitori e differenti contenitori diversi durante un viaggio potrebbero essere ricevuti in momenti diversi o in date diverse.

TMS e Costo sbarcato forniscono funzionalità per la gestione della ricezione delle merci in un contenitore. TMS utilizza il concetto di carichi per gestire le merci, gli ordini fornitore e gli ordini di trasferimento associati a un contenitore di spedizione. TMS supporta il ricevimento sulla base di una struttura di imballaggio ricevuta tramite un ASN (Advance Shipping Notice). Costo sbarcato utilizza il concetto di contenitori di spedizione per elaborare ordini fornitore e controllare i costi generali associati a un contenitore su un'imbarcazione.

### <a name="tms-receiving-by-container-features"></a>Funzionalità di ricevimento tramite contenitore di TMS

TMS supporta ASN in entrata, tutte le varianti di ricevimento tramite l'app warehouse e tutti i metodi di ricevimento tramite il client Supply Chain Management.

### <a name="landed-cost-receiving-by-container-features"></a>Funzionalità di ricevimento tramite contenitore di Costo sbarcato

Per supportare il ricevimento tramite contenitore, Costo sbarcato crea record contenitore di spedizione e associa ordini fornitore a uno specifico contenitore di spedizione utilizzando il relativo ID contenitore. I costi generali possono quindi essere applicati a quel contenitore di spedizione e suddivisi in modo da essere associati agli ordini fornitore pertinenti.

I contenitori in Costo sbarcato possono essere ricevuti tramite un nuovo tipo di ricezione noto come *ricezione merci in transito*, tramite giornali di registrazione arrivi o tramite il ricevimento con dispositivi mobili. Quando si utilizzano giornali di registrazione arrivi, le quantità possono essere inizializzate dall'ordine merci in transito o dalle righe dell'ordine fornitore originale nel contenitore. Costo sbarcato fornisce due tipi di lavoro per il ricevimento tramite l'app di magazzino.

Costo sbarcato non fornisce un ASN per la ricezione elettronica delle merci. Inoltre, non supporta i flussi delle app di magazzino che elaborano il ricevimento di carichi, targhe o targhe miste.

## <a name="rate-shopping-by-vendor"></a>Carrello tariffe in base al venditore

Il carrello tariffario consente a un'azienda di selezionare un fornitore di servizi di trasporto in base al prezzo più basso, all'itinerario più veloce o a una combinazione di entrambe le considerazioni.

### <a name="tms-rate-shopping-features"></a>Funzionalità di carrello tariffe di TMS

TMS consente di identificare soluzioni relative a fornitori e cicli di lavorazione per ordini in entrata e in uscita. Ad esempio, è possibile identificare l'itinerario più rapido o la tariffa più economica per una spedizione.

TMS fornisce un carrello tariffe completo e l'ottimizzazione del trasporto tramite la tariffa workbench dell'itinerario, opzioni di valutazione flessibili tramite il motore di valutazione, un'API del motore di valutazione per l'integrazione con parti esterne e supporto per il peso volumetrico.

Per ulteriori informazioni, vedere [Motori di gestione del trasporto](../transportation/transportation-management-engines.md).

### <a name="landed-cost-rate-shopping-features"></a>Funzionalità di carrello tariffe di Costo sbarcato

Costo sbarcato fornisce solo un supporto limitato per il carrello tariffe da parte del fornitore. Sebbene sia possibile immettere valori per lo spedizioniere, Costo sbarcato non li confronta tra più fornitori.

## <a name="driver-check-incheck-out-with-appointment-scheduling"></a>Check-in/check-out del conducente con programmazione appuntamenti

Le funzionalità di check-in/check-out del conducente consentono al sistema di monitorare gli arrivi e prevenire la congestione nelle banchine di carico.

### <a name="tms-driver-check-incheck-out-features"></a>Funzionalità di check-in/check-out del conducente di TMS

TMS consente di creare *appuntamenti*. Un appuntamento rappresenta eventi che si verificano presso una banchina per ricevere un ordine fornitore, spedire un ordine cliente o elaborare un carico in entrata o in uscita a una data e un'ora specifica. Gli appuntamenti garantiscono la disponibilità delle banchine per il carico e lo scarico delle merci e aiutano a prevenire situazioni in cui più vettori arrivano in un'ubicazione contemporaneamente.

Il sistema consente ai conducenti di effettuare il check-in presso una specifica porta della banchina.

### <a name="landed-cost-driver-check-incheck-out-features"></a>Funzionalità di check-in/check-out del conducente di Costo sbarcato

Costo sbarcato può memorizzare la data e l'ora stimate in cui un contenitore verrà consegnato.

## <a name="transfer-orders-and-additional-costs"></a>Ordini di trasferimento e costi aggiuntivi

Spesso le aziende devono essere in grado di trasferire le merci tra magazzini. Quando si verifica questo tipo di trasferimento, i costi vengono associati ed è possibile che si voglia riconoscere tali costi. In Costo sbarcato, è possibile aggiungere ordini di trasferimento a un viaggio o a un'imbarcazione per tenere traccia del movimento delle merci da un magazzino o sito a un altro, stimare il tempo di consegna e la data di consegna prevista e aggiungere costi generali al trasferimento delle merci.

### <a name="tms-transfer-order-cost-features"></a>Funzionalità del costo di ordini di trasferimento di TMS

TMS supporta la creazione di spese di trasporto collegate ai trasferimenti. Sebbene queste spese possano essere visualizzate nell'ordine di trasferimento, il costo sbarcato non viene aggiunte al costo dell'articolo. La riconciliazione del trasporto è supportata attraverso la creazione di una fattura di trasporto basata su queste spese. Questa fattura di trasporto viene quindi abbinata a una fattura di trasporto fornitore.

### <a name="landed-cost-transfer-order-cost-features"></a>Funzionalità del costo di ordini di trasferimento di Costo sbarcato

Costo sbarcato ti consente di aggiungere ordini di trasferimento a un'imbarcazione o a un viaggio. In questo modo, è possibile aggiungere costi di spedizione al viaggio come liquidazioni magazino al momento del ricevimento dell'ordine di trasferimento. I costi generali possono essere fatturati per i costi effettivi e monitorati rispetto a un viaggio per aggiornare il costo del venduto. Sebbene gli ordini di trasferimento non utilizzino l'elaborazione di merci in transito nella versione standard, possono essere aggiunti ai viaggi. Il costo sbarcato viene aggiunto al costo totale di ogni articolo.
