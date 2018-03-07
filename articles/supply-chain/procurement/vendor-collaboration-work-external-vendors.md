---
title: Collaborazione fornitore con i fornitori esterni
description: In questo argomento viene illustrato come gli addetti agli acquisti possono collaborare con i fornitori esterni per scambiare informazioni sugli ordini fornitore e l'inventario spedizione.
author: mkirknel
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTableListPage, VendVendorPortalInvoicePart
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: b56cf58f78e5b3ed9bdd0d88f85d31123ec63451
ms.contentlocale: it-it
ms.lasthandoff: 12/14/2017

---

# <a name="vendor-collaboration-with-external-vendors"></a>Collaborazione fornitore con i fornitori esterni

[!include[banner](../includes/banner.md)]

Il modulo **Collaborazione fornitore** si rivolge ai fornitori che non dispongono di integrazione di scambio di dati elettronici (EDI) con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Consente ai fornitori di utilizzare ordini di acquisto, fatture, dati dell'inventario spedizione e richieste di offerta (RdO) e consente loro di accedere a parti dei dati master del fornitore. In questo argomento viene spiegato come è possibile collaborare con i fornitori esterni che usano l'interfaccia di collaborazione fornitore per utilizzare ordini fornitore, richieste di offerta e l'inventario spedizione. Viene inoltre illustrato come attivare un fornitore specifico per utilizzare la collaborazione fornitore e come definire i dati che tutti i fornitori vedranno quando risponderanno a un ordine fornitore.

Per ulteriori informazioni sulle attività che i fornitori esterni possono eseguire nell'interfaccia di collaborazione fornitore, vedere [Collaborazione fornitore con i clienti](vendor-collaboration-work-customers-dynamics-365-operations.md).

> [!NOTE]
> Le informazioni in questo argomento relative alla collaborazione con i fornitori sono applicabili solo alla versione corrente di Finance and Operations. In Microsoft Dynamics AX 7.0 (febbraio 2016) e Microsoft Dynamics AX versione applicazione 7.0.1 (maggio 2016), è possibile collaborare con i fornitori tramite il modulo del **Portale fornitori**. Per informazioni sul modulo **Portale fornitori**, vedere [Collaborazione con i fornitori tramite il portale fornitori](collaborate-vendors-vendor-portal.md).

Per ulteriori informazioni su come i fornitori possono utilizzare la collaborazione fornitore nei processi di fatturazione, vedere [Area di lavoro fatturazione di collaborazione fornitore](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md). Per informazioni su come richiedere il provisioning di nuovi utenti di collaborazione fornitore, vedere [Gestire gli utenti di collaborazione fornitore](manage-vendor-collaboration-users.md).

## <a name="defining-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Definire i dati che vengono visualizzati ai fornitori quando rispondono a ordini fornitore

Quando i fornitori rispondono a un ordine fornitore che hanno ricevuto, viene visualizzata una delle tre finestre di messaggio in cui devono confermare che desiderano accettarlo, rifiutarlo oppure che desiderano accettarlo con modifiche. Poiché i dati che devono essere visualizzati al fornitore a questo punto potrebbero essere specifici dell'azienda, è possibile specificare il testo che verrà visualizzato in ciascun messaggio di conferma. Ad esempio, il testo può informare il fornitore sui passaggi successivi della procedura o sui termini e le condizioni.

Per definire il testo visualizzato nella risposta dell'ordine fornitore, attenersi alla seguente procedura

1. Nella pagina **Informazioni per i fornitori che rispondono agli ordini di acquisto** selezionare il tipo di risposta e quindi selezionare **Modifica**.
2. Nella casella **Messaggio informazioni** immettere le informazioni che dovranno essere visualizzate ai fornitori nella finestra di messaggio visualizzata.

Se è necessario aggiungere messaggi in più lingue, creare messaggi separati con codice lingua appropriato. Per ogni fornitore verrà visualizzato il messaggio nella lingua che utilizza.

## <a name="setting-the-vendor-collaboration-options-for-a-specific-vendor"></a>Impostare le opzioni di collaborazione fornitore per un fornitore specifico

Un amministratore può configurare le impostazioni generali per la collaborazione fin Finance and Operations, ad esempio i ruoli di sicurezza disponibili per tutti i fornitori con cui collabora. Tuttavia, sono previste anche alcune impostazioni che possono essere diverse per ciascun conto fornitore. È necessario configurare queste impostazioni.

- Abilitare la collaborazione fornitore.
- Specificare se il fornitore deve visualizzare le informazioni sul prezzo.

