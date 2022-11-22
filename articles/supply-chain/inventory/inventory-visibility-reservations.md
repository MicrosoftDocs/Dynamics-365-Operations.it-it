---
title: Prenotazioni di Inventory Visibility
description: Questo articolo descrive come impostare la funzione di prenotazione per creare prenotazioni, consumare prenotazioni, e/o sbloccare quantità di inventario specificate usando Visibilità dell'inventario.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0ae0589f8bac7ebf9b43cf0f3bc02680d324b29b
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762743"
---
# <a name="inventory-visibility-reservations"></a>Prenotazioni di Inventory Visibility

[!include [banner](../includes/banner.md)]

Questo articolo descrive un caso d'uso tipico per le prenotazioni temporanee e spiega come configurarle in Visibilità inventario. Include informazioni su come creare prenotazioni temporanee, compensarle in base al consumo fisico e regolare o annullare la prenotazione di quantità di scorte specificate.

## <a name="sample-use-case-for-soft-reservation"></a>Caso d'uso di esempio per la prenotazione temporanea

Le prenotazioni temporanee aiutano le organizzazioni a ottenere un'unica fonte di verità per l'inventario disponibile, in particolare durante il processo di evasione degli ordini. Questa funzionalità è utile per le organizzazioni in cui esistono le seguenti condizioni:

- L'organizzazione dispone di almeno due sistemi diversi che accettano direttamente gli ordini in uscita.
- L'organizzazione è molto rigorosa e desidera evitare la doppia prenotazione dell'inventario dei prodotti, che può verificarsi se più sistemi sono in grado di prenotare in eccesso l'ultimo pezzo di stock. Questa situazione viene evitata quando tutti i sistemi di ordine possono effettuare chiamate API di prenotazione soft istantanee a Inventory Visibility, che fornisce un'unica fonte di verità per la disponibilità dell'inventario.

[<img src="media/inventory-visibility-soft-reservation.png" alt="Inventory Visibility soft reservation." title="Prenotazioni temporanee di Visibilità inventario" width="720" />](media/inventory-visibility-soft-reservation.png)

L'illustrazione precedente mostra come funziona la prenotazione temporanea ed evidenzia le seguenti operazioni:

- Il tuo livello di inventario iniziale è sincronizzato con Inventory Visibilità inventario di Microsoft Dynamics 365 Supply Chain Management.
- Le prenotazioni temporanee vengono registrate da ciascuno dei tuoi canali o sistemi di ordine in Visibilità inventario. La visibilità dell'inventario convalida la disponibilità dell'inventario e tenta di effettuare una prenotazione temporanea. Se la prenotazione temporanea ha esito positivo, Visibilità inventario si aggiunge alla quantità prenotata temporanea, la sottrae dalla quantità disponibile per la prenotazione (AFR) e risponde con un ID prenotazione temporanea.
- In questo momento, la quantità di inventario fisico rimane la stessa.
- È quindi possibile sincronizzare gli ordini con prenotazione temporanea singoli o aggregati (righe d'ordine) in Supply Chain Management per effettuare prenotazioni definitive e rilasciarle al magazzino o aggiornare la quantità di inventario finale.
- Puoi impostare il sistema per [compensare le prenotazioni tempooranee](#offset-scm) quando l'inventario fisico viene aggiornato in Supply Chain Management.

Le prenotazioni temporanee vengono in genere create, consumate e cancellate utilizzando chiamate API al servizio Visibilità dell'inventario.

> [!NOTE]
> È possibile impostare opzionalmente Supply Chain Management (e altri sistemi di terze parti) per compensare automaticamente la quantità che è stata riservata utilizzando la Visibilità dell'inventario. La quantità compensata è cancellata dalle registrazioni di prenotazione in Visibilità dell'inventario.
>
> Per impostazione predefinita, la funzione di compensazione viene attivata automaticamente quando si abilita la funzione di prenotazione temporanea.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Attivare e configurare la funzionalità di prenotazione

Per attivare la funzione di prenotazione, seguite questi passi.

1. Accedi a Power Apps, e apri **Visibilità inventario**.
1. Aprire la pagina di **configurazione** .
1. Nella scheda **Gestione funzioni** , attiva la funzione *OnHandReservation* .
1. Accedi all'ambiente Supply Chain Management.
1. Andare all'area di lavoro **[Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e abilitare la funzionalità *Integrazione di Visibilità inventario con offset della prenotazione* (richiede la versione 10.0.22 o successiva).
1. Andare a **Gestione inventario \> Impostazione \> Parametri di integrazione di Visibilità inventario**, aprire la scheda **Offset prenotazione** ed effettuare le seguenti impostazioni:

    - **Abilita offset prenotazione** - Impostare su *Sì* per abilitare questa funzionalità.
    - **Modificatore offset prenotazione** - Selezionare lo stato della transazione di inventario che eseguirà l'offset delle prenotazioni effettuato su Visibilità inventario. Questa impostazione determina la fase di elaborazione dell'ordine che attiva gli offset. La fase è tracciata dallo stato di transazione dell'inventario dell'ordine. Selezionare uno dei seguenti valori:

        - *Su ordine*: gli ordini con stato *Su ordine* invieranno una richiesta di offset quando vengono creati. La quantità su cui è stato eseguito l'offset sarà la quantità dell'ordine creato (riga).
        - *Prenotazioni*: gli ordini con stato *Prenotazioni* invieranno una richiesta di ofset quando sono prenotati per ordine o prenotati fisicamente. Quando esegui l'offset nello stato *Prenotazioni*, l'ordine invierà una richiesta di offset a qualsiasi nuovo stato di inventario più vicino al prelievo prenotato (ad esempio, prelievo, documento di trasporto registrato o fatturato). Questo comportamento si verifica anche se si ignora la prenotazione in Supply Chain Management e si passa a un altro stato dell'inventario (ad esempio, se si passa dal rilascio al magazzino per prelevare e imballare). La richiesta verrà attivata una sola volta. Se è stata attivata al momento del prelievo, non duplicherà l'offset quando viene registrato un documento di trasporto. La quantità su cui è stato eseguito l'offset sarà pari alla quantità dello stato della transazione di inventario quando l'offset è stato attivato (in altre parole *Ordinato prenotato*/*Prenotazione fisica* o uno stato successivo nella riga dell'ordine corrispondente).

1. Accedi nuovamente all'app Visibilità inventario, vai alla pagina **Configurazione**, e poi, nella scheda **Prenotazione temporanea**, rivedi la gerarchia di prenotazione termporanea predefinita. Aggiungi nuove dimensioni alla gerarchia come richiesto.
1. Nella sezione **Impostare una mappatura delle prenotazioni temporanee**, visualizza le impostazioni predefinite. Per impostazione predefinita, le quantità di inventario con prenotazione temporanea verranno registrate rispetto alla misura fisica `softreservephysical` dell'origine dati `iv`. La misura calcolata *Disponibile per prenotazione* viene mappata a `availabletoreserve`. Se vuoi aggiornare la misura calcolata `availabletoreserve`, vai alla pagina **Configurazione**, e poi, nella scheda **Misura calcolata**, espandi e modifica la misura calcolata.

Per ulteriori informazioni, vedere [Configurare Visibilità inventario](inventory-visibility-configuration.md).

> [!NOTE]
> La gerarchia delle prenotazioni descrive la sequenza delle dimensioni che devono essere specificate quando si fanno le prenotazioni. Funziona nello stesso modo in cui la gerarchia dell'indice funziona per le query sulla disponibilità, ma viene utilizzata in modo indipendente in modo che gli utenti possano specificare i dettagli della dimensione per effettuare prenotazioni più precise.
>
> La gerarchia delle prenotazioni preliminari dovrebbe contenere `SiteId` e `LocationId` come componenti perché costruiscono la configurazione della partizione di Visibilità inventario.

Per ulteriori informazioni su come configurare le prenotazioni, vedere [Configurazione della prenotazione](inventory-visibility-configuration.md#reservation-configuration).

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Utilizzare la funzione di prenotazione in Visibilità dell'inventario

Quando chiamate l'API di prenotazione, il sistema segna la prenotazione delle merci e delle quantità specificate.

Ecco uno scenario di esempio e un corpo di query API di esempio. La società Contoso vende il prodotto D0002 (Cabinet) dal proprio sito Web di e-commerce. Un cliente invia un ordine di vendita per un armadietto rosso tramite il sito Web. Contoso decide di evadere questo ordine utilizzando le seguenti dimensioni:

- ID organizzazione = usmf
- Sito = 1
- Magazzino = 11
- Prodotto = D0002
- Colore = rosso
- Dimensioni = piccola

Contoso ha già configurato una connessione API a Visibilità inventario dal proprio sistema di e-commerce. Quando l'ordine viene ricevuto, il sistema attiva immediatamente una chiamata API per effettuare una prenotazione temporanea per l'armadietto in Visibilità inventario.

### <a name="create-soft-reservations-using-the-reservation-api"></a>Creare prenotazioni temporanee utilizzando l'API di prenotazione

Le prenotazioni sono fatte nel servizio di Visibilità dell'inventario inviando una richiesta POST all'URL del servizio, come `/api/environment/{environmentId}/onhand/reserve`.

Per una prenotazione, il corpo della richiesta deve contenere un ID dell'organizzazione, un ID del prodotto, quantità riservate e dimensioni.

Quando si chiama l'API di prenotazione, è possibile controllare la convalida della prenotazione specificando il parametro booleano `ifCheckAvailForReserv` nel corpo della richiesta. Un valore di `True` significa che è richiesta la convalida, mentre un valore di `False` significa che la convalida non è richiesta. Il valore predefinito è `True`.

Se si desidera annullare una prenotazione o annullare la prenotazione di quantità di inventario specificate, impostare la quantità su un valore negativo e impostare il parametro `ifCheckAvailForReserv` su `False` per saltare la convalida.

Di seguito è riportato un esempio del corpo della richiesta che fa riferimento all'ordine cliente nel contesto precedente.

```json
# Url

#Replace {endpoint} with your system endpoint.
    {endpoint}/api/environment/{environmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "Testrequest-0005",
    "organizationId": "usmf",
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "softreservphysical",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

Una richiesta di prenotazione temporanea andata a buon fine restituisce un *ID prenotazione temporanea* per ogni record di prenotazione. L'ID di prenotazione temporanea non è un identificatore univoco per un singolo record di prenotazione temporanea, ma una combinazione dell'ID prodotto e dei valori di dimensione associati alla richiesta di prenotazione temporanea. È possibile registrare l'ID di prenotazione temporanea nella riga dell'ordine quando si sincronizzano gli ordini prenotati con successo in Supply Chain Management o in un altro sistema ERP per l'offset.

### <a name="offset-soft-reservations-in-supply-chain-management"></a><a name="offset-scm"></a>Offset di prenotazioni temporanee in Supply Chain Management

È possibile eseguire l'offset di una quantità con prenotazione temporanea dopo che la quantità su un ordine è stata detratta fisicamente in Supply Chain Management o in un altro sistema ERP. Visibilità inventario offre l'integrazione dell'offset di prenotazione temporanea predefinita con Supply Chain Management.

Segui questi passaggi per eseguire l'offset di una prenotazione temporanea.

1. Accedere a Supply Chain Management.
1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Ricrea l'ordine cliente esterno e aggiungi una riga di vendita che utilizza esattamente gli stessi valori di ID prodotto, organizzazione, sito, magazzino e dimensioni.
1. Nella Scheda dettaglio **Righe ordine cliente**, seleziona la riga di vendita appena immessa, quindi, nella barra degli strumenti, seleziona **Inventario \> ID prenotazione**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Copia l'ID prenotazione temporanea nella risposta alla richiesta di prenotazione temporanea e incollalo nel campo **ID prenotazione**.
    - Lascia il campo **ID prenotazione** vuoto, ma seleziona la casella di controllo **Offset automatico del servizio di inventario**. Il sistema determinerà automaticamente il prodotto e le dimensioni del prodotto da compensare, in base all'ID articolo e ai valori delle dimensioni immessi nella riga selezionata.

1. Seleziona **OK**.
1. Quando la stessa riga di vendita è ancora selezionata, prenota fisicamente la quantità ordinata selezionando **Inventario \> Prenotazione** nella barra degli strumenti della Scheda dettaglio **Righe ordine cliente**.
1. Se hai precedentemente impostato il campo **Modificatore offset prenotazione** su *Prenotato*, l'offset verrà attivato quando lo stato della riga dell'ordine è di *Prenotazione fisica* o *Prenotazione ordinata*. Un processo batch viene eseguito una volta al minuto per sincronizzare le richieste di offset da Supply Chain Management a Visibilità inventario.

> [!NOTE]
> Per gli stati di transazione che includono un modificatore di compensazione della riserva specificato, l'aggiornamento della transazione compenserà il record di prenotazione corrispondente quando tutte le seguenti condizioni sono soddisfatte:
>
> - L'ID della prenotazione sulla transazione d'inventario corrisponde all'ID della prenotazione del record della prenotazione in Visibilità inventario.
> - Le dimensioni della transazione d'inventario corrispondono alle dimensioni del record di prenotazione in Visibilità inventario.
> - I cambiamenti nello stato della transazione d'inventario innescano compensazioni per le prenotazioni quando lo stato della transazione d'inventario riflette il fatto che un processo dell'ordine è stato completato o saltato.

Le quantità di offset seguono le quantità d'inventario specificate nelle relative transazioni d'inventario. Un offset avrà effetto solo se la quantità riservata rimane in Visibilità inventario.

### <a name="cancel-or-revert-a-soft-reservation"></a>Annullare o annullare una prenotazione temporanea

Se una riga dell'ordine originale viene annullata o eliminata ed è necessario annullare la prenotazione temporanea corrispondente, registra una quantità negativa con le stesse identiche informazioni nel corpo della query API.
