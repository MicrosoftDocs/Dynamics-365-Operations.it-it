---
title: Visibilità dell'inventario con programmazioni di modifiche scorte disponibili e available-to-promise
description: In questo argomento viene descritto come pianificare le modifiche future delle scorte disponibili e calcolare le quantità available-to-promise (ATP).
author: yufeihuang
ms.date: 03/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-04
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 7ce868871f093fd734a466bb8a06c5782bf83302
ms.sourcegitcommit: a3b121a8c8daa601021fee275d41a95325d12e7a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "8525884"
---
# <a name="inventory-visibility-on-hand-change-schedules-and-available-to-promise"></a>Visibilità dell'inventario con programmazioni di modifiche scorte disponibili e available-to-promise

[!include [banner](../includes/banner.md)]

Questo argomento descrive come impostare la funzionalità *Programmazione delle modifiche scorte disponibili* per programmare le modifiche future delle scorte disponibili e calcolare le quantità available-to-promise (ATP). ATP è la quantità di un articolo disponibile e che può essere promessa a un cliente nel prossimo periodo. L'uso di questo calcolo può aumentare notevolmente la capacità di evasione degli ordini.

Per molti produttori, rivenditori o venditori, non è sufficiente solo sapere cosa è attualmente disponibile. Devono avere piena visibilità sulla disponibilità futura. Questa disponibilità futura deve considerare l'offerta futura, la domanda futura e l'ATP.

## <a name="enable-and-set-up-the-features"></a><a name="setup"></a>Abilitare e configurare le funzionalità

Prima di poter utilizzare l'ATP, è necessario impostare una o più misure calcolate per calcolare le quantità ATP. Devi anche attivare la funzione e configurare le impostazioni ATP in Microsoft Power Apps.

### <a name="set-up-calculated-measures-for-atp-quantities"></a>Impostare le misure calcolate per le quantità ATP

La *Misura calcolata ATP* è una misura calcolata predefinita che viene in genere utilizzata per trovare la quantità di scorte attualmente disponibile. La somma delle quantità del modificatore di addizione è la quantità di offerta e la somma delle quantità del modificatore di sottrazione è la quantità di domanda.

Puoi aggiungere più misure calcolate per calcolare le quantità ATP. Tuttavia, il numero totale di modificatori in tutte le misure calcolate ATP deve essere inferiore a nove.

È ad esempio possibile impostare la seguente misura calcolata:

**On-hand-available** = (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) – (*ReservPhysical* + *SoftReservePhysical* + *Outbound*)

La somma (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) rappresenta l'offerta e la somma (*ReservPhysical* + *SoftReservePhysical* + *Outbound*) rappresenta la domanda. Pertanto, la misura calcolata può essere intesa nel modo seguente:

**Scorte disponibili** = *Offerta* – *Domanda*

