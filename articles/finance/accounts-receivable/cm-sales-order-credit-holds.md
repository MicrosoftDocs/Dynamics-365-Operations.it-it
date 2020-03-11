---
title: Sospensioni credito per ordini cliente
description: ''
author: mikefalkner
manager: AnnBe
ms.date: 01/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 316a626e6a18f0afda632111138482f62f6809db
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057672"
---
# <a name="credit-holds-for-sales-orders"></a>Sospensioni credito per ordini cliente
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Questo argomento descrive l'impostazione delle regole utilizzate per mettere un ordine cliente in attesa del credito. Le regole di blocco della gestione dei crediti possono essere applicate a un singolo cliente o a un gruppo di clienti.  Le regole di blocco definiscono le risposte alle seguenti circostanze:

1. Numero di giorni in ritardo
2. Stato dei conti
3. Termini di pagamento
4. Limite di credito scaduto
5. Importo scaduto
6. Importo ordine cliente
7. Porzione di credito disponibile utilizzata

Inoltre, esistono due parametri che controllano scenari aggiuntivi che bloccano un ordine cliente

1. Variazione nei termini di pagamento
2. Variazione negli sconti di liquidazione

## <a name="set-up-blocking-rules-and-exclusion-rules"></a>Impostare regole di blocco e regole di esclusione

Quando un cliente avvia una transazione di vendita, le informazioni sull'ordine cliente vengono esaminate rispetto a una serie di regole di blocco che determinano la decisione di estendere o meno il credito al cliente e consentire alla vendita di proseguire. È anche possibile definire esclusioni che sostituiranno le regole di blocco e consentiranno l'elaborazione di un ordine cliente. È possibile impostare regole di blocco e regole di esclusione nella pagina **Gestione crediti > Impostazione> Impostazione gestione crediti > Regole di blocco**.

### <a name="days-overdue"></a>Giorni di ritardo

Aprire la scheda **Giorni in ritardo** se la regola di blocco si applica al cliente con una o più fatture scadute da un certo numero di giorni.
1. Selezionare la gamma di clienti a cui applicare questa regola nel campo **Valido per**.
   - Selezionare **Tabella** se la regola si applica a un cliente specifico.
   - Selezionare **Gruppo** se la regola viene applicata a livello di gruppo di clienti. 
   - Selezionare **Tutti** se la regola si applica a tutti i clienti.
2. Dopo aver specificato l'intervallo, è necessario specificare il **Conto/gruppo** che verrà utilizzato nell'intervallo.
   - Per l'intervallo **Tabella**, la ricerca fornirà un elenco di clienti da selezionare. 
   - Selezionare un **Gruppo** se la regola si applica a un gruppo di crediti cliente.
   - Selezionare **Tutti** se la regola si applica a tutti i clienti. 
3. Selezionare **Gruppo di rischio** per utilizzare criteri per applicare una sospensione della gestione di crediti ai clienti che sono raggruppati in base a un set di fattori comuni, come i loro rating Dun e Bradstreet, il numero di anni di attività, la quantità di tempo che sono tuoi clienti e così via.  
4. Selezionare il tipo di regola che si sta impostando. L'opzione **Blocco** creerà una regola che blocca un ordine. L'opzione **Esclusione** creerà una regola che escluderà un'altra regola di blocco di un ordine. 
5. Selezionare un **tipo di valore**. La voce predefinita è un numero di giorni fisso. Se si sta creando un'esclusione, è possibile specificare un numero fisso di giorni o un importo. 
6. Inserire il numero di giorni **In ritardo** che sarà autorizzato per la regola di blocco selezionata prima che un ordine venga messo in attesa della gestione del credito per verifica. Il numero di giorni di ritardo rappresenta un numero supplementare di giorni di tolleranza che vengono aggiunti al numero di giorni oltre la data di scadenza del pagamento che la fattura può avere prima che sia considerata in ritardo. Se è stato specificato il **Tipo di valore** come importo per un'esclusione, inserire un importo e una valuta per tale importo.

### <a name="accounts-status"></a>Stato dei conti

