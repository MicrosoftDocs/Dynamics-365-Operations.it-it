---
title: Componente aggiuntivo Inventory Visibility
description: Questo argomento descrive come installare e configurare il componente aggiuntivo Inventory Visibility per Dynamics 365 Supply Chain Management.
author: sherry-zheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e6f7e0a3978bbf7e520f8cbcfd27c4cfe507777
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114672"
---
# <a name="inventory-visibility-add-in"></a>Componente aggiuntivo Inventory Visibility

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Il componente aggiuntivo Inventory Visibility è un microservizio indipendente e altamente scalabile che consente il monitoraggio dell'inventario disponibile in tempo reale, fornendo così una visione globale della visibilità dell'inventario.

Tutte le informazioni relative alle scorte disponibili vengono esportate nel servizio quasi in tempo reale tramite l'integrazione SQL di basso livello. I sistemi esterni accedono al servizio tramite API RESTful per interrogare le informazioni sulle scorte disponibili su determinati set di dimensioni, recuperando così un elenco di posizioni disponibili.

Inventory Visibility è un microservizio basato su Microsoft Dataverse, il che significa che è possibile estenderlo creando Power Apps e applicando Power BI per fornire funzionalità personalizzate per soddisfare i requisiti aziendali. È anche possibile aggiornare l'indice per eseguire query sull'inventario.

Inventory Visibility fornisce opzioni di configurazione che consentono l'integrazione con più sistemi di terze parti. Supporta la dimensione dell'inventario standardizzata, l'estensibilità personalizzata e le quantità calcolate standardizzate e configurabili.

Questo argomento descrive come installare e configurare il componente aggiuntivo Inventory Visibility per Dynamics 365 Supply Chain Management e come utilizzare l'API.

## <a name="install-the-inventory-visibility-add-in"></a>Installare il componente aggiuntivo Inventory Visibility

È necessario installare il componente aggiuntivo Inventory Visibility utilizzando Microsoft Dynamics Lifecycle Services (LCS). LCS è un portale di collaborazione che fornisce un ambiente e una serie di servizi regolarmente aggiornati che aiutano a gestire il ciclo di vita dell'applicazione delle app Dynamics 365 Finance and Operations.

Per ulteriori informazioni, vedere [Risorse Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).

### <a name="prerequisites"></a>Prerequisiti

Prima di poter installare il componente aggiuntivo Inventory Visibility è necessario effettuare quanto segue:

- Ottenere un progetto di implementazione LCS con almeno un ambiente distribuito.
- Generare le chiavi beta per l'offerta in LCS.
- Abilitare le chiavi beta per l'offerta per l'utente in LCS.
- Contattare il team del prodotto Microsoft Inventory Visibility e fornire un ID ambiente in cui si desidera distribuire il componente aggiuntivo Inventory Visibility.

In caso di domande su questi prerequisiti, contattare il team del prodotto Inventory Visibility.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Installare il componente aggiuntivo

Per installare il componente aggiuntivo Inventory Visibility effettuare quanto segue:

