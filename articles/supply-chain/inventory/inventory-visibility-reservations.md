---
title: Prenotazioni di visibilità dell'inventario
description: Questo argomento descrive come impostare la funzione di prenotazione per creare prenotazioni, consumare prenotazioni, e/o sbloccare quantità di inventario specificate usando Visibilità dell'inventario.
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
ms.openlocfilehash: 6c87018cbfbe22fbbc441a1a23aee0ac44af9ddc
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345151"
---
# <a name="inventory-visibility-reservations"></a>Prenotazioni di visibilità dell'inventario

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Questo argomento descrive come impostare la funzione di prenotazione per creare prenotazioni, consumare prenotazioni, e/o sbloccare quantità di inventario specificate usando Visibilità dell'inventario.

Le prenotazioni segnano una quantità di inventario che sarà utilizzata in futuro. Quando crei una prenotazione, il sistema impedisce ad altri ordini di riservare o consumare la merce riservata fino a quando la prenotazione non viene consumata o non è più riservata. Le prenotazioni vengono create, consumate e cancellate utilizzando chiamate API al servizio Visibilità dell'inventario.

È possibile impostare opzionalmente Microsoft Dynamics 365 Supply Chain Management (e altri sistemi di terze parti) per compensare automaticamente la quantità che è stata riservata utilizzando la Visibilità dell'inventario. La quantità compensata è cancellata dalle registrazioni di prenotazione in Visibilità dell'inventario.

Quando attivate la funzione di prenotazione, Supply Chain Management diventa automaticamente pronto a compensare le prenotazioni che vengono fatte usando Visibilità dell'inventario.

> [!NOTE]
> La funzionalità offset richiede la versione 10.0.22 o successiva di Supply Chain Management. Se vuoi usare le prenotazioni di Visibilità dell'inventario, ti consigliamo di aspettare di aver aggiornato Supply Chain Management alla versione 10.0.22 o successiva.

## <a name="turn-on-the-reservation-feature"></a>Attivare la funzione di prenotazione

Per attivare la funzione di prenotazione, seguite questi passi.

1. In Power Apps, aprite **Visibilità dell'inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Gestione funzioni** , attiva la funzione *OnHandReservation* .
1. Accedere a Supply Chain Management.
1. Vai a **Inventory Management \> Impostazione \> Visibilità dell'inventario integration parameters**.
1. Sotto **Offset prenotazione**, impostate l'opzione **Abilita offset prenotazione** su *Yes*.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Utilizzare la funzione di prenotazione in Visibilità dell'inventario

Quando chiamate l'API di prenotazione, il sistema segna la prenotazione delle merci e delle quantità specificate. È necessario definire una gerarchia di prenotazione e pubblicare le richieste che corrispondono a tale gerarchia di prenotazione. Le prenotazioni possono poi essere effettuate chiamando direttamente le API di prenotazione.

### <a name="configure-the-reservation-hierarchy"></a>Configurare la gerarchia delle prenotazioni

La gerarchia delle prenotazioni descrive la sequenza delle dimensioni che devono essere specificate quando si fanno le prenotazioni. Funziona nello stesso modo in cui la gerarchia degli indici funziona per le query on-hand.

La gerarchia delle prenotazioni può essere diversa dalla gerarchia degli indici. Questa indipendenza permette di implementare la gestione delle categorie in cui gli utenti possono scomporre le dimensioni in dettagli per specificare i requisiti per fare prenotazioni più precise.

Per configurare una gerarchia di soft reservation in Power Apps, apri la pagina **Configurazione** e poi, nella scheda **Mapping prenotazione preliminare** , imposta la gerarchia di prenotazione aggiungendo e/o modificando le dimensioni e i loro livelli di gerarchia.

### <a name="call-the-reservation-api"></a>Chiamare l'API di prenotazione

Le prenotazioni sono fatte nel servizio di Visibilità dell'inventario inviando una richiesta POST all'URL del servizio, come `/api/environment/{environment-ID}/onhand/reserve`.

Per una prenotazione, il corpo della richiesta deve contenere un ID dell'organizzazione, un ID del prodotto, quantità riservate e dimensioni. La richiesta genera un ID di prenotazione unico per ogni record di prenotazione. Il record di prenotazione contiene la combinazione unica dell'ID del prodotto e delle dimensioni.

Ecco un esempio del corpo della richiesta, per riferimento.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
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
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "SoftReservOrdered",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

## <a name="offset-reservations-in-supply-chain-management"></a>Prenotazioni di compensazione in Supply Chain Management

Per gli stati di transazione dell'inventario che includono un modificatore di compensazione della riserva specificato, l'aggiornamento della transazione compenserà il record di prenotazione corrispondente quando tutte le seguenti condizioni sono soddisfatte:

- L'ID della prenotazione sulla transazione d'inventario corrisponde all'ID della prenotazione del record della prenotazione nel servizio Visibilità dell'inventario.
- Le dimensioni della transazione d'inventario sono identiche alle dimensioni del record di prenotazione nel servizio Visibilità dell'inventario.
- I cambiamenti nello stato della transazione d'inventario innescano compensazioni per le prenotazioni quando lo stato della transazione d'inventario riflette il fatto che un processo dell'ordine è stato completato o saltato.

La quantità compensata segue la quantità d'inventario che è specificata nelle transazioni d'inventario. L'offset non ha effetto se nessuna quantità riservata rimane nel servizio Visibilità dell'inventario.

> [!NOTE]
> La funzionalità di offset è disponibile a partire dalla versione 10.0.22

### <a name="set-up-the-reserve-offset-modifier"></a>Impostare il modificatore di offset della riserva

Il modificatore di offset di riserva determina la fase di elaborazione dell'ordine che fa scattare gli offset. La fase è tracciata dallo stato di transazione dell'inventario dell'ordine. Per impostare il modificatore di offset di riserva, seguite questi passi.

1. Vai a **Gestione dell'inventario \> Impostazione \> Parametri di integrazione della visibilità dell'inventario \> Offset di prenotazione**.
1. Impostare il campo **Modificatore offset prenotazione** su uno dei seguenti valori:

    - *Su ordine* - Per lo stato *On transaction* , un ordine invierà una richiesta di offset quando viene creato.
    - *Riserva* - Per lo stato di *transazione Riserva ordinata* , un ordine invierà una richiesta di compensazione quando viene prenotato, prelevato, imbucato o fatturato. La richiesta sarà attivata solo una volta, per il primo passo quando si verifica il processo menzionato.

### <a name="set-up-reservation-ids"></a>Impostare gli ID di prenotazione

L'ID della prenotazione contrassegna in modo univoco un record di prenotazione nella Visibilità dell'inventario. In Supply Chain Management, gli utenti mettono le prenotazioni sulle linee d'ordine per segnare l'offset del record di prenotazione corrispondente.

Per impostare gli ID di prenotazione in Supply Chain Management, seguite questi passi.

1. Aprire un ordine di vendita (per esempio, dalla pagina **Tutti gli ordini di vendita** ).
1. Nella FastTab **Linee d'ordine di vendita** , seleziona una linea d'ordine.
1. Nella FastTab delle **linee dell'ordine di vendita** , sulla barra degli strumenti, seleziona **Aggiorna linea \> Inventario \> Integrazione della visibilità dell'inventario**.
1. Inserisci i relativi ID di prenotazione.

Il cambiamento di stato dell'inventario corrisponde all'impostazione del modificatore di offset.
