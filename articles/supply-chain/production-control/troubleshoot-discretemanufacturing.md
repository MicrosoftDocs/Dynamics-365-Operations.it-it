---
title: Risolvere i problemi di produzione discreta
description: Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizza la produzione discreta.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 895126d9c80c2eb6328c5c6c24140d1a7dc0818762f3f93c737a7858843d3eb7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780030"
---
# <a name="troubleshoot-discrete-manufacturing"></a>Risolvere i problemi di produzione discreta

Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizza la produzione discreta.

## <a name="i-receive-the-following-error-message-warehouse-management-processes-are-currently-being-used-if-work-lines-are-not-yet-registered-you-can-cancel-the-created-work-and-any-load-or-shipment-lines-and-then-continue-with-the-picking-or-shipping-process"></a>Viene visualizzato il seguente messaggio di errore: "I processi di gestione del magazzino sono attualmente in uso. Se le righe di lavoro non sono ancora registrate, è possibile annullare il lavoro creato e qualsiasi riga di carico o spedizione, quindi continuare il processo di prelievo o spedizione."

### <a name="issue-description"></a>Descrizione del problema

Questo problema si verifica se si tenta di prenotare o rilasciare il lavoro per una riga, ma la transazione di inventario ha uno stato *Prelevato*, che indica che il materiale è stato prelevato.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Per risolvere questo problema, eseguire uno dei passaggi seguenti.

- Modificare di nuovo lo stato dell'ordine di produzione in *Stimato* o *Rilasciato*.
- Aprire la pagina dei dettagli dell'ordine di produzione pertinente. Nel riquadro azioni, nella scheda **Magazzino** nel gruppo **Interrompi**, selezionare **Interrompi e annulla prelievo** per annullare tutte le transazioni prelevate. Quindi selezionare **Rimuovi interruzione** per elaborare l'ordine di produzione.

Ecco una spiegazione delle funzioni *Annulla prelievo* e *Interrompi*:

- **Annulla prelievo** - Questa funzione inverte lo stato delle transazioni di inventario per le righe della distinta base (DBA) e le righe della formula che hanno uno stato da *Prelevato* a *In ordine*. Quando il lavoro per il prelievo delle materie prime è completato, lo stato delle righe viene impostato su *Prelevato*. Questo stato impedisce il ripristino dell'ordine di produzione sullo stato *Creato*. In questo caso, è possibile usare la funzione *Annulla prelievo* per ripristinare le transazioni dallo stato *Prelevato* e quindi reimpostare l'ordine di produzione sullo stato *Creato*.
- **Interrompi** - Questa funzione imposta un flah **Interrotto** sull'ordine di produzione per impedire qualsiasi aggiornamento dello stato dell'ordine. Il flag **Interrotto** si trova nella scheda dettaglio **Magazzino** della pagina dei dettagli dell'ordine di produzione.

> [!NOTE]
>
> - I pulsanti sono visibili solo quando viene creato l'ordine di produzione per gli articoli abilitati per i processi di magazzino.
> - Il gruppo **Interrompi** è visibile solo nella scheda **Magazzino** nel riquadro azioni della pagina dei dettagli dell'ordine di produzione. Non è visibile nella Scheda dettaglio **Magazzino** della pagina elenco **Ordini di produzione**.

## <a name="the-matching-resource-name-isnt-updated-after-i-change-a-worker-name-in-the-global-address-book"></a>Il nome della risorsa corrispondente non viene aggiornato dopo aver modificato il nome di un lavoratore nella rubrica globale.

### <a name="issue-description"></a>Descrizione del problema

Se si modifica il nome di un lavoratore nella rubrica globale, il nome della risorsa corrispondente non viene aggiornato nei dati master del gruppo di risorse.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo scenario non è attualmente supportato. Per risolvere il problema, è necessario aggiornare manualmente il nome della risorsa.

## <a name="when-i-create-a-new-production-order-i-dont-receive-the-following-message-insert-the-active-version-of-bill-of-material-and-route"></a>Quando si crea un nuovo ordine di produzione, non viene visualizzato il seguente messaggio: "Inserire la versione attiva della distinta base e del ciclo di lavorazione?"

### <a name="issue-description"></a>Descrizione del problema