Aprire la scheda **Stato dei conti** se la regola di blocco si applica a un cliente con lo stato di conto selezionato.
1. Selezionare il tipo di regola che si sta impostando.  L'opzione **Blocco** creerà una regola che blocca un ordine. L'opzione **Esclusione** cerea una regola che escluderà una regola di blocco di un ordine. 
2. Selezionare lo **Stato dei conti** in seguito al quale la regola metterà in attesa un ordine cliente o lo escluderà.

### <a name="terms-of-payment"></a>Termini di pagamento

Selezionare **Termini di pagamento** se la regola di blocco si applica ai termini di pagamento selezionati.
1. Selezionare il tipo di regola che si sta impostando.  L'opzione **Blocco** creerà una regola che blocca un ordine. L'opzione **Esclusione** cerea una regola che escluderà una regola di blocco di un ordine. 
2. Selezionare i **Terminidi pagamento** in seguito ai quale la regola metterà un ordine cliente in attesa o lo escluderà.

### <a name="credit-limit-expired"></a>Limite di credito scaduto

Aprire la scheda **Limite di credito scaduto** se la regola di blocco si applica ai clienti con limiti di credito scaduti.
1. Selezionare la gamma di clienti a cui applicare questa regola nel campo **Valido per**.
   - Selezionare **Tabella** se la regola si applica a un cliente specifico.
   - Selezionare **Gruppo** se la regola viene applicata a livello di gruppo di clienti. 
   - Selezionare **Tutti** se la regola si applica a tutti i clienti.
2. Dopo aver specificato l'intervallo, si deve specificare il **Conto/gruppo** che verrà utilizzato nell'intervallo.
   - Per l'intervallo **Tabella**, la ricerca fornirà un elenco di clienti in cui effettuare la selezione. 
   - Selezionare un **Gruppo** se la regola si applica a un gruppo di gestione di crediti cliente.
   - Selezionare **Tutti** se la regola si applica a tutti i clienti. 
3. Selezionare un **Gruppo di rischio** per limitare ulteriormente l'elenco dei clienti che verranno messi in attesa della gestione del credito. 
4. Selezionare il tipo di regola che si sta impostando. 
  - Selezionare **Blocco** per creare una regola che blocca un ordine. 
  - Selezionare **Esclusione** per creare una regola che escluderà un'altra regola di blocco di un ordine. 
6. Immettere il valore **Giorni limite di credito scaduto** per la regola di blocco selezionata prima che un ordine venga messo in attesa della gestione del credito. Il numero di giorni scaduti rappresenta i giorni di tolleranza aggiuntivi che vengono aggiunti al numero di giorni in cui il limite di credito è scaduto.

### <a name="overdue-amount"></a>Importo scaduto

Aprire la scheda **Importo scaduto** se la regola di blocco si applica ai clienti con importi scaduti.
1. Selezionare la gamma di clienti a cui applicare questa regola nel campo **Valido per**.
   - Selezionare **Tabella** se la regola si applica a un cliente specifico.
   - Selezionare **Gruppo** se la regola viene applicata a livello di gruppo di clienti. 
   - Selezionare **Tutti** se la regola si applica a tutti i clienti.
2. Dopo aver specificato l'intervallo, si deve specificare il **Conto/gruppo** che verrà utilizzato nell'intervallo.
   - Per l'intervallo **Tabella**, la ricerca fornirà una ricerca per clienti. 
   - Selezionare un **Gruppo** se la regola si applica a un gruppo di gestione di crediti cliente.
   - Selezionare **Tutti** se la regola si applica a tutti i clienti. 
3. Selezionare un **Gruppo di rischio** per limitare ulteriormente l'elenco dei clienti che verranno messi in attesa della gestione del credito. 
4. Selezionare il tipo di regola che si sta impostando. 
  - Selezionare **Blocco** per creare una regola che blocca un ordine. 
  - Selezionare **Esclusione** per creare una regola che escluderà un'altra regola di blocco di un ordine. 
