---
title: Collaborazione fornitore con i fornitori esterni
description: In questo argomento viene illustrato come gli addetti agli acquisti possono collaborare con i fornitori esterni per scambiare informazioni sugli ordini fornitore e l'inventario spedizione.
author: BibiSp
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: cbd099403f48b502ca74bcb38ae12decedb8f2da
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---

# <a name="vendor-collaboration-with-external-vendors"></a>Collaborazione fornitore con i fornitori esterni

[!include[banner](../includes/banner.md)]


In questo argomento viene illustrato come gli addetti agli acquisti possono collaborare con i fornitori esterni per scambiare informazioni sugli ordini fornitore e l'inventario spedizione.

Il modulo **Collaborazione fornitore** si rivolge ai fornitori che non dispongono di integrazione di scambio di dati elettronici (EDI) con Microsoft Dynamics 365 for Finance and Operations. Consente ai fornitori di utilizzare ordini fornitore, fatture e dati dell'inventario spedizione. In questo argomento viene descritto come è possibile collaborare con i fornitori esterni che usano l'interfaccia di collaborazione fornitore per utilizzare gli ordini fornitore e l'inventario spedizione. Viene inoltre descritto come attivare un fornitore specifico per utilizzare la collaborazione fornitore e come definire i dati che tutti i fornitori vedranno quando risponderanno a un ordine fornitore. Per ulteriori informazioni sulle attività che i fornitori esterni possono eseguire nell'interfaccia di collaborazione fornitore, vedere [Collaborazione fornitore con i clienti](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Per ulteriori informazioni su come i fornitori possono utilizzare la collaborazione fornitore nei processi di fatturazione, vedere [Area di lavoro fatturazione di collaborazione fornitore](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace). Per informazioni su come richiedere il provisioning di nuovi utenti di collaborazione fornitore, vedere [Gestire gli utenti di collaborazione fornitore](manage-vendor-collaboration-users.md).

Per ulteriori informazioni su come i fornitori possono utilizzare la collaborazione fornitore nei processi di fatturazione, vedere [Area di lavoro fatturazione di collaborazione fornitore](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace). 

Per informazioni su come richiedere il provisioning di nuovi utenti di collaborazione fornitore, vedere [Gestire gli utenti di collaborazione fornitore](manage-vendor-collaboration-users.md).

## <a name="define-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Definire i dati che vengono visualizzati ai fornitori quando rispondono a ordini fornitore
Quando i fornitori rispondono a un ordine fornitore che hanno ricevuto, vedono una finestra di messaggio in cui devono confermare che desiderano accettarlo, rifiutarlo oppure che desiderano accettarlo con modifiche. Poiché i dati che devono essere visualizzati al fornitore a questo punto potrebbero essere specifici dell'azienda, è possibile specificare il testo che verrà visualizzato in ciascuno dei tre messaggi di conferma. Ad esempio, il testo può informare il fornitore sui passaggi successivi della procedura o sui termini e le condizioni.  

Per definire il testo visualizzato nella risposta dell'ordine fornitore:

1.  Aprire la pagina **Informazioni per i fornitori che rispondono agli ordini di acquisto**.
2.  Selezionare uno dei tipi di risposta.
3.  Fare clic su **Modifica**.
4.  Immettere i dati da visualizzare ai fornitori nella casella **Messaggio informazioni**.

Se è necessario aggiungere messaggi in più lingue, creare messaggi separati con codici lingua appropriati. Al fornitore verrà visualizzato il messaggio nella lingua che utilizza.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Impostare le opzioni di collaborazione fornitore per un fornitore specifico
Le impostazioni generali per la collaborazione fornitore in Finance and Operations vengono configurate da un amministratore. Ad esempio, un amministratore determina quali ruoli di sicurezza sono disponibili per tutti i fornitori con cui si collabora. Sono previste anche alcune impostazioni che possono essere diverse per ciascun conto fornitore ed è consigliabile definire le seguenti:
-   Abilitare la collaborazione fornitore.
-   Specificare se si desidera che il fornitore visualizzi le informazioni relative ai prezzi.

### <a name="enable-vendor-collaboration"></a>Abilitare la collaborazione fornitore

Prima di creare account utente per un fornitore esterno, è necessario configurare il conto fornitore per consentire l'utilizzo della collaborazione fornitore. A tale scopo, impostare il campo **Attivazione collaborazione** su Attivo nella scheda **Generale** della pagina **Fornitori**. Sono disponibili due opzioni selezionabili:

-   **Attiva (con conferma automatica OF)**- Gli ordini fornitore vengono confermati automaticamente quando il fornitore li accetta senza apportare modifiche.
-   **Attiva (senza conferma automatica OF)**- Gli ordini fornitore devono essere confermati manualmente dall'organizzazione dopo che il fornitore li ha accettati.

### <a name="decide-whether-you-want-the-vendor-to-see-price-information"></a>Specificare se si desidera che il fornitore visualizzi le informazioni relative ai prezzi.

Se si desidera condividere le informazioni relative ai prezzi, ad esempio il prezzo unitario, gli sconti e le spese mediante l'interfaccia di collaborazione, è necessario impostare l'opzione **Prezzi/Importo ordine fornitore** su **Sì** nel conto fornitore. Questa opzione è disponibile nella scheda **Impostazioni predefinite ordine fornitore** .

## <a name="work-with-pos-when-using-vendor-collaboration"></a>Ricorrere agli ordini fornitore quando si utilizza la collaborazione fornitore
### <a name="sending-a-po-to-the-vendor"></a>Invio di un ordine fornitore al fornitore

Gli ordini fornitore sono preparati in Finance and Operations. Quando l'ordine fornitore ha lo stato **Approvato**, viene inviato al fornitore che utilizza l'azione **Invia per conferma** nella pagina **Ordine fornitore**. Lo stato dell'ordine fornitore diventa **In revisione esterna**. Dopo aver inviato l'ordine fornitore, il fornitore lo può vedere nella pagina **Ordini fornitore per la revisione** dell'interfaccia della collaborazione fornitore. Il fornitore può quindi accettare l'ordine, rifiutarlo o suggerire modifiche. Il fornitore può anche aggiungere commenti per comunicare informazioni come modifiche all'ordine fornitore. Se si desidera richiamare l'attenzione del fornitore su un nuovo ordine fornitore, è anche possibile utilizzare il sistema di gestione stampa per inviare l'ordine per e-mail.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>Conferma e accettazione dell'ordine fornitore da parte del fornitore

Se un fornitore ha accettato un ordine fornitore, l'ordine fornitore può essere confermato automaticamente o è possibile che debba essere confermato manualmente. Ciò dipende dal fatto che il campo **Attivazione fornitore** è impostato su **Attiva (con conferma automatica OF)** o su **Attiva (senza conferma automatica OF)** per il fornitore.  

La tabella di seguito mostra uno scambio di informazioni tipico, a seconda del modo in cui il fornitore risponde quando si invia un ordine fornitore per la conferma.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Risposta fornitore</strong></td>
<td><strong>Risultato</strong></td>
</tr>
<tr class="even">
<td>Il fornitore <strong>accetta</strong> l'ordine. Finance and Operations è configurato per confermare automaticamente gli ordini fornitore quando il fornitore li accetta.</td>

<td>Lo stato dell'ordine viene aggiornato a <strong>Confermato</strong>. Se qualcosa impedisce l'aggiornamento dell'ordine, la risposta del fornitore viene comunque registrata come <strong>Accettata</strong>, ma lo stato dell'ordine fornitore rimane <strong>In revisione esterna</strong>. 

L'ordine fornitore che è stato inviato al fornitore e che ha lo stato **In revisione esterna** viene aggiornato con le date di consegna confermate nelle righe. L'aggiornamento avvia una nuova versione che viene aggiornata automaticamente allo stato **Confermato**. Quando l'ordine fornitore viene confermato, viene visualizzato nell'interfaccia della collaborazione fornitore.</td>
</tr>
<tr class="odd">
<td>Il fornitore <strong>accetta</strong> l'ordine. Finance and Operations non è configurato per confermare automaticamente gli ordini fornitore quando il fornitore li accetta.</td>
<td>La risposta del fornitore viene registrata come <strong>Accettata</strong>, ma lo stato dell'ordine fornitore rimane <strong>In revisione esterna</strong>.

L'ordine fornitore che è stato inviato al fornitore e che ha lo stato **In revisione esterna** viene aggiornato con le date di consegna confermate nelle righe. L'aggiornamento avvia una nuova versione che viene impostata su **In revisione esterna**. In questo modo è possibile confermare l'ordine fornitore manualmente.</td>

</tr>
<tr class="even">
<td>Il fornitore <strong>rifiuta</strong> l'ordine.</td>
<td>La risposta del fornitore viene registrata come <strong>Rifiutata</strong> e lo stato dell'ordine fornitore rimane <strong>In revisione esterna</strong>. Il rifiuto viene ricevuto insieme alla nota del fornitore.</td>
</tr>
<tr class="odd">
<td>Il fornitore <strong>accetta l'ordine con le modifiche</strong>. Le modifiche vengono suggerite a livello di riga. È possibile accettare o rifiutare singole righe. Altre modifiche possibili sono:
<ul>
<li>Modificare le date o quantità.</li>
<li>Suddividere righe per date o quantità di consegna differenti.</li>
<li>Sostituire un articolo.</li>
</ul>
Le informazioni relative ai prezzi e le spese non possono essere modificate dal fornitore. Eventuali modifiche possono essere suggerite utilizzando le note.</td>
<td>La risposta del fornitore viene registrata come <strong>Accettata con modifiche</strong> e lo stato dell'ordine fornitore rimane impostato su <strong>In revisione esterna</strong>. Gli stati indicano quali tipi di modifiche ha suggerito il fornitore. Per informazioni sul consumo automatico delle modifiche, vedere la sezione di seguito su come aggiornare un ordine fornitore quando un fornitore suggerisce delle modifiche. </td>
</tr>
</tbody>
</table>

È possibile utilizzare l'area di lavoro **Preparazione** **ordini acquisto** per controllare a quali ordini fornitore il fornitore ha risposto. Questa area di lavoro contiene due elenchi che contengono gli ordini fornitore con stato **In revisione esterna**:

-   In revisione esterna richiede un'azione.
-   In revisione esterna in attesa della risposta fornitore.

### <a name="changing-a-po"></a>Modifica di un ordine fornitore

Per modificare un ordine fornitore a cui si è già risposto, è necessario inviare una nuova versione dell'ordine al fornitore. Il nuovo ordine fornitore presenterà un suffisso versione per indicare che si tratta di una versione modificata di un ordine fornitore comunicato in precedenza. La pagina **Storico conferme fornitore per l'ordine fornitore** consente al cliente e ai suoi fornitori di tenere traccia dello storico di ciascun ordine. La versione confermata in precedenza dell'ordine fornitore rimane nell'elenco di ordini confermati finché non viene confermato il nuovo ordine.

### <a name="cancelling-a-po"></a>Annullamento di un ordine fornitore

Quando si annulla un ordine fornitore, viene ripristinato lo stato **Approvato**. È necessario inviare nuovamente l'ordine al fornitore tramite il portale in modo che possa confermare o rifiutare l'annullamento. Dopo la conferma dell'annullamento l'ordine fornitore risulta **Annullato** nell'elenco degli ordini fornitori confermati del fornitore.

### <a name="adding-attachments-to-a-po"></a>Aggiunta degli allegati a un ordine fornitore

È possibile aggiungere allegati quali file, immagini e note all'ordine fornitore utilizzando il sistema di gestione documenti. Gli allegati di tipo **Esterno** saranno visibili al fornitore quando si invia un ordine fornitore.

## <a name="update-the-po-when-a-vendor-suggests-changes"></a>Aggiornare l'ordine fornitore quando un fornitore suggerisce modifiche
Dopo che un fornitore ha risposto all'ordine fornitore e ha suggerito delle modifiche, il passaggio successivo consiste nell'elaborare la risposta.
Nell'area di lavoro **Preparazione ordini acquisto**, nell'elenco In revisione esterna richiede un'azione, è possibile identificare un ordine fornitore a cui un fornitore ha risposto accettando le modifiche. Nell'elenco In revisione esterna richiede un'azione è inoltre possibile passare alla risposta del fornitore. In una risposta, un fornitore può modificare le informazioni seguenti nell'intestazione.
 
-   Riferimento documento fornitore
-   Modalità di consegna
-   Termini di consegna
-   Data di consegna confermata

Il fornitore può inoltre aggiungere una nota o un allegato

Nelle righe, il fornitore può modificare la quantità e le date di consegna, aggiunge note e allegati, rifiutare una riga, sostituire una riga con un altro prodotto immesso come testo e dividere una riga in più consegne. A seconda delle modifiche suggerite dal fornitore, lo stato delle righe sarà diverso:
    
-   **Accettata con modifiche**
-   **Rifiutata**
-   **Sostituita**: in questo caso verrà aggiunta un'altra riga con lo stato **Sostituire**.
-   **Confermata** Suddivisa in programmazione: in questo caso verranno aggiunte altre righe con lo stato **Riga programmazione**.

Se una riga non include modifiche, lo stato della riga è **Accettata**.

Nella risposta, è possibile visualizzare gli stati di riga precedentemente menzionati che indicano i tipi di modifiche apportate dal fornitore. Inoltre, tutti i campi modificati vengono visualizzati in grassetto per aiutare l'individuazione delle modifiche.

È possibile aggiornare un ordine fornitore facendo clic sull'azione **Elabora aggiornamento ordine fornitore** nella risposta o in una riga alla volta. Un indicatore, **L'aggiornamento ordine fornitore è stato elaborato?**, presente nell'intestazione e nelle righe consente di vedere se il sistema ha elaborato l'intestazione o le righe per aggiornare l'ordine fornitore con le potenziali modifiche originate dalla risposta. È possibile eseguire il processo **Elabora aggiornamento ordine fornitore** solo una volta per intestazione o per riga.

Non tutte le modifiche suggerite possono essere aggiornate in un ordine fornitore. Solo gli aggiornamenti nell'intestazione e gli aggiornamenti di date e quantità nelle righe possono essere aggiornati automaticamente nell'ordine fornitore. Per le altre modifiche, è necessario aggiornare l'ordine fornitore manualmente. In questo caso, l'indicatore **L'aggiornamento ordine fornitore è stato elaborato?** mostra **Aggiornamento manuale**. Un esempio di modifica che deve essere gestita manualmente è quando un fornitore suggerisce di dividere una riga in una programmazione.

Una riga con stato **Accettata** ha una data di consegna confermata che sarà aggiornata nell'ordine fornitore quando si esegue l'azione **Elabora aggiornamento ordine fornitore**. Le note e gli allegati non vengono trasferiti automaticamente all'ordine fornitore corrente. Quando si aggiorna l'ordine fornitore corrente mediante l'azione **Elabora aggiornamento ordine fornitore**, gli accordi commerciali non vengono rivalutati nelle righe dell'ordine fornitore.


## <a name="po-statuses-and-versions"></a>Stati e versioni dell'ordine fornitore
In questa sezione vengono descritti i vari stati che un ordine fornitore può avere fino al momento in cui non viene confermato. Viene inoltre descritto quando le nuove versioni dell'ordine fornitore vengono rese disponibili al fornitore. Il comportamento varia a seconda che si utilizzi la gestione delle modifiche per gli ordini fornitore. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versioni e stati se non si utilizza la gestione modifiche

Nella tabella seguente è riportato un esempio delle modifiche dello stato e della versione a cui potrebbe essere sottoposto un ordine fornitore.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Azione**                                                               | **Stato e versione**                                                                                                                                       |
| La versione iniziale dell'ordine fornitore viene creata in Finance and Operations. | Lo stato è **Approvato**.                                                                                                                                  |
| L'ordine fornitore viene inviato al fornitore.                                            | Una versione viene registrata nell'interfaccia di collaborazione fornitore e lo stato viene impostato su **In revisione esterna**.                                          |
| Il fornitore invia una risposta **Accettata con modifiche** .                  | Lo stato è ancora **In revisione esterna**.                                                                                                                  |
| Si apportano alcune modifiche richieste dal fornitore.                  | Lo stato viene impostato su **Approvato**.                                                                                                                        |
| La nuova versione dell'ordine fornitore viene inviata al fornitore.                        | Una nuova versione viene registrata nell'interfaccia di collaborazione fornitore e lo stato viene impostato su **In revisione esterna**.                                      |
| Il fornitore accetta la nuova versione dell'ordine.                            | Lo stato è ancora **In revisione esterna** a meno che il conto fornitore sia configurato per impostare automaticamente l'ordine fornitore su uno stato **Confermato** quando viene accettato. |


I fornitori non devono confermare l'ordine fornitore tramite l'interfaccia di collaborazione fornitore. Possono anche inviare un messaggio di posta elettronica o comunicare l'accettazione di un ordine attraverso altri canali. È quindi possibile confermare l'ordine manualmente in Finance and Operations. In questo caso, viene visualizzato un avviso che l'ordine sta per essere confermato anche in assenza di risposte dal fornitore. L'ordine fornitore viene visualizzato nello storico di conferma come ordine confermato aperto che non dispone di risposte. Il fornitore non ha più la possibilità di rifiutare o confermare l'ordine fornitore.  


>[!NOTE]
>La versione dell'ordine fornitore disponibile ad altri processi in Dynamics 365 for Finance and Operations è sempre la versione più recente, anche se tale versione non è ancora stata registrata nell'interfaccia di collaborazione fornitore.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versioni e stati se si utilizza la gestione modifiche

Se è stata abilitata la gestione delle modifiche degli ordini fornitore, l'ordine deve superare un flusso di lavoro di approvazione per ottenere lo stato **Approvato**. Questo processo non è visibile al fornitore.  

Nella tabella riportata di seguito viene mostrato un esempio di modifica allo stato e alla versione a cui l'ordine potrebbe essere sottoposto quando la gestione delle modifiche è abilitata. La versione viene registrata quando l'ordine fornitore viene approvato, non quando viene inviato al fornitore o confermato.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Azione**                                                               | **Stato e versione**                                                                                                                                       |
| La versione iniziale dell'ordine fornitore viene creata in Finance and Operations.      | Lo stato è **Bozza**.  |
| L'ordine fornitore viene inviato al processo di approvazione. Il processo di approvazione è un processo interno che non coinvolge il fornitore.                                                           | Lo stato viene modificato da **Bozza** a **In revisione** ad **Approvazione** se l'ordine fornitore non viene rifiutato durante il processo di approvazione. L'ordine fornitore approvato viene registrato come una versione.           | 
| L'ordine fornitore viene inviato al fornitore.                                                            | La versione viene registrata nell'interfaccia di collaborazione fornitore e lo stato viene impostato su **In revisione esterna**.      |
| È possibile apportare alcune modifiche richieste dal fornitore manualmente o utilizzando l'azione sulla risposta per aggiornare l'ordine fornitore.                                                            | Lo stato torna a essere **Bozza**.     |
|L'ordine fornitore viene nuovamente inviato al processo di approvazione.                                                |  Lo stato viene modificato da **Bozza** a **In revisione** ad **Approvazione** se l'ordine fornitore non viene rifiutato durante il processo di approvazione. In alternativa, il sistema può essere configurato in modo che modifiche specifiche ai campi non richiedano una nuova approvazione. In questo caso, lo stato viene inizialmente modificato in **Bozza** e quindi automaticamente aggiornato ad **Approvato**. L'ordine fornitore approvato viene registrato come nuova versione.                                         |
|La nuova versione dell'ordine fornitore viene inviata al fornitore.                                                |  La nuova versione viene registrata nell'interfaccia di collaborazione fornitore e lo stato viene impostato su **In revisione esterna**.                                         |
|Il fornitore approva la nuova versione dell'ordine.                                                |  Lo stato viene modificato in **Confermato** automaticamente o quando si riceve la risposta dal fornitore e quindi si conferma l'ordine. |

## <a name="share-information-about-consignment-inventory"></a>Condividere le informazioni sull'inventario spedizione
Se si utilizza l'inventario spedizione, i fornitori possono usare l'interfaccia di collaborazione fornitore per visualizzare le informazioni nelle pagine seguenti:

-   **Ordini fornitore che utilizzano inventario spedizione** - Gli ordini fornitore per l'inventario di spedizione vengono generati quando la proprietà dell'inventario passa dal fornitore alla società. Contemporaneamente viene registrata un'entrata prodotti. Questi ordini fornitore di spedizione vengono visualizzati solo nella pagina **Ordini fornitore che utilizzano inventario spedizione**. Non sono inclusi nella pagina **Tutti gli ordini fornitore confermati** del modulo **Collaborazione fornitore**.
-   **Prodotti entrati da inventario spedizione** - In questa pagina sono elencate tutte le transazioni in cui la proprietà dei prodotti è stata trasferita dal fornitore alla società. I fornitori possono utilizzare queste informazioni per la fatturazione al cliente.
-   **Inventario spedizione disponibile** - In questa pagina viene mostrato l'inventario spedizione disponibile di proprietà del fornitore, che è stato ricevuto presso il magazzino del cliente.





