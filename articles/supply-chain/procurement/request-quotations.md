---
title: Panoramica delle richieste di offerta (RdO)
description: In questo argomento è riportata una panoramica relativa alle richieste di offerta (RdO). Le organizzazioni emettono una richiesta di offerta quando devono acquistare articoli o servizi e desiderano ricevere offerte competitive da diversi fornitori.
author: mkirknel
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage, BOMExpandPurchRFQ
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eedf6b08ef9a4b7f164db60433dd16922a8ec807
ms.sourcegitcommit: 97d4a9bd442fe20f90605d8154c3a947c7645b37
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "3895622"
---
# <a name="requests-for-quotation-rfqs-overview"></a>Panoramica delle richieste di offerta (RdO)

[!include [banner](../includes/banner.md)]

In questo argomento è riportata una panoramica relativa alle richieste di offerta (RdO). Le organizzazioni emettono una richiesta di offerta quando devono acquistare articoli o servizi e desiderano ricevere offerte competitive da diversi fornitori. In una richiesta di offerta viene richiesto ai fornitori di fornire i prezzi e i tempi di consegna per le quantità di articoli specificati.
È inoltre possibile chiedere ai fornitori di specificare se esistono eventuali spese accessorie, ad esempio i costi di spedizione o se il fornitore offre sconti per grandi ordini o per il pagamento anticipato della fattura fornitore.

Il processo RdO comporta le seguenti attività:

1.  Creazione e invio di una RdO per uno o più fornitori.

2.  Ricezione e registrazione di offerte (risposte alla RdO).

3.  Trasferimento delle offerte accettate per un ordine fornitore, un contratto di acquisto oppure a una richiesta di acquisto.

Nell'illustrazione riportata di seguito viene mostrata una panoramica del processo relativo alla richiesta di offerta.