Per ulteriori informazioni sulle misure calcolate, vedi [Misure calcolate](inventory-visibility-configuration.md#calculated-measures).

### <a name="turn-on-the-on-hand-change-schedule-feature-and-configure-atp-settings"></a>Attivare la funzione di programmazione delle modifiche scorte disponibili e configurare le impostazioni ATP

Segui questi passaggi per attivare la funzionalità *programmazione delle modifiche scorte disponibili* in Power Apps e configurare le impostazioni ATP.

1. Accedi a Power Apps, e apri Visibilità inventario.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Gestione funzioni** , attiva la funzione *OnhandChangeSchedule* .
1. Seleziona la scheda **Impostazioni ATP**.
1. Quando esegui la query in Visibilità inventario, il risultato include ogni misura calcolata ATP che aggiungi qui. Seleziona **Aggiungi** per aggiungere una nuova misura calcolata per ATP.
1. Impostare i seguenti campi:

    - **Origine dati** – Seleziona l'origine dati associata alla misura calcolata.
    - **Misura calcolata** – Seleziona la misura calcolata associata all'origine dati selezionata e che vuoi utilizzare per trovare la quantità di scorte attualmente disponibile.
    - **Periodo di programmazione** – Immetti il numero di giorni in cui gli utenti possono visualizzare e inviare le modifiche programmate per le scorte disponibili quando viene utilizzata la misura calcolata selezionata. Gli utenti che richiedono informazioni sulle scorte riceveranno la quantità disponibile, le modifiche programmate per le scorte disponibili e l'ATP per ogni giorno in questo periodo, a partire dalla data corrente. Seleziona un numero intero compreso tra 1 e 7.

    > [!IMPORTANT]
    > Il periodo di programmazione include la data corrente. Pertanto, gli utenti possono programmare le modifiche disponibili in modo che avvengano in qualsiasi momento dalla data corrente (il giorno in cui viene inviata la modifica) fino a (periodo di pianificazione - 1) giorni futuri.

1. Seleziona **Salva**.
1. Ripetere i passaggi da 5 a 7 fino a quando non sono stati aggiunti tutte le misure calcolate necessarie per ATP.
1. Al termine della configurazione di tutte le impostazioni richieste, seleziona **Aggiorna configurazione**.

Per ulteriori informazioni, vedere [Completare e aggiornare la configurazione](inventory-visibility-configuration.md).

## <a name="how-the-on-hand-change-schedule-and-atp-calculations-work"></a>Come funzionano la programmazione delle modifiche scorte disponibili e i calcoli ATP

La *programmazione delle modifiche scorte disponibili* stabilisce le date previste e le quantità di modifiche programmate per le scorte disponibili. Puoi inviare una programmazione delle modifiche scorte disponibili a Visibilità inventario, a condizione che le date rientrino nel periodo definito dall'impostazione **Periodo di programmazione** (vedi la sezione [Abilitare e configurare le funzionalità](#setup)). Gli utenti che richiedono informazioni sulle scorte riceveranno la quantità disponibile, le modifiche programmate per le scorte disponibili e l'ATP per ogni giorno in questo periodo.

Le modifiche programmate inizialmente non sono confermate e quindi non influiscono sulle quantità effettive di scorte disponibili nel sistema. Per confermare le modifiche, è necessario inviare un *evento di modifica scorte disponibili*, che aggiorna la quantità effettiva disponibile. È quindi necessario ripristinare la modifica programmata inviando una programmazione delle modifiche scorte disponibili per una quantità negativa corrispondente.

Ad esempio, effettui un ordine per 10 biciclette e prevedi che arrivi domani. Pertanto, invii una programmazione delle modifiche scorte disponibili con una quantità in entrata di 10 e datata per domani. Quando l'ordine arriva il giorno successivo, aggiungi le biciclette al tuo inventario fisico di scorte disponibili. È quindi necessario confermare la modifica nel sistema per aggiornare la quantità effettivamente disponibile. Per confermare la modifica, invii un evento di modifica scorte disponibili con una quantità in entrata di 10. Quindi ripristini la modifica programmata inviando una programmazione delle modifiche scorte disponibili per una quantità in entrata di -10.

Quando si esegue una query in Visibilità inventario per le quantità di scorte disponibili e ATP, vengono restituite le seguenti informazioni per ogni giorno del periodo di programmazione:

- **Data** – La data a cui si applica il risultato.
- **Quantità disponibile** – La quantità effettivamente disponibile per la data specificata. Questo calcolo viene effettuato in base alla misura calcolata dall'ATP configurata per Visibilità inventario.
- **Offerta programmata** – La somma di tutte le quantità in entrata programmate che non sono diventate fisicamente disponibili per il consumo o la spedizione alla data specificata.
- **Domanda programmata** – La somma di tutte le quantità in uscita programmate che non sono state consumate o spedite alla data specificata.
- **Quantità ATP** – La quantità minima prevista disponibile dalla data specificata fino alla fine del periodo di programmazione. Questa quantità include tutte le rettifiche di quantità programmate. È la quantità massima che può essere promessa alla data corrente per la consegna o il consumo in quel giorno.

Ad esempio, se la data corrente è il 1° febbraio 2022 e il periodo di programmazione è 7, gli utenti possono inviare modifiche programmate per scorte disponibili che devono verificarsi dal 1° febbraio al 7 febbraio 2022. In questo caso, la quantità ATP per il 3 febbraio, ad esempio, viene calcolata in base alla quantità disponibile per quel giorno e alle quantità programmate dal 3 febbraio al 7 febbraio.

## <a name="example"></a>Esempio

L'esempio seguente mostra come una serie di modifiche alla quantità programmata influisca sulle quantità disponibili e ATP restituite da Visibilità inventario. Mostra anche come confermare una modifica programmata, come una modifica della programmazione confermata influisce sui risultati e cosa può accadere se non si conferma una modifica programmata.

I risultati in questo esempio mostrano un valore di *scorte disponibili previste*. Questo valore incorpora tutti gli aggiornamenti pianificati a scopo illustrativo, ma in realtà non viene restituito quando si esegue una query in Visibilità inventario.

1. Le seguenti impostazioni sono configurate per il tuo sistema nella pagina **Impostazione ATP** in Power Apps:

    - **Misura calcolata ATP** – Hai una misura calcolata denominata *Scorte disponibili*. È calcolato come *Scorte disponibili = Offerta – Domanda*. Seleziona la misura qui.
    - **Periodo di programmazione** – Scegli *7*.

1. Vengono applicate anche le seguenti condizioni:

    - La data corrente è il 1° febbraio 2022.
    - La quantità corrente di scorte disponibili è 20,

1. Per la data corrente (1 febbraio 2022), invii una quantità di domanda programmata pari a 3 a Visibilità inventario. La quantità disponibile prevista è quindi 17. La seguente tabella mostra il risultato.

    | Data | Disponibilità | Offerta programmata | Domanda programmata | Scorte disponibili previste | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 20 | | 3 | 17 | 17 |
    | 02/02/2022 | 20 | | | 17 | 17 |
    | 03/02/2022 | 20 | | | 17 | 17 |
    | 04/02/2022 | 20 | | | 17 | 17 |
    | 05/02/2022 | 20 | | | 17 | 17 |
    | 06/02/2022 | 20 | | | 17 | 17 |
    | 07/02/2022 | 20 | | | 17 | 17 |

1. Alla data corrente (1 febbraio 2022), invii una quantità di offerta programmata di 10 per il 3 febbraio 2022. La seguente tabella mostra il risultato.

    | Data | Disponibilità | Offerta programmata | Domanda programmata | Scorte disponibili previste | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 20 | | 3 | 17 | 17 |
    | 02/02/2022 | 20 | | | 17 | 17 |
    | 03/02/2022 | 20 | 10 | | 27 | 27 |
    | 04/02/2022 | 20 | | | 27 | 27 |
    | 05/02/2022 | 20 | | | 27 | 27 |
    | 06/02/2022 | 20 | | | 27 | 27 |
    | 07/02/2022 | 20 | | | 27 | 27 |

1. Alla data corrente (1 febbraio 2022), invii le seguenti modifiche alla quantità programmate:

    - Quantità della domanda di 15 per il 4 febbraio 2022
    - Quantità dell'offerta di 1 per il 5 febbraio 2022
    - Quantità della domanda di 3 per il 6 febbraio 2022

    La seguente tabella mostra il risultato.

    | Data | Disponibilità | Offerta programmata | Domanda programmata | Scorte disponibili previste | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 20 | | 3 | 17 | 12 |
    | 02/02/2022 | 20 | | | 17 | 12 |
    | 03/02/2022 | 20 | 10 | | 27 | 12 |
    | 04/02/2022 | 20 | | 15 | 12 | 12 |
    | 05/02/2022 | 20 | 1 | | 13 | 13 |
    | 06/02/2022 | 20 | 3 | | 16 | 16 |
    | 07/02/2022 | 20 | | | 16 | 16 |

1. Alla data corrente (1 febbraio 2022), spedisci la quantità della domanda programmata di 3: Pertanto, devi confermare questa modifica in modo che si rifletta sulla quantità effettiva disponibile. Per confermare la modifica, invii un evento di modifica scorte disponibili con una quantità in uscita di 3. Quindi ripristini la modifica programmata inviando una programmazione delle modifiche scorte disponibili per una quantità in uscita di -3. La seguente tabella mostra il risultato.

    | Data | Disponibilità | Offerta programmata | Domanda programmata | Scorte disponibili previste | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 01/02/2022 | 17 | | 0 | 17 | 12 |
    | 02/02/2022 | 17 | | | 17 | 12 |
    | 03/02/2022 | 17 | 10 | | 27 | 12 |
    | 04/02/2022 | 17 | | 15 | 12 | 12 |
    | 05/02/2022 | 17 | 1 | | 13 | 13 |
    | 06/02/2022 | 17 | 3 | | 16 | 16 |
    | 07/02/2022 | 17 | | | 16 | 16 |

1. Il giorno successivo (2 febbraio 2022), il periodo di programmazione si sposta in avanti di un giorno. La seguente tabella mostra il risultato.

    | Data | Disponibilità | Offerta programmata | Domanda programmata | Scorte disponibili previste | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 02/02/2022 | 17 | | | 17 | 12 |
    | 03/02/2022 | 17 | 10 | | 27 | 12 |
    | 04/02/2022 | 17 | | 15 | 12 | 12 |
    | 05/02/2022 | 17 | 1 | | 13 | 13 |
    | 06/02/2022 | 17 | 3 | | 16 | 16 |
    | 07/02/2022 | 17 | | | 16 | 16 |
    | 08/02/2022 | 17 | | | 16 | 16 |

1. Tuttavia, due giorni dopo (4 febbraio 2022), la quantità di offerta di 10 prevista per il 3 febbraio non è ancora arrivata. La seguente tabella mostra il risultato.

    | Data | Disponibilità | Offerta programmata | Domanda programmata | Scorte disponibili previste | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 04/02/2022 | 17 | | 15 | 2 | 2 |
    | 05/02/2022 | 17 | 1 | | 3 | 3 |
    | 06/02/2022 | 17 | 3 | | 6 | 6 |
    | 07/02/2022 | 17 | | | 6 | 6 |
    | 08/02/2022 | 17 | | | 6 | 6 |
    | 09/02/2022 | 17 | | | 6 | 6 |
    | 10/02/2022 | 17 | | | 6 | 6 |

    Come puoi vedere, le modifiche alle scorte disponibili programmate (ma non confermate) non influiscono sulla quantità disponibile effettiva.

## <a name="submit-change-schedules-change-events-and-atp-queries-through-the-api"></a><a name="api-urls"></a>Inviare programmazioni di modifica, eventi di modifica e query ATP tramite l'API

È possibile utilizzare i seguenti URL API (Application Programming Interface) per inviare le programmazioni delle modifiche scorte disponibili, eventi di modifica e query.

| Percorso | Metodo | Description |
| --- | --- | --- |
| `/api/environment/{environmentId}/on-hand/changeschedule` | `POST` | Crea una modifica scorte disponibili programmata. |
| `/api/environment/{environmentId}/on-hand/changeschedule/bulk` | `POST` | Crea più modifiche scorte disponibili programmate. |
| `/api/environment/{environmentId}/onhand` | `POST` | Creare un evento di modifica scorte disponibili. |
| `/api/environment/{environmentId}/onhand/bulk` | `POST` | Creare più eventi di modifica scorte disponibili. |
| `/api/environment/{environmentId}/onhand/indexquery` | `POST` | Esegui la query utilizzando il metodo `POST`. |
| `/api/environment/{environmentId}/onhand` | `GET` | Esegui la query utilizzando il metodo `GET`. |

Per maggiori informazioni, vedi [API pubbliche di Visibilità inventario](inventory-visibility-api.md).

### <a name="submit-on-hand-change-schedules"></a>Inviare le programmazioni di modifiche scorte disponibili

Le programmazioni di modifiche scorte disponibili vengono effettuate inviando una richiesta `POST` all'URL del servizio di visibilità inventario pertinente (vedi la sezione [Inviare programmazioni di modifica, eventi di modifica e query ATP tramite l'API](#api-urls)). Puoi anche inviare richieste in blocco.

Per inviare una programmazione delle modifiche scorte disponibili, il corpo della richiesta deve contenere un ID organizzazione, un ID prodotto, una data programmata e le quantità per data. La data programmata deve essere compresa tra la data corrente e la fine del periodo di programmazione corrente.

#### <a name="example-request-body-that-contains-a-single-update"></a>Esempio di corpo della richiesta che contiene un singolo aggiornamento

Il seguente esempio mostra un corpo della richiesta che contiene un singolo aggiornamento.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/on-hand/changeschedule

# Method
Post

# Header
# Replace {access_token} with the one from your security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId": "Small"
    },
    "quantitiesByDate":
    {
        "2022/02/01": // today
        {
            "pos":{
                "inbound": 10,
            },
        },
    },
}
```

#### <a name="example-request-body-that-contains-multiple-bulk-updates"></a>Esempio di corpo della richiesta che contiene più aggiornamenti (in blocco)

Il seguente esempio mostra un corpo della richiesta che contiene più aggiornamenti (in blocco).

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/on-hand/changeschedule/bulk

# Method
Post

# Header
# replace {access_token} with the one from your security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

[
    {
        "id": "id-bike-0001",
        "organizationId": "usmf",
        "productId": "Bike",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId": "Small"
        },
        "quantitiesByDate":
        {
            "2022/02/01": // today
            {
                "pos":{
                    "inbound": 10,
                },
            },
        },
    },
    {
        "id": "id-bike-0002",
        "organizationId": "usmf",
        "productId": "Car",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId": "Small"
        },
        "quantitiesByDate":
        {
            "2022/02/05":
            {
                "pos":{
                    "outbound": 10,
                },
            },
        },
    }
]
```