5. Immettere il valore di **Importo scaduto** per la regola di blocco selezionata prima che un ordine venga messo in attesa della gestione del credito per verifica. 
6. Selezionare l'opzione **Tipo di valore** che definisce il tipo di valore che verrà utilizzato per verificare anche la quantità di limite di credito utilizzata. Le regole di blocco richiedono una percentuale ma un'esclusione può avere una soglia di importo o percentuale
fissa. La soglia si riferisce al limite di credito.
7. Immettere il valore **Soglia limite di credito** per la regola selezionata prima che un cliente venga messo in attesa della gestione del credito. Questo valore può essere un importo o una percentuale in base al tipo di valore selezionato in Tipo di valore.
8. La regola controlla se i valori **Importo scaduto** e **Soglia limite di credito** vengono superati. 

### <a name="sales-order"></a>Ordine cliente 

Selezionare **Ordine cliente** se la regola di blocco si applica al valore dell'ordine cliente.
1. Selezionare la gamma di clienti a cui applicare questa regola nel campo **Valido per**.
   - Selezionare **Tabella** se la regola si applica a un cliente specifico.
   - Selezionare **Gruppo** se la regola viene applicata a livello di gruppo di clienti. 
   - Selezionare **Tutti** se la regola si applica a tutti i clienti.
2. Dopo aver specificato l'intervallo, si deve specificare il **Conto/gruppo** che verrà utilizzato nell'intervallo.
   - Per l'intervallo **Tabella**, la ricerca fornirà una ricerca per clienti. 
   - Selezionare un **Gruppo** se la regola si applica a un gruppo di gestione di crediti cliente.
   - Selezionare **Tutti** se la regola si applica a tutti i clienti. 
3. Selezionare un **Gruppo di rischio** per limitare ulteriormente l'elenco dei clienti che verranno messi in attesa della gestione del credito. 
4. Selezionare il tipo di regola che si sta impostando.  
  - Selezionare **Blocco** per creare una regola che blocca un ordine. 
  - Selezionare **Esclusione** per creare una regola che escluderà un'altra regola di blocco di un ordine. 
6. Immettere il valore **Importo ordine cliente** per la regola di blocco selezionata prima che un ordine venga messo in attesa della gestione del credito. 

La regola dell'ordine cliente include un'impostazione aggiuntiva che sostituisce tutte le altre regole. Per creare un'esclusione che rilascerà l'ordine cliente senza applicare altre regole, selezionare la casella di controllo **Rilascia ordine cliente** nella riga di esclusione.

### <a name="credit-limit-used"></a>Limite di credito usato

Selezionare **Limite di credito usato** se la regola di blocco si applica all'importo del limite di credito utilizzato.
1. Selezionare la gamma di clienti a cui applicare questa regola nel campo **Valido per**.
   - Selezionare **Tabella** se la regola si applica a un cliente specifico.
   - Selezionare **Gruppo** se la regola viene applicata a livello di gruppo di clienti. 
   - Selezionare **Tutti** se la regola si applica a tutti i clienti.
2. Dopo aver specificato l'intervallo, si deve specificare il **Conto/gruppo** che verrà utilizzato nell'intervallo.
   - Per l'intervallo **Tabella**, la ricerca fornirà una ricerca per clienti. 
   - Selezionare un **Gruppo** se la regola si applica a un gruppo di gestione di crediti cliente.
   - Selezionare **Tutti** se la regola si applica a tutti i clienti. 
3. Selezionare un **Gruppo di rischio** per limitare ulteriormente l'elenco dei clienti che verranno messi in attesa della gestione del credito. 
4. Selezionare il tipo di regola che si sta impostando.
   - Selezionare **Blocco** per creare una regola che blocca un ordine. 
   - Selezionare **Esclusione** per creare una regola che escluderà un'altra regola di blocco di un ordine. 
5. Selezionare il valore **Soglia rimanente** che definisce la percentuale del limite di credito che bloccherà l'ordine cliente. Se il valore di un ordine aumenta l'importo del limite di credito utilizzato al di sopra della percentuale, l'ordine verrà messo in attesa. 

## <a name="put-a-sales-order-on-hold-based-on-other-criteria"></a>Mettere in attesa un ordine cliente in base ad altri criteri
  
### <a name="rank-payment-terms"></a>Classifica termini di pagamento  

