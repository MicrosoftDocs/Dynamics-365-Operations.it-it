---
title: Richieste di offerta (RdO)
description: Questo argomento fornisce una panoramica delle richieste di offerta (RdO) emesse dalle organizzazioni quando devono acquistare articoli o servizi e desiderano ricevere offerte competitive da fornitori diversi.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 495e28a5d61d8c0c3ccfbf731e693f2b5e2e7892
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="request-for-quotations-rfqs"></a>Richieste di offerta (RdO)

[!include[banner](../includes/banner.md)]


Questo argomento fornisce una panoramica delle richieste di offerta (RdO) emesse dalle organizzazioni quando devono acquistare articoli o servizi e desiderano ricevere offerte competitive da fornitori diversi. In una richiesta di offerta viene richiesto ai fornitori di fornire i prezzi e i tempi di consegna per le quantità di articoli specificati. È inoltre possibile chiedere ai fornitori di specificare se esistono eventuali spese accessorie, ad esempio i costi di spedizione o se il fornitore offre sconti per grandi ordini o per il pagamento anticipato della fattura fornitore.

Il processo di richiesta di offerta (RdO) riguarda le seguenti attività:

-   Creazione e invio di una richiesta di offerta a uno o più fornitori.
-   Ricezione e registrazione delle risposte alla richiesta di offerta (offerte).
-   Trasferimento di offerte accettate a un ordine fornitore, un contratto di acquisto oppure a una richiesta di acquisto.

Nell'illustrazione riportata di seguito viene fornita una panoramica del processo relativo alla richiesta di offerta.  

