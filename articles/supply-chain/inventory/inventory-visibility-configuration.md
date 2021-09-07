---
title: Configurazione della visibilità dell'inventario
description: Questo argomento descrive come configurare la visibilità dell'inventario.
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
ms.openlocfilehash: 92e42b22d424ab80303d771f760cfcf0599b9f4c
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345035"
---
# <a name="inventory-visibility-configuration"></a>Configurazione della visibilità dell'inventario

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Questo argomento descrive come configurare la visibilità dell'inventario.

## <a name="introduction"></a><a name="introduction"></a>Introduzione

Prima di iniziare a lavorare con la Visibilità dell'inventario, è necessario completare la seguente configurazione come descritto in questo argomento:

- [Configurazione dell'origine dati](#data-source-configuration)
- [Configurazione della partizione](#partition-configuration)
- [Configurazione della gerarchia dell'indice del prodotto](#index-configuration)
- [Configurazione della prenotazione (opzionale)](#reservation-configuration)
- [Esempio di configurazione predefinita](#default-configuration-sample)

> [!NOTE]
> È possibile visualizzare e modificare le configurazioni di visibilità dell'inventario in [Microsoft Power Apps](./inventory-visibility-power-platform.md#configuration). Dopo che la configurazione è stata completata, seleziona **Aggiorna configurazione** nell'app.

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Configurazione dell'origine dati

L'origine dei dati rappresenta il sistema da cui provengono i tuoi dati. Gli esempi includono `fno` (che sta per "Dynamics 365 Finance and Operations apps") e `pos` (che sta per "point of sale").

La configurazione dell'origine dati include le seguenti parti:

- Dimensione (mappatura delle dimensioni)
- Misura fisica
- Misura calcolata

> [!NOTE]
> L'origine dati `fno` è riservata a Dynamics 365 Supply Chain Management.

### <a name="dimension-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimensione (mappatura delle dimensioni)

Lo scopo della configurazione delle dimensioni è quello di standardizzare l'integrazione multi-sistema per la pubblicazione di eventi e query, sulla base di combinazioni di dimensioni.

Visibilità inventario supporta le seguenti dimensioni generali di base.

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
| Interno | `ExtendedDimension1` attraverso `ExtendedDimension8` |

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

### <a name="physical-measures"></a>Misure fisiche

Le misure fisiche modificano la quantità e riflettono lo stato dell'inventario. Potete definire le vostre misure fisiche, in base alle vostre esigenze.

Visibilità inventario fornisce una lista di misure fisiche predefinite che sono collegate a Supply Chain Management (la fonte di dati `fno` ). La seguente tabella fornisce un esempio di misure fisiche.

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

### <a name="calculated-measures"></a><a name="data-source-configuration-calculated-measure"></a>Misure calcolate

Le misure calcolate forniscono una formula di calcolo personalizzata che consiste in una combinazione di misure fisiche. Questa funzionalità permette di definire un insieme di misure fisiche che saranno aggiunte, e/o un insieme di misure fisiche che saranno sottratte, per formare la misura personalizzata.

Per esempio, avete il seguente risultato della query.

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

L'uscita `MyCustomAvailableforReservation` , basata sull'impostazione di calcolo nelle misure personalizzate, è 100 + 50 + 80 + 90 + 30 - 10 - 20 - 60 - 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Configurazione della partizione

La configurazione della partizione consiste in una combinazione di dimensioni di base. Definisce il modello di distribuzione dei dati. Le operazioni sui dati nella stessa partizione supportano alte prestazioni e non costano troppo. Pertanto, buoni modelli di partizione possono contribuire a benefici significativi.

Visibilità inventario fornisce la seguente configurazione predefinita delle partizioni.

| Dimensione della base | Hierarchy |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

> [!NOTE]
> La configurazione predefinita della partizione è solo per riferimento. Non è necessario definirlo in Visibilità dell'inventario. Attualmente, l'aggiornamento della configurazione della partizione non è supportato.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Configurazione della gerarchia dell'indice del prodotto

La maggior parte delle volte, la query dell'inventario on-hand non sarà solo al livello più alto "totale". Invece, potreste voler vedere anche i risultati aggregati in base alle dimensioni dell'inventario.

Visibilità inventario fornisce flessibilità permettendovi di impostare gli _indici_. Questi indici sono basati su una dimensione o su una combinazione di dimensioni. Un indice consiste in un *numero di set*, una *dimensione* e una *gerarchia*, come definito nella tabella seguente.

| Nome | descrizione |
|---|---|
| Impostare il numero | Le dimensioni che appartengono allo stesso set (indice) saranno raggruppate insieme, e verrà loro assegnato lo stesso numero di set. |
| Dimensione | Dimensioni di base su cui viene aggregato il risultato della query. |
| Hierarchy | La gerarchia è usata per definire le combinazioni di dimensioni supportate che possono essere interrogate. Per esempio, si imposta un set di dimensioni che ha una sequenza gerarchica di `(ColorId, SizeId, StyleId)`. In questo caso, il sistema supporta query su quattro combinazioni di dimensioni. La prima combinazione è vuota, la seconda è `(ColorId)`, la terza è `(ColorId, SizeId)`, e la quarta è `(ColorId, SizeId, StyleId)`. Le altre combinazioni non sono supportate. Per maggiori informazioni, vedere l'esempio che segue. |

### <a name="example"></a>Esempio

Questa sezione fornisce un esempio che mostra come funziona la gerarchia.

Hai i seguenti oggetti nel tuo inventario.

| Articolo | ColorId | SizeId | StyleId | Quantità |
|---|---|---|---|---|
| Maglietta | Nero | Piccolo | Largo | 1 |
| Maglietta | Nero | Piccolo | Regolare | 2 |
| Maglietta | Nero | Grande | Largo | 3 |
| Maglietta | Nero | Grande | Regolare | 4 |
| Maglietta | Rosso | Piccolo | Largo | 5 |
| Maglietta | Rosso | Piccolo | Regolare | 6 |
| Maglietta | Rosso | Grande | Regolare | 7 |

Ecco l'indice.

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

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Configurazione della prenotazione (opzionale)

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

La configurazione della prenotazione è necessaria se si vuole usare la funzione di prenotazione soft. La configurazione consiste in due parti fondamentali:

- Mappatura morbida delle prenotazioni
- Gerarchia delle prenotazioni soft

### <a name="soft-reservation-mapping"></a>Mappatura morbida delle prenotazioni

Quando fate una prenotazione, potreste voler sapere se l'inventario disponibile è attualmente disponibile per la prenotazione. La convalida è legata a una misura calcolata che rappresenta una formula di calcolo di una combinazione di misure fisiche.

Per esempio, una misura di prenotazione è basata sulla misura fisica `SoftReservOrdered` dalla fonte di dati `iv` (Visibilità inventario). In questo caso, è possibile impostare la misura calcolata `AvailableToReserve` dell'origine dati `iv` come mostrato qui.

| Tipo di calcolo | Origine dati | Misura fisica |
|---|---|---|
| Aggiunta | `fno` | `AvailPhysical` |
| Aggiunta | `pos` | `Inbound` |
| Sottrazione | `pos` | `Outbound` |
| Sottrazione | `iv` | `SoftReservOrdered` |

Poi impostare una mappatura soft reservation per fornire una mappatura dalla misura di prenotazione `SoftReservOrdered` alla misura calcolata `AvailableToReserve` .

| Fonte di dati della misura fisica | Misura fisica | Disponibile per l'origine dati della prenotazione | Disponibile per la prenotazione misura calcolata |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

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

### <a name="soft-reservation-hierarchy"></a>Gerarchia delle prenotazioni soft

La gerarchia delle prenotazioni descrive la sequenza delle dimensioni che devono essere specificate quando si fanno le prenotazioni. Funziona nello stesso modo in cui la gerarchia degli indici dei prodotti funziona per le query on-hand.

La gerarchia delle prenotazioni è indipendente dalla gerarchia degli indici dei prodotti. Questa indipendenza permette di implementare la gestione delle categorie in cui gli utenti possono scomporre le dimensioni in dettagli per specificare i requisiti per fare prenotazioni più precise.

Ecco un esempio di gerarchia di prenotazione soft.

| Dimensione della base | Hierarchy |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

In questo esempio, potete fare la prenotazione nelle seguenti sequenze di dimensioni:

- `()` - Nessuna dimensione è specificata.
- `(SiteId)`
- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Una sequenza di dimensioni valida deve seguire rigorosamente la gerarchia delle prenotazioni, dimensione per dimensione. Per esempio, la sequenza gerarchica `(SiteId, LocationId, SizeId)` non è valida, perché manca `ColorId` .

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Esempio di configurazione predefinita

Durante la sua fase di inizializzazione, Visibilità inventario imposta una configurazione predefinita. Potete modificare la configurazione secondo le vostre esigenze.

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

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

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
