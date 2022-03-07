---
title: Consolidare le spedizioni quando vengono rilasciate al magazzino utilizzando Rilascio automatico degli ordini cliente
description: Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino nella stessa procedura periodica di rilascio al magazzino automatizzata.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 82a95ecf196ef7c33831da7f4d03df629b17fa53
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807562"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a>Consolidare le spedizioni quando vengono rilasciate al magazzino utilizzando Rilascio automatico degli ordini cliente

[!include [banner](../includes/banner.md)]

Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino nella stessa procedura periodica di rilascio al magazzino automatizzata. Gli ordini verranno automaticamente consolidati in spedizioni, in base a regole definite come criteri di consolidamento delle spedizioni.

Durante lo scenario, creerai serie di ordini cliente e rilascerai ogni serie nel magazzino. Esaminerai quindi le spedizioni che vengono create o aggiornate durante il consolidamento della spedizione, in base ai criteri configurati.

## <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Lo scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management. Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Impostare i criteri di consolidamento delle spedizioni e i filtri per i prodotti

Lo scenario qui descritto presuppone che tu abbia già attivato la funzione, eseguito gli esercizi [Configurare i criteri di consolidamento della spedizione](configure-shipment-consolidation-policies.md) e creato i criteri e altri record ivi descritti. Assicurati di eseguire quegli esercizi prima di continuare con questo scenario.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crea gli ordini cliente per questo scenario

Inizia creando una raccolta di ordini cliente con cui puoi lavorare. Devi lavorare con un magazzino abilitato per i processi di magazzino avanzati (WMS). A meno che non venga esplicitamente menzionato un magazzino diverso, tale magazzino deve essere utilizzato per ciascuna dei seguenti insiemi di ordini.

Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente** e crea una raccolta di ordini cliente con le impostazioni descritte nelle sottosezioni seguenti.

### <a name="create-order-set-1"></a>Crea un insieme di ordini 1

#### <a name="sales-order-1-1"></a>Ordine cliente 1-1

1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Modalità di consegna:** *Airwa-Air*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

#### <a name="sales-order-1-2"></a>Ordine cliente 1-2

1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Modalità di consegna:** *Airwa-Air*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

#### <a name="sales-order-1-3"></a>Ordine cliente 1-3

1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Modalità di consegna:** *10*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Aggiungi una seconda riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0002* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*
    - **Modalità di consegna:** *Airwa-Air*

### <a name="create-order-set-2"></a>Crea un insieme di ordini 2

#### <a name="sales-orders-2-1-and-2-2"></a>Ordini cliente 2-1 e 2-2

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-002*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *M9200* (un articolo il cui filtro **Codice 4** è impostato su *Infiammabile*)
    - **Quantità:** *1.00*

1. Aggiungi una seconda riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *M9201* (un articolo il cui filtro **Codice 4** è impostato su *Esplosivo*)
    - **Quantità:** *1.00*
    - **Modalità di consegna:** *Airwa-Air*

### <a name="create-order-set-3"></a>Crea un insieme di ordini 3

#### <a name="sales-order-3-1"></a>Ordine cliente 3-1

1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-002*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *M9200* (un articolo il cui filtro **Codice 4** è impostato su *Infiammabile*)
    - **Quantità:** *1.00*

1. Aggiungi una seconda riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *M9201* (un articolo il cui filtro **Codice 4** è impostato su *Esplosivo*)
    - **Quantità:** *1.00*
    - **Modalità di consegna:** *Airwa-Air*

> [!NOTE]
> Questo ordine è identico ai due ordini creati per l'insieme di ordini 2. Tuttavia, è elencato come insieme di ordini perché lo rilascerai separatamente più avanti in questo scenario.

### <a name="create-order-set-4"></a>Crea un insieme di ordini 4

#### <a name="sales-order-4-1"></a>Ordine cliente 4-1

1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Richiesta di approvvigionamento cliente:** *1*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

### <a name="create-order-set-5"></a>Crea un insieme di ordini 5

#### <a name="sales-orders-5-1-and-5-2"></a>Ordini cliente 5-1 e 5-2

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Richiesta di approvvigionamento cliente:** *2*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

#### <a name="sales-order-5-3"></a>Ordine cliente 5-3

1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Richiesta di approvvigionamento cliente:** *1*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

### <a name="create-order-set-6"></a>Crea un insieme di ordini 6

#### <a name="sales-orders-6-1-and-6-2"></a>Ordini cliente 6-1 e 6-2

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-003*
    - **Richiesta di approvvigionamento cliente:** *2*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

#### <a name="sales-orders-6-3-and-6-4"></a>Ordini cliente 6-3 e 6-4

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-004*
    - **Richiesta di approvvigionamento cliente:** *1*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

#### <a name="sales-orders-6-5-and-6-6"></a>Ordini cliente 6-5 e 6-6

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-007*
    - **Sito:** *6*
    - **Magazzino:** *61*
    - **Pool:** *ShipCons*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

#### <a name="sales-orders-6-7-and-6-8"></a>Ordini cliente 6-7 e 6-8

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-007*
    - **Sito:** *6*
    - **Magazzino:** *61*
    - **Pool:** lasciare vuoto questo campo.

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a>Rilascio automatico di ordini cliente nel magazzino

