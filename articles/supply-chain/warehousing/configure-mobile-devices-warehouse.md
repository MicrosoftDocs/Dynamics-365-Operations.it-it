---
title: Impostare i dispositivi mobili per il lavoro di magazzino
description: Viene descritto come si configurano le voci di menu che i lavoratori del magazzino utilizzano per svolgere il proprio lavoro su un dispositivo mobile.
author: MarkusFogelberg
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFSysDirSort, WHSWorkUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29941
ms.assetid: 6dff6313-dc6e-4f06-9c0c-dab24eefe4da
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 657dd864885bc7c8216aab95a73f389f21f7cccd
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102928"
---
# <a name="set-up-mobile-devices-for-warehouse-work"></a>Impostare i dispositivi mobili per il lavoro di magazzino

[!include [banner](../includes/banner.md)]

Viene descritto come si configurano le voci di menu che i lavoratori del magazzino utilizzano per svolgere il proprio lavoro su un dispositivo mobile.

> [!NOTE]
> Questo argomento si applica alle funzionalità in Gestione magazzino. e non viene applicato alle funzionalità in Gestione articoli. Le voci di menu visualizzate nei menu in un dispositivo mobile di magazzino vengono configurate nella pagina **Voci di menu del dispositivo mobile**. Poiché le voci di menu possono essere immesse in menu diversi, è semplice configurare le strutture di menu in modo da esporre solo tipi specifici di lavoro a utenti specifici. Le voci di menu possono essere configurate per eseguire le attività indicate di seguito.

- Elaborare una richiesta di informazioni o eseguire un'attività, ad esempio stampare un'etichetta, generare numeri di identificazione, avviare un ordine di produzione o trovare rapidamente le informazioni sugli articoli in un'ubicazione.
- Creare un lavoro che viene eseguito tramite un altro processo. Ad esempio, la ricezione di un articolo per un ordine fornitore può creare il lavoro di stoccaggio per un altro lavoratore.
- Eseguire il lavoro creato da un altro processo (lavoro esistente), ad esempio lavoro di stoccaggio creato quando un articolo è stato ricevuto per un ordine fornitore.

Per creare una voce di menu per un'attività o una richiesta, impostare il campo **Modalità** su **Indiretta**. Diventa quindi disponibile un elenco di opzioni **Codice attività**, nel quale è possibile selezionare il tipo di richiesta o di attività per il quale è impostata la voce di menu. Per creare una voce di menu per generare il lavoro magazzino, impostare il campo **Modalità** su **Lavoro**. Diventa disponibile un elenco di opzioni **Processo di creazione lavoro**. Per creare una voce di menu per elaborare un lavoro di magazzino esistente, impostare il campo **Modo** su **Lavoro**, quindi impostare l'opzione **Utilizza lavoro esistente** su **Sì**. 

> [!NOTE]
> Se la voce di menu viene utilizzata per eseguire un lavoro esistente e a seconda della modalità selezionata per la voce di menu, sono disponibili campi aggiuntivi per le voci di menu. Per informazioni sulle selezioni dei campi aggiuntivi, vedere la sezione "Opzioni aggiuntive della voce di menu" in questo argomento.

## <a name="configure-menu-items-for-activities-and-inquiries"></a>Configurare voci di menu per attività e richieste di informazioni

Se il campo **Modo** per una voce di menu è impostato su **Indiretto**, è possibile creare una voce di menu per eseguire un'attività o una richiesta di informazioni generale che non crea il lavoro. Esempi includono attività quali la ristampa di etichette targa e le richieste di informazioni per gli articoli in un'ubicazione. Nella seguente tabella vengono elencate le opzioni disponibili.