### <a name="enabling-vendor-collaboration"></a>Abilitare la collaborazione fornitore

Prima di creare account utente per un fornitore esterno, è necessario configurare il conto fornitore per consentire al fornitore l'utilizzo della collaborazione fornitore. Nella pagina **Fornitori** nella scheda **Generale** impostare il campo **Attivazione collaborazione**. Sono disponibili le opzioni seguenti:

- **Attiva (con conferma automatica OF)**- Gli ordini fornitore vengono confermati automaticamente se il fornitore li accetta senza apportare modifiche.
- **Attiva (senza conferma automatica OF)**- Gli ordini fornitore devono essere confermati manualmente dall'organizzazione dopo che il fornitore li ha accettati.

### <a name="specifying-whether-the-vendor-should-see-price-information"></a>Specificare se il fornitore deve visualizzare le informazioni sul prezzo

Per condividere le informazioni sui prezzi per gli ordini di acquisto tramite l'interfaccia di collaborazione del fornitore, è necessario impostare l'opzione **Impostazioni predefinite ordine fornitore** nella scheda **Impostazioni predefinite ordine fornitore** per il conto fornitore su **Sì**. Le informazioni sul prezzo includono prezzo unitario, sconti e spese.

## <a name="working-with-pos-when-vendor-collaboration-is-used"></a>Ricorrere agli ordini fornitore quando viene utilizzata la collaborazione fornitore

### <a name="sending-a-po-to-a-vendor"></a>Inviare un ordine fornitore a un fornitore

Gli ordini fornitore vengono preparati in Finance and Operations. Quando un ordine fornitore ha lo stato **Approvato**, viene inviato al fornitore selezionando l'azione **Invia per conferma** nella pagina **Ordine fornitore**. Lo stato dell'ordine fornitore diventa **In revisione esterna**. Dopo aver inviato l'ordine fornitore, il fornitore lo può vedere nella pagina **Ordini fornitore per la revisione** dell'interfaccia della collaborazione fornitore. Il fornitore può quindi accettare l'ordine fornitore, rifiutarlo o suggerire modifiche. Il fornitore può anche aggiungere commenti per comunicare informazioni come modifiche all'ordine fornitore. Se si desidera richiamare l'attenzione del fornitore su un nuovo ordine fornitore è anche possibile utilizzare il sistema di gestione stampa per inviare l'ordine per e-mail.

### <a name="confirmation-and-acceptance-of-a-po-by-a-vendor"></a>Conferma e accettazione di un ordine fornitore da parte di un fornitore

Dopo che un fornitore accetta un ordine fornitore, l'ordine fornitore può essere confermato automaticamente oppure potrebbe essere necessario una conferma manuale. Questo comportamento dipende dal fatto che il campo **Attivazione collaborazione** è impostato su **Attiva (con conferma automatica OF)** o su **Attiva (senza conferma automatica OF)** per il fornitore.

La tabella di seguito mostra uno scambio di informazioni tipico, a seconda della risposta del fornitore risponde quando si invia un ordine fornitore per la conferma.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>Risposta fornitore</th>
<th>Risultato</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td>Il fornitore <strong>accetta</strong> l'ordine di dati finanziari e Finance and Operations è configurato per confermare automaticamente gli ordini di acquisto accettati dal fornitore.</td>
<td>Lo stato dell'ordine viene aggiornato a <strong>Confermato</strong>. Se qualcosa impedisce l'aggiornamento dell'ordine, la risposta del fornitore viene comunque registrata come <strong>Accettata</strong>, ma lo stato dell'ordine fornitore rimane <strong>In revisione esterna</strong>. 

L'ordine fornitore che è stato inviato al fornitore e con stato <strong>In revisione esterna</strong> viene aggiornato con le date di consegna confermate nelle righe. Questo aggiornamento avvia una nuova versione che viene impostata automaticamente sullo stato <strong>Confermato</strong>. Quando l'ordine fornitore viene confermato, viene visualizzato nell'interfaccia di collaborazione fornitore.</td>
</tr>
<tr class="odd">
<td>Il fornitore <strong>accetta</strong> l'ordine, ma Finance and Operations non è configurato per confermare automaticamente gli ordini fornitore accettati dal fornitore.</td>
<td>La risposta del fornitore viene registrata come <strong>Accettata</strong>, ma lo stato dell'ordine fornitore rimane <strong>In revisione esterna</strong>.

