---
title: Alternative di consegna
description: I dipendenti che gestiscono gli ordini cliente possono utilizzare la pagina Alternative di consegna per trovare opzioni alternative l'evasione dell'ordine.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 829775e36a2d49ebbab5c719436cff4c92984635
ms.sourcegitcommit: ca7fc46607ae9d07725e1486b43c66d39ec5cdb5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035268"
---
# <a name="delivery-alternatives"></a>Alternative di consegna

[!include [banner](../includes/banner.md)]

I dipendenti che gestiscono gli ordini cliente possono utilizzare la pagina **Alternative di consegna** per trovare opzioni alternative l'evasione dell'ordine.

Il layout della pagina **Alternative di consegna** offre una panoramica di tutte le opzioni alternative. Consente inoltre ai dipendenti che gestiscono gli ordini di effettuare un'analisi oltre la società corrente per individuare opportunità di evasione. È ora possibile visualizzare sia le opportunità interaziendali che le opportunità di fornitori esterni. Tramite l'ordinamento delle opzioni per data di consegna, dipendenti che gestiscono gli ordini cliente possono visualizzare un elenco di intelligente di alternative di consegna. Inoltre, i parametri consentono di gestire in modo migliore le consegne suggerite. Poiché il tempo di trasporto può influire sulle date di consegna, gli addetti agli ordini cliente possono esaminare le varie opzioni di trasporto che i vettori offrono. Per ogni suggerimento vengono mostrate informazioni dettagliate, gli addetti agli ordini cliente possono quindi prendere decisioni informate direttamente nella pagina **Alternative di consegna**.

## <a name="open-the-delivery-alternatives-page"></a>Aprire la pagina di Alternative di consegna

È possibile aprire la pagina **Alternative di consegna** della riga ordine cliente.

1. Selezionare **Prodotti e fornitura \> Alternative di consegna**.
1. Selezionare **Dettagli riga \> Consegna \> Alternative di consegna**.

È anche possibile aprire la pagina **Alternative di consegna** aprendo l'area di lavoro **Elaborazione e richiesta di informazioni ordini cliente** e selezionando **Ordini e preferiti \> Righe ordine ritardate \> Alternative di consegna** **Nota:** è possibile aprire la pagina **Alternative di consegna** solo se entrambe le seguenti condizioni sono state soddisfatte:

- Tutte le informazioni obbligatorie per la riga di vendita sono state specificate.
- Il campo **Controllo data di consegna** è impostato su un valore deverso da **Nessuno**.

## <a name="delivery-date-control-methods"></a>Metodi di controllo data di consegna

Il metodo di controllo della data di consegna determina le modalità secondo cui il sistema stabilisce le date di consegna, calcola le alternative di consegna e stabilisce le informazioni da visualizzare. Si noti che il controllo della data di consegna si basa sui calendari. Di conseguenza, i calendari seguenti possono influire sulla data di ricezione suggerita: calendario di magazzino, calendario di spedizione, calendario del fornitore e calendario del cliente. Nella seguente tabella viene descritto ogni metodo per il controllo della data di consegna.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Metodo</strong></td>
<td><strong>Descrizione</strong></td>
</tr>
<tr class="even">
<td><strong>Nessuna priorità</strong></td>
<td><ul>
<li>Le alternative di consegna per le righe di vendita non sono supportate. Questa opzione disattiva il controllo della data di consegna.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Lead time di vendita</strong></td>
<td><ul>
<li>Le alternative di consegna vengono calcolate in base al lead time di vendita predefinito. I giorni di trasporto vengono calcolati in base alla modalità di consegna.</li>
<li>Le alternative di consegna includono i magazzini con scorte disponibili e ordini di domanda/fornitura.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>ATP</strong></td>
<td><ul>
<li>Le alternative di consegna vengono calcolate in base a logica available-to-promise (ATP). Vengono considerate la disponibilità corrente e la disponibilità futura. I giorni di trasporto vengono calcolati in base alla modalità di consegna.</li>
<li>Le alternative di consegna includono i magazzini con scorte disponibili e ordini di domanda/fornitura.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>ATP + margine su uscita magazzino</strong></td>
<td><ul>
<li>Le alternative di consegna vengono calcolate come per il metodo di calcolo ATP, ma il margine su uscita da magazzino viene incluso nel calcolo.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>CTP</strong></td>
<td><ul>
<li>Le alternative di consegna vengono calcolate in base a logica capable-to-promise (CTP). L'esplosione MRP viene utilizzata per determinare la disponibilità. Tenere presente che, al minimo, CTP imposta le date di consegna al lead time di vendita. I giorni di trasporto vengono calcolati in base alla modalità di consegna.</li>
<li>Le date di consegna alternative includono suggerimenti per i magazzini seguenti:
<ul>
<li>Magazzino corrente</li>
<li>Magazzino predefinito</li>
<li>Tutti i magazzini con scorte disponibili</li>
<li>Tutti i magazzini con ordini di fornitura</li>
<li>Tutti i magazzini con versioni attive della distinta base (BOM)</li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a>Visualizzare informazioni sulle alternative di consegna

In questa sezione vengono descritte le informazioni sulle alternative di consegna disponibili in ogni Scheda dettaglio della pagina **Alternative di consegna**.

### <a name="the-product-fasttab"></a>Scheda dettaglio Prodotto

In questa Scheda dettaglio viene visualizzato un riepilogo dei prodotti e i dettagli della riga di vendita corrente.