| Opzione | Descrizione |
|---|---|
| Nessuno | Il valore predefinito non abilita un'attività o una richiesta di informazioni. |
| Informazioni su | Visualizzare informazioni sul sistema, ad esempio il numero di versione, l'ID magazzino e il lavoratore attualmente collegato. |
| Modifica magazzino | Cambiare il magazzino a cui è collegato un lavoratore. |
| Richiesta di informazioni sull'ubicazione | Visualizzare informazioni su tutti gli articoli e le quantità per un'ubicazione. |
| Richiesta di informazioni sulla targa | Visualizzare la quantità di articoli in una targa e l'ubicazione della targa. |
| Avvia ordine di produzione | Avviare un ordine di produzione. |
| Scarti di produzione | Immettere la quantità di scarto creato durante la produzione per ogni riga della distinta base (DBA). |
| Ultimo pallet produzione | Indicare che è stato prodotto l'ultimo pallet di articoli per un ordine di produzione e che lo stato dell'ordine di produzione deve essere aggiornato impostandolo su **Dichiarato finito**. Lo stato delle materie prime che non sono state utilizzate durante la produzione viene reimpostato da **Quantità prelevata** a **In ordinazione** e gli articoli possono essere restituiti al magazzino. |
| Richiesta informazioni su articolo | Eseguire la scansione di un articolo per determinarne la posizione nel magazzino. La richiesta di informazioni restituisce tutte le ubicazioni e le quantità dell'articolo sottoposto a scansione. |
| Ristampa etichetta | Ristampare un'etichetta targa. |
| Compilazioni targa | Creare una targa padre combinando più targhe nella stessa ubicazione. Questa opzione è utile se si spostano più targhe contemporaneamente. Dopo aver spostato la targa padre, è necessario eseguire una suddivisione delle targhe prima di prelevare gli articoli da ciascuna targa. <p></p>**Suggerimento**: per spostare una targa padre, è necessario utilizzare un dispositivo mobile configurato per creare lavoro per i movimenti. |
| Suddivisioni targa | Suddividere la compilazione di una targa in modo da poter prelevare gli articoli dalle targhe presenti nella compilazione. |
| Check-in conducente | Se si utilizza Gestione trasporto, registrare l'arrivo di un conducente eseguendo la scansione dell'ID carico in uscita, dell'ID appuntamento o dell'ID spedizione. Per questa opzione, è necessario che un carico sia assegnato all'appuntamento e che lo stato del carico sia **Caricato**. |
| Check-out conducente | Registrare che il conducente ha completato il suo appuntamento. |
| Cancella cache sequenza numerica | Eliminare i numeri della sequenza numerica dalla cache della sequenza numerica. Questa attività in genere viene eseguita da un amministratore di sistema per risolvere i problemi di cache quando si utilizzano i dispositivi mobili. |
| Modifica smaltimento batch | Consentire a un lavoratore di specificare un codice smaltimento batch per un articolo e un batch. Questa selezione aggiornerà il codice smaltimento specificato per il batch. |
| Visualizza elenco lavori aperti | Visualizzare un elenco di lavoro disponibile per un utente specifico. L'utente può selezionare il lavoro da eseguire e verrà diretto al lavoro stesso. Questo elenco può essere visualizzato sui dispositivi tablet con dimensioni dello schermo di 7 pollici o più. Quando si seleziona questa opzione, le voci di menu **Modifica query** ed **Elenco campi** sono abilitate. Nella pagina **Modifica query** è possibile impostare i criteri per il lavoro riportato nell'elenco. Nella pagina **Elenco campi** è possibile selezionare i campi che vengono visualizzati nell'elenco di lavoro. Ad esempio, è possibile ridurre il numero di campi visibili per rendere più rapida per l'utente la selezione degli elementi di lavoro più appropriati. Nella scheda dettaglio **Generale**, nel campo **Record per pagina**, è inoltre possibile selezionare il numero di record visualizzati per pagina. Se l'opzione **Consenti agli utenti di filtrare il lavoro in base al tipo di transazione** è selezionata, nell'elenco sarà presente un controllo aggiuntivo **Filtra lavoro** che consente di applicare un filtro in base al tipo di transazione. Nell'elenco gli utenti vedranno solo il lavoro per cui dispongono delle autorizzazioni di accesso. Verificare che gli utenti dispongano delle autorizzazione per una o più voci di menu definite dall'utente che supportano i tipi della classe di lavoro specifici a cui è necessario accedere. Le autorizzazioni vengono verificate quando l'utente tenta di eseguire il lavoro dall'elenco.|
| Crea ordine di trasferimento da targhe | Consente agli addetti al magazzino di creare ed elaborare ordini di trasferimento direttamente nell'app per dispositivi mobili Gestione magazzino. Gli addetti al magazzino iniziano selezionando il magazzino di destinazione e possono quindi eseguire la scansione di una o più targhe utilizzando l'app. Quando l'addetto al magazzino seleziona **Completa ordine**, un processo batch creerà l'ordine di trasferimento richiesto e le righe dell'ordine in base alle scorte disponibili registrate per tali targhe. Per ulteriori informazioni, vedi [Creare ordini di trasferimento nell'app di magazzino](create-transfer-order-from-warehouse-app.md)

## <a name="configure-menu-items-to-create-work-for-another-worker-or-process"></a>Configurare voci di menu per creare il lavoro per un altro lavoratore o processo

È possibile impostare una voce di menu che crea il lavoro per un altro lavoratore dopo l'esecuzione di un'azione iniziale sul dispositivo mobile. Ad esempio, quando un lavoratore utilizza un dispositivo mobile per ricevere un articolo, viene creato il lavoro di stoccaggio per un altro lavoratore. Per impostare una voce di menu che crea il lavoro, nella pagina **Voci di menu del dispositivo mobile**, nel campo **Modalità** selezionare **Lavoro**. Nella tabella seguente le opzioni nel campo **Processo di creazione lavoro** sono disposte tipo di ordine di lavoro.