[![Processo richiesta di offerta](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)  

È possibile creare una richiesta di offerta da ordini pianificati, da una richiesta di acquisto o da un'immissione manuale. La richiesta di offerta creata è denominata caso RdO e si tratta del documento di base da utilizzare per emettere una richiesta di offerta a ciascun fornitore. Dopo aver preparato il caso RdO e aver aggiunto i fornitori, fare clic su **Invia** nel caso RdO. Verrà generato un giornale di registrazione richieste di offerta per ogni fornitore a cui si invia la richiesta di offerta. È possibile configurare le impostazioni di gestione della stampa per l'azione Invia per stampare un report per ogni fornitore in un archivio o per inviare un report all'indirizzo di posta elettronica di ogni fornitore. Inoltre, il giornale di registrazione di richieste di offerta per ciascun fornitore può essere utilizzato per generare un report da inviare o inviare successivamente a un fornitore. È inoltre possibile configurare l'azione Invio per generare un foglio di risposta che il fornitore può completare.  

Se è necessario modificare una richiesta di offerta dopo averla inviata, è possibile inviarla nuovamente ai fornitori quando è completata.  

Quando si ricevono le offerte, è necessario immetterle nella pagina **Risposte alle richieste di offerta**. Se si seleziona l'opzione **Copia dati nella risposta**, dati diversi, ad esempio la quantità e le date del caso RdO verranno copiati nella risposta. È possibile modificare questi dati in base all'offerta del fornitore.  

Se una seconda iterazione di una risposta è necessaria per un fornitore specifico, fare clic su **Reso** nella pagina **Risposta alla richiesta di offerta**. L'azione di reso genera un nuovo giornale di registrazione e un report che verranno stampati, archiviati e inviati in base alle impostazioni di gestione stampa.  

Se sono stati aggiunti criteri di punteggio al caso RdO, alla risposta alla richiesta di offerta sarà associato un pannello in cui è possibile immettere i punteggi. I punteggi totali verranno visualizzati quando si confrontano le risposte nella pagina **Confronta risposte**, in cui è inoltre possibile confrontare altri dati di risposta, ad esempio il prezzo della riga, la data di consegna e il prezzo totale.  

Dopo aver deciso se considerare un'offerta oppure offerte parziali, è possibile accettarle e rifiutare il resto. Vengono generati giornali di registrazione accettazione, giornali di registrazione rifiuto e report corrispondenti. Questi giornali verranno stampati, archiviati e inviati in base alle impostazioni di gestione della stampa. Quando si accetta un'offerta o si accettano righe specifiche di un'offerta, viene generato un contratto di acquisto o un ordine fornitore oppure viene aggiornata una richiesta di acquisto, a seconda del tipo di acquisto correlato alla richiesta di offerta. È possibile creare un accordo commerciale che è possibile utilizzare successivamente per qualsiasi risposta, indipendentemente dal fatto che siano state accettate o rifiutate.  

Lo stato di una richiesta di offerta viene visualizzato nell'intestazione della richiesta e dipende dallo stato delle righe della richiesta di offerta. Lo status indica il punto fino al quale la richiesta è stata elaborata. Ogni richiesta di offerta dispone di due valori per lo stato: il minimo e il massimo. Lo stato minimo corrisponde allo stato meno avanzato, mentre stato massimo è lo stato più avanzato di qualsiasi riga della richiesta di offerta. Ad esempio, se la fase meno avanzata in una richiesta di offerta è per una riga creata, lo stato minimo per la richiesta di offerta è **Creato**. Se la fase più avanzata in una richiesta di offerta è per una riga inviata ai fornitori, lo stato massimo per la richiesta di offerta è **Inviato**. Gli stati vengono aggiornati automaticamente quando si elabora una richiesta di offerta.  

È possibile visualizzare gli stati minimo e massimo per l'intestazione di una richiesta di offerta nella pagina di elenco **Tutte le richieste di offerta**. È possibile visualizzare gli stati minimo e massimo per una riga di una richiesta di offerta nella scheda **Righe** nella pagina **Richieste di offerta**.  

La sequenza di stati per l'elaborazione di una RdO è la seguente:

1.  **Creato**
2.  **Inviato**
3.  **Ricevuto**
4.  **Accettato**/**Annullato**/**Rifiutato**

Gli stati verranno descritti in modo più dettagliato nelle sezioni successive dell'argomento.

## <a name="setting-up-rfq-functionality"></a>Impostare la funzionalità della richiesta di offerta
Prima di creare un caso RdO, è necessario impostare le informazioni sulla richiesta di offerta nella pagina **Parametri di approvvigionamento**. Quando si crea un caso RdO, è possibile specificare i valori predefiniti che vengono copiati nella richiesta di offerta. È possibile specificare i seguenti valori predefiniti:

-   Tipo di acquisto delle nuove richieste di offerta: **Ordine fornitore** o **Contratto di acquisto**.
-   Impostazioni per data e ora di scadenza.
-   Informazioni di consegna e condizioni di pagamento.
-   Campi che devono essere inclusi nella risposta alla RdO.

È possibile sostituire tali valori per un caso specifico della richiesta di offerta. È inoltre necessario configurare il processo di modifica. Come parte della configurazione, è possibile attivare il blocco dei campi. Quando il blocco dei campi è attivato, un professionista dell'approvvigionamento che desidera modificare una richiesta di offerta deve innanzitutto fare clic su **Crea** nella sezione **Modifica** della scheda **Offerta**. Dopo che la RdO è stata aggiornata con la modifica, il responsabile approvvigionamenti deve completare il processo facendo clic su **Finalizza**. L'azione **Finalizza** genera un messaggio di posta elettronica che notifica ai fornitori della RdO rettificata. Selezionare il modello per la notifica tramite posta elettronica che viene inviata ai fornitori nella pagina **Parametri di approvvigionamento**. Quando viene creato, un modello può includere i seguenti token di sostituzione:

-   %Motivo di restituzione dell'offerta%
-   %Motivo della modifica%
-   %Modifica preparata da%
-   %Società%

I token %Motivo di restituzione dell'offerta% e %Motivo della modifica% vengono sostituiti da testo che il professionista dell'approvvigionamento può immettere quando completa la modifica nella procedura guidata **Modifica**. I valori dei token %Modifica preparata da% e %Società% vengono ottenuti automaticamente dalla richiesta di offerta.  

Se si desidera utilizzare i codici motivo in una risposta alla richiesta di offerta per indicare il motivo per cui un'offerta è stata accettata o rifiutata, è necessario impostarli nella pagina **Motivi fornitore**.  

È possibile configurare l'aspetto dei documenti della richiesta di offerta stampati o archiviati nella pagina **Impostazione moduli** in Approvvigionamento. 

**Nota:** per la configurazione del settore pubblico, eventuali modifiche a una RdO che è già stata inviata richiedono l'utilizzo del processo di modifica. Quando la RdO viene inviata, i campi vengono bloccati, pertanto selezionare **Crea** per utilizzare il processo di modifica come descritto sopra è un passaggio obbligatorio per apportare modifiche alla RdO.
Questo aspetto è controllato dal parametro di blocco dei campi **Blocca RdO quando inviate** in **Parametri di approvvigionamento**. Questo parametro è impostato su **Sì** e per una configurazione del settore pubblico questa è l'impostazione predefinita che non può essere modificata. Ciò significa che mentre il processo di modifica può essere gestito manualmente in una configurazione non del settore pubblico, il processo di gestione delle modifiche in presenza del blocco dei campi dopo l'invio della RdO è obbligatorio per il settore pubblico.

Quando si crea una richiesta di offerta per un ordine fornitore e si aggiunge un articolo di magazzino, viene creata anche un'operazione di magazzino con lo stato in entrata impostato su **Ricevimento offerta**. Solo le righe della richiesta di offerta con questo stato sono considerate quando si utilizza un piano generale per calcolare le forniture. Se si desidera che il piano generale includa le righe della richiesta di offerta come entrata prevista, è necessario configurare questo comportamento nella pianificazione generale.  

Come un responsabile o un addetto acquisti, è possibile creare e gestire i tipi di sollecito per abbinare i requisiti di approvvigionamento per l'organizzazione. Ogni tipo di sollecito può determinare metodi di assegnazione del punteggio. Tali metodi sono costituiti da un gruppo di criteri che possono essere utilizzati quando si valutano le offerte. È necessario impostare tipi di sollecito, metodi di assegnazione dei punteggi e criteri di assegnazione nelle pagine **Tipo di sollecito** e **Metodo di assegnazione del punteggio**.

## <a name="creating-and-sending-an-rfq"></a>Creazione e invio di una richiesta di offerta
Creare una richiesta di offerta, selezionare i fornitori ai quali si desidera fare un'offerta sulla richiesta di offerta, quindi inviare la richiesta di offerta ai fornitori. È possibile utilizzare la gestione stampa per inviare report di richiesta di offerta e report di fogli di risposta alla destinazione preferita.  

È possibile creare una richiesta di offerta per tipo di acquisto **Ordine fornitore** o **Contratto di acquisto**.  

Se la richiesta di offerta viene generata da una richiesta di acquisto, il tipo **Richiesta di acquisto** viene assegnato automaticamente. Non è possibile creare manualmente una richiesta di offerta di tipo **Richiesta di acquisto**. Se la richiesta di offerta è di tipo **Ordine fornitore**:

-   Quando le righe della richiesta di offerta vengono create, le operazioni di magazzino vengono generate con stato di entrata **Ricevimento offerta**.
-   Quando si accetta un'offerta, viene generato un ordine fornitore.

Se la richiesta di offerta è di tipo **Ordine fornitore**:

-   La richiesta di offerta viene utilizzata per un contratto che prevede l'acquisto di una quantità o di un valore specifico di prodotti nel tempo. È necessario selezionare l'intervallo di date applicabile al contratto di acquisto e il nome della persona responsabile della gestione del contratto di acquisto.
-   Quando si accetta un'offerta, viene generato un contratto di acquisto.

È possibile creare una richiesta di offerta da una richiesta di acquisto solo se lo stato della richiesta di acquisto è **In revisione** e l'utente può svolgere l'attività del flusso di lavoro successiva. Le righe della richiesta di acquisto vengono aggiornate automaticamente quando si accettano le righe delle risposte alla richiesta di offerta (offerte) ricevute dai fornitori. Mentre la richiesta di offerta è in corso, non è possibile completare, rifiutare, approvare la richiesta di acquisto o eseguire qualsiasi azione sulla richiesta di acquisto.  

Quando si crea una richiesta di offerta, è possibile selezionare un tipo di sollecito. Il tipo di sollecito determina il set di criteri di assegnazione punteggi per valutare le risposte alla richiesta di offerta.  

È possibile aggiungere un questionario a un caso RdO. Il questionario verrà visualizzato su tutte le risposte dopo aver inviato la richiesta.  

Sono disponibili tre modi per selezionare i fornitori da aggiungere a un caso RdO:

-   Aggiungere i fornitori singolarmente.
-   Ricercare tutti i fornitori che soddisfano criteri specifici.
-   Aggiungere automaticamente tutti i fornitori approvati per le categorie di approvvigionamento utilizzate nelle righe della richiesta di offerta.

Quando il caso RdO è pronto, fare clic su **Invia**. L'azione di invio genera nuovi giornali di registrazione e nuovi report che verranno stampati, archiviati e inviati in base alle impostazioni di gestione stampa.  

Se si selezionano le caselle di controllo **Usa fornitore per ricalcolo prezzi** e **Usa informazioni sugli articoli specifiche del fornitore** nella pagina **Invio richiesta di offerta** dopo aver inviato la richiesta ai fornitori, alcune informazioni specifiche dei fornitori vengono immesse automaticamente. È possibile modificare queste informazioni nella pagina **Risposta alla richiesta di offerta**.  

Nella seguente tabella vengono visualizzati i cambiamenti di stato di una richiesta di offerta quando viene inviata ai fornitori.

|                                    |                              |                                                 |                            |                             |
|------------------------------------|------------------------------|-------------------------------------------------|----------------------------|-----------------------------|
| **Azione**                         | **Stato minimo intestazione RdO** | **Stato massimo intestazione RdO**                   | **Stato minimo riga RdO** | **Stato massimo riga RdO** |
| Creare l'intestazione e la riga RdO.    | Creata                      | Creata                                         | Creata                    | Creata                     |
| Inviare la richiesta di offerta a un fornitore specifico. | Inviato                         | Inviato                                            | Inviato                       | Inviato                        |
| Aggiungere un altro fornitore.                | Creata                      | Inviato (la richiesta di offerta è stata inviata a un solo fornitore). | Creata                    | Inviata                        |
| Inviare la richiesta di offerta al secondo fornitore. | Inviata                         | Inviata                                            | Inviata                       | Inviata                        |

**Nota:** è possibile aggiungere altri fornitori a una richiesta di offerta in qualsiasi momento. Gli stati minimo e massimo verranno modificati per riflettere i nuovi fornitori. Se ad esempio sono state ricevute offerte da tutti i fornitori ed è stata accettata almeno una riga in un'offerta, lo stato minimo dell'intestazione della richiesta di offerta è **Rifiutato** e lo stato massimo è **Accettato**. Se si aggiunge un nuovo fornitore, lo stato minimo di qualsiasi riga è **Creato**. Pertanto lo stato minimo dell'intestazione della richiesta di offerta viene modificato in **Creato** e lo stato massimo rimane **Accettato**.

## <a name="amending-an-rfq"></a>Modifica di una richiesta di offerta
Occasionalmente, è necessario modificare una richiesta di offerta dopo averla inviata. Questa esigenza può verificarsi, ad esempio, se le date di consegna sono state modificate o si desiderano prodotti aggiuntivi o quantità diverse di prodotti. È possibile configurare il processo di modifica in modo che sia più restrittivo o meno restrittivo.  

Se si utilizza il processo di modifica più restrittivo, è necessario fare clic su **Crea** sul caso RdO per avviare una modifica prima di modificare i campi nel caso RdO. Al termine delle modifiche, è necessario fare clic su **Finalizza**. L'utente verrà quindi guidato nel processo di aggiunta di informazioni per il messaggio di posta elettronica inviato per comunicare ai fornitori la modifica. Il report della richiesta di offerta aggiornato, che include una nota delle modifiche, viene automaticamente collegato al messaggio.  

Se si utilizza il processo meno restrittivo delle modifiche, non è necessario creare un le modifiche prima di poter modificare i campi in un caso RdO che è già stato inviato. Tuttavia, è necessario aggiungere manualmente una nota delle modifiche nella richiesta di offerta.

## <a name="receiving-and-registering-rfq-replies"></a>Ricezione e registrazione delle risposte alla richiesta di offerta
Quando si invia una richiesta di offerta, viene generato automaticamente un foglio di risposta. Man mano che si ricevono le risposte (offerte) a una richiesta di offerta, immettere le informazioni relative alla risposta di ciascun fornitore nel modulo Risposta alla richiesta di offerta specifica del fornitore. Se sono state aggiunti criteri di punteggio, è possibile assegnarli alla risposte. È quindi possibile confrontare le offerte dei fornitori classificandole in base a determinati criteri di punteggio, ad esempio il miglior prezzo totale o il miglior tempo di consegna totale.  

Se un questionario è collegato al caso RdO, è necessario immettere manualmente le risposte alle domande nel foglio di risposta.  

Se è necessario immettere righe alternative e il caso RdO lo consente, nella scheda dettaglio **Righe offerte di acquisto** fare clic su **Aggiungi riga**. Immettere le informazioni sul prodotto, ad esempio il numero di articolo o la categoria di approvvigionamento, la quantità, il prezzo e lo sconto.  

Se è stata specificata una risposta ma si richiede una nuova offerta dal fornitore, è possibile inviare nuovamente la RdO. Verranno generati un giornale di registrazione e un report nuovi che sarà possibile utilizzare per richiedere modifiche dal fornitore.  

È possibile visualizzare una panoramica di tutte le richieste di offerta e di tutti i relativi stati nella pagina **Follow-up richiesta di offerta**.  

Nella seguente tabella viene visualizzato il modo in cui la richiesta di offerta cambia quando si ricevono le offerte e si registrano le informazioni nel foglio di risposta.

|                                                |                       |                        |                              |                               |                            |                             |
|------------------------------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Azione**                                     | **Stato offerta minimo** | **Stato offerta massimo** | **Stato minimo intestazione RdO** | **Stato massimo intestazione RdO** | **Stato minimo riga RdO** | **Stato massimo riga RdO** |
| Registrare l'offerta di un fornitore e salvarla.        | Inviato                  | Ricevuto               | Inviato                         | Ricevuto                      | Inviato                       | Ricevuto                    |
| Registrare la seconda offerta di un fornitore e salvarla. | Ricevuto              | Ricevuto               | Ricevuto                     | Ricevuto                      | Ricevuto                   | Ricevuto                    |

**Nota:** se si restituisce un'offerta a un fornitore per una ulteriore negoziazione, lo stato minimo e quello massimo rimangono invariati su **Ricevuto**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Accettazione e rifiuto di offerte e trasferimento di offerte accettate ai documenti downstream

Dopo avere identificato la migliore offerta, ad esempio quella che offre il miglior prezzo totale, accettarla. Lo stato della risposta alla richiesta di offerta specifica del fornitore viene aggiornato in **Accettato**. Quando si accetta l'offerta o le righe specifiche in un'offerta, un ordine fornitore o un contratto di acquisto viene generato automaticamente ed è possibile rifiutare le offerte da altri fornitori.  

Quando si accetta una risposta a una richiesta di offerta di tipo **Richiesta di acquisto**, le righe della richiesta di acquisto vengono aggiornate in base alle seguenti informazioni presenti nelle righe della risposta alla richiesta di offerta:

-   Prezzo unitario
-   Percentuale sconto
-   Importo sconto
-   Spese di acquisto
-   Spese riga
-   Fornitore
-   Numero esterno
-   Descrizione esterna

Nella risposta, è possibile aggiungere un codice motivo per spiegare perché un'offerta è accettata o rifiutata.  

È possibile accettare alcune righe in un'offerta e rifiutarne altre. È inoltre possibile accettare le righe dai fornitori diversi. Notare che se si accettano alcune righe, verrà richiesto di rifiutare tutte le altre. Di conseguenza, se si desidera accettare altre righe, è necessario fare clic su **Annulla** quando si riceve la richiesta.  

Nella seguente tabella viene indicato come cambia lo stato della richiesta di offerta quando si rifiutano le offerte dei fornitori.

|                         |                       |                        |                              |                               |                            |                             |
|-------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Azione**              | **Stato offerta minimo** | **Stato offerta massimo** | **Stato minimo intestazione RdO** | **Stato massimo intestazione RdO** | **Stato minimo riga RdO** | **Stato massimo riga RdO** |
| Accettare una delle offerte. | Ricevuto              | Accettata               | Ricevuto                     | Accettata                      | Ricevuto                   | Accettata                    |
| Rifiutare le altre offerte.  | Rifiutati              | Accettata               | Rifiutati                     | Accettata                      | Rifiutati                   | Accettata                    |






