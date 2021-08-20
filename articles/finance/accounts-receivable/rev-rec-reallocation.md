---
title: Riallocazione del riconoscimento ricavi
description: Questo argomento fornisce informazioni sulla riallocazione, che consente alle organizzazioni di ricalcolare i prezzi dei ricavi quando vengono modificati i termini di una vendita contrattuale. Include i collegamenti ad altri argomenti che descrivono come riconoscere i ricavi in più scenari.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 50ae395c370947e348714ce5685123328849966f3a67903e9ddf8c27dee42f5f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745039"
---
# <a name="revenue-recognition-reallocation"></a>Riallocazione del riconoscimento ricavi

[!include [banner](../includes/banner.md)]

La riallocazione consente alle organizzazioni di ricalcolare i prezzi dei ricavi quando vengono modificati i termini di una vendita contrattuale. Ai fini del riconoscimento dei ricavi, i documenti dell'ordine cliente costituiscono il contratto.

L'organizzazione deve determinare autonomamente se è necessaria la riallocazione. L'aggiunta di una nuova riga a un ordine cliente o l'aggiunta di un nuovo ordine cliente per un cliente potrebbe non costituire una modifica al contratto. La riallocazione può essere richiesta nei seguenti scenari:

- Un cliente ha aggiunto articoli a un ordine cliente o ha rimosso articoli dall'ordine cliente dopo che l'ordine è stato fatturato interamente o parzialmente.
- Per lo stesso contratto negoziato sono stati immessi più ordini cliente, nello stato confermato o fatturato.
- Un cliente ha restituito o ricevuto un credito per un articolo dopo che l'ordine cliente originale è stato fatturato interamente o parzialmente.

Ci sono alcune importanti limitazioni al processo di riallocazione:

- Il processo può essere eseguito solo una volta. Pertanto, è importante eseguirlo solo dopo aver finalizzato tutte le modifiche.
- Il processo non può essere eseguito sugli ordini cliente del progetto.
- Se sono coinvolti più ordini cliente, devono essere per lo stesso conto cliente.
- Tutti gli ordini cliente riallocati devono essere nella stessa valuta di transazione.
- Il processo non può essere stornato o annullato dopo essere stato eseguito.

## <a name="set-up-reallocation"></a>Impostare la riallocazione

Un parametro influisce sul processo di riallocazione.

Poiché la riallocazione può essere eseguita su un ordine cliente parzialmente o interamente fatturato, qualsiasi precedente voce contabile per la fattura deve essere corretta utilizzando i nuovi prezzi dei ricavi riallocati. Questa correzione viene eseguita stornando la voce contabile della fattura originale e registrando una nuova voce contabile basata sui prezzi dei ricavi riallocati.

Ogni organizzazione deve decidere se la correzione aggiorna solo la contabilità generale o anche la contabilità clienti. La decisione determina l'impostazione appropriata dell'opzione **Correzioni delle fatture registrate in contabilità clienti** nella scheda **Riconoscimento ricavi** della pagina **Parametri di contabilità generale** (**Riconoscimento ricavi \> Impostazione \> Parametri di contabilità generale**). L'impostazione appropriata dipende dallo scenario specifico. Per ulteriori informazioni sui possibili scenari, utilizzare i collegamenti nella sezione [Scenari per la riallocazione](#scenarios-for-reallocation) più avanti in questo argomento.

[![Scheda Riconoscimento ricavi nella pagina Parametri di contabilità generale.](./media/01_RevRecScenarios.png)](./media/01_RevRecScenarios.png)

Se l'opzione **Correzioni delle fatture registrate in contabilità clienti** è impostata su **Sì**, il processo di riallocazione produce il seguente risultato:

- Un documento di credito viene creato in contabilità clienti per stornare la fattura che richiede la correzione.

    - Il documento di credito riutilizza il numero di fattura originale, a cui viene aggiunto "-1".
    - Il documento di credito viene automaticamente liquidato a fronte della fattura originale. Se la fattura originale era già stata liquidata con un altro documento di credito o pagamento, tale liquidazione viene automaticamente stornata.
    - Il documento di credito viene registrato nella contabilità generale per stornare la voce contabile registrata nella fattura originale. Tuttavia, le voci delle transazioni inventario e costo del venduto (COGS) non vengono stornate.

