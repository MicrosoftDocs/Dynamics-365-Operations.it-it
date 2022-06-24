---
title: Gestire le registrazioni
description: In questo articolo viene descritto come utilizzare le registrazioni. Una registrazione è in genere costituita dalle merci di un fornitore per un'entità o una azienda per spedizione. Le merci in una registrazione possono essere in un contenitore o distribuite tra più contenitori.
author: Weijiesa
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMFolioTable, ITMFolioTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 4cc556c47f7027f2f5d5b24c235b11ced63b3e4e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905894"
---
# <a name="manage-folios"></a>Gestire le registrazioni

[!include [banner](../../includes/banner.md)]

Una registrazione è spesso determinata dalle normative doganali. Può essere costituita dalle merci di un fornitore per un'entità o un'azienda per spedizione. Le merci in una registrazione sono gestite in un contenitore.

Per aprire la pagina **Tutti i viaggi**, selezionare **Costo sbarcato \> Registrazioni \> Tutte le registrazioni**. Questa pagina mostra un elenco di tutte le registrazioni correnti. È possibile utilizzare i pulsanti nel riquadro Azioni per creare, eliminare e utilizzare le registrazioni. Selezionare una registrazione nell'elenco per visualizzarne i dettagli nella pagina **Registrazioni**.

## <a name="action-pane"></a>Riquadro azioni

Il riquadro Azioni nelle pagine **Tutte le registrazioni** e **Registrazioni** include pulsanti che consentono di utilizzare una registrazione selezionata. Ogni pulsante esegue una singola azione. Il riquadro Azioni include anche schede, ognuna delle quali, a sua volta, fornisce una serie di pulsanti correlati. Tranne quando diversamente indicato, tutti i pulsanti e le schede descritti nelle sottosezioni seguenti sono disponibili sia nella visualizzazione elenco (ovvero, nella pagina **Tutte le registrazioni**) che nella visualizzazione dettagliata (ovvero, nella pagina **Registrazioni**).

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Pulsanti visualizzati direttamente nel riquadro Azioni

Nella seguente tabella sono descritti i pulsanti direttamente disponibili nel riquadro Azioni.

| Pulsante | Descrizione |
|---|---|
| Nuove | Consente di creare una registrazione. |
| Elimina | Elimina la registrazione aperta o selezionata. |
| Costi di viaggio | Apre la pagina **Costi di viaggio** dove è possibile visualizzare e aggiungere costi a livello di registrazione a tutte le merci del viaggio. Quando i costi della registrazione vengono aggiunti manualmente al viaggio, sono aggiunti automaticamente alla pagina della richiesta di informazioni sui costi e ripartiti tra le merci in base al metodo specificato nella pagina **Costi di viaggio**. |

### <a name="buttons-on-the-manage-tab"></a>Pulsanti della scheda Gestisci

Nella seguente tabella sono descritti i pulsanti disponibili nella scheda **Gestisci** del riquadro Azioni.

| Pulsante | Descrizione |
|---|---|
| Registra elenco entrate | Consente di registrare un elenco entrate per tutte le righe di ordine fornitore nella registrazione. Se si utilizzano spedizioni con più società, per ogni società viene aperta una nuova finestra di dialogo per la registrazione degli elenchi entrate. |
| Registra entrata prodotti | Consente di registrare un entrata prodotti per tutte le righe di ordine fornitore nella registrazione. In caso di viaggi con più società, per ogni società viene aperta una nuova finestra di dialogo per la registrazione delle entrate prodotti. |
| Registra fattura | Consente di registrare una fattura per tutte le righe di ordine fornitore nella registrazione. In caso di viaggi con più società, per ogni società viene aperta una nuova finestra di dialogo per la registrazione delle fatture. |
| Ordine di trasferimento spedizione | Consente di registrare un ordine di trasferimento per tutte le righe di ordine di trasferimento correlate alla registrazione corrente nella relativa spedizione. |
| Ricevi ordine di trasferimento | Consente di registrare un ricevimento dell'ordine di trasferimento per tutte le righe di ordine di trasferimento correlate alla registrazione corrente nella relativa spedizione. |
| Ricevi merci in transito | Consente di ricevere tutte le righe dell'ordine in transito nella registrazione. |
| Documenti ricevuti | Imposta l'opzione **Documenti ricevuti** su *Sì*. È possibile utilizzare questo pulsante per bloccare l'articolo e/o la riga di acquisto di modo che non possa essere aggiornato ulteriormente. |
| Trova costi automatici | Consente di trovare costi di viaggio pertinenti. Se questi costi sono già stati trovati o aggiornati, viene visualizzato il seguente messaggio: "Esistono righe di costo non fatturate. Sovrascriverle? Da notare che i costi di viaggio associati alla registrazione e che sono stati fatturati non verranno sovrascritti. |
| Crea giornale di registrazione arrivi | Consente di generare un giornale di registrazione arrivi per le organizzazioni utilizzando funzionalità di magazzino avanzate. È possibile selezionare **Inizializza quantità** (consigliata) e **Crea da merci in transito** e/o **Crea da ordini fornitore**. L'ultima opzione dipende dall'utilizzo o meno dell'elaborazione merci in transito. |
| Attribuisci costi | Consente di attribuire costi quando un tipo di costo include un conto CoGe specificato per l'addebito. Questo pulsante viene generalmente utilizzato quando le scorte sono in transito o dopo che le merci sono state ricevute e fatturate. |

