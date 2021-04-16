---
title: Gestire i viaggi
description: In questo argomento viene descritto come utilizzare i viaggi. Un viaggio rappresenta in genere un'imbarcazione. Tuttavia, a seconda delle pratiche e delle procedure, può rappresentare un fornitore, un ordine fornitore o qualche altro elemento che abbia senso per l'organizzazione.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMTableListPage, ITMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 0b1414efbdde77af5d7fa15ff066e4ddcfd6bad2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833787"
---
# <a name="manage-voyages"></a>Gestire i viaggi

[!include [banner](../../includes/banner.md)]

Un viaggio rappresenta in genere un'imbarcazione. Tuttavia, a seconda delle pratiche e delle procedure, può rappresentare un fornitore, un ordine fornitore o qualche altro elemento che abbia senso per l'organizzazione.

La pagina **Tutti i viaggi** fornisce dettagli sui viaggi, informazioni su consegne e costi e informazioni su articoli, ordini fornitore e ordini di trasferimento. Per aprire la pagina **Tutti i viaggi**, selezionare **Costo sbarcato \> Viaggi \> Tutti i viaggi**. Questa pagina mostra un elenco di tutti i viaggi correnti. È possibile utilizzare i pulsanti nel riquadro Azioni per creare, eliminare e utilizzare i viaggi. Selezionare un viaggio nell'elenco per visualizzarne i dettagli.

> [!NOTE]
> Le registrazioni e i contenitori di spedizione sono collegati a un viaggio. Le righe di acquisto sono collegate a un contenitore di spedizione. Se le registrazioni e i contenitori di spedizione sono disattivati, possono anche essere collegati direttamente a un viaggio. Inoltre, i costi immessi qui vengono ripartiti tra tutte le righe di acquisto associate.

## <a name="action-pane"></a>Riquadro azioni

Il riquadro azioni della pagina **Viaggi** include pulsanti che consentono di utilizzare un viaggio selezionato. Ogni pulsante esegue una singola azione. Il riquadro Azioni include anche schede, ognuna delle quali, a sua volta, fornisce una serie di pulsanti correlati. Salvo diversamente indicato, tutti i pulsanti e le schede sono disponibili sia nella visualizzazione elenco della pagina **Tutti i viaggi**, sia nella vista dettagliata per un singolo viaggio selezionato.

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Pulsanti visualizzati direttamente nel riquadro Azioni

Nella seguente tabella sono descritti i pulsanti direttamente disponibili nel riquadro Azioni.

| Pulsante | Descrizione |
|---|---|
| Nuovo | Consente di creare un viaggio. <!-- KFM: Link to scenario --> |
| Elimina | Consente di eliminare il viaggio corrente. Solo i viaggi il cui stato è *Confermato* possono essere eliminati. Dopo che un viaggio lascia il porto ed elabora le merci in transito, non può più essere eliminato. |
| Editor viaggio | Apre la pagina **Editor viaggio** dove è possibile aggiungere o rimuovere righe di acquisto per il viaggio, creare nuovi contenitori e modificare i dettagli del viaggio stesso. |
| Costi di viaggio | Apre la pagina **Costi di viaggio** dove è possibile visualizzare e aggiungere costi di viaggio a tutte le merci del viaggio. Quando i costi di viaggio vengono aggiunti manualmente al viaggio, sono aggiunti automaticamente alla pagina **Richiesta di informazioni sui costi** e ripartiti a ogni merce secondo il metodo specificato nella pagina **Costi di viaggio**. |

### <a name="buttons-on-the-voyage-tab"></a>Pulsanti nella scheda Viaggio

Nella seguente tabella sono descritti i pulsanti disponibili nella scheda **Viaggio** del riquadro Azioni. Questa scheda è disponibile solo con la visualizzazione elenco della pagina **Tutti i viaggi**.