- Nella contabilità clienti viene creata una nuova fattura basata sui nuovi importi di prezzo riallocati.

    - La nuova fattura riutilizza il numero di fattura originale, a cui viene aggiunto "-2".
    - La nuova fattura viene automaticamente liquidata a fronte di qualsiasi documento di credito o pagamento precedentemente liquidato con la fattura originale.
    - La nuova fattura viene registrata nella contabilità generale utilizzando i nuovi importi dei prezzi dei ricavi riallocati. Non viene registrata nuovamente nei conti di magazzino e COGS perché queste voci vengono conservate nella voce contabile della fattura originale.

Se l'opzione **Correzioni delle fatture registrate in contabilità clienti** è impostata su **No**, il processo di riallocazione produce il seguente risultato:

- Una voce contabile di storno viene registrata solo nella contabilità generale. Tutta la contabilità della fattura originale viene stornata, ad eccezione delle voci contabili di inventario e COGS.
- Una nuova voce contabile viene registrata solo nella contabilità generale, in base ai nuovi prezzi dei ricavi riallocati. Non viene registrata nuovamente nei conti di magazzino e COGS perché queste voci vengono conservate nella voce contabile della fattura originale.
- La fattura nella pagina **Transazioni cliente** non è interessata o modificata e ancora riflette la voce contabile originale. Non vi è alcun riferimento allo storno o alle nuove voci contabili.

Come è stato accennato, è possibile aggiornare solo la contabilità generale oppure è possibile aggiornare sia la contabilità generale che la contabilità clienti. Entrambi gli approcci hanno vantaggi e svantaggi. Consigliamo di valutare i requisiti dell'organizzazione per determinare quale opzione usare. Se si aggiorna sia la contabilità generale che la contabilità clienti, le voci contabili corrette verranno mostrate sulla nuova fattura e potranno essere visualizzate dal documento nella pagina **Transazioni cliente**. Inoltre, il processo di liquidazione utilizzerà le voci contabili aggiornate per registrare eventuali sconti di cassa e utili o perdite. D'altra parte, il documento di credito e la nuova fattura saranno presenti sugli estratti conto dei clienti e sui report di aging, proprio come gli altri documenti di credito e le fatture cliente. La descrizione dei documenti indicherà che sono stati creati tramite una correzione contabile.

## <a name="run-the-reallocation-process"></a>Eseguire il processo di riallocazione

Per avviare il processo di riallocazione, selezionare **Riallocazione del prezzo con nuove righe ordine** in qualsiasi ordine cliente che è necessario riallocare. In alternativa, andare a **Riconoscimento ricavi \> Attività periodiche \> Riallocazione del prezzo con nuove righe ordine**, quindi inserire i filtri appropriati, ad esempio il conto cliente.

[![Riallocazione del prezzo con nuove righe ordine.](./media/02_RevRecScenarios.png)](./media/02_RevRecScenarios.png)

La griglia superiore della pagina **Riallocazione del prezzo con nuove righe ordine** è denominata **Vendite**. Elenca gli ordini cliente. Selezionare gli ordini cliente che devono essere riallocati. Non è possibile selezionare ordini cliente di progetto, perché gli ordini cliente di progetto non possono essere riallocati. Inoltre, non è possibile selezionare ordini cliente che hanno già un ID riallocazione, perché gli ordini cliente non di progetto possono essere riallocati solo una volta. Se un ordine cliente ha un ID riallocazione, è già stato contrassegnato per la riallocazione da un altro utente.

La griglia inferiore della pagina è denominata **Righe**. Dopo aver selezionato uno o più ordini cliente nella griglia **Vendite**, la griglia **Righe** mostra le righe dell'ordine cliente. Selezionare le righe ordine cliente che devono essere riallocate. Se è stato selezionato un solo ordine cliente, le righe dello stesso ordine cliente devono essere riallocate. Questa situazione può verificarsi quando una delle righe dell'ordine cliente è stata precedentemente fatturata e quindi è stata aggiunta una nuova riga oppure una riga esistente è stata rimossa o annullata. Se una riga è stata rimossa, non viene inclusa nella griglia. Pertanto, non può essere selezionata. Tuttavia, verrà comunque considerata quando viene eseguito il processo di riallocazione.

Dopo aver selezionato le righe dell'ordine cliente richieste, utilizzare i pulsanti nel riquadro Azioni come descritto di seguito:

- **Aggiorna riallocazione** - Calcola i nuovi importi del prezzo dei ricavi per le righe dell'ordine cliente selezionate. Se una riga è stata rimossa o annullata, la riallocazione verrà eseguita solo per le righe esistenti selezionate. La figura seguente mostra un esempio di righe ordine cliente prima dell'aggiornamento della riallocazione.

    [![Righe ordine cliente prima dell'aggiornamento della riallocazione.](./media/03_RevRecScenarios.png)](./media/03_RevRecScenarios.png)

    I nuovi importi dei prezzi dei ricavi vengono visualizzati nella colonna **Importo riallocato** della griglia **RIghe**. A questo punto, la riallocazione è stata elaborata, ma non è stata ancora calcolata. La figura seguente mostra un esempio di righe ordine cliente dopo l'aggiornamento della riallocazione.

    [![Righe ordine cliente dopo l'aggiornamento della riallocazione.](./media/04_RevRecScenarios.png)](./media/04_RevRecScenarios.png)

- **Elabora** - Elaborare o registrare i prezzi dei ricavi riallocati. Dopo aver selezionato questo pulsante, non è possibile annullare la riallocazione. Se non si seleziona **Aggiorna riallocazione** prima di selezionare **Elabora**, la riallocazione viene eseguita automaticamente.

    - Se non è stata fatturata alcuna riga ordine cliente, gli importi dei prezzi dei ricavi vengono aggiornati su tutti gli ordini cliente selezionati per la riallocazione.
    - Se una o più righe ordine cliente sono state fatturate, vengono registrate le voci contabili di correzione e vengono corretti tutti i dettagli della programmazione ricavi creati per la riga ordine cliente fatturata.

- **Giustificativo previsto** - Mostra un'anteprima delle voci contabili che sono state create per tutte le righe ordine cliente fatturate. Se non sono state fatturate righe, non viene visualizzato nulla. Se non si seleziona **Aggiorna riallocazione** prima di selezionare **Giustificativo previsto**, la riallocazione viene eseguita automaticamente.
- **Riallocazione dei ricavi** - Aprire una pagina che mostra l'allocazione dei prezzi dei ricavi per tutte le righe selezionate. Non è possibile modificare nessuna delle informazioni sulla pagina. Vengono visualizzati gli importi riga utilizzati per la riallocazione.

    [![Importi riga utilizzati per la riallocazione.](./media/05_RevRecScenarios.png)](./media/05_RevRecScenarios.png)

- **Reimposta i dati per il cliente selezionato** - Se il processo di riallocazione è stato avviato ma non è stato completato, cancellare i dati nella tabella di riallocazione solo per il cliente selezionato. Ad esempio, se si contrassegnano più righe ordine cliente per la riallocazione, si lascia la pagina aperta senza selezionare **Elabora**, quindi si verifica il timeout della pagina. In questo caso, le righe ordine cliente rimarranno contrassegnate e non saranno disponibili per un altro utente per completare il processo di riallocazione. La pagina potrebbe anche essere vuota quando viene aperta. In questa situazione, il pulsante **Reimposta i dati per il cliente selezionato** può essere utilizzato per cancellare gli ordini cliente non elaborati in modo che un altro utente possa completare il processo di riallocazione.

## <a name="scenarios-for-reallocation"></a>Scenari per la riallocazione

I seguenti argomenti trattano vari scenari per il riconoscimento dei ricavi:

- [Riallocazione del riconoscimento dei ricavi - Scenario 1](rev-rec-reallocation-scenario-1.md) - Vengono immessi due ordini clienti che vengono solo confermati. Lo stesso scenario produrrà risultati simili se più di due ordini cliente sono nello stato confermato.
- [Riallocazione del riconoscimento dei ricavi - Scenario 2](rev-rec-reallocation-scenario-2.md) - Vengono immessi due ordini cliente e quindi il cliente aggiunge un articolo al contratto dopo che il primo ordine cliente è stato fatturato.
- [Riallocazione del riconoscimento dei ricavi - Scenario 3](rev-rec-reallocation-scenario-3.md) - Viene aggiunta una nuova riga a un ordine cliente fatturato esistente.
- [Riallocazione del riconoscimento dei ricavi - Scenario 4](rev-rec-reallocation-scenario-4.md) - Viene rimossa una riga da un ordine cliente fatturato parzialmente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]