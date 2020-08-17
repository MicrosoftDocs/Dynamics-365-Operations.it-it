---
title: Operazione di magazzino in uscita in POS
description: Questo argomento descrive le funzionalità dell'operazione di magazzino in uscita del punto vendita (POS).
author: hhaines
manager: annbe
ms.date: 07/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 026d25717dec8c5633f19fe63c6d6f64284d322d
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2020
ms.locfileid: "3646161"
---
# <a name="outbound-inventory-operation-in-pos"></a>Operazione di magazzino in uscita in POS

[!include [banner](includes/banner.md)]


In Microsoft Dynamics 365 Commerce versione 10.0.10 e successive, le operazioni in entrata e in uscita del punto vendita (POS) sostituiscono l'operazione di prelievo e ricezione.

> [!NOTE]
> Nella versione 10.0.10 e successive, eventuali nuove funzionalità dell'applicazione POS correlate all'inventario del negozio in entrata rispetto agli ordini fornitore e agli ordini di trasferimento verranno aggiunte alle operazioni in entrata. Se al momento si sta utilizzando l'operazione di prelievo e ricezione nel POS, consigliamo di sviluppare una strategia per passare alle nuove operazioni in entrata e in uscita. Sebbene l'operazione di prelievo e ricezione non verrà rimossa dal prodotto, non vi saranno ulteriori investimenti dal punto di vista funzionale o prestazionale, dopo la versione 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Prerequisito: configurare un framework di documenti asincrono

L'operazione in uscita include miglioramenti delle prestazioni per garantire che gli utenti con elevati volumi di registrazioni di entrata in molti negozi o aziende e di documenti di inventario, possano elaborare tali documenti presso in Commerce Headquarters senza subire timeout o guasti. Questi miglioramenti richiedono l'uso di un framework di documenti asincrono.

Quando viene utilizzato un framework di documenti asincrono, è possibile eseguire il commit delle modifiche ai documenti in uscita da POS a Commerce Headquarters e quindi passare ad altre attività mentre l'elaborazione in Commerce Headquarters viene eseguita in background. È possibile verificare lo stato del documento nella pagina elenco documenti **Operazione in uscita** nel POS per assicurarsi che la pubblicazione sia avvenuta correttamente. Nell'applicazione POS, è inoltre possibile utilizzare l'elenco dei documenti attivi dell'operazione in uscita per visualizzare tutti i documenti che non possono essere registrati in Commerce Headquarters. Se un documento ha esito negativo, gli utenti POS possono apportare correzioni e riprovare a elaborarlo in Commerce Headquarters.

> [!IMPORTANT]
> Il framework di documenti asincrono deve essere configurato prima che un'azienda tenti di utilizzare l'operazione in uscita nel POS.

Per configurare un framework di documenti asincrono, completare le seguenti procedure.

### <a name="create-and-configure-a-number-sequence"></a>Creare e configurare una sequenza numerica

1. Fare clic su **Amministrazione organizzazione \> Sequenze numeriche \> Sequenze numeriche**.
2. Nella pagina **Sequenze numeriche**, creare una sequenza numerica.
3. Nei campi **Codice sequenza numerica** e **Nome**, immettere i valori definiti dall'utente.
4. Nella Scheda dettaglio **Riferimenti** selezionare **Aggiungi**.
5. Nel campo **Area** selezionare **Parametri di commercio**.
6. Nel campo **Riferimento** selezionare **Identificatore operazione documento vendita al dettaglio**.
7. Nella scheda dettaglio **Generale** nella sezione **Impostazione**, impostare l'opzione **Continuo** su **No** per garantire che non vi siano problemi di prestazioni.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Creare e pianificare due lavori batch per le attività di elaborazione e monitoraggio dei documenti

> [!NOTE]
> In Commerce versione 10.0.13 e successive, non è necessario configurare i processi batch tramite il framework dei processi batch. I processi batch possono essere configurati dal menu **Retail e Commerce > Vendita al dettaglio e commercio IT**. Utilizzare le opzioni di menu **Monitoraggio operazione documento vendita al dettaglio** e **Elaborazione operazione documento vendita al dettaglio** per configurare i processi batch