| Pulsante | Descrizione |
|---|---|
| Contenitore di spedizione | Apre una pagina che mostra tutti i contenitori di spedizione associati al viaggio selezionato. Può visualizzare uno o più contenitori. |
| Registrazione | Apre una pagina che mostra tutte le registrazioni associata al viaggio selezionato. Può visualizzare una o più registrazioni. |

### <a name="buttons-on-the-manage-tab"></a>Pulsanti della scheda Gestisci

Nella seguente tabella sono descritte le azioni disponibili nella scheda **Gestisci** del riquadro Azioni.

| Pulsante | Descrizione |
|---|---|
| Documenti ricevuti | Aggiorna il viaggio di modo che l'opzione **Documenti ricevuti** sia impostata su *Sì*. È possibile utilizzare questo pulsante per bloccare l'articolo e/o la riga di acquisto di modo che non possa essere aggiornato ulteriormente. |
| In transito | Aggiorna il campo **Stato viaggio** allo stato In transito stabilito nella pagina **[Parametri di costo sbarcato](landed-cost-parameters.md)**. Non c'è ulteriore logica in questo processo. Un viaggio può anche essere aggiornato automaticamente allo stato in transito, in base alle impostazioni nel [Centro di controllo tracciabilità](delivery-information-setup.md).
| Pronto per determinazione costi | Aggiorna il campo **Stato viaggio** allo stato Pronto per determinazione costi nella pagina **[Parametri di costo sbarcato](landed-cost-parameters.md)**. È possibile preventivare il costo di un viaggio quando tutte le fatture sono state elaborate (sia le fatture scorte che le fatture costo di viaggio) e le merci sono state ricevute. Se i costi stimati associati a un viaggio non sono stati preventivati, si verifica un errore quando si tenta di elaborare il costo di un viaggio. |
| Preventivato | Elimina eventuali irregolarità nei costi dopo la creazione di una fattura per tutti gli ordini fornitore e i costi di viaggio. Quando si seleziona questo pulsante, viene visualizzata la finestra di dialogo **Aggiornamento viaggio - Preventivato**. Nella finestra di dialogo, è possibile registrare la data finanziaria standard o specificare una data di registrazione e quindi eseguire l'azione. È possibile rieseguire l'azione tutte le volte che si vuole. È anche possibile usare la finestra di dialogo **Aggiornamento viaggio - Preventivato** allo scopo di stabilire una pianificazione per eseguire l'azione come attività periodica (processo batch). Si consiglia di eseguire regolarmente l'azione configurandola come processo batch. |
| Registra elenco entrate | Consente di registrare un elenco di entrate per tutte le righe di ordine fornitore nel viaggio. In caso di viaggi con più società, viene aperta una nuova finestra di dialogo per la registrazione dell'elenco entrate per ciascuna società, che deve essere elaborata in ogni persona giuridica. |
| Registra entrata prodotti | Consente di registrare un entrata prodotti per tutte le righe di ordine fornitore nel viaggio. Il processo di entrata prodotti per le righe di ordine fornitore associate a un viaggio verrà utilizzato solo se per le merci **non** viene eseguita un'elaborazione merci in transito. Se per le merci viene eseguita un'elaborazione merci in transito, viene visualizzato un errore quando si tenta di registrare l'entrata prodotti per una riga di ordine fornitore. In caso di viaggi con più società, viene aperta una nuova finestra di dialogo per la registrazione della bolla di consegna per ciascuna società. |
| Registra fattura | Consente di registrare una fattura per tutte le righe di ordine fornitore nel viaggio. Se per le merci del viaggio non viene eseguita un'elaborazione merci in transito, le righe di ordine fornitore verranno fatturate prima dell'esecuzione del processo di ricevimento. Quando l'ordine fornitore originale viene fatturato, verranno creati ordini di merci in transito associati alle righe dell'ordine fornitore originale. Tali ordini possono quindi essere ricevuti dal magazzino. Se si utilizzano spedizioni con più società, per ogni società viene aperta una nuova finestra di dialogo per la registrazione delle fatture. |
| Ordine di trasferimento spedizione | Consente di registrare un viaggio dell'ordine di trasferimento per tutte le righe dell'ordine di trasferimento nel viaggio. Quando questo pulsante è selezionato, solo gli ordini di trasferimento saranno disponibili per l'aggiornamento. |
| Ricevi ordine di trasferimento | Consente di registrare un ricevimento dell'ordine di trasferimento per tutte le righe dell'ordine di trasferimento nel viaggio. |
| Ricevi merci in transito | Consente di ricevere tutte le righe dell'ordine in transito nel viaggio. Questo pulsante è una delle tre opzioni disponibili per ricevere merci in transito di un viaggio. (Le altre due opzioni sono il pulsante **Crea giornale di registrazione arrivi** descritto più avanti in questa tabella e nell'app per dispositivi mobili Gestione magazzino). Questa opzione è la più semplice ed elaborerà le merci in transito che non sono nel magazzino merci in transito e nel magazzino di destinazione finale. Se si desidera un maggiore controllo sul processo, utilizzare il giornale di registrazione arrivi o un dispositivo mobile per elaborare il ricevimento delle merci. |
| Trova costi automatici | Consente di trovare eventuali costi di viaggio pertinenti. Se questi costi sono già stati trovati o aggiornati, viene visualizzato il seguente messaggio: "Esistono righe di costo non fatturate. Sovrascriverle? Verranno rilevati tutti i costi che non erano associati al viaggio al momento della creazione. I costi di viaggio associati a un viaggio che sono stati fatturati non verranno sovrascritti. |
| Crea giornale di registrazione arrivi | <p>Apre la finestra di dialogo **Crea giornale di registrazione arrivi**, in cui è possibile creare un giornale di registrazione arrivi che specifica un'ubicazione. La finestra di dialogo include le opzioni seguenti:</p><ul><li>**Crea da merci in transito** o **Crea da ordine di trasferimento** - L'etichetta di questa opzione cambia a seconda che si stia utilizzando o meno il processo di merci in transito. Impostarla su *Sì* per aprire una pagina del giornale di registrazione arrivi che consente di elaborare un giornale di registrazione arrivi standard per le merci in transito associate al viaggio. Se l'articolo è già stato ricevuto nel magazzino di destinazione finale, non verrà aggiunto alle righe del giornale di registrazione arrivi.</li><li>**Inizializza quantità** - Impostare questa opzione su *Sì* per inizializzare la quantità che verrà ricevuta, in base alla quantità di merci specificata nella riga di viaggio. Se la riga di viaggio è stata ricevuta parzialmente, questa quantità sarà la quantità rimanente. È consigliabile impostare questa opzione su *Sì*.</li><li>**Crea da righe ordine** - Impostare questa opzione su *Sì* per ottenere il valore dalle righe dell'ordine.</li></ul><p>Questo pulsante è una delle tre opzioni disponibili per ricevere merci di un viaggio (Le altre opzioni sono il pulsante **Ricevi merci in transito** descritto in precedenza in questa tabella e l'app per dispositivi mobili Gestione magazzino.)</p> |
| Attribuisci costi | È possibile attribuire costi quando un tipo di costo include un conto CoGe specificato per l'addebito. Questo pulsante viene generalmente utilizzato quando le scorte sono in transito o dopo che le merci sono state ricevute e fatturate. |
| Aggrega costi | Consente di spostare i costi dal livello contenitore di spedizione al livello viaggio. Si potrebbe utilizzare questo pulsante in uno scenario di servizi/spedizioni condivisi, in cui più entità condividono lo spazio di un contenitore di spedizione o di uno scatolone. Ad esempio, il viaggio comporta un contenitore di spedizione di 40 piedi e un contenitore di spedizione di 20 piedi e la ripartizione viene effettuata in base al volume. In questo caso, le merci/entità che condividono o utilizzano lo spazio nel contenitore di spedizione di 20 piedi potrebbero essere penalizzate. Per distribuire equamente i costi, alcune organizzazioni potrebbero voler trasferire i costi al viaggio e distribuirli in base al metodo di ripartizione a livello di viaggio. |
| Cambia modello di percorso | Apre una finestra di dialogo in cui è possibile modificare il modello di percorso. Dopo la modifica del modello, i costi di viaggio verranno eliminati. Pertanto, potrebbe essere necessario selezionare **Trova costi automatici** (vedere la descrizione in precedenza in questa tabella) o aggiungere di nuovo i costi manualmente. |

### <a name="buttons-on-the-general-tab"></a>Pulsanti della scheda Generale

Nella seguente tabella sono descritti i pulsanti disponibili nella scheda **Generale** del riquadro Azioni.

| Pulsante | Descrizione |
|---|---|
| Elenco entrate | Apre un elenco di entrate prodotti per tutte le righe di ordine fornitore nel viaggio. In caso di viaggi con più società, viene aperto un nuovo elenco di entrate per ciascuna società. Se nessun elenco di entrate prodotti è stato elaborato, questo pulsante non è disponibile. |
| Entrata prodotti | Apre il record di entrata prodotti per le righe dell'ordine fornitore associate al viaggio, se viene utilizzato tale record. Se nessuna entrata prodotti è stata registrata, questo pulsante non è disponibile. Il processo di entrata prodotti non verrà utilizzato se si utilizza l'elaborazione merci in transito. |
| Arrivo articoli | Apre il giornale di registrazione arrivi di articoli, se utilizzato. |
| Tracciabilità | Apre la pagina **Tracciabilità in entrata**, in cui è possibile aggiornare la data di arrivo prevista delle merci in un contenitore di spedizione e in un viaggio e quindi aggiornare le date di consegna previste delle righe dell'ordine fornitore. |
| Richiesta di informazioni sui costi | <p>Apre la pagina **Richiesta di informazioni sui costi**, che mostra tutti i costi di un viaggio.</p><p>Nel riquadro azioni, selezionare **Visualizza** per modificare la visualizzazione. È possibile visualizzare uno qualsiasi dei livelli, oltre al codice di articolo e di tipo di costo.</p><p>Solo i codici di tipo di costo direttamente correlati alle transazioni di magazzino vengono visualizzati nella pagina **Richiesta di informazioni sui costi**. Rimuovendo i codici di tipo di costo, è possibile modificare la pagina raggruppando i costi. Questa funzionalità può essere utile se si utilizzano dimensioni e colori.</p><p>La pagina **Richiesta di informazioni sui costi** mostra solo i codici di tipo di costo in cui il campo **Dare** è impostato su *Articolo*.</p> |
| Ordini merci in transito | Apre la pagina **Ordini merci in transito**, che mostra i record di merci in transito solo per il viaggio selezionato. |

## <a name="lines-view"></a>Visualizzazione Righe

Per aprire la visualizzazione **Righe**, aprire un viaggio, quindi selezionare la scheda **Righe** in alto a destra nell'intestazione del viaggio.

### <a name="information-on-the-voyage-header-fasttab"></a>Informazioni sulla Scheda dettaglio Intestazione viaggio

La Scheda dettaglio **Intestazione viaggio** nella visualizzazione **Righe** contiene le informazioni di base che descrivono il viaggio. Molti dei campi visualizzati in questa Scheda dettaglio compaiono anche nella visualizzazione **Intestazione**, come descritto più avanti in questo argomento.

### <a name="information-on-the-voyage-lines-fasttab"></a>Informazioni sulla Scheda dettaglio Righe viaggio

La Scheda dettaglio **Righe di viaggio** nella visualizzazione **Righe** di un viaggio è correlata ai dettagli del viaggio e alle informazioni sui costi che si applicano a livello di viaggio. In questa Scheda dettaglio è possibile esaminare contenitori di spedizione, registrazioni e articoli associati al viaggio. Sono inoltre visualizzati il prezzo e la quantità degli articoli del viaggio. È possibile visualizzare qualsiasi contenitore di spedizione o registrazione elencato selezionando il collegamento pertinente.

### <a name="information-on-the-line-details-fasttab"></a>Informazioni sulla Scheda dettaglio Dettagli riga

La Scheda dettaglio **Dettagli righe** nella visualizzazione **Righe** di un viaggio fornisce ulteriori informazioni sulla riga correntemente selezionata nella Scheda dettaglio **Righe viaggio**. Si noti che questa Scheda dettaglio include dettagli sulla posizione che ogni riga occupa nel contenitore e la relativa quantità dichiarata.

## <a name="header-view"></a>Visualizzazione intestazione

Per aprire la visualizzazione **Intestazione**, aprire un viaggio, quindi selezionare la scheda **Intestazione** in alto a destra nell'intestazione del viaggio.

### <a name="settings-on-the-general-fasttab"></a>Impostazioni nella Scheda dettaglio Generale

La tabella seguente descrive i campi disponibili nella Scheda dettaglio **Generale** nella visualizzazione **Intestazione** di un viaggio.

| Campo | Descrizione |
|---|---|
| Viaggio | Immettere il numero di viaggio o di volo. |
| Riferimento prenotazione | Se il mittente o il centro di spedizione fornisce un numero di riferimento per identificare il viaggio (ovvero il riferimento interno del mittente o del centro di spedizione), immetterlo qui. |
| Imbarcazione | Immettere o selezionare l'imbarcazione. Se l'imbarcazione non è elencata come valore, è possibile inserire l'ID imbarcazione come testo libero. In tal caso, la tabella principale non viene aggiornata di modo che l'ID imbarcazione possa essere selezionato in questo campo in un secondo momento. |
| ID viaggio esterno | Immettere l'ID disponibile pubblicamente per il viaggio (come il numero del volo). |
| Lettera di vettura aerea generale/polizza di carico | Immettere il numero della lettera di vettura aerea principale o della polizza di carico. È possibile specificare questo valore quando si esegue la spedizione per via aerea. |
| Lettera di vettura aerea/polizza di carico | Immettere la lettera di vettura aerea o la polizza di carico per il contenitore di spedizione. |
| Noleggio | Selezionare questa casella di controllo per indicare che il contenitore è un contenitore a noleggio che deve essere restituito. |
| Descrizione | Immettere una descrizione del viaggio per facilitarne il riconoscimento. |
| Stato viaggio | Lo stato del viaggio. I valori sono *Creato*, *In transito*, *Documenti ricevuti* e *Preventivato*. Questo campo non è calcolato in base alla logica. Viene aggiornato solo tramite l'azione di registrazione. Il valore *Preventivato* indica che è stata ricevuta una fattura per lo stock e tutti i costi di viaggio. A meno che non venga ricevuta una fattura, un viaggio non può avere lo stato *Preventivato*. |
| Stato ordine fornitore | Lo stato più elevato raggiunto tra tutti gli ordini fornitore associati al viaggio. |
| Documenti ricevuti | Un valore che indica se l'azienda ha ricevuto tutti i documenti associati al viaggio. Per modificare il valore, selezionare **Documenti ricevuti** nel gruppo **Aggiornamento viaggio** della scheda **Gestisci** del riquadro Azioni. |
| Società di spedizione | Selezionare la società di spedizione per questo viaggio. Questo campo può essere utilizzato per determinare i costi automatici. |
| Nome | Il nome della società selezionato nel campo **Società di spedizione**. |
| Misura | Questo campo consente di specificare una misura in un costo automatico. Le misure sono spesso utilizzate dalle organizzazioni che non conoscono il volume o il peso individuale delle merci, ma che richiedono una ripartizione più accurata di quella mediante le opzioni Importo e Quantità. Lo spedizioniere fornirà il peso o la misura cubica, a livello di articolo o di ordine fornitore. Può essere aggiornato automaticamente se il parametro è selezionato, oppure può essere immesso manualmente. |
| Unità di misura | L'unità di misura che si applica al valore nel campo **Misura**. |
| Numero di pallet | Specificare il numero di pallet nella riga di viaggio. Questo campo viene aggiornato automaticamente se l'opzione **Aggiorna automaticamente il numero di cartoni** è impostata su *Sì* nella scheda **Generale** della pagina **Parametri di costo sbarcato**. |

### <a name="settings-on-the-delivery-fasttab"></a>Impostazioni nella Scheda dettaglio Consegna

La tabella seguente descrive i campi disponibili nella Scheda dettaglio **Consegna** nella visualizzazione **Intestazione** di un viaggio.

| Campo | Descrizione |
|---|---|
| Data e ora creazione | La data e l'ora in cui è stato creato il viaggio. |
| Data franco fabbrica | Questo campo seleziona la prima data franco fabbrica tra gli ordini fornitore collegati al viaggio. La data franco fabbrica è disponibile nell'intestazione dell'ordine fornitore e viene aggiornata utilizzando la funzionalità di controllo della tracciabilità. |
| Data di spedizione | La data stimata in cui l'aereo o l'imbarcazione lascia il punto di origine. |
| Data di partenza | La data di partenza è solitamente la data in cui l'aereo o l'imbarcazione lascia effettivamente il porto d'oltremare. La data di spedizione e la data di partenza non devono coincidere. Il campo **Data di partenza** è presente solo a scopo informativo. Non viene utilizzato per stimare la data di consegna prevista. La funzionalità di controllo della tracciabilità viene utilizzata per stimare la data di consegna prevista e questo campo può essere impostato di modo che venga compilato automaticamente dalla funzione di controllo della tracciabilità. |
| Data ingresso punto vendita | Questo campo seleziona la prima data in cui le merci degli ordini fornitore collegati al viaggio saranno disponibili per la vendita. |
| Data di consegna stimata | La data di consegna stimata è solitamente la data in cui la merce deve arrivare nel magazzino. Questo campo è fornito solo a scopo informativo. Non viene utilizzato per la pianificazione generale delle merci. La data di consegna prevista nella riga dell'ordine fornitore viene utilizzata per la pianificazione generale delle merci in un viaggio e viene aggiornata utilizzando la funzionalità di controllo della tracciabilità. Questo campo può essere impostato in modo che venga compilato dalla funzionalità di controllo della tracciabilità. |
| Data di consegna effettiva | La prima data di consegna, in base alle merci collegate al viaggio. |
| Data/ora di arrivo stimata al porto di spedizione | Immettere la data di arrivo prevista del viaggio al porto di spedizione, in base alle informazioni fornite dallo spedizioniere. |
| Documenti originali ricevuti | Immettere la data in cui sono stati ricevuti i documenti originali. |
| Broker consigliato | Immettere la data in cui il broker è stato consigliato. |
| Polizza di carico originale inviata | Immettere la data in cui è stata inviata la polizza di carico originale. |
| Merci rilasciate | Immettere la data in cui le merci sono state rilasciate dalla dogana. |
| Appuntamento cliente | Immettere la data dell'appuntamento del cliente, ovvero la data in cui si prevede che il cliente assumerà la proprietà delle merci. |
| Consegnato al magazzino | Immettere la data in cui le merci sono state consegnate al magazzino. |
| Data di verifica | Immettere la data di verifica. |
| Istruzioni di consegna | Immettere la data in cui sono state ricevute le istruzioni di consegna. |
| Modalità di consegna | Questo campo fornisce informazioni sul metodo utilizzato per consegnare il viaggio e la selezione dei costi automatici associati a tale metodo di consegna. |
| Porto di origine | Il porto da cui ha origine il viaggio. |
| Porto di destinazione | Il porto dove arriva il viaggio. I contenitori di spedizione possono avere porti diversi, perché l'imbarcazione potrebbe fermarsi in più porti. Verificando il porto di destinazione a livello di contenitore di spedizione, si forniscono dettagli precisi sul porto per ogni contenitore di spedizione di un viaggio. Il costo automatico associato al trasporto viene determinato in base alla combinazione del tipo di contenitore di spedizione, del porto di destinazione e del porto di origine. |
| Spedizioniere locale | Questo campo è fornito solo a scopo informativo. Lo spedizioniere locale deve essere selezionabile nella tabella dei fornitori. |
| Data trasporto locale | La data per la quale è prenotato il trasporto locale. Questo campo può aiutare il magazzino a eseguire la pianificazione. |
| Ora trasporto locale | La fascia oraria per la quale è prenotato il trasporto locale. Questo campo può aiutare il magazzino a eseguire la pianificazione. |
| Modello di percorso | Il modello di percorso specificato per il viaggio. Il modello di percorso viene utilizzato per immettere il porto di destinazione e il porto di origine del contenitore di spedizione e del viaggio. Questi valori, a loro volta, aiutano a identificare i costi automatici associati al viaggio. |

### <a name="settings-on-the-other-fasttab"></a>Impostazioni nella Scheda dettaglio Altro

La tabella seguente descrive i campi disponibili nella Scheda dettaglio **Altro** nella visualizzazione **Intestazione** di un viaggio.

| Campo | Descrizione |
|---|---|
| Note | Immettere ulteriori informazioni correlate al viaggio. |
| Data valutazione | Selezionare la prima data franco fabbrica per gli ordini fornitore collegati al viaggio. |
| Viaggio in sospeso | Può essere utilizzato per indicare se la spedizione o il viaggio è già partita o meno. Viene fornita solo a scopo informativo.  |
| Ridenominazione dei contenitori di spedizione | Per i viaggi che hanno più contenitori, il numero di contenitori che non sono stati ancora ricevuti. |

## <a name="voyage-update-periodic-tasks"></a>Attività periodiche di aggiornamento del viaggio

Il modulo **Costo sbarcato** include diverse attività periodiche relative al viaggio che possono aggiornare in blocco diversi aspetti dei viaggi. Per eseguire o pianificare queste attività periodiche, selezionare **Costo sbarcato \> Attività periodiche \> Aggiornamenti viaggio**, quindi selezionare uno dei seguenti tipi di attività:

- **Documenti ricevuti** - Questa attività consente di impostare **Documenti ricevuti** su *Sì* per più viaggi contemporaneamente. Usare le impostazioni **Filtro** per definire l'insieme di viaggi che si desidera aggiornare.
- **In transito** - Questa attività consente di impostare il campo **Stato viaggio** sullo stato In transito definito nella pagina **[Parametri di costo sbarcato](landed-cost-parameters.md)** per più viaggi contemporaneamente. Usare le impostazioni **Filtro** per definire l'insieme di viaggi che si desidera aggiornare.
- **Pronto per determinazione costi** - Questa attività consente di impostare il campo **Stato viaggio** sullo stato Pronto per determinazione costi definito nella pagina **[Parametri di costo sbarcato](landed-cost-parameters.md)** per più viaggi contemporaneamente. In genere si configura questa attività affinché venga eseguita regolarmente.
- **Preventivato** - Questa attività consente di impostare il campo **Stato viaggio** sullo stato Preventivato definito nella pagina **[Parametri di costo sbarcato](landed-cost-parameters.md)** per più viaggi contemporaneamente, a condizione che siano stati preventivati ma non ancora aggiornati nel viaggio. In genere si configura questa attività affinché venga eseguita regolarmente.