<table>
<tbody>
<tr>
<th>Tipo ordine di lavoro</th>
<th>Opzione</th>
<th>Descrizione</th>
</tr>
<tr>
<td rowspan="8">Ordine acquisto</td>
<td>Ricevimento riga ordine acquisto</td>
<td>Registrare l'entrata della quantità di un articolo utilizzando il numero di ordine fornitore e il numero di riga dell'ordine fornitore e creare lavoro di stoccaggio per un altro lavoratore.</td>
</tr>
<tr>
<td>Ricevimento e stoccaggio riga ordine acquisto</td>
<td>Registrare l'entrata della quantità di un articolo utilizzando il numero di ordine fornitore e il numero di riga dell'ordine fornitore e stoccare gli articoli. Lo stesso lavoratore esegue entrambe le azioni.</td>
</tr>
<tr>
<td>Ricevimento articolo ordine acquisto</td>
<td>Registrare l'entrata della quantità di un articolo per un ordine fornitore utilizzando il numero di ordine fornitore e il numero di articolo e creare lavoro di stoccaggio per un altro lavoratore.</td>
</tr>
<tr>
<td>Ricevimento e stoccaggio articolo ordine acquisto</td>
<td>Registrare l'entrata della quantità di un articolo per un ordine fornitore registrando il numero ordine fornitore e stoccare l'articolo. Lo stesso lavoratore esegue entrambe le azioni.</td>
</tr>
<tr>
<td>Ricevimento targa</td>
<td>Ricevere un Advance Shipping Notice (ASN) in entrata utilizzando l'ID targa.</td>
</tr>
<tr>
<td>Ricevimento e stoccaggio targa</td>
<td>Ricevere e stoccare un Advance Shipping Notice (ASN) in entrata utilizzando l'ID targa.</td>
</tr>
<tr>
<td>Ricezione articoli di carico</td>
<td>Registrare l'entrata della quantità di un carico registrando l'ID carico e creare il lavoro di stoccaggio per un altro lavoratore. Il numero di articolo e le dimensioni del prodotto associa l'entrata alle righe ordine fornitore.</td>
</tr>
<tr>
<td>Ricevimento e stoccaggio articoli di carico</td>
<td>Registrare l'entrata di un carico utilizzando l'ID carico e stoccare gli articoli. Il numero di articolo e le dimensioni del prodotto associa l'entrata alle righe ordine fornitore. Lo stesso lavoratore esegue entrambe le azioni.</td>
</tr>
<tr>
<td rowspan="2">Ordine di reso</td>
<td>Ricevimento ordine di reso</td>
<td>Registrare l'entrata della quantità di un articolo registrando il codice NAR e creare il lavoro di stoccaggio per un altro lavoratore.</td>
</tr>
<tr>
<td>Ricevimento e stoccaggio ordine di reso</td>
<td>Registrare l'entrata della quantità di un articolo registrando il codice NAR e stoccare gli articoli. Lo stesso lavoratore esegue entrambe le azioni.</td>
</tr>
<tr>
<td rowspan="6">Ordine di trasferimento</td>
<td>Ricevimento articolo ordine di trasferimento</td>
<td>Registrare l'entrata della quantità di un articolo e creare il lavoro di stoccaggio per un altro lavoratore.

<strong>Nota:</strong> utilizzare questa opzione solo se gli articoli sono stati spediti da un magazzino che non è abilitato per i processi di gestione magazzino.</td>
</tr>
<tr>
<td>Ricevimento e stoccaggio articolo ordine di trasferimento</td>
<td>Registrare l'entrata della quantità di un articolo e stoccare gli articoli. Lo stesso lavoratore esegue entrambe le azioni.

<strong>Nota:</strong> utilizzare questa opzione solo se gli articoli sono stati spediti da un magazzino che non è abilitato per i processi di gestione magazzino.</td>
</tr>
<tr>
<td>Ricevimento riga ordine di trasferimento</td>
<td>Registrare l'entrata della quantità di un articolo e creare il lavoro di stoccaggio per un altro lavoratore.</td>
</tr>
<tr>
<td>Ricevimento e stoccaggio riga ordine di trasferimento</td>
<td>Registrare l'entrata della quantità di un articolo e stoccare gli articoli. Lo stesso lavoratore esegue entrambe le azioni.</td>
</tr>
<tr>
<td>Ricevimento targa</td>
<td>Ricevere un Advance Shipping Notice (ASN) in entrata utilizzando l'ID targa.</td>
</tr>
<tr>
<td>Ricevimento e stoccaggio targa</td>
<td>Ricevere e stoccare un Advance Shipping Notice (ASN) in entrata utilizzando l'ID targa.</td>
</tr>
<tr>
<td rowspan="4">Produzione</td>
<td>Dichiarazione di finito</td>
<td>Registrare la quantità di un articolo finito che è stato completato per una produzione e creare lavoro di stoccaggio per un altro lavoratore. La quantità può essere parte della quantità o tutta la quantità pianificata per la produzione.</td>
</tr>
<tr>
<td>Dichiarato di finito e stoccato</td>
<td>Registrare la quantità di un articolo finito che è stato completato per una produzione e stoccare gli articoli. La quantità può essere parte della quantità o tutta la quantità pianificata per la produzione. Lo stesso lavoratore esegue entrambe le azioni.</td>
</tr>
<tr>
<td>Kanban</td>
<td>Indicare che un kanban è completato e creare il lavoro di stoccaggio per un altro lavoratore.</td>
</tr>
<tr>
<td>Stoccaggio kanban</td>
<td>Indicare che un kanban è completato e stoccare gli articoli. Lo stesso lavoratore esegue entrambe le azioni.</td>
</tr>
<tr>
<td rowspan="5">Inventario</td>
<td>Spostamento</td>
<td>Registrare che gli articoli sono stati spostati da un'ubicazione a un'altra. Il lavoratore specifica l'ubicazione di provenienza degli articoli e l'ubicazione in cui vengono spostati.</td>
</tr>
<tr>
<td>Quarantena</td>
<td>Cambiare lo stato delle scorte disponibili per una targa o un'ubicazione per rendere non disponibili gli articoli di magazzino danneggiati o mancanti.</td>
</tr>
<tr>
<td>Movimento per modello</td>
<td>Spostare gli articoli da un'ubicazione a un'altra in modo semiautomatico. Il lavoratore seleziona l'ubicazione da cui spostare gli articoli e il sistema utilizza la direttiva di ubicazione per determinare l'ubicazione in cui spostarli.</td>
</tr>
<tr>
<td>Trasferimento di magazzino</td>
<td>Registrare che gli articoli sono stati trasferiti da un magazzino a un altro. È necessario che il lavoratore sia autorizzato a eseguire il lavoro in entrambi i magazzini.