L'ordine fornitore che è stato inviato al fornitore e con stato <strong>In revisione esterna</strong> viene aggiornato con le date di consegna confermate nelle righe. Questo aggiornamento avvia una nuova versione che viene impostata automaticamente sullo stato <strong>In revisione esterna</strong>. È quindi possibile confermare manualmente l'ordine fornitore.</td>
</tr>
<tr class="even">
<td>Il fornitore <strong>rifiuta</strong> l'ordine.</td>
<td>La risposta del fornitore viene registrata come <strong>Rifiutata</strong> e lo stato dell'ordine fornitore rimane <strong>In revisione esterna</strong>. Il rifiuto viene ricevuto insieme alla nota del fornitore.</td>
</tr>
<tr class="odd">
<td>Il fornitore <strong>accetta</strong> l'ordine <strong>con modifiche</strong>. Le modifiche vengono suggerite a livello di riga. Il fornitore può accettare o rifiutare singole righe. Di seguito vengono riportati alcune altre modifiche che il fornitore può suggerire:
<ul>
<li>Modificare le date o quantità.</li>
<li>Suddividere righe per date o quantità di consegna differenti.</li>
<li>Sostituire un articolo.</li>
</ul>
Le informazioni relative ai prezzi e alle spese non possono essere modificate dal fornitore. Tuttavia, il fornitore può suggerire queste modifiche tramite le note.</td>
<td>La risposta del fornitore viene registrata come <strong>Accettata con modifiche</strong> e lo stato dell'ordine fornitore rimane impostato su <strong>In revisione esterna</strong>. Gli stati indicano i tipi di modifiche che ha suggerito il fornitore. Per informazioni sul consumo automatico delle modifiche, vedere la sezione di seguito Aggiornare l'ordine fornitore quando un fornitore suggerisce modifiche. </td>
</tr>
</tbody>
</table>

È possibile utilizzare l'area di lavoro **Preparazione ordini acquisto** per controllare a quali ordini fornitore il fornitore ha risposto. Questa area di lavoro contiene due elenchi che contengono gli ordini fornitore con stato **In revisione esterna**:

- In revisione esterna richiede un'azione
- In revisione esterna in attesa della risposta fornitore

### <a name="changing-a-po"></a>Modifica di un ordine fornitore

Per modificare un ordine fornitore a cui un fornitore ha già risposto, è necessario inviare al fornitore una nuova versione dell'ordine. Il nuovo ordine fornitore presenterà un suffisso versione per indicare che si tratta di una versione modificata di un ordine fornitore inviato in precedenza. La pagina **Storico conferme fornitore per l'ordine fornitore** consente al cliente e ai suoi fornitori di tenere traccia dello storico di ciascun ordine. La versione confermata in precedenza dell'ordine fornitore rimane nell'elenco di ordini confermati finché non viene confermato il nuovo ordine.

### <a name="canceling-a-po"></a>Annullare un ordine fornitore

Quando si annulla un ordine fornitore, viene ripristinato lo stato **Approvato**. È necessario inviare di nuovo l'ordine al fornitore in modo che possa confermare o rifiutare l'annullamento. Dopo la conferma dell'annullamento, l'ordine fornitore viene visualizzato nell'elenco dell'elenco del fornitore degli ordini come **Annullato**.

### <a name="adding-attachments-to-a-po"></a>Aggiunta degli allegati a un ordine fornitore

È possibile aggiungere allegati quali file, immagini e note all'ordine fornitore utilizzando il sistema di gestione documenti. Gli allegati di tipo **Esterno** saranno visibili al fornitore quando si invia un ordine fornitore.

## <a name="updating-a-po-when-a-vendor-suggests-changes"></a>Aggiornare un ordine fornitore quando un fornitore suggerisce modifiche

Se un fornitore ha risposto a un ordine fornitore e ha suggerito delle modifiche, il passaggio successivo consiste nell'elaborare la risposta.

Nell'area di lavoro **Preparazione ordini acquisto** nell'elenco **In revisione esterna richiede un'azione**, è possibile identificare gli ordini fornitore a cui un fornitore ha risposto accettando le modifiche. Dall'elenco, è inoltre possibile accedere alla risposta del fornitore.

In una risposta, un fornitore può modificare le informazioni seguenti nell'intestazione:
 
- Riferimento documento fornitore
- Modalità di consegna
- Termini di consegna
- Data di consegna confermata

Il fornitore può inoltre aggiungere una nota o un allegato.

