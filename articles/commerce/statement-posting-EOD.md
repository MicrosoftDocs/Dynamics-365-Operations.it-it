---
title: Miglioramenti alla funzionalità di registrazione del rendiconto
description: Questo articolo descrive i miglioramenti apportati alla funzionalità di registrazione dei rendiconti.
author: analpert
ms.date: 05/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2018-04-30
ms.openlocfilehash: a7f25a7cc1e214b5c08013055126728b2ad10f3f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886908"
---
# <a name="improvements-to-statement-posting-functionality"></a>Miglioramenti alla funzionalità di registrazione del rendiconto

[!include [banner](includes/banner.md)]

Questo articolo descrive il primo set di miglioramenti apportati alla funzionalità di registrazione dei rendiconti. Questi miglioramenti sono disponibili in Microsoft Dynamics 365 for Finance and Operations 7.3.2.

## <a name="activation"></a>Attivazione

Per impostazione predefinita, durante la distribuzione di Finanza e operazioni 7.3.2, il programma è configurato per l'utilizzo della funzionalità di registrazione dei rendiconti legacy. Per attivare la funzionalità di registrazione dei rendiconti migliorata, è necessario attivare la chiave di configurazione relativa.

- Accedere a **Amministrazione sistema** \> **Impostazione** \> **Configurazione licenza**, quindi nel nodo **Retail e Commerce**, deselezionare la casella di controllo **Rendiconti (legacy)** e selezionare la casella di controllo **Rendiconti**.

Quando la nuova chiave di configurazione **Rendiconti** è attivata, è disponibile una nuova voce di menu denominata **Rendiconti**. Questa voce di menu consente di creare manualmente, calcolare e registrare rendiconti. Tutti i rendiconti che causano un errore durante l'utilizzo del processo di registrazione batch saranno disponibili anche mediante questa voce di menu. (Quando la chiave di configurazione **Rendiconti (legacy)** viene attivata, la voce di menu è denominata **Rendiconti aperti**).

Commerce include le seguenti convalide correlate a queste chiavi di configurazione:

- Le chiavi di configurazione non possono essere attivate contemporaneamente.
- Le stesse chiavi di configurazione devono essere utilizzate per tutte le operazioni eseguite per un determinato rendiconto durante il relativo ciclo di vita (Crea, Calcola, Cancella, Registra e così via). Ad esempio, non è possibile creare e calcolare un rendiconto quando la chiave di configurazione **Rendiconti (legacy)** è attivata e quindi cercare di registrare lo stesso rendiconto mentre la chiave di configurazione **Rendiconti** è attivata .

> [!NOTE]
> Si consiglia di utilizzare la chiave di configurazione **Rendiconti** per la funzionalità di registrazione di rendiconti migliorata, a meno che non si abbiano ragioni valide di utilizzare la chiave di configurazione **Rendiconti (legacy)**. Microsoft continuerà a investire nella nuova funzionalità di registrazione di rendiconti migliorata ed è importante passare a questa funzionalità il prima possibile. La funzionalità di registrazione di rendiconti legacy è deprecata a partire dalla versione 8.0.

## <a name="setup"></a>Impostazione

Come parte dei miglioramenti alla funzionalità di registrazione dei rendiconti, tre nuovi parametri sono stati introdotti nella Scheda dettaglio **Rendiconto** della scheda **Registrazione** nella pagina **Parametri di commercio**:

- **Disabilita cancellazione rendiconto** – Questa opzione è applicabile solo per la funzionalità di registrazione dei rendiconti legacy. Si consiglia di impostare questa opzione su **No** per impedire agli utenti di cancellare rendiconti semi-registrati. Se si cancellano i rendiconti semi-registrati, i dati vengono danneggiati. Questa opzione dovrebbe essere impostata su **Sì** solo in circostanze eccezionali.
- **Prenota scorte durante il calcolo** – Si consiglia di utilizzare il processo batch **Registra magazzino** per la prenotazione delle scorte e di impostare questa opzione su **No**. Quando questa opzione è impostata su **No**, la funzionalità di registrazione dei rendiconti migliorata non tenta di creare voci di prenotazione scorte al momento del calcolo (se le voci erano già state create mediante il processo batch **Registra magazzino**). La funzionalità crea invece voci di prenotazione scorte solo al momento della registrazione. Questa implementazione era una scelta di progettazione ed era basata sul fatto che l'intervallo di tempo tra il processo di calcolo e il processo di registrazione è in genere ridotto. Tuttavia, se si desidera prenotare le scorte al momento del calcolo, è possibile impostare questa opzione su **Sì**.

    La funzionalità di registrazione dei rendiconti legacy prenota sempre le scorte durante il processo di calcolo dei rendiconti (se la prenotazione non era già stata effettuata mediante il processo batch **Registra magazzino**), indipendentemente dall'impostazione di questa opzione.

- **Disabilita conteggio richiesto** – Quando questa opzione è impostata su **Sì**, il processo di registrazione per un rendiconto continua, anche se la differenza tra l'importo conteggiato e l'importo della transazione nel rendiconto non rientra nella soglia definita nella Scheda dettaglio **Rendiconto** per punti vendita.

> [!NOTE]
> A partire dalla versione Commerce 10.0.14, quando la funzionalità **Rendiconti di vendita al dettaglio (inserimento continuo)** è abilitata, il processo batch **Registra magazzino** non è più applicabile e non può essere eseguito.

## <a name="processing"></a>Elaborazione

I rendiconti possono essere calcolati e registrati in batch utilizzando le voci di menu **Calcola rendiconti in batch** e **Registra rendiconti in batch**. In alternativa, i rendiconti possono essere calcolati e registrati manualmente utilizzando la voce di menu **Rendiconti** fornita dalla funzionalità di registrazione dei rendiconti migliorata.

Il processo e i passaggi per il calcolo e la registrazione dei rendiconti in un batch sono uguali a quelli della funzionalità di registrazione dei rendiconti legacy. Tuttavia, miglioramenti significativi sono stati apportati nell'elaborazione backend core dei rendiconti. Questi miglioramenti rendono il processo più resiliente e forniscono una migliore visibilità sugli stati e sulle informazioni relative agli errori. Di conseguenza, gli utenti possono eliminare la causa principale degli errori e quindi continuare il processo di registrazione senza il rischio di danneggiare i dati e la necessità di dover apportare le correzioni.

Nelle sezioni seguenti vengono descritti alcuni dei principali miglioramenti alla funzionalità di registrazione dei rendiconti nell'interfaccia utente per i rendiconti e i rendiconti registrati.

### <a name="status-details"></a>Dettagli stato

Un nuovo modello di stato è stato introdotto nella routine di registrazione dei rendiconti attraverso i processi di calcolo e di registrazione.

Nella tabella seguente vengono descritti i vari stati e il relativo ordine durante il processo di calcolo.

| Ordine stato | Stato/regione      | Descrizione |
|-------------|------------|-------------|
| 1           | Avviata    | Il rendiconto è stato creato ed è pronto per essere calcolato. |
| 2           | Contrassegnato     | Le transazioni nell'ambito di un rendiconto vengono identificate in base ai parametri del rendiconto e vengono contrassegnate con l'ID del rendiconto. |
| 3           | Calcolato | Le righe del rendiconto vengono calcolate e visualizzate. |

Nella tabella seguente vengono descritti i vari stati e il relativo ordine durante il processo di registrazione.

