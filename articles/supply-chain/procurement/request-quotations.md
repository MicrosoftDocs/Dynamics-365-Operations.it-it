---
title: Richieste di offerta (RdO)
description: "In questo argomento è riportata una panoramica relativa alle richieste di offerta (RdO). Le organizzazioni emettono una richiesta di offerta quando devono acquistare articoli o servizi e desiderano ricevere offerte competitive da diversi fornitori."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: 42ab7beb8a269cd37fd9100385bd302e4945c1e0
ms.contentlocale: it-it
ms.lasthandoff: 12/14/2017

---

# <a name="requests-for-quotation-rfqs"></a>Richieste di offerta (RdO)

[!include[banner](../includes/banner.md)]

In questo argomento è riportata una panoramica relativa alle richieste di offerta (RdO). Le organizzazioni emettono una richiesta di offerta quando devono acquistare articoli o servizi e desiderano ricevere offerte competitive da diversi fornitori. In una richiesta di offerta viene richiesto ai fornitori di fornire i prezzi e i tempi di consegna per le quantità di articoli specificati. È inoltre possibile chiedere ai fornitori di specificare se esistono eventuali spese accessorie, ad esempio i costi di spedizione o se il fornitore offre sconti per grandi ordini o per il pagamento anticipato della fattura fornitore.

Il processo RdO comporta le seguenti attività:

1. Creazione e invio di una RdO per uno o più fornitori.
2. Ricezione e registrazione di risposte alla RdO (offerte).
3. Trasferimento delle offerte accettate per un ordine fornitore, un contratto di acquisto oppure a una richiesta di acquisto.

Nell'illustrazione riportata di seguito viene mostrata una panoramica del processo relativo alla richiesta di offerta.