Quando si crea un nuovo ordine di produzione, dopo aver immesso il numero articolo, i campi **Sito** e **Magazzino** vengono impostati automaticamente sul sito e sul magazzino predefiniti definiti nella pagina **Impostazioni dell'ordine predefinite** per l'articolo prodotti finiti. Inoltre, il numero DBA attivo e il numero di ciclo di lavorazione vengono inseriti automaticamente. Non viene visualizzato il messaggio seguente che richiede tali valori:

> Inserire la versione attiva per distinta base e ciclo di lavorazione?

### <a name="issue-resolution"></a>Risoluzione dei problemi

Non viene richiesto di inserire i numeri di DBA e ciclo di lavorazione se si seleziona un prodotto per il quale sono definiti un sito e un magazzino nella pagina **Impostazioni dell'ordine predefinite**. Vengono richiesti solo se questi valori non sono definiti per il prodotto selezionato.

## <a name="production-orders-arent-shown-on-the-marking-page"></a>Gli ordini di produzione non vengono visualizzati nella pagina Contrassegno.

### <a name="issue-description"></a>Descrizione del problema

Alcuni ordini di produzione non vengono visualizzati nella pagina **Contrassegno**.

### <a name="issue-resolution"></a>Risoluzione dei problemi

I prodotti con la seguente configurazione non sono disponibili per il contrassegno. Pertanto, non verranno mostrati nella pagina **Contrassegno**:

- I prodotti sono definiti come prodotti di tipo *peso variabile*.
- Sono abilitati per i processi di magazzino avanzati.
- Sono configurati per essere controllati dal principio *Costo standard*.

## <a name="when-i-try-to-end-a-production-order-i-receive-the-following-error-message-calculating-bom-consumptioncost-value-must-be-negative-upon-issue-from-inventory"></a>Quando si tenta di terminare un ordine di produzione, viene visualizzato il seguente messaggio di errore: "Il calcolo del valore dei costi di consulo della distinta base deve essere negativo all'emissione dall'inventario".

Questo problema è stato risolto nella versione 10.0.15.

## <a name="when-the-status-of-a-production-order-is-changed-from-reported-as-finished-to-end-i-receive-the-following-error-messages-update-conflict-the-standard-cost-does-not-match-with-the-financial-inventory-value-after-the-update-and-a-critical-error-has-occurred-in-function-inventcostmovementcheckvariance"></a>Quando lo stato di un ordine di produzione viene modificato da Dichiarato finito a Fine, vengono visualizzati i seguenti messaggi di errore: "Conflitto di aggiornamento. Il costo standard non corrisponde al valore dell'inventario finanziario dopo l'aggiornamento" e "Si è verificato un errore critico nella funzione InventCostMovement.checkVariance".

Questo problema si verifica perché i dati sottostanti sono stati modificati da un altro processo. Il processo proverà ad aggiornare i dati fino a cinque volte. Se il conflitto persiste dopo cinque tentativi, vengono visualizzati i seguenti messaggi di errore:

> Conflitto di aggiornamento. Il costo standard non corrisponde al valore dell'inventario finanziario dopo l'aggiornamento.

> Si è verificato un errore critico nella funzione InventCostMovement.checkVariance.

Questo comportamento è predefinito. Per contenere il problema, riprendere il processo batch. Deve finire l'esecuzione.

Se il processo batch non riesce in modo coerente dopo essere stato ripreso, verificare che la precisione di arrotondamento per la valuta predefinita della contabilità generale sia conforme all'arrotondamento applicato ai valori nella tabella InventSum. Se la precisione di arrotondamento è stata modificata in un valore non conforme, è probabile che sia necessario modificarla nuovamente in un valore conforme. Cercare **ModifiedDateTime**. In questo caso, il valore mostrerà in genere che la precisione di arrotondamento è stata modificata di recente.