| Ordine stato | Stato/regione                   | Descrizione |
|-------------|-------------------------|-------------|
| 1           | Verificato                 | Vengono effettuate molteplici convalide correlate ai parametri (ad esempio l'addebito di smaltimento) nonché al rendiconto e alle righe del rendiconto (ad esempio la differenza tra l'importo conteggiato e l'importo della transazione). |
| 2           | Aggregato              | Le transazioni di vendita per i clienti con e senza nome vengono aggregate in base alla configurazione. Ogni transazione aggregata viene convertita in un ordine cliente. |
| 3           | Ordine cliente creato  | In base alla transazione aggregata, gli ordini cliente vengono creati nel sistema. |
| 4           | Ordine cliente fatturato | Gli ordini cliente sono fatturati. |
| 5           | Sconti registrati        | Giornali di registrazione sconti periodici sono registrati in base alla configurazione. |
| 6           | Ricavi/spese registrati   | Le transazioni ricavi/spese sono registrate come giustificativi. |
| 7           | Giustificativi collegati         | I giornali di registrazione vengono creati e collegati alla fattura corrispondente. |
| 8           | Pagamenti registrati         | I giornali di registrazione vengono registrati. |
| 9           | Gift card registrate       | Le transazioni gift card sono registrate come giustificativi. |
| 10          | Contabilizzato                  | Il rendiconto viene contrassegnato come registrato. |

Ogni stato nelle tabelle precedenti è indipendente in natura e una dipendenza gerarchica viene generata tra gli stati. Questa dipendenza va dall'alto in basso. Se nel sistema si verificano degli errori durante l'elaborazione di uno stato, viene ripristinato lo stato precedente del rendiconto. Qualsiasi tentativo successivo del processo riprende dal punto in cui si è verificato l'errore. Questo approccio presenta i seguenti vantaggi:

- L'utente ha una visibilità completa sullo stato durante il quale si è verificato l'errore.
- I dati non vengono danneggiati. Ad esempio, nella funzionalità di registrazione dei rendiconti legacy c'erano delle istanze in cui alcuni ordini cliente venivano fatturati mentre altri erano lasciati aperti. Erano presenti anche delle istanze in cui alcuni giornali di registrazione pagamenti non avevano una fattura corrispondente da liquidare, in quanto la registrazione della fattura comportava un errore.
- Gli utenti possono visualizzare lo stato corrente di un rendiconto utilizzando il pulsante **Dettagli stato** nel gruppo **Dettagli esecuzione** del rendiconto. La pagina dei dettagli dello stato ha tre aree:

    - La prima mostra lo stato corrente del rendiconto, insieme al codice di errore e a un messaggio di errore dettagliato, se si è verificato un errore.
    - La seconda area visualizza i vari stati del processo di calcolo. Sono segnalati gli stati eseguiti correttamente, quelli che non sono stati eseguiti a causa di errori e quelli non ancora eseguiti.
    - La terza area visualizza i vari stati del processo di registrazione. Sono segnalati gli stati eseguiti correttamente, quelli che non sono stati eseguiti a causa di errori e quelli non ancora eseguiti.

Inoltre, l'intestazione della seconda e della terza area mostra lo stato complessivo del processo pertinente.

### <a name="event-logs"></a>Registri eventi

Per un rendiconto vengono eseguite varie operazioni (ad esempio, Crea, Calcola, Cancella e Registra) e più istanze della stessa operazione possono essere chiamate durante il ciclo di vita del rendiconto. Ad esempio, dopo la creazione e il calcolo di un rendiconto, un utente può cancellare il rendiconto e ricalcolarlo. Il pulsante **Registri eventi** nel gruppo **Dettagli esecuzione** del rendiconto fornisce un audit trail completo delle varie operazioni chiamate su un rendiconto, insieme alle informazioni relative a quando tali operazioni sono state chiamate.

### <a name="aggregated-transactions"></a>Transazioni aggregate

Durante il processo di registrazione, le transazioni cash and carry vengono aggregate per cliente e prodotto. Pertanto, il numero di ordini cliente e righe creati è ridotto. Le transazioni aggregate sono archiviate nel sistema e utilizzate per creare ordini cliente. Ogni transazione aggregata crea un ordine cliente corrispondente nel sistema. 

Se un rendiconto non è completamente registrato, puoi visualizzare le transazioni aggregate nel rendiconto. Nel riquadro azioni, nella scheda **Rendiconto**, nel gruppo **Dettagli esecuzione** seleziona **Transazioni aggregate**.

![Pulsante Transazioni aggregate per un rendiconto non completamente registrato.](media/aggregated-transactions.png)

Per i rendiconto registrati puoi visualizzare le transazioni aggregate nella pagina **Rendiconti registrati**. Nel riquadro azioni, seleziona **Richieste di informazioni**, quindi seleziona **Transazioni aggregate**.

![Comando Transazioni aggregate per i rendiconti registrati.](media/aggregated-transactions-posted-statements.png)

La scheda dettaglio **Dettagli ordine cliente** di una transazione aggregata visualizza le seguenti informazioni:

- **ID record** – L'ID della transazione aggregata.
- **Numero rendiconto** – Il rendiconto a cui appartiene la transazione aggregata.
- **Data** – La data di creazione della transazione aggregata.
- **ID vendite** – Quando un ordine cliente viene creato a partire dalla transazione aggregata, l'ID dell'ordine cliente. Se questo campo è vuoto, l'ordine cliente corrispondente non è stato creato.
- **Numero di righe aggregate** – Il numero totale di righe per la transazione aggregata e l'ordine cliente.
- **Stato** – L'ultimo stato della transazione aggregata.
- **ID fattura** – Quando l'ordine cliente per la transazione aggregata viene fatturato, l'ID della fattura di vendita. Se questo campo è vuoto, la fattura dell'ordine cliente non è stata registrata.
- **Codice di errore** – Questo campo è impostato se l'aggregazione è in uno stato di errore.
- **Messaggio di errore** – Questo campo è impostato se l'aggregazione è in uno stato di errore. Mostra i dettagli su cosa ha causato l'esito negativo del processo. Puoi utilizzare le informazioni nel codice di errore per risolvere il problema, quindi riavviare manualmente il processo. A seconda del tipo di risoluzione, le vendite aggregate potrebbero dover essere eliminate ed elaborate su un nuovo rendiconto.

![Campi nella Scheda dettaglio Dettagli ordine cliente di una transazione aggregata.](media/aggregated-transactions-error-message-view.png)

Nella scheda dettaglio **Dettagli transazioni** di una transazione aggregata vengono visualizzate tutte le transazioni inserite nella transazione aggregata. Le righe aggregate nella transazione aggregata visualizzano tutti i record aggregati delle transazioni. Le righe aggregate visualizzano anche dettagli quali articolo, variante, quantità, prezzo, importo netto, unità e magazzino. In pratica, ogni riga aggregata corrisponde a una riga di ordine cliente.

![Scheda dettaglio Dettagli transazione di una transazione aggregata.](media/aggregated-transactions-sales-details.png)

In alcune situazioni, le transazioni aggregate potrebbero non riuscire a registrare l'ordine cliente consolidato. In queste situazioni, allo stato dell'istruzione verrà associato un codice di errore. Per visualizzare solo le transazioni aggregate che presentano errori, è possibile abilitare il filtro **Mostra solo errori** nella vista delle transazioni aggregate selezionando la casella di controllo. Abilitando questo filtro, limiti i risultati alle transazioni aggregate che contengono errori che richiedono una risoluzione. Per informazioni su come correggere questi errori, vedi [Modificare e verificare l'ordine online e le transazioni asincrone degli ordini dei clienti](edit-order-trans.md).

![Casella di controllo per il filtro Mostra solo errori nella vista delle transazioni aggregate.](media/aggregated-transactions-failure-view.png)

Dalla pagina **Transazioni aggregate**, è possibile scaricare l'XML per una specifica transazione aggregata selezionando **Esporta dati aggregati**. È possibile rivedere l'XML in qualsiasi strumento di formattazione XML per visualizzare i dettagli dei dati effettivi che implicano la creazione e la registrazione di ordini cliente. La funzionalità per il download dell'XML per le transazioni aggregate non è disponibile per i rendiconti registrati.

![Pulsante Esporta dati di aggregazione nella pagina Transazioni aggregate.](media/aggregated-transactions-export.png)

Nel caso in cui non sia possibile correggere l'errore correggendo i dati sull'ordine cliente o i dati che supportano l'ordine cliente, un pulsante **Elimina ordine cliente** è disponibile. Per eliminare un ordine, seleziona la transazione aggregata non riuscita, quindi seleziona **Elimina ordine cliente**. La transazione aggregata e l'ordine cliente corrispondente vengono eliminati. Ora puoi rivedere le transazioni utilizzando la funzionalità di modifica e controllo. In alternativa, possono essere rielaborati attraverso un nuovo rendiconto. Dopo che tutti gli errori sono stati corretti, è possibile riprendere la registrazione del rendiconto eseguendo la funzione di post rendiconto per il rendiconto pertinente.

![Pulsante Elimina ordine cliente nella vista delle transazioni aggregate.](media/aggregated-transactions-delete-cust-order.png)

La visualizzazione delle transazioni aggregate fornisce i seguenti vantaggi:

- L'utente ha visibilità sulle transazioni aggregate non riuscite durante la creazione degli ordini cliente e sugli ordini cliente non riusciti durante la fatturazione.
- L'utente ha visibilità sul modo in cui le transazioni vengono aggregate.
- L'utente dispone di un audit trail completo, dalle transazioni agli ordini cliente e alle fatture di vendita. Questo audit trail non era disponibile nella funzionalità di registrazione dei rendiconti legacy.
- Il file XML aggregato rende più semplice l'identificazione di eventuali problemi durante la creazione e la fatturazione di ordini cliente.

> [!NOTE]
> Quando le transazioni vengono aggregate, il membro del personale assegnato alla transazione non è più disponibile per il **Report primi venditori**, nel senso che il **Report primi venditori** non mostrerà tutte le transazioni. Ti consigliamo di non utilizzare il **Report primi venditori** con transazioni aggregate.

### <a name="journal-vouchers"></a>Giustificativi giornale di registrazione

Il pulsante **Giustificativi giornale di registrazione** nel gruppo **Dettagli esecuzione** del rendiconto mostra tutte le varie transazioni giustificativo create per un rendiconto e correlate a sconti, conti ricavi/spese, gift card e così via.

Attualmente, il programma visualizza questi dati solo per rendiconti registrati.

### <a name="payment-journals"></a>Giornali di registrazione pagamenti

Il pulsante **Giornali di registrazione pagamenti** nel gruppo **Dettagli di esecuzione** del rendiconto mostra tutti i vari giornali di registrazione pagamenti creati per un rendiconto.

Attualmente, il programma visualizza questi dati solo per rendiconti registrati.

## <a name="other-improvements"></a>Altri miglioramenti

Altri miglioramenti back-end visibili agli utenti sono stati apportati alla funzionalità di registrazione dei rendiconti. Di seguito sono riportati alcuni esempi.

- L'aggregazione non prende in considerazione le entità personale, terminale e turno. Poiché sono disponibili meno parametri di aggregazione, è necessario elaborare meno righe di ordine cliente.
- La possibilità di un blocco critico sulle tabelle di transazioni risulta ridotta grazie all'introduzione di ulteriori tabelle di estensione e all'esecuzione di operazioni di inserimento anziché operazioni di aggiornamento sulle tabelle di transazioni.
- Sono stati introdotti parametri e limiti per il numero di attività batch in esecuzione. Di conseguenza, questo numero può essere ottimizzato per l'ambiente di un cliente. Nella funzionalità di registrazione dei rendiconti legacy, veniva creato un numero illimitato di attività batch simultanee. Ciò comportava carichi non gestibili, overhead e colli di bottiglia nel server batch.
- I rendiconti vengono inseriti in una coda in modo efficiente in quanto viene data la priorità ai rendiconti con il numero massimo di transazioni.
- I processi batch quali **Calcolare rendiconti in batch** e **Registra rendiconti in batch** vengono eseguiti solo in modalità batch. Nella funzionalità di registrazione dei rendiconti legacy, gli utenti potevano scegliere di eseguire questi processi batch in una modalità interattiva, ovvero mediante un'operazione con thread singolo, a differenza dei processi batch che sono a thread multipli.
- Nella funzionalità di registrazione dei rendiconti legacy, un qualsiasi errore di un'attività batch comportava lo stato di errore per l'intero processo batch. Nella funzionalità migliorata, ciò non avviene se altre attività batch vengono completate senza errori. Si consiglia di determinare lo stato di registrazione di un'esecuzione batch tramite la pagina **Rendiconti**, in cui è possibile visualizzare tutti i rendiconti non registrati a causa di errori.
- Nella funzionalità di registrazione dei rendiconti legacy, la prima occorrenza di un errore di rendiconto comporta l'errore dell'intero batch e i rendiconti rimanenti non vengono elaborati. Nella funzionalità migliorata, il processo batch continua a elaborare tutti i rendiconti, anche se alcuni presentano degli errori. Un vantaggio è che gli utenti acquisiscono maggiore visibilità sul numero esatto di rendiconti con errori. Di conseguenza, gli utenti non sono obbligati a correggere gli errori e a eseguire il processo di registrazione dei rendiconti fino a che tutti i rendiconti sono registrati.

## <a name="general-guidance-about-the-statement-posting-process"></a>Indicazioni generali sul processo di registrazione dei rendiconti

- Si consiglia di eseguire il processo di registrazione dei rendiconti in un batch, poiché le esecuzioni batch sfruttano l'efficacia del framework batch in termini di multithreading. Il multithreading è necessario per gestire grandi volumi di transazioni, tipici delle registrazioni di rendiconti.
- Si consiglia di abilitare l'inventario fisico negativo per il gruppo di modelli di articoli, in modo da ottenere un'esperienza di registrazione senza problemi. In alcuni scenari, i rendiconti negativi potrebbero non essere registrati a meno che non sia presente un inventario fisico negativo. Ad esempio, in teoria, se è presente una sola unità di un articolo in magazzino ed è stato eseguita una transazione di vendita e una transazione di reso per l'articolo, la registrazione della transazione dovrebbe essere possibile anche se l'inventario negativo non è attivato. Tuttavia, poiché il processo di registrazione dei rendiconti integra la transazione di vendita e quella di reso in un singolo ordine cliente, non c'è alcuna garanzia che la riga di vendita venga registrata per prima, seguita dalla riga di reso. Di conseguenza, è possibile che si abbiano degli errori. Se l'inventario negativo è attivato in questo scenario, la registrazione della transazione non viene alterata negativamente e il sistema rifletterà correttamente l'inventario.
- Si consiglia di utilizzare l'aggregazione durante il calcolo e la registrazione dei rendiconti. Di conseguenza, le seguenti impostazioni sono consigliate per alcuni dei parametri di aggregazione:

    - Accedere a **Retail e Commerce** \> **Impostazione sedi centrali** \> **Parametri** \> **Parametri di commercio**. Quindi, ,nella scheda **Registrazione**, nella Scheda dettaglio **Aggiornamento dell'inventario**, nel campo **Livello dettagli** selezionare **Riepilogo**.
    - Accedere a **Retail e Commerce** \> **Impostazione sedi centrali** \> **Parametri** \> **Parametri di commercio**. Quindi, nella scheda **Registrazione**, nella Scheda dettaglio **Aggregazione**, impostare l'opzione **Transazioni giustificativo** su **Sì**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
