---
title: Pianificazione generale per prodotti con durata a scaffale limitata
description: Questo articolo descrive come configurare e utilizzare le funzionalità di pianificazione che tengono conto della durata a scaffale dei prodotti deperibili.
author: t-benebo
ms.date: 08/10/2022
ms.topic: article
ms.search.form: ReqPlanSched, CustTable, EcoResProductDetailsExtended, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 95c905cbcc3c057dbccf2b7d6e894b1e99ddfba5
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337145"
---
# <a name="master-planning-for-products-with-limited-shelf-life"></a>Pianificazione generale per prodotti con durata a scaffale limitata

[!include [banner](../../includes/banner.md)]

La durata a scaffale è la quantità di tempo in cui un prodotto può essere conservato fino a quando non può più essere utilizzato o venduto. Per i prodotti che hanno una durata a scaffale limitata, utilizzerai probabilmente una strategia di magazzino FEFO (first-expire, first-out), che dà la priorità al consumo e alla vendita degli articoli in base alla relativa durata a scaffale rimanente. Questa strategia di magazzino è pertinente per alimenti, medicinali e altri beni caratterizzati da un breve tempo di conservazione. Secondo FEFO, gli articoli nel magazzino sono stoccati come merce su uno scaffale di un supermercato: i prodotti che hanno una lunga durata a scaffale sono collocati dietro negli scaffali, di modo che i prodotti che hanno una durata a scaffale rimanente più breve vengano spediti per primi.

## <a name="using-shelf-life-in-master-planning"></a>Utilizzare la durata a scaffale nella pianificazione generale

Questa sezione descrive il modo in cui la pianificazione generale suggerisce la fornitura per articoli con durata a scaffale.

Quando esegui un piano generale, genera ordini pianificati suggeriti (fornitura) che soddisferanno la tua domanda e ridurranno al minimo i ritardi. Se il tuo piano include articoli con una durata a scaffale limitata, i calcoli di pianificazione diventano più complessi, poiché il piano non solo deve ridurre al minimo i ritardi, ma deve anche utilizzare la fornitura esistente prima che scada. Il piano deve cercare di utilizzare la fornitura più vicina alla data di scadenza prima della fornitura che scade più tardi. Pertanto, la pianificazione generale cerca di raggiungere i seguenti obiettivi, in questo ordine:

1. Ridurre al minimo la somma dei ritardi.
1. Massimizzare la somma della fornitura FEFO.
1. Ridurre al minimo il rifornimento delle scorte.

In alcuni casi potrebbe esserci un conflitto tra i primi due obiettivi ed è necessario fare una scelta: intendi ritardare una spedizione o utilizzare una fornitura che scade più tardi al posto di una fornitura che scade prima? Per risolvere questo conflitto durante la pianificazione generale, il sistema dà la priorità alla riduzione al minimo dei ritardi rispetto all'utilizzo della fornitura con scadenza a breve. In genere, questo tipo di conflitto si verifica quando potrebbero esserci ritardi e una copertura per periodo. Pertanto, ti consigliamo di utilizzare un periodo di copertura inferiore alla durata a scaffale di un articolo. È improbabile che questo tipo di conflitto si verifichi con altri tipi di copertura (ad esempio il fabbisogno).

## <a name="set-up-shelf-life"></a>Impostare la durata a scaffale

### <a name="configure-each-master-plan-to-consider-shelf-life"></a>Configurare ogni piano generale per prendere in considerazione la durata a scaffale

Per impostazione predefinita, i piani generali non prendono in considerazione la durata a scaffale. Utilizza la procedura seguente per abilitare i calcoli della durata a scaffale per ogni piano generale che li richiede.

1. Vai a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Seleziona un piano esistente nel riquadro elenco o creane uno.
1. Nella Scheda dettaglio **Generale**, imposta l'opzione **Utilizza date di durata a scaffale** su *Sì*.

### <a name="configure-tracking-dimension-groups-to-track-the-batch-dimension"></a>Configurare gruppi di dimensioni di tracciabilità per tenere traccia della dimensione del lotto

