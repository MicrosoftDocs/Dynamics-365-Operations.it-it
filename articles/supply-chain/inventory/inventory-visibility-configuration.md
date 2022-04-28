---
title: Configurare Visibilità inventario
description: Questo argomento descrive come configurare la visibilità dell'inventario.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a2f7929026f41e921b71bc5a899810695c859902
ms.sourcegitcommit: d475dea4cf13eae2f0ce517542c5173bb9d52c1c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547790"
---
# <a name="configure-inventory-visibility"></a>Configurare Visibilità inventario

[!include [banner](../includes/banner.md)]


Questo argomento descrive come configurare Visibilità inventario utilizzando l'app Visibilità inventario in Power Apps.

## <a name="introduction"></a><a name="introduction"></a>Introduzione

Prima di iniziare a lavorare con la Visibilità dell'inventario, è necessario completare la seguente configurazione come descritto in questo argomento:

- [Configurazione dell'origine dati](#data-source-configuration)
- [Configurazione della partizione](#partition-configuration)
- [Configurazione della gerarchia dell'indice del prodotto](#index-configuration)
- [Configurazione della prenotazione (opzionale)](#reservation-configuration)
- [Esempio di configurazione predefinita](#default-configuration-sample)

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, installare e configurare il componente aggiuntivo Visibilità inventario come descritto in [Installare e configurare Visibilità inventario](inventory-visibility-setup.md).

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>Pagina Configurazione dell'app Visibilità inventario

In Power Apps, la pagina **Configurazione** dell'[app Visibilità inventario](inventory-visibility-power-platform.md) aiuta a impostare la configurazione delle scorte disponibili e la configurazione delle prenotazioni preliminari. Dopo l'installazione dell'add-in, la configurazione predefinita include il valore di Microsoft Dynamics 365 Supply Chain Management (l'origine dati `fno` ). È possibile rivedere le impostazioni predefinite. Inoltre, in base alle esigenze aziendali e ai requisiti di registrazione dell'inventario del sistema esterno, è possibile modificare la configurazione per standardizzare il modo in cui le modifiche all'inventario possono essere registrate, organizzate e interrogate su più sistemi. Le restanti sezioni di questo argomento spiegano come utilizzare ogni parte della pagina **Configurazione**.

Dopo che la configurazione è stata completata, assicurarsi di selezionare **Aggiorna configurazione** nell'app.

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>Abilitare le funzionalità Visibilità inventario nella gestione delle funzionalità di Power Apps

Il componente aggiuntivo Visibilità inventario aggiunge diverse nuove funzionalità all'installazione di Power Apps. Per impostazione predefinita, queste funzioni sono disattivate. Per utilizzarle, apri la pagina **configurazione** e quindi, nella scheda **Gestione funzionalità**, attiva le seguenti funzionalità secondo le necessità.

| Nome Gestione funzionalità | Description |
|---|---|
| *OnHandReservation* | Questa funzione ti consente di creare prenotazioni, consumare prenotazioni, e/o sbloccare quantità di inventario specificate usando Visibilità inventario. Per maggiori informazioni, vedere [Prenotazioni di visibilità dell'inventario](inventory-visibility-reservations.md). |
| *OnHandMostSpecificBackgroundService* | Questa funzionalità fornisce un riassunto dell'inventario per i prodotti insieme a tutte le dimensioni. I dati di riepilogo dell'inventario verranno sincronizzati periodicamente da Visibilità inventario. Per ulteriori informazioni, vedere [Riepilogo inventario](inventory-visibility-power-platform.md#inventory-summary). |
| *OnhandChangeSchedule* | La funzione facoltativa abilita la programmazione delle modifiche scorte disponibili e le funzionalità ATP. Per altre informazioni vedi [Visibilità dell'inventario con programmazioni di modifiche scorte disponibili e available-to-promise](inventory-visibility-available-to-promise.md). |
| *Abilita articoli di magazzino in Visibilità inventario* | Questa funzione opzionale consente a Visibilità inventario di supportare gli articoli abilitati per i processi di magazzino avanzati (articoli WHS). Per maggiori informazioni, vedere [Supporto di visibilità inventario per articoli WHS](inventory-visibility-whs-support.md). |

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Trovare l'endpoint del servizio

Se non conosci l'endpoint corretto del servizio Visibilità inventario, apri la pagina di **configurazione** in Power Apps e poi seleziona **Mostra endpoint del servizio** nell'angolo in alto a destra. La pagina mostrerà l'endpoint di servizio corretto.

## <a name="data-source-configuration"></a>Configurazione dell'origine dati

Ogni origine dati rappresenta un sistema da cui provengono i dati. Alcuni esempi di nomi delle origini dati includono `fno` (che sta per "app per la finanza e le operazioni Dynamics 365") e `pos` (che sta per "point of sale" ovvero punto vendita). Per default, Supply Chain Management è impostato come fonte di dati predefinita (`fno`) in Visibilità inventario.

> [!NOTE]
> L'origine dati `fno` è riservata a Supply Chain Management. Se il tuo componente aggiuntivo Visibilità inventario è integrato con un ambiente Supply Chain Management, ti consigliamo di non eliminare le configurazioni relative a `fno` nell'origine dati.

Per aggiungere un'origine dati, seguite questi passi.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Origine dati** , selezionare **Nuova origine dati** per aggiungere un'origine dati.

> [!NOTE]
> Quando si aggiunge un'origine dati, assicurarsi di convalidare il nome dell'origine dati, le misure fisiche e le mappature delle dimensioni prima di aggiornare la configurazione del servizio Visibilità inventario. Non sarà possibile modificare queste impostazioni dopo aver selezionato **Aggiorna configurazione**.

La configurazione dell'origine dati include le seguenti parti:

- Dimensioni (mapping delle dimensioni)
- Misure fisiche
- Misure calcolate

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimensioni (mapping delle dimensioni)

Lo scopo della configurazione delle dimensioni è quello di standardizzare l'integrazione multi-sistema per la pubblicazione di eventi e query, sulla base di combinazioni di dimensioni. Visibilità inventario fornisce una lista di dimensioni di base che possono essere mappate dalle dimensioni della vostra fonte di dati. Trentatré dimensioni sono disponibili per la mappatura.

- Per default, se state usando Supply Chain Management come una delle vostre fonti di dati, 13 dimensioni sono mappate alle dimensioni standard di Supply Chain Management. Dodici altre dimensioni (da`inventDimension1` a `inventDimension12`) sono mappate su dimensioni personalizzate in Supply Chain Management. Le otto dimensioni rimanenti sono dimensioni estese che si possono mappare su fonti di dati esterne.
- Se non usate Supply Chain Management come una delle vostre fonti di dati, potete mappare liberamente le dimensioni. La seguente tabella mostra l'elenco completo delle dimensioni disponibili.

> [!NOTE]
> Se la tua dimensione non è nell'elenco delle dimensioni predefinite e stai usando un'origine dati esterna, ti consigliamo di usare `ExtendedDimension1` attraverso `ExtendedDimension8` per fare la mappatura.

| Tipo di dimensione | Dimensione della base |
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
| Estensione | `ExtendedDimension1` attraverso `ExtendedDimension8` |
| System | `Empty` |

> [!NOTE]
> I tipi di dimensione che sono elencati nella tabella precedente sono solo per riferimento. Non è necessario definirli in Visibilità dell'inventario.
>
> Le dimensioni di inventario (personalizzate) potrebbero essere riservate a Supply Chain Management. In questo caso, potete invece usare le dimensioni estese.

I sistemi esterni possono accedere a Visibilità inventario attraverso le sue API RESTful. Per l'integrazione, Visibilità inventario ti permette di configurare l' _origine dati esterna_ e la mappatura dalle _dimensioni esterne_ alle _dimensioni di base_. Ecco un esempio di tabella di mappatura delle dimensioni.

| Dimensione esterna | Dimensione della base |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

Configurando una mappatura delle dimensioni, è possibile inviare le dimensioni esterne direttamente a Visibilità inventario. Visibilità inventario convertirà automaticamente le dimensioni esterne in dimensioni di base.

Per aggiungere le mappature delle dimensioni, seguite questi passi.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Origine dati** , nella sezione **Mappature di dimensione** , selezionare **Aggiungi** per aggiungere le mappature di dimensione.
    ![Aggiunta di mappature di dimensioni](media/inventory-visibility-dimension-mapping.png "Aggiunta di mappature di dimensioni")

1. Nel campo **Nome della dimensione** , specificare la dimensione di origine.
1. Nel campo **Dimensione di base di destinazione** , selezionate la dimensione in Visibilità inventario che volete mappare.
1. Selezionare **Salva**.

Per esempio, se la vostra origine dati include una dimensione di colore del prodotto, potete mapparla alla dimensione base `ColorId` per aggiungere una dimensione personalizzata `ProductColor` nell'origine dati `exterchannel` . Viene poi mappato alla dimensione di base `ColorId` .

### <a name="physical-measures"></a>Misure fisiche

Quando una fonte di dati inserisce una variazione d'inventario in Visibilità inventario, inserisce tale variazione utilizzando le *misure fisiche*. Le misure fisiche modificano la quantità e riflettono lo stato dell'inventario. Potete definire le vostre misure fisiche, in base alle vostre esigenze. Le interrogazioni possono essere basate sulle misure fisiche.

Visibilità inventario fornisce una lista di misure fisiche predefinite che sono collegate a Supply Chain Management (la fonte di dati `fno` ). Queste misure fisiche predefinite sono prese dagli stati delle transazioni d'inventario sulla pagina della **lista di disponibilità** in Supply Chain Management **(Inventory Management \> Inquiries and Report \> On-hand list**). La seguente tabella fornisce un esempio di misure fisiche.

| Nome della misura fisica | descrizione |
|---|---|
| `NotSpecified` | Non specificato |
| `Arrived` | Arrivata |
| `AvailOrdered` | Disponibile ordinato |
| `AvailPhysical` | Fisico disponibile |
| `Deducted` | Detratto |
| `OnOrder` | OnOrder |
| `Ordered` | Quantità ordinata |
| `PhysicalInvent` | Inventario fisico |
| `Picked` | Prelevato |
| `PostedQty` | Quantità registrata |
| `QuotationIssue` | Rilascio offerta |
| `QuotationReceipt` | Ricevimento offerta |
| `Received` | Ricevute |
| `Registered` | Registrata |
| `ReservOrdered` | Ordinato prenotato |
| `ReservPhysical` | Fisico prenotato |

Se l'origine dei dati è Supply Chain Management, non è necessario ricreare le misure fisiche predefinite. Tuttavia, per le fonti di dati esterne, è possibile creare nuove misure fisiche seguendo questi passi.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Origine dati** , nella sezione **Misure fisiche** , selezionare **Aggiungi**, specificare il nome di una misura sorgente e salvare le modifiche.

### <a name="calculated-measures"></a>Misure calcolate

Puoi usare Visibilità inventario per interrogare sia le misure fisiche dell'inventario che le *misure calcolate personalizzate*. Le misure calcolate forniscono una formula di calcolo personalizzata che consiste in una combinazione di misure fisiche. Questa funzionalità permette di definire un insieme di misure fisiche che saranno aggiunte, e/o un insieme di misure fisiche che saranno sottratte, per formare la misura personalizzata.

La configurazione permette di definire un insieme di modificatori che vengono aggiunti o sottratti per ottenere la quantità totale aggregata in uscita.

Per configurare una misura calcolata personalizzata, effettuare le seguenti operazioni.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Misura calcolata** , seleziona **Nuova misura calcolata** per aggiungere una misura calcolata.
1. Imposta i seguenti campi per la nuova misura calcolata:

    - **Nome nuova misura calcolata** – Immetti il nome della misura calcolata.
    - **Origine dati** – Seleziona l'origine dati associata al nuovo modificatore. Il sistema di interrogazione è una fonte di dati.

1. Seleziona **Aggiungi** per aggiungere un modificatore alla nuova misura calcolata.
1. Imposta i seguenti campi per il nuovo modificatore:

    - **Modificatore** – Seleziona il tipo di modificatore (*Aggiunta* o *Sottrazione*).
    - **Origine dati** – Seleziona l'origine dati in cui deve essere trovata la misura che fornisce il valore del modificatore.
    - **Misura** – Seleziona il nome della misura (dall'origine dati selezionata) che fornisce il valore per il modificatore.

1. Ripeti i passaggi da 5 a 6 finché non hai aggiunto tutti i modificatori richiesti.
1. Seleziona **Salva**.

Per esempio, è possibile che si riceva il seguente risultato di query.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]
```

Si configura quindi una misura calcolata che si chiama `MyCustomAvailableforReservation`, come mostrato nella tabella seguente. Questa misura calcolata sarà consumata dal sistema di consumo.

| Sistema di consumo | Misura calcolata | Origine dati | Misura fisica | Tipo di calcolo |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `scheduled` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `reserved` | `Subtraction` |

Quando si usa questa formula di calcolo, il nuovo risultato della query includerà la misura personalizzata.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

L'output `MyCustomAvailableforReservation`, basato sull'impostazione di calcolo nelle misure personalizzate, è 100 + 50 - 10 + 80 - 20 + 90 + 30 - 60 - 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Configurazione della partizione

Attualmente la configurazione della partizione attualmente si compone di due dimensioni di base (`SiteId` e `LocationId`) che indicano come sono distribuiti i dati. Le operazioni nella stessa partizione possono fornire prestazioni più elevate a costi inferiori. La tabella seguente mostra la configurazione predefinita della partizione fornita dal componente aggiuntivo Visibilità inventario.

| Dimensione della base | Gerarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

La soluzione include questa configurazione della partizione per impostazione predefinita. Di conseguenza, *non è necessario ridefinirla*.

> [!IMPORTANT]
> Non personalizzare la configurazione della partizione predefinita. Se la elimini o la modifichi, è probabile che si verifichi un errore imprevisto.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Configurazione della gerarchia dell'indice del prodotto

La maggior parte delle volte, la query dell'inventario on-hand non sarà solo al livello più alto "totale". Invece, potreste voler vedere anche i risultati aggregati in base alle dimensioni dell'inventario.

Visibilità inventario fornisce flessibilità permettendovi di impostare gli _indici_. Questi indici sono basati su una dimensione o su una combinazione di dimensioni. Un indice consiste in un *numero di set*, una *dimensione* e una *gerarchia*, come definito nella tabella seguente.

| Nome | descrizione |
|---|---|
| Impostare il numero | Le dimensioni che appartengono allo stesso set (indice) saranno raggruppate insieme, e verrà loro assegnato lo stesso numero di set. |
| Dimensione | Dimensioni di base su cui viene aggregato il risultato della query. |
| Hierarchy | La gerarchia è usata per definire le combinazioni di dimensioni supportate che possono essere interrogate. Per esempio, si imposta un set di dimensioni che ha una sequenza gerarchica di `(ColorId, SizeId, StyleId)`. In questo caso, il sistema supporta query su quattro combinazioni di dimensioni. La prima combinazione è vuota, la seconda è `(ColorId)`, la terza è `(ColorId, SizeId)`, e la quarta è `(ColorId, SizeId, StyleId)`. Le altre combinazioni non sono supportate. Per maggiori informazioni, vedere l'esempio che segue. |

Per impostare il tuo indice di gerarchia dei prodotti, segui questi passi.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Indice della gerarchia dei prodotti** , nella sezione **Mappature** delle dimensioni, seleziona **Aggiungi** per aggiungere le mappature delle dimensioni.
1. Per impostazione predefinita, viene fornita una lista di indici. Per modificare un indice esistente, seleziona **Modifica** o **Aggiungi** nella sezione per il relativo indice. Per creare un nuovo set di indici, selezionare **Nuovo set di indici**. Per ogni riga di ogni set di indici, nel campo **Dimensione** , selezionate dall'elenco delle dimensioni di base. I valori per i seguenti campi sono generati automaticamente:

    - **Numero di set** - Le dimensioni che appartengono allo stesso gruppo (indice) saranno raggruppate insieme, e lo stesso numero di set sarà assegnato loro.
    - **Gerarchia** - La gerarchia è usata per definire le combinazioni di dimensioni supportate che possono essere interrogate in un gruppo di dimensioni (indice). Per esempio, se impostate un gruppo di dimensioni che ha una sequenza gerarchica di *Stile*, *Colore* e *Dimensione*, il sistema supporta il risultato di tre gruppi di query. Il primo gruppo è solo stile. Il secondo gruppo è una combinazione di stile e colore. E il terzo gruppo è una combinazione di stile, colore e dimensioni. Le altre combinazioni non sono supportate.

### <a name="example"></a>Esempio

Questa sezione fornisce un esempio che mostra come funziona la gerarchia.

La seguente tabella fornisce un elenco di inventario disponibile per questo esempio.

| Articolo | ColorId | SizeId | StyleId | Quantità |
|---|---|---|---|---|
| Maglietta | Nero | Piccolo | Largo | 1 |
| Maglietta | Nero | Piccolo | Regolare | 2 |
| Maglietta | Nero | Grande | Largo | 3 |
| Maglietta | Nero | Grande | Regolare | 4 |
| Maglietta | Rosso | Piccolo | Largo | 5 |
| Maglietta | Rosso | Piccolo | Regolare | 6 |
| Maglietta | Rosso | Grande | Regolare | 7 |

La tabella seguente mostra come è impostata la gerarchia degli indici.

| Numero set | Dimensione | Hierarchy |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

L'indice permette di interrogare l'inventario in mano nei seguenti modi:

- `()` - Raggruppati per tutti

    - Maglietta, 28

- `(ColorId)` - Raggruppati per `ColorId`

    - Maglietta, Nero, 10
    - Maglietta, rosso, 18

- `(ColorId, SizeId)` - Raggruppati per la combinazione di `ColorId` e `SizeId`

    - Maglietta, nero, piccolo, 3
    - Maglietta, nero, grande, 7
    - Maglietta, rosso, piccolo, 11
    - Maglietta, rosso, grande, 7

- `(ColorId, SizeId, StyleId)` - Raggruppati per la combinazione di `ColorId`, `SizeId`, e `StyleId`

    - Maglietta, nero, piccolo, largo, 1
    - Maglietta, nero, piccolo, regolare, 2
    - Maglietta, nero, grande, largo, 3
    - Maglietta, nero, grande, regolare, 4
    - Maglietta, rosso, piccolo, largo, 5
    - Maglietta, rosso, piccolo, regolare, 6
    - Maglietta, rosso, grande, regolare, 7

> [!NOTE]
> Le dimensioni di base che sono definite nella configurazione della partizione non dovrebbero essere definite nelle configurazioni degli indici.
> 
> Se è necessario interrogare solo l'inventario aggregato da tutte le combinazioni di dimensioni, è possibile configurare un unico indice che contenga la dimensione di base `Empty`.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Configurazione della prenotazione (opzionale)

La configurazione della prenotazione è necessaria se si vuole usare la funzione di prenotazione soft. La configurazione consiste in due parti fondamentali:

- Mappatura morbida delle prenotazioni
- Gerarchia delle prenotazioni soft

### <a name="soft-reservation-mapping"></a>Mappatura morbida delle prenotazioni

Quando fate una prenotazione, potreste voler sapere se l'inventario disponibile è attualmente disponibile per la prenotazione. La convalida è legata a una misura calcolata che rappresenta una formula di calcolo di una combinazione di misure fisiche.

Impostando la mappatura dalla misura fisica alla misura calcolata, si abilita il servizio Visibilità inventario a convalidare automaticamente la disponibilità delle prenotazioni, in base alla misura fisica.

Prima di impostare questa mappatura, le misure fisiche, le misure calcolate e le loro fonti di dati devono essere definite nelle schede **Origine dati** e **Misura calcolata** della pagina **Configurazione** in Power Apps (come descritto precedentemente in questo argomento).

Per definire la mappatura delle soft reservation, seguite questi passi.

1. Definire la misura fisica che serve come misura di riserva morbida (per esempio, `SoftReservOrdered`).
1. Nella scheda **Misura calcolata** della pagina **Configurazione** , definisci la misura calcolata *disponibile per la prenotazione* (AFR) che contiene la formula di calcolo AFR che vuoi mappare alla misura fisica. Per esempio, si potrebbe impostare `AvailableToReserve` (disponibile per la prenotazione) in modo che sia mappato alla misura fisica precedentemente definita `SoftReservOrdered` . In questo modo, potete trovare quali quantità che hanno lo stato di inventario `SoftReservOrdered` saranno disponibili per la prenotazione. La tabella seguente mostra la formula di calcolo dell'AFR.

    | Tipo di calcolo | Origine dati | Misura fisica |
    |---|---|---|
    | Aggiunta | `fno` | `AvailPhysical` |
    | Aggiunta | `pos` | `Inbound` |
    | Sottrazione | `pos` | `Outbound` |
    | Sottrazione | `iv` | `SoftReservOrdered` |

    Si consiglia di configurare la misura calcolata in modo che contenga la misura fisica su cui si basa la misura di prenotazione. In questo modo, la quantità di misura calcolata sarà influenzata dalla quantità di misura di prenotazione. Pertanto, in questo esempio, la misura calcolata `AvailableToReserve` dell'origine dati `iv` dovrebbe contenere la misura fisica `SoftReservOrdered` da `iv` come componente.

1. Aprire la pagina di **configurazione** .
1. Nella scheda **Mapping prenotazione preliminare** , impostare la mappatura dalla misura fisica alla misura calcolata. Per l'esempio precedente, si potrebbero usare le seguenti impostazioni per mappare `AvailableToReserve` alla misura fisica precedentemente definita `SoftReservOrdered` .

    | Fonte di dati della misura fisica | Misura fisica | Disponibile per l'origine dati della prenotazione | Disponibile per la prenotazione misura calcolata |
    |---|---|---|---|
    | `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > Se non è possibile modificare la scheda **Mapping prenotazione preliminare**, potrebbe essere necessario attivare la funzionalità *OnHandReservation* sulla scheda **Gestione funzionalità**.

Ora, quando fate una prenotazione su `SoftReservOrdered`, Visibilità inventario troverà automaticamente `AvailableToReserve` e la sua formula di calcolo relativa per fare la convalida della prenotazione.

Per esempio, avete il seguente inventario a disposizione in Visibilità inventario.

```json
{
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservOrdered": 90
        },
        "fno": {
            "availphysical": 70.0,
        },
        "pos": {
            "inbound": 50.0,
            "outbound": 20.0
        }
    }
}
```

In questo caso, si applica il seguente calcolo:

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` - `pos.outbound` - `iv.SoftReservOrdered`  
= 70 + 50 – 20 – 90  
= 10

Pertanto, se si cerca di fare prenotazioni su `iv.SoftReservOrdered`, e la quantità è inferiore o uguale a `AvailableToReserve` (10), si può fare la prenotazione.

> [!NOTE]
> Quando si chiama l'API di prenotazione, è possibile controllare la convalida della prenotazione specificando il parametro booleano `ifCheckAvailForReserv` nel corpo della richiesta. Un valore di `True` significa che è richiesta la convalida, mentre un valore di `False` significa che la convalida non è richiesta. Il valore predefinito è `True`.

### <a name="soft-reservation-hierarchy"></a>Gerarchia delle prenotazioni soft

La gerarchia delle prenotazioni descrive la sequenza delle dimensioni che devono essere specificate quando si fanno le prenotazioni. Funziona nello stesso modo in cui la gerarchia degli indici dei prodotti funziona per le query on-hand.

La gerarchia delle prenotazioni è indipendente dalla gerarchia degli indici dei prodotti. Questa indipendenza permette di implementare la gestione delle categorie in cui gli utenti possono scomporre le dimensioni in dettagli per specificare i requisiti per fare prenotazioni più precise. La gerarchia delle prenotazioni preliminari dovrebbe contenere `SiteId` e `LocationId` come componenti perché costruiscono la configurazione della partizione. Quando si effettua la prenotazione, è necessario specificare una partizione per il prodotto.

Ecco un esempio di gerarchia di prenotazione soft.

| Dimensione della base | Hierarchy |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

In questo esempio, è possibile effettuare la prenotazione nelle seguenti sequenze di dimensioni. Quando si effettua la prenotazione, è necessario specificare una partizione per il prodotto. Pertanto, la gerarchia di base che è possibile utilizzare è `(SiteId, LocationId)`.

- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Una sequenza di dimensioni valida deve seguire rigorosamente la gerarchia delle prenotazioni, dimensione per dimensione. Per esempio, la sequenza gerarchica `(SiteId, LocationId, SizeId)` non è valida, perché manca `ColorId` .

## <a name="available-to-promise-configuration-optional"></a>Configurazione available-to-promise (opzionale)

È possibile impostare la visibilità inventario per pianificare le modifiche future disponibili e calcolare le quantità ATP (available-to-promise). ATP è la quantità di un articolo disponibile e che può essere promessa a un cliente nel prossimo periodo. L'uso di questo calcolo può aumentare notevolmente la capacità di evasione degli ordini. Per utilizzare questa funzione, è necessario abilitarla nella scheda **Gestione funzionalità** e quindi configurarla nella scheda **Impostazione ATP**. Per ulteriori informazioni, vedi [Visibilità dell'inventario con programmazioni di modifiche scorte disponibili e available-to-promise](inventory-visibility-available-to-promise.md).

## <a name="complete-and-update-the-configuration"></a>Completare e aggiornare la configurazione

Dopo aver completato la configurazione, è necessario impegnare tutte le modifiche a Visibilità inventario. Per impegnare le modifiche, seleziona **Aggiorna configurazione** nell'angolo in alto a destra della pagina **Configurazione** in Power Apps.

La prima volta che selezioni **Aggiorna configurazione**, il sistema richiede le tue credenziali.

- **ID client** - L'ID dell'applicazione Azure che hai creato per la visibilità dell'inventario.
- **ID tenant** - Il tuo Azure tenant ID.
- **Segreto client** - Il segreto dell'applicazione Azure che hai creato per Visibilità inventario.

Dopo l'accesso, la configurazione viene aggiornata nel servizio Visibilità inventario.

> [!NOTE]
> Assicurati di convalidare il nome dell'origine dati, le misure fisiche e le mappature delle dimensioni prima di aggiornare la configurazione del servizio Visibilità inventario. Non sarà possibile modificare queste impostazioni dopo aver selezionato **Aggiorna configurazione**.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Esempio di configurazione predefinita

Durante la sua fase di inizializzazione, Visibilità inventario imposta una configurazione predefinita, dettagliata qui. È possibile modificare questa configurazione in base alle proprie esigenze.

### <a name="data-source-configuration"></a>Configurazione dell'origine dati

#### <a name="configuration-of-the-iv-data-source"></a>Configurazione dell'origine dati iv

Questa sezione descrive la configurazione dell'origine dati `iv` .

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Misure fisiche configurate per l'origine dati iv

Le seguenti misure fisiche sono configurate per l'origine dati `iv` :

- `Ordered`
- `SoftReservPhysical`
- `SoftReservOrdered`
- `ReservOrdered`
- `ReservPhysical`

##### <a name="orderedtotal-calculated-measure"></a>Misura calcolata OrderedTotal

La misura calcolata `OrderedTotal` è configurata per l'origine dati `iv` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `Ordered` |
| Aggiunta | `fno` | `Arrived` |
| Aggiunta | `iv` | `Ordered` |

##### <a name="onhand-calculated-measure"></a>Misura calcolata OnHand

La misura calcolata `OnHand` è configurata per l'origine dati `iv` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `PhysicalInvent` |
| Aggiunta | `iom` | `OnHand` |
| Aggiunta | `erp` | `Unrestricted` |
| Aggiunta | `erp` | `QualityInspection` |
| Aggiunta | `pos` | `PosInbound` |
| Sottrazione | `pos` | `PosOutbound` |

##### <a name="reservedtotal-calculated-measure"></a>RiservatoTotale misura calcolata

La misura calcolata `ReservedTotal` è configurata per l'origine dati `iv` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `ReservPhysical` |
| Aggiunta | `fno` | `ReservOrdered` |
| Aggiunta | `iv` | `SoftReservPhysical` |
| Aggiunta | `iv` | `SoftReservOrdered` |
| Aggiunta | `iv` | `ReservPhysical` |
| Aggiunta | `iv` | `ReservOrdered` |

##### <a name="softreserved-calculated-measure"></a>Misura calcolata SoftReserved

La misura calcolata `SoftReserved` è configurata per l'origine dati `iv` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `iv` | `SoftReservPhysical` |
| Aggiunta | `iv` | `SoftReservOrdered` |

##### <a name="hardreserved-calculated-measure"></a>HardReserved misura calcolata

La misura calcolata `HardReserved` è configurata per l'origine dati `iv` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `ReservPhysical` |
| Aggiunta | `fno` | `ReservOrdered` |
| Aggiunta | `iv` | `ReservPhysical` |
| Aggiunta | `iv` | `ReservOrdered` |

##### <a name="openorder-calculated-measure"></a>Misura calcolata OpenOrder

La misura calcolata `OpenOrder` è configurata per l'origine dati `iv` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `OnOrder` |
| Aggiunta | `iom` | `OnOrder` |

##### <a name="onhandavailable-calculated-measure"></a>Misura calcolata OnHandAvailable

La misura calcolata `OnHandAvailable` è configurata per l'origine dati `iv` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `PhysicalInvent` |
| Aggiunta | `iom` | `OnHand` |
| Aggiunta | `erp` | `Unrestricted` |
| Aggiunta | `erp` | `QualityInspection` |
| Aggiunta | `pos` | `PosInbound` |
| Sottrazione | `fno` | `ReservPhysical` |
| Sottrazione | `iv` | `SoftReservPhysical` |
| Sottrazione | `pos` | `PosOutbound` |

##### <a name="availabletoreserve-calculated-measure"></a>Misura calcolata AvailableToReserve

La misura calcolata `AvailableToReserve` è configurata per l'origine dati `iv` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `PhysicalInvent` |
| Aggiunta | `iom` | `OnHand` |
| Aggiunta | `erp` | `Unrestricted` |
| Aggiunta | `erp` | `QualityInspection` |
| Aggiunta | `pos` | `PosInbound` |
| Aggiunta | `fno` | `Ordered` |
| Aggiunta | `fno` | `Arrived` |
| Aggiunta | `iv` | `Ordered` |
| Sottrazione | `fno` | `ReservPhysical` |
| Sottrazione | `fno` | `ReservOrdered` |
| Sottrazione | `iv` | `SoftReservPhysical` |
| Sottrazione | `iv` | `SoftReservOrdered` |
| Sottrazione | `iv` | `ReservPhysical` |
| Sottrazione | `iv` | `ReservOrdered` |
| Sottrazione | `pos` | `PosOutbound` |

##### <a name="inventorysupply-calculated-measure"></a>Misura calcolata InventorySupply

La misura calcolata `InventorySupply` è configurata per l'origine dati `iv` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `Ordered` |
| Aggiunta | `fno` | `Arrived` |
| Aggiunta | `iv` | `Ordered` |
| Aggiunta | `fno` | `PhysicalInvent` |
| Aggiunta | `iom` | `OnHand` |
| Aggiunta | `erp` | `Unrestricted` |
| Aggiunta | `erp` | `QualityInspection` |
| Aggiunta | `pos` | `PosInbound` |
| Sottrazione | `pos` | `PosOutbound` |

##### <a name="inventorydemand-calculated-measure"></a>Misura calcolata InventoryDemand

La misura calcolata `InventoryDemand` è configurata per l'origine dati `iv` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `OnOrder` |
| Aggiunta | `iom` | `OnOrder` |
| Aggiunta | `iv` | `SoftReservPhysical` |
| Aggiunta | `iv` | `SoftReservOrdered` |
| Aggiunta | `fno` | `ReservPhysical` |
| Aggiunta | `fno` | `ReservOrdered` |
| Aggiunta | `iv` | `ReservPhysical` |
| Aggiunta | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>Configurazione dell'origine dati fno

Questa sezione descrive la configurazione dell'origine dati `fno` .

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Mappature delle dimensioni per l'origine dati fno

Le mappature delle dimensioni elencate nella seguente tabella sono configurate per l'origine dati `fno` .

| Dimensione esterna | Dimensione della base |
|---|---|
| `InventBatchId` | `BatchId` |
| `InventColorId` | `ColorId` |
| `InventLocationId` | `LocationId` |
| `InventSerialId` | `SerialId` |
| `InventSiteId` | `SiteId` |
| `InventSizeId` | `SizeId` |
| `InventStatusId` | `StatusId` |
| `InventStyleId` | `StyleId` |
| `LicensePlateId` | `LicensePlateId` |
| `WMSLocationId` | `WMSLocationId` |
| `WMSPalletId` | `WMSPalletId` |
| `ConfigId` | `ConfigId` |
| `InventVersionId` | `VersionId` |
| `InventDimension1` | `CustomDimension1` |
| `InventDimension2` | `CustomDimension2` |
| `InventDimension3` | `CustomDimension3` |
| `InventDimension4` | `CustomDimension4` |
| `InventDimension5` | `CustomDimension5` |
| `InventDimension6` | `CustomDimension6` |
| `InventDimension7` | `CustomDimension7` |
| `InventDimension8` | `CustomDimension8` |
| `InventDimension9` | `CustomDimension9` |
| `InventDimension10` | `CustomDimension10` |
| `InventDimension11` | `CustomDimension11` |
| `InventDimension12` | `CustomDimension12` |

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Misure fisiche configurate per l'origine dati fno

Le seguenti misure fisiche sono configurate per l'origine dati `fno` :

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>Configurazione dell'origine dati pos

Questa sezione descrive la configurazione dell'origine dati `pos` .

##### <a name="physical-measures-for-the-pos-data-source"></a>Misure fisiche per la fonte di dati pos

Le seguenti misure fisiche sono configurate per l'origine dati `pos` :

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>Misura calcolata AvailQuantity

La misura calcolata `AvailQuantity` è configurata per l'origine dati `pos` come mostrato nella tabella seguente.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `AvailPhysical` |
| Aggiunta | `pos` | `PosInbound` |
| Sottrazione | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>Configurazione dell'origine dati iom

Le seguenti misure fisiche sono configurate per la fonte di dati `iom` (gestione intelligente degli ordini):

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Configurazione dell'origine dati erp

Le seguenti misure fisiche sono configurate per l'origine dati `erp` (enterprise resource planning):

- `Unrestricted`
- `QualityInspection`

### <a name="partition-configuration"></a>Configurazione della partizione

La tabella seguente mostra la configurazione predefinita delle partizioni.

| Dimensione della base | Hierarchy |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>Configurazione dell'indice

La tabella seguente mostra la configurazione predefinita dell'indice.

| Numero set | Dimensione | Hierarchy |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

### <a name="reservation-configuration"></a>Configurazione della prenotazione

Questa sezione descrive la configurazione predefinita delle prenotazioni.

#### <a name="reservation-mapping"></a>Mappatura delle prenotazioni

La tabella seguente mostra la mappatura predefinita delle prenotazioni.

| Fonte di dati della misura fisica | Misura fisica | Disponibile per l'origine dati della prenotazione | Disponibile per la prenotazione misura calcolata |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Gerarchia prenotazioni

La tabella seguente mostra la gerarchia di prenotazione predefinita.

| Dimensione della base | Hierarchy |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |
| `BatchId` | 6 |
| `SerialId` | 7 |
| `StatusId` | 8 |
| `LicensePlateId` | 9 |
| `WMSLocationId` | 10 |
| `WMSPalletId` | 11 |
| `ConfigId` | 12 |
| `VersionId` | 13 |
| `CustomDimension1` | 14 |
| `CustomDimension2` | 15 |
| `CustomDimension3` | 16 |
| `CustomDimension4` | 17 |
| `CustomDimension5` | 18 |
| `CustomDimension6` | 19 |
| `CustomDimension7` | 20 |
| `CustomDimension8` | 21 |
| `CustomDimension9` | 22 |
| `CustomDimension10` | 23 |
| `CustomDimension11` | 24 |
| `CustomDimension12` | 25 |
| `ExtendedDimension1` | 26 |
| `ExtendedDimension2` | 27 |
| `ExtendedDimension3` | 28 |
| `ExtendedDimension4` | 29 |
| `ExtendedDimension5` | 30 |
| `ExtendedDimension6` | 31 |
| `ExtendedDimension7` | 32 |
| `ExtendedDimension8` | 33 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