<strong>Nota:</strong> questa voce di menu richiede un giornale di registrazione predefinito di <strong>trasferimento scorte</strong> con il campo del giustificativo elementi immessi impostato sulla <strong>registrazione</strong>.</td>
</tr>
<tr>
<td>Caricamento targa</td>
<td>Utilizzare questa opzione quando si imposta per la prima volta il magazzino. Eseguire la scansione di tutte le targhe in tutte le ubicazioni del magazzino. Le ubicazioni devono essere controllate da targa. Non è possibile utilizzare questa opzione se il campo <strong>Numero di serie</strong> o <strong>Numero batch</strong> è presente prima di <strong>Ubicazione</strong> nella gerarchia di prenotazione scorte.</td>
</tr>
<tr>
<td rowspan="3">Conteggio ciclo</td>
<td>Rettifica in entrata</td>
<td>Aumentare la quantità degli articoli nel magazzino. Specificare l'ubicazione, la targa, l'articolo, la quantità, l'unità di misura e lo stato.</td>
</tr>
<tr>
<td>Rettifica in uscita</td>
<td>Ridurre la quantità degli articoli nel magazzino. Specificare l'ubicazione, la targa, l'articolo, la quantità, l'unità di misura e lo stato del magazzino.</td>
</tr>
<tr>
<td>Conteggio ciclo a campione</td>
<td>Avviare il conteggio per un'ubicazione. Il lavoratore deve conteggiare tutti gli articoli dell'ubicazione. Quando il risultato di un conteggio è inferiore alla quantità prevista, la quantità mancante viene considerata una perdita.</td>
</tr>
</tbody>
</table>

## <a name="configure-menu-items-to-process-existing-work"></a>Configurare voci di menu per elaborare il lavoro esistente
Oltre a impostare voci di menu per creare il lavoro di magazzino, è possibile impostare le voci di menu per elaborare lavoro che è già stato creato. Impostare il campo **Modalità** su **Lavoro** e selezionare l'opzione **Utilizza lavoro esistente**. Alcune opzioni aggiuntive diventano disponibili nella scheda **Generale**. È possibile controllare l'accesso alla voce di menu assegnando una o più classi di lavoro nella scheda dettaglio **Classe lavoro**. Le classi di lavoro definiscono il lavoro che la voce di menu può elaborare. La classe di lavoro può anche essere utilizzata per concedere l'accesso a ruoli utente specifici o per separare l'elaborazione per diversi tipi di transazioni. Nella seguente tabella vengono illustrate le opzioni disponibili. L'opzione può essere scelta nel campo **Diretto da** della pagina **Voci di menu del dispositivo mobile**. 

<table>