Nelle righe, il fornitore può modificare la quantità e le date di consegna, aggiunge note e allegati, rifiutare una riga, sostituire una riga con un altro prodotto inserito come testo e dividere una riga in più consegne. Lo stato di una riga varia in base alle modifiche che il fornitore ha suggerito:
    
- **Accettata con modifiche**
- **Rifiutata**
- **Sostituita**: in questo caso, viene aggiunta un'altra riga con stato **Sostituisci**.
- **Confermato**
- **Sostituita**: in questo caso verranno aggiunte altre righe con stato **Righe programmazione**.

Se una riga non include modifiche, lo stato della riga è **Accettata**.

Nella risposta, gli stati di riga indicano i tipi di modifiche apportati dal fornitore. Inoltre, tutti i campi modificati vengono mostrati in grassetto per aiutare l'individuazione delle modifiche.

È possibile aggiornare un ordine fornitore selezionando **Elabora aggiornamento ordine fornitore** nella risposta o in una riga alla volta. Un campo **L'aggiornamento ordine fornitore è stato elaborato?** presente nell'intestazione e nelle righe consente di vedere se il sistema ha elaborato l'intestazione o le righe per aggiornare l'ordine fornitore con le potenziali modifiche originate dalla risposta. È possibile eseguire l'azione **Elabora aggiornamento ordine fornitore** solo una volta per intestazione o per riga.

Non tutte le modifiche suggerite possono essere aggiornate in un ordine fornitore. Solo gli aggiornamenti nell'intestazione e gli aggiornamenti di date e quantità nelle righe possono essere aggiornati automaticamente nell'ordine fornitore. Per le altre modifiche, è necessario aggiornare l'ordine fornitore manualmente. In questo caso, il valore del campo **L'aggiornamento ordine fornitore è stato elaborato?** è **Aggiornamento manuale**. Ad esempio, se un fornitore suggerisce di dividere una riga in una programmazione, questa modifica deve essere effettuata manualmente.

Ogni riga con stato **Accettato** avrà una data di consegna confermata. Quando si esegue l'azione **Elabora aggiornamento ordine fornitore**, questa data viene aggiornata nell'ordine fornitore. Le note e gli allegati non vengono trasferiti automaticamente all'ordine fornitore corrente. Inoltre, quando si aggiorna l'ordine fornitore corrente mediante l'azione **Elabora aggiornamento ordine fornitore**, gli accordi commerciali non vengono rivalutati nelle righe dell'ordine fornitore.

## <a name="po-statuses-and-versions"></a>Stati e versioni dell'ordine fornitore

In questa sezione vengono descritti i vari stati che un ordine fornitore può avere fino al momento in cui non viene confermato. Viene inoltre descritto quando le nuove versioni di un ordine fornitore vengono rese disponibili al fornitore. Il comportamento varia a seconda che si utilizzi la gestione delle modifiche per gli ordini fornitore. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versioni e stati se non si utilizza la gestione modifiche

Nella tabella seguente è riportato un esempio delle modifiche dello stato e della versione a cui potrebbe essere sottoposto un ordine fornitore.

| Azione | Stato e versione |
|--------|--------------------|
| La versione iniziale dell'ordine fornitore viene creata in Finance and Operations. | Lo stato è **Approvato**. |
| L'ordine fornitore viene inviato al fornitore. | Una versione viene registrata nell'interfaccia di collaborazione fornitore e lo stato viene impostato su **In revisione esterna**. |
| Il fornitore invia una risposta **Accettata con modifiche** . | Lo stato è ancora **In revisione esterna**. |
| Si apportano alcune modifiche richieste dal fornitore. | Lo stato viene impostato su **Approvato**. |
| La nuova versione dell'ordine fornitore viene inviata al fornitore. | Una nuova versione viene registrata nell'interfaccia di collaborazione fornitore e lo stato viene impostato su **In revisione esterna**. |
| Il fornitore accetta la nuova versione dell'ordine. | Lo stato è ancora **In revisione esterna** a meno che il conto fornitore sia configurato per impostare automaticamente gli ordini fornitore su uno stato **Confermato** quando accettati dal fornitore. |

I fornitori non devono confermare un ordine fornitore tramite l'interfaccia di collaborazione fornitore. Possono anche inviare messaggi di posta elettronica o comunicare l'accettazione di un ordine attraverso altri canali. È quindi possibile confermare manualmente l'ordine in Finance and Operations. In questo caso, viene visualizzato un avviso che informa che l'ordine sta per essere confermato anche in assenza di risposte dal fornitore. L'ordine fornitore viene visualizzato nello storico di conferma come ordine confermato aperto che non dispone di risposte. A questo punto, il fornitore non ha più la possibilità di rifiutare o confermare l'ordine fornitore.

