---
title: Allocazione inventario di Inventory Visibility
description: Questo articolo spiega come impostare e utilizzare la funzione di allocazione dell'inventario, che ti consente di mettere da parte un inventario dedicato per assicurarti di soddisfare i tuoi canali o clienti più redditizi.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: ccc3a8c4b3d0649397b1d1f9139f7feebf39b02f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852507"
---
# <a name="inventory-visibility-inventory-allocation"></a>Allocazione inventario di Inventory Visibility

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Background aziendale e scopo

In molti casi, produttori, rivenditori e altri titolari di attività della catena di approvvigionamento devono allocare in anticipo le scorte per importanti canali di vendita, località o clienti o per eventi di vendita specifici. L'allocazione delle scorte è una pratica tipica nel processo di pianificazione operativa delle vendite e viene eseguita prima che si verifichino le attività di vendita effettive e venga creato un ordine cliente.

Ad esempio, un'azienda di biciclette ha scorte limitate disponibili per una bicicletta molto popolare. Questa azienda effettua vendite sia online che in negozio. In ogni canale di vendita, l'azienda ha alcuni importanti partner aziendali (marketplace e grandi rivenditori) che richiedono che una parte specifica dell'inventario disponibile della bicicletta venga salvata per loro. Pertanto, l'azienda di biciclette deve essere in grado di bilanciare la distribuzione delle azioni attraverso i canali e anche di gestire le aspettative dei suoi partner VIP. Il modo migliore per raggiungere entrambi gli obiettivi è utilizzare l'allocazione dell'inventario, in modo che ogni canale e rivenditore possano ricevere quantità specifiche allocate che possono essere vendute ai consumatori in un secondo momento.

L'allocazione dell'inventario ha due scopi aziendali fondamentali:

- **Protezione dell'inventario (ringfencing)** – Le organizzazioni desiderano allocare in anticipo scorte limitate a canali prioritari, aree, clienti VIP e società sussidiarie. La funzione di allocazione Inventory Visibility mira a proteggere l'inventario allocato, in modo che altre allocazioni, prenotazioni o altre richieste di vendita non influiscano sull'inventario allocato in precedenza.
- **Controllo delle vendite eccessive** – La funzione di allocazione della visibilità dell'inventario mira a limitare le quantità assegnate in precedenza, in modo che la parte ricevente (ad esempio un canale o un gruppo di clienti) non le consumi eccessivamente quando l'effettiva transazione di vendita si basa su una prenotazione temporanea che entra in vigore.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Definizione dell'allocazione nel servizio di visibilità inventario

Sebbene la funzione di allocazione nel servizio di visibilità inventario non metta da parte le quantità di inventario fisico, fa riferimento alla quantità di inventario fisico disponibile per definirne la quantità di pool virtuale iniziale *disponibile per l'assegnazione*. L'allocazione dell'inventario in Inventory Visibility è un'allocazione temporanea. Viene eseguita prima che si verifichino le transazioni di vendita effettive e non dipende dagli ordini cliente. Ad esempio, puoi allocare le scorte ai tuoi canali di vendita più importanti o ai grandi rivenditori aziendali prima che i clienti finali visitino il canale di vendita o il negozio al dettaglio per acquistare.

