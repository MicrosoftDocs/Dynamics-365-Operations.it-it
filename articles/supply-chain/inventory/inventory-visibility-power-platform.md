---
title: App Visibilità dell'inventario
description: Questo argomento descrive come utilizzare l'applicazione Visibilità dell'inventario.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: cc09dd82547ec42041889e9a96662cd17549a3ea
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345004"
---
# <a name="inventory-visibility-app"></a>App Visibilità dell'inventario

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Questo argomento descrive come utilizzare l'applicazione Visibilità dell'inventario.

Visibilità inventario fornisce un'applicazione guidata dal modello per la visualizzazione. L'applicazione contiene tre pagine: **Configurazione**, **visibilità operativa** e **riepilogo dell'inventario**. Ha le seguenti caratteristiche:

- Fornisce un'interfaccia utente (UI) per la configurazione on-hand e la configurazione soft reservation.
- Supporta le interrogazioni in tempo reale dell'inventario su varie combinazioni di dimensioni.
- Fornisce un'interfaccia utente per pubblicare le richieste di prenotazione.
- Fornisce una visione personalizzata dell'inventario a disposizione dei prodotti insieme a tutte le dimensioni

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, installa e configura l'add-in Visibilità dell'inventario come descritto in Configurare la [visibilità dell'inventario](inventory-visibility-setup.md).

## <a name="configuration"></a><a name="configuration"></a>Configurazione

La pagina di **configurazione** ti aiuta a impostare la configurazione on-hand e la configurazione soft reservation. Dopo l'installazione dell'add-in, la configurazione predefinita include il valore di Microsoft Dynamics 365 Supply Chain Management (l'origine dati `fno` ). Potete rivedere l'impostazione predefinita. Inoltre, in base alle tue esigenze aziendali e ai requisiti di registrazione dell'inventario del tuo sistema esterno, puoi modificare la configurazione in [Dataverse](/powerapps/maker/common-data-service/data-platform-intro) per standardizzare il modo in cui le modifiche all'inventario possono essere registrate, organizzate e interrogate attraverso i sistemi multipli.

### <a name="define-data-sources"></a>Definire le fonti di dati

Tu definisci ogni *fonte di dati* che vuoi integrare con Visibilità inventario. Visibilità inventario supporta l'integrazione con varie fonti di dati, come il vostro sistema di punti vendita (POS), Supply Chain Management e altri sistemi esterni. Per default, Supply Chain Management è impostato come fonte di dati predefinita (`fno`) in Visibilità inventario.

Per aggiungere un'origine dati, seguite questi passi.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Origine dati** , selezionare **Nuova origine dati** per aggiungere un'origine dati.

> [!NOTE]
> Quando si aggiunge un'origine dati, assicurarsi di convalidare il nome dell'origine dati, le misure fisiche e le mappature delle dimensioni prima di aggiornare la configurazione del servizio Visibilità inventario. Non sarà possibile modificare queste impostazioni dopo aver selezionato **Aggiorna configurazione**.

### <a name="set-up-dimension-mappings"></a>Impostare le mappature delle dimensioni

Visibilità inventario fornisce una lista di dimensioni di base che possono essere mappate dalle dimensioni della vostra fonte di dati. Trentatré dimensioni sono disponibili per la mappatura.

- Per default, se state usando Supply Chain Management come una delle vostre fonti di dati, 13 dimensioni sono mappate alle dimensioni standard di Supply Chain Management. Dodici altre dimensioni (da`inventDimension1` a `inventDimension12`) sono mappate su dimensioni personalizzate in Supply Chain Management. Le otto dimensioni rimanenti sono dimensioni estese che si possono mappare su fonti di dati esterne.
- Se non usate Supply Chain Management come una delle vostre fonti di dati, potete mappare liberamente le dimensioni. La seguente tabella mostra l'elenco completo delle dimensioni disponibili.

> [!NOTE]
> Se la tua dimensione non è nell'elenco delle dimensioni predefinite e stai usando un'origine dati esterna, ti consigliamo di usare `ExtendedDimension1` attraverso `ExtendedDimension8` per fare la mappatura.

| Tipo di dimensione | Nome dimensione |
|---|---|
| Prodotto | `ColorId` |
| Prodotto | `SizeId` |
| Prodotto | `StyleId` |
| Prodotto | `ConfigId` |
| Tracciabilità | `BatchId` |
| Tracciabilità | `SerialId` |
| Posizione | `LocationId` |
| Posizione | `SiteId` |
| Stato inventario | `StatusId` |
| Specifico del magazzino | `WMSLocationId` |
| Specifico del magazzino | `WMSPalletId` |
| Specifico del magazzino | `LicensePlateId` |
| Altro | `VersionId` |
| Inventario (personalizzato) | `InventDimension1` attraverso `InventDimension12` |
| Altro | `ExtendedDimension1` attraverso `ExtendedDimension8` |

Per aggiungere le mappature delle dimensioni, seguite questi passi.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Origine dati** , nella sezione **Mappature di dimensione** , selezionare **Aggiungi** per aggiungere le mappature di dimensione.
1. Nel campo **Nome della dimensione** , specificare la dimensione di origine.
1. Nel campo **Dimensione di base di destinazione** , selezionate la dimensione in Visibilità inventario che volete mappare.
1. Selezionare **Salva**.

![Aggiunta di mappature di dimensioni](media/inventory-visibility-dimension-mapping.png "Aggiunta di mappature di dimensioni")

Per esempio, se la vostra origine dati include una dimensione di colore del prodotto, potete mapparla alla dimensione base `ColorId` per aggiungere una dimensione personalizzata `ProductColor` nell'origine dati `exterchannel` . Viene poi mappato alla dimensione di base `ColorId` .

## <a name="create-a-physical-measure"></a>Creare una misura fisica

Quando una fonte di dati inserisce una variazione d'inventario in Visibilità inventario, inserisce tale variazione utilizzando le *misure fisiche*. Le misure fisiche sono modificatori che riflettono gli stati riassuntivi delle transazioni d'inventario. Le interrogazioni possono essere basate sulle misure fisiche.

Visibilità inventario ha una lista di misure fisiche predefinite. Queste misure fisiche predefinite sono prese dagli stati delle transazioni d'inventario sulla pagina della **lista di disponibilità** in Supply Chain Management **(Inventory Management \> Inquiries and Report \> On-hand list**).

| Modificatore | Nome |
|---|---|
| `PhysicalInvent` | Inventario fisico |
| `ReservPhysical` | Fisico Riservato |
| `AvailPhysical` | Fisico disponibile |
| `ReservOrdered` | Ordinato Riservato |
| `PostedQty` | Quantità inviata |
| `Deducted` | Detratto |
| `Picked` | Prelevato |
| `Received` | Ricevute |
| `Registered` | Registrata |
| `Arrived` | Arrivata |
| `Ordered` | Quantità ordinata |
| `OnOrder` | Su ordinazione |
| `QuotationReceipt` | Ricevuta del preventivo |
| `QuotationIssue` | Questione di quotazione |

Se l'origine dei dati è Supply Chain Management, non è necessario ricreare le misure fisiche predefinite. Tuttavia, per le fonti di dati esterne, è possibile creare nuove misure fisiche seguendo questi passi.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Origine dati** , nella sezione **Misure fisiche** , selezionare **Aggiungi**, specificare il nome di una misura sorgente e salvare le modifiche.

## <a name="define-the-product-hierarchy-index"></a>Definire l'indice della gerarchia dei prodotti

Impostando gruppi di dimensioni aggregate, è possibile utilizzare Visibilità inventario per interrogare lo stato dell'inventario a portata di mano. In Visibilità inventario, ogni gruppo di dimensioni è conosciuto come un *indice*. Ogni indice corrisponde a un numero stabilito. Puoi decidere quali dimensioni saranno utilizzate per impostare l'indicizzazione, in base al modo in cui farai la query su Visibilità inventario.

Per impostare il tuo indice di gerarchia dei prodotti, segui questi passi.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Indice della gerarchia dei prodotti** , nella sezione **Mappature** delle dimensioni, seleziona **Aggiungi** per aggiungere le mappature delle dimensioni.
1. Per impostazione predefinita, viene fornita una lista di indici. Per modificare un indice esistente, seleziona **Modifica** o **Aggiungi** nella sezione per il relativo indice. Per creare un nuovo set di indici, selezionare **Nuovo set di indici**. Per ogni riga di ogni set di indici, nel campo **Dimensione** , selezionate dall'elenco delle dimensioni di base. I valori per i seguenti campi sono generati automaticamente:

    - **Numero di set** - Le dimensioni che appartengono allo stesso gruppo (indice) saranno raggruppate insieme, e lo stesso numero di set sarà assegnato loro.
    - **Gerarchia** - La gerarchia è usata per definire le combinazioni di dimensioni supportate che possono essere interrogate in un gruppo di dimensioni (indice). Per esempio, se impostate un gruppo di dimensioni che ha una sequenza gerarchica di *Stile*, *Colore* e *Dimensione*, il sistema supporta il risultato di tre gruppi di query. Il primo gruppo è solo stile. Il secondo gruppo è una combinazione di stile e colore. E il terzo gruppo è una combinazione di stile, colore e dimensioni. Le altre combinazioni non sono supportate.

Per maggiori informazioni, vedere [Configurazione della gerarchia degli indici dei prodotti](inventory-visibility-configuration.md#index-configuration).

### <a name="example"></a>Esempio

Questa sezione fornisce un esempio che mostra come funziona la gerarchia. La seguente tabella fornisce un elenco di inventario disponibile per questo esempio.

| Articolo | Stile | Colore | Dimensioni | Quantità |
|---|---|---|---|---|
| I0001 | Largo | Nero | Piccolo | 1 |
| I0001 | Largo | Nero | Grande | 2 |
| I0001 | Largo | Rosso | Piccolo | 3 |
| I0001 | Regolare | Nero | Piccolo | 4 |
| I0001 | Regolare | Nero | Grande | 5 |
| I0001 | Regolare | Rosso | Piccolo | 6 |
| I0001 | Regolare | Rosso | Grande | 7 |

La tabella seguente mostra come è impostata la gerarchia degli indici.

| Chiave | Impostare il numero | Hierarchy |
|---|---|---|
| `StyleId` | 1 | 1 |
| `ColorId` | 1 | 2 |
| `SizeId` | 1 | 3 |

In base alle impostazioni precedenti, la combinazione di dimensioni per la query di Visibilità dell'inventario è *Stile*, *Colore* e *Dimensione*. L'impostazione della gerarchia permette ai sistemi esterni di interrogare l'inventario on-hand nei seguenti modi:

- `()` - Raggruppati per tutti. Ecco l'output:

    - I0001, 28

- `(StyleId)` - Raggruppare per stile. Ecco l'output:

    - I0001, Largo, 6
    - I0001, regolare, 22

- `(StyleId, ColorId)` - Raggruppati per la combinazione di stile e colore. Ecco l'output:

    - I0001, largo, nero,3
    - I0001, largo, rosso, 3
    - I0001, regolare, nero, 9
    - I0001, regolare, rosso, 13

- `(StyleId, ColorId, SizeId)` - Raggruppati per la combinazione di stile, colore e dimensione. Ecco l'output:

    - I0001, largo, nero, piccolo, 1
    - I0001, largo, nero, grande, 2
    - I0001, largo, rosso, piccolo, 3
    - I0001, regolare, nero, piccolo, 4
    - I0001, regolare, nero, grande, 5
    - I0001, regolare, rosso, piccolo, 6
    - I0001, regolare, rosso, grande, 7

## <a name="set-up-a-custom-calculated-measure"></a>Impostare una misura calcolata personalizzata

Puoi usare Visibilità inventario per interrogare sia le misure fisiche dell'inventario che le *misure calcolate personalizzate*.

La configurazione permette di definire un insieme di modificatori che vengono aggiunti o sottratti per ottenere la quantità totale aggregata in uscita.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Misura calcolata** , seleziona **Nuova misura calcolata** per aggiungere una misura calcolata. Impostare poi i campi come descritto nella tabella seguente.

    | Campo | Valore |
    |---|---|
    | Nuovo nome della misura calcolata | Inserire il nome della misura calcolata. |
    | Origine dati | Il sistema di interrogazione è una fonte di dati. |
    | Fonte di dati del modificatore | Inserisci l'origine dei dati del modificatore. |
    | Modificatore | Inserisci il nome del modificatore. |
    | Tipo di modificatore | Seleziona il tipo di modificatore *(Aggiunta* o *Sottrazione*). |

La tabella seguente mostra un esempio della misura calcolata personalizzata `MyCustomAvailableforReservation` . Per maggiori informazioni su questo esempio, vedere [Configurazione dell'origine dati](inventory-visibility-configuration.md#data-source-configuration).

| Fonte dei dati della misura calcolata | Misura calcolata | Fonte di dati del modificatore | Modificatore | Tipo di modificatore |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `Exteexterchannelrchannel` | `reserved` | `Subtraction` |

### <a name="set-up-a-soft-reservation-mapping"></a><a name="setup-reservation-mapping"></a>Impostare una mappatura delle prenotazioni soft

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Prima di poter modificare la scheda **Mapping prenotazione preliminare** , è necessario attivare la funzione *OnHandReservation* nella scheda **Gestione funzionalità** .

Impostando la mappatura dalla misura fisica alla misura calcolata, si abilita il servizio Visibilità inventario a convalidare automaticamente la disponibilità delle prenotazioni, in base alla misura fisica.

Prima di impostare questa mappatura, le misure fisiche, le misure calcolate e le loro fonti di dati devono essere definite nelle schede **Origine dati** e **Misura calcolata** della pagina **Configurazione** in Power Apps (come descritto precedentemente in questo argomento).

Per definire la mappatura delle soft reservation, seguite questi passi.

1. Definire la misura fisica che serve come misura di riserva morbida (per esempio, `softreservordered`).
1. Nella scheda **Misura calcolata** della pagina **Configurazione** , definisci la misura calcolata *disponibile per la prenotazione* (AFR) che contiene la formula di calcolo AFR che vuoi mappare alla misura fisica. Per esempio, si potrebbe impostare `availforreserv` (disponibile per la prenotazione) in modo che sia mappato alla misura fisica precedentemente definita `softreservordered` . In questo modo, potete trovare quali quantità che hanno lo stato di inventario `softreservordered` saranno disponibili per la prenotazione. La tabella seguente mostra la formula di calcolo dell'AFR.

    | Modificatore | Origine dati | Unità di misura |
    |---|---|---|
    | `Addition` | `fno` | `availphysical` |
    | `Addition` | `pos` | `inbound` |
    | `Subtraction` | `pos` | `outbound` |
    | `Subtraction` | `iv` | `softreservordered` |

1. Aprire la pagina di **configurazione** .
1. Nella scheda **Mapping prenotazione preliminare** , impostare la mappatura dalla misura fisica alla misura calcolata. Per l'esempio precedente, si potrebbero usare le seguenti impostazioni per mappare `availforreserv` alla misura fisica precedentemente definita `softreservordered` .

    | Fonte di dati della misura fisica | Misura fisica | Disponibile per l'origine dati della prenotazione | Disponibile per la prenotazione misura calcolata |
    |---|---|---|---|
    | `iv` | `softreservordered` | `iv` | `availforreserv` |

### <a name="set-up-a-soft-reservation-hierarchy"></a><a name="setup-reservation-hierarchy"></a>Impostare una gerarchia di prenotazioni soft

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Prima di poter modificare la scheda **Gerarchia prenotazione preliminare** , è necessario attivare la funzione *OnHandReservation* nella scheda **Gestione funzionalità** .

La gerarchia delle prenotazioni descrive la sequenza delle dimensioni che devono essere specificate quando si fanno le prenotazioni. Funziona nello stesso modo in cui la gerarchia degli indici dei prodotti funziona per le query on-hand.

La gerarchia delle prenotazioni può differire dalla gerarchia dell'indice di disponibilità. Questa indipendenza permette di implementare la gestione delle categorie in cui gli utenti possono scomporre le dimensioni in dettagli per specificare i requisiti per fare prenotazioni più precise.

#### <a name="example"></a>Esempio

La seguente gerarchia di prenotazioni è impostata nel vostro sistema.

| Dimensione | Hierarchy |
|---|---|
| `ColorId` | 1 |
| `SizeId ` | 2 |
| `StyleId` | 3 |

Data questa gerarchia di prenotazione, potete fare la prenotazione nei seguenti ordini di dimensioni:

- `()` - Nessuna dimensione è data.
- `(ColorId)`
- `(ColorId, SizeId)`
- `(ColorId, SizeId, StyleId)`

L'ordine delle dimensioni deve seguire rigorosamente la sequenza della gerarchia delle prenotazioni, dimensione per dimensione. Per esempio, le prenotazioni che hanno `(ColorId, StyleId)` non saranno permesse in questo esempio, perché questa sequenza non è definita nella gerarchia delle prenotazioni.

### <a name="control-feature-management"></a><a name="feature-switch"></a>Gestione delle funzioni di controllo

L'add-in per la visibilità dell'inventario fornisce funzioni come *OnHandReservation* e *OnHandMostSpecificBackgroundService*. Per impostazione predefinita, queste funzioni sono disattivate. Per usarli, aprite la pagina di **configurazione** in Power Apps, e poi, nella scheda **Gestione funzionalità** , attivateli.

### <a name="complete-and-update-the-configuration"></a>Completare e aggiornare la configurazione

Dopo aver completato la configurazione, è necessario impegnare tutte le modifiche a Visibilità inventario. Per impegnare le modifiche, seleziona **Aggiorna configurazione** nell'angolo in alto a destra della pagina **Configurazione** in Power Apps.

La prima volta che selezioni **Aggiorna configurazione**, il sistema richiede le tue credenziali.

- **ID client** - L'ID dell'applicazione Azure che hai creato per la visibilità dell'inventario.
- **ID tenant** - Il tuo Azure tenant ID.
- **Segreto client** - Il segreto dell'applicazione Azure che hai creato per Visibilità inventario.

Dopo l'accesso, la configurazione viene aggiornata nel servizio Visibilità inventario.

> [!NOTE]
> Assicurati di convalidare il nome dell'origine dati, le misure fisiche e le mappature delle dimensioni prima di aggiornare la configurazione del servizio Visibilità inventario. Non sarà possibile modificare queste impostazioni dopo aver selezionato **Aggiorna configurazione**.

### <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Trovare l'endpoint del servizio

Se non conosci l'endpoint corretto del servizio Visibilità inventario, apri la pagina di **configurazione** in Power Apps e poi seleziona **Mostra endpoint del servizio** nell'angolo in alto a destra. La pagina mostrerà l'endpoint di servizio corretto.

## <a name="operational-visibility"></a>Visibilità operativa

La pagina di **Visibilità operativa** fornisce i risultati di una query di inventario in tempo reale, basata su varie combinazioni di dimensioni. Quando la funzione *OnHandReservation* è attivata, puoi anche inviare richieste di prenotazione dalla pagina di  **Visibilità operativa** .

### <a name="on-hand-query"></a>Interrogazione a portata di mano

La scheda **Query disponibilità** mostra i risultati di una query di inventario in tempo reale.

Quando selezioni la scheda **Query disponibilità** , il sistema richiede le tue credenziali in modo che possa ottenere il token del portatore che è necessario per interrogare il servizio Visibilità inventario. Potete semplicemente incollare il token del portatore nel campo **BearerToken** e chiudere la finestra di dialogo. Puoi quindi pubblicare una richiesta di ricerca a portata di mano.

Se il token del portatore non è valido, o se è scaduto, devi incollarne uno nuovo nel campo **BearerToken** . Inserisci i valori corretti di **ID cliente**, **ID inquilino**, **Segreto cliente** e poi seleziona **Aggiorna**. Il sistema otterrà automaticamente un nuovo token al portatore valido.

Per pubblicare una query on-hand, inserisci la query nel corpo della richiesta. Usate il modello che è descritto in [Query usando il metodo post](inventory-visibility-api.md#query-with-post-method).

![Impostazioni della query a portata di mano](media/inventory-visibility-query-settings.png "Impostazioni della query a portata di mano")

### <a name="reservation-posting"></a>Prenotazione

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Usa la scheda **Prenotazione** per pubblicare una richiesta di prenotazione. Prima di poter pubblicare una richiesta di prenotazione, devi attivare la funzione *OnHandReservation* . Per ulteriori informazioni su questa funzione, vedere [Prenotazioni di visibilità dell'inventario](inventory-visibility-reservations.md).

Per pubblicare una richiesta di prenotazione, devi inserire un valore nel corpo della richiesta. Usate il modello che è descritto in [Creare un evento di prenotazione](inventory-visibility-api.md#create-one-reservation-event). Poi seleziona **Registra**. Per visualizzare i dettagli della risposta alla richiesta, seleziona **Mostra dettagli**. Puoi anche ottenere il valore **reservationId** dai dettagli della risposta.

## <a name="inventory-summary"></a>Riassunto dell'inventario

Il **riepilogo dell'inventario** è una vista personalizzata per l' *entità Inventory OnHand Sum*. Fornisce un riassunto dell'inventario per i prodotti insieme a tutte le dimensioni. Usando il **filtro avanzato** che Dataverse fornisce, puoi creare una vista personale che mostra le righe che sono importanti per te. Le opzioni di filtro avanzate ti permettono di creare una vasta gamma di visualizzazioni, dalle più semplici alle più complesse. Permettono anche di aggiungere condizioni raggruppate e annidate ai filtri.

Per saperne di più su come usare il **filtro** avanzato, vedi [Modificare o creare viste personali usando i filtri avanzati della griglia](/powerapps/user/grid-filters-advanced)

La parte superiore della vista personalizzata fornisce tre campi: **Dimensione predefinita**, **Dimensione personalizzata** e **Misura**. Puoi usare questi campi per controllare quali colonne sono visibili.

Puoi selezionare l'intestazione della colonna per filtrare o ordinare il risultato corrente.

La parte inferiore della vista personalizzata mostra informazioni come "50 record (29 selezionati)" o "50 record" Questa informazione si riferisce ai record attualmente caricati dal risultato del **filtro avanzato** . Il testo "29 selezionati" si riferisce al numero di record che sono stati selezionati utilizzando il filtro di intestazione della colonna per i record caricati.

Nella parte inferiore della vista c'è un pulsante **Ulteriori informazioni** che puoi usare per caricare altri record da Dataverse. Il numero predefinito di record che viene caricato è 50. Quando si seleziona **Carica altro**, i prossimi 1.000 record disponibili vengono caricati nella vista. Il numero sul pulsante **Carica altro** indica i record attualmente caricati e il numero totale di record per il risultato del **filtro avanzato** .

![Riepilogo scorte](media/inventory-visibility-onhand-list.png "Riepilogo scorte")