È possibile forzare l'esecuzione delle regole di controllo del credito in caso di modifica dei termini di pagamento. È necessario classificare i termini di pagamento e assegnargli un valore di classificazione. Se i termini di pagamento nell'ordine vengono sostituiti con termini di pagamento classificati più in alto rispetto ai termini di pagamento precedenti, l'ordine verrà inviato a Gestione crediti e dovrà essere approvato.

È possibile impostare la classificazione dei termini di pagamento nella pagina **Gestione crediti > Impostazione > Impostazione gestione crediti> Classifica termini di pagamento**.

1. Selezionare i termini di pagamento da classificare nel campo **Termini di pagamento**; quando si seleziona un termine, la descrizione verrà visualizzata nel campo **Descrizione**.
2. Selezionare la classificazione dei termini nel campo **Classificazione**. I valori sono tutti reciprocamente relativi quindi è possibile utilizzare 1, 2, 3 oppure 10, 20, 30. È anche possibile utilizzare lo stesso valore per la maggior parte dei termini di pagamento in modo che solo uno o due termini di pagamento attiveranno il controllo del credito.

### <a name="rank-settlement-discounts"></a>Classifica sconti liquidazione   

È possibile forzare l'esecuzione delle regole di controllo del credito in caso di modifica degli sconti di liquidazione. È necessario classificare gli sconti di liquidazione e assegnargli un valore di classificazione. Se gli sconti di liquidazione nell'ordine vengono sostituiti con sconti di liquidazione classificati più in alto rispetto agli sconti di liquidazione precedenti, l'ordine verrà inviato a Gestione crediti e dovrà essere approvato.

È possibile impostare la classificazione degli sconti di liquidazione nella pagina **Gestione crediti > Impostazione > Impostazione gestione crediti> Classifica sconti di liquidazione**.

1. Selezionare lo **Sconto di cassa** che si desidera classificare. Verrà visualizzata la **Descrizione** dello sconto di liquidazione.
2. Selezionare il valore **Classificazione**. I valori sono tutti reciprocamente relativi quindi è possibile utilizzare 1, 2, 3 oppure 10, 20, 30. È anche possibile utilizzare lo stesso valore per la maggior parte degli sconti di liquidazione, in modo che solo uno o due sconti di liquidazione attiveranno il controllo del credito.

## <a name="sequence-the-application-of-rules"></a>Sequenza dell'applicazione delle regole

Le regole vengono eseguite in un ordine specifico che si modifica per soddisfare le esigenze della propria organizzazione. 

- Un'istanza delle regole di esclusione di ordini cliente consente di sovrascrivere tutte le regole che potrebbero bloccare un ordine cliente. Creare una regola di esclusione di ordini cliente e contrassegnare l'opzione **Rilascia ordine cliente**. L'ordine non verrà messo in attesa se tale regola di esclusione è vera e non vengono selezionate altre regole.
- Le regole di blocco possono mettere in attesa l'ordine.
- Le regole di esclusione vengono eseguite dopo le regole di esclusione. Le regole di esclusione influiranno solo la regola in base alla quale sono definite. 
- Le regole di blocco ed esclusione vengono eseguite nell'ordine Tabella, Gruppo e Tutte. A causa di questo ordine di elaborazione, è possibile che una regola di blocco al livello Tutte non venga eseguita poiché viene eseguita una regola di esclusione al livello Tabella o Gruppo.
- Le esclusioni non sostituiscono la regola di blocco se sono allo stesso livello. Ad esempio, una regola di esclusione al livello Gruppo non sostituirà la regola di blocco al livello Gruppo. Non sarà necessario impostare le esclusioni al livello Tutte, ad eccezione di quanto indicato sopra con un'istanza della regola di esclusione di ordini cliente. 