[![Processo RFQ](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

È possibile creare una RdO da ordini pianificati, da una richiesta di acquisto o con un'immissione manuale. L'RdO creata viene definita un caso RdO. In caso RdO è il documento di base utilizzato per emettere un'RdO per ciascun fornitore.

Dopo avere preparato il caso RdO e aggiunto i fornitori, selezionare **Invia** nel caso RdO. Un giornale di registrazione RdO viene generato per ciascun fornitore a cui viene inviata una RdO. È possibile configurare le impostazioni di gestione della stampa per l'azione Invia così da stampare un report per ogni fornitore in un archivio o per inviare un report all'indirizzo di posta elettronica di ogni fornitore. Inoltre, il giornale di registrazione di RdO per ciascun fornitore può essere utilizzato per generare un report da inviare o inviare successivamente a un fornitore. È inoltre possibile configurare l'azione Invio per generare automaticamente un foglio di risposta che il fornitore può completare.

In questo argomento vengono illustrati il processo di gestione delle richieste di offerta quando la collaborazione fornitore non viene utilizzata. Se il sistema è impostato per la collaborazione fornitori, i fornitori possono immettere le offerte direttamente in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Per ulteriori informazioni, vedere [Collaborazione fornitore con i clienti](vendor-collaboration-work-customers-dynamics-365-operations.md).
 
Se è necessario modificare una RdO dopo averla inviata, è possibile inviare l'RdO ai fornitori al termine utilizzando le due azioni di modifica: Crea e Finalizza.

Quando si ricevono le offerte tramite posta elettronica, è necessario immetterle nella pagina **Risposte alle richieste di offerta**. Se si seleziona l'opzione **Copia dati nella risposta**, dati diversi, ad esempio la quantità e le date del caso RdO verranno copiati nella risposta. È possibile modificare questi dati in base all'offerta del fornitore.

Se una seconda iterazione di una risposta è necessaria per un fornitore, selezionare **Reso** nella pagina **Risposta alla richiesta di offerta**. L'azione di reso genera un nuovo giornale di registrazione e un report che verranno stampati, archiviati e inviati in base alle impostazioni di gestione stampa.

Se sono stati aggiunti criteri di punteggio al caso RdO, alla risposta alla richiesta di offerta sarà associato un pannello in cui è possibile immettere i punteggi. I punteggi totali verranno visualizzati quando si confrontano le risposte nella pagina **Confronta risposte**. In questa pagina, è inoltre possibile confrontare altri dati di risposte, ad esempio il prezzo riga, la data di consegna e il prezzo totale.

Dopo aver scelto se considerare un'offerta oppure offerte parziali, è possibile accettarle e rifiutare il resto. I giornali di accettazione, i giornali di rifiuto e i relativi report vengono generati e stampati, archiviati e inviati in base alle impostazioni di gestione della stampa. Quando si accetta un'offerta o si accettano righe specifiche di un'offerta, viene generato un contratto di acquisto o un ordine fornitore oppure viene aggiornata una richiesta di acquisto, a seconda del tipo di acquisto correlato alla RdO. È possibile creare un accordo commerciale che è possibile utilizzare successivamente per qualsiasi risposta, indipendentemente dal fatto che siano state accettate o rifiutate.

Lo stato di una richiesta di offerta viene visualizzato nell'intestazione della richiesta e dipende dallo stato delle righe della RdO. Lo status indica il punto fino al quale l'RdO è stata elaborata. Ogni RdO dispone di due valori per lo stato: il minimo e il massimo. Lo stato minimo corrisponde allo stato meno avanzato, mentre stato massimo è lo stato più avanzato di qualsiasi riga della richiesta di offerta. Ad esempio, se la fase meno avanzata in una richiesta di offerta è per una riga creata, lo stato minimo per la richiesta di offerta è **Creato**. Se la fase più avanzata in una richiesta di offerta è per una riga inviata ai fornitori, lo stato massimo per la richiesta di offerta è **Inviato**. Gli stati vengono aggiornati automaticamente quando si elabora una richiesta di offerta.

È possibile visualizzare gli stati minimo e massimo per l'intestazione di una richiesta di offerta nella pagina di elenco **Tutte le richieste di offerta**. È possibile visualizzare gli stati minimo e massimo per una riga di una richiesta di offerta nella scheda **Righe** nella pagina **Richieste di offerta**.

La sequenza di stati per l'elaborazione di un'RdO è la seguente:

1. **Creato**
2. **Inviato**
3. **Ricevuto**
4. **Accettato**, **Annullato** o **Rifiutato**

Questi stati verranno descritti in modo più dettagliato nelle sezioni successive dell'argomento.

## <a name="setting-up-rfq-functionality"></a>Impostare la funzionalità della richiesta di offerta

Prima di creare un caso RdO, è necessario impostare le informazioni sulla richiesta di offerta nella pagina **Parametri di approvvigionamento**. Quando si crea un caso RdO, è possibile specificare i valori predefiniti che vengono copiati nella richiesta di offerta. È possibile specificare i seguenti valori predefiniti:

- Il tipo di acquisto delle nuove richieste di offerta, ovvero **Ordine fornitore** o **Contratto di acquisto**
- Ora e data di scadenza
- Informazioni di consegna e condizioni di pagamento
- Campi che devono essere inclusi nella risposta alla richiesta di offerta

È possibile sostituire tali valori per un caso specifico della richiesta di offerta.

È inoltre necessario configurare il processo di modifica. Come parte della configurazione, è possibile attivare il blocco dei campi. Quando il blocco dei campi è attivato, un professionista dell'approvvigionamento che desidera modificare una richiesta di offerta deve innanzitutto selezionare **Crea** nella sezione **Modifica** della scheda **Offerta**. Dopo che la RdO è stata aggiornata con la modifica, il responsabile approvvigionamenti deve completare il processo selezionando **Finalizza**. L'azione Finalizza genera un messaggio di posta elettronica che notifica ai fornitori la RdO rettificata.

Nella pagina **Parametri di approvvigionamento**, selezionare il modello da usare per la notifica tramite posta elettronica che viene inviata ai fornitori. Quando viene creato, un modello può includere i seguenti token di sostituzione:

- %Caso RdO%
- %Motivo di restituzione dell'offerta%
- %Motivo della modifica%
- %Modifica preparata da%
- %Società%
- %Nome caso RdO%
- %ExpiryDateTime%
- %Data%

I token %Motivo di restituzione dell'offerta% e %Motivo della modifica% vengono sostituiti da testo che il professionista dell'approvvigionamento può immettere quando completa la modifica nella procedura guidata **Modifica**. I valori dei token %Modifica preparata da% e %Società% vengono ottenuti automaticamente dalla richiesta di offerta. Per impostazione predefinita, il token %Data% viene sostituito dalla data corrente.

Un modello di messaggio di posta elettronica verrà richiesto anche se si annulla una RdO dopo che è stata inviata. Questo modello di messaggio di posta elettronica viene utilizzato per inviare la notifica di annullamento ai contatti del fornitore. Il modello deve essere selezionato nella pagina **Parametri di approvvigionamento**. Quando viene creato, il modello può includere i seguenti token di sostituzione:

- %Motivo dell'annullamento%
- %Caso RdO% 
- %RdO annullata da%
- %Società%
- %Nome caso RdO%
- %Data%

Il token %Motivo dell'annullamento% viene sostituito da testo che il professionista di approvvigionamento può immettere tramite la procedura guidata **Annullamento**. Per impostazione predefinita, il token %Data% viene sostituito dalla data corrente.

Se si desidera utilizzare i codici motivo in una risposta alla richiesta di offerta per indicare il motivo per cui un'offerta è stata accettata o rifiutata, è necessario impostarli nella pagina **Motivi fornitore**.

È possibile configurare l'aspetto dei documenti della RdO stampati o archiviati nella pagina **Impostazione moduli** in Approvvigionamento.

> [!NOTE]
> Per la configurazione del settore pubblico, eventuali modifiche a una RdO che è già stata inviata richiedono l'utilizzo del processo di modifica. Quando viene inviata una RdO, i campi risultano bloccati. Pertanto, per apportare modifiche alla RdO, è necessario selezionare **Creare** per avviare il processo di modifica, come descritto in precedenza. Questo comportamento di blocco è controllato dall'opzione **Blocca RdO quando inviate** in **Parametri di approvvigionamento**. Per impostazione predefinita, questo parametro è impostato su **Sì** e per una configurazione del settore pubblico questa è l'impostazione predefinita che non può essere modificata. Di conseguenza, anche se il processo di modifica può essere gestito manualmente in una configurazione non del settore pubblico, deve essere utilizzato per una configurazione settore pubblico.

Quando si crea una richiesta di offerta per un ordine fornitore e si aggiunge un articolo di magazzino, viene creata anche un'operazione di magazzino con lo stato in entrata impostato su **Ricevimento offerta**. Solo le righe della richiesta di offerta con questo stato sono considerate quando si utilizza un piano generale per calcolare le forniture. Se si desidera che il piano generale includa le righe della richiesta di offerta come entrata prevista, è necessario configurare questo comportamento nella pianificazione generale.

Un responsabile o un addetto acquisti può creare e gestire i tipi di sollecito per abbinare i requisiti di approvvigionamento dell'organizzazione. Ogni tipo di sollecito può essere associato a un metodo di punteggio. Tali metodi sono costituiti da un gruppo di criteri che possono essere utilizzati quando si valutano le offerte. È necessario impostare tipi di sollecito, metodi di assegnazione dei punteggi e criteri di assegnazione nelle pagine **Tipo di sollecito** e **Metodo di assegnazione del punteggio**.

## <a name="creating-and-sending-an-rfq"></a>Creazione e invio di una richiesta di offerta

Creare una richiesta di offerta, selezionare i fornitori ai quali si desidera fare un'offerta sulla richiesta di offerta, quindi inviare la richiesta di offerta ai fornitori. È possibile utilizzare la gestione della stampa per inviare report di richiesta di offerta e report di fogli di risposta alla destinazione preferita.

È possibile creare una RdO per tipo di acquisto **Ordine fornitore** o **Contratto di acquisto**.

Se la RdO è di tipo **Ordine fornitore**, il comportamento è il seguente:

- Quando le righe della richiesta di offerta vengono create, le operazioni di magazzino vengono generate con stato di entrata **Ricevimento offerta**.
- Quando si accetta un'offerta, viene generato un ordine fornitore.

Se la RdO è di tipo **Contratto di acquisto**, il comportamento è il seguente:

- La richiesta di offerta viene utilizzata per un contratto che prevede l'acquisto di una quantità o di un valore specifico di prodotti nel tempo. È necessario selezionare l'intervallo di date applicabile al contratto di acquisto e il nome della persona responsabile della gestione del contratto di acquisto.
- Quando si accetta un'offerta, viene generato un contratto di acquisto.

Se la richiesta di offerta viene generata da una richiesta di acquisto, il tipo **Richiesta di acquisto** viene assegnato automaticamente. Non è possibile creare manualmente una richiesta di offerta di tipo **Richiesta di acquisto**.

È possibile creare una Contratto di acquisto da una richiesta di acquisto solo se lo stato della richiesta di acquisto è **In revisione** e l'utente può svolgere l'attività del flusso di lavoro successiva. Le righe della richiesta di acquisto vengono aggiornate automaticamente quando si accettano le righe delle risposte alla RdO (offerte) ricevute dai fornitori. Mentre la richiesta di offerta è in corso, non è possibile completare, rifiutare, approvare la richiesta di acquisto o eseguire qualsiasi azione sulla richiesta di acquisto.

Quando si crea una RdO, è possibile selezionare un tipo di sollecito. Il tipo di sollecito determina il set di criteri di assegnazione punteggi per valutare le risposte alla richiesta di offerta.

È possibile aggiungere un questionario a un caso RdO. Il questionario verrà visualizzato su tutte le risposte dopo aver inviato la richiesta.

Sono disponibili tre modi per selezionare i fornitori da aggiungere a un caso RdO:

- Aggiungere i fornitori singolarmente.
- Ricercare tutti i fornitori che soddisfano criteri specifici.
- Aggiungere automaticamente tutti i fornitori approvati per le categorie di approvvigionamento utilizzate nelle righe della richiesta di offerta.

Quando il caso RdO è pronto, selezionare **Invia**. L'azione di invio genera nuovi giornali di registrazione e nuovi report che verranno stampati, archiviati e inviati in base alle impostazioni di gestione stampa.

Se si impostano **Usa fornitore per ricalcolo prezzi** e **Usa informazioni sugli articoli specifiche del fornitore** su **Sì** nella pagina **Invio richiesta di offerta** dopo aver inviato la RdO ai fornitori, alcune informazioni specifiche dei fornitori vengono immesse automaticamente. È possibile modificare queste informazioni nella pagina **Risposta alla richiesta di offerta**.

Nella seguente tabella vengono visualizzati i cambiamenti di stato di una richiesta di offerta quando viene inviata ai fornitori.

| Azione                             | Stato minimo intestazione RdO | Stato massimo intestazione RdO                        | Stato minimo riga RdO | Stato massimo riga RdO |
|------------------------------------|--------------------------|--------------------------------------------------|------------------------|-------------------------|
| Creare l'intestazione e la riga RdO.    | Creata                  | Creata                                          | Creata                | Creata |
| Inviare la richiesta di offerta a un fornitore specifico. | Inviato                     | Inviato                                             | Inviato                   | Inviato |
| Aggiungere un altro fornitore.                | Creata                  | Inviato (la richiesta di offerta è stata inviata a un solo fornitore). | Creata                | Inviato |
| Inviare la richiesta di offerta al secondo fornitore. | Inviato                     | Inviato                                             | Inviato                   | Inviato |

> [!NOTE]
> È possibile aggiungere altri fornitori a una RdO in qualsiasi momento. Gli stati massimo e minimo verranno modificati per riflettere i fornitori aggiunti. Se ad esempio sono state ricevute offerte da tutti i fornitori ed è stata accettata almeno una riga in un'offerta, lo stato minimo dell'intestazione della richiesta di offerta è **Rifiutato** e lo stato massimo è **Accettato**. Se si aggiunge un nuovo fornitore, lo stato minimo di qualsiasi riga è **Creato**. Pertanto lo stato minimo dell'intestazione della RdO viene aggiornato in **Creato** ma lo stato massimo rimane **Accettato**.

## <a name="amending-an-rfq"></a>Modifica di una richiesta di offerta

Occasionalmente, è necessario modificare una richiesta di offerta dopo averla inviata. Potrebbe essere necessario modificare una RdO, ad esempio, se le date di consegna sono state modificate o si desiderano prodotti aggiuntivi o quantità diverse di prodotti. È possibile configurare il processo di modifica in modo che sia più restrittivo o meno restrittivo.

Se si configura il processo di modifica in modo che risulti più restrittivo, prima di poter modificare i campi in un caso RdO che è già stato inviato, è necessario selezionare **Crea** nel caso RdO per avviare una modifica. Al termine delle modifiche, è necessario selezionare **Finalizza**. L'utente viene quindi guidato nel processo di aggiunta di informazioni per il messaggio di posta elettronica inviato per comunicare ai fornitori la modifica. Il report della RdO aggiornato, che include una nota delle modifiche, viene automaticamente collegato al messaggio.

Se si configura il processo meno restrittivo delle modifiche, non è necessario selezionare **Crea** prima di poter modificare i campi in un caso RdO che è già stato inviato. Tuttavia, è necessario aggiungere manualmente una nota delle modifiche nella RdO e inviare di nuovo il caso. Tenere presente che tale approccio può essere utilizzato solo se nessuna delle risposte (Offerte) è stata modificata. Se è stata specificata una risposte ma non ha stato **Ricevuta**, il pulsante **Invia** non sarà disponibile. In questo caso, è necessario selezionare **Crea** e **Finalizza**, come nel processo più restrittivo. La risposta viene reimpostata per riflettere le modifiche nel caso RdO. 

Se i fornitori utilizzano l'interfaccia di collaborazione fornitore per immettere le offerte, è necessario utilizzare sempre il processo di modifica per informare i fornitori delle modifiche al caso RdO. Questo requisito aiuta a prevenire la situazione in cui i venditori fanno offerte per una richiesta RdO obsoleta mentre la loro offerta è in corso. Per ulteriori informazioni sulle funzionalità di collaborazione fornitore, vedere [Collaborazione fornitore con i fornitori esterni](vendor-collaboration-work-external-vendors.md). 

Se si desidera invitare altri fornitori a fare un'offerta e non sono state apportate modifiche al caso RdO, è possibile utilizzare il pulsante **Invia**. I fornitori aggiunti verranno visualizzati nella pagina **Invia** e riceveranno un invito di posta elettronica.

## <a name="receiving-and-registering-rfq-replies"></a>Ricezione e registrazione delle risposte alla richiesta di offerta

Quando si invia una richiesta di offerta, viene generato automaticamente un foglio di risposta. Man mano che si ricevono le risposte (offerte) a una richiesta di offerta, immettere le informazioni relative alla risposta di ciascun fornitore nel modulo Risposta alla richiesta di offerta specifica del fornitore. Se sono state aggiunti criteri di punteggio, è possibile assegnarli alle risposte. È quindi possibile confrontare le offerte dei fornitori classificandole in base a determinati criteri di punteggio, ad esempio il miglior prezzo totale o il miglior tempo di consegna totale.

Se un questionario è collegato al caso RdO, è necessario immettere manualmente le risposte alle domande nel foglio di risposta.

È inoltre possibile immettere righe alterne, se il caso RdO consente le righe alterne. Nella Scheda dettaglio **Righe offerte di acquisto** selezionare **Aggiungi riga**. Immettere le informazioni sul prodotto, ad esempio il numero di articolo o la categoria di approvvigionamento, la quantità, il prezzo e lo sconto.

Se è stata specificata una risposta ma si richiede una nuova offerta dal fornitore, è possibile inviare nuovamente la RdO. Verranno generati un giornale di registrazione e un report nuovi, che sarà possibile utilizzare per richiedere modifiche dal fornitore.

È possibile visualizzare una panoramica di tutte le richieste di offerta e di tutti i relativi stati nella pagina **Follow-up richiesta di offerta**.

Nella seguente tabella viene visualizzato il modo in cui la RdO cambia quando si ricevono le offerte e si registrano le informazioni nel foglio di risposta.

| Azione                                         | Stato offerta minimo | Stato offerta massimo | Stato minimo intestazione RdO | Stato massimo intestazione RdO | Stato minimo riga RdO | Stato massimo riga RdO |
|------------------------------------------------|-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Registrare l'offerta di un fornitore e salvarla.        | Inviato              | Ricevuti           | Inviato                     | Ricevuti                  | Inviato                   | Ricevuti |
| Registrare la seconda offerta di un fornitore e salvarla. | Ricevuti          | Ricevuti           | Ricevuti                 | Ricevuti                  | Ricevuti               | Ricevuto |

> [!NOTE]
> Se si restituisce un'offerta a un fornitore per una ulteriore negoziazione, lo stato minimo e quello massimo rimangono invariati su **Ricevuto**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Accettazione e rifiuto di offerte e trasferimento di offerte accettate ai documenti downstream

Dopo avere identificato la migliore offerta, ad esempio quella che offre il miglior prezzo totale, accettarla. È possibile accettare alcune righe in un'offerta e rifiutarne altre. È inoltre possibile accettare le righe dai fornitori diversi. Notare che se si accettano alcune righe, verrà richiesto di rifiutare tutte le altre. Di conseguenza, se si desidera accettare altre righe, è necessario selezionare **Annulla** quando si riceve la richiesta. Lo stato della risposta RdO per ogni fornitore da cui si accettano offerte o righe viene aggiornato a **Accettato**. 

Quando si accetta l'offerta o le righe specifiche in un'offerta, un ordine fornitore o un contratto di acquisto viene generato automaticamente. È quindi possibile rifiutare le offerte da tutti gli altri fornitori.

Nella risposta, è possibile aggiungere un codice motivo per spiegare perché un'offerta è accettata o rifiutata.

Quando si accetta una risposta a una richiesta di offerta di tipo **Richiesta di acquisto**, le righe della richiesta di acquisto vengono aggiornate in base alle seguenti informazioni presenti nelle righe della risposta alla richiesta di offerta:

- Prezzo unitario
- Percentuale sconto
- Importo sconto
- Spese di acquisto
- Spese riga
- Fornitore
- Numero esterno
- Descrizione esterna

Nella seguente tabella viene indicato come cambia lo stato della richiesta di offerta quando si rifiutano le offerte dei fornitori.

| Azione                      | Stato offerta minimo | Stato offerta massimo | Stato minimo intestazione RdO | Stato massimo intestazione RdO | Stato minimo riga RdO | Stato massimo riga RdO |
|-------------------------    |-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Accettare una delle offerte.     | Ricevuti          | Accettate           | Ricevuti                 | Accettate                  | Ricevuti               | Accettate |
| Rifiutare tutte le altre offerte.  | Rifiutato          | Accettate           | Rifiutato                 | Accettate                  | Rifiutato               | Accettata |

