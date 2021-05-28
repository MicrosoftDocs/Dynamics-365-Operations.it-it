---
title: Risolvere i problemi relativi a gerarchie di prenotazione batch e numeri di serie di magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le gerarchie di prenotazione che possono utilizzare dimensioni batch e serie.
author: perlynne
ms.date: 3/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 3/12/2021
ms.openlocfilehash: 1cd4883cdd95a97f821e0103da910e2c0346a08d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022548"
---
# <a name="troubleshoot-warehouse-batch-and-serial-reservation-hierarchies"></a>Risolvere i problemi relativi a gerarchie di prenotazione batch e numeri di serie di magazzino

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le gerarchie di prenotazione che possono utilizzare dimensioni batch e serie.

Per ulteriori informazioni, vedere [Criteri flessibili di prenotazione delle dimensioni a livello di magazzino](flexible-warehouse-level-dimension-reservation.md)

La gerarchia di prenotazione di un articolo determina il requisito delle dimensioni di immagazzinamento che devono essere soddisfatte per assegnare un'ubicazione a un ordine di domanda. Queste dimensioni possono essere descritte come *dimensioni sopra l'ubicazione*, per tutte le dimensioni che devono essere soddisfatte prima dell'assegnazione di un'ubicazione e *dimensioni sotto l'ubicazione* per le dimensioni che possono essere allocate dopo che un'ubicazione è stata assegnata all'ordine di domanda. Queste gerarchie di prenotazione sono note anche come gerarchie di prenotazione *batch-above* e *batch-below* o gerarchie di prenotazione *serial-above* e *serial-below*.

L'inventario può essere allocato correttamente solo se non ci sono spazi vuoti nelle dimensioni sopra l'ubicazione. Ad esempio, in una gerarchia di prenotazione *batch-above*, le dimensioni **Sito,** **Magazzino,** e **Numero di lotto** devono essere specificate sull'ordine di domanda. Se manca una di queste dimensioni, il processo di allocazione avrà esito negativo. Al contrario, in una gerarchia di prenotazione *batch-below* o *serial-below*, un batch o un numero di serie può essere specificato nell'ordine di domanda, ma il processo di allocazione non lo richiede.

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>Viene visualizzato il seguente messaggio di errore: "Per essere assegnate al ciclo, le righe di carico devono specificare le dimensioni sopra l'ubicazione. Per assegnare queste dimensioni, prenotare e ricreare la riga di carico. "

### <a name="issue-description"></a>Descrizione del problema

Quando si utilizza un articolo che ha una gerarchia di prenotazione *batch-above*, il comando **Rilascia in magazzino** nella pagina **Workbench di pianificazione** non funziona se provi a rilasciare un carico per una quantità parziale. Viene visualizzato questo messaggio di errore e non viene creato alcun lavoro per la quantità parziale.

Tuttavia quando utilizzi un articolo che ha una gerarchia di prenotazione *batch-below*, è possibile rilasciare un carico per una quantità parziale dalla pagina **Workbench di pianificazione del carico**.

### <a name="issue-cause"></a>Causa del problema

Quando una dimensione è sopra la dimensione **Ubicazione** nella gerarchia di prenotazione, deve essere specificata prima del rilascio al magazzino. Le quantità parziali non possono essere rilasciate se una o più dimensioni sopra **Ubicazione** non sono specificate.

## <a name="the-auto-reservation-prompt-for-a-batch-number-is-triggered-even-though-there-is-available-inventory"></a>La richiesta di prenotazione automatica per un numero di batch viene attivata anche se l'inventario è disponibile.

### <a name="issue-description"></a>Descrizione del problema

Quando usi un oggetto con una gerarchia di prenotazione *batch-above* in un magazzino che non ha abilitato i processi di magazzino e la prenotazione automatica è abilitata, la richiesta di prenotazione automatica per un numero di batch viene visualizzata anche se è disponibile un solo batch per il prelievo.

Tuttavia, quando utilizzi lo stesso articolo in un magazzino in cui sono abilitati i processi di magazzino, la richiesta di prenotazione automatica non viene visualizzata.

### <a name="issue-cause"></a>Causa del problema

Se una gerarchia di prenotazione è definita come *batch-above* o *serial-above*, la dimensione di riferimento (**Numero batch** o **Numero di serie**) deve sempre essere specificata su ordini di domanda. I processi di magazzino potrebbero essere in grado di completare le informazioni se è disponibile un singolo batch o numero di serie. Tuttavia, poiché il magazzino non è abilitato per i processi di magazzino, l'utente deve sempre specificare tutte le dimensioni sopra **Ubicazione**.

## <a name="slotting-templates-that-have-the-consider-on-hand-slot-criterion-dont-consider-current-on-hand-inventory-for-batch-enabled-items"></a>I modelli di assegnazione che hanno il criterio di assegnazione Considera scorte, non considerano le scorte disponibili correnti per gli articoli abilitati per il batch.

Per ulteriori informazioni, vedi [Assegnazione magazzino](warehouse-slotting.md).

### <a name="issue-description"></a>Descrizione del problema

I modelli di assegnazione che hanno il criterio di assegnazione *Considera scorte*, non considerano le scorte disponibili correnti per gli articoli *batch-above*. Lo considerano solo se il numero di batch è specificato nella riga dell'ordine cliente.

Tuttavia, quando usi articoli *batch-below*, le scorte disponibili correnti sono considerate come previsto.

### <a name="issue-cause"></a>Causa del problema

L'intestazione del modello di assegnazione può essere definita per la strategia della domanda *Ordinato*, *Prenotato*, o *Rilasciato*. Per la strategia della domanda *Ordinato* si applicano gli stessi requisiti della gerarchia di prenotazione che si applicano alla prenotazione o al rilascio ai processi di magazzino. Pertanto, per gli articoli che hanno gerarchie di prenotazione *batch-above* e *serial-below*, il batch o il numero di serie devono essere specificati nell'ordine di domanda (vendita o trasferimento). In alternativa, la strategia della domanda *Prenotato* può essere utilizzata per selezionare il batch o il numero di serie prima che venga generata la domanda di assegnazione del magazzino.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