<thead>
<tr class="header">
<th>Opzione</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nessuna</td>
<td>Per impostazione predefinita il lavoro non viene elaborato.</td>
</tr>
<tr class="even">
<td>Diretto dal sistema</td>
<td>Supply Chain Management controlla il tipo di lavoro che viene assegnato al lavoratore e l'ordine in cui il lavoratore esegue il lavoro. Quando selezioni questa opzione, puoi selezionare <strong>Lavoro gestito dal sistema</strong> nel riquadro azioni per aprire la pagina <strong>Ordinamento gestito dal sistema</strong>, nella quale si possono impostare i criteri di ordinamento per il lavoro. I criteri di ordinamento controllano l'ordine in cui il lavoratore esegue il lavoro. È possibile aggiungere tutti i criteri necessari.</td>
</tr>
<tr class="odd">
<td>Diretto dall'utente</td>
<td>Il lavoratore seleziona il lavoro da eseguire e l'ordine in eseguirlo.</td>
</tr>
<tr class="even">
<td>Raggruppamento utenti</td>
<td>Il lavoratore raggruppa manualmente il lavoro. Ad esempio, questa opzione è utile quando un lavoratore può prelevare più articoli contemporaneamente in un'ubicazione. Una volta completato il prelievo di tutti gli articoli richiesti, il lavoratore può stoccare gli articoli.</td>
</tr>
<tr class="odd">
<td>Raggruppamento sistema</td>
<td>Supply Chain Management raggruppa il lavoro per il lavoratore in base al campo specificato. Ad esempio, il lavoro di prelievo è raggruppato quando un lavoratore esegue la scansione di un ID spedizione, di un ID carico o di qualsiasi valore che può collegare ogni unità di lavoro. Se si seleziona questa opzione, i seguenti campi sono obbligatori:
<ul>
<li><strong>Campo di raggruppamento sistema</strong>: selezionare il campo che verrà sottoposto a scansione dal lavoratore per raggruppare il lavoro.</li>
<li><strong>Etichetta di raggruppamento sistema</strong>: immettere il testo per indicare al lavoratore gli elementi da sottoporre a scansione per raggruppare il lavoro.</li>
</ul></td>
</tr>
<tr class="even">
<td>Diretto dall'utente con convalida</td>
<td>Il lavoratore seleziona il lavoro da eseguire quando il lavoro è associato a un'entità più grande, ad esempio un carico o una spedizione. Il lavoratore determina l'ordine in cui prelevare gli articoli. Se si seleziona questa opzione, i seguenti campi sono obbligatori:
<ul>
<li><strong>Campo diretto dall'utente con convalida</strong>: selezionare il campo che verrà sottoposto a scansione dal lavoratore per raggruppare il lavoro.</li>
<li><strong>Etichetta diretta dall'utente con convalida</strong>: immettere il testo per indicare al lavoratore gli elementi da sottoporre a scansione quando il lavoro di prelievo viene raggruppato dal sistema.</li>
</ul>
Questa opzione è utile, ad esempio, quando più pallet sono approntati per un carico. Se si seleziona <strong>ID carico</strong> nel campo <strong>Diretto dall'utente con convalida</strong>, il lavoratore può prelevare qualsiasi pallet associato al carico. Il lavoratore riceve un messaggio di errore se esegue la scansione di un articolo che non è associato al carico.</td>
</tr>
<tr class="odd">
<td>Prelievo cluster</td>
<td>Il lavoratore raggruppa il lavoro in cluster. I cluster consentono ai lavoratori di prelevare gli articoli da un'unica ubicazione per più ordini di lavoro contemporaneamente.</td>
</tr>
<tr class="even">
<td>Raggruppamento conteggio ciclo</td>
<td>Il lavoratore seleziona una zona, un pool di lavoro o un'ubicazione e in Supply Chain Management il lavoro viene assegnato in base alla selezione. Se si seleziona questa opzione, è inoltre possibile fare clic su <strong>Conteggio ciclo</strong> nel riquadro azioni per specificare informazioni aggiuntive per visualizzare e specificare il numero di volte in cui il lavoratore deve ripetere il conteggio se viene rilevata una differenza.</td>
</tr>
 <tr class="odd">
<td>Caricamento di trasporto</td>
<td>Questa funzionalità consente a più addetti al magazzino di caricare le scorte dallo stesso carico o da carichi diversi nello stesso camion, con carichi che sono spediti completamente o parzialmente.</td>
</tr>
</tbody>
</table>

## <a name="additional-menu-item-options"></a>Opzioni aggiuntive della voce di menu
Opzioni aggiuntive delle voci di menu sono disponibili nella pagina **Voci di menu del dispositivo mobile**. Le opzioni variano a seconda del processo per cui è si configura la voce di menu. 

Nella seguente tabella sono descritte queste opzioni.

<table>




