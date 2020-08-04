---
title: Operazione di magazzino in ingresso in POS
description: Questo argomento descrive le funzionalità dell'operazione di magazzino in entrata del punto vendita (POS).
author: hhaines
manager: annbe
ms.date: 07/10/2020
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
ms.openlocfilehash: cf3bec8ab0bfafccfe4b2b5b245d00fd6aeff635
ms.sourcegitcommit: 037712e348fcbf3569587089bd668ee7bf5567ff
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "3551603"
---
# <a name="inbound-inventory-operation-in-pos"></a>Operazione di magazzino in ingresso in POS

[!include [banner](includes/banner.md)]

In Microsoft Dynamics 365 Commerce versione 10.0.10 e successive, le operazioni in entrata e in uscita del punto vendita (POS) sostituiscono l'operazione di prelievo e ricezione.

> [!NOTE]
> Nella versione 10.0.10 e successive, eventuali nuove funzionalità dell'applicazione POS correlate all'inventario del negozio in entrata rispetto agli ordini fornitore e agli ordini di trasferimento verranno aggiunte alle **operazioni in entrata** del POS. Se al momento si sta utilizzando l'operazione di prelievo e ricezione nel POS, consigliamo di sviluppare una strategia per passare alle nuove operazioni in entrata e in uscita. Sebbene l'operazione di prelievo e ricezione non verrà rimossa dal prodotto, non vi saranno ulteriori investimenti dal punto di vista funzionale o prestazionale, dopo la versione 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Prerequisito: configurare un framework di documenti asincrono

L'operazione in entrata include miglioramenti delle prestazioni per garantire che gli utenti con elevati volumi di registrazioni di entrata in molti negozi o aziende e di documenti di inventario, possano elaborare tali documenti presso in Commerce Headquarters senza subire timeout o guasti. Questi miglioramenti richiedono l'uso di un framework di documenti asincrono.

Quando viene utilizzato un framework di documenti asincrono, è possibile eseguire il commit delle modifiche ai documenti in entrata da POS a Commerce Headquarters e quindi passare ad altre attività mentre l'elaborazione in Commerce Headquarters viene eseguita in background. È possibile verificare lo stato del documento nella pagina elenco documenti **Operazione in entrata** nel POS per assicurarsi che la pubblicazione sia avvenuta correttamente. Nell'applicazione POS, è inoltre possibile utilizzare l'elenco dei documenti attivi dell'operazione in entrata per visualizzare tutti i documenti che non possono essere registrati in Commerce Headquarters. Se un documento ha esito negativo, gli utenti POS possono apportare correzioni e riprovare a elaborarlo in Commerce Headquarters.

> [!IMPORTANT]
> Il framework di documenti asincrono deve essere configurato prima che un'azienda tenti di utilizzare l'operazione in entrata nel POS.

Per configurare un framework di documenti asincrono, completare le seguenti procedure.

### <a name="create-and-configure-a-number-sequence"></a>Creare e configurare una sequenza numerica

1. Fare clic su **Amministrazione organizzazione \> Sequenze numeriche \> Sequenze numeriche**.
2. Nella pagina **Sequenze numeriche**, creare una sequenza numerica.
3. Nei campi **Codice sequenza numerica** e **Nome**, immettere i valori definiti dall'utente.
4. Nella Scheda dettaglio **Riferimenti** selezionare **Aggiungi**.
5. Nel campo **Area** selezionare **Parametri di commercio**.
4. Nel campo **Riferimento** selezionare **Identificatore operazione documento vendita al dettaglio**.
5. Nella scheda dettaglio **Generale** nella sezione **Impostazione**, impostare l'opzione **Continuo** su **No** per garantire che non vi siano problemi di prestazioni.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Creare e pianificare due lavori batch per le attività di elaborazione e monitoraggio dei documenti