### <a name="the-delivery-alternatives-fasttab"></a>Scheda dettaglio Alternative di consegna

La Scheda dettaglio consente di visualizzare un elenco di alternative di consegna ordinate per data di ricezione. Sopra l'elenco, è possibile selezionare le opzione in base alla quale visualizzare i suggerimenti. È inoltre possibile selezionare la modalità di consegna, che determina i giorni di spedizione. Sono disponibili le seguenti opzioni:

- **Includi altre varianti prodotto** - Questa opzione è disponibile per i prodotti con varianti prodotto. verranno incluse le alternative di consegna per altre varianti prodotto. Questa opzione non è disponibile per CTP.
- **Includi quantità parziale** - Per impostazione predefinita, vengono inclusi solo i suggerimenti che soddisfano l'intera quantità della riga cliente. Selezionare questa opzione per includere i suggerimenti che soddisfano solo parzialmente la riga di vendita. Questa opzione è utile quando il cliente richiede una data più vicina e accetta la consegna parziale.
- **Includi date successive** - Per impostazione predefinita, vengono mostrati solo i suggerimenti migliori (precedenti) rispetto alle date correnti nella riga di vendita. Selezionare questa opzione per includere le dati successive. Questa opzione può risultare utile nelle situazioni in cui parametri diversi dalla data hanno priorità. Ad esempio, un fornitore o un magazzino specifico può essere preferito.
- **Modalità di consegna** - Selezionare la modalità di consegna preferita per ottimizzare il tempo e costo di trasporto. L'effetto sarà immediatamente visualizzato nelle alternative di consegna suggerite. Di conseguenza, è facile confrontare le alternative.
- **Includi approvvigionamento** - Quando è selezionato l'approvvigionamento, le alternative di consegna suggerite includono opzioni relative sia ai fornitori esterni che ad altre società dell'impresa (interaziendale). L'opzione **Includi approvvigionamento** è supportata per il controllo delle date di consegna ATP e ATP + margine su uscita magazzino. Vengono incluse le opzioni di approvvigionamento del fornitore acquisti predefinito per il prodotto e di tutti i fornitori approvati per il prodotto.
- Per i fornitori esterni, il calcolo è basato sul lead time di acquisto.
- Per gli ordini interaziendali, il calcolo prende in considerazione i prodotti disponibili dalla società di approvvigionamento, in base al controllo della data di consegna nella società di approvvigionamento.
- **Tipo di consegna** (Rilevante per l'approvvigionamento)
  - **Scorte** - I prodotti vengono spediti dal magazzino di approvvigionamento al sito/magazzino nella riga di vendita. Vengono quindi spediti da tale magazzino al cliente.
  - **Consegna diretta** - I prodotti devono essere inviati direttamente dal magazzino di approvvigionamento al cliente.

### <a name="the-availability-information-fasttab"></a>Scheda dettaglio Informazioni sulla disponibilità

Le informazioni contenute in questa Scheda dettaglio sono correlate alla riga alternativa di consegna selezionata. Vengono indicate le seguenti informazioni, a seconda del controllo della data di consegna per la riga ordine:

- **Lead time di vendita**
  - **Disponibile oggi** - Mostra le scorte fisiche attualmente disponibili, la qtà fisica prenotata e la qtà fisica disponibile.
  - **Parametri** - Mostra il lead time di vendita e l'unità di magazzino.

- **ATP e ATP + Margine su uscita da magazzino**
  - **Disponibile oggi** - Mostra le scorte fisiche attualmente disponibili, la qtà fisica prenotata e la qtà fisica disponibile.
  - **Parametri** - Mostra il lead time di vendita e l'unità di magazzino.
  - **Disponibilità futura** - Mostra una rappresentazione grafica della disponibilità corrente e futura per il sito e il magazzino selezionati in **Alternative di consegna**. È possibile selezionare le colonne del grafico per visualizzare informazioni più dettagliate sulla futura disponibilità del prodotto. Il cursore mostra un elenco degli ordini di fornitura rilevanti e della domanda in un intervallo temporale ATP.

- **CTP**
  - **Disponibile oggi** - Mostra le scorte fisiche attualmente disponibili, la qtà fisica prenotata e la qtà fisica disponibile.
  - **Parametri** - Mostra il lead time di vendita e l'unità di magazzino.
  - **Esplosione** - Mostra un'esplosione della fornitura per l'alternativa di consegna selezionata. È possibile utilizzare le **impostazioni** per modificare i campi e le dimensioni inventariali che vengono visualizzati nell'esplosione.

### <a name="the-impact-of-selected-alternative-fasttab"></a>Scheda dettaglio Impatto dell'alternativa selezionata

Questa Scheda dettaglio evidenzia l'impatto dell'alternativa di consegna selezionata. Se si seleziona **OK**, la riga di vendita viene aggiornata con i valori evidenziati nelle colonne SELEZIONATE. Si noti che, se la quantità dell'alternativa di consegna selezionata è inferiore alla quantità delle righe di vendita, viene creata una programmazione consegna e la riga ordine viene divisa in due righe: una riga per la quantità selezionata e una riga per la quantità rimanente. È inoltre possibile aggiornare la riga commerciale in modo che corrisponda alle righe di programmazione che influiscono sulla valutazione.

## <a name="additional-resources"></a>Risorse aggiuntive

[Promesse ordine](delivery-dates-available-promise-calculations.md)
