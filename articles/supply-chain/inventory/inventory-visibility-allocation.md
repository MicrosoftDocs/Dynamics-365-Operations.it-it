---
title: Allocazione inventario di Inventory Visibility
description: Questo articolo spiega come impostare e utilizzare la funzione di allocazione dell'inventario, che ti consente di mettere da parte un inventario dedicato per assicurarti di soddisfare i tuoi canali o clienti più redditizi.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 449ca0616405ba589b92fba1ef078a4350d1e3b1
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762674"
---
# <a name="inventory-visibility-inventory-allocation"></a>Allocazione inventario di Inventory Visibility

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Background aziendale e scopo

Le organizzazioni spesso devono preallocare le scorte disponibili ai loro canali di vendita, gruppi di clienti, regioni ed eventi promozionali più importanti per garantire che lo stock preallocato sia protetto da qualsiasi altro utilizzo e possa essere consumato solo tramite transazioni di vendita rilevanti per l'allocazione. L'allocazione delle scorte in Visibilità inventario è un componente del processo di pianificazione operativa delle vendite e viene eseguita prima che si verifichino le attività di vendita effettive o venga creato un ordine cliente.

Ad esempio, un'azienda denominata Contoso produce una bicicletta popolare. Sfortunatamente, poiché una recente interruzione della catena di approvvigionamento ha interessato tutte le scorte in transito di quella bicicletta, Contoso dispone solo di scorte disponibili limitate e deve sfruttarle al meglio. Contoso effettua vendite sia online che in negozio. In ogni canale di vendita, l'azienda ha alcuni importanti partner aziendali (marketplace e grandi rivenditori) che richiedono che una parte specifica dell'inventario disponibile della bicicletta venga salvata per loro. Pertanto, l'azienda di biciclette deve essere in grado di bilanciare la distribuzione delle azioni attraverso i canali e anche di gestire le aspettative dei suoi partner VIP. Il modo migliore per raggiungere entrambi gli obiettivi è utilizzare l'allocazione dell'inventario, in modo che ogni canale e rivenditore possano ricevere quantità specifiche allocate che possono essere vendute ai consumatori in un secondo momento.

L'allocazione dell'inventario ha due scopi aziendali fondamentali:

- **Protezione dell'inventario (ringfencing)** – Le organizzazioni desiderano allocare in anticipo scorte limitate a canali prioritari, aree, clienti VIP e società sussidiarie. La funzione di allocazione Inventory Visibility mira a proteggere l'inventario allocato, in modo che altre allocazioni, prenotazioni o altre richieste di vendita non influiscano sull'inventario allocato in precedenza.
- **Controllo delle vendite eccessive** – La funzione di allocazione della visibilità dell'inventario mira a limitare le quantità assegnate in precedenza, in modo che la parte ricevente (ad esempio un canale o un gruppo di clienti) non le consumi eccessivamente quando l'effettiva transazione di vendita si basa su una prenotazione temporanea che entra in vigore.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Definizione dell'allocazione nel servizio di visibilità inventario

### <a name="allocation-virtual-pool"></a>Pool virtuale di allocazione

Sebbene la funzione di allocazione in Visibilità inventario non metta da parte le quantità di inventario fisico, fa riferimento alla quantità di inventario fisico disponibile per definirne la quantità di pool virtuale iniziale *disponibile per l'assegnazione*. L'allocazione dell'inventario in Inventory Visibility è un'allocazione temporanea. Viene eseguita prima che si verifichino le transazioni di vendita effettive e non dipende dagli ordini cliente. Ad esempio, puoi allocare le scorte ai tuoi canali di vendita più importanti o ai grandi rivenditori aziendali prima che i clienti finali visitino il canale di vendita o il negozio al dettaglio per acquistare.

### <a name="difference-between-inventory-allocation-and-soft-reservation"></a>Differenza tra allocazione dell'inventario e prenotazione temporanea