> [!NOTE]
> In Commerce versione 10.0.13 e successive, non è necessario configurare questi processi batch tramite il framework dei processi batch. I processi batch possono essere configurati dal menu **Retail e Commerce > Vendita al dettaglio e commercio IT**. Utilizzare le opzioni di menu **Monitoraggio operazione documento vendita al dettaglio** e **Elaborazione operazione documento vendita al dettaglio** per configurare i processi batch.

I lavori batch creati vengono utilizzati per elaborare i documenti che hanno restituito un errore o un timeout. Saranno inoltre utilizzati quando il numero di documenti di magazzino attivi elaborati dal POS supera un valore configurato dal sistema.

1. Andare a **Amministrazione sistema \> Richieste di informazioni \> Processi batch**.
2. Nella pagina **Processo batch** creare due processi batch:

    - Configurare un processo per eseguire la classe **RetailDocumentOperationMonitorBatch**.
    - Configurare l'altro processo per eseguire la classe **RetailDocumentOperationProcessingBatch**.

2. Pianificare l'esecuzione dei nuovi processi batch su base ricorrente. Ad esempio, impostare la pianificazione in modo che i processi vengano eseguiti ogni cinque minuti.

## <a name="prerequisite-add-inbound-operation-to-the-pos-screen-layout"></a>Prerequisito: aggiungere l'operazione in entrata al layout dello schermo del POS

Prima che l'organizzazione possa utilizzare la funzionalità dell'operazione in entrata, è necessario configurare l'operazione del POS **Operazione in entrata** su uno o più [layout dello schermo del POS](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Prima di distribuire la nuova operazione in un ambiente di produzione, assicurarsi di testarla a lungo e addestrare gli utenti a usarla.

## <a name="overview"></a>Panoramica

L'operazione in entrata consente agli utenti del POS di eseguire le seguenti attività:

- Ricevere le scorte nello stock del negozio da documenti di ordini fornitore confermati o documenti di ordini di trasferimento spediti.
- Visualizzare le informazioni sulle entrate in magazzino storiche per un periodo di sette giorni dopo la completa ricezione del documento.
- Creare nuove richieste di ordini di trasferimento in entrata.

Quando l'operazione in entrata viene avviata dall'applicazione POS, viene visualizzata una pagina di elenco. Questa visualizzazione mostra i documenti di ordine fornitore e ordine di trasferimento aperti che hanno righe di magazzino pianificate per essere ricevute dal negozio corrente. Per trovare e selezionare un documento specifico, gli utenti possono scorrere l'elenco o utilizzare la funzione di ricerca.

L'elenco dei documenti di magazzino in entrata ha tre schede:

- **Attivi** - Questa scheda mostra i documenti che sono completamente o parzialmente aperti e che contengono righe o quantità su righe che devono ancora essere ricevute.
- **Bozza** - Questa scheda mostra le nuove richieste di ordini di trasferimento in entrata che il negozio ha creato. Tuttavia, i documenti sono stati salvati solo localmente. Non sono ancora stati inviati a Commerce Headquarters per l'elaborazione.
- **Completati** - Questa scheda mostra un elenco di documenti ordine fornitore o ordine di trasferimento che il negozio ha ricevuto negli ultimi sette giorni. Questa scheda è fornita solo a scopo informativo. Tutte le informazioni sui documenti sono dati di sola lettura per il negozio.

Quando si visualizzano i documenti in una qualsiasi delle schede, il campo **Stato** può aiutare a capire la fase in cui si trova il documento.