1. Accedere al portale [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Nella home page, selezionare il progetto in cui è distribuito l'ambiente.
1. Nella pagina del progetto, selezionare l'ambiente in cui si desidera installare il componente aggiuntivo.
1. Nella pagina dell'ambiente, scorrere verso il basso fino a visualizzare la sezione **Componenti aggiuntivi per l'ambiente**. Se la sezione non è visibile, assicurarsi che le chiavi beta dei prerequisiti siano state completamente elaborate.
1. Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.
    ![La pagina dell'ambiente in LCS](media/inventory-visibility-environment.png "La pagina dell'ambiente in LCS")
1. Selezionare il collegamento **Installare un nuovo componente aggiuntivo**. Si apre un elenco di componenti aggiuntivi disponibili.
1. Selezionare il servizio **Inventory** dall'elenco. Nota: potrebbe ora essere elencato come **Componente aggiuntivo Inventory Visibility per Dynamics 365 Supply Chain Management**.
1. Immettere i valori per i seguenti campi per il proprio ambiente:

    - **ID applicazione AAD**
    - **ID tenant AAD**

    ![Pagina Impostazione del componente aggiuntivo](media/inventory-visibility-setup.png "Pagina Impostazione del componente aggiuntivo")

1. Accettare le condizioni selezionando la casella di controllo **Condizioni**.
1. Seleziona **Installa**. Lo stato del componente aggiuntivo verrà visualizzato com e **Installazione**. Al termine, aggiornare la pagina per vedere lo stato cambiare in **Installato**.

### <a name="get-a-security-service-token"></a>Ottenere un token per il servizio di sicurezza

Ottieni un token del servizio di sicurezza effettuando le seguenti operazioni:

1. Accedere al portale di Azure e utilizzarlo per trovare `clientId` e `clientSecret` per la tua applicazione di Supply Chain Management.
1. Recuperare un token Azure Active Directory (`aadToken`) inviando una richiesta HTTP con le seguenti proprietà:
    - **URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
    - **Metodo** - `GET`
    - **Contenuto del corpo (dati del modulo)**:

        | chiave | valore |
        | --- | --- |
        | client_id | ${aadAppId} |
        | client_secret | ${aadAppSecret} |
        | grant_type | client_credentials |
        | risorsa | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
1. Dovresti ricevere un `aadToken` in risposta, che assomiglia al seguente esempio.

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

1. Formulare una richiesta JSON simile alla seguente:

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    Percorso:
    - Il valore `client_assertion` deve essere `aadToken` ricevuto nel passaggio precedente.
    - Il valore `context` deve essere l'ID dell'ambiente in cui si desidera distribuire il componente aggiuntivo.
    - Impostare tutti gli altri valori come mostrato nell'esempio.

1. Inviare una richiesta HTTP con le seguenti proprietà:
    - **URL** - `https://securityservice.operations365.dynamics.com/token`
    - **Metodo** - `POST`
    - **Intestazione HTTP**: includere la versione API (la chiave è `Api-Version` e il valore è `1.0`)
    - **Contenuto del corpo**: includi la richiesta JSON che hai creato nel passaggio precedente.

1. Viene restituito un `access_token` in risposta. Questo è ciò di cui si ha bisogno come token di connessione per chiamare l'API di Inventory Visibility. Ecco un esempio.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a>Disinstallare il componente aggiuntivo

Per disinstallare il componente aggiuntivo, selezionar e **Disinstalla**. Aggiornare LCS e il componente aggiuntivo Inventory Visibility verrà rimosso. Il processo di disinstallazione rimuoverà la registrazione del componente aggiuntivo e avvierà anche un processo per pulire tutti i dati aziendali archiviati nel servizio.

## <a name="inventory-visibility-add-in-public-api"></a>API pubblica del componente aggiuntivo Inventory Visibility

L'API REST pubblica del componente aggiuntivo Inventory Visibility presenta diversi endpoint specifici di integrazione. Supporta tre principali tipi di interazione:

- Inserimento delle modifiche delle scorte disponibili al componente aggiuntivo da un sistema esterno.
- Interrogazione delle quantità disponibili correnti da un sistema esterno.
- Sincronizzazione automatica con le scorte disponibili di Supply Chain Management.

La sincronizzazione automatica non fa parte dell'API pubblica ma viene invece gestita in background per gli ambienti che hanno abilitato il componente aggiuntivo Inventory Visibility.

### <a name="authentication"></a>Autenticazione

Il token di sicurezza della piattaforma viene utilizzato per chiamare il componente aggiuntivo Inventory Visibility, quindi è necessario generare un token Azure Active Directory utilizzando l'applicazione Azure Active Directory.

Per ulteriori informazioni su come ottenere il token di sicurezza, vedere [Installare il componente aggiuntivo Inventory Visibility](#install-add-in).

### <a name="configure-the-inventory-visibility-api"></a>Configurare l'API di Inventory Visibility

Prima di utilizzare il servizio, è necessario completare le configurazioni descritte nelle sottosezioni seguenti. La configurazione può variare in base ai dettagli del proprio ambiente. Comprende principalmente quattro parti:

- [Partizionamento](#partitioning)
- [Configurazioni delle dimensioni](#dimension-configurations)
- [Indicizzazione](#indexing)
- [Misura personalizzata](#custom-measurement)

#### <a name="partitioning"></a>Partizionamento

Il partizionamento può influenzare in modo significativo le prestazioni dell'API di Inventory Visibility. È una buona idea definire uno schema che consenta piccoli raggruppamenti di dati pur consentendo query di dati significative.

L'elemento `organizationId` (`dataAreaId` in Supply Chain Management) farà sempre parte del partizionamento e, per impostazione predefinita, Inventory Visibility è impostato su partizionamento per dimensioni come *Sito + Posizione*. Ciò significa che il servizio deve essere sempre interrogato con queste dimensioni definite sui filtri.

> [!NOTE]
> *Sito* e *Posizione* sono due dimensioni predefinite generali in Inventory Visibility. In Supply Chain Management, queste dimensioni vengono chiamate *Sito* (`InventSiteId`) e *Magazzino* (`InventLocationId`)

### <a name="dimension-configurations"></a>Configurazioni delle dimensioni

Inventory Visibility fornirà un elenco di dimensioni predefinite generali per abilitare l'integrazione di più sistemi di origine.

La tabella seguente elenca le dimensioni dell'inventario che saranno i nomi delle dimensioni predefinite in Inventory Visibility.

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

> [!NOTE]
> Il tipo di dimensione elencato nella tabella precedente è solo di riferimento. Non è necessario definire il tipo di dimensione in Inventory Visibility.

Se esiste una dimensione personalizzata che diventare un valore predefinito quando viene utilizzata da Inventory Visibility, è possibile configurare il nome **Dimensione personalizzata** in Inventory Visibility.

I sistemi esterni accedono a Inventory Visibility tramite le API RESTful che consentono di interrogare le informazioni disponibili su determinati set di dimensioni. Per l'integrazione, Inventory Visibility consente di configurare l'*origine dati del canale esterno* e la dimensione di origine sulle *dimensioni di destinazione* in Inventory Visibility.

Le dimensioni di destinazione deve essere una delle seguenti:

- Dimensioni predefinite in Inventory Visibility
- Dimensioni personalizzate

Lo scopo della configurazione delle dimensioni è standardizzare l'integrazione multi-sistema per la query sulle dimensioni e l'evento di registrazione con le dimensioni.

#### <a name="indexing"></a>Indicizzazione

La maggior parte delle volte, la query delle scorte disponibili non sarà solo sul livello "totale" più alto, ma si potrebbe voler vedere i risultati aggregati in base alle dimensioni dell'inventario.

Inventory Visibility offre flessibilità consentendo di impostare gli indici, che si basano sulla dimensione o sulla combinazione delle dimensioni.

> [!NOTE]
> Al momento, è possibile configurare solo fino a un massimo di cinque indici. È necessario considerare attentamente quale dimensione o combinazione di dimensioni si utilizzerà prima dell'implementazione per assicurarsi che soddisfi le esigenze aziendali. Ad esempio, se si desidera eseguire query sui prodotti come segue:

- Query delle scorte del prodotto aggregato per dimensioni *Colore* e *Dimensione*.
- In alcuni casi, si desidera solo eseguire una query sul prodotto in totale.

Sarebbero disponibili due indici definiti come segue:

- `["ColorId", "SizeId"]`
- `[]`

La parentesi vuota si aggregherà in base all'ID del prodotto all'interno della partizione.

L'indicizzazione definisce come raggruppare i risultati in base all'impostazione della query `groupBy`. In questo caso se non si definiscono valori `groupBy` si ottengono i totali per `productid`. Altrimenti se si definisce `groupBy` come `groupBy=ColorId&groupBy=SizeId`, verranno restituite più righe, in base alle diverse combinazioni di colori e dimensioni nel sistema.

È possibile inserire i criteri della query nel corpo della richiesta.

Ecco una query di esempio sul prodotto con combinazione di colore e dimensione.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a>Misura personalizzata

Le quantità di misura predefinite sono collegate a Supply Chain Management, tuttavia potrebbe essere necessario disporre di una quantità composta da una combinazione delle misure predefinite. Per fare ciò, è possibile avere una configurazione di quantità personalizzate, che verranno aggiunte all'output delle query disponibili.

La funzionalità consente semplicemente di definire un insieme di misure che verranno aggiunte, e/o un insieme di misure che verranno sottratte, in modo da ottenere dalla misura personalizzata.

Ad esempio, con la seguente condizione di query, si configura la quantità di misura personalizzata come `MyCustomAvailableforReservation` per essere utilizzata dal sistema di consumo.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| Sistema di consumo | Misure calcolate | Origine dati | Modificatore | Tipo di calcolo del modificatore |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | Addizione |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | Addizione |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | Sottrazione |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | Addizione |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | Sottrazione |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | Addizione |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | Addizione |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | Sottrazione |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | Sottrazione |

Con ciò, la query sulla quantità di misura personalizzata restituirà il seguente output.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
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

L'output `MyCustomAvailableforReservation` si basa sull'impostazione del calcolo nelle misure personalizzate come:  
 *100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*

### <a name="posting-on-hand-changes"></a>Registrazione delle modifiche delle scorte disponibili

L'URL esatto in cui verrà pubblicato l'evento dipenderà dalla regione geografica. Avrà il formato:

`https://{serviceURL}/api/environment/{environmentId}/onhand`

Una volta autenticato, questo URL può essere utilizzato insieme al metodo HTTP `POST` per inviare al servizio eventi di modifica delle scorte disponibili.

Un'intestazione speciale viene utilizzata per comunicare con i servizi Dynamics 365 tramite richieste HTTP, indicando l'ID ambiente dell'istanza di Supply Chain Management a cui sono collegati i dati. Ad esempio:

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a>Registrazione delle modifiche delle scorte disponibili - esempio di query 1

Questo esempio mostra uno scenario in cui verrà impostata la configurazione della dimensione in Power Apps.

Utilizzare la seguente query per configurare la mappatura delle dimensioni in Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Ora è possibile specificare `dimensionDataSource` e utilizzare le dimensioni personalizzate nelle query. Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a>Registrazione delle modifiche delle scorte disponibili - esempio di query 2

Questo esempio mostra uno scenario in cui non sono impostate mappature per la configurazione della dimensione in Power Apps, quindi la registrazione deve utilizzare anche le dimensioni di base. Tutte le dimensioni devono essere dimensioni di base quando il campo `dimensionDataSource` è nullo, vuoto o spazio bianco.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a>Proprietà dei campi del documento JSON

I campi degli esempi di query JSON forniti in precedenza hanno le proprietà elencate nella tabella seguente.

| ID campo | descrizione |
|---|---|
| `id` | Un ID univoco per l'evento di modifica specifico. Questo ID viene utilizzato per garantire che se la comunicazione con il servizio non riesce durante la registrazione, il reinvio dell'evento non comporta il doppio conteggio dello stesso evento nel sistema. |
| `organizationId` | L'identificatore dell'organizzazione collegata all'evento. Viene mappato agli ID area dati o alle organizzazioni di Supply Chain Management. |
| `productId` | L'identificatore del prodotto in questione. |
| `quantity` | La quantità in base alla quale è necessario modificare la disponibilità. Se, ad esempio, 10 nuovi bagel venissero aggiunti a uno scaffale, questo valore sarebbe 10. Se 3 bagel venissero poi rimossi dallo scaffale o venduti, questo valore sarebbe -3. |
| `dimensionDataSource` | L'origine dati delle dimensioni utilizzate nella query e nell'evento di modifica della registrazione. Se si specifica l'origine dati, è possibile utilizzare le dimensioni personalizzate dell'origine dati specificata. Con la configurazione delle dimensioni, Inventory Visibility può mappare le dimensioni personalizzate alle dimensioni predefinite generali. Se `dimensionDataSource` non è specificato, è possibile utilizzare solo le dimensioni predefinite generali nelle query.   |
| `dimensions` | Un insieme dinamico di coppie chiave/valore. Questi verranno mappati ad alcune dimensioni in Supply Chain Management, ma è possibile anche aggiungere dimensioni personalizzate (come *origine*) che può indicare se l'evento proveniva da Supply Chain Management o da un sistema esterno. |

### <a name="querying-current-on-hand"></a>Interrogazione delle quantità disponibili correnti

L'endpoint per l'interrogazione delle quantità disponibili correnti avrà un URL simile:

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

Sarà interrogato con il metodo HTTP `POST`.

#### <a name="current-on-hand-query-example-1"></a>Esempio di query delle quantità disponibili correnti 1

Questo esempio mostra uno scenario in cui è già stata impostata la configurazione della dimensione in Power Apps.

Utilizzare la seguente query per configurare la mappatura delle dimensioni in Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Ora è possibile specificare `dimensionDataSource` e utilizzare le dimensioni personalizzate nelle query. Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base. È possibile specificare `DimensionDataSource` in `filters` e specificare le dimensioni personalizzate in `filters` e `groupByValues`. Il sistema convertirà automaticamente le dimensioni personalizzate in dimensioni di base.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a>Esempio di query delle quantità disponibili correnti 2

Questo esempio mostra uno scenario in cui non sono impostate mappature per la configurazione della dimensione in Power Apps, quindi la registrazione deve utilizzare anche le dimensioni di base. Tutte le dimensioni devono essere dimensioni di base quando il campo `dimensionDataSource` in `filters` è nullo, vuoto o spazio bianco.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a>Esempio di risultato restituito

Le query mostrate negli esempi precedenti potrebbero restituire un risultato come questo.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
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

Notare che i campi delle quantità sono strutturati come un dizionario di misure e dei valori associati.