Il comportamento della regola **Limite di credito usato** cambierà in base alle impostazioni del parametro **Verifica limite di credito per ordini cliente** nel modulo Credito e riscossioni.
- Se il parametro è impostato su No, la regola Limite di credito usato non verrà eseguita.
- Se il parametro è impostato su Sì e **Notifica in caso di superamento limite di credito** è impostato su Avviso, si riceverà un avviso quando viene superato il limite di credito. Le regole **Limite di credito usato** verranno eseguite per determinare se vi sono regole che si desidera eseguire. Tuttavia, per questo scenario, normalmente non si aggiungono regole.
- Se il parametro è impostato su Sì e **Notifica in caso di superamento limite di credito** è impostato su Errore, il limite di credito verrà verificato e l'ordine verrà messo in attesa se viene superato il limite di credito. Inoltre, le regole **Limite di credito usato** verranno eseguite per determinare se vi sono ulteriori regole che devono essere eseguite. Non verrà visualizzato un messaggio di errore, ma il motivo di blocco **Limite di credito superato**. 

## <a name="settings-that-will-change-the-way-an-order-is-placed-on-hold"></a>Impostazioni che modificheranno il modo in cui un ordine viene messo in attesa

Gli ordini possono essere esclusi dalla gestione dei crediti anche se sono in vigore delle regole. 

- Se si imposta su **Sì** l'opzione **Escludi cliente da gestione crediti** in **Tutti i clienti > Seleziona cliente > scheda dettaglio Crediti e riscossioni**, non verranno elaborati ordini per quel cliente.
- Se si imposta su **Sì** l'opzione **Escludi gestione crediti** nell'**intestazione degli ordini cliente** nella **scheda dettaglio Gestione crediti**, le regole di gestione dei crediti non verranno elaborate. Questa impostazione può essere effettuata solo dall'addetto o dal responsabile che si occupa della gestione dei crediti.

## <a name="processing-orders-on-hold-using-the-credit-management-hold-list"></a>Elaborazione di ordini in attesa mediante l'elenco di sospensioni di gestione crediti

L'elenco di sospensioni di gestione crediti consente ai responsabili della gestione dei crediti di visualizzare tutti gli ordini cliente che sono stati messi in attesa e consente loro di rimuovere le sospensioni quando i problemi di credito sono stati mitigati. La pagina **Elenco sospensioni gestione crediti** mostra tutti gli ordini cliente che sono stati messi in attesa. È possibile visualizzare l'elenco di ordini cliente in attesa nella pagina **Tutti i crediti sospesi** (**Gestione crediti > Elenco sospensioni gestione crediti > Tutti i crediti sospesi**).
Gli ordini cliente di tutte le persone giuridiche vengono inviati alla stesso elenco di sospensioni di gestione crediti, fornendo una visualizzazione centralizzata di tutte le transazioni che richiedono attenzione. Gli utenti vedranno solo le informazioni sulle persone giuridiche a cui hanno accesso.

Un ordine cliente può essere inserito nell'elenco di sospensioni per i seguenti motivi:
1. Il cliente ha una fattura scaduta da un determinato numero di giorni. 
2. L'ordine ha uno stato conto specifico.
3. L'ordine ha termini di pagamento specifici.
4. Il cliente ha un limite di credito scaduto.
5. Il cliente ha un importo scaduto e ha utilizzato una percentuale specifica del proprio limite di credito
6. L'ordine cliente supera un determinato importo.
7. Il cliente ha superato una determinata percentuale del proprio limite di credito.
8. I termini di pagamento differiscono dai termini di pagamento predefiniti per il cliente.
9. Gli sconti di liquidazione differiscono dallo sconto di liquidazione predefinito per il cliente.

Il motivo del blocco viene visualizzato per ciascun ordine cliente nell'elenco di sospensioni. Se ci sono molteplici motivi per la sospensione, il motivo verrà visualizzato come **Multiplo**. È possibile usare il menu **Motivi di blocco** nel riquadro azioni per visualizzare tutti i motivi per cui l'ordine cliente è stato messo in attesa. È anche possibile visualizzare i **Motivi di blocco** in un Dettaglio informazioni.

### <a name="releasing-orders-from-the-hold-list-for-processing"></a>Rilasciare ordini dall'elenco di sospensioni per l'elaborazione

Dopo aver ricercato i motivi della sospensione e averli attenuati, è possibile rilasciare gli ordini cliente per ulteriori elaborazioni.