> [!NOTE]
> La versione dell'ordine fornitore disponibile ad altri processi in Finance and Operations è sempre la versione più recente, anche se tale versione non è ancora stata registrata nell'interfaccia di collaborazione fornitore.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versioni e stati se si utilizza la gestione modifiche

Se è stata abilitata la gestione delle modifiche degli ordini fornitore, gli ordini devono superare un flusso di lavoro di approvazione per ottenere lo stato **Approvato**. Questo processo non è visibile al fornitore.

Nella tabella riportata di seguito viene mostrato un esempio di modifica allo stato e alla versione a cui l'ordine potrebbe essere sottoposto quando la gestione delle modifiche è abilitata. Una versione viene registrata quando l'ordine fornitore viene approvato, non quando viene inviato al fornitore o confermato.

| Azione | Stato e versione |
|--------|--------------------|
| La versione iniziale dell'ordine fornitore viene creata in Finance and Operations. | Lo stato è **Bozza**. |
| L'ordine fornitore viene inviato al processo di approvazione. Il processo di approvazione è un processo interno che non coinvolge il fornitore. | Lo stato viene modificato da **Bozza** a **In revisione** ad **Approvazione** se l'ordine non viene rifiutato durante il processo di approvazione. L'ordine fornitore approvato viene registrato come una versione. | 
| L'ordine fornitore viene inviato al fornitore. | La versione viene registrata nell'interfaccia di collaborazione fornitore e lo stato viene impostato su **In revisione esterna**. |
| È possibile apportare alcune modifiche richieste dal fornitore manualmente o utilizzando l'azione **Elabora aggiornamento ordine fornitore** sulla risposta per aggiornare l'ordine fornitore. | Lo stato torna a essere **Bozza**. |
| L'ordine fornitore viene nuovamente inviato al processo di approvazione. | Lo stato viene modificato da **Bozza** a **In revisione** ad **Approvazione** se l'ordine non viene rifiutato durante il processo di approvazione. In alternativa, il sistema può essere configurato in modo che modifiche specifiche ai campi non richiedano una nuova approvazione. In questo caso, lo stato viene inizialmente modificato in **Bozza** e quindi automaticamente aggiornato ad **Approvato**. L'ordine fornitore approvato viene registrato come nuova versione. |
| La nuova versione dell'ordine fornitore viene inviata al fornitore. | La nuova versione viene registrata nell'interfaccia di collaborazione fornitore e lo stato viene impostato su **In revisione esterna**. |
| Il fornitore approva la nuova versione dell'ordine. | Lo stato viene modificato in **Confermato** automaticamente o quando si riceve la risposta dal fornitore e quindi si conferma l'ordine. |

## <a name="sharing-information-about-consignment-inventory"></a>Condividere informazioni sull'inventario spedizione

Se si utilizza l'inventario spedizione, i fornitori possono usare l'interfaccia di collaborazione fornitore per visualizzare le informazioni nelle pagine seguenti:

- **Ordini fornitore che utilizzano inventario spedizione** - Gli ordini fornitore per l'inventario di spedizione vengono generati quando la proprietà dell'inventario passa dal fornitore alla società. Contemporaneamente viene registrata un'entrata prodotti. Questi ordini fornitore di spedizione vengono mostrati solo nella pagina **Ordini fornitore che utilizzano inventario spedizione**. Non sono inclusi nella pagina **Tutti gli ordini fornitore confermati** del modulo **Collaborazione fornitore**.
- **Prodotti entrati da inventario spedizione** - In questa pagina sono elencate tutte le transazioni in cui la proprietà dei prodotti è stata trasferita dal fornitore alla società. I fornitori possono utilizzare queste informazioni per la fatturazione al cliente.
- **Inventario spedizione disponibile** - In questa pagina viene mostrato l'inventario spedizione disponibile di proprietà del fornitore, che è stato ricevuto presso il magazzino del cliente.

## <a name="working-with-rfqs-when-you-use-vendor-collaboration"></a>Ricorrere alle RdO quando viene utilizzata la collaborazione fornitore

In questa sezione vengono descritte le interazioni tra clienti e fornitori durante il processo RdO. Viene inoltre illustrato come le informazioni vengono comunicate ai fornitori. Per una panoramica di base del processo RdO, vedere [Richieste di offerta (RdO)](request-quotations.md).