### <a name="submit-on-hand-change-events"></a>Inviare eventi di modifica delle scorte disponibili

Gli eventi di modifica delle scorte disponibili vengono effettuati inviando una richiesta `POST` all'URL del servizio di visibilità inventario pertinente (vedi la sezione [Inviare programmazioni di modifica, eventi di modifica e query ATP tramite l'API](#api-urls)). Puoi anche inviare richieste in blocco.

> [!NOTE]
> Gli eventi di modifica delle scorte disponibili non sono univoci nella funzionalità ATP ma fanno parte dell'API di visibilità inventario standard. Questo esempio è stato incluso perché gli eventi sono rilevanti quando si lavora con ATP. Gli eventi di modifica delle scorte disponibili assomigliano alle prenotazioni di modifica delle scorte disponibili, ma i messaggi di evento devono essere inviati a un URL API diverso e gli eventi utilizzano `quantities` invece di `quantityByDate` nel corpo del messaggio. Per ulteriori informazioni sugli eventi di modifica delle scorte disponibili e altre funzionalità dell'API di visibilità inventario, vedi [API pubbliche di Visibilità inventario](inventory-visibility-api.md).

Per inviare un evento di modifica delle scorte disponibili, il corpo della richiesta deve contenere un ID organizzazione, un ID prodotto, una data programmata e le quantità per data. La data programmata deve essere compresa tra la data corrente e la fine del periodo di programmazione corrente.

Il seguente esempio mostra un corpo della richiesta che contiene un singolo evento di modifica delle scorte disponibili.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# Replace {access_token} with the one from your security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "SizeId": "Big",
        "ColorId": "Red",
    },
    "quantities": {
        "pos": {
            "inbound": 10.0
        }
    }
}
```

## <a name="query-the-scheduled-on-hand-changes-and-atp-results"></a>Eseguire query per le modifiche scorte disponibili programmate e i risultati ATP

Puoi eseguire query per le modifiche scorte disponibili programmate e i risultati ATP inviando una richiesta `POST` o una richiesta `GET` all'URL dell'API appropriato (vedi la sezione [Inviare programmazioni di modifica, eventi di modifica e query ATP tramite l'API](#api-urls)).

Nella richiesta, imposta `QueryATP` su *vero* se vuoi eseguire query per le modifiche scorte disponibili programmate e i risultati ATP.

- Se stai inviando la richiesta utilizzando il metodo `GET`, imposta questo parametro nell'URL.
- Se stai inviando la richiesta utilizzando il metodo `POST`, imposta questo parametro nel corpo della richiesta.

> [!NOTE]
> Indipendentemente dal fatto che il parametro `returnNegative` è impostato su *vero* o *falso* nel corpo della richiesta, il risultato includerà valori negativi quando esegui una query per le modifiche scorte disponibili programmate e i risultati ATP. Questi valori negativi verranno inclusi perché, se sono programmati solo ordini di domanda o se le quantità di offerta sono inferiori alle quantità di domanda, le quantità di modifiche programmate per le scorte disponibili saranno negative. Se i valori negativi non fossero inclusi, i risultati sarebbero imprecisi. Per ulteriori informazioni su questa opzione e su come funziona per altri tipi di query, vedi [API pubbliche di Visibilità inventario](inventory-visibility-api.md).

### <a name="post-method-example"></a>Esempio di metodo POST

L'esempio seguente mostra come creare un corpo della richiesta che può essere inviato a Visibilità inventario utilizzando il metodo `POST`.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/on-hand/indexquery

# Method
Post

# Header
# replace {access_token} with the one from your security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "siteId": ["1"],
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true,
}
```