[![Processo RFQ](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

È possibile creare un caso RdO da ordini pianificati, da una richiesta di acquisto o con un'immissione manuale. In caso RdO è il documento di base utilizzato per emettere un'RdO per ciascun fornitore.+

Dopo che si prepara il caso RdO e aggiungere i fornitori, selezionare **Invia** (**Invia e pubblica** per il settore pubblico) nel caso RdO. Un giornale di registrazione RdO viene generato per ciascun fornitore a cui viene inviata una RdO. È possibile configurare le opzioni di stampa per l'azione Invia così da stampare un report per ogni fornitore in un archivio o per inviare un report all'indirizzo di posta elettronica di ogni fornitore. Inoltre, il giornale di registrazione di RdO per ciascun fornitore può essere utilizzato per generare un report da inviare o inviare successivamente a un fornitore. È inoltre possibile configurare l'azione Invio per generare automaticamente un foglio di risposta che il fornitore può completare.

In questo argomento vengono illustrati il processo di gestione delle richieste di offerta quando la collaborazione fornitore non viene utilizzata. Se il sistema è impostato per la collaborazione fornitori, i fornitori possono immettere le offerte direttamente in Supply Chain Management. Per ulteriori informazioni, vedere [Collaborazione fornitore con i clienti](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations) e [Collaborazione fornitore con i fornitori esterni](vendor-collaboration-work-external-vendors.md).

Se è necessario modificare una RdO dopo averla inviata, è possibile inviare l'RdO ai fornitori al termine utilizzando le due azioni di modifica: Crea e Finalizza.+

Quando si ricevono le offerte tramite posta elettronica, è possibile gestirle tramite la pagina **Richieste di offerta**.

Se una seconda iterazione di una risposta è necessaria da un fornitore, selezionare **Reso** nella pagina **Richiesta di offerta**. L'azione di reso genera un nuovo giornale di registrazione e un report che verranno stampati, archiviati e inviati in base alle impostazioni di stampa.

Se sono stati aggiunti criteri di punteggio al caso RdO, alla richiesta di offerta sarà associato un riquadro in cui è possibile immettere i punteggi. I punteggi totali verranno visualizzati nella RdO quando si confrontano le risposte nella pagina **Confronta risposte**. Nella pagina **Confronta risposte**, è inoltre possibile confrontare altri dati di risposte, ad esempio il prezzo riga, la data di consegna e il prezzo totale.

Dopo aver scelto un'offerta o una serie di righe in un'offerta, è possibile accettare alcune o tutte le righe e rifiutare il resto. I giornali di accettazione, i giornali di rifiuto e i relativi report vengono generati e stampati, archiviati e inviati in base alle impostazioni di stampa. Quando si accetta un'offerta o si accettano righe specifiche di un'offerta, viene generato un contratto di acquisto o un ordine fornitore oppure viene aggiornata una richiesta di acquisto, a seconda del tipo di acquisto correlato alla RdO. È possibile creare un accordo commerciale che è possibile utilizzare successivamente per qualsiasi risposta, indipendentemente dal fatto che siano state accettate o rifiutate.

Un caso RdO ha due stati: minimo e massimo che è possibile visualizzare nella pagina elenco per **Tutte le richieste di offerta**. Lo stato minimo corrisponde allo stato meno avanzato del caso RdO, mentre stato massimo è lo stato più avanzato di qualsiasi riga del caso RdO. Ad esempio, si supponga che un caso di RdO con tre righe venga inviato a due fornitori, quindi ci saranno due RdO ciascuna con tre righe. Tutte le righe hanno stato **Inviata**. Ora viene immessa un'offerta da uno dei fornitori e le righe RdO ottengono lo stato **Ricevuta**. Ciò significa che delle tre righe del caso RdO hanno tutte stato **Inviata** per una RdO e stato **Ricevuta** per un'altra RdO. Lo stato minimo sarà quindi **Inviata** e lo stato massimo **Ricevuta**.

Questi stati verranno descritti in modo più dettagliato nelle sezioni successive dell'argomento.

## <a name="setting-up-rfq-functionality"></a>Impostare la funzionalità della richiesta di offerta

Prima di creare un caso RdO, è necessario impostare le informazioni sulla richiesta di offerta nella pagina **Parametri di approvvigionamento**. Quando si crea un caso RdO, è possibile specificare i valori predefiniti che vengono copiati nella richiesta di offerta. È possibile specificare i seguenti valori predefiniti:

-   Il tipo di acquisto delle nuove richieste di offerta, ovvero **Ordine fornitore** o **Contratto di acquisto**

-   Lo scostamento dell'ora e della data di scadenza rispetto al giorno in cui è stato creato il caso RdO

-   Il tipo di sollecito, che può impostare come predefinito un metodo di punteggio specifico per il caso RdO

-   Informazioni di consegna e condizioni di pagamento

-   Campi che devono essere inclusi nell'offerta

È possibile sostituire tali valori per un caso specifico della richiesta di offerta.

È inoltre necessario configurare il processo di modifica. Come parte della configurazione, è possibile attivare il blocco dei campi. Quando il blocco dei campi è attivato, un professionista dell'approvvigionamento che desidera modificare una richiesta di offerta deve innanzitutto selezionare **Crea** nella sezione **Modifica** della scheda **Offerta** nel caso RdO. Quindi, dopo che il caso RdO è stato aggiornato con la modifica, il responsabile approvvigionamenti deve completare il processo selezionando **Finalizza**. L'azione Finalizza genera un messaggio di posta elettronica che notifica ai fornitori la RdO rettificata.

Nella pagina **Parametri di approvvigionamento**, selezionare il modello da usare per la notifica tramite posta elettronica che viene inviata ai fornitori. Quando viene creato in **Modelli di messaggio di posta elettronica**, un modello può includere i seguenti token di sostituzione:

-   %Caso RdO%

-   %Motivo di restituzione dell'offerta%

-   %Motivo della modifica%

-   %Modifica preparata da%

-   %Società%

-   %Nome caso RdO%

-   %Ora e data di scadenza%

-   %Data%

I token %Motivo di restituzione dell'offerta% e %Motivo della modifica% vengono sostituiti da testo che il professionista dell'approvvigionamento può immettere quando completa la modifica nella procedura guidata **Modifica**. I valori dei token %Modifica preparata da% e %Società% vengono ottenuti automaticamente dalla richiesta di offerta. Per impostazione predefinita, il token %Data% viene sostituito dalla data corrente.

Se si desidera annullare una RdO dopo che è stata inviata, è possibile farlo dal caso RdO. Per l'annullamento, è necessario un modello di messaggio di posta elettronica per inviare la notifica di annullamento ai contatti del fornitore. Il modello deve essere selezionato nella pagina **Parametri di approvvigionamento**. Quando viene creato, il modello può includere i seguenti token di sostituzione:

-   %Motivo dell'annullamento%

-   %Caso RdO%

-   %RdO annullata da%

-   %Società%

-   %Nome caso RdO%

-   %Data%

Il token %Motivo dell'annullamento% viene sostituito da testo che il professionista di approvvigionamento può immettere tramite la procedura guidata **Annullamento**. Per impostazione predefinita, il token %Data% viene sostituito dalla data corrente.

Se si desidera utilizzare i codici motivo in un'offerta per indicare il motivo per cui è stata accettata o rifiutata, è necessario impostarli nella pagina **Motivi fornitore**.

È possibile configurare l'aspetto dei documenti della RdO stampati o archiviati nella pagina **Impostazione moduli** in Approvvigionamento.

> [!NOTE]
> Per la configurazione del settore pubblico, eventuali modifiche a una RdO che è già stata inviata richiedono l'utilizzo del processo di modifica. Quando viene inviata una RdO, i campi risultano bloccati.
Pertanto, per apportare modifiche alla RdO, è necessario selezionare **Creare** per avviare il processo di modifica, come descritto in precedenza. Questo comportamento di blocco è controllato dall'opzione **Blocca RdO quando inviate** in **Parametri di approvvigionamento**. Per impostazione predefinita, questo parametro è impostato su **Sì** e per una configurazione del settore pubblico questa è l'impostazione predefinita che non può essere modificata. Di conseguenza, anche se il processo di modifica può essere gestito manualmente in una configurazione non del settore pubblico, deve essere utilizzato per una configurazione settore pubblico.

Quando si crea un caso RdO del tipo ordine fornitore e si aggiunge un articolo di magazzino alla RdO, viene creata anche una transazione di magazzino con lo stato in entrata impostato su **Ricevimento offerta**. Solo le righe del caso RdO con questo stato sono considerate quando si utilizza un piano generale per calcolare le forniture. Se si desidera che il piano generale includa le righe del caso RdO come entrata prevista, è necessario configurare questo comportamento nella pianificazione generale.

Un responsabile o un addetto acquisti può creare e gestire i tipi di sollecito per abbinare i requisiti di approvvigionamento dell'organizzazione. Ogni tipo di sollecito può essere associato a un metodo di punteggio. Tali metodi sono costituiti da un gruppo di criteri che possono essere utilizzati quando si valutano le offerte. È necessario impostare tipi di sollecito, metodi di assegnazione dei punteggi e criteri di assegnazione nelle pagine **Tipo di sollecito** e **Metodo di assegnazione del punteggio**.

## <a name="creating-and-sending-an-rfq"></a>Creazione e invio di una richiesta di offerta

Creare un caso RdO, selezionare i fornitori ai quali si desidera fare un caso RdO, quindi inviare la RdO ai fornitori. È possibile utilizzare le impostazioni di stampa per inviare report di richiesta di offerta e report di fogli di risposta alla destinazione preferita.

È possibile creare manualmente un caso RdO per tipo di acquisto **Ordine fornitore** o **Contratto di acquisto**.

Se il caso RdO è di tipo **Ordine fornitore**, si verifica il seguente comportamento che devia da altri tipi di casi RdO:

-   Quando le righe del caso RdO vengono create, le operazioni di magazzino vengono generate con stato di entrata **Ricevimento offerta**.

-   Quando si accetta un'offerta, viene generato un ordine fornitore.

Se il caso RdO è di tipo **Contratto di acquisto**, si verifica il seguente comportamento che devia da altri casi RdO:

-   Il caso RdO viene utilizzato per un contratto che prevede l'acquisto di una quantità o di un valore specifico di prodotti nel tempo. È necessario selezionare l'intervallo di date applicabile al contratto di acquisto e il nome della persona responsabile della gestione del contratto di acquisto.

-   Quando si accetta un'offerta, viene generato un contratto di acquisto.

Se il caso RdO viene generato da una richiesta di acquisto, il tipo **Richiesta di acquisto** viene assegnato automaticamente. Non è possibile creare manualmente un caso RdO di tipo **Richiesta di acquisto**.

È possibile creare una Contratto di acquisto da un caso RdO solo se lo stato della richiesta di acquisto è **In revisione** e l'utente può svolgere l'attività del flusso di lavoro successiva. Le righe della richiesta di acquisto vengono aggiornate automaticamente quando si accettano le righe delle offerte (risposte alla RdO) ricevute dai fornitori. Non è possibile completare, rifiutare, approvare o eseguire altre azioni sulla richiesta di acquisto fino a quando la riga della richiesta non viene aggiornata con una riga RdO accettata o il caso RdO viene annullato.

Quando si crea un caso RdO, è possibile selezionare un tipo di sollecito. Il tipo di sollecito determina il set di criteri di assegnazione punteggi per valutare le risposte al caso RdO.

È possibile aggiungere un questionario a un caso RdO. Il questionario verrà visualizzato su tutte le risposte alla RdO dopo aver inviato la richiesta. Il completamento del questionario è un'attività obbligatoria affinché l'offerta possa essere inviata.


Sono disponibili tre modi per selezionare i fornitori da aggiungere a un caso RdO:

- Aggiungere i fornitori singolarmente.
- Ricercare tutti i fornitori che soddisfano criteri specifici.
- Aggiungere automaticamente tutti i fornitori approvati per le categorie di approvvigionamento utilizzate nelle righe del caso RdO.

Quando il caso RdO è pronto, selezionare **Invia**. L'azione di invio genera nuovi giornali di registrazione e nuovi report che verranno stampati, archiviati e inviati in base alle impostazioni di stampa.

Se si impostano **Usa fornitore per ricalcolo prezzi** e **Usa informazioni sugli articoli specifiche del fornitore** su **Sì** nella pagina **Invio richiesta di offerta** dopo aver inviato la RdO a un fornitore, alcune informazioni specifiche dei fornitori vengono immesse automaticamente nella RdO per quel fornitore.


## <a name="amending-an-rfq-case"></a>Modifica di un caso RdO

Occasionalmente, è necessario modificare un caso RdO dopo averlo inviato. Potrebbe essere necessario modificare un caso RdO, ad esempio, se le date di consegna sono state modificate o si desiderano prodotti aggiuntivi o quantità diverse di prodotti. È possibile configurare il processo di modifica in modo che sia più restrittivo o meno restrittivo.

Se si configura il processo di modifica in modo che risulti più restrittivo, prima di poter modificare i campi in un caso RdO che è già stato inviato, è necessario selezionare **Crea** nel caso RdO per avviare una modifica. Al termine delle modifiche, è necessario selezionare **Finalizza**. L'utente viene quindi guidato nel processo di aggiunta di informazioni per il messaggio di posta elettronica inviato per comunicare ai fornitori la modifica. Il report della RdO aggiornato, che include una nota delle modifiche, viene automaticamente collegato al messaggio.

Se si configura il processo meno restrittivo delle modifiche, non è necessario selezionare **Crea** prima di poter modificare i campi in un caso RdO che è già stato inviato. Tuttavia, è necessario aggiungere manualmente una nota delle modifiche nella RdO e inviare di nuovo il caso. Tenere presente che tale approccio può essere utilizzato solo se nessuna delle risposte (Offerte) è stata modificata. Se è stata specificata una risposte ma non ha stato **Ricevuta**, il pulsante **Invia** non sarà disponibile. In questo caso, è necessario selezionare **Crea** e **Finalizza**, come nel processo più restrittivo. La risposta viene reimpostata per riflettere le modifiche nel caso RdO.

Se i fornitori utilizzano l'interfaccia di collaborazione fornitore per immettere le offerte, è necessario utilizzare sempre il processo di modifica per informare i fornitori delle modifiche al caso RdO. Questo processo aiuta a prevenire la situazione in cui i venditori fanno offerte per una richiesta RdO obsoleta mentre la loro offerta è in corso. Per ulteriori informazioni sulle funzionalità di collaborazione fornitore, vedere [Collaborazione fornitore con i fornitori esterni](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-external-vendors).

Se si desidera invitare altri fornitori a fare un'offerta e non sono state apportate modifiche al caso RdO, è possibile utilizzare il pulsante **Invia**. I fornitori aggiunti verranno visualizzati nella pagina **Invia** e riceveranno un invito di posta elettronica.


## <a name="receiving-and-registering-rfq-replies"></a>Ricezione e registrazione delle risposte alla richiesta di offerta

Quando si invia una richiesta di offerta, viene generato automaticamente un foglio di risposta. Quando si ricevono le offerte in una RdO, è necessario immetterle tramite la pagina **Richiesta di offerta** facendo clic sull'azione **Modifica risposta RdO**. In questo modo sarà possibile immettere informazioni di offerta in un modulo dedicato di offerta. Inizialmente, il campo **Avanzamento risposta** sarà **Non avviata**. Quando si fa clic su **Modifica risposta RdO** lo stato di avanzamento diventa **Aggiornamento in corso dell'acquirente** fino all'invio dell'offerta. Fare clic su **Invia** dopo avere immesso le informazioni di offerta. Lo stato di avanzamento della risposta viene modificato in **Inviata dall'acquirente**. Analogamente, con la collaborazione fornitore attivata, **Avanzamento risposta** viene aggiornato ma mano che il fornitore interagisce con l'offerta. Lo stato quindi viene modificato da **Aggiornamento in corso del fornitore** a **Inviata dal fornitore**. Quando l'offerta viene inviata, viene creato un giornale di registrazione come **Ricevuta**. La risposta (offerta) deve essere presentata per essere registrata come ricevuta e solo successivamente può essere ulteriormente elaborata come accettata o rifiutata.

Se è necessario aggiornare l'offerta, è necessario effettuare lo stesso processo come sopra e ripetere l'invio.

Si noti che la modifica del modulo **Richiesta di offerta** è consentita solo per informazioni relative all'elaborazione dell'offerta, non per l'immissione dell'offerta. Per immettere o modificare l'offerta, fare clic su **Modifica risposta RdO**.

Quando si immettono le informazioni per l'offerta, se il caso RdO consente righe alternative, è possibile aggiungere righe alternative per le righe che contengono una sola categoria di approvvigionamento e nessun articolo catalogo specificato. Fare clic su **Aggiungi alternativa** per aggiungere righe alternativa.

Se è stata specificata una risposta ma si richiede una nuova offerta dal fornitore, è possibile restituire la RdO. Un nuovo giornale di registrazione e un report vengono generati, che possono essere inviati al fornitore.

È possibile visualizzare una panoramica di tutte le richieste di offerta e di tutti i relativi stati: **Inviata, Ricevuta, Accettata, Rifiutata, Annullata, Declinata** nella pagina **Follow-up richiesta di offerta**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Accettazione e rifiuto di offerte e trasferimento di offerte accettate ai documenti downstream

Dopo avere identificato la migliore offerta, ad esempio quella che offre il miglior prezzo totale, accettarla. È possibile accettare alcune righe in un'offerta e rifiutarne altre.
È inoltre possibile accettare le righe dai fornitori diversi. Notare che se si accettano alcune righe, verrà richiesto di rifiutare tutte le altre. Di conseguenza, se si desidera accettare altre righe, è necessario selezionare **Annulla** quando si riceve la richiesta. Lo stato della risposta RdO per ogni fornitore da cui si accettano offerte o righe viene aggiornato a **Accettato**.

Se, mentre si prepara l'ordine fornitore o il contratto di acquisto, è necessario aggiungere una riga aggiuntiva alla RdO, è possibile farlo facendo clic su **Aggiungi riga** nella griglia della pagina **Richiesta di offerta**. È possibile visualizzare e modificare la riga solo nella pagina **Richiesta di offerta**. Sarà visibile nella pagina di offerta quando viene accettata.

Quando si accetta un'offerta o una o più righe specifiche in un'offerta, un ordine fornitore o un contratto di acquisto viene generato automaticamente. È quindi possibile rifiutare le offerte da tutti gli altri fornitori.

Nella risposta, è possibile aggiungere un codice motivo per spiegare perché un'offerta è accettata o rifiutata.

Quando si accetta un'offerta di tipo **Richiesta di acquisto**, le righe della richiesta di acquisto vengono aggiornate in base alle seguenti informazioni che riflettono i dati dell'offerta accettata:

-   Prezzo unitario

-   Percentuale sconto

-   Importo sconto

-   Spese di acquisto

-   Spese riga

-   Fornitore

-  Numero esterno

-   Descrizione esterna


Nella seguente tabella viene indicato come cambia lo stato della richiesta di offerta quando si rifiutano le offerte dei fornitori.

<a name="statuses--highest-and-lowest"></a>Stati: minimo e massimo
-----------------------------

Nella scheda fornitore del caso RdO, è possibile visualizzare le righe con stato minimo e massimo per un fornitore specifico. Quando il fornitore viene aggiunto e nessuna riga è ancora stata inviata, sia lo stato minimo che massimo è <strong>Creata</strong>. Quando la richiesta di offerta viene inviata al fornitore con tutte le righe, lo stato delle due righe diventerà <strong>Inviata</strong>. Se alcune righe di un'offerta di un fornitore vengono accettate e altre vengono rifiutate, le righe rifiutate otterranno lo stato più basso, ovvero <strong>Rifiutata</strong>, e le righe accettate avranno lo stato più alto che è <strong>Accettata</strong>.

Nelle righe del caso RdO, è possibile visualizzare lo stato massimo e minimo per riga in tutti i fornitori. Se è stata inviata una riga a tutti i fornitori del caso RdO e nessuno ha ancora risposto, sia lo stato minimo che quello massimo saranno **Inviata**. Quando almeno un fornitore risponde, lo stato massimo verrà modificato in **Ricevuta**. Se si aggiunge un nuovo fornitore al caso, lo stato minimo diventerà **Creata**.

Lo stato minimo e massimo della RdO sono un'aggregazione dello stato nella \<scheda Fornitore e nella scheda Righe.

Gli stati sono classificati nel seguente modo dal minimo al massimo: Creata, Inviata, Ricevuta, Rifiutata, Accettata, Declinata, Annullata.

La seguente tabella mostra come cambia lo stato del caso RdO quando si crea un caso RdO con righe e quindi lo si invia ai fornitori.

| **Azione**                                | **Stato minimo caso RdO** | **Stato massimo caso RdO** | **Stato minimo riga caso RdO** | **Stato massimo riga caso RdO** |
|-------------------------------------------|----------------------------|-----------------------------|---------------------------------|----------------------------------|
| Creare l'intestazione e la riga del caso RdO.      | Data di creazione                    | Data di creazione                     | Data di creazione                         | Data di creazione                          |
| Inviare le RdO a tutti i fornitori nel caso RdO. | Inviato                       | Inviato                        | Inviato                            | Inviato                             |
| Aggiungere un altro fornitore.                       | Data di creazione                    | Inviato                        | Data di creazione                         | Inviato                             |
| Inviare la richiesta di offerta al secondo fornitore.        | Inviato                       | Inviato                        | Inviato                            | Inviato                             |

Tutte le linee sulle RdO correlate al caso RdO saranno nello stato **Inviata**.

Nella seguente tabella viene visualizzato il modo in cui la RdO cambia quando si ricevono le offerte e si registrano le informazioni nel foglio di risposta.

| **Azione**                                               | **Stato minimo in tutte le righe di tutte le RdO** | **Stato massimo in tutte le righe di tutte le RdO** | **Stato minimo intestazione caso RdO** | **Stato massimo intestazione caso RdO** | **Stato minimo riga caso RdO** | **Stato massimo riga caso RdO** |
|----------------------------------------------------------|------------------------------------------------|-------------------------------------------------|-----------------------------------|------------------------------------|---------------------------------|----------------------------------|
| Registrare l'offerta di un fornitore a una RdO e salvarla.        | Inviato                                           | Ricevuti                                        | Inviato                              | Ricevuti                           | Inviato                            | Ricevuti                         |
| Registrare la seconda offerta di un fornitore a una RdO e salvarla. | Ricevuti                                       | Ricevuti                                        | Ricevuti                          | Ricevuti                           | Ricevuti                        | Ricevuti                         |


Nell'esempio seguente è possibile visualizzare lo stato massimo e minimo nel caso RdO in cui un'offerta è stata ricevuta e l'altra è stata accettata. Quando un'offerta ricevuta viene rifiutata, lo stato minimo passerà da ricevuta a rifiutata nell'intestazione e nella riga del caso RdO.


|            <strong>Azione</strong>             | <strong>Stato minimo in tutte le righe di tutte le RdO</strong> | <strong>Stato massimo in tutte le righe di tutte le RdO</strong> | <strong>Stato minimo intestazione caso RdO</strong> | <strong>Stato massimo intestazione caso RdO</strong> | <strong>Stato minimo riga caso RdO</strong> | <strong>Stato massimo riga caso RdO</strong> |
|------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------------|------------------------------------------------|-------------------------------------------------|----------------------------------------------|-----------------------------------------------|
| Accettare una delle offerte. (o almeno una riga) |                          Ricevuti                           |                           Accettate                           |                    Ricevuti                    |                    Accettate                     |                   Ricevuti                   |                   Accettate                    |
|           Rifiutare tutte le altre offerte.           |                          Rifiutato                           |                           Accettate                           |                    Rifiutato                    |                    Accettate                     |                   Rifiutato                   |                   Accettata                    |

