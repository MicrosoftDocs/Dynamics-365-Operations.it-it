---
title: Consolidare le spedizioni utilizzando il workbench di consolidamento delle spedizioni
description: Questo articolo presenta uno scenario in cui più ordini vengono rilasciati al magazzino e consolidati successivamente in spedizioni utilizzando il workbench di consolidamento delle spedizioni.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationSetShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: eed484cd37b02e58831e0041c3e0625091283b65
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428119"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a>Consolidare le spedizioni utilizzando il workbench di consolidamento delle spedizioni

[!include [banner](../includes/banner.md)]

Questo articolo presenta uno scenario in cui più ordini vengono rilasciati al magazzino e consolidati successivamente in spedizioni utilizzando il workbench di consolidamento delle spedizioni.

## <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Lo scenario in questo articolo fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management. Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Impostare i criteri di consolidamento delle spedizioni e i filtri per i prodotti

Lo scenario qui descritto presuppone che tu abbia già attivato la funzione, eseguito gli esercizi [Configurare i criteri di consolidamento delle spedizioni](configure-shipment-consolidation-policies.md) e creato i criteri e altri record ivi descritti. Assicurati di eseguire quegli esercizi prima di continuare con questo scenario.

## <a name="turn-the-manual-shipment-consolidation-feature-on-or-off"></a>Attivare la funzionalità Consolidamento spedizioni manuali

Per poter usare la funzionalità Consolidamento spedizioni manuali, è necessario attivarla per il sistema. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è attivata per impostazione predefinita. Gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Consolidamento spedizioni manuale* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Devi anche attivare la funzionalità *Consolida spedizione* per poter creare criteri (a partire da Supply Chain Management versione 10.0.29, la funzionalità è obbligatoria e non può essere disattivata). Per ulteriori informazioni, vedi [Configurazione dei criteri di consolidamento delle spedizioni](configure-shipment-consolidation-policies.md).

## <a name="create-the-sales-orders-for-this-scenario"></a>Crea gli ordini cliente per questo scenario

Inizia creando una raccolta di ordini cliente con cui puoi lavorare. Devi lavorare con un magazzino abilitato per i processi di magazzino avanzati (WMS). A meno che non venga esplicitamente menzionato un magazzino diverso, tale magazzino deve essere utilizzato per ciascuna dei seguenti insiemi di ordini.

Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente** e crea una raccolta di ordini cliente con le impostazioni descritte nelle sottosezioni seguenti.

### <a name="create-order-set-1"></a>Crea un insieme di ordini 1

#### <a name="sales-orders-1-1-and-1-2"></a>Ordini cliente 1-1 e 1-2

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Modalità di consegna:** *Airwa-Air*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.

#### <a name="sales-order-1-3"></a>Ordine cliente 1-3

1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Modalità di consegna:** *10*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.
1. Aggiungi una seconda riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0002* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*
    - **Modalità di consegna:** *Airwa-Air*

1. Seleziona **Magazzino \> Prenotazione**, quindi, nel riquadro azioni, seleziona **Prenota lotto** per prenotare la seconda riga dell'ordine.

### <a name="create-order-set-2"></a>Crea un insieme di ordini 2

#### <a name="sales-orders-2-1-and-2-2"></a>Ordini cliente 2-1 e 2-2

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-002*
    - **Modalità di consegna:** *Airwa-Air*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *M9200* (un articolo il cui filtro **Codice 4** è impostato su *Infiammabile*)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.
1. Aggiungi una seconda riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *M9201* (un articolo il cui filtro **Codice 4** è impostato su *Esplosivo*)
    - **Quantità:** *1.00*
    - **Modalità di consegna:** *Airwa-Air*

1. Seleziona **Magazzino \> Prenotazione**, quindi, nel riquadro azioni, seleziona **Prenota lotto** per prenotare la seconda riga dell'ordine.

### <a name="create-order-set-3"></a>Crea un insieme di ordini 3

#### <a name="sales-orders-3-1-and-3-2"></a>Ordini cliente 3-1 e 3-2

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Richiesta di approvvigionamento cliente:** *1*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.

#### <a name="sales-orders-3-3-and-3-4"></a>Ordini cliente 3-3 e 3-4

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Richiesta di approvvigionamento cliente:** *2*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.

### <a name="create-order-set-4"></a>Crea un insieme di ordini 4

#### <a name="sales-orders-4-1-and-4-2"></a>Ordini cliente 4-1 e 4-2

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-003*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.

