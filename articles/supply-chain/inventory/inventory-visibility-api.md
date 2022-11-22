---
title: API pubbliche di visibilità dell'inventario
description: Questo articolo descrive le API pubbliche fornite da Visibilità inventario.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 8b0b8ca261237fbb2190f2a94cc11b816ae05af5
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762836"
---
# <a name="inventory-visibility-public-apis"></a>API pubbliche di visibilità dell'inventario

[!include [banner](../includes/banner.md)]

Questo articolo descrive le API pubbliche fornite da Visibilità inventario.

L'API REST pubblica del componente aggiuntivo Visibilità magazzino presenta diversi endpoint specifici per l'integrazione. Supporta quattro tipi principali di interazione:

- Registrazione delle modifiche delle scorte disponibili nel componente aggiuntivo da un sistema esterno
- Impostazione o sovrascrittura delle quantità dell'inventario a disposizione nell'add-in da un sistema esterno
- Inviare eventi di prenotazione all'add-in da un sistema esterno
- Interrogazione delle quantità disponibili correnti da un sistema esterno

La seguente tabella elenca le API che sono attualmente disponibili:

| Percorso | Metodo | descrizione |
|---|---|---|
| /api/environment/{environmentId}/onhand | Registra | [Creare un evento di cambiamento a portata di mano](#create-one-onhand-change-event)|
| /api/environment/{environmentId}/onhand/bulk | Registra | [Creare più eventi di cambiamento](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Registra | [Impostare/sovrascrivere le quantità disponibili](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Registra | [Creare un evento di prenotazione temporanea](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Registra | [Creare più eventi di prenotazione temporanea](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/unreserve | Registra | [Invertire un evento di prenotazione temporanea](#reverse-one-reservation-event) |
| /api/environment/{environmentId}/onhand/unreserve/bulk | Registra | [Invertire più eventi di prenotazione temporanea](#reverse-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/changeschedule | Registra | [Crea una modifica scorte disponibili programmata](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/changeschedule/bulk | Registra | [Crea più modifiche scorte disponibili con date](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/indexquery | Registra | [Query esatte usando il metodo post](#query-with-post-method) (opzione consigliata) |
| /api/environment/{environmentId}/onhand | Ottieni | [Interrogare usando il metodo get](#query-with-get-method) |
| /api/environment/{environmentId}/onhand/exactquery | Registra | [Query esatte usando il metodo post](#exact-query-with-post-method) |
| /api/environment/{environmentId}/allocation<wbr>/allocate | Registra | [Creare un evento di allorazione](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/unallocate | Registra | [Creare un evento di annullamento dell'allorazione](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/reallocate | Registra | [Creare un evento di riallorazione](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/consume | Registra | [Creare un evento di consumo](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/query | Registra | [Risultato della query di allocazione](inventory-visibility-allocation.md#using-allocation-api) |

> [!NOTE]
> La parte del percorso {environmentId} è l'ID ambiente in Microsoft Dynamics Lifecycle Services.
> 
> L'API in blocco può restituire un massimo di 512 record per ogni richiesta.

Microsoft ha fornito una raccolta di richieste di *Postman* out-of-box. Puoi importare questa collezione nel tuo software *Postman* utilizzando il seguente link condiviso: <https://www.getpostman.com/collections/95a57891aff1c5f2a7c2>.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a><a name = "endpoint-lcs"></a>Trova l'endpoint secondo il tuo ambiente Lifecycle Services

Il microservizio di Visibilità dell'inventario è distribuito su Microsoft Azure Service Fabric, in più aree geografiche e più regioni. Attualmente non c'è un endpoint centrale che possa reindirizzare automaticamente la tua richiesta alla geografia e alla regione corrispondente. Pertanto, è necessario comporre i pezzi di informazioni in un URL utilizzando il seguente schema:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

Il nome breve della regione può essere trovato nell'ambiente Lifecycle Services. La seguente tabella elenca le regioni che sono attualmente disponibili.

| Regione Azure        | Nome breve della regione |
| ------------------- | ----------------- |
| Australia orientale      | eau               |
| Australia sud-orientale | seau              |
| Canada centrale      | cca               |
| Canada orientale         | eca               |
| Europa settentrionale        | neu               |
| Europa occidentale         | weu               |
| Stati Uniti orientali             | eus               |
| Stati Uniti occidentali             | wus               |
| Regno Unito meridionale            | suk               |
| Regno Unito occidentale             | wuk               |
| Giappone orientale          | ejp               |
| Giappone occidentale          | wjp               |
| India centrale       | cin               |
| India meridionale         | sin               |
| Svizzera settentrionale   | nch               |
| Svizzera occidentale    | wch               |
| Francia meridionale        | sfr               |
| Asia orientale           | eas               |
| Asia sud-orientale     | seas              |
| Emirati Arabi Uniti settentrionali           | nae               |
| Norvegia orientale         | eno               |
| Norvegia occidentale         | wno               |
| Sudafrica occidentale   | wza               |
| Sudafrica settentrionale  | nza               |

Il numero dell'isola è dove il tuo ambiente Lifecycle Services è distribuito su Service Fabric. Attualmente non c'è modo di ottenere queste informazioni dal lato utente.

Microsoft ha costruito un'interfaccia utente (UI) in Power Apps in modo da poter ottenere l'endpoint completo del microservizio. Per maggiori informazioni, vedere [Trovare l'endpoint del servizio](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Autenticazione

Il token di sicurezza della piattaforma è usato per chiamare l'API pubblica Visibilità inventario. Pertanto, è necessario generare un token *Azure Active Directory (Azure AD)* usando l'applicazione Azure AD. È quindi necessario utilizzare il token Azure AD per ottenere il *token di accesso* dal servizio di sicurezza.

Microsoft fornisce una raccolta di ottenimento di token *Postman* out-of-box. Puoi importare questa collezione nel tuo software *Postman* utilizzando il seguente link condiviso: <https://www.getpostman.com/collections/496645018f96b3f0455e>.

Per ottenere un token di servizio di sicurezza, seguite questi passi.

1. Accedi al portale Azure e usalo per trovare i valori `clientId` e `clientSecret` per la tua app Dynamics 365 Supply Chain Management.
1. Recupera un token Azure AD (`aadToken`) inviando una richiesta HTTP che ha le seguenti proprietà:

    - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/v2.0/token`
    - **Metodo:** `GET`
    - **Contenuto del corpo (dati del modulo):**

        | Chiave           | Valore                                            |
        | ------------- | -------------------------------------------------|
        | client_id     | ${aadAppId}                                      |
        | client_secret | ${aadAppSecret}                                  |
        | grant_type    | client_credentials                               |
        | scope         | 0cdb527f-a8d1-4bf8-9436-b352c68682b2/.default    |

    Dovreste ricevere un token Azure AD (`aadToken`) in risposta. Il risultato sarà simile all'esempio seguente.

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. Formulare una richiesta JSON (JavaScript Object Notation) che assomigli al seguente esempio.

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type": "aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope": "https://inventoryservice.operations365.dynamics.com/.default",
        "context": "{$LCS_environment_id}",
        "context_type": "finops-env"
    }
    ```

    Notare i punti seguenti:

    - Il valore `client_assertion` deve essere il token Azure AD (`aadToken`) che avete ricevuto nel passo precedente.
    - Il valore `context` deve essere l'ID dell'ambiente Lifecycle Services in cui si desidera distribuire il componente aggiuntivo.
    - Impostare tutti gli altri valori come mostrato nell'esempio.

1. Recuperare un token di accesso (`access_token`) inviando una richiesta HTTP che ha le seguenti proprietà:

    - **URL:** `https://securityservice.operations365.dynamics.com/token`
    - **Metodo:** `POST`
    - **Intestazione HTTP:** Includere la versione dell'API. (La chiave è `Api-Version`, e il valore è `1.0`.)
    - **Contenuto del corpo:** Includete la richiesta JSON che avete creato nel passo precedente.

    Dovresti ricevere un token di accesso (`access_token`) in risposta. È necessario utilizzare questo token come token portatore per chiamare l'API di visibilità dell'inventario. Ecco un esempio.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 3600
    }
    ```

> [!IMPORTANT]
> Quando si utilizza la raccolta di richieste di *Postman* per chiamare le API pubbliche di Visibilità inventario, è necessario aggiungere un token di connessione per ogni richiesta. Per trovare il token di connessione, selezionare la scheda **Autorizzazione** nell'URL della richiesta, selezionare il tipo **Token di connessione** e copiare il token di connessione recuperato nell'ultimo passaggio. Nelle sezioni successive di questo articolo, si utilizzerà `$access_token` per rappresentare il token che è stato recuperato nell'ultimo passo.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Creare eventi di cambiamento a portata di mano

Ci sono due API per la creazione di eventi di cambiamento on-hand:

- Creare un record: `/api/environment/{environmentId}/onhand`
- Creare record multipli: `/api/environment/{environmentId}/onhand/bulk`

La tabella seguente riassume il significato di ogni campo nel corpo JSON.

| ID campo | Description |
|---|---|
| `id` | Un ID univoco per l'evento di modifica specifico. Se si verifica un nuovo invio a causa di un errore del servizio, questo ID è usato per assicurare che lo stesso evento non sarà contato due volte nel sistema se viene ripresentato. |
| `organizationId` | L'identificatore dell'organizzazione che è collegata all'evento. Questo valore è mappato a un'organizzazione o a un ID dell'area dati in Supply Chain Management. |
| `productId` | Identificatore del prodotto. |
| `quantities` | La quantità di cui deve essere cambiata la quantità a disposizione. Per esempio, se 10 nuovi libri vengono aggiunti a uno scaffale, questo valore sarà `quantities:{ shelf:{ received: 10 }}`. Se tre libri vengono rimossi dallo scaffale o venduti, questo valore sarà `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | L'origine dei dati delle dimensioni che sono utilizzate nell'evento di modifica del distacco e nella query. Se si specifica l'origine dati, è possibile utilizzare le dimensioni personalizzate dell'origine dati specificata. Visibilità inventario può utilizzare la configurazione delle dimensioni per mappare le dimensioni personalizzate alle dimensioni generali predefinite. Se nessun valore `dimensionDataSource` è specificato, potete usare solo le [dimensioni di base](inventory-visibility-configuration.md#data-source-configuration-dimension) generali nelle vostre query. |
| `dimensions` | Una coppia chiave-valore dinamica. I valori sono mappati ad alcune delle dimensioni del Supply Chain Management. Tuttavia, puoi anche aggiungere dimensioni personalizzate (per esempio, *Source*) per indicare se l'evento proviene da Supply Chain Management o da un sistema esterno. |

> [!NOTE]
> I parametri `siteId` e `locationId` costruiscono la [configurazione della partizione](inventory-visibility-configuration.md#partition-configuration). Pertanto, è necessario specificarli nelle dimensioni quando si creano eventi di modifica delle scorte disponibili, si impostano o si sostituiscono le quantità delle scorte disponibili o si creano eventi di prenotazione.

Le seguenti sottosezioni forniscono esempi che mostrano come utilizzare queste API.

### <a name="create-one-on-hand-change-event"></a><a name="create-one-onhand-change-event"></a>Creare un evento di cambiamento a portata di mano

Questa API crea un singolo evento di cambiamento on-hand.

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string, # Optional
        dimensions: {
            [key:string]: string,
        },
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
    }
```

L'esempio seguente mostra un esempio di contenuto del corpo. In questo esempio, l'azienda dispone di un sistema POS (point of sale) che elabora le transazioni in negozio e quindi le variazioni di inventario. Il cliente ha restituito una maglietta rossa al tuo negozio. Per riflettere la modifica, pubblichi un singolo evento di cambiamento per il prodotto *T-shirt* . Questo evento aumenterà la quantità del prodotto *T-shirt* di 1.

```json
{
    "id": "Test201",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "posMachineId": "0001",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

Il seguente esempio mostra un esempio di contenuto del corpo senza `dimensionDataSource`. In questo caso, le `dimensions` saranno le [dimensioni di base](inventory-visibility-configuration.md#data-source-configuration-dimension). Se `dimensionDataSource` è impostato, le `dimensions` possono essere le dimensioni dell'origine dati o le dimensioni di base.

```json
{
    "id": "Test202",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Creare più eventi di cambiamento

Questa API può creare eventi di modifica, proprio come l'[API a evento singolo](#create-one-onhand-change-event). L'unica differenza è che questa API può creare più record allo stesso tempo. Quindi, i valori `Path` e `Body` differiscono. Per questa API, `Body` fornisce un array di record. Il numero massimo di record è 512. Pertanto, l'API della programmazione delle modifiche delle scorte disponibili può supportare fino a 512 eventi di modifica alla volta. 

Ad esempio, un computer POS di un punto vendita al dettaglio ha elaborato le seguenti due transazioni:

- Un ordine di reso di una maglietta rossa
- Una transazione di vendita di tre magliette nere

In questo caso, puoi includere entrambi gli aggiornamenti dell'inventario in una chiamata API.

```txt
Path:
    /api/environment/{environmentId}/onhand/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
        ...
    ]
```

L'esempio seguente mostra un esempio di contenuto del corpo.

```json
[
    {
        "id": "Test203",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "SiteId": "Site1",
            "LocationId": "11",
            "posMachineId&quot;: &quot;0001"
            "colorId&quot;: &quot;red"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "Test204",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensions": {
            "siteId": "1",
            "locationId": "11",
            "colorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Impostare/sovrascrivere le quantità disponibili

L'API *Set on-hand* sovrascrive i dati attuali per il prodotto specificato. Questa funzionalità viene in genere utilizzata per eseguire gli aggiornamenti del conteggio dell'inventario. Ad esempio, durante il conteggio giornaliero dell'inventario, un punto vendita potrebbe scoprire che l'inventario effettivamente disponibile per una maglietta rossa è 100. Pertanto, la quantità in entrata POS deve essere aggiornata a 100, indipendentemente da quale fosse la quantità precedente. Puoi utilizzare questa API per sovrascrivere il valore esistente.

```txt
Path:
    /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifiedDateTimeUTC: datetime,
        },
        ...
    ]
```

L'esempio seguente mostra un esempio di contenuto del corpo. Il comportamento di questa API differisce da quello delle API che sono descritte nella sezione [Creare eventi di modifica on-hand in](#create-onhand-change-event) precedenza in questo articolo. In questo esempio, la quantità del prodotto *T-shirt* sarà impostata a 1.

```json
[
    {
        "id": "Test204",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "posMachineId": "0001"
            "colorId": "red"
        },
        "quantities": {
            "pos": {
                "inbound": 100
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Creare eventi di prenotazione

Per utilizzare l'API di *riserva* , è necessario attivare la funzione di prenotazione e completare la configurazione della prenotazione. Per ulteriori informazioni (incluso un flusso di dati e uno scenario di esempio), vedere [Configurazione della prenotazione (facoltativa)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Creare un evento di prenotazione

È possibile effettuare una prenotazione su impostazioni dell'origine dati diverse. Per configurare questo tipo di prenotazione, specificare prima l'origine dati nel parametro `dimensionDataSource`. Quindi, nel parametro `dimensions`, specificare le dimensioni in base alle impostazioni delle dimensioni nell'origine dati di destinazione.

Quando si chiama l'API di prenotazione, è possibile controllare la convalida della prenotazione specificando il parametro booleano `ifCheckAvailForReserv` nel corpo della richiesta. Un valore di `True` significa che è richiesta la convalida, mentre un valore di `False` significa che la convalida non è richiesta. Il valore predefinito è `True`.

Se si desidera annullare una prenotazione o annullare la prenotazione di quantità di inventario specificate, impostare la quantità su un valore negativo e impostare il parametro `ifCheckAvailForReserv` su `False` per saltare la convalida. Esiste anche un'API per annullare la prenotazione dedicata per fare lo stesso. La differenza è solo nel modo in cui vengono chiamate le due API. È più facile annullare un evento di prenotazione specifico utilizzando `reservationId` con l'API di *annullamento della prenotazione*. Per ulteriori informazioni, vedere [Annullare la prenotazione di un evento di prenotazione](#reverse-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string,
        dimensions: {
            [key:string]: string,
        },
        quantityDataSource: string, # optional
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
        modifier: string,
        quantity: number,
        ifCheckAvailForReserv: boolean,
    }
```

L'esempio seguente mostra un esempio di contenuto del corpo.

```json
{
    "id": "reserve-0",
    "organizationId": "SCM_IV",
    "productId": "iv_postman_product",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softReservOrdered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "colorId": "red",
        "sizeId&quot;: &quot;small"
    }
}
```

L'esempio seguente mostra una risposta riuscita.

```json
{
    "reservationId": "RESERVATION_ID",
    "id": "ohre~id-822-232959-524",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
``` 

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Creare più eventi di prenotazione

Questa API è una versione in blocco dell' [API a evento singolo](#create-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string,
            dimensions: {
                [key:string]: string,
            },
            quantityDataSource: string, # optional
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifier: string,
            quantity: number,
            ifCheckAvailForReserv: boolean,
        },
        ...
    ]
```

## <a name="reverse-reservation-events"></a>Annullare gli eventi di prenotazione

L'API *Annulla prenotazione* funge da operazione di annullamento per gli eventi [*Prenotazione*](#create-reservation-events). Fornisce un modo per annullare un evento di prenotazione specificato da `reservationId` o per diminuire la quantità di prenotazione.

### <a name="reverse-one-reservation-event"></a><a name="reverse-one-reservation-event"></a>Annullare la prenotazione di un evento

Quando viene creata una prenotazione, un `reservationId` sarà incluso nel corpo di risposta. Devi fornire lo stesso `reservationId` per cancellare la prenotazione, e includere lo stesso `organizationId` e `dimensions` utilizzato per la chiamata API di prenotazione. Infine, specificare un valore `OffsetQty` che rappresenta il numero di elementi da liberare dalla prenotazione precedente. Una prenotazione può essere completamente o parzialmente annullata a seconda del valore `OffsetQty` specificato. Ad esempio, se *100* unità di articoli sono state prenotate, è possibile specificare `OffsetQty: 10` per annullare la prenotazione di *10* dell'importo iniziale riservato.

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        reservationId: string,
        dimensions: {
            [key:string]: string,
        },
        OffsetQty: number
    }
```

Il codice seguente mostra un esempio di contenuto del corpo.

```json
{
    "id": "unreserve-0",
    "organizationId": "SCM_IV",
    "reservationId": "RESERVATION_ID",
    "dimensions": {
        "siteid":"iv_postman_site",
        "locationid":"iv_postman_location",
        "ColorId": "red",
        "SizeId&quot;: &quot;small"
    },
    "OffsetQty": 1
}
```

Il codice seguente mostra un esempio del corpo della risposta riuscita.

```json
{
    "reservationId": "RESERVATION_ID",
    "totalInvalidOffsetQtyByReservId": 0,
    "id": "ohoe~id-823-11744-883",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
```

> [!NOTE]
> Nel corpo della risposta, quando `OffsetQty` è inferiore o uguale alla quantità di prenotazione, `processingStatus` sarà "*riuscito*" e `totalInvalidOffsetQtyByReservId` sarà *0*.
>
> Se `OffsetQty` è maggiore dell'importo prenotato, `processingStatus` sarà "*partialSuccess* " e `totalInvalidOffsetQtyByReservId` sarà la differenza tra `OffsetQty` e l'importo prenotato.
>
>Ad esempio, se la prenotazione ha una quantità di *10*, e `OffsetQty` ha un valore di *12*, `totalInvalidOffsetQtyByReservId` sarebbe *2*.

### <a name="reverse-multiple-reservation-events"></a><a name="reverse-multiple-reservation-events"></a>Annullare più eventi di prenotazione

Questa API è una versione in blocco dell' [API a evento singolo](#reverse-one-reservation-event).

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [      
        {
            id: string,
            organizationId: string,
            reservationId: string,
            dimensions: {
                [key:string]: string,
            },
            OffsetQty: number
        }
        ...
    ]
```

## <a name="query-on-hand"></a>Interrogazione a portata di mano

usa l'API *Query on-hand* per recuperare i dati di inventario correnti per i tuoi prodotti. Puoi utilizzare questa API ogni volta che devi conoscere lo stock, ad esempio quando desideri esaminare i livelli di stock dei prodotti sul tuo sito Web di e-commerce o quando desideri verificare la disponibilità dei prodotti nelle aree geografiche o nei punti vendita e magazzini vicini. L'API attualmente supporta le query fino a 5000 singoli elementi con il valore `productID`. Più valori `siteID` e `locationID` possono anche essere specificati in ogni query. Il limite massimo è definito dalla seguente equazione:

*NumOf(SiteID) \* NumOf(LocationID) <= 100*.

### <a name="query-by-using-the-post-method"></a><a name="query-with-post-method"></a>Interrogare usando il metodo post

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            siteId: string[],
            locationId: string[],
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

Nella parte del corpo di questa richiesta, `dimensionDataSource` è ancora un parametro facoltativo. Se non è impostato, i `filters` saranno considerati come *dimensioni di base*. Sono presenti quattro campi obbligatori per `filters`: `organizationId`, `productId`, `siteId` e `locationId`.

- `organizationId` deve contenere un solo valore, ma è ancora una matrice.
- `productId` potrebbe contenere uno o più valori. Se è una matrice vuota, verranno restituiti tutti i prodotti.
- `siteId` e `locationId` vengono utilizzati per il partizionamento in Visibilità inventario. È possibile specificare più di un valore `siteId` e `locationId` in una richiesta *Query a portata di mano*. Nella versione corrente, è necessario specificare entrambi i valori `siteId` e `locationId`.

È consigliabile utilizzare il parametro `groupByValues` per seguire la configurazione effettuata per l'indicizzazione. Per maggiori informazioni, vedere [Configurazione della gerarchia degli indici dei prodotti](./inventory-visibility-configuration.md#index-configuration).

Il parametro `returnNegative` controlla se i risultati contengono voci negative.

> [!NOTE]
> Se hai abilitato la pianificazione delle modifiche scorte disponibili e le funzionalità ATP (available-to-promise), la tua query può includere anche il parametro booleano `QueryATP` che controlla se i risultati della query includono informazioni ATP. Per altre informazioni ed esempi vedi [Visibilità dell'inventario con programmazioni di modifiche scorte disponibili e available-to-promise](inventory-visibility-available-to-promise.md).

L'esempio seguente mostra un esempio di contenuto del corpo. Mostra che è possibile eseguire query sull'inventario disponibile da più posizioni (magazzini).

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "locationId": ["11","12","13"],
        "colorId": ["red"]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

L'esempio seguente mostra come eseguire query su tutti i prodotti in un sito e in una posizione specifici.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": [],
        "siteId": ["1"],
        "locationId": ["11"],
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>Interrogare usando il metodo get

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Get
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Query(Url Parameters):
    groupBy
    returnNegative
    [Filters]
```

Ecco un esempio di URL. Questa richiesta di get è esattamente la stessa dell'esempio di post che è stato fornito prima.

```txt
/api/environment/{environmentId}/onhand?organizationId=SCM_IV&productId=iv_postman_product&siteId=iv_postman_site&locationId=iv_postman_location&colorId=red&groupBy=colorId,sizeId&returnNegative=true
```

## <a name="on-hand-exact-query"></a><a name="exact-query-with-post-method"></a>Query sulla disponibilità esatta

Le query sulla disponibilità esatta assomigliano alle normali query disponibili, ma consentono di specificare una gerarchia di mapping tra un sito e una posizione. Per esempio, hai i seguenti due siti:

- Sito 1, mappato alla posizione A
- Sito 2, mappato alla posizione B

Per una normale richiesta di disponibilità, se specifichi `"siteId": ["1","2"]` e `"locationId": ["A","B"]`, Visibilità inventario eseguirà automaticamente query sul risultato per i seguenti siti e località:

- Sito 1, posizione A
- Sito 1, posizione B
- Sito 2, posizione A
- Sito 2, posizione B

Come vedi, la normale query sulla disponibilità non riconosce che la posizione A esiste solo nel sito 1 e la posizione B esiste solo nel sito 2. Pertanto, effettua query ridondanti. Per soddisfare questo mapping gerarchico, è possibile utilizzare una query esatta disponibile e specificare i mapping della posizione nel corpo della query. In questo caso, eseguirai la query e riceverai i risultati solo per il sito 1, posizione A e per il sito 2, posizione B.

### <a name="exact-query-by-using-the-post-method"></a><a name="exact-query-with-post-method"></a>Query esatte usando il metodo post

```txt
Path:
    /api/environment/{environmentId}/onhand/exactquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            dimensions: string[],
            values: string[][],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

Nella parte del corpo di questa richiesta, `dimensionDataSource` è un parametro facoltativo. Se non è impostato, `dimensions` in `filters` saranno considerati come *dimensioni di base*. Sono presenti quattro campi obbligatori per `filters`: `organizationId`, `productId`, `dimensions` e `values`.

- `organizationId` deve contenere un solo valore, ma è ancora una matrice.
- `productId` potrebbe contenere uno o più valori. Se è una matrice vuota, verranno restituiti tutti i prodotti.
- Nella matrice `dimensions`, `siteId` e `locationId` sono obbligatori ma potrebbero apparire con altri elementi in qualsiasi ordine.
- `values` potrebbe contenere una o più distinte tuple di valori corrispondenti a `dimensions`.

I valori `dimensions` in `filters` verranno automaticamente aggiunti a `groupByValues`.

Il parametro `returnNegative` controlla se i risultati contengono voci negative.

L'esempio seguente mostra un esempio di contenuto del corpo.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": ["iv_postman_product"],
        "dimensions": ["siteId", "locationId", "colorId"],
        "values" : [
            ["iv_postman_site", "iv_postman_location", "red"],
            ["iv_postman_site", "iv_postman_location", "blue"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

L'esempio seguente mostra come eseguire query su tutti i prodotti in più siti e ubicazioni.

```json
{
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": [],
        "dimensions": ["siteId", "locationId"],
        "values" : [
            ["iv_postman_site_1", "iv_postman_location_1"],
            ["iv_postman_site_2", "iv_postman_location_2"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

## <a name="available-to-promise"></a>Available-to-promise

È possibile impostare la visibilità inventario per pianificare le modifiche future disponibili e calcolare le quantità ATP. ATP è la quantità di un articolo disponibile e che può essere promessa a un cliente nel prossimo periodo. L'uso del calcolo ATP può aumentare notevolmente la capacità di evasione degli ordini. Per informazioni su come abilitare questa funzione e su come interagire con la visibilità inventario tramite la relativa API dopo che la funzione è stata abilitata, vedi [Visibilità dell'inventario con programmazioni di modifiche scorte disponibili e available-to-promise](inventory-visibility-available-to-promise.md#api-urls).

## <a name="allocation"></a>Allocazione

Le API relative all'allocazione si trovano in [Allocazione di Inventory Visibility](inventory-visibility-allocation.md#using-allocation-api).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