- **Bozza** - Il documento ordine di trasferimento è stato salvato solo localmente nel database del canale del negozio. Nessuna informazione sulla richiesta dell'ordine di trasferimento è stata ancora inviata a Commerce Headquarters.
- **Richiesto** - L'ordine fornitore o l'ordine di trasferimento è stato creato in Commerce Headquarters ed è aperto. Nessuna entrata è stata ancora elaborata rispetto al documento. Per i documenti del tipo di documento ordine fornitore, l'entrata può iniziare in qualsiasi momento mentre lo stato è **Richiesto**.
- **Parzialmente spedito** - Il documento ordine di trasferimento ha una o più righe o quantità di righe parziali che sono state registrate come spedite dal magazzino in uscita. È possibile ricevere queste righe spedite tramite l'operazione in entrata.
- **Spedito in modo completo** - Tutte le righe e le quantità di righe complete dell'ordine di trasferimento sono state registrate come spedite dal magazzino in uscita. È possibile ricevere l'intero documento tramite l'operazione in entrata.
- **Parzialmente ricevuto** - Alcune delle righe o quantità di righe nel documento ordine fornitore od ordine di trasferimento sono state ricevute dal negozio, ma alcune righe rimangono aperte.
- **Completamente ricevuto** - Tutte le righe e le quantità nel documento ordine fornitore od ordine di trasferimento sono state interamente ricevute. I documenti sono accessibili solo nella scheda **Completato** e sono di sola lettura per gli utenti del negozio.
- **In corso** - Questo stato viene utilizzato per informare gli utenti del dispositivo che il documento è in fase di elaborazione da parte di un altro utente.
- **In sospeso** - Questo stato viene visualizzato se viene selezionato **Sospendi ricezione** per interrompere temporaneamente il processo di ricezione.
- **Elaborazione in sede centrale** - Il documento è stato inviato a Commerce Headquarters dall'applicazione POS, ma non è stato ancora registrato in Commerce Headquarters. Il documento è nel processo di registrazione documento asincrono. Dopo che il documento è stato registrato in Commerce Headquarters, lo stato viene aggiornato in **Completamente ricevuto** o **Parzialmente ricevuto**.
- **Elaborazione non riuscita** - Il documento è stato inviato a Commerce Headquarters ed è stato rifiutato. Il riquadro **Dettagli** mostra il motivo dell'errore di registrazione. Il documento deve essere modificato per risolvere i problemi relativi ai dati, quindi deve essere inviato nuovamente a Commerce Headquarters per l'elaborazione.

Quando si seleziona una riga del documento nell'elenco, viene visualizzato il riquadro **Dettagli**. Questo riquadro mostra ulteriori informazioni sul documento, come le informazioni sulla spedizione e sulla data. Una barra di avanzamento mostra quanti articoli devono ancora essere elaborati. Se il documento non viene elaborato correttamente in Commerce Headquarters, il riquadro **Dettagli** mostra anche i messaggi di errore correlati.

Nella visualizzazione della pagina dell'elenco documenti, è possibile selezionare **Dettagli ordine** sulla barra dell'app per visualizzare i dettagli del documento. È inoltre possibile attivare l'elaborazione della ricezione per le righe del documento idonee.

Nella visualizzazione della pagina elenco documenti, è anche possibile creare una nuova richiesta di ordine di trasferimento in entrata per un negozio. I documenti rimangono nello stato **Bozza** e possono essere regolati o eliminati fino a quando non vengono inviati a Commerce Headquarters per l'elaborazione. Dopo che sono stati inviati a Commerce Headquarters , le righe dell'ordine di trasferimento non possono più essere modificate dall'applicazione POS.

## <a name="receiving-process"></a>Processo di ricezione

Dopo aver selezionato un documento ordine fornitore od ordine di trasferimento nella scheda **Attivi**, è possibile selezionare **Dettagli ordine** per iniziare il processo di ricevimento.

Per impostazione predefinita, viene visualizzazione la pagina **In ricevimento ora**. Questa visualizzazione è ottimizzata per la scansione di codici a barre. Può essere utilizzata per creare un elenco degli articoli che sono stati scansionati, in modo che tali articoli possano essere ricevuti. Per iniziare il processo di ricevimento, è possibile iniziare la scansione dei codici a barre degli articoli.