Le [prenotazioni temporanee](inventory-visibility-reservations.md) sono in genere collegate a transazioni di vendita effettive (righe ordine cliente). Sia l'allocazione che la prenotazione temporanea possono essere utilizzate indipendentemente, ma se si desidera utilizzarle insieme, la prenotazione temporanea deve essere eseguita dopo l'allocazione. È consigliabile eseguire prima l'allocazione delle scorte e quindi la prenotazione temporanea rispetto alle quantità allocate per ottenere il consumo in tempo reale a fronte dell'allocazione. Per ulteriori informazioni, vedi [Consumare come prenotazione temporanea](#consume-to-soft-reserved).

La funzione di allocazione dell'inventario consente ai pianificatori delle vendite o ai responsabili di account chiave di gestire e allocare in anticipo le scorte importanti tra gruppi di allocazione (come canali, aree e gruppi di clienti). Supporta anche il monitoraggio, la rettifica e l'analisi in tempo reale del consumo rispetto alle quantità assegnate, in modo che il rifornimento o la riallocazione possano essere eseguiti in tempo. Questa capacità di avere visibilità in tempo reale sull'allocazione, sul consumo e sul saldo dell'allocazione è particolarmente importante in occasione di vendite rapide o eventi promozionali.

## <a name="terminology"></a>Terminologia

I seguenti termini e concetti sono utili nelle discussioni sull'allocazione dell'inventario:

- **Gruppo di allocazione** – Il gruppo proprietario dell'allocazione, ad esempio un canale di vendita, un gruppo di clienti o un tipo di ordine.
- **Valore del gruppo di allocazione** – Il valore di ciascun gruppo di allocazione. Per esempio, *web* o *negozio* potrebbe essere il valore del gruppo di allocazione del canale di vendita, mentre *VIP* o *normale* potrebbe essere il valore del gruppo di allocazione del cliente.
- **Gerarchia di allocazione** – Un mezzo per combinare i gruppi di allocazione in modo gerarchico. Ad esempio, puoi definire *canale* come livello gerarchico 1, *area* come livello 2, e *gruppo di clienti* come livello 3. Durante l'allocazione delle scorte, è necessario seguire la sequenza della gerarchia di allocazione quando si specifica il valore del gruppo di allocazione. Ad esempio, potresti assegnare 200 biciclette rosse al canale *Web*, all'area *Londra* e al gruppo di clienti *VIP*.
- **Disponibile per l'allocazione** - Il *pool comune virtuale* che indica la quantità disponibile per un'ulteriore allocazione. È una misura calcolata che puoi definire liberamente utilizzando la tua formula. Se stai utilizzando anche la funzione di prenotazione temporanea, ti consigliamo di utilizzare la stessa formula per calcolare la disponibilità per l'allocazione e la disponibilità per la prenotazione.
- **Allocato** – Una misura fisica che mostra la quota allocata che può essere utilizzata dai gruppi di allocazione. Viene detratto contestualmente all'aggiunta della quantità consumata.
- **Consumato** – Una misura fisica che indica le quantità che sono state consumate rispetto alla quantità allocata originale. Man mano che i numeri vengono aggiunti a questa misura fisica, la misura fisica allocata viene automaticamente ridotta.

L'illustrazione seguente mostra il flusso di lavoro aziendale per l'allocazione dell'inventario.

![Flusso di lavoro aziendale di allocazione di Inventory Visibility.](media/inventory-visibility-allocation-flow.png "Flusso di lavoro aziendale di allocazione di Inventory Visibility.")

La figura seguente mostra la gerarchia di allocazione e i gruppi di allocazione. Il *pool comune virtuale* mostrato qui è la quantità disponibile per l'allocazione.

[<img src="media/inventory-visibility-allocation-hierarchy.png" alt="Inventory Visibility allocation hierarchy." title="Gerarchia di allocazione inventario di Visibilità inventario" width="720" />](media/inventory-visibility-allocation-hierarchy.png)

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

Il processo di configurazione della funzione di allocazione prevede tre passaggi:

- Abilita la funzionalità nell'app Visibilità inventario passando a **Configurazione \> Gestione funzionalità e impostazioni \> Allocazione**.
- Imposta [l'origine dati](inventory-visibility-configuration.md#data-source-configuration) e [le misure](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Imposta il nome e la gerarchia del gruppo di allocazione.

### <a name="predefined-data-source"></a>Origine dati predefinita

Quando si abilita la funzione di allocazione e si chiama l'API di aggiornamento della configurazione, la visibilità dell'inventario crea un'origine dati predefinita e diverse misure iniziali.

L'origine dati è denominata `@iv`. Include una serie di misure fisiche predefinite. Puoi visualizzarle dall'app Visibilità inventario passando a **Configurazione \> Origine dati**. Dovresti vedere **Origine dati - @IV**. Espandi l'origine dati `@iv` per visualizzare l'elenco delle misure fisiche iniziali:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Seleziona la scheda **Misure calcolate** per visualizzare la misura calcolata iniziale, denominata `@iv.@available_to_allocate`:

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Aggiungere altre misure fisiche alla misura calcolata disponibile per l'allocazione

Per utilizzare l'allocazione, è necessario configurare correttamente la formula per la misura calcolata disponibile per l'allocazione (`@iv.@available_to_allocate`). Ad esempio, hai l'origine dati `fno` e la misura `onordered`, l'origine dati `pos` e la misura `inbound` e vuoi fare l'allocazione delle scorte per la somma di `fno.onordered` e `pos.inbound`. In questo caso, `@iv.@available_to_allocate` deve contenere `pos.inbound` e `fno.onordered` nella formula. Ecco un esempio:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

> [!NOTE]
> L'origine dati `@iv` è un'origine dati predefinita e le misure fisiche definite in `@iv` con prefisso `@` sono misure predefinite. Queste misure sono una configurazione predefinita per la funzionalità di allocazione, quindi non modificarle o eliminarle altrimenti è probabile che si verifichino errori imprevisti durante l'utilizzo della funzionalità di allocazione.
>
> Puoi aggiungere nuove misure fisiche alla misura calcolata predefinita `@iv.@available_to_allocate`, ma non devi cambiarne il nome.

### <a name="manage-allocation-groups"></a>Gestire i gruppi di allocazione

È possibile impostare un massimo di otto nomi di gruppi di assegnazione. I gruppi hanno una gerarchia. Segui questi passaggi per visualizzare e aggiornare i gruppi di allocazione.

1. Accedi al tuo ambiente Power Apps e apri **Visibilità inventario**.
1. Apri la pagina **Configurazione**, e poi, nella scheda **Allocazione**, seleziona **Modifica configurazione**. Per impostazione predefinita, esiste una gerarchia di allocazione che ha quattro livelli: `Channel` (livello superiore), `customerGroup` (secondo livello), `Region` (terzo livello) e `OrderType` (quarto livello).
1. È possibile rimuovere un gruppo di allocazione esistente selezionando la **X** accanto a esso. È inoltre possibile aggiungere nuovi gruppi di allocazione alla gerarchia immettendo il nome di ogni nuovo gruppo direttamente nel campo.

    > [!IMPORTANT]
    > Presta attenzione quando elimino o modifichi il mapping della gerarchia di allocazione. Per istruzioni, vedi [Suggerimenti per l'utilizzo dell'allocazione](#allocation-tips).

1. Al termine della configurazione del gruppo di allocazione e delle impostazioni della gerarchia, salva le modifiche e quindi seleziona **Aggiorna configurazione** in alto a destra. I valori dei gruppi di allocazione configurati verranno aggiornati quando crei un'allocazione utilizzando l'interfaccia utente o API POST (/api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate). I dettagli su entrambi gli approcci vengono forniti più avanti in questo articolo.

Se utilizzi quattro nomi di gruppo e li imposti su \[`channel`, `customerGroup`, `region`, `orderType`\], questi nomi saranno validi per le richieste relative all'allocazione quando chiami l'API di aggiornamento della configurazione.

### <a name="tips-for-using-allocation"></a><a name="allocation-tips"></a>Suggerimento per l'utilizzo dell'allocazione

- Per ogni prodotto, la funzione di allocazione deve essere utilizzata nello stesso *livello di dimensione* in base alla gerarchia dell'indice del prodotto impostata nella [configurazione della gerarchia dell'indice di prodotto](inventory-visibility-configuration.md#index-configuration).. Ad esempio, supponiamo che la tua gerarchia di indici sia \[`Site`, `Location`, `Color`, `Size`\]. Se assegni una certa quantità per un prodotto nel livello di dimensione \[`Site`, `Location`, `Color`\], la prossima volta che vuoi allocare questo prodotto, è necessario allocare allo stesso livello, \[`Site`, `Location`, `Color`\]. Se usi il livello \[`Site`, `Location`, `Color`, `Size`\] o \[`Site`, `Location`\], i dati saranno incoerenti.
- **Modifica dei gruppi di allocazione e della gerarchia:** se i dati di allocazione esistono già nel sistema, l'eliminazione dei gruppi di allocazione esistenti o uno spostamento nella gerarchia del gruppo di allocazione danneggerà il mapping esistente tra i gruppi di allocazione. Pertanto, assicurati di ripulire manualmente tutti i vecchi dati prima di aggiornare la nuova configurazione. Tuttavia, poiché l'aggiunta di nuovi gruppi di allocazione alla gerarchia più bassa non influisce sui mapping esistenti, non sarà necessario pulire i dati.
- L'allocazione avrà successo solo se il prodotto ha una quantità `available_to_allocate` positiva.
- Per allocare prodotti dal gruppo di *livello di allocazione* elevato in un sottogruppo, utilizza l'API `Reallocate`. Ad esempio, hai una gerarchia di gruppi di allocazione \[`channel`, `customerGroup`, `region`, `orderType`\], e vuoi allocare un prodotto dal gruppo di allocazione \[Online, VIP\] al sottogruppo di assegnazione \[Online, VIP, EU\], utilizza l'API `Reallocate` per spostare la quantità. Se usi l'API `Allocate` viene assegnata la quantità dal pool comune virtuale.
- Per visualizzare la disponibilità complessiva del prodotto (il pool comune), utilizza l'API delle [scorte disponibili](inventory-visibility-api.md#query-on-hand) per richiedere la quantità di inventario che è *disponibile per l'allocazione*. È quindi possibile prendere decisioni di allocazione in base a queste informazioni.

## <a name="use-the-allocation-api"></a><a name="using-allocation-api"></a>Utilizzare l'API di allocazione

Attualmente sono aperte cinque API di allocazione:

- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate** – Questa API viene utilizzata per creare l'allocazione iniziale.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/unallocate** – Questa API viene utilizzata per ripristinare o rimuovere le quantità allocate.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/reallocate** – Questa API viene utilizzata per spostare la quantità allocata da un'allocazione esistente ad altri gruppi di allocazione.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/consume** – Questa API viene utilizzata per detrarre la quantità allocata.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/query** – Questa API viene utilizzata per controllare i record di allocazione esistenti rispetto ai gruppi di allocazione e alla gerarchia.

### <a name="allocate"></a>Alloca

Chiama l'API `Allocate` per allocare un prodotto con dimensioni specifiche. Ecco lo schema per il corpo della richiesta.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test101",
    "productId": "Bike",
    "groups": {
        "channel": "Web",
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

### <a name="unallocate"></a>Unallocate

Utilizza l'API `Unallocate` per annullare l'operazione `Allocate`. La quantità negativa non è consentita in un'operazione `Allocate`. Il corpo di `Unallocate` è identico al corpo di `Allocate`.

### <a name="reallocate"></a>Reallocate

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
    "groups": {
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
    "id": "test102",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
    "groups": {
        "channel": "Web",
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

### <a name="consume"></a>Utilizzo

Utilizza l'API `Consume` per registrare la quantità di consumo rispetto all'allocazione. Ad esempio, potresti utilizzare questa API per spostare la quantità allocata su alcune misure reali. Ecco lo schema per il corpo della richiesta.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test103",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Web",
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

### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Consumare come prenotazione temporanea

L'API `Consume` può anche consumare la quantità allocata come prenotazione temporanea. In questo caso, l'operazione `Consume` ridurrà la quantità allocata e quindi eseguirà una prenotazione temporanea per tale quantità. Per utilizzare questo approccio, è necessario utilizzare anche la funzionalità [prenotazione temporanea](inventory-visibility-reservations.md) di Inventory Visibility.

Ad esempio, hai impostato una misura fisica di prenotazione temporanea come `iv.softreserved`. La formula seguente viene utilizzata per la misura calcolata disponibile per la prenotazione:

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
    "groups": {
        "channel": "Web",
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

### <a name="query"></a>Query

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
        "channel": "Web",
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
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

## <a name="use-the-allocation-user-interface"></a>Utilizzare l'interfaccia utente di allocazione

Puoi gestire manualmente le allocazioni tramite l'interfaccia utente aprendo l'app Visibilità inventario e passando a **Visibilità operativa \> Allocazione**. Da lì, puoi eseguire una qualsiasi delle azioni descritte nelle seguenti sottosezioni.

### <a name="create-an-allocation"></a>Creare un'allocazione

Segui questi passaggi per creare un'allocazione dalla pagina **Allocazione** dell'app Visibilità inventario.

1. Seleziona **Alloca**.
1. Imposta i valori dei campi di base, delle dimensioni e dei gruppi di allocazione target. (Quando si seleziona l'origine dati di raccolta nella sezione **Dimensioni**, utilizza prima l'elenco a discesa per specificare le dimensioni (ad esempio, `siteId`). Quindi immetti i valori delle dimensioni nei campi visualizzati.)
1. Seleziona **Invia**.

### <a name="consume-an-allocation"></a>Utilizzare un'allocazione

Seleziona **Utilizza** per utilizzare un'allocazione. Per assicurarti di utilizzare all'interno del gruppo e della gerarchia di allocazione corretti, inserisci gli stessi set di dettagli relativi all'organizzazione e alle dimensioni che hai inserito quando hai creato l'allocazione.

### <a name="reallocate-an-allocation"></a>Riallocare un'allocazione

Seleziona **Rialloca** per spostare la quantità allocata esistente da un insieme di gruppi di allocazione a un altro.

### <a name="query-existing-allocations"></a>Query sulle allocazioni esistenti

Seleziona **Query** e quindi immetti i valori del prodotto, dell'organizzazione, della dimensione e del gruppo di allocazione per ottenere i risultati della query delle allocazioni esistenti.
