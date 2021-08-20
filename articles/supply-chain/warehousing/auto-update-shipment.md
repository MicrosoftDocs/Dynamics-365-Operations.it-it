---
title: Aggiornamenti automatici delle spedizioni
description: In questo argomento viene fornita una panoramica della funzionalità che fornisce aggiornamenti automatici delle spedizioni.
author: josaw1
ms.date: 11/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable,SalesTableListPage,SalesTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 69d20615eb72b036659fe99b140ca18b1fb529bf5ec03bf9390615ea315e9202
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760252"
---
# <a name="shipment-auto-updates"></a>Aggiornamenti automatici delle spedizioni

[!include [banner](../includes/banner.md)]

La funzionalità di aggiornamento automatico delle spedizioni aggiorna automaticamente le quantità (aumenti e diminuzioni) in una riga di carico associata a una spedizione, dopo che il carico è stato rilasciato in un magazzino. Questa funzionalità rimarrà attivata fino all'elaborazione della riga di carico nella spedizione o del carico in un'ondata. Quando utilizzata, gli aggiornamenti degli ordini vengono automaticamente inviati al magazzino, senza richiedere un intervento manuale, fino alla creazione del lavoro di magazzino.

Quando la funzionalità di aggiornamento automatico delle spedizioni non è utilizzata, solo le diminuzioni della quantità vengono automaticamente inviate al magazzino fino alla creazione del lavoro di magazzino. Gli utenti devono aggiornare o eliminare manualmente le righe e devono quindi rilasciarle di nuovo se le quantità degli ordini aumentano o si aggiungono nuove righe ordine. Mediante la funzionalità di aggiornamento automatico delle spedizioni, le aziende possono fornire facilmente aggiornamenti al magazzino senza doversi preoccupare dell'eventuale non corrispondenza di spedizioni e carichi con gli aggiornamenti delle righe ordine.

La funzionalità di aggiornamento automatico delle spedizioni si applica alle righe ordine cliente e alle righe ordine di trasferimento ed è attivata per uno specifico magazzino. Di conseguenza, le aziende possono applicare differenti criteri di aggiornamento automatico delle spedizioni ai magazzini, in base alle proprie esigenze. Per impostazione predefinita, i criteri di aggiornamento automatico delle spedizioni per le diminuzioni della quantità sono applicati a tutti i magazzini che utilizzano processi di gestione magazzino. Quando si utilizzano questi criteri predefiniti, solo le diminuzioni della quantità vengono automaticamente dirette a una spedizione e a un carico fino alla creazione di un lavoro di magazzino. Questo comportamento è simile a quello utilizzato prima dell'introduzione della funzionalità di aggiornamento automatico delle spedizioni.

## <a name="main-elements-of-the-functionality"></a>Elementi principali della funzionalità

La funzionalità di aggiornamento automatico delle spedizioni si basa principalmente sullo stato della spedizione per determinare se la quantità in una riga di carico deve essere modificata in caso di modifica di una riga ordine cliente o ordine di trasferimento. Si basa sullo stato della spedizione anche per determinare quando una nuova riga di carico deve essere aggiunta automaticamente a un carico esistente. Quando lo stato della spedizione è **In ondata** o superiore, non si ha alcun aggiornamento automatico.

Anche lo stato dell'ondata viene preso in considerazione per gli aggiornamenti automatici. Quando lo stato dell'ondata correlata alla riga di carico è **Tenuta**, **In esecuzione**, **Rilasciata**, **Prelevata** o **Spedita**, se un utente tenta di ridurre la quantità in una riga di carico (tramite una diminuzione della quantità nella riga ordine cliente o ordine di trasferimento) viene visualizzato il messaggio di errore "Impossibile rimuovere le prenotazioni perché è presente lavoro creato che si basa sulle prenotazioni". Inoltre, quando lo stato dell'ondata è uno degli stati menzionati precedentemente, se un utente tenta di aumentare indirettamente la quantità nella riga di carico aumentando la quantità nella riga ordine cliente o ordine di trasferimento, la quantità nella riga di carico non viene aumentata automaticamente. In tal caso, la riga di carico deve essere aggiornata manualmente.

## <a name="scenarios"></a>Scenari

La funzionalità di aggiornamento automatico delle spedizioni supporta quattro scenari: aggiunta di una nuova riga ordine, aumento della quantità in una riga ordine, diminuzione della quantità in una riga ordine e rimozione di una riga ordine.