### <a name="buttons-on-the-general-tab"></a>Pulsanti della scheda Generale

Nella seguente tabella sono descritti i pulsanti disponibili nella scheda **Generale** del riquadro Azioni.

| Pulsante | Descrizione |
|---|---|
| Elenco entrate | Consente di registrare un elenco entrate per tutte le righe di ordine fornitore nella registrazione. In caso di viaggi con più società, per ogni società viene aperta una nuova finestra di dialogo per la registrazione degli elenchi entrate. |
| Entrata prodotti | Visualizza il record dell'entrata prodotti, se utilizzato. |
| Arrivo articoli | Visualizza il giornale di registrazione arrivi articoli, se utilizzato. |
| Richiesta di informazioni sui costi | Apre la pagina della richiesta di informazioni dei costi per visualizzare tutti i costi di un viaggio, inclusi il contenitore di spedizione, la registrazione e l'ordine fornitore. È possibile modificare la visualizzazione esatta della pagina utilizzando l'azione Visualizza. Nella pagina della richiesta di informazioni sui costi, è possibile visualizzare una qualsiasi delle aree, più l'articolo e il codice di tipo di costo. Rimuovendo questi articoli, è possibile modificare la pagina raggruppando i costi. Questa funzionalità può essere utile se si utilizzano dimensioni e colori. È possibile modificare le dimensioni visualizzate nella pagina. La pagina **Costi** mostra solo i codici di tipo di costo in cui il campo **Dr** nella scheda **Registrazione** è impostato su *Articolo*. |

## <a name="header-view"></a>Visualizzazione intestazione

Per aprire la visualizzazione **Intestazione**, aprire una registrazione, quindi selezionare la scheda **Intestazione** in alto a destra nell'intestazione della registrazione.

### <a name="settings-on-the-general-fasttab"></a>Impostazioni nella Scheda dettaglio Generale

La tabella seguente descrive i campi disponibili nella Scheda dettaglio **Generale** nella visualizzazione **Intestazione** di una registrazione.