1) Selezionare una riga nell'elenco di sospensioni. È possibile rilasciare più ordini selezionando più di una riga.
2) Selezionare un **Motivo di rilascio** per l'ordine selezionato per il rilascio.  
3) Immettere una data in **Data revisione** per ogni ordine selezionato per il rilascio.  
4) Selezionare il menu **Rilascio** nel riquadro azioni per rilasciare un ordine. Questo menu sarà disponibile solo dopo aver selezionato le transazioni. L'utente ha a disposizione due opzioni:
 - Selezionare **Con registrazione** per rimuovere la sospensione e registrare il documento utilizzando lo stesso processo di registrazione utilizzato quando è stato messo in attesa. Ad esempio, se la conferma dell'ordine cliente è stata messa in attesa, la conferma dell'ordine cliente verrà completata dopo il rilascio. Verrà visualizzato il modulo di registrazione dell'ordine cliente che consente all'utente di registrare la conferma.
 - Selezionare **Senza registrazione** per rimuovere la sospensione senza eseguire ulteriori elaborazioni. L'ordine cliente può ora registrato manualmente.

### <a name="rejecting-orders-in-the-hold-list"></a>Rifiutare ordini nell'elenco di sospensioni
È possibile utilizzare il menu **Rifiuta** nel riquadro azioni per rifiutare un ordine cliente.
1. Selezionare una riga nell'elenco di sospensioni. È possibile rilasciare più ordini selezionando più di una riga.
2. L'ordine verrà rimosso dall'elenco di sospensioni e l'intestazione dell'ordine cliente verrà aggiornata per mostrare che l'ordine è stato rifiutato.

### <a name="automatically-releasing-credit-management-holds"></a>Rilascio automatico delle sospensioni di gestione crediti
Gli ordini cliente vengono inseriti nell'elenco di sospensioni in base alle regole di blocco. Tuttavia, alcuni motivi delle sospensioni possono cambiare nel tempo se l'ordine cliente rimane nell'elenco di sospensioni per un periodo di tempo. Ad esempio, un cliente può pagare la fattura, liberando il limite di credito. 

È possibile utilizzare il menu **Valuta per rilascio** per esaminare gli ordini cliente nell'elenco di sospensioni e rilasciarli automaticamente se il motivo della sospensione è stato mitigato.
1.  Selezionare il menu **Valuta per rilascio**
2.  Selezionare **Elabora regole di blocco** per esaminare tutti gli ordini cliente. Selezionare **Elabora regole di blocco per righe selezionate** per esaminare solo le righe selezionate.
3. Apparirà un dispositivo di scorrimento in modo da poter selezionare un singolo cliente. Lasciare vuota la casella a discesa Cliente per tutti i clienti. 
4. Quando si fa clic su OK, il processo viene eseguito in background e si può continuare a lavorare su altre attività. Se si seleziona l'elaborazione in batch prima di fare clic su OK, il processo verrà eseguito in batch quando si fa clic su OK. L'elaborazione degli ordini in attesa nell'elenco potrebbe richiedere del tempo, quindi utilizzare Aggiorna per aggiornare lo stato degli ordini. 
5.  Se un motivo di blocco non è più applicabile per un ordine, il motivo di blocco non sarà più considerato valido e un segno di spunta non sarà più visualizzato accanto al motivo quando si visualizzano i motivi di blocco.
6.  Se vengono eliminati tutti i motivi di blocco, un nuovo motivo, **Pronto per il rilascio**, viene aggiunto all'elenco dei motivi di blocco. L'ordine cliente può essere rilasciato automaticamente.
7.  Se il parametro **Rilascio automatico** nella scheda **Credito e riscossioni > Impostazione > Parametri credito e riscossioni > Credito > Rilascio automatico** è impostato su **Con registrazione**, verrà richiesto di registrare utilizzando il modulo di registrazione per il documento che è stato bloccato.
8.  Se il parametro **Rilascio automatico** nella scheda **Credito e riscossioni > Impostazione > Parametri credito e riscossioni > Credito > Rilascio automatico** è impostato su **Senza registrazione**, sarà necessario registrare manualmente l'ordine.