Mentre i codici a barre degli articoli vengono scansionati nella visualizzazione **In ricevimento ora**, l'applicazione convalida gli articoli rispetto al documento di acquisto o di trasferimento selezionato, per assicurarsi che ciascun articolo scansionato corrisponda a un articolo valido del documento. Nella visualizzazione **In ricevimento ora** si presume che ogni scansione di codice a barre rappresenti l'entrata di una quantità di un'unità, a meno che una quantità non sia incorporata nel codice a barre. È possibile scansionare ripetutamente i codici a barre in questa visualizzazione per creare un elenco di tutti gli articoli e le quantità per il ricevimento.

### <a name="example-scenario"></a>Scenario di esempio

Un utente riceve un ordine fornitore che contiene 10 unità del codice a barre 5657900266. L'utente può scansionare quel codice a barre 10 volte per aggiornare il campo **In ricevimento ora** di un'unità per scansione. Quando l'utente ha completato le scansioni, il campo **In ricevimento ora** per la riga dell'articolo mostrerà che è stata ricevuta una quantità di 10.

In alternativa, in uno scenario in cui la quantità di articoli è elevata, l'utente potrebbe scegliere di immettere manualmente la quantità anziché scansionare il codice a barre per ciascun articolo ricevuto. In questo caso, l'utente può eseguire la scansione del codice a barre una volta per aggiungere l'articolo all'elenco **In ricevimento ora**. L'utente può quindi selezionare la riga associata in **In ricevimento ora** e quindi, nel riquadro **Dettagli** sul lato destro della pagina, aggiornare il campo **Quantità ricevuta** per l'articolo.

Sebbene la visualizzazione **In ricevimento ora** sia ottimizzata per la scansione del codice a barre, gli utenti possono anche selezionare **Ricevi prodotto** sulla barra dell'app, quindi immettere l'ID elemento o il codice a barre tramite una finestra di dialogo. Dopo la convalida dell'articolo inserito, all'utente viene richiesto di inserire la quantità ricevuta.

La visualizzazione **In ricevimento ora** fornisce agli utenti un modo mirato di vedere quali prodotti si stanno ricevendo. In alternativa, può essere usata la visualizzazione **Elenco completo ordini**. Questa visualizzazione mostra l'intero elenco delle righe per il documento ordine fornitore od ordine di trasferimento selezionato. Gli utenti possono selezionare manualmente le righe nell'elenco e, quindi, nel riquadro **Dettagli** aggiornare il campo **Quantità ricevuta** per la riga selezionata. Nella visualizzazione **Elenco completo ordini** gli utenti possono eseguire la scansione dei codici a barre o possono utilizzare la funzione **Ricevi prodotto** per inserire l'ID articolo o il codice a barre e i dati sulla quantità ricevuta, senza dover prima selezionare la riga articolo corrispondente nell'elenco.

### <a name="over-receiving-validations"></a>Convalide entrate eccessive

Le convalide si verificano durante il processo di ricezione per le righe del documento. Includono le convalide per consegna in eccesso. Se un utente tenta di ricevere più scorte di quelle ordinate in un ordine fornitore ma la consegna in eccesso non è configurata o l'importo ricevuto supera la tolleranza di consegna in eccesso configurata per la riga dell'ordine fornitore, l'utente riceve un errore e non è consentito ricevere la quantità in eccesso.

Le entrate eccessive non sono consentite per i documenti ordine di trasferimento. Gli utenti riceveranno sempre errori se provano a ricevere più di quanto è stato spedito per la riga dell'ordine di trasferimento.

### <a name="receiving-location-controlled-items"></a>Ricezione di articoli controllati in base alla posizione

Se gli articoli che vengono ricevuti sono controllati in base alla posizione, gli utenti possono selezionare la posizione in cui desiderano ricevere gli articoli durante il processo di ricezione. Consigliamo di configurare una posizione di ricezione predefinita per il magazzino del negozio, per rendere questo processo più efficiente. Anche se è configurata una posizione predefinita, gli utenti possono sovrascrivere la posizione di ricezione sulle righe selezionate come necessario.

