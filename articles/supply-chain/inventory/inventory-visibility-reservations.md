---
title: Prenotazioni di Inventory Visibility
description: Questo articolo descrive come impostare la funzione di prenotazione per creare prenotazioni, consumare prenotazioni, e/o sbloccare quantità di inventario specificate usando Visibilità dell'inventario.
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
ms.openlocfilehash: 3b74907709ab97ddf4cc829dba324df213ca229f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895730"
---
# <a name="inventory-visibility-reservations"></a>Prenotazioni di Inventory Visibility

[!include [banner](../includes/banner.md)]


Questo articolo descrive come impostare la funzione di prenotazione per creare prenotazioni, consumare prenotazioni, e/o sbloccare quantità di inventario specificate usando Visibilità dell'inventario.

Le prenotazioni segnano una quantità di inventario che sarà utilizzata in futuro. Quando crei una prenotazione, il sistema impedisce ad altri ordini di riservare o consumare la merce riservata fino a quando la prenotazione non viene consumata o non è più riservata. Le prenotazioni vengono create, consumate e cancellate utilizzando chiamate API al servizio Visibilità dell'inventario.

È possibile impostare opzionalmente Microsoft Dynamics 365 Supply Chain Management (e altri sistemi di terze parti) per compensare automaticamente la quantità che è stata riservata utilizzando la Visibilità dell'inventario. La quantità compensata è cancellata dalle registrazioni di prenotazione in Visibilità dell'inventario.

Quando attivate la funzione di prenotazione, Supply Chain Management diventa automaticamente pronto a compensare le prenotazioni che vengono fatte usando Visibilità dell'inventario.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Attivare e configurare la funzionalità di prenotazione

Per attivare la funzione di prenotazione, seguite questi passi.

1. Accedere a Power Apps e aprire **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Gestione funzioni** , attiva la funzione *OnHandReservation* .
1. Accedere a Supply Chain Management.
1. Andare all'area di lavoro **[Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e abilitare la funzionalità *Integrazione di Visibilità inventario con offset della prenotazione* (richiede la versione 10.0.22 o successiva).
1. Andare a **Gestione inventario \> Impostazione \> Parametri di integrazione di Visibilità inventario**, aprire la scheda **Offset prenotazione** ed effettuare le seguenti impostazioni:
    - **Abilita offset prenotazione** - Impostare su *Sì* per abilitare questa funzionalità.
    - **Modificatore offset prenotazione** - Selezionare lo stato della transazione di inventario che eseguirà l'offset delle prenotazioni effettuato su Visibilità inventario. Questa impostazione determina la fase di elaborazione dell'ordine che attiva gli offset. La fase è tracciata dallo stato di transazione dell'inventario dell'ordine. Sono disponibili le seguenti opzioni:
        - *Su ordine* - Per lo stato *On transaction* , un ordine invierà una richiesta di offset quando viene creato. La quantità su cui è stato eseguito l'offset sarà la quantità dell'ordine creato.
        - *Riserva* - Per lo stato di *transazione Riserva ordinata* , un ordine invierà una richiesta di compensazione quando viene prenotato, prelevato, imbucato o fatturato. La richiesta sarà attivata solo una volta, per il primo passo quando si verifica il processo menzionato. La quantità su cui è stato eseguito l'offset sarà la quantità da cui lo stato della transazione di inventario è stato modificato da *Merci ordinate in corso di consegna* a *Ordinato prenotato* (o stato successivo) nella riga dell'ordine corrispondente.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Utilizzare la funzione di prenotazione in Visibilità dell'inventario

Quando chiamate l'API di prenotazione, il sistema segna la prenotazione delle merci e delle quantità specificate. È necessario definire una gerarchia di prenotazione e pubblicare le richieste che corrispondono a tale gerarchia di prenotazione. Le prenotazioni possono poi essere effettuate chiamando direttamente le API di prenotazione.

### <a name="configure-the-reservation-hierarchy"></a>Configurare la gerarchia delle prenotazioni

La gerarchia delle prenotazioni descrive la sequenza delle dimensioni che devono essere specificate quando si fanno le prenotazioni. Funziona nello stesso modo in cui la gerarchia degli indici funziona per le query on-hand.

La gerarchia delle prenotazioni può essere diversa dalla gerarchia degli indici. Questa indipendenza permette di implementare la gestione delle categorie in cui gli utenti possono scomporre le dimensioni in dettagli per specificare i requisiti per fare prenotazioni più precise.

Per configurare una gerarchia di prenotazioni preliminari in Power Apps, aprire la pagina **Configurazione** e quindi, nella scheda **Gerarchia delle prenotazioni preliminari**, impostare la gerarchia di prenotazioni aggiungendo e/o modificando le dimensioni e i relativi livelli di gerarchia.

La gerarchia delle prenotazioni preliminari dovrebbe contenere `SiteId` e `LocationId` come componenti perché costruiscono la configurazione della partizione.

Per ulteriori informazioni su come configurare le prenotazioni, vedere [Configurazione della prenotazione](inventory-visibility-configuration.md#reservation-configuration).

### <a name="call-the-reservation-api"></a>Chiamare l'API di prenotazione

Le prenotazioni sono fatte nel servizio di Visibilità dell'inventario inviando una richiesta POST all'URL del servizio, come `/api/environment/{environment-ID}/onhand/reserve`.

Per una prenotazione, il corpo della richiesta deve contenere un ID dell'organizzazione, un ID del prodotto, quantità riservate e dimensioni. La richiesta genera un ID di prenotazione unico per ogni record di prenotazione. Il record di prenotazione contiene la combinazione unica dell'ID del prodotto e delle dimensioni.

Quando si chiama l'API di prenotazione, è possibile controllare la convalida della prenotazione specificando il parametro booleano `ifCheckAvailForReserv` nel corpo della richiesta. Un valore di `True` significa che è richiesta la convalida, mentre un valore di `False` significa che la convalida non è richiesta. Il valore predefinito è `True`.

Se si desidera annullare una prenotazione o annullare la prenotazione di quantità di inventario specificate, impostare la quantità su un valore negativo e impostare il parametro `ifCheckAvailForReserv` su `False` per saltare la convalida.

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

### <a name="set-up-the-reservation-offset-modifier"></a>Configurare il modificatore di offset della prenotazione

Se non è stata ancora effettuata tale operazione, configurare il modificatore di prenotazione come descritto in [Attivare e configurare la funzionalità di prenotazione](#turn-on).

### <a name="set-up-reservation-ids"></a>Impostare gli ID di prenotazione

L'ID della prenotazione contrassegna in modo univoco un record di prenotazione nella Visibilità dell'inventario. In Supply Chain Management, gli utenti mettono le prenotazioni sulle linee d'ordine per segnare l'offset del record di prenotazione corrispondente.

Per impostare gli ID di prenotazione in Supply Chain Management, seguite questi passi.

1. Aprire un ordine di vendita (per esempio, dalla pagina **Tutti gli ordini di vendita** ).
1. Nella FastTab **Linee d'ordine di vendita** , seleziona una linea d'ordine.
1. Nella FastTab delle **linee dell'ordine di vendita** , sulla barra degli strumenti, seleziona **Aggiorna linea \> Inventario \> Integrazione della visibilità dell'inventario**.
1. Inserisci i relativi ID di prenotazione.

Il cambiamento di stato dell'inventario corrisponde all'impostazione del modificatore di offset.