### <a name="credit-management-approval-workflow"></a>Flusso di lavoro di approvazione di gestione crediti

È anche possibile creare **Flussi di lavoro di gestione crediti** per controllare il rilascio dei crediti sospesi. Dopo aver impostato il flusso di lavoro utilizzando la pagina **Gestione crediti > Impostazione > Flussi di lavoro di gestione crediti**, gli ordini contrassegnati per il rilascio o il rifiuto verranno inviati al flusso di lavoro dove devono essere approvati prima di essere rilasciati o rifiutati. 

Se si includono le attività per il rilascio con registrazione o senza registrazione nel flusso di lavoro, l'approvazione del flusso di lavoro rilascerà anche l'ordine cliente. Tuttavia, se si verifica un errore nel processo di rilascio a causa di informazioni mancanti o altre cause, sarà necessario richiamare l'ordine cliente dal flusso di lavoro, risolvere il problema che ha causato l'errore e quindi inviare nuovamente l'ordine al flusso di lavoro.

Se non si includono le attività per il rilascio con registrazione o senza registrazione nel flusso di lavoro, il processo di approvazione del flusso di lavoro consentirà il rilascio manuale dell'ordine cliente una volta completata l'approvazione.

### <a name="forced-credit-hold"></a>Sospensione forzata dei crediti  
  
A volte, potrebbe essere necessario bloccare gli ordini cliente anche se l'ordine non soddisfa i criteri delle regole di blocco. Ad esempio, un responsabile della gestione dei crediti può essere informato di un problema con il cliente non inerente al credito e decidere di mettere in attesa immediatamente gli ordini manualmente fino a quando il problema non viene risolto. È possibile forzare manualmente la messa in attesa di un ordine cliente se si verifica tale situazione.

1. Aprire l'ordine cliente che si desidera mettere in attesa.  
2. Selezionare **Forza sospensione credito** nella scheda **Gestione crediti** del riquadro azioni **Gestione crediti**.
3. Selezionare un valore in **Motivo della sospensione forzata**.
4. Fare clic su **OK**. L'ordine cliente verrà inserito nell'elenco di sospensioni di gestione crediti.

È anche possibile forzare la messa in attesa di più ordini utilizzando la pagina **Gestione crediti > Attività periodiche > Forza sospensione credito**. Ad esempio, è possibile mettere in attesa tutti gli ordini cliente per un cliente specifico.
1. Selezionare un valore in **Motivo della sospensione forzata**. 
2. Fare clic su **Record da includere** per selezionare gli ordini cliente da mettere in attesa. 
3. Fare clic su **OK** per elaborare gli ordini clienti selezionati.

Gli ordini cliente la cui messa in attesa è stata forzata non possono essere elaborati con il flusso di lavoro.

#### <a name="releasing-orders-that-were-added-to-the-credit-management-hold-list-with-a-forced-credit-hold"></a>Rilascio di ordini aggiunti all'elenco di sospensioni di gestione crediti con una sospensione forzata del credito
Gli ordini cliente con un motivo di sospensione forzata non possono essere rilasciati automaticamente. Se la sospensione dell'ordine cliente è stata forzata e si è utilizzato un processo che rilascia automaticamente gli ordini cliente, l'ordine cliente verrà visualizzato come **Pronto per il rilascio** e rimane nell'elenco delle sospensioni. È necessario usare il menu **Rilascio** per rilasciare l'ordine.
 
## <a name="free-text-invoices-orders-and-project-invoice-support-in-credit-management"></a>Fatture a testo libero, ordini e supporto per fatture di progetto in Gestione crediti 
Attualmente Gestione crediti può essere utilizzato solo per gli ordini cliente. Le fatture a testo libero, gli ordini POS e gli ordini servizio clienti utilizzeranno i limiti di credito temporanei e le assicurazioni/garanzie aggiunte per adeguare il limite di credito. Non utilizzeranno le regole di blocco e non verranno inseriti nell'elenco di sospensioni in caso di problemi con il limite di credito.

Non esiste supporto per le fatture di progetto in Gestione crediti.