Puoi tenere traccia della durata a scaffale di un articolo solo se si tiene traccia di tale articolo a livello della dimensione del lotto. In altre parole, il riferimento del lotto e le date richieste devono essere registrati al momento del ricevimento o della produzione e con ogni transazione di magazzino dell'articolo. Per gestire questa opzione, imposta uno o più gruppi di dimensioni di tracciabilità per eseguire il rilevamento richiesto, quindi assegna gli articoli pertinenti a tali gruppi come necessario.

Utilizza la procedura seguente per impostare un gruppo di dimensioni di tracciabilità per tenere traccia della dimensione del lotto.

1. Vai a **Gestione informazioni sul prodotto \> Impostazioni \> Gruppi di dimensioni e di varianti \> Gruppi di dimensioni di tracciabilità**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Nel riquadro azioni, seleziona **Nuovo** per creare un nuovo gruppo di dimensioni di tracciabilità. Nel riquadro azioni seleziona **Salva** e immetti un nome e una descrizione.
    - Nel riquadro elenco, seleziona il gruppo di dimensioni di tracciabilità esistente che vuoi impostare per tenere traccia della dimensione del lotto.

1. Nella Scheda dettaglio **Dimensione di tracciabilità**, nella riga **Numero batch**, seleziona le caselle di controllo nelle colonne **Attivo** e **Inventario fisico**.

### <a name="set-up-shelf-life-for-a-product"></a>Impostare la durata a scaffale per un prodotto

Utilizza la procedura seguente per impostare la durata a scaffale per un prodotto.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Crea o apri il prodotto che vuoi impostare.
1. Per utilizzare le impostazioni della durata a scaffale, nella Scheda dettaglio **Generale**, imposta il campo **Gruppo di dimensioni di tracciabilità** su un gruppo di dimensioni di tracciabilità che è impostato per tenere traccia della dimensione batch. Puoi impostare questo campo solo quando crei un prodotto per la prima volta. Non puoi modificare il valore per i prodotti esistenti.
1. Nella Scheda dettaglio **Gestione articoli**, imposta i seguenti campi:

    - **Durata a scaffale consigliata in giorni** – Specifica il periodo (in giorni) entro il quale controllare un batch del prodotto per assicurarti che sia idoneo al consumo o alla rivendita. Il valore di questo campo viene aggiunto alla *data di fabbricazione* di un batch per determinarne la *Data di durata a scaffale consigliata*. Puoi configurare il sistema per generare ordini di controllo qualità quando un batch è prossimo alla data di durata a scaffale consigliata.
    - **Periodo di durata a scaffale in giorni** – Specifica il numero di giorni prima della scadenza di un batch del prodotto. Questo valore viene aggiunto alla *data di fabbricazione* per determinare la *data di scadenza*. Il batch viene considerato inutilizzabile dopo tale data.
    - **Periodo di consumo consigliato espresso in giorni** – Specifica il periodo (in giorni) dopo il quale un batch del prodotto è ritenuto ancora vendibile, ma perde alcune delle sue proprietà originali. Questo valore viene aggiunto alla *data di fabbricazione* per determinare la *data di consumo consigliata*. Puoi eseguire report per identificare le scorte che hanno superato la data di consumo consigliata. 

### <a name="set-a-sellable-days-rule-for-each-customer"></a>Impostare una regola di giorni di vendita per ogni cliente

La funzionalità *Giorni di vendita* garantisce che i prodotti di un batch che scadrà a breve non vengano inviati ai clienti. Inoltre, garantisce che quando i prodotti sono inviati a un cliente, rimarrà un numero sufficiente di giorni di vendita dopo la consegna.

Per utilizzare la funzionalità dei giorni di vendita, devi definire il numero di giorni di vendita che si applica a ciascun prodotto (o gruppo di prodotti) per ogni cliente. Devi completare manualmente questo processo, poiché non esiste un'entità di dati.

Utilizza la procedura seguente per impostare giorni di vendita per ciascun prodotto per ogni cliente.