I lavori batch creati vengono utilizzati per elaborare i documenti che hanno restituito un errore o un timeout. Saranno inoltre utilizzati quando il numero di documenti di magazzino attivi elaborati dal POS supera un valore configurato dal sistema.

1. Andare a **Amministrazione sistema \> Richieste di informazioni \> Processi batch**.
2. Nella pagina **Processo batch** creare due processi batch:

    - Configurare un processo per eseguire la classe **RetailDocumentOperationMonitorBatch**.
    - Configurare l'altro processo per eseguire la classe **RetailDocumentOperationProcessingBatch**.

3. Pianificare l'esecuzione dei nuovi processi batch su base ricorrente. Ad esempio, impostare la pianificazione in modo che i processi vengano eseguiti ogni cinque minuti.

## <a name="prerequisite-add-outbound-operation-to-the-pos-screen-layout"></a>Prerequisito: aggiungere l'operazione in uscita al layout dello schermo del POS

Prima che l'organizzazione possa utilizzare la funzionalità dell'operazione in uscita, è necessario configurare l'operazione del POS **Operazione in uscita** su uno o più [layout dello schermo del POS](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Prima di distribuire la nuova operazione in un ambiente di produzione, assicurarsi di testarla a lungo e addestrare gli utenti a usarla.

## <a name="overview"></a>Panoramica

L'operazione in uscita consente agli utenti del POS di eseguire le seguenti attività:

- Registrare le spedizioni per i documenti di ordine di trasferimento nei casi in cui il negozio dell'utente è il magazzino in uscita designato.
- Visualizzare le informazioni sulle spedizioni storiche degli ordini di trasferimento che sono state registrate dal negozio.
- Creare nuove richieste di ordini di trasferimento in uscita.

Quando l'operazione in uscita viene avviata dall'applicazione POS, viene visualizzata una pagina di elenco. Questa visualizzazione mostra i documenti di ordine di trasferimento aperti che hanno righe di magazzino che il negozio corrente dell'utente è destinato a spedire ed evadere. Per trovare un documento selezionato, gli utenti possono scorrere l'elenco o utilizzare la funzione di ricerca.

L'elenco dei documenti di magazzino in uscita ha tre schede.