<thead>
<tr class="header">
<th>Campo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Consenti suddivisione del lavoro</td>
<td>Selezionare questa opzione per consentire agli utenti di inserire gli articoli di un ordine di lavoro in più targhe di destinazione. Questa opzione è utile, ad esempio, quando una targa di destinazione è completa e il lavoratore deve aggiungere gli articoli rimanenti in un'altra targa. Il lavoratore può selezionare <strong>Completa</strong> per indicare che la targa è completa e non è possibile ricevere il lavoro di prelievo. Viene quindi visualizzata l'ubicazione di stoccaggio per gli articoli prelevati e il lavoro di prelievo che è stato già completato viene spostato in un nuovo ordine di lavoro. Il lavoro di prelievo rimanente per la targa di destinazione rimane nell'ordine di lavoro originale.</td>
</tr>
<tr class="even">
<td>Ancoraggio</td>
<td>Selezionare questa opzione per consentire ai lavoratori di specificare un'ubicazione che sostituisca l'ubicazione di carico o di gestione temporanea suggerita. Tutto il lavoro di stoccaggio rimanente viene indirizzato alla nuova ubicazione. Ad esempio, questa opzione è utile quando un lavoratore deve inserire gli articoli per l'ordine 1 in un'ubicazione di gestione temporanea dalla banchina 1, ma non può perché un carico precedente non ha cancellato l'ubicazione. Anziché attendere che diventi disponibile l'ubicazione gestione temporanea banchina 1, il lavoratore può scegliere di utilizzare l'ubicazione gestione temporanea per la banchina 2. In questo caso, il lavoratore ignora l'ubicazione gestione temporanea suggerita. L'ubicazione di stoccaggio per tutti gli articoli rimanenti dell'ordine di lavoro viene aggiornata impostando l'ubicazione di gestione temporanea della banchina 2. Se si seleziona questa opzione, è necessario immettere un valore nel campo <strong>Ancora per</strong>.</td>
</tr>
<tr class="odd">
<td>Ancora per</td>
<td>Se si utilizza l'ancoraggio, è necessario specificare se si desidera ancorare in base alla spedizione o al carico.</td>
</tr>
<tr class="even">
<td>ID modello di audit</td>
<td>Selezionare il modello di audit lavoro che interrompe il processo di lavoro per la voce di menu in modo da poter eseguire un'altra operazione. Ad esempio, se la voce di menu è per un lavoro in entrata, il modello di audit può richiedere che il lavoratore controlli la temperatura nel contenitore di consegna. Il punto in cui il processo viene interrotto è specificato nel modello di controllo. Questo punto può essere determinato, ad esempio, quando il lavoro è avviato o completato o quando lo stato cambia.</td>
</tr>
<tr class="odd">
<td>ID profilo cluster</td>
<td>Selezionare il profilo del cluster da utilizzare per il prelievo del cluster. Il profilo del cluster include le impostazioni che stabiliscono, ad esempio, se i cluster vengono creati automaticamente, i nomi delle posizioni e il numero di unità di lavoro a cui possono essere assegnati, quando suddividere i cluster in singole unità e se la verifica è obbligatoria. Questo campo è disponibile solo se l'opzione <strong>Prelievo cluster</strong> è selezionata nel campo <strong>Diretto da</strong>.</td>
</tr>
<tr class="even">
<td>Conteggia prima la quantità totale di articoli</td>
<td>Selezionare questa opzione per richiedere al lavoratore di conteggiare innanzitutto la quantità totale durante un conteggio. Se viene rilevata una differenza, il lavoratore deve fornire informazioni aggiuntive, ad esempio il numero di identificazione, il numero batch e i numeri di serie.</td>
</tr>
<tr class="odd">
<td>Crea spostamento</td>
<td>Selezionare questa opzione per consentire a un lavoratore di creare il lavoro per un movimento senza richiedere al lavoratore di eseguire immediatamente il lavoro. Ad esempio, questa opzione è utile quando un controllo di qualità viene completato e l'addetto alle ispezioni desidera che l'articolo venga spostato dall'area di ispezione qualità.</td>
</tr>
<tr class="even">
<td>Codice direttiva</td>
<td>Per utilizzare una direttiva ubicazione specifica, selezionare il codice della direttiva associato alla direttiva ubicazione. Questo campo è disponibile quando si crea un lavoro e il processo di creazione del lavoro è <strong>Movimento per modello</strong>.</td>
</tr>
<tr class="odd">
<td>Disabilita soglie conteggio ciclo</td>
<td>Selezionare questa opzione per ignorare le soglie del conteggio ciclo. Se si seleziona questa opzione, il lavoro del conteggio ciclo non viene creato quando i valori di soglia vengono superati.</td>
</tr>
<tr class="even">
<td>Visualizza codice smaltimento batch</td>
<td>Selezionare questa opzione per visualizzare i codici di smaltimento batch. Ad esempio, è possibile visualizzare i codici di smaltimento batch quando si riceve un batch reso. In tal modo i lavoratori possono valutare lo stato o la qualità di un batch e selezionare il codice appropriato. Le regole del codice di smaltimento batch determinano se il batch sarà disponibile per altri processi di magazzino. Se non si seleziona questa opzione, viene utilizzato uno dei seguenti codici di smaltimento batch:
<ul>
<li>Se si riceve un nuovo numero batch, viene utilizzato il codice di smaltimento batch predefinito specificato nel gruppo di modelli dell'articolo.</li>
<li>Viene utilizzato il codice di smaltimento batch già assegnato al batch.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Visualizza codice smaltimento</td>
<td>Selezionare questa opzione per visualizzare i codici di smaltimento. Ad esempio, è possibile visualizzare i codici di smaltimento quando si ricevono articoli resi. In tal modo i lavoratori possono valutare lo stato o la qualità degli articoli e selezionare il codice appropriato. Le regole del codice di smaltimento determinano se gli articoli sono disponibili per altri processi di magazzino.</td>
</tr>
<tr class="even">
<td>Visualizza stato inventario</td>
<td>Selezionare questa opzione per visualizzare lo stato degli articoli nel magazzino. Questa opzione è disponibile per tutte le voci di menu che utilizzano il lavoro esistente, ad eccezione del conteggio ciclo.</td>
</tr>
<tr class="odd">
<td>Visualizza riepilogo della schermata di prelievo</td>
<td>Selezionare questa opzione per visualizzare un riepilogo del lavoro di prelievo relativo all'ordine di lavoro selezionato. Il riepilogo è visualizzato fino all'elaborazione della prima riga di lavoro dell'ordine di lavoro.</td>
</tr>
<tr class="even">
<td>Genera targa</td>
<td>Selezionare questa opzione per generare un numero di identificazione univoco in base alla selezione della sequenza numerica. Ad esempio, è possibile generare un numero di identificazione per gli articoli ricevuti per gli ordini fornitore.</td>
</tr>
<tr class="odd">
<td>Stoccaggio di gruppo</td>
<td>Selezionare questa opzione di controllo per raggruppare il lavoro di stoccaggio. Questa opzione è disponibile quando il lavoro è stato raggruppato dal lavoratore o da Supply Chain Management. Quando il lavoratore ha terminato tutto il lavoro di prelievo nel gruppo, viene creato un lavoro di stoccaggio per lo stesso gruppo.</td>
</tr>
<tr class="even">
<td>Tipi di correzione inventario</td>
<td>Selezionare il tipo di correzione magazzino che determina il giornale di registrazione conteggi scorte che viene utilizzato per registrare la correzione e se le prenotazioni vengono rimosse. Questo campo è disponibile solo per il processo di creazione lavoro <strong>Rettifica in entrata</strong> o <strong>Rettifica in uscita</strong>.</td>
</tr>
<tr class="odd">
<td>Ignora numero batch</td>
<td>Selezionare questa opzione per consentire ai lavoratori che dichiarano una quantità come finita per un ordine di produzione, di immettere un numero batch diverso dal numero batch assegnato all'ordine di produzione.</td>
</tr>
<tr class="even">
<td>Ignora targa destinazione</td>
<td>Selezionare questa opzione per consentire ai lavoratori di specificare un numero di identificazione diverso da quello suggerito. Utilizzare questa opzione quando il primo prelievo per un ordine di lavoro è per l'intera quantità di un articolo in una targa. Questa opzione è utile ad esempio quando si riutilizza un pallet.</td>
</tr>
<tr class="odd">
<td>Preleva e imballa</td>
<td>Selezionare questa opzione per consentire ai lavoratori di combinare il lavoro di un ordine cliente o di un carico in una singola unità di lavoro. Un lavoratore può eseguire il lavoro solo per l'ordine cliente o il carico. Ad esempio, questa opzione è utile quando è necessario aumentare una quantità per un ordine cliente dopo che il carico, la spedizione e il lavoro sono stati creati per l'ordine cliente. Questa opzione è disponibile se la voce di menu utilizza il lavoro esistente e il lavoro è indirizzato dall'utente o dal sistema.</td>
</tr>
<tr class="even">
<td>Preleva batch meno recente</td>
<td>Indicare se il lavoratore deve prelevare per primo il batch meno recente in un'ubicazione. Sono disponibili le seguenti opzioni:
<ul>
<li><strong>Nessuno</strong>: il lavoratore può prelevare qualsiasi batch nell'ubicazione. Il lavoratore non riceverà alcun messaggio.</li>
<li><strong>Avvisa</strong>: il lavoratore può prelevare qualsiasi batch nell'ubicazione, ma viene visualizzato un messaggio di avviso se il batch non è il meno recente.</li>
<li><strong>Forza</strong>: il lavoratore deve prelevare il batch meno recente nell'ubicazione. Il lavoratore riceve un messaggio di errore se un batch non è il batch più recente. <strong>Nota:</strong> questa opzione è rilevante solo se il valore del campo <strong>Numero batch</strong> è minore del valore del campo <strong>Ubicazione</strong> nella gerarchia di prenotazione assegnata all'articolo.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Stampa etichetta</td>
<td>Selezionare questa opzione per consentire ai lavoratori di stampare le etichette targa.</td>
</tr>
<tr class="even">
<td>Campo di raggruppamento sistema</td>
<td>Selezionare il campo che determina la modalità di raggruppamento del lavoro di prelievo per il lavoratore utilizzata da Supply Chain Management. Ad esempio, se si seleziona il campo <strong>ID spedizione</strong>, il lavoratore esegue la scansione dell'ID spedizione per raggruppare il lavoro di prelievo. Tutto il lavoro di spedizione verrà quindi assegnato al lavoratore. Per questo campo è richiesta la creazione di una voce di menu per utilizzare il lavoro esistente raggruppato dal sistema. È necessario immettere inoltre testo nel campo <strong>Etichetta di raggruppamento sistema</strong> per indicare al lavoratore gli elementi da sottoporre a scansione.</td>
</tr>
<tr class="odd">
<td>Etichetta di raggruppamento sistema</td>
<td>Immettere il testo per indicare al lavoratore gli elementi da sottoporre a scansione quando il lavoro di prelievo viene raggruppato da Supply Chain Management. Ad esempio, se si utilizza il campo <strong>ID spedizione</strong> per raggruppare il lavoro di prelievo in base alla spedizione, è possibile immettere l'<strong>ID spedizione</strong> nel campo. Per questo campo è richiesta la creazione di una voce di menu per utilizzare il lavoro esistente raggruppato dal sistema. È inoltre necessario selezionare il campo in base a cui raggruppare nel campo <strong>Raggruppamento sistema</strong>.</td>
</tr>
<tr class="even">
<td>Utilizza dati predefiniti</td>
<td>Selezionare questa opzione per abilitare il pulsante <strong>Dati predefiniti</strong> nel riquadro azioni che consente di selezionare i campi per visualizzare i dati solitamente necessari a un lavoratore per svolgere il lavoro giornaliero. Ad esempio, questa opzione è utile se un lavoratore preleva spesso gli articoli dalla stessa ubicazione. È possibile selezionare il campo <strong>Ubicazione origine</strong> per visualizzare l'ubicazione per impostazione predefinita.</td>
</tr>
<tr class="odd">
<td>Campo diretto dall'utente con convalida</td>
<td>Selezionare il campo che verrà sottoposto a scansione dal lavoratore per raggruppare il lavoro. Ad esempio, se si seleziona <strong>ID carico</strong>, un lavoratore può prelevare qualsiasi lavoro associato a un carico selezionato. È necessario immettere inoltre testo nel campo <strong>Etichetta diretta dall'utente con convalida</strong> per indicare al lavoratore gli elementi da sottoporre a scansione.</td>
</tr>
<tr class="even">
<td>Etichetta diretta dall'utente con convalida</td>
<td>Immettere il testo per indicare al lavoratore gli elementi da sottoporre a scansione quando il lavoro di prelievo viene raggruppato da un campo indirizzato dall'utente con convalida. Ad esempio, se si utilizza il campo <strong>ID carico</strong> per raggruppare il lavoro di prelievo per un carico, è possibile immettere l'<strong>ID carico</strong> nel campo.</td>
</tr>
<tr class="odd">
<td>Codice modello lavoro</td>
<td>Selezionare il modello di lavoro che crea il lavoro per un processo. Ad esempio, se si riceve un articolo per un ordine fornitore, il lavoro di stoccaggio viene generato in base al modello di lavoro. Se non si seleziona un modello di lavoro, Supply Chain Management assegna un modello, in base ai criteri di query. Per ulteriori informazioni sui modelli di lavoro, vedi <a href="control-warehouse-location-directives.md">Controllo del lavoro di magazzino con modelli di lavoro e direttive di ubicazione</a>.</td>
<tr class="even">
<td>Mostra elenco righe di lavoro</td>
<td>Seleziona un'opzione per il modo in cui i lavoratori potranno visualizzare e interagire con le righe per il lavoro di prelievo attualmente selezionato. Per altre informazioni su questa opzione, vedi <a href="pick-line-overview.md">Configurare una voce di menu del dispositivo mobile per fornire una panoramica della riga di prelievo</a>.</td>
</tr>
</tbody>
</table>