### <a name="alternates-attachments-amendments-and-returns"></a>Alternative, allegati, modifiche e resi

- **Alternative** - Nell'intestazione di un caso RdO, è possibile specificare che le alternative sono consentite per righe articolo fuori catalogo. Quando le alternative sono abilitate, i fornitori possono aggiungere una riga alternativa per ogni riga richiesta.
- **Allegati** - Gli allegati possono essere aggiunti sia a livello di intestazione sia a livello di riga i un caso RdO. Gli allegati possono essere classificati come interni o esterni. Gli allegati interni possono essere visualizzati solo da parte dei clienti, mentre i fornitori possono visualizzare gli allegati esterni dopo essere stati inviati.

    I fornitori possono inoltre aggiungere allegati alla relativa risposta. Questi allegati possono essere visualizzati da parte del cliente dopo che un fornitore invia la richiesta di offerta. Gli allegati che i fornitori aggiungono sono sempre classificati come esterni. Per accedere all'allegato che un fornitore ha inviato insieme a un'offerta, selezionare **Allegati offerta** o **Allegati riga di offerta**.
    
    Per aprire gli allegati che sono stati inviati insieme al caso RdO, utilizzare il simbolo di graffetta per la gestione documenti nella risposta.

- **Modifiche** - Quando una modifica è finalizzata, le risposte all'offerta esistenti vengono rimosse in modo che possano essere sostituite da valori aggiornati. Informazioni quali il prezzo della riga e la quantità delle risposte all'offerta precedenti possono essere visualizzate tramite i diari sul caso RdO.

    Per applicare l'elaborazione della modifica, nella pagina **Parametri di approvvigionamento** nella scheda dettaglio **Richiesta di offerta** impostare l'opzione **Blocca RdO quando inviate** su **Sì**. (Questa opzione è impostata e richiesta per il settore pubblico.)

- **Resi** - Se il fornitore ha inviato un'offerta, ma sono necessarie informazioni in più o modificate per il caso RdO, il cliente può restituire l'offerta al venditore. I dati dell'offerta precedentemente inviata vengono conservati e il fornitore può apportare le modifiche richieste senza dover iniziare di nuovo il processo di offerta.

## <a name="public-sector-extensions"></a>Estensioni per il settore pubblico

Per il settore pubblico, la funzionalità estesa consente di inviare un caso RdO ai fornitori e di pubblicarlo. Quando si pubblica una RdO, qualsiasi utente che richiede le informazioni può visualizzare il lavoro che corrisponde alla maggior parte delle normative del settore pubblico. Qualsiasi lavoro disponibile viene visualizzato nella pagina elenco **Richieste di offerta pubblicate aperte** e le richieste di offerta annullate, in sospeso o assegnate possono essere visualizzate nella pagina elenco **Richieste di offerta pubblicate chiuse**. Questi documenti possono essere visualizzati in un sito esterno a Finance and Operations tramite le integrazioni con le seguenti entità dei dati:

- Richieste di offerta pubblicate
- Riga di richieste di offerta pubblicate
- Allegati intestazioni richieste di offerta pubblicate

Queste entità consentono alle persone che non sono utenti di Finance and Operations, ma che hanno accesso anonimo al sito esterno, di visualizzare il lavoro disponibile e chiuso. Inoltre, la funzionalità estesa **Invia e pubblica** consente all'utente che ha impostato i parametri per il processo RdO di definire un modello di messaggio di posta elettronica. In seguito, quando la persona responsabile dell'approvvigionamento crea il caso RdO, dovrà selezionare il modello di messaggio di posta elettronica per inviare le informazioni necessarie ai fornitori nel caso RdO. 

L'utente che imposta i parametri per il processo RdO può creare più modelli di messaggio di posta elettronica. Questi modelli di messaggio di posta elettronica possono contenere sia testo statico che i seguenti token di sostituzione. I token verranno sostituiti con i valori contestuali quando viene creato un messaggio di posta elettronica.

- %RFQCase%
- %RFQCaseName%
- %bidType%
- %inviteOnly%
- %expiryDateTime%
- %requester%
- %requestingDepartment%
- %accountnum%
- %todaysdate%
- %createddate%

Se è richiesta una modifica e viene inviata dopo l'invio della RdO, la RdO verrà inviata nuovamente a tutti i fornitori invitati. Il documento pubblicato verrà aggiornato anche nella pagina **Richieste di offerta pubblicate aperte**.