L'operazione rispetta la configurazione **Entrata non specificata consentita** nelle dimensioni di immagazzinamento della **Ubicazione** e non richiede l'inserimento di una dimensione di ubicazione se è configurata l'entrata non specificata. Se per un articolo non sono consentite le ubicazioni con entrata non specificata, l'applicazione POS restituisce un errore e richiede l'inserimento di un'ubicazione prima di poter registrare l'entrata.

### <a name="receive-all"></a>Ricevi tutto

Quando necessario, è possibile selezionare **Ricevi tutto** sulla barra dell'app per aggiornare rapidamente la quantità **In ricevimento ora** per tutte le righe del documento fino al valore massimo disponibile per l'entrata di quelle righe.

### <a name="cancel-receiving"></a>Annulla ricezione

È necessario usare la funzione **Annulla ricezione** sulla barra dell'app solo se si desidera uscire dal documento e non si desidera salvare alcuna modifica. Ad esempio, inizialmente è stato selezionato il documento errato e non si desidera salvare nessuno dei dati di ricezione precedenti.

### <a name="pause-receiving"></a>Metti in pausa ricezione

Se si ricevono le scorte, è possibile utilizzare la funzione **Sospendi ricezione** se si desidera sospendere il processo di ricezione. Ad esempio, è possibile eseguire un'altra operazione dal POS, ad esempio telefonare all'addetto alle vendite di un cliente o ritardare la registrazione della ricezione.

Quando si seleziona **Sospendi ricezione**, lo stato del documento diventa **In sospeso**. Pertanto, gli utenti sapranno che sono stati immessi dei dati per il documento, ma il documento non è stato ancora stato sottoposto al commit. Quando si è pronti per riprendere il processo di ricezione, selezionare il documento in sospeso, quindi selezionare **Dettagli ordine**. Qualunque quantità **In ricevimento ora** precedentemente salvata viene conservata e può essere visualizzata dalla visualizzazione **Elenco completo ordini**.

### <a name="finish-receiving"></a>Termina ricezione

Una volta inserite tutte le quantità **In ricevimento ora** per i prodotti, è necessario selezionare **Termina ricezione** sulla barra dell'app per elaborare la ricezione.

Quando gli utenti completano la ricezione dell'ordine fornitore, viene richiesto di immettere un valore nel campo **Numero ricevuta**, se questa funzionalità è configurata. In genere, questo valore equivale all'identificatore della bolla di accompagnamento del fornitore. Il **Numero ricevuta** viene archiviato nel giornale di registrazione dei prodotti in Commerce Headquarters. I numeri delle ricevute non vengono acquisiti per le ricevute dell'ordine di trasferimento.

Quando viene utilizzata l'elaborazione di documenti asincrona, la ricevuta viene inviata attraverso un framework di documenti asincrono. Il tempo necessario per la registrazione del documento dipende dalle dimensioni del documento (il numero di righe) e dal traffico di elaborazione generale che si verifica sul server. In genere, questo processo avviene in pochi secondi. Se la registrazione di documenti non riesce, l'utente viene avvisato tramite l'elenco dei documenti **Operazione in entrata** in cui verrà aggiornato lo stato del documento su **Elaborazione non riuscita**. L'utente può quindi selezionare il documento non riuscito nel POS per visualizzare i messaggi di errore e il motivo dell'errore nel riquadro **Dettagli**. Un documento non riuscito rimane non registrato e richiede che l'utente ritorni alle righe del documento selezionando **Dettagli ordine** nel POS. L'utente deve quindi aggiornare il documento apportando le correzioni in base agli errori. Dopo aver corretto il documento, l'utente può riprovare a elaborarlo selezionando **Termina evasione** sulla barra dell'app.

## <a name="create-an-inbound-transfer-order"></a>Creare un ordine di trasferimento in entrata