- **Attivi** - Questa scheda mostra gli ordini di trasferimento con lo stato **Richiesto** o **Parzialmente spedito**. Gli ordini contengono righe o quantità su righe che devono essere spedite dal negozio corrente dell'utente. Questa scheda mostra anche gli ordini con lo stato **Elaborazione in sede centrale** (ovvero, in attesa di conferma dell'avvenuta registrazione da Commerce Headquarters) o **Elaborazione non riuscita** (ovvero la registrazione in Commerce Headquarters non è andata a buon fine e l'utente deve correggere i dati e riprovare a inviare gli ordini).
- **Bozza** - Questa scheda mostra le nuove richieste di ordini di trasferimento in uscita che il negozio dell'utente ha creato. Tuttavia, i documenti sono stati salvati solo localmente. Non sono ancora stati inviati a Commerce Headquarters per l'elaborazione.
- **Completati** - Questa scheda mostra un elenco di documenti ordine di trasferimento che il negozio ha spedito negli ultimi sette giorni. Questa scheda è fornita solo a scopo informativo. Tutte le informazioni sui documenti sono dati di sola lettura per il negozio.

Quando si visualizzano i documenti in una qualsiasi delle schede, il campo **Stato** può aiutare a capire la fase in cui si trova il documento.

- **Bozza** - Il documento ordine di trasferimento è stato salvato solo localmente nel database del canale del negozio. Nessuna informazione sulla richiesta dell'ordine di trasferimento è stata ancora inviata a Commerce Headquarters.
- **Richiesto** - L'ordine fornitore o l'ordine di trasferimento è stato creato in Commerce Headquarters ed è aperto. Il negozio corrente dell'utente ha elaborato eventuali spedizioni rispetto al documento.
- **Parzialmente spedito** - Il documento ordine di trasferimento ha una o più righe o quantità di righe parziali che sono state registrate come spedite dal magazzino in uscita. È possibile ricevere queste righe spedite tramite l'operazione in entrata.
- **Spedito in modo completo** - Tutte le righe e le quantità di righe complete dell'ordine di trasferimento sono state registrate come spedite dal magazzino in uscita.
- **In corso** - Questo stato viene utilizzato per informare gli utenti del dispositivo che il documento è in fase di elaborazione da parte di un altro utente.
- **In sospeso** - Questo stato viene visualizzato se viene selezionato **Sospendi ricezione** per interrompere temporaneamente il processo di ricezione.
- **Elaborazione in sede centrale** - Il documento è stato inviato a Commerce Headquarters dall'applicazione POS, ma non è stato ancora registrato in Commerce Headquarters. Il documento è nel processo di registrazione documento asincrono. Dopo che il documento è stato registrato in Commerce Headquarters, lo stato viene aggiornato in **Completamente ricevuto** o **Parzialmente ricevuto**.
- **Elaborazione non riuscita** - Il documento è stato inviato a Commerce Headquarters ed è stato rifiutato. Il riquadro **Dettagli** mostra il motivo dell'errore di registrazione. Il documento deve essere modificato per risolvere i problemi relativi ai dati, quindi deve essere inviato nuovamente a Commerce Headquarters per l'elaborazione.

Quando si seleziona una riga del documento nell'elenco, viene visualizzato il riquadro **Dettagli**. Questo riquadro mostra ulteriori informazioni sul documento, come le informazioni sulla spedizione e sulla data. Una barra di avanzamento mostra quanti articoli devono ancora essere elaborati. Se il documento non viene elaborato correttamente in Commerce Headquarters, il riquadro **Dettagli** mostra anche i messaggi di errore correlati.

Nella visualizzazione della pagina dell'elenco documenti, è possibile selezionare **Dettagli ordine** sulla barra dell'app per visualizzare i dettagli del documento. È inoltre possibile attivare l'elaborazione della ricezione per le righe del documento idonee.

Nella visualizzazione della pagina elenco documenti, è anche possibile creare un nuovo ordine di trasferimento in uscita per un negozio.

## <a name="transfer-order-shipping-process"></a>Processo spedizione ordine di trasferimento

Dopo aver selezionato un documento ordine di trasferimento nella scheda **Attivi**, è possibile selezionare **Dettagli ordine** per iniziare il processo di evasione. Viene visualizzata la pagina **Elenco completo ordini**. Questa pagina mostra tutte le righe del documento che contengono l'articolo. Mostra anche i dettagli della quantità ordinata.

Ogni scansione di un codice a barre aggiorna la quantità nel campo **In spedizione ora** di un'unità. In alternativa, è possibile inserire una quantità di spedizione selezionando **Spedisci prodotto** sulla barra dell'app, inserendo un ID articolo, quindi inserendo la quantità. Se l'articolo è controllato in base all'ubicazione, è possibile confermare o impostare l'ubicazione di spedizione per la riga del documento.

Nella pagina **Elenco completo ordini**, è possibile selezionare manualmente una riga nell'elenco e quindi aggiornare la quantità **In spedizione ora** per la riga selezionata nel riquadro **Dettagli**.

### <a name="over-delivery-shipping-validations"></a>Convalide della spedizione per consegna in eccesso

Le convalide si verificano durante il processo di ricezione per le righe del documento. Includono le convalide per consegna in eccesso. Se un utente tenta di ricevere più scorte di quelle ordinate in un ordine fornitore ma la consegna in eccesso non è configurata o la quantità ricevuta supera la tolleranza di consegna in eccesso configurata per la riga dell'ordine fornitore, l'utente riceve un errore e non è consentito ricevere la quantità in eccesso.

### <a name="underdelivery-close-lines"></a>Riga chiusura limite minimo di fornitura

In Commerce versione 10.0.12, è stata aggiunta la funzionalità che consente agli utenti POS di chiudere o annullare le quantità rimanenti durante la spedizione dell'ordine in uscita se il magazzino in uscita determina che non può spedire l'intera quantità richiesta. Le quantità possono anche essere chiuse o cancellate in seguito. Per utilizzare questa funzionalità, la società deve essere configurata per consentire il limite minimo di fornitura degli ordini di trasferimento. Inoltre, una percentuale del limite minimo di fornitura deve essere definita per la riga dell'ordine di trasferimento.

Per configurare la società in modo da consentire il limite minimo di fornitura degli ordini di trasferimento, in Commerce Headquarters, visita **Gestione inventario \> Impostazione \> Parametri di gestione articoli e magazzino**. Nella pagina **Parametri di gestione articoli e magazzino**, nella scheda **Ordini di trasferimento**, attiva il parametro **Accetta limite minimo di fornitura**. Quindi esegui il processo Retail Scheduler **1070** di distribuzione per sincronizzare le modifiche ai parametri al canale del negozio.

Le percentuali di limite minimo di fornitura per una riga di ordine di trasferimento possono essere predefinite sui prodotti come parte della configurazione del prodotto in Commerce Headquarters. In alternativa, possono essere impostate o sovrascritte su una specifica riga dell'ordine di trasferimento tramite Commerce Headquarters.

Dopo che un'organizzazione completa la configurazione del limite minimo di fornitura dell'ordine di trasferimento, gli utenti POS vedranno una nuova opzione **Chiudi quantità rimanente** nel pannello **Dettagli** quando selezionano una riga ordine di trasferimento in uscita tramite la funzione **Operazione in uscita**. Quando l'utente completa la spedizione utilizzando l'operazione **Termina evasione**, possono inviare una richiesta a Commerce Headquarters per annullare la quantità non spedita rimanente. Se l'utente chiude la quantità rimanente, Commerce effettua una convalida per verificare che la quantità annullata rientri nella tolleranza della percentuale del limite minimo di fornitura definita nella riga dell'ordine di trasferimento. Se viene superata la tolleranza del limite minimo di fornitura, viene visualizzato un messaggio di errore e l'utente non sarà in grado di chiudere la quantità rimanente fino a quando la quantità precedentemente spedita e la quantità "da spedire ora" soddisfa o supera la tolleranza del limite minimo di fornitura.

Dopo che la spedizione è stata sincronizzata con Commerce Headquarters, le quantità definite nel campo **Spedisci ora** per la riga dell'ordine di trasferimento in POS vengono aggiornate allo stato spedito in Commerce Headquarters. Le quantità non spedite che in precedenza sarebbero state considerate quantità "rimanenza spedizione" (ovvero quantità che verranno spedite in un secondo momento) sono invece considerate quantità annullate. La quantità "rimanenza spedizione" per la riga dell'ordine di trasferimento è impostata su **0** (zero) e la riga è considerata completamente spedita.

### <a name="shipping-location-controlled-items"></a>Spedizione di articoli controllati in base alla posizione

Se gli articoli che vengono spediti sono controllati in base alla posizione, gli utenti possono selezionare la posizione da cui desiderano far uscire le scorte durante il processo di spedizione. Consigliamo di configurare una posizione di uscita predefinita per il magazzino del negozio, per rendere questo processo più efficiente. Anche se è configurata una posizione predefinita, gli utenti possono sovrascrivere la posizione di uscita sulle righe selezionate come necessario.

L'operazione rispetta la configurazione **Entrata non specificata consentita** nelle dimensioni di immagazzinamento della **Ubicazione** e non richiede l'inserimento di una dimensione di ubicazione se è configurata l'entrata non specificata. Se per un articolo non sono consentite le ubicazioni con entrata non specificata, l'applicazione POS restituisce un errore e richiede l'inserimento di un'ubicazione prima di poter registrare l'entrata.

### <a name="ship-all"></a>Spedisci tutto

Quando necessario, è possibile selezionare **Spedisci tutto** sulla barra dell'app per aggiornare rapidamente la quantità **In spedizione ora** per tutte le righe del documento fino al valore massimo disponibile per l'evasione di quelle righe.

### <a name="cancel-fulfillment"></a>Annulla evasione

Utilizzare la funzione **Annulla evasione** sulla barra dell'app solo se si desidera uscire dal documento e non si desidera salvare alcuna modifica. Ad esempio, inizialmente è stato selezionato il documento errato e non si desidera salvare nessuno dei dati di spedizione precedenti.

### <a name="pause-fulfillment"></a>Metti in pausa evasione

Se si evade l'ordine di trasferimento, è possibile utilizzare la funzione **Sospendi evasione** se si desidera sospendere il processo di evasione. Ad esempio, è possibile eseguire un'altra operazione dal POS, ad esempio telefonare all'addetto alle vendite di un cliente o ritardare la registrazione della spedizione in Commerce Headquarters.

Quando si seleziona **Sospendi evasione**, lo stato del documento diventa **In sospeso**. Pertanto, gli utenti sapranno che sono stati immessi dei dati nel documento, ma il documento non è stato ancora stato sottoposto al commit. Quando si è pronti per riprendere il processo di evasione, selezionare il documento in sospeso, quindi selezionare **Dettagli ordine**. Qualunque quantità **In spedizione ora** precedentemente salvata viene conservata e può essere visualizzata dalla visualizzazione **Elenco completo ordini**.

### <a name="review"></a>Rivedi

Prima dell'impegno finale dell'evasione per Commerce Headquarters (HQ), è possibile utilizzare la funzione **Revisione** per convalidare il documento in uscita. Questa funzione avviserà di eventuali dati mancanti o errati che potrebbero causare errori di elaborazione e darà l'opportunità di correggere i problemi prima di inviare la richiesta di evasione. Per abilitare la funzione **Revisione** sulla barra delle applicazioni, abilitare la funzionalità **Abilita convalida nelle operazioni di magazzino POS in entrata e in uscita** tramite l'area di lavoro Gestione funzionalità in Commerce Headquarters (HQ).

La funzione **Revisione** convalida i seguenti problemi in un documento in uscita:
- **Spedizione in eccesso**: la quantità spedita ora è maggiore della quantità ordinata. La gravità di questo problema è determinata dalla configurazione di consegna in eccesso in Commerce Headquarters (HQ).
- **Spedizione in difetto**: la quantità spedita ora è minore della quantità ordinata. La gravità di questo problema è determinata dalla configurazione di consegna in difetto in Commerce Headquarters (HQ).
- **Numero di serie**: il numero seriale non viene fornito o non è disponibile per un articolo serializzato che richiede la registrazione del numero di serie nell'inventario.
- **Ubicazione non impostata**: l'ubicazione non è specificata per un elemento controllato in base all'ubicazione in cui non è consentita l'ubicazione vuota.
- **Righe eliminate**: l'ordine include righe eliminate da un utente Commerce Headquarters (HQ) che non è noto all'applicazione POS.

Se si imposta il parametro **Abilita convalida automatica** su **Sì** in **Parametri di Commerce** > **Inventario** > **Scorte di magazzino** per fare eseguire automaticamente la convalida quando si seleziona la funzione **Termina la ricezione** .

### <a name="finish-fulfillment"></a>Termina evasione

Una volta inserite tutte le quantità **In spedizione ora** per i prodotti, è necessario selezionare **Termina evasione** sulla barra dell'app.

Quando viene utilizzata l'elaborazione di documenti asincrona, la ricevuta viene inviata attraverso un framework di documenti asincrono. Il tempo necessario per la registrazione del documento dipende dalle dimensioni del documento (il numero di righe) e dal traffico di elaborazione generale che si verifica sul server. In genere, questo processo avviene in pochi secondi. Se la registrazione di documenti non riesce, l'utente viene avvisato tramite l'elenco dei documenti **Operazione in uscita** nella scheda **Attivi** in cui verrà aggiornato lo stato del documento su **Elaborazione non riuscita**. L'utente può quindi selezionare il documento non riuscito nel POS per visualizzare i messaggi di errore e il motivo dell'errore nel riquadro **Dettagli**. Un documento non riuscito rimane non registrato e richiede che l'utente ritorni alle righe del documento selezionando **Dettagli ordine** nel POS. L'utente deve quindi aggiornare il documento apportando le correzioni in base agli errori. Dopo aver corretto il documento, l'utente può riprovare a elaborarlo selezionando **Termina evasione** sulla barra dell'app.

## <a name="create-an-outbound-transfer-order"></a>Creare un ordine di trasferimento in uscita

Dal POS, gli utenti possono creare nuovi documenti ordine di trasferimento. Per iniziare il processo, selezionare **Nuovo** sulla barra delle app mentre è aperto l'elenco documenti principale **Operazione in uscita**. Viene quindi richiesto di selezionare un magazzino o un negozio a cui **trasferire** le scorte dal negozio corrente. I valori sono limitati alla selezione definita nella configurazione del gruppo di evasione del negozio. In una richiesta di trasferimento in uscita, il negozio attuale sarà sempre il magazzino da cui **trasferire** per l'ordine di trasferimento. Il valore non può essere modificato.

È possibile inserire valori nei campi **Data spedizione**, **Data di ricezione** e **Modalità di spedizione** come richiesto. È inoltre possibile aggiungere una nota che verrà archiviata insieme all'intestazione dell'ordine di trasferimento, come allegato al documento in Commerce Headquarters.

Dopo aver creato le informazioni dell'intestazione, è possibile aggiungere prodotti all'ordine di trasferimento. Per avviare il processo di aggiunta di articoli e quantità richieste, eseguire la scansione dei codici a barre o selezionare **Aggiungi prodotto**.

Dopo aver inserito le righe nell'ordine di trasferimento in uscita, è necessario selezionare **Salva** per salvare le modifiche del documento localmente o **Invia richiesta** per inviare i dettagli dell'ordine a Commerce Headquarters per ulteriori elaborazioni. Se si seleziona **Salva**, il documento bozza viene archiviato nel database del canale e il magazzino in uscita non può eseguire il documento fino a quando non viene elaborato correttamente tramite **Invia richiesta**. Selezionare **Salva** solo se non si è pronti a inviare la richiesta a Commerce Headquarters per l'elaborazione.

Se un documento viene salvato localmente, è disponibile nella scheda **Bozze** dell'elenco documenti **Operazione in entrata**. Quando un documento è nello stato **Bozza** è possibile modificarlo selezionando **Modifica**. È possibile aggiornare, aggiungere o eliminare le righe secondo le necessità. Inoltre, è possibile eliminare l'intero documento in stato **Bozza** selezionando **Elimina** nella scheda **Bozze**.

Quando il documento in bozza viene correttamente inviato a Commerce Headquarters, viene visualizzato nella scheda **Attivi** con lo stato **Richiesto**. A questo punto, solo gli utenti nel magazzino in uscita possono modificare il documento, selezionando **Operazione in uscita** nell'applicazione POS. Gli utenti del magazzino in entrata possono visualizzare l'ordine di trasferimento nella scheda **Attivi** dell'elenco documenti **Operazione in entrata**, ma non possono modificarlo o eliminarlo. Il blocco delle modifiche garantisce che non si verifichino conflitti perché un richiedente in entrata modifica l'ordine di trasferimento mentre lo spedizioniere in uscita sta attivamente prelevando e spedendo l'ordine. Se sono necessarie modifiche dal negozio o dal magazzino in entrata dopo l'invio dell'ordine di trasferimento, è necessario contattare lo spedizioniere in uscita e chiedere di inserire le modifiche.

Quando il documento è nello stato **Richiesto** è pronto per l'elaborazione dell'evasione da parte del magazzino in uscita. Mentre la spedizione viene elaborata dall'operazione di uscita, lo stato dei documenti ordine di trasferimento viene aggiornato da **Richiesto** in **Spedito in modo completo** o **Parzialmente spedito**. Dopo che i documenti sono nello stato **Spedito in modo completo** o **Parzialmente spedito**, il negozio o il magazzino in entrata possono registrare le entrate utilizzando il processo di ricezione dell'operazione in entrata.

Gli ordini di trasferimento spediti in modo completo vengono spostati nella scheda **Completati** dell'elenco documenti **Operazione in uscita**. In questa scheda rimangono visibili agli utenti del negozio o del magazzino in uscita, in modalità di sola lettura, per sette giorni.

## <a name="related-topics"></a>Argomenti correlati

[Operazione di magazzino in ingresso in POS](pos-inbound-inventory-operation.md)