La differenza tra allocazione dell'inventario e [prenotazione temporanea dell'inventario](inventory-visibility-reservations.md) è che la prenotazione temporanea è solitamente collegata alle transazioni di vendita effettive (righe dell'ordine cliente). Pertanto, se vuoi utilizzare insieme le funzioni di allocazione e prenotazione temporanea, ti consigliamo di eseguire prima l'allocazione delle scorte e quindi la prenotazione temporanea rispetto alle quantità allocate. Per ulteriori informazioni, vedi [Consumare come prenotazione temporanea](#consume-to-soft-reserved).

La funzione di allocazione dell'inventario consente ai pianificatori delle vendite o ai responsabili di account chiave di gestire e allocare in anticipo le scorte importanti tra gruppi di allocazione (come canali, aree e gruppi di clienti). Supporta anche il monitoraggio, la rettifica e l'analisi in tempo reale del consumo rispetto alle quantità assegnate, in modo che il rifornimento o la riallocazione possano essere eseguiti in tempo. Questa capacità di avere visibilità in tempo reale sull'allocazione, sul consumo e sul saldo dell'allocazione è particolarmente importante in occasione di vendite rapide o eventi promozionali.

## <a name="terminology"></a>Terminologia

I seguenti termini e concetti sono utili nelle discussioni sull'allocazione dell'inventario:

- **Gruppo di allocazione** – Il gruppo proprietario dell'allocazione, ad esempio un canale di vendita, un gruppo di clienti o un tipo di ordine.
- **Valore del gruppo di allocazione** – Il valore di ciascun gruppo di allocazione. Per esempio, *web* o *negozio* potrebbe essere il valore del gruppo di allocazione del canale di vendita, mentre *VIP* o *normale* potrebbe essere il valore del gruppo di allocazione del cliente.
- **Gerarchia di allocazione** – Un mezzo per combinare i gruppi di allocazione in modo gerarchico. Ad esempio, puoi definire *canale* come livello gerarchico 1, *area* come livello 2, e *gruppo di clienti* come livello 3. Durante l'allocazione delle scorte, è necessario seguire la sequenza della gerarchia di allocazione quando si specifica il valore del gruppo di allocazione. Ad esempio, potresti assegnare 200 biciclette rosse al canale *Web*, all'area *Londra* e al gruppo di clienti *VIP*.
- **Disponibile per l'allocazione** - Il *pool comune virtuale* che indica la quantità disponibile per un'ulteriore allocazione. È una misura calcolata che puoi definire liberamente utilizzando la tua formula. Se stai utilizzando anche la funzione di prenotazione temporanea, ti consigliamo di utilizzare la stessa formula per calcolare la disponibilità per l'allocazione e la disponibilità per la prenotazione.
- **Allocato** – Una misura fisica che mostra la quota allocata che può essere utilizzata dai gruppi di allocazione.
- **Consumato** – Una misura fisica che indica le quantità che sono state consumate rispetto alla quantità allocata originale. Man mano che i numeri vengono aggiunti a questa misura fisica, la misura fisica allocata viene automaticamente ridotta.

L'illustrazione seguente mostra il flusso di lavoro aziendale per l'allocazione dell'inventario.

![Flusso di lavoro aziendale di allocazione di Inventory Visibility.](media/inventory-visibility-allocation-flow.png "Flusso di lavoro aziendale di allocazione di Inventory Visibility.")

## <a name="set-up-inventory-allocation"></a>Impostare l'allocazione dell'inventario

La funzione di allocazione dell'inventario è composta dai seguenti componenti:

- L'origine dati predefinita relativa all'allocazione, le misure fisiche e le misure calcolate.
- Gruppi di allocazione personalizzabili con un massimo di otto livelli.
- Un set di API di allocazione:

    - allocate
    - reallocate
    - unallocate
    - consume
    - query

Il processo di configurazione della funzione di allocazione prevede due passaggi:

- Imposta [l'origine dati](inventory-visibility-configuration.md#data-source-configuration) e [le misure](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Imposta il nome e la gerarchia del gruppo di allocazione.

### <a name="predefined-data-source"></a>Origine dati predefinita

Quando si abilita la funzione di allocazione e si chiama l'API di aggiornamento della configurazione, la visibilità dell'inventario crea un'origine dati predefinita e diverse misure iniziali.

L'origine dati è denominata `@iv`.

Ecco le misure fisiche iniziali:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Ecco le misure calcolate iniziali:

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Aggiungere altre misure fisiche alla misura calcolata disponibile per l'allocazione

Per utilizzare l'allocazione, è necessario impostare la misura calcolata disponibile per l'allocazione (`@iv.@available_to_allocate`). Ad esempio, hai l'origine dati `fno` e la misura `onordered`, l'origine dati `pos` e la misura `inbound` e vuoi fare l'allocazione delle scorte per la somma di `fno.onordered` e `pos.inbound`. In questo caso, `@iv.@available_to_allocate` deve contenere `pos.inbound` e `fno.onordered` nella formula. Ecco un esempio:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

### <a name="change-the-allocation-group-name"></a>Modificare il nome del gruppo di allocazione

È possibile impostare un massimo di otto nomi di gruppi di assegnazione. I gruppi hanno una gerarchia.

Imposta i nomi dei gruppi nella pagina **Configurazione di Power App per Inventory Visibility**. Per aprire questa pagina, nel tuo ambiente Microsoft Dataverse, apri l'app Inventory Visibility e seleziona **Configurazione \> Allocazione**.

Ad esempio, se utilizzi quattro nomi di gruppo e li imposti su \[`channel`, `customerGroup`, `region`, `orderType`\], questi nomi saranno validi per le richieste relative all'allocazione quando chiami l'API di aggiornamento della configurazione.

### <a name="allocation-using-tips"></a>Allocazione usando i suggerimenti

- Per ogni prodotto, la funzione di allocazione deve essere utilizzata nello stesso *livello di dimensione* in base alla gerarchia dell'indice del prodotto impostata nella [configurazione della gerarchia dell'indice di prodotto](inventory-visibility-configuration.md#index-configuration).. Ad esempio, supponiamo che la tua gerarchia di indici sia \[`Site`, `Location`, `Color`, `Size`\]. Se assegni una certa quantità per un prodotto nel livello di dimensione \[`Site`, `Location`, `Color`\], la prossima volta che vuoi allocare questo prodotto, è necessario allocare allo stesso livello, \[`Site`, `Location`, `Color`\]. Se usi il livello \[`Site`, `Location`, `Color`, `Size`\] o \[`Site`, `Location`\], i dati saranno incoerenti.
- La modifica del nome del gruppo di allocazione non influirà sui dati salvati nel servizio.
- L'allocazione deve avvenire dopo che il prodotto ha la quantità positiva disponibile.
- Per allocare prodotti dal gruppo di *livello di allocazione* elevato in un sottogruppo, utilizza l'API `Reallocate`. Ad esempio, hai una gerarchia di gruppi di allocazione \[`channel`, `customerGroup`, `region`, `orderType`\], e vuoi allocare un prodotto dal gruppo di allocazione \[Online, VIP\] al sottogruppo di assegnazione \[Online, VIP, EU\], utilizza l'API `Reallocate` per spostare la quantità. Se usi l'API `Allocate` viene assegnata la quantità dal pool comune virtuale.

### <a name="using-the-allocation-api"></a><a name="using-allocation-api"></a>Utilizzo dell'API di allocazione

Attualmente sono aperte cinque API di allocazione:

- POST /api/environment/{environmentId}/allocation/allocate
- POST /api/environment/{environmentId}/allocation/unallocate
- POST /api/environment/{environmentId}/allocation/reallocate
- POST /api/environment/{environmentId}/allocation/consume
- POST /api/environment/{environmentId}/allocation/query

#### <a name="allocate"></a>Alloca

Chiama l'API `Allocate` per allocare un prodotto con dimensioni specifiche. Ecco lo schema per il corpo della richiesta.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Ad esempio, si desidera allocare una quantità di 10 per il prodotto *Bicicletta*, sito *1*, ubicazione *11*, colore *rosso*, canale *online*, Gruppo di clienti *VIP*, e are *Stati Uniti*. Per eseguire questa allocazione, è possibile effettuare una chiamata con il seguente contenuto del corpo.

```json
{
    "id": "???",
    "productId": "Bike",
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 10,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

La quantità deve essere sempre maggiore di 0 (zero).

#### <a name="unallocate"></a>Unallocate

Utilizza l'API `Unallocate` per annullare l'operazione `Allocate`. La quantità negativa non è consentita in un'operazione `Allocate`. Il corpo di `Unallocate` è identico al corpo di `Allocate`.

#### <a name="reallocate"></a>Reallocate

Utilizza l'API `Reallocate` per spostare una quantità allocata in un'altra combinazione di gruppi. Ecco lo schema per il corpo della richiesta.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "sourceGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "targetGroups": {
        "groupD": "string",
        "groupE": "string",
        "groupF": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Ad esempio, puoi spostare due biciclette che hanno le dimensioni \[sito=1, posizione=11, colore=rosso\] dal gruppo di assegnazione \[Online, VIP, Stati Uniti\] al gruppo di assegnazione \[Online, VIP, UE\] chiamando l'API `Reallocate` e fornendo il seguente corpo del testo.

```json
{
    "id": "???",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "EU"
    },
    "quantity": 2,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

#### <a name="consume"></a>Utilizzo

Utilizza l'API `Consume` per registrare la quantità di consumo rispetto all'allocazione. Ad esempio, potresti utilizzare questa API per spostare la quantità allocata su alcune misure reali. Ecco lo schema per il corpo della richiesta.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "physicalMeasures": {
        "datasource1": {
            "measure": "string" // Addition or Subtraction
        }
    }
}
```

Ad esempio, ci sono otto biciclette assegnate che hanno le dimensioni \[sito=1, posizione=11, colore=rosso\] per il gruppo di assegnazione \[Online, VIP, Stati Uniti\]. Viene utilizzata la seguente formula disponibile per l'allocazione:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

Le otto bici sono assegnate dalla misura `pos.inbound`.

Ora vengono vendute tre biciclette e vengono prelevate dal pool di allocazione. Per registrare questo movimento, puoi effettuare una chiamata con il seguente corpo della richiesta.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "pos": {
            "inbound": "Subtraction"
        }
    }
}
```

Dopo questa chiamata, la quantità assegnata per il prodotto verrà ridotta di 3. Inoltre, Inventory Visibility genererà un evento di modifica disponibile dove `pos.inbound` = *-3*. In alternativa, puoi conservare il valore `pos.inbound` così com'è e consumare solo la quantità allocata. Tuttavia, in questo caso, è necessario creare un'altra misura fisica per conservare le quantità consumate o utilizzare la misura predefinita `@iv.@consumed`.

In questa richiesta, tieni presente che la misura fisica utilizzata nel corpo della richiesta di consumo deve utilizzare il tipo di modificatore opposto (Addizione o Sottrazione), rispetto al tipo di modificatore utilizzato nella misura calcolata. Quindi in questo corpo di consumo, `iv.inbound` ha il valore `Subtraction`, non `Addition`.

L'origine dati `fno` non può essere utilizzata nel corpo di consumo poiché abbiamo sempre affermato che la visibilità dell'inventario non può modificare alcun dato per l'origine dati `fno`. Il flusso di dati è unidirezionale, il che significa che tutte le quantità cambiano per l'origine dati `fno` deve provenire dall'ambiente di Supply Chain Management.

#### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Consumare come prenotazione temporanea

L'API `Consume` può anche consumare la quantità allocata come prenotazione temporanea. In questo caso, l'operazione `Consume` ridurrà la quantità allocata e quindi eseguirà una prenotazione temporanea per tale quantità. Per utilizzare questo approccio, è necessario utilizzare anche la funzionalità [prenotazione temporanea](inventory-visibility-reservations.md) di Inventory Visibility.

Ad esempio, hai impostato un modificatore di prenotazione temporanea (misura) come `iv.softreserved`. La formula seguente viene utilizzata per la misura calcolata disponibile per la prenotazione:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved`

Per utilizzare questa configurazione con la funzione di allocazione, aggiungi `@iv.@allocated` a `iv.available_to_reserve` per produrre la seguente formula:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved` – `@iv.@allocated`

Quindi aggiorna `@iv.@available_to_allocate` allo stesso valore.

Se si vuole consumare una quantità pari a 3 e riservare direttamente tale quantità, è possibile effettuare una chiamata che abbia il seguente corpo della richiesta.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "iv": {
            "softreserved": "Addition"
        }
    }
}
```

In questa richiesta, nota che `iv.softreserved` ha il valore `Addition`, non `Subtraction`.

#### <a name="query"></a>Query

Utilizza l'API `Query` per recuperare le informazioni relative all'allocazione per alcuni prodotti. È possibile utilizzare i filtri delle dimensioni e dei gruppi di allocazione per limitare i risultati. Le dimensioni devono corrispondere esattamente a quella che vuoi recuperare, ad esempio, \[sito=1, ubicazione=11\] avrà risultati non correlati rispetto a \[sito=1, ubicazione=11, colore=rosso\].

```json
{
    "productId": "string",
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "groups": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
    },
}
```

Ad esempio, usa \[sito=1, ubicazione=11, colore=rosso\] e il campo gruppi vuoto per ottenere tutti i record di allocazione:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

Usa \[sito=1, ubicazione=11, colore=rosso\] e gruppi \[canale=Online, customerGroup=VIP, area=Stati Uniti\] per ottenere i record di allocazione per questo gruppo:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```