1. Vai a **Vendite e marketing \> Clienti \> Tutti i clienti**.
1. Trova e seleziona il cliente che vuoi impostare.
1. Nel riquadro azioni, nella scheda **Vendi**, nel gruppo **Imposta**, seleziona **Vendi \> Giorni di vendita**.
1. Nella pagina **Giorni di vendita per cliente**, la griglia elenca le regole di giorni di vendita esistenti per ogni prodotto o gruppo di prodotti. Utilizza i pulsanti del riquadro azioni per aggiungere o modificare le righe nella griglia come necessario. Un **filtro** viene fornito per aiutarti a trovare le righe esistenti.
1. Per ciascuna riga, imposta i seguenti campi:

    - **Codice articolo** - Seleziona uno dei seguenti valori per specificare l'ambito degli articoli che saranno interessati.

        - *Tabella* - La riga si applica a un articolo specifico.
        - *Gruppo* - La riga si applica a un gruppo di articoli specifico.
        - *Tutti* - La riga si applica a tutti gli articoli.

    - **Relazione articolo** - Se imposti il campo **Codice articolo** su *Tabella*, seleziona un articolo specifico. Se hai impostato il campo **Codice articolo** su *Gruppo*, seleziona un gruppo di articoli. Se imposti il campo **Codice articolo** su *Tutti*, questo campo non è disponibile.
    - **Giorni di vendita** – Immetti il numero minimo di giorni che il cliente deve avere per vendere i prodotti corrispondenti prima della scadenza del batch. Il valore dei giorni di vendita si basa sulla data di ricevimento richiesta (o sulla data di ricevimento confermata, se definita) per i prodotti corrispondenti nell'ordine cliente.
    - *(Altre dimensioni del prodotto)* – Per limitare ulteriormente l'ambito di una riga, specifica altri valori di dimensione (come **Dimensione** e **Colore**) come necessario. Per determinare quali dimensioni sono visualizzate nella griglia, seleziona **Visualizza dimensioni** nel riquadro azioni.

### <a name="set-up-all-relevant-products-so-that-they-are-fefo-date-controlled"></a>Impostare tutti i prodotti pertinenti di modo che siano controllati in base alla data FEFO

Affinché i giorni di vendita funzionino, ogni articolo pertinente deve appartenere a un gruppo di modelli di articoli in cui la casella di controllo **Controllo in base a data FEFO** è selezionata.

Utilizza la procedura seguente per impostare un gruppo di modelli di articoli di modo che supporti la funzionalità dei giorni di vendita.

1. Andare a **Gestione articoli \> Impostazioni \> Scorte \> Gruppi di modelli di articoli**.
1. Seleziona un gruppo esistente nel riquadro elenco oppure creane uno selezionando **Nuovo** nel riquadro azioni.
1. Nella Scheda dettaglio **Criteri di inventario**, seleziona la casella di controllo **Controllo in base a data FEFO**.
1. Imposta altri campi per il gruppo come necessario.

Utilizza la procedura seguente per visualizzare o impostare il gruppo di modelli di articoli a cui appartiene un prodotto.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Apri il prodotto che vuoi esaminare o modificare.
1. Nella Scheda dettaglio **Generale**, imposta il campo **Gruppo di modelli di articoli** su un gruppo in cui la casella di controllo **Controllo in base a data FEFO** è selezionata.

## <a name="example-1-simple-fefo-10-day-period-zero-days-of-lead-time"></a>Esempio 1: FEFO semplice, periodo di 10 giorni, zero giorni di lead time

Questo esempio mostra un esempio di base della durata a scaffale, in cui il pegging tra gli ordini di fornitura e la domanda viene eseguito per soddisfare i seguenti obiettivi del sistema:

- Ridurre al minimo la somma dei ritardi.
- Massimizzare la somma della fornitura FEFO.
- Ridurre al minimo il rifornimento delle scorte.

Il sistema presenta le seguenti impostazioni relative ad articoli e al piano generale:

- **Codice copertura (strategia di rifornimento):** periodo 
- **Periodo copertura:** 10 giorni (pari alla durata a scaffale)
- **Durata a scaffale:** 10 giorni
- **Giorni di vendita:** 0 giorni
- **Lead time:** 0 giorni
- **Giorni negativi:** 0 giorni
- **Tipo di ordine pianificato (impostazioni dell'ordine predefinite dell'articolo):** ordine fornitore

Nel sistema sono presenti i seguenti ordini cliente per l'articolo:

- **SO1:** quantità (qtà) = 2, data di consegna richiesta = oggi + 1 giorno
- **SO2:** qtà = 1, data di consegna richiesta = oggi + 4 giorni
- **SO3:** qtà = 1, data di consegna richiesta = oggi + 5 giorni