- **Aggiungere una nuova riga ordine** - Quando il campo **Aggiornamento automatico spedizione** nella Scheda dettaglio **Magazzino** della pagina **Magazzini** (**Gestione magazzino \> Impostazione \> Magazzino \> Magazzini**) è impostato su **Sempre**, se una spedizione esiste per l'ordine e una nuova riga ordine viene aggiunta a un ordine cliente o a un ordine di trasferimento dopo che un carico è già stato creato per l'ordine cliente, il carico esistente non viene aggiornato. Una nuova riga di carico che non ha riferimento al carico corrente viene creata e associata a una spedizione esistente. La nuova riga viene aggiunta al carico e rilasciata.
- **Aumentare la quantità in una riga ordine** - Quando il campo **Aggiornamento automatico spedizione** è impostato su **Sempre**, se una spedizione esiste per l'ordine e la quantità in una riga ordine cliente o ordine di trasferimento esistente viene aumentata dopo che un carico è già stato creato per l'ordine cliente, la riga di carico viene aumentata della stessa quantità della riga ordine. Se il carico è stato rilasciato, ma non è stato creato alcun lavoro, la riga di carico viene aumentata della stessa quantità della riga ordine.
- **Diminuire la quantità in una riga ordine** - Quando il campo **Aggiornamento automatico spedizione** è impostato su **Sempre** o su **Alla diminuzione della quantità** e la quantità in una riga ordine cliente o ordine di trasferimento viene diminuita dopo che un carico è già stato creato per l'ordine cliente, la quantità nella riga di carico associata viene aggiornata di conseguenza, a meno che la quantità nella riga di carico sia già uguale o inferiore alla nuova quantità nella riga ordine. In tal caso, la riga di carico resta invariata. Se il carico è stato rilasciato, ma non è stato creato alcun lavoro, la quantità della riga di carico associata viene aggiornata di conseguenza, a meno che la quantità nella riga di carico sia già uguale o inferiore alla nuova quantità nella riga ordine. In tal caso, la riga di carico cambia.
- **Rimuovere una riga ordine** - Quando il campo **Aggiornamento automatico spedizione** è impostato su **Sempre** o su **Alla diminuzione della quantità**, se l'utente tenta di rimuovere una riga ordine per la quale esiste una riga di carico, viene visualizzato un messaggio di errore.

## <a name="example-scenario"></a>Scenario di esempio

Per questo scenario, i dati dimostrativi devono essere installati ed è necessario utilizzare la società di dati dimostrativi **USMF**.

### <a name="turn-on-the-auto-update-shipment-functionality"></a>Attivare la funzionalità di aggiornamento automatico della spedizione

Per attivare la funzionalità di aggiornamento automatico della spedizione, attenersi alla procedura seguente.

1. Selezionare **Gestione magazzino \> Impostazioni \> Magazzino \> Magazzini**.
2. Selezionare il magazzino **24**.
3. Nella Scheda dettaglio **Magazzino**, nel campo **Aggiornamento spedizione automatica**, modificare il valore da **Alla diminuzione della quantità** a **Sempre**.

Dopo aver impostato il valore **Sempre**, gli aumenti o le diminuzioni delle quantità nelle righe ordine cliente e ordine di trasferimento e le aggiunte di nuove righe vengono riflessi nelle spedizioni e nei carichi per il magazzino selezionato, dati i vincoli di aggiornamento menzionati precedentemente.

### <a name="change-the-wave-template-so-that-load-lines-arent-automatically-processed"></a>Modificare il modello di ondata di modo che le righe non siano elaborate automaticamente

Per configurare il modello di ondata di modo che non elabori automaticamente le righe di carico, procedere come segue.

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
2. Selezionare il modello di ondata **Spedizione predefinita 24**.
3. Selezionare **Modifica**.
4. Nella Scheda dettaglio **Generale**, impostare l'opzione **Automatizza creazione ondata** su **Sì** e verificare che tutte le altre opzioni siano impostate su **No**.

È importante che nessun lavoro venga creato e rilasciato automaticamente come parte del processo di creazione dell'ondata. Dopo la creazione di lavoro correlato alla riga di carico creata per la riga ordine cliente, la riga di carico non viene più aggiornata automaticamente se la quantità nella riga ordine cliente viene modificata.

### <a name="create-a-sales-order"></a>Crea un ordine cliente

Per creare un ordine cliente, procedere come segue.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
2. Selezionare il cliente **US-003**.
3. Creare una riga per il numero di articolo **A0001**.
4. Immettere la quantità **10** (assicurarsi di utilizzare il magazzino **24**).
5. Selezionare **Salva**.
6. Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**. Vengono creati una spedizione e un'ondata.