| Campo | Descrizione |
|---|---|
| Registrazione | Il nome della registrazione. Questo nome viene generato automaticamente quando viene creata la registrazione.|
| Viaggio | Il viaggio associato alla registrazione. |
| Broker doganale | Selezionare il broker doganale per la registrazione. I broker doganali sono definiti nel venditore. Consentono di determinare automaticamente i costi creati. |
| Lettera di vettura aerea/polizza di carico | Specificare la lettera di vettura aerea della casa o la polizza di carico che si applica alla registrazione. |
| Società | La persona giuridica associata alla registrazione. |
| Numero di controllo cargo | Questo campo viene utilizzato dai servizi doganali di alcuni paesi o regioni. |
| Misura | Questo campo consente di specificare una misura nel modulo **Costo sbarcato**. Le misure sono spesso utilizzate dalle organizzazioni che non conoscono il volume o il peso individuale delle merci, ma che richiedono una ripartizione più accurata di quella mediante le opzioni Importo e Quantità. Lo spedizioniere fornirà il peso o la misura cubica, a livello di articolo o di ordine fornitore. Può essere aggiornato automaticamente se il parametro viene selezionato o immesso manualmente. |
| Unità di misura | L'unità che si applica alla misura specificata. |
| Numero di cartoni | Il numero di cartoni nella registrazione. Questo campo può essere aggiornato automaticamente, a seconda della selezione del parametro. |
| Account fornitore | Selezionare il fornitore associato alla registrazione. Questo campo è fornito solo a scopo informativo. Non influisce su alcuna funzionalità. |
| Nome | Il nome del conto fornitore selezionato. |
| Note | Immettere eventuali ulteriori informazioni correlate alla registrazione. |
| Descrizione delle merci | Selezionare una descrizione delle merci per identificare più facilmente la registrazione. Per ulteriori informazioni, vedere [Descrizione delle merci](shipping-information-setup.md#description-of-goods). |
| Data valutazione | Questo campo è correlato alla pagina di immissione dei dazi. Il modulo **Costo sbarcato** utilizzerà il tasso di cambio doganale per la data impostata qui. Il valore predefinito è la data nella pagina di immissione dei dazi. |
| ID dogana | Immettere l'ID dogana. Questo ID viene fornito dai servizi doganali. |
| Codice tariffa | Immettere un codice tariffario da associare alla registrazione. Questo codice è in genere richiesto (e definito) dal paese o dalla regione di destinazione della spedizione. |

### <a name="settings-on-the-delivery-fasttab"></a>Impostazioni nella Scheda dettaglio Consegna

La tabella seguente descrive le impostazioni disponibili nella Scheda dettaglio **Consegna** della visualizzazione **Intestazione** di una registrazione.

| Campo | Descrizione |
|---|---|
| Data registrazione | Selezionare una data da associare alla registrazione. Il valore predefinito è la data di creazione del viaggio. |
| Data/ora di arrivo stimata al porto di spedizione | L'ora di arrivo stimata nel porto di destinazione. |
| Data di consegna stimata | Di solito, la data in cui le merci devono arrivare al magazzino. Questo campo non viene utilizzato quando la data di consegna stimata viene calcolata. (al suo posto viene utilizzata la data di consegna stimata del controllo di tracciabilità). Per impostare questo campo di modo che il valore corrisponda alla data di consegna stimata del controllo di tracciabilità, utilizzare il [Centro di controllo tracciabilità](delivery-information-setup.md#tracking-control-center). |
| Documenti originali ricevuti | La data in cui sono stati ricevuti i documenti originali. |
| Broker consigliato | La data in cui il broker è stato consigliato. |
| Polizza di carico originale inviata | La data in cui è stata inviata la polizza di carico originale. |
| Merci rilasciate | La data in cui le merci sono state rilasciate. |
| Appuntamento cliente | La data dell'appuntamento con il cliente. |
| Consegnato al magazzino | La data in cui le merci sono state consegnate al magazzino. |
| Data di verifica | La data di verifica. |
| Istruzioni di consegna | La data in cui sono state ricevute le istruzioni di consegna. |
| Porto di origine | Il porto da cui ha origine il viaggio. |
| Porto di destinazione | Il porto dove arriva il viaggio. Il contenitore di spedizione potrebbe avere un porto diverso poiché l'imbarcazione potrebbe fermarsi in più porti. |

### <a name="settings-on-the-export-fasttab"></a>Impostazioni nella Scheda dettaglio Esportazione

La tabella seguente descrive le impostazioni disponibili nella Scheda dettaglio **Esportazione** della visualizzazione **Intestazione** di una registrazione.

| Campo | Descrizione |
|---|---|
| Esportatore | L'esportatore può essere memorizzato nella registrazione. Nel commercio internazionale, si potrebbe inviare un ordine fornitore a una società ma ricevere la merce da un'altra società. Tracciabilità e documentazione sono richieste dalla dogana. Il nome e l'indirizzo dell'esportatore possono essere memorizzati qui. |
| Nome | Il nome dell'esportatore selezionato. |

## <a name="lines-view"></a>Visualizzazione Righe

Per aprire la visualizzazione **Righe**, aprire una registrazione, quindi selezionare la scheda **Righe** in alto a destra nell'intestazione della registrazione.

### <a name="information-on-the-folio-fasttab"></a>Informazioni nella Scheda dettaglio Registrazione

La Scheda dettaglio **Registrazione** nella visualizzazione **Righe** mostra le informazioni sulla registrazione. La maggior parte di queste informazioni appare anche nella visualizzazione **Intestazione**, come descritto in precedenza in questo articolo.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Informazioni e pulsanti nella Scheda dettaglio Righe

La Scheda dettaglio **Righe** nella visualizzazione **Righe** mostra i dettagli su ciascuna riga di ordine fornitore completa o parziale inclusa nella registrazione corrente.

Nella seguente tabella vengono descritti i pulsanti disponibili nella Scheda dettaglio **Righe** della visualizzazione **Righe**.

| Pulsante | Descrizione |
|---|---|
| Rimuovi | Consente di rimuovere la riga di ordine fornitore selezionata dal viaggio. |
| Magazzino \> Transazioni | Consente di visualizzare le transazioni di magazzino per la riga di ordine fornitore selezionata. Da notare che se si utilizzano merci in transito, vengono visualizzati anche l'ordine originale e gli ordini merci in transito. |
| Magazzino \> Visualizza dimensioni | Apre una finestra di dialogo in cui è possibile selezionare le dimensioni inventariali disponibili per le transazioni visualizzate. |
| Aggiornamento | Aggiorna le informazioni relative a importo, peso o volume della riga di ordine fornitore selezionata. |

### <a name="information-on-the-lines-details-fasttab"></a>Informazioni sulla Scheda dettaglio Dettagli righe

La Scheda dettaglio **Dettagli righe** nella visualizzazione **Righe** mostra informazioni sulla riga di ordine fornitore correntemente selezionata nella Scheda dettaglio **Righe**.