## <a name="when-i-release-to-a-warehouse-i-receive-the-following-error-message-item-rm-could-not-be-fully-reserved-ensure-that-the-full-quantity-is-available-or-reserve-the-items-manually-if-the-reservation-field-on-the-bom-line-is-set-to-manual-or-started-could-not-release-the-order-to-warehouse-because-some-materials-could-not-be-reserved-however-the-status-is-updated-to-released"></a>Quando si rilascia in un magazzino, viene visualizzato il seguente messaggio di errore: "Impossibile prenotare completamente l'articolo RM. Verificare che l'intera quantità sia disponibile o prenotare gli articoli manualmente se il campo Prenotazione nella riga DBA è impostato su Manuale o Avviato. Impossibile rilasciare l'ordine al magazzino perché non è stato possibile prenotare alcuni materiali." Tuttavia, lo stato viene aggiornato su Rilasciato.

### <a name="issue-description"></a>Descrizione del problema

Se non tutte le voci della distinta base sono fisicamente disponibili quando viene rilasciato un ordine di produzione, e il criterio **Rilascia in magazzino** è impostato su *Richiedi prenotazione completa* nell'ordine di produzione, viene visualizzato il seguente messaggio di errore:

> L'articolo RM non può essere prenotato completamente. Verificare che l'intera quantità sia disponibile o prenotare gli articoli manualmente se il campo Prenotazione nella riga DBA è impostato su Manuale o Avviato. Impossibile rilasciare l'ordine al magazzino perché non è stato possibile prenotare alcuni materiali.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è di progettazione e funziona come previsto.

## <a name="when-i-try-to-end-a-production-order-and-report-as-finished-i-receive-the-following-error-message-total-good-quantity-reported-as-finished-for-the-production-will-be-1-feedback-for-the-last-operation-is-000-in-total"></a>Quando si prova a terminare un ordine di produzione e lo si contrassegna come finito, viene visualizzato il seguente messaggio di errore: "La quantità totale merci contrassegnata come finita per la produzione sarà %1. Il riscontro complessivo per l'ultima operazione è pari a 0,00."

### <a name="issue-description"></a>Descrizione del problema

Quando si tenta di registrare un report come giornale di registrazione finito in un ordine di produzione, viene visualizzato il seguente messaggio di errore:

> La quantità idonea totale dichiarata finita per la produzione sarà pari a %1. Il riscontro complessivo per l'ultima operazione è pari a 0,00.

### <a name="possible-cause"></a>Possibile causa

Questo problema si verifica se le quantità registrate nelle ultime operazioni non erano corrette. Ad esempio, se la produzione viene avviata, ma la quantità che deve essere avviata non viene allocata, il giornale di registrazione scheda ciclo di lavorazione verrà registrato senza righe. Per confermare la situazione, aprire l'ordine di produzione, quindi, nel riquadro azioni, nella scheda **Visualizza** selezionare **Scheda ciclo di lavorazione**.

### <a name="workaround"></a>Soluzione alternativa

È possibile risolvere questo problema registrando giornali aggiuntivi per le operazioni per le quali i giornali non sono stati registrati correttamente. Riavviare l'ordine di produzione e selezionare per registrare i giornali aggiuntivi. Questa azione non avvierà l'ordine di produzione, ma registrerà i giornali. La scheda ciclo mostra quindi le quantità che sono state registrate ed è possibile terminare correttamente gli ordini di produzione.

## <a name="can-i-report-a-production-order-as-finished-while-i-report-the-error-quantity-but-not-while-i-report-the-time-or-material-quantity"></a>È possibile segnalare un ordine di produzione come finito mentre si riporta la quantità di errore, ma non mentre si riporta il tempo o la quantità di materiale?

Non è possibile segnalare la quantità di errore in un ordine di produzione a meno che non si segnali anche la quantità di merce. Questo scenario **non** è supportato. Il report come aggiornamento terminato alla fine non riesce quando si tenta di terminare l'ordine di produzione e verrà visualizzato il seguente messaggio di errore:

> Manca quantità dichiarata finita.

## <a name="can-i-trace-the-serial-numbers-of-finished-goods-against-the-serial-numbers-of-consumed-goods"></a>È possibile tracciare i numeri di serie dei prodotti finiti rispetto ai numeri di serie dei prodotti consumati?

Non è possibile tracciare i numeri di serie dei prodotti finiti rispetto ai numeri di serie del materiale che un ordine di produzione consuma per realizzare tali prodotti finiti. Questo scenario non è attualmente supportato. La soluzione consiste nel creare ordini di produzione per una quantità di 1.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]