Per ciascuna serie di ordini cliente creati in precedenza, dovrai completare una procedura per il rilascio automatico nel magazzino. In ogni caso, proseguirai attraverso la [procedura base di rilascio al magazzino](#release-procedure) riportata qui.

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a>Procedura di rilascio in magazzino di base

Per ciascuna serie di ordini cliente creata in precedenza, verranno completate le tre procedure descritte nelle sottosezioni seguenti.

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a>Aggiorna il modello ondata che verrà utilizzato durante il rilascio

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Imposta il campo **Tipo di modello ondata** su *Spedizione*.
1. Trova e seleziona il modello ondata associato al magazzino utilizzato nei insieme di ordini creati per questo scenario. Ad esempio, se hai utilizzato il magazzino *24*, seleziona il modello ondata **Spedizione predefinita 24**. Se hai utilizzato il magazzino *61*, seleziona il modello ondata **Spedizione 61**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Impostare l'opzione **Elabora ondata al rilascio in magazzino** su *No*.

#### <a name="release-to-the-warehouse"></a>Rilascia al magazzino

1. Vai a **Gestione del magazzino \> Rilascio in magazzino \> Rilascio automatico degli ordini cliente**.
1. Imposta il campo **Quantità da rilasciare** su *Tutto*.
1. Nella Scheda dettaglio **Record da includere**, seleziona **Filtro** per aprire la finestra di dialogo dell'editor di query.
1. Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga che ha le seguenti impostazioni alla griglia:

    - **Tabella:** *Ordine cliente*
    - **Tabella derivata:** *Ordine cliente*
    - **Campo:** *Ordine cliente*
    - **Criteri:** immetti un elenco separato da virgole dei numeri degli ordini cliente dall'insieme di ordini desiderato.

1. Seleziona **OK** per salvare la tua query.
1. Seleziona **OK** per iniziare la procedura *Rilascio automatico in magazzino*.

#### <a name="review-the-shipment-that-is-created-or-updated"></a>Rivedi la spedizione creata o aggiornata

1. Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.
1. Trova e seleziona la spedizione richiesta.
1. Se è stato utilizzato un criterio di consolidamento al momento della creazione o dell'aggiornamento della spedizione, dovresti visualizzarlo nel campo **Criteri di consolidamento della spedizione**.

### <a name="release-sales-orders-from-order-set-1"></a>Rilascia gli ordini cliente dall'insieme di ordini 1

Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 1.

Al termine, dovresti vedere che sono state create due spedizioni:

- La prima spedizione contiene tre righe ed è stata creata utilizzando il criterio di consolidamento della spedizione *CustomerMode*.
- La seconda spedizione, che non utilizza la modalità di trasporto della consegna *Airways*, è stata creata utilizzando i criteri di consolidamento della spedizione *CustomerOrderNo*.

### <a name="release-sales-orders-from-order-set-2"></a>Rilascia gli ordini cliente dall'insieme di ordini 2

Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 2.

Al termine, dovresti vedere che sono state create tre spedizioni:

- La prima spedizione contiene articoli *Infiammabili*.
- Ognuna delle altre due spedizioni contiene una riga che ha l'articolo *Esplosivo*.

### <a name="release-sales-orders-from-order-set-3"></a>Rilascia gli ordini cliente dall'insieme di ordini 3

Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 3.

Al termine, dovresti vedere che si sono verificate le seguenti azioni:

- Una spedizione esistente (la spedizione creata quando l'insieme di ordini 2 è stato rilasciato nel magazzino) è stata aggiornata. Una riga che ha l'articolo *Infiammabile* è stata aggiunta.
- È stata creata una nuova spedizione che contiene l'articolo *Esplosivo*.

### <a name="release-sales-orders-from-order-set-4"></a>Rilascia gli ordini cliente dall'insieme di ordini 4

Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 4.

Al termine, dovresti vedere quella spedizione esistente (dove il campo **Richiesta di approvvigionamento cliente** è impostato su *1*) è stato aggiornato. È stata aggiunta una nuova riga.

### <a name="release-sales-orders-from-order-set-5"></a>Rilascia gli ordini cliente dall'insieme di ordini 5

Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 5.

Al termine, dovresti vedere che si sono verificate le seguenti azioni:

- Una spedizione esistente (dove il campo **Richiesta di approvvigionamento cliente** è impostato su *1*) è stata aggiornata. Una riga dall'ordine cliente 5-3 (dove il campo **Richiesta di approvvigionamento cliente** è impostato su *1*) è stata aggiunta ad esso.
- È stata creata una nuova spedizione, in cui le righe degli ordini cliente 5-1 e 5-2 sono raggruppate in un'unica spedizione.

### <a name="release-sales-orders-from-order-set-6"></a>Rilascia gli ordini cliente dall'insieme di ordini 6

Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 6.

Al termine, dovresti vedere che sono state create quattro spedizioni:

- Le righe dei due ordini per il cliente *US-003* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.
- Le righe dei due ordini per il cliente *US-004* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.
- Le righe dagli ordini cliente 6-5 e 6-6 per cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.
- Le righe dagli ordini cliente 6-7 e 6-8 per cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *CrossOrder*.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Criteri consolidamento spedizione](about-shipment-consolidation-policies.md)
- [Configurazione dei criteri di consolidamento delle spedizioni](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]