## <a name="require-workers-to-confirm-the-product-location-or-quantity-when-they-pick-items"></a>Richiedere ai lavoratori di confermare il prodotto, l'ubicazione o la quantità quando prelevano gli articoli

È possibile impostare le conferme di lavoro che richiedono a un lavoratore di utilizzare un dispositivo mobile per registrare l'ubicazione o la quantità quando esegue il lavoro nel magazzino. In questo modo è possibile garantire che il lavoratore sia nell'ubicazione corretta o stia gestendo la quantità corretta di articoli. È inoltre possibile consentire a Supply Chain Management di confermare automaticamente la registrazione del lavoratore. Se si abilita la conferma automatica, non è possibile richiedere anche le conferme per l'ubicazione o la quantità. Le conferme di lavoro includono anche i prodotti e le varianti prodotto. Inoltre, è possibile registrare le conferme eseguendo la scansione di un codice a barre. Per confermare i prodotti e le varianti prodotto, è necessario immettere un ID per il prodotto o la variante prodotto. Può essere un ID prodotto, un ID ricerca prodotti, un ID esterno, un codice GTIN o un codice a barre. Dopo aver immesso l'ID o eseguito la scansione del codice a barre, le dimensioni della variante prodotto vengono visualizzate sul dispositivo mobile. 

