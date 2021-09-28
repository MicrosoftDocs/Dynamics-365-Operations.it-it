---
title: API pubbliche di visibilità dell'inventario
description: Questo argomento descrive le API pubbliche fornite da Visibilità inventario.
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
ms.openlocfilehash: 6dff54f54a495c2b4a7837f3a41f410d418cf12b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474654"
---
# <a name="inventory-visibility-public-apis"></a>API pubbliche di visibilità dell'inventario

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Questo argomento descrive le API pubbliche fornite da Visibilità inventario.

L'API REST pubblica del componente aggiuntivo Visibilità magazzino presenta diversi endpoint specifici per l'integrazione. Supporta quattro tipi principali di interazione:

- Registrazione delle modifiche delle scorte disponibili nel componente aggiuntivo da un sistema esterno
- Impostazione o sovrascrittura delle quantità dell'inventario a disposizione nell'add-in da un sistema esterno
- Inviare eventi di prenotazione all'add-in da un sistema esterno
- Interrogazione delle quantità disponibili correnti da un sistema esterno

La seguente tabella elenca le API che sono attualmente disponibili:

| Percorso | Metodo | descrizione |
|---|---|---|
| /api/environment/{environmentId}/onhand | Registra | [Creare un evento di cambiamento a portata di mano](#create-one-onhand-change-event) |
| /api/environment/{environmentId}/onhand/bulk | Registra | [Creare più eventi di cambiamento](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Registra | [Impostare/sovrascrivere le quantità disponibili](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Registra | [Creare un evento di prenotazione](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Registra | [Creare più eventi di prenotazione](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/indexquery | Ottieni | [Interrogare usando il metodo post](#query-with-post-method) |
| /api/environment/{environmentId}/onhand/indexquery | Registra | [Interrogare usando il metodo get](#query-with-get-method) |

Microsoft ha fornito una raccolta di richieste di *Postman* out-of-box. Puoi importare questa collezione nel tuo software *Postman* utilizzando il seguente link condiviso: <https://www.getpostman.com/collections/90bd57f36a789e1f8d4c>.

> [!NOTE]
> La parte del percorso {environmentId} è l'ID ambiente in Microsoft Dynamics Lifecycle Services (LCS).

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>Trova l'endpoint secondo il tuo ambiente Lifecycle Services

Il microservizio di Visibilità dell'inventario è distribuito su Microsoft Azure Service Fabric, in più aree geografiche e più regioni. Attualmente non c'è un endpoint centrale che possa reindirizzare automaticamente la tua richiesta alla geografia e alla regione corrispondente. Pertanto, è necessario comporre i pezzi di informazioni in un URL utilizzando il seguente schema:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

Il nome breve della regione può essere trovato nell'ambiente Microsoft Dynamics Lifecycle Services (LCS). La seguente tabella elenca le regioni che sono attualmente disponibili.

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
| Brasile meridionale        | sbr               |
| Stati Uniti centro-meridionali    | scus              |

Il numero dell'isola è dove il tuo ambiente LCS è distribuito su Service Fabric. Attualmente non c'è modo di ottenere queste informazioni dal lato utente.

Microsoft ha costruito un'interfaccia utente (UI) in Power Apps in modo da poter ottenere l'endpoint completo del microservizio. Per maggiori informazioni, vedere [Trovare l'endpoint del servizio](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Autenticazione

Il token di sicurezza della piattaforma è usato per chiamare l'API pubblica Visibilità inventario. Pertanto, è necessario generare un token _Azure Active Directory (Azure AD)_ usando l'applicazione Azure AD. È quindi necessario utilizzare il token Azure AD per ottenere il _token di accesso_ dal servizio di sicurezza.

Per ottenere un token di servizio di sicurezza, seguite questi passi.

1. Accedi al portale Azure e usalo per trovare i valori `clientId` e `clientSecret` per la tua app Dynamics 365 Supply Chain Management .
1. Recupera un token Azure AD (`aadToken`) inviando una richiesta HTTP che ha le seguenti proprietà:

   - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
   - **Metodo:** `GET`
   - **Contenuto del corpo (dati del modulo):**

     | Chiave           | Valore                                |
     | ------------- | ------------------------------------ |
     | client_id     | ${aadAppId}                          |
     | client_secret | ${aadAppSecret}                      |
     | grant_type    | client_credentials                   |
     | risorsa      | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |

   Dovreste ricevere un token Azure AD (`aadToken`) in risposta. Il risultato sarà simile all'esempio seguente.

   ```json
   {
       "token_type": "Bearer",
       "expires_in": "3599",
       "ext_expires_in": "3599",
       "expires_on": "1610466645",
       "not_before": "1610462745",
       "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
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
       "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
       "context_type": "finops-env"
   }
   ```

   Notare i punti seguenti:

   - Il valore `client_assertion` deve essere il token Azure AD (`aadToken`) che avete ricevuto nel passo precedente.
   - Il valore `context` deve essere l'ID dell'ambiente LCS in cui si desidera distribuire il componente aggiuntivo.
   - Impostare tutti gli altri valori come mostrato nell'esempio.

1. Invia una richiesta HTTP che ha le seguenti proprietà:

   - **URL:** `https://securityservice.operations365.dynamics.com/token`
   - **Metodo:** `POST`
   - **Intestazione HTTP:** Includere la versione dell'API. (La chiave è `Api-Version`, e il valore è `1.0`.)
   - **Contenuto del corpo:** Includete la richiesta JSON che avete creato nel passo precedente.

   Dovresti ricevere un token di accesso (`access_token`) in risposta. È necessario utilizzare questo token come token portatore per chiamare l'API di visibilità dell'inventario. Ecco un esempio.

   ```json
   {
       "access_token": "{Returned_Token}",
       "token_type": "bearer",
       "expires_in": 3600
   }
   ```

Nelle sezioni successive, si userà `$access_token` per rappresentare il token che è stato recuperato nell'ultimo passo.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Creare eventi di cambiamento a portata di mano

Ci sono due API per la creazione di eventi di cambiamento on-hand:

- Creare un record: `/api/environment/{environmentId}/onhand`
- Creare record multipli: `/api/environment/{environmentId}/onhand/bulk`

La tabella seguente riassume il significato di ogni campo nel corpo JSON.

| ID campo | descrizione |
|---|---|
| `id` | Un ID univoco per l'evento di modifica specifico. Questo ID è usato per assicurare che, se la comunicazione con il servizio fallisce durante la pubblicazione, lo stesso evento non sarà contato due volte nel sistema se viene ripresentato. |
| `organizationId` | L'identificatore dell'organizzazione che è collegata all'evento. Questo valore è mappato a un'organizzazione o a un ID dell'area dati in Supply Chain Management. |
| `productId` | Identificatore del prodotto. |
| `quantities` | La quantità di cui deve essere cambiata la quantità a disposizione. Per esempio, se 10 nuovi libri vengono aggiunti a uno scaffale, questo valore sarà `quantities:{ shelf:{ received: 10 }}`. Se tre libri vengono rimossi dallo scaffale o venduti, questo valore sarà `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | L'origine dei dati delle dimensioni che sono utilizzate nell'evento di modifica del distacco e nella query. Se si specifica l'origine dati, è possibile utilizzare le dimensioni personalizzate dell'origine dati specificata. Visibilità inventario può utilizzare la configurazione delle dimensioni per mappare le dimensioni personalizzate alle dimensioni generali predefinite. Se nessun valore `dimensionDataSource` è specificato, potete usare solo le [dimensioni di base](inventory-visibility-configuration.md#data-source-configuration-dimension) generali nelle vostre query. |
| `dimensions` | Una coppia chiave-valore dinamica. I valori sono mappati ad alcune delle dimensioni del Supply Chain Management. Tuttavia, puoi anche aggiungere dimensioni personalizzate (per esempio, _Source_) per indicare se l'evento proviene da Supply Chain Management o da un sistema esterno. |

> [!NOTE]
> I parametri `SiteId` e `LocationId` costruiscono la [configurazione della partizione](inventory-visibility-configuration.md#partition-configuration). Pertanto, è necessario specificarli nelle dimensioni quando si creano eventi di modifica delle scorte disponibili, si impostano o si sostituiscono le quantità delle scorte disponibili o si creano eventi di prenotazione.

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

L'esempio seguente mostra un esempio di contenuto del corpo. In questo esempio, pubblichi un evento di cambiamento per il prodotto *T-shirt* . Questo evento proviene dal sistema POS (point of sale), e il cliente ha restituito una maglietta rossa al tuo negozio. Questo evento aumenterà la quantità del prodotto *T-shirt* di 1.

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "PosMachineId": "0001",
        "ColorId": "Red"
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
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Creare più eventi di cambiamento

Questa API può creare più record allo stesso tempo. Le uniche differenze tra questa API e l' [API a evento singolo](#create-one-onhand-change-event) sono i valori `Path` e `Body` . Per questa API, `Body` fornisce un array di record.

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
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "usmf",
        "productId": "Pants",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Impostare/sovrascrivere le quantità disponibili

L'API _Set on-hand_ sovrascrive i dati attuali per il prodotto specificato.

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

L'esempio seguente mostra un esempio di contenuto del corpo. Il comportamento di questa API differisce da quello delle API che sono descritte nella sezione [Creare eventi di modifica on-hand in](#create-onhand-change-event) precedenza in questo argomento. In questo esempio, la quantità del prodotto *T-shirt* sarà impostata a 1.

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
             "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId": "0001"
        },
        "quantities": {
            "pos": {
                "inbound": 1
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Creare eventi di prenotazione

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Per utilizzare l'API di *riserva* , è necessario aprire la funzione di prenotazione e completare la configurazione della prenotazione. Per maggiori informazioni, vedere [Configurazione della prenotazione (opzionale)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Creare un evento di prenotazione

È possibile effettuare una prenotazione su impostazioni dell'origine dati diverse. Per configurare questo tipo di prenotazione, specificare prima l'origine dati nel parametro `dimensionDataSource`. Quindi, nel parametro `dimensions`, specificare le dimensioni in base alle impostazioni delle dimensioni nell'origine dati di destinazione.

Quando si chiama l'API di prenotazione, è possibile controllare la convalida della prenotazione specificando il parametro booleano `ifCheckAvailForReserv` nel corpo della richiesta. Un valore di `True` significa che è richiesta la convalida, mentre un valore di `False` significa che la convalida non è richiesta. Il valore predefinito è `True`.

Se si desidera annullare una prenotazione o annullare la prenotazione di quantità di inventario specificate, impostare la quantità su un valore negativo e impostare il parametro `ifCheckAvailForReserv` su `False` per saltare la convalida.

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
    "organizationId": "usmf",
    "productId": "T-shirt",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softreservordered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    }
}
```

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Creare più eventi di prenotazione

Questa API è una versione in blocco dell' [API a evento singolo](#create-one-reservation-event).

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

## <a name="query-on-hand"></a>Interrogazione a portata di mano

L'API _Query on-hand_ è usata per recuperare i dati di inventario correnti per i tuoi prodotti.

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
- `productId` può contenere uno o più valori. Se è una matrice vuota, verranno restituiti tutti i prodotti.
- `siteId` e `locationId` vengono utilizzati in Visibilità inventario per il partizionamento.

Il parametro `groupByValues` dovrebbe seguire la configurazione effettuata per l'indicizzazione. Per maggiori informazioni, vedere [Configurazione della gerarchia degli indici dei prodotti](./inventory-visibility-configuration.md#index-configuration).

Il parametro `returnNegative` controlla se i risultati contengono voci negative.

L'esempio seguente mostra un esempio di contenuto del corpo.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "LocationId": ["11"],
        "ColorId": ["Red"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true
}
```

Gli esempi seguenti mostrano come eseguire query su tutti i prodotti in un sito e in una posizione specifici.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": [],
        "siteId": ["1"],
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>Interrogare usando il metodo get

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
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
/api/environment/{environmentId}/onhand/indexquery?organizationId=usmf&productId=T-shirt&SiteId=1&LocationId=11&ColorId=Red&groupBy=ColorId,SizeId&returnNegative=true
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]