### <a name="get-method-example"></a>Esempio di metodo GET

L'esempio seguente mostra come creare un URL di richiesta come richiesta `GET`.

```txt
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand?organizationId=usmf&productId=Bike&SiteId=1&groupBy=ColorId,SizeId&returnNegative=true&QueryATP=true
```

Il risultato di questa richiesta `GET` è esattamente uguale al risultato della richiesta `POST` dell'esempio precedente.

### <a name="query-result-example"></a>Esempio di risultato di query

Entrambi gli esempi di query precedenti possono produrre la seguente risposta. Per questo esempio, il sistema è configurato con le seguenti impostazioni:

- **Misura calcolata ATP:** *iv.onhand = pos.inbound – pos.outbound*
- **Periodo programmazione:** *7*

Di seguito è riportato un esempio di corpo della richiesta.

```json
[
    {
        "quantitiesByDate": {
            "2022-02-02T00:00:00": {
                "pos": {
                    "outbound": 5,
                    "inbound": 0,
                },
                "iv": {
                    "onhand": -5,
                },
            },
            "2022-02-06T00:00:00": {
                "pos": {
                    "inbound": 7,
                    "outbound": 0,
                },
                "iv": {
                    "onhand": 7,
                },
            }
        },
        "atpQuantities": {
            "2022-02-01T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-02T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-03T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-04T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-05T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-06T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            },
            "2022-02-07T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            }
        },
        "productId": "Bike ",
        "dimensions": {
            "ColorId": "Red",
            "SizeId": "Big",
            "siteid": "1",
            "locationid": "11"
        },
        "quantities": {
            "pos": {
                "inbound": 10.0,
                "outbound": 0,
            },
            "iv": {
                "onhand": 10.0,
            }
        }
    }
]
```