Nella tabella seguente sono descritti i diversi tipi di lavoro per cui è possibile utilizzare le conferme di lavoro.

| Opzione | Descrizione |
|------------------------|----------------------------------------------------------------------------|
| Preleva | Richiedere una conferma quando si prelevano articoli. |
| Inserisci | Richiedere una conferma quando si inseriscono articoli in un'ubicazione. |
| Conteggio | Richiedere una conferma durante un conteggio ciclo. |
| Rettifiche | Richiedere una conferma quando si rettificano le quantità delle scorte. |
| Personalizza | Richiedere una conferma per il lavoro personalizzato. |
| Quarantena | Richiedere una conferma quando si spostano articoli in quarantena. |
| Compilazione targa | Richiedere una conferma per il consolidamento degli articoli per compilare una targa. |
| Stampa | Richiedere una conferma quando si stampano le etichette targa. |
| Modifica stato | Richiedere una conferma quando cambia lo stato del magazzino. |

> [!NOTE]
> La conferma prodotto può essere richiesta solo per i tipi di lavoro prelievo e stoccaggio.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Impostare una voce di menu del dispositivo mobile per ultimare i lavori di tipo ordine acquisto](tasks/set-up-mobile-device-menu.md)
- [Impostare una voce di menu del dispositivo mobile per registrare gli articoli ricevuti](tasks/set-up-mobile-device-menu-item-register-received-items.md)
- [Stati inventario](../inventory/inventory-statuses.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]