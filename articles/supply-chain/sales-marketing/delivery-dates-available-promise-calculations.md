---
title: Promesse ordine
description: Questo articolo fornisce informazioni sulle promesse di ordine. La promessa di ordine consente di promettere in modo affidabile le date di consegna ai clienti e di restituire la flessibilità in modo che sia possibile rispettare le date.
author: Henrikan
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesATP, SalesAvailableDlvDates, SalesCarrier
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c835e25348b937c1dd68d8fa45b0264bd6815c23
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228268"
---
# <a name="order-promising"></a>Promesse ordine

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulle promesse di ordine. La promessa di ordine consente di promettere in modo affidabile le date di consegna ai clienti e di restituire la flessibilità in modo che sia possibile rispettare le date.

Le promesse di ordine calcolano la prima data di spedizione e di entrate e si basa sul metodo di controllo data di consegna e sui giorni di consegna. Puoi scegliere tra i seguenti quattro metodi di controllo della data di consegna:

- **Lead time di vendita**: è il tempo che trascorre tra la creazione di un ordine cliente e la spedizione degli articoli. Il calcolo della data di consegna è basato su un numero predefinito di giorni e non prende in considerazione la disponibilità delle scorte, la domanda nota e l'offerta pianificata.
- **ATP (available-to-promise)**: è la quantità di un articolo disponibile e che può essere promessa a un cliente in una data specifica. Il calcolo della quantità ATP include magazzino non impegnato, lead time, entrate e uscite pianificate.
- **ATP + margine su uscita magazzino**: la data di spedizione è uguale alla data ATP più il margine su uscita da magazzino per l'articolo. Il margine su uscita da magazzino consiste nel tempo richiesto per preparare gli articoli per la spedizione.
- **CTP (capable-to-promise)**: la disponibilità viene calcolata tramite un'esplosione. Se utilizzi Ottimizzazione pianificazione, il metodo di controllo della data di consegna *CTP* non è consentito e se è selezionato, causerà un errore durante l'esecuzione del calcolo. Per ulteriori informazioni su come impostare e usare le funzionalità CTP, vedi [Calcolare le date di consegna di ordini cliente utilizzando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).
- **CTP per Ottimizzazione pianificazione**: utilizza il calcolo CTP fornito da Ottimizzazione pianificazione. Questa opzione non ha effetto se stai utilizzando il motore di pianificazione generale integrato. Per ulteriori informazioni su come impostare e usare le funzionalità CTP, vedi [Calcolare le date di consegna di ordini cliente utilizzando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

> [!NOTE]
> Quando un ordine cliente viene aggiornato, le informazioni sulla promessa d'ordine vengono aggiornate solo se la data di promessa d'ordine esistente non può essere soddisfatta, come illustrato nei seguenti esempi:
>
> - **Esempio 1**: l'attuale data di promessa d'ordine è il 20 luglio, ma a causa dell'aumento della quantità, non sarà possibile effettuare consegne fino al 25 luglio. Poiché la data corrente non può più essere soddisfatta, viene attivata la promessa d'ordine.
> - **Esempio 2**: l'attuale data di promessa d'ordine è il 20 luglio, ma a causa della riduzione della quantità, è ora possibile effettuare consegne il 15 luglio. Tuttavia, poiché la data corrente può ancora essere soddisfatta, la promessa d'ordine non viene attivata e il 20 luglio rimane la data di promessa d'ordine.

## <a name="atp-calculations"></a>Calcoli ATP

La quantità ATP viene calcolata in base al metodo "ATP cumulativa includendo i periodi futuri". Il metodo di calcolo ATP ha come vantaggio principale la capacità di gestire i casi in cui la somma delle uscite tra le entrate è maggiore dell'ultima entrata, ad esempio nei casi in cui è necessario utilizzare una quantità di un'entrata precedente per soddisfare un fabbisogno. Il metodo di calcolo "ATP cumulativa includendo i periodi futuri" include tutte le uscite finché la quantità cumulativa da ricevere non supera la quantità cumulativa per l'uscita. Di conseguenza, il metodo di calcolo ATP valuta se parte della quantità di un periodo precedente può essere utilizzata in un periodo successivo.

La quantità ATP è il saldo di magazzino non impegnato nel primo periodo. In genere viene calcolato per ogni periodo in cui è programmata un'entrata. Il periodo ATP viene calcolato in giorni e come prima data per la quantità ATP viene calcolata la data corrente. Nel primo periodo la quantità ATP include le scorte disponibili meno gli ordini cliente in scadenza o scaduti.

La quantità ATP viene calcolata utilizzando la seguente formula:

ATP = ATP del periodo precedente + entrate del periodo corrente - uscite del periodo corrente - quantità di uscita netta di ciascun periodo futuro fino al periodo in cui la somma delle entrate di tutti i periodi futuri (periodo futuro incluso) non supera la somma delle uscite (periodo futuro incluso).

Si noti che il calcolo ATP non include le informazioni sulla data di scadenza e oltre all'intervallo temporale dell'ATP che il sistema prevede quando sarà possibile promettere una quantità.

Una volta considerate tutte le uscite o le entrate, la quantità ATP delle date successive corrisponderà all'ultima quantità ATP calcolata.

Se non vengono fornite tutte le dimensioni utilizzate per un articolo quando viene completato il controllo ATP, è comunque possibile specificarle nelle uscite e nelle entrate. In questo caso nel calcolo ATP le entrate e le uscite devono essere aggregate alle dimensioni esistenti per ridurre il numero di righe di entrate e di uscite utilizzate nel calcolo ATP.

La quantità ATP indicata è sempre maggiore o uguale a 0 (zero). Se il calcolo restituisce una quantità ATP negativa, ad esempio se la quantità promessa in precedenza supera la quantità disponibile, la quantità è impostata automaticamente su 0.

### <a name="example"></a>Esempio

Il campo **Intervallo temporale domanda all'indietro ATP** controlla quanti giorni indietro va eseguita la ricerca di ordini di domanda ritardata o uscite dal magazzino. Il campo **Intervallo temporale offerta all'indietro ATP** controlla quanti giorni indietro va eseguita la ricerca di ordini di fornitura ritardata o di entrate in magazzino. Ad esempio, se gli ordini ritardati di solo sette giorni devono essere considerati nel calcolo ATP, entrambi i campi devono essere impostati su **7**.

I campi **Offset domanda ritardata ATP** e **Offset offerta ritardata ATP** controllano quando la domanda o l'offerta ritardata verrà considerata nel calcolo ATP. Ad esempio, se la domanda o l'offerta ritardata deve essere considerata nel calcolo ATP dopo due giorni, entrambi i campi devono essere impostati su **2**. Un valore di **2** significa che la quantità di un articolo in un ordine fornitore ritardato che deve essere considerato nel calcolo ATP sarà vista come disponibile due giorni dopo la data corrente.

Per il seguente esempio, **7** viene immesso nei campi **Intervallo temporale domanda all'indietro ATP** e **Intervallo temporale offerta all'indietro ATP** e **1** viene immesso nei campi **Offset domanda ritardata ATP** e **Offset offerta ritardata ATP**.

Un ordine fornitore per 200 pezzi di prodotto che doveva essere ricevuto tre giorni fa non è ancora stato ricevuto. Pertanto, una riga ordine cliente per 75 pezzi dello stesso prodotto che doveva essere spedito ieri non è stata spedita.

Un cliente chiama per ordinare 150 pezzi dello stesso prodotto. Quando si verifica la disponibilità del prodotto, si rileva la presenza di un altro ordine fornitore per 100 pezzi del prodotto che verrà consegnato 10 giorni dopo.

Si crea una riga ordine cliente per il prodotto e si immette **150** per la quantità.

Poiché il metodo di controllo della data di consegna è ATP, i dati ATP vengono calcolati per individuare la prima data di spedizione possibile. In base alle impostazioni, vengono considerati l'ordine fornitore e l'ordine cliente in ritardo e la quantità ATP risultante per la data corrente è 0. Il giorno successivo, quando è in programma la ricezione dell'ordine fornitore in ritardo, la quantità ATP viene calcolata come maggiore di 0, in questo caso, viene calcolata come 125. Nei 10 giorni successivi alla data corrente, quando si prevede la ricezione di un altro ordine fornitore da 100 pezzi, la quantità ATP diventa superiore a 150.

La data di spedizione viene quindi impostata su 10 giorni dalla data corrente, in base al calcolo ATP. SI informa pertanto il cliente che la quantità richiesta può essere consegnata a 10 giorni dalla data odierna.

## <a name="ctp-calculations"></a>Calcoli CTP

La funzionalità CTP ti consente di fornire ai clienti date realistiche per quando puoi promettere merci specifiche. Per ogni riga di vendita, puoi fornire una data che tenga conto delle scorte disponibili, della capacità di produzione e dei tempi di trasporto esistenti.

CTP estende la funzionalità ATP prendendo in considerazione le informazioni sulla capacità. Mentre ATP prende in considerazione solo la disponibilità dei materiali e presuppone risorse di capacità infinite, CTP prende in considerazione la disponibilità di materiali e capacità. Pertanto, fornisce un quadro più realistico della possibilità di soddisfare la domanda entro un determinato intervallo di tempo.

CTP funziona in modo leggermente differente, a seconda del motore di pianificazione generale in uso (Ottimizzazione pianificazione o motore di pianificazione integrato). CTP per Ottimizzazione pianificazione supporta attualmente solo un sottoinsieme degli scenari CTP supportati dal motore integrato.

Per informazioni dettagliate su come impostare e usare le funzionalità CTP per ogni motore, vedi [Calcolare le date di consegna di ordini cliente utilizzando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