Tutti questi ordini cliente creano domanda per l'articolo.

Per l'articolo esiste la seguente fornitura:

- **Scorte disponibili:** qtà = 1, data di scadenza = oggi + 5 giorni
- **Ordine fornitore 1 (PO1):** data di ricevimento = oggi + 2 giorni, qtà = 1, data di scadenza = oggi + 4 giorni

Il sistema crea un elenco di forniture in grado di coprire questa domanda e ordina l'elenco per data di scadenza (utilizzando FEFO).

La pianificazione generale crea il pegging richiesto tra domanda e offerta. Crea inoltre qualsiasi domanda richiesta in base all'elenco di forniture (utilizzando FEFO) e prende in considerazione la data di disponibilità.

- SO1 può essere soddisfatto dalla quantità disponibile, ma non può essere soddisfatto da PO1, poiché la data di disponibilità per PO1 è un giorno più tardi di quanto richiesto da SO1. Pertanto, SO1 genera domanda per un'unità di merci.
- SO2 può essere coperto da PO1, poiché PO1 arriverà all'ora richiesta e la data di scadenza sarà ancora valida. Pertanto, il fabbisogno di SO2 è completamente coperto da PO1.
- SO3 non è coperto poiché le risorse non sono disponibili. Pertanto, SO3 genera domanda per un'unità di merci.

Per coprire tutti i fabbisogni restanti, il sistema deve creare il seguente ordine fornitore pianificato:

- **PPO1:** data di ricevimento = oggi, qtà = 2, data di scadenza = oggi + 10 giorni

La seguente tabella riepiloga il risultato.

| Domanda | Pegging |
|---|---|
| **SO1:** data di consegna = oggi + 1 giorno, qtà = 2 | <p>**Disponibilità:** qtà = 1, data di scadenza = oggi + 5 giorni</p><p>**PPO1:** data di ricevimento = oggi, qtà = 1, data di scadenza = oggi + 10 giorni</p> |
| **SO2:** data di consegna = oggi + 4 giorni, qtà = 1 | **PO1:** data di ricevimento = oggi + 2 giorni, qtà = 1, data di scadenza = oggi + 4 giorni |
| **SO3:** data di consegna = oggi + 5 giorni, qtà = 1 | **PPO1:** data di ricevimento = oggi, qtà = 2, data di scadenza = oggi + 10 giorni |

L'illustrazione seguente mostra la sequenza temporale per questo esempio.

![Esempio 1: FEFO semplice, periodo di 10 giorni, zero giorni di lead time.](media/fefo-example-1.png "Esempio 1: FEFO semplice, periodo di 10 giorni, zero giorni di lead time")

## <a name="example-2-simple-fefo-requirement-three-days-of-lead-time"></a>Esempio 2: FEFO semplice, fabbisogno, tre giorni di lead time

Questo esempio mostra come il tentativo del sistema di ridurre al minimo i ritardi a volte può generare un ordine eccessivo di ordini.

Il sistema presenta le seguenti impostazioni relative ad articoli e al piano generale:

- **Codice copertura (strategia di rifornimento):** fabbisogno
- **Durata a scaffale:** 10 giorni
- **Giorni di vendita:** 0 giorni
- **Lead time:** stabilito dai seguenti accordi commerciali con i fornitori:

    - **Accordo commerciale 1:** se qtà = 1, lead time = 4
    - **Accordo commerciale 2:** se qtà = 2, lead time = 3

- **Giorni negativi:** 0 giorni
- **Tipo di ordine pianificato (impostazioni dell'ordine predefinite dell'articolo):** ordine fornitore

Il seguente ordine cliente esiste nel sistema:

- **SO1:** qtà = 2, data di consegna richiesta = oggi + 3 giorni

Questa domanda è coperta dalla fornitura esistente e da un ordine fornitore confermato:

- **Scorte disponibili:** disponibile = oggi, qtà = 1, data di scadenza = oggi + 2 giorni
- **PO1:** data di ricevimento = oggi + 3 giorni, qtà = 1, data di scadenza = oggi + 4 giorni

SO1 non può essere soddisfatto dalle scorte disponibili in quanto la data di scadenza delle scorte è precedente alla data di spedizione. PO1 può coprire il fabbisogno di SO1 anche con una quantità pari a 1. Pertanto, SO1 genera domanda per un'unità di merci. Per coprire questo fabbisogno, il sistema crea un ordine fornitore pianificato (PPO1).

Il sistema prevede due accordi commerciali (uno per qtà = 1, lead time = 4 giorni e uno per qtà = 2, lead time = 3 giorni). Pertanto, il sistema tenta di ridurre al minimo i ritardi creando un ordine fornitore pianificato (PPO1) che soddisfi il secondo accordo commerciale. Il risultato è una consegna eccessiva (qtà = 2, data di scadenza = oggi + 10 giorni).

La seguente tabella riepiloga il risultato.

| Domanda | Pegging |
|---|---|
| **SO1:** data di consegna = oggi + 3 giorni, qtà = 2 | <p>**PO1:** data di ricevimento = oggi + 3 giorni, qtà = 1, data di scadenza = oggi + 4 giorni</p><p>**PPO1:** data di ricevimento = oggi + 3 giorni, qtà = 1, data di scadenza = oggi + 10 giorni</p> |

L'illustrazione seguente mostra la sequenza temporale per questo esempio.

![Esempio 2: FEFO semplice, fabbisogno, tre giorni di lead time.](media/fefo-example-2.png "Esempio 2: FEFO semplice, fabbisogno, tre giorni di lead time")

## <a name="example-3-simple-fefo-requirement-three-days-of-lead-time-five-sellable-days"></a>Esempio 3: FEFO semplice, fabbisogno, tre giorni di lead time, cinque giorni di vendita

Questo esempio mostra come funziona la durata a scaffale quando vengono aggiunti giorni di vendita per un articolo.

Il sistema presenta le seguenti impostazioni relative ad articoli e al piano generale:

- **Codice copertura (strategia di rifornimento):** fabbisogno
- **Durata a scaffale:** 10 giorni
- **Giorni di vendita:** 5 giorni
- **Lead time:** 5 giorni
- **Giorni negativi:** 0 giorni
- **Tipo di ordine pianificato (impostazioni dell'ordine predefinite dell'articolo):** ordine fornitore

I seguenti ordini cliente esistono nel sistema:

- **SO1:** qtà = 2, data di consegna richiesta = oggi + 2 giorni
- **SO2:** qtà = 1, data di consegna richiesta = oggi + 3 giorni
- **SO3:** qtà = 1, data di consegna richiesta = oggi + 5 giorni

Questa domanda può essere coperta dalla fornitura esistente e da un ordine fornitore confermato:

- **Scorte disponibili:** disponibili = oggi, qtà = 1, data di scadenza = oggi + 6 giorni
- **PO1:** data di ricevimento = oggi + 2 giorni, qtà = 3, data di scadenza = oggi + 10 giorni

Il sistema crea un elenco di candidati al pegging, in base all'elenco di forniture (FEFO) e alle date di disponibilità. Pertanto, SO1 non può essere soddisfatto dalle scorte disponibili, poiché tali scorte scadono prima della fine dei giorni di vendita richiesti dal cliente (data di ricevimento richiesta + 5 giorni). PO1 può coprire il fabbisogno di SO1 con due unità e il fabbisogno di SO2 con un'unità. Pertanto, solo SO3 ha ancora una domanda non coperta per un'unità di merci. Per coprire questo fabbisogno, il sistema crea il seguente ordine fornitore pianificato:

- **PP01:** data di ricevimento = oggi + 5 giorni, qtà = 1, data di scadenza = oggi + 10 giorni

La seguente tabella riepiloga il risultato.

| Domanda | Pegging |
|---|---|
| **SO1:** data di consegna = oggi + 2 giorni, qtà = 2 | **PO1:** data di ricevimento = oggi + 2 giorni, qtà = 2, data di scadenza = oggi + 10 giorni |
| **SO2:** data di consegna = oggi + 3 giorni, qtà = 1 | **PO1:** data di ricevimento = oggi + 2 giorni, qtà = 1, data di scadenza = oggi + 10 giorni |
| **SO3:** data di consegna = oggi + 5 giorni, qtà = 1 | **PPO1:** data di ricevimento = oggi + 5 giorni, qtà = 1, data di scadenza = oggi + 10 giorni |

L'illustrazione seguente mostra la sequenza temporale per questo esempio.

![Esempio 3: FEFO semplice, fabbisogno, tre giorni di lead time, cinque giorni di vendita.](media/fefo-example-3.png "Esempio 3: FEFO semplice, fabbisogno, tre giorni di lead time, cinque giorni di vendita")

## <a name="example-4-simple-fefo-period-lead-time-depends-on-the-quantity"></a>Esempio 4: FEFO semplice, periodo, lead time dipende dalla quantità

Questo esempio mostra come il tentativo del sistema di ridurre al minimo i ritardi a volte può generare un ordine eccessivo di ordini.

Il sistema presenta le seguenti impostazioni relative ad articoli e al piano generale:

- **Codice copertura (strategia di rifornimento):** periodo
- **Periodo copertura:** 10 giorni (pari alla durata a scaffale)
- **Durata a scaffale:** 10 giorni
- **Giorni di vendita:** 0 giorni
- **Lead time:** stabilito dai seguenti accordi commerciali con i fornitori:

    - **Accordo commerciale 1:** se qtà = 1, lead time = 5
    - **Accordo commerciale 2:** se qtà = 2, lead time = 0

- **Giorni negativi:** 0 giorni
- **Tipo di ordine pianificato (impostazioni dell'ordine predefinite dell'articolo):** ordine fornitore

I seguenti ordini cliente esistono nel sistema:

- **SO1:** qtà = 1, data di consegna richiesta = oggi
- **SO2:** qtà = 1, data di consegna richiesta = oggi + 6 giorni

Questa domanda può essere parzialmente coperta dalla fornitura esistente dei seguenti ordini fornitore confermati:

- **PO1:** data di ricevimento = oggi + 1 giorni, qtà = 1, data di scadenza = oggi + 2 giorni
- **PO2:** data di ricevimento = oggi + 3 giorni, qtà = 1, data di scadenza = oggi + 7 giorni

Il sistema prevede due accordi commerciali (uno per qtà = 1, lead time = 5 giorni e uno per qtà = 2, lead time = 0 giorni). Pertanto, il sistema tenta di ridurre al minimo i ritardi creando il seguente ordine fornitore pianificato che soddisfi il secondo accordo commerciale:

- **PP01:** data di ricevimento = oggi, qtà = 2, data di scadenza = oggi + 10 giorni

SO1 sarà coperto da un'unità di PPO1. SO2 sarà coperto da PO2, poiché PO2 scade prima di PPO1.

La seguente tabella riepiloga il risultato.

| Domanda | Pegging |
|---|---|
| **SO1:** data di consegna = oggi, qtà = 1 | **PPO1:** data di ricevimento = oggi, qtà = 1, data di scadenza = oggi + 10 giorni |
| **SO2:** data di consegna = oggi + 6 giorni, qtà = 1 | **PO2:** data di ricevimento = oggi + 3 giorni, qtà = 1, data di scadenza = oggi + 7 giorni |

> [!NOTE]
> PO1 non viene utilizzato poiché arriverà troppo tardi per S01 e scadrà prima della consegna di S02. PPO1 ha ordinato un'unità in più per consentire al lead time di essere 0 (zero), secondo l'accordo commerciale 2.

L'illustrazione seguente mostra la sequenza temporale per questo esempio.

![Esempio 4: FEFO semplice, periodo, lead time dipende dalla quantità.](media/fefo-example-4.png "Esempio 4: FEFO semplice, periodo, lead time dipende dalla quantità")

## <a name="example-5-simple-fefo-requirement-10-negative-days"></a>Esempio 5: FEFO semplice, fabbisogno, 10 giorni negativi

<!-- KFM: This is more of a negative days example than a shelf life example. We should point out more explicitly how shelf life affects this situation (or maybe otherwise remove this example). -->

Questo esempio mostra come funziona la durata a scaffale quando un gran numero di giorni negativi viene aggiunto per un articolo. I giorni negativi sono il numero di giorni che sei disposto ad attendere prima di ordinare il rifornimento di un articolo in caso di scorte negative. Il sistema non crea una fornitura a meno che non venga superato il numero di giorni negativi.

Il sistema presenta le seguenti impostazioni relative ad articoli e al piano generale:

- **Codice copertura (strategia di rifornimento):** fabbisogno
- **Lead time:** 0 giorni
- **Giorni negativi:** 10 giorni
- **Tipo di ordine pianificato (impostazioni dell'ordine predefinite dell'articolo):** ordine fornitore

Il seguente ordine cliente esiste nel sistema:

- **SO1:** qtà = 1, data di consegna richiesta = oggi

Questa domanda può essere coperta dalla fornitura esistente del seguente ordini fornitore confermato:

- **PO1:** data di ricevimento = oggi + 3 giorni, qtà = 1, data di scadenza = oggi + 5 giorni

Poiché il sistema è configurato per consentire 10 giorni negativi, copre la domanda di SO1 utilizzando PO1, anche se il risultato sarà un ritardo di tre giorni poiché SO1 crea scorte negative fino all'arrivo di PO1. Non viene creato alcun ordine fornitore pianificato, anche se il lead time è 0 (zero) e la creazione di un ordine fornitore pianificato ridurrebbe i ritardi.

La seguente tabella riepiloga il risultato.

| Domanda | Pegging |
|---|---|
| **SO1:** data di consegna = oggi, qtà = 1 | **PO1:** data di ricevimento = oggi + 3 giorni, qtà = 1, data di scadenza = oggi + 5 giorni |

L'illustrazione seguente mostra la sequenza temporale per questo esempio.

![Esempio 5: FEFO semplice, fabbisogno, 10 giorni negativi.](media/fefo-example-5.png "Esempio 5: FEFO semplice, fabbisogno, 10 giorni negativi")

## <a name="example-6-simple-fefo-requirement-five-negative-days"></a>Esempio 6: FEFO semplice, fabbisogno, cinque giorni negativi

Questo esempio mostra come funziona la durata a scaffale quando il numero di giorni negativi per un articolo è inferiore al relativo periodo di durata a scaffale.

Il sistema presenta le seguenti impostazioni relative ad articoli e al piano generale:

- **Codice copertura (strategia di rifornimento):** fabbisogno
- **Giorni di vendita:** 0 giorni
- **Lead time:** 0 giorni
- **Giorni negativi:** 5 giorni
- **Tipo di ordine pianificato (impostazioni dell'ordine predefinite dell'articolo):** ordine fornitore

Il seguente ordine cliente esiste nel sistema:

- **SO1:** qtà = 2, data di consegna richiesta = oggi

Questa domanda può essere coperta dalla fornitura esistente dei seguenti ordini fornitore confermati:

- **PO1:** data di ricevimento = oggi, qtà = 1, data di scadenza = oggi + 1 giorno
- **PO2:** data di ricevimento = oggi + 2 giorni, qtà = 1, data di scadenza = oggi + 3 giorni

Tuttavia, il sistema deve rispettare la restrizione secondo la quale gli articoli spediti non possono essere scaduti al momento della spedizione. Pertanto, PO2 e PO1 non possono essere utilizzati entrambi per SO1, poiché PO1 scade prima dell'arrivo di PO2. Il sistema crea il seguente ordine fornitore pianificato per completare la copertura della domanda per SO1:

- **PPO1:** data di ricevimento = oggi, qtà = 1, data di scadenza = oggi + 10 giorni

Il sistema può sfruttare i cinque giorni negativi e utilizzare PO2 e PPO1 per coprire SO1. Tuttavia, questo approccio ritarderà la consegna fino all'arrivo di PO2 e nel frattempo PO1 scadrà. Pertanto, il sistema copre SO1 utilizzando PPO1 e PO1.

La seguente tabella riepiloga il risultato.

| Domanda | Pegging |
|---|---|
| **SO1:** data di consegna = oggi, qtà = 2 | <p>**PO1:** data di ricevimento = oggi, qtà = 1, data di scadenza = oggi + 1 giorno</p><p>**PPO1:** data di ricevimento = oggi, qtà = 1, data di scadenza = oggi + 10 giorni</p> |

L'illustrazione seguente mostra la sequenza temporale per questo esempio.

![Esempio 6: FEFO semplice, fabbisogno, cinque giorni negativi.](media/fefo-example-6.png "Esempio 6: FEFO semplice, fabbisogno, cinque giorni negativi")