Poiché il modello di ondata è stato modificato nella procedura precedente, non viene creato alcun carico o lavoro. Lo stato della spedizione è **Aperta** e lo stato dell'ondata è **Creata**.

### <a name="decrease-the-quantity-on-a-sales-order-line"></a>Diminuire la quantità in una riga ordine cliente

Per diminuire la quantità in una riga ordine cliente, procedere come segue.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
2. Selezionare l'ordine cliente appena rilasciato nel magazzino.
3. Selezionare la riga ordine cliente. Nel campo **Quantità**, cambiare il valore da **10** a **8**.
4. Dalla riga ordine cliente, selezionare **Magazzino \> Dettagli spedizione**. Nella pagina **Dettagli spedizione**, nella Scheda dettaglio **Righe carico**, la quantità riflette la modifica nella riga ordine cliente.

### <a name="increase-the-quantity-on-a-sales-order-line"></a>Aumentare la quantità in una riga ordine cliente

Per aumentare la quantità in una riga ordine cliente, procedere come segue.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
2. Selezionare l'ordine cliente rilasciato precedentemente nel magazzino.
3. Modificare la quantità della riga da **8** a **12**.
4. Selezionare **Salva**.
5. Ritornare alla pagina **Tutti gli ordini clienti** e selezionare di nuovo l'ordine cliente.
5. Nella scheda **Magazzino** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Dettagli spedizione**. Nella pagina **Dettagli spedizione**, nella Scheda dettaglio **Righe carico**, la quantità riflette la modifica nella riga ordine cliente.

Sebbene la quantità nella riga di carico sia stata aumentata da 8 a 12, soltanto otto articoli rimangono prenotati, a meno che la prenotazione automatica non sia attivata. Poiché la quantità che è stata aggiunta alla spedizione esistente non è stata prenotata, se a questo punto l'ondata viene elaborata senza prenotazione, il lavoro viene creato solo per la quantità già prenotata.

> [!NOTE]
> Quando la quantità in una riga ordine viene diminuita, quella nella riga di carico resta invariata se è già uguale o inferiore alla nuova quantità nella riga ordine. Quando la quantità in una riga ordine viene aumentata, la riga di carico viene aumentata della stessa quantità della riga ordine. Se la quantità nella riga ordine differisce da quella nella riga di carico, la differenza rimane.

### <a name="add-a-sales-order-line"></a>Aggiungere una riga ordine cliente

Per aggiungere una riga ordine cliente, procedere come segue.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
2. Selezionare l'ordine cliente rilasciato precedentemente nel magazzino.
3. Creare una riga per il numero di articolo **A0002**.
4. Nel campo **Quantità** immettere **10** (assicurarsi di utilizzare il magazzino **24**). La nuova riga viene automaticamente aggiunta alla spedizione esistente.
5. Selezionare **Salva**.
6. Ritornare alla pagina **Tutti gli ordini clienti** e selezionare di nuovo l'ordine cliente.
7. Nella scheda **Magazzino** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Dettagli spedizione**. Nella pagina **Dettagli spedizione** della Scheda dettaglio **Righe carico**, notare la seconda riga di carico.

Poiché la riga ordine cliente appena aggiunta alla spedizione esistente non è stata prenotata, se a questo punto l'ondata viene elaborata, il lavoro viene creato solo per la quantità nella prima riga ordine cliente e nella prima riga di carico.

### <a name="process-a-wave"></a>Elaborare un'ondata

Per elaborare l'ondata, procedere come segue.

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
2. Selezionare l'ondata creata in precedenza.
3. Nel riquadro azioni, scheda **Ondata**, gruppo **Ondata**, selezionare **Elabora**.

L'ondata viene elaborata e viene creato un lavoro per le quantità prenotate nelle righe di carico. Lo stato della spedizione passa da **Aperta** a **In ondata**. Quando lo stato della spedizione diventa **In ondata**, le eventuali modifiche, come diminuzioni o aumenti nelle quantità delle righe, o l'aggiunta di nuove righe all'ordine cliente, non influiranno sulle righe di carico esistenti associate alla spedizione in ondata.

Se lo stato di una spedizione è **In ondata** o superiore, gli aggiornamenti alla quantità di una riga ordine cliente non vengono applicati a una riga di carico associata alla spedizione o convalidati a fronte di tale riga. Le modifiche alla quantità in una riga di carico devono essere eseguite direttamente nella riga di carico.

La convalida viene eseguita dopo aver creato un lavoro per la riga di carico ed effettuato una prenotazione. Una diminuzione della quantità nella riga ordine cliente viene quindi convalidata a fronte della prenotazione della riga di lavoro.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]