#### <a name="sales-orders-4-3-and-4-4"></a>Ordini cliente 4-3 e 4-4

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-004*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.

#### <a name="sales-orders-4-5-and-4-6"></a>Ordini cliente 4-5 e 4-6

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-007*
    - **Sito:** *6*
    - **Magazzino:** *61*
    - **Pool:** *ShipCons*

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.

#### <a name="sales-orders-4-7-and-4-8"></a>Ordini cliente 4-7 e 4-8

1. Crea due ordini cliente identici con le seguenti impostazioni:

    - **Conto cliente:** *US-007*
    - **Sito:** *6*
    - **Magazzino:** *61*
    - **Pool:** lasciare vuoto questo campo.

1. Aggiungi una riga ordine con le seguenti impostazioni:

    - **Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)
    - **Quantità:** *1.00*

1. Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.

## <a name="release-the-orders-to-the-warehouse"></a>Rilascia gli ordini al magazzino

Segui questi passaggi per rilasciare ciascun ordine cliente creato per questo scenario nel magazzino.

1. Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente**.
1. Trova e seleziona l'ordine cliente da rilasciare.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Azioni \> Rilascia in magazzino** per rilasciare l'ordine cliente selezionato.
1. Ripeti questa procedura per ogni altro ordine cliente creato per questo scenario.

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a>Consolidare le spedizioni utilizzando il workbench di consolidamento delle spedizioni

1. Vai a **Gestione magazzino \> Rilascia in magazzino \> Workbench consolidamento spedizione**.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor delle query, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga che ha le seguenti impostazioni alla griglia:

    - **Tabella:** *Ordini cliente*
    - **Campo:** *Ordine cliente*
    - **Criteri:** immetti un elenco separato da virgole dei numeri di ordini cliente per ciascun insieme di ordini creato per questo scenario.

1. Seleziona **OK** per salvare la query e chiudere la finestra dialogo.
1. Nel riquadro azioni, seleziona **Consolida spedizioni**.
1. Seleziona tutte le spedizioni, quindi nel riquadro azioni, seleziona **Consolida**.

## <a name="verify-the-shipments"></a>Verifica le spedizioni

La seguente procedura consente di verificare le spedizioni che sono state create o aggiornate a seguito del consolidamento della spedizione. Usala per rivedere ogni insieme di ordini che hai creato per questo scenario, quindi rivedi le sottosezioni che seguono per assicurarti di aver ottenuto i risultati previsti.

1. Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.
1. Trova e seleziona la spedizione richiesta.
1. Se è stato utilizzato un criterio di consolidamento al momento della creazione o dell'aggiornamento della spedizione, dovresti visualizzarlo nel campo **Criteri di consolidamento della spedizione**.

### <a name="related-shipments-for-order-set-1"></a>Spedizioni correlate per insiemi di ordini 1

Dovrebbero essere state create due spedizioni:

- La prima spedizione contiene tre righe ed è stata creata utilizzando il criterio di consolidamento della spedizione *CustomerMode*.
- La seconda spedizione, che non utilizza la modalità di trasporto della consegna *Airways*, è stata creata utilizzando i criteri di consolidamento della spedizione *CustomerOrderNo*.

### <a name="related-shipments-for-order-set-2"></a>Spedizioni correlate per insiemi di ordini 2

Dovrebbero essere state create tre spedizioni:

- La prima spedizione contiene articoli *Infiammabili*.
- Ognuna delle altre due spedizioni contiene una riga che ha l'articolo *Esplosivo*.

### <a name="related-shipments-for-order-set-3"></a>Spedizioni correlate per insiemi di ordini 3

Dovrebbero essere state create due spedizioni:

- La prima spedizione contiene righe di ordini dall'ordine cliente il cui campo **Richiesta di approvvigionamento cliente** è impostato su *1*.
- La seconda spedizione contiene righe di ordini dall'ordine cliente il cui campo **Richiesta di approvvigionamento cliente** è impostato su *2*.

### <a name="related-shipments-for-order-set-4"></a>Spedizioni correlate per insiemi di ordini 4

Dovrebbero essere state create quattro spedizioni:

- Le righe dei due ordini per il cliente *US-003* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.
- Le righe dei due ordini per il cliente *US-004* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.
- Le righe dagli ordini cliente 4-5 e 4-6 per cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.
- Le righe dagli ordini cliente 4-7 e 4-8 per cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *CrossOrder*.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei criteri di consolidamento delle spedizioni](about-shipment-consolidation-policies.md)
- [Configurazione dei criteri di consolidamento delle spedizioni](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]