Dal POS, gli utenti possono creare nuovi documenti ordine di trasferimento. Per iniziare il processo, selezionare **Nuovo** sulla barra delle app mentre è aperto l'elenco documenti principale **Operazione in entrata**. Viene quindi richiesto di selezionare un magazzino o un negozio da cui **trasferire** che fornirà le scorte all'ubicazione del negozio. I valori sono limitati alla selezione definita nella configurazione del gruppo di evasione del negozio. In una richiesta di trasferimento in entrata, il negozio attuale sarà sempre il magazzino a cui **trasferire** per l'ordine di trasferimento. Il valore non può essere modificato.

È possibile inserire valori nei campi **Data spedizione**, **Data di ricezione** e **Modalità di spedizione** come richiesto. È inoltre possibile aggiungere una nota che verrà archiviata insieme all'intestazione dell'ordine di trasferimento, come allegato al documento in Commerce Headquarters.

Dopo aver creato le informazioni dell'intestazione, è possibile aggiungere prodotti all'ordine di trasferimento. Per avviare il processo di aggiunta di articoli e quantità richieste, selezionare **Aggiungi prodotto**. Nel riquadro **Dettagli**, è inoltre possibile aggiungere una nota specifica della riga alle righe del giornale di registrazione. Queste note verranno archiviate come allegato della riga.

Dopo aver inserito le righe nell'ordine di trasferimento in entrata, è necessario selezionare **Salva** per salvare le modifiche del documento localmente o **Invia richiesta** per inviare i dettagli dell'ordine a Commerce Headquarters per ulteriori elaborazioni. Se si seleziona **Salva**, il documento bozza viene archiviato nel database del canale e il magazzino in uscita non può eseguire il documento fino a quando non viene elaborato correttamente tramite **Invia richiesta**. Selezionare **Salva** solo se non si è pronti a inviare la richiesta a Commerce Headquarters per l'elaborazione.

Se un documento viene salvato localmente, è disponibile nella scheda **Bozze** dell'elenco documenti **Operazione in entrata**. Quando un documento è nello stato **Bozza** è possibile modificarlo selezionando **Modifica**. È possibile aggiornare, aggiungere o eliminare le righe secondo le necessità. Inoltre, è possibile eliminare l'intero documento in stato **Bozza** selezionando **Elimina** nella scheda **Bozze**.

Quando il documento in bozza viene correttamente inviato a Commerce Headquarters, viene visualizzato nella scheda **Attivi** con lo stato **Richiesto**. A questo punto, gli utenti nel negozio o nel magazzino in entrata non possono più modificare il documento dell'ordine di trasferimento in entrata richiesto. Solo gli utenti nel magazzino in uscita possono modificare il documento, selezionando **Operazione in uscita** nell'applicazione POS. Il blocco delle modifiche garantisce che non si verifichino conflitti perché un richiedente in entrata modifica l'ordine di trasferimento mentre lo spedizioniere in uscita sta attivamente prelevando e spedendo l'ordine. Se sono necessarie modifiche dal negozio o dal magazzino in entrata dopo l'invio dell'ordine di trasferimento, è necessario contattare lo spedizioniere in uscita e chiedere di inserire le modifiche.

Quando il documento è nello stato **Richiesto**, è visibile nella scheda **Attivi**. Tuttavia, non può ancora essere ricevuto dal negozio o dal magazzino in entrata. Dopo che il magazzino in uscita ha spedito completamente o parzialmente l'ordine di trasferimento, il negozio o il magazzino in entrata possono registrare le entrate nel POS. Quando il lato in uscita elabora i documenti ordine di trasferimento, lo stato viene aggiornato da **Richiesto** a **Spedito** o **Parzialmente spedito**. Dopo che i documenti sono nello stato **Spedito** o **Parzialmente spedito**, il negozio o il magazzino in entrata possono registrare le entrate utilizzando il processo di ricezione dell'operazione in entrata.

## <a name="related-topics"></a>Argomenti correlati

[Operazione di magazzino in uscita in POS](pos-outbound-inventory-operation.md)
