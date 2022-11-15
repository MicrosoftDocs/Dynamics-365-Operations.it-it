---
title: Imposta i piani generali
description: In questo articolo vengono descritte varie strategie e parametri importanti utilizzati per impostare la pianificazione generale.
author: t-benebo
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 150e02916e056946016155d1b4969e99fbd47af5
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740659"
---
# <a name="set-up-master-plans"></a>Imposta i piani generali

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritte varie strategie e parametri importanti utilizzati per impostare la pianificazione generale. L'argomento include una panoramica dei tipi di piani utilizzati dalla pianificazione generale e illustra quale strategia dei piani è necessario utilizzare, in base alle proprie esigenze aziendali. Descrive inoltre i parametri principali che influiscono sul piano e l'impatto degli stessi sugli ordini pianificati suggeriti.

## <a name="types-of-master-plans"></a>Tipi di piani generali

La pianificazione generale include due tipi di piani: statico e dinamico. Ogni tipo è progettato per un utilizzo differente. Per ottenere le migliori prestazioni, è consigliabile utilizzare il piano appropriato per lo scenario in uso.

### <a name="static-plan"></a>Piano statico

Il piano statico rimane invariato, indipendentemente dalle eventuali modifiche nell'offerta e nella domanda, fino alla successiva esecuzione della pianificazione generale.

Il piano statico viene utilizzato per approvare e stabilizzare gli ordini che vengono suggeriti. Si tratta di un piano operativo che può essere utilizzato dal personale della società a vari livelli (ad esempio un acquirente o un addetto alla pianificazione della produzione) come base per le decisioni e per lo svolgimento dei compiti e delle attività giornalieri.

Il piano statico inoltre supporta la rigenerazione. Un piano ottimizzato completamente nuovo viene calcolato a ogni esecuzione della pianificazione generale e ogni eliminazione degli ordini esistenti che non sono stati approvati.

### <a name="dynamic-plan"></a>Piano dinamico

Il piano dinamico inizia in genere come copia del piano statico, ma può essere aggiornato ogni volta che i dati master cambiano. Ad esempio, se i dati cambiano, viene creato un nuovo ordine cliente.

Il piano dinamico viene utilizzato per la pianificazione ad hoc. Consente alla società di monitorare la rete di ordini e la disponibilità di articoli senza interferire con il piano statico utilizzato da altri dipendenti per i processi lavorativi. Viene utilizzato soprattutto per capable-to-promise (CTP). Il piano dinamico è il piano predefinito quando i fabbisogni netti vengono aperti dalle pagine degli ordini (ad esempio pagine degli ordini cliente, ordini fornitore o ordini di produzione).

Il piano dinamico utilizza la modifica netto. Di conseguenza, garantisce un tempo di esecuzione più rapido.

## <a name="strategies-for-using-master-plans"></a>Strategie per l'utilizzo di piani generali

È possibile utilizzare un piano o due piani nella pianificazione generale. La strategia utilizzata dipende dai requisiti aziendali.

### <a name="one-plan-strategy"></a>Strategia a un piano

Per la strategia a un piano, si utilizza lo stesso piano generale per il piano statico e il piano dinamico. Questa strategia viene utilizzata per gli scenari produzione per magazzino, in cui in genere non è necessario simulare un piano che evade un ordine.

La strategia a un piano è in genere utilizzata nei settori della vendita al dettaglio e della distribuzione, o nei casi in cui le date delle consegne vendita sono confermate in base ai contratti di servizio o ai lead time. Per il piano, il controllo delle date di consegna può essere utilizzato senza CTP.

Se è necessario eseguire una simulazione, il piano può essere eseguito di nuovo per gli articoli che richiedono la simulazione. Gli ordini pianificati prodotti dalle simulazioni degli ordini sono in genere stabilizzati.

### <a name="two-plan-strategy"></a>Strategia a due piani

Per la strategia a due piani, si utilizza un piano statico e un piano dinamico differente. La strategia a due piani è in genere utilizzata per gli scenari configure-to-order e produzione su ordine in cui è necessario eseguire simulazioni degli ordini cliente e calcolare le date di consegna esatte per gli ordini cliente, ma i calcoli non devono influenzare le operazioni giornaliere. Queste simulazioni vengono sempre effettuate nel piano dinamico. La strategia a due piani è utile, ad esempio, nell'industria automobilistica e nel settore OEM.

Per la strategia a due piani, è possibile utilizzare il controllo delle date di consegna con CTP. Quando si utilizza CTP, viene automaticamente generata l'esecuzione nel piano dinamico.

### <a name="setting-up-the-plans"></a>Impostazione dei piani

È possibile creare piani nella pagina **Piani generali** (**Pianificazione generale \> Impostazioni \> Piani \> Piani generali**).

È possibile specificare i piani da utilizzare per il piano statico e il piano dinamico impostando i campi **Piano generale statico corrente** e **Piano generale dinamico corrente** nella pagina **Parametri di pianificazione generale** (**Pianificazione generale \> Impostazioni \> Parametri di pianificazione generale**). Per utilizzare una strategia a un piano, selezionare lo stesso piano nei campi **Piano generale dinamico corrente** e **Piano generale statico corrente**.

## <a name="types-of-planning-methods"></a>Tipi di metodi di pianificazione

Per eseguire la pianificazione generale, è possibile utilizzare due metodi di calcolo: rigenerazione e modifica netto. Ogni metodo genera un piano differente quando eseguito.

Il metodo di pianificazione viene specificato nella finestra di dialogo **Esecuzione della pianificazione generale**. Per aprire questa finestra di dialogo, accedere a **Pianificazione generale \> Pianificazione generale \> Esegui \> Pianificazione generale** o selezionare **Esegui** nell'area di lavoro **Pianificazione generale**

### <a name="regeneration"></a>Rigenerazione

Il metodo di pianificazione con rigenerazione elimina gli ordini pianificati esistenti, a meno che non siano stabilizzati. Genera nuovi ordini pianificati, in base a tutti i fabbisogni. La rigenerazione è l'unico metodo di pianificazione disponibile per i piani statici.

- Le modifiche nella fornitura sono prese in considerazione. Queste modifiche includono quelle nella previsione.
- Questo metodo tiene conto del codice di copertura **Periodo**.
- Questo metodo supporta la funzionalità di sostituzione dei prodotti.

### <a name="net-change"></a>Modifica netto

Il metodo di pianificazione con modifica netto genera ordini pianificati per coprire i fabbisogni creati o modificati dopo l'ultima esecuzione della pianificazione generale. Le modifiche non vengono prese in considerazione quando si utilizza tale metodo. Il sistema non considera le nuove forniture e gli ordini pianificati creati in precedenza non vengono eliminati se non sono più necessari. Il metodo di pianificazione con modifica netto viene eseguito più velocemente rispetto al metodo con rigenerazione. È disponibile solo per i piani dinamici.

- Le date azione e i ritardi sono aggiornati per tutti i fabbisogni.
- Questo metodo non tiene conto del codice di copertura **Periodo**.
- Questo metodo non soddisfa la previsione, anche se è selezionato per il piano.
- Questo metodo non supporta la funzionalità di sostituzione dei prodotti.

### <a name="net-change-minimized"></a>Modifica netto minimizzata

Il metodo di pianificazione con modifica netto minimizzata genera ordini pianificati per coprire solo i fabbisogni creati o modificati dopo l'ultima esecuzione della programmazione della pianificazione generale. Per questo metodo, a differenza del metodo con modifica netto, le date azione e le date ritardi vengono aggiornate solo per i nuovi fabbisogni o quelli modificati. Questo metodo di pianificazione è disponibile solo per i piani dinamici.

## <a name="types-of-scheduling-methods"></a>Tipi di metodi di programmazione

Per ogni piano, nella scheda dettaglio **Generale** della pagina **Piani generali** (**Pianificazione generale \> Impostazioni \> Piani \> Piani generali**), è necessario selezionare il metodo di programmazione utilizzato per gli ordini di produzione. È possibile programmare la produzione il livello di operazione e di processo.

### <a name="operations-scheduling"></a>Programmazione operazioni

Questo tipo di programmazione può essere utilizzato per ottenere una stima generale del processo di produzione nel tempo. La programmazione operazioni non esplode le operazioni per il ciclo di lavorazione produzione in processi. Per ulteriori informazioni sulla programmazione operazioni, vedere [Programmazione operazioni](/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling).

### <a name="job-scheduling"></a>Programmazione processo

La programmazione processo è un metodo di programmazione più dettagliato, dove ogni operazione viene suddivisa in singole attività o processi. La programmazione processo include sulla capacità. Viene solitamente utilizzata per programmare singoli processi del reparto produzione e viene eseguita immediatamente o entro un breve intervallo di tempo. Per ulteriori informazioni sulla programmazione processo, vedere [Programmazione processo](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="time-fences-in-days"></a>Intervalli temporali in giorni

Per ogni piano, è possibile selezionare fino a quando i vari fabbisogni e altre considerazioni devono essere calcolati mediante la pianificazione generale. Il periodo è noto come *intervallo temporale*. Per le migliori prestazioni nella pianificazione generale, si consiglia di rettificare i vari intervalli temporali per soddisfare i requisiti aziendali. Per ogni piano, è possibile trovare gli intervalli temporali nella scheda dettaglio **Intervalli temporali in giorni** della pagina **Piani generali** (**Pianificazione generale \> Impostazioni \> Piani \> Piani generali**).

> [!NOTE]
> Gli intervalli temporali indicano fino a quando i vari fabbisogni e altre considerazioni vengono calcolati mediante la pianificazione generale. Gli intervalli temporali selezionati in questa pagina sostituiranno quelli definiti nel gruppo di copertura. Ciò significa impostare un'opzione relativa agli intervalli temporali su Sì e definire i giorni che sostituiranno l'intervallo temporale definito nel gruppo di copertura. Quando impostato su No, l'intervallo temporale verrà definito nel gruppo di copertura. Infine, se non si desidera o non è necessario utilizzare un'opzione (ad esempio non si desidera utilizzare i messaggi d'azione), impostare **Sì** e quindi impostare l'intervallo temporale su **0** (zero) giorni.

### <a name="coverage"></a>Copertura

L'intervallo temporale di copertura rappresenta il periodo di programmazione o fino a quando la domanda deve essere inclusa. In altre parole, indica l'orizzonte di pianificazione.

Impostando l'opzione **Copertura** su **Sì**, è possibile ignorare l'intervallo temporale di copertura definito per l'articolo durante la programmazione generale. In questo caso, immettere il numero di giorni in cui i fabbisogni dovranno essere coperti dal calcolo della programmazione generale. L'intervallo temporale di copertura viene calcolato in avanti a partire dalla data corrente. I fabbisogni che si verificano prima della data corrente vengono sempre elaborati.

> [!NOTE]
> Per le migliori prestazioni nella pianificazione generale, si consiglia di modificare l'intervallo temporale di copertura in base all'orizzonte di pianificazione.

### <a name="freeze"></a>Blocca

L'intervallo temporale di blocco rappresenta il periodo in cui gli ordini pianificati esistenti non vengono modificati quando viene eseguita una nuova programmazione generale. Gli ordini pianificati vengono bloccati e non verranno suggeriti nuovi ordini pianificati.

Impostando l'opzione **Blocca** su **Sì**, è possibile ignorare l'intervallo temporale di blocco definito per l'articolo durante la programmazione generale. In questo caso, immettere il numero di giorni in cui l'attività di pianificazione deve essere bloccata. Considerare che in tale periodo non verranno generati nuovi ordini pianificati e non si potrà modificare gli ordini pianificati esistenti.

### <a name="firming"></a>Stabilizzazione

L'intervallo temporale di stabilizzazione indica l'orizzonte temporale in cui gli ordini pianificati vengono convertiti automaticamente in ordini di produzione e fornitore. Questo processo è anche noto come *stabilizzazione automatica degli ordini pianificati*.

Impostando l'opzione **Stabilizzazione** su **Sì**, è possibile ignorare l'intervallo temporale di stabilizzazione definito per l'articolo durante la programmazione generale. In questo caso, immettere il numero di giorni in cui gli ordini di produzione e gli ordini fornitore pianificati devono essere stabilizzati automaticamente. L'intervallo temporale di stabilizzazione viene calcolato in avanti a partire dalla data della programmazione generale. La stabilizzazione automatica di un ordine fornitore pianificato può avvenire solo se l'articolo è associato a un fornitore.

### <a name="forecast-plan"></a>Piano previsionale

L'intervallo temporale di piano previsionale indica fino a quando la pianificazione generale crea ordini pianificati per gli articoli con domanda prevista.

Impostando l'opzione **Copertura** su **Sì**, è possibile ignorare l'intervallo temporale di piano previsionale definito per l'articolo durante la programmazione generale. In questo caso, immettere il numero di giorni in cui le previsioni di vendita generate dal piano previsionale devono essere incluse nella pianificazione generale.

### <a name="capacity"></a>Capacità

L'intervallo temporale di capacità indica fino a quando il sistema prende in considerazione la capacità massima delle risorse durante la programmazione degli ordini. In altre parole, il piano programma gli ordini di produzione mediante il ciclo di lavorazione produzione per gli articoli e prende in considerazione le risorse del ciclo di lavorazione produzione e la capacità massima di ogni risorsa.

Impostando l'opzione **Capacità** su **Sì**, è possibile ignorare l'intervallo temporale di capacità definito per l'articolo durante la programmazione generale. In questo caso, immettere il numero di giorni in cui la capacità deve essere pianificata per gli ordini di produzione pianificati. Nella programmazione generale viene utilizzato il ciclo di lavorazione produzione attivo per l'articolo e la programmazione viene eseguita a ritroso a partire dalla data del fabbisogno. Se la data del fabbisogno di un ordine di produzione pianificato non è compresa nell'intervallo temporale di capacità, il lead time viene determinato dal tempo di consegna dell'articolo. L'intervallo temporale di capacità viene calcolato in avanti a partire dalla data corrente.

### <a name="action-message"></a>Messaggio d'azione

I messaggi d'azione suggeriscono le modifiche che è possibile effettuare all'ordine di fornitura per ottimizzare il piano di fornitura. Ad esempio, potrebbero suggerire di anticipare o posticipare gli ordini oppure di aumentare o diminuire le quantità degli ordini.

Impostando l'opzione **Messaggio d'azione** su **Sì**, è possibile ignorare l'intervallo temporale del messaggio d'azione definito per l'articolo durante la programmazione generale. In questo caso, immettere il numero di giorni in cui la programmazione generale deve generare messaggi d'azione per i fabbisogni. L'intervallo temporale del messaggio d'azione viene calcolato in avanti a partire dalla data corrente.

Per ulteriori informazioni sui messaggi d'azione, vedere [Messaggi d'azione](/dynamics365/unified-operations/supply-chain/master-planning/action-messages).

> [!NOTE]
> Il calcolo dei messaggi d'azione genera un tempo di esecuzione più lungo per la pianificazione generale. Se i messaggi d'azione non sono analizzati e applicati regolarmente (giornalmente, settimanalmente e così via), valutare l'opportunità di disattivare il calcolo durante l'esecuzione della pianificazione generale. Per disattivare il calcolo, nella pagina **Piani generali**, impostare l'intervallo temporale **Messaggio d'azione** su **0** (zero) per il piano generale in esecuzione. Assicurarsi inoltre che l'impostazione **Messaggio d'azione** sia disattivata per tutti i gruppi di copertura.

### <a name="calculated-delays"></a>Ritardi calcolati

È possibile specificare fino a che punto i possibili ritardi vengono individuati e notificati. In questo modo, è possibile programmare le date di consegna (ritardate) possibili.

Se un ordine pianificato non può essere evaso per la data richiesta, viene pianificato per la prima data di evasione possibile per una transazione, in base ai lead time e alla disponibilità di materiali e capacità.

### <a name="approved-requisitions-time-fence"></a>Intervallo temporale richieste approvate

È possibile impostare la pianificazione generale per creare ordini pianificati per la domanda della richiesta. Impostare l'opzione **Includi richieste** su **Sì** nella Scheda dettaglio **Generale** della pagina **Piani generali**. Quindi, quando lo scopo di una richiesta approvata è il rifornimento, la pianificazione generale genera automaticamente un ordine pianificato corrispondente per evaderlo. Il metodo di rifornimento viene determinato in base ai criteri di fornitura impostati per gli articoli nell'organizzazione. Dopo la creazione e l'approvazione della richiesta di rifornimento, non è richiesta alcuna ulteriore azione.

Impostando l'opzione **Intervallo temporale richieste approvate** su **Sì** nella scheda dettaglo **Intervalli temporali in giorni**, è possibile ignorare l'intervallo temporale delle richieste approvate definito per l'articolo durante la programmazione generale. In questo caso, immettere il numero di giorni nel passato durante i quali la domanda risultante dalle richieste approvate con lo scopo Rifornimento deve essere inclusa nella programmazione generale. Ad esempio, è possibile indicare che solo la domanda non evasa o scaduta dalle richieste approvate create negli ultimi 10 giorni deve essere presa in considerazione e programmata.

### <a name="sequencing"></a>Sequenziamento

Il sequenziamento consente di disporre gli ordini pianificati in base agli attributi di sequenziamento associati al prodotto finito. Viene spesso utilizzato per preparare gli ordini di produzione per l'imballaggio. Ad esempio, può essere utilizzato per imballare scatole in una sequenza specifica, in base al colore e alle dimensioni.

Impostando **Sequenziamento** su **Sì**, è possibile specificare fino a quando le operazioni o i processi devono essere disposti in sequenza. Da notare che maggiore è l'intervallo temporale, più lunga sarà l'esecuzione della pianificazione generale.

### <a name="calculated-delays"></a>Ritardi calcolati

Le opzioni di ritardo garantiscono date pianificate attuabili per gli ordini. Le opzioni seguenti sono disponibili nella scheda dettaglio **Ritardi calcolati** della pagina **Piani generali**:

- **Assicurarsi che gli ordini pianificati non vengano creati prima della data di esecuzione della pianificazione generale** - Impostare questa opzione su **Sì** per garantire che gli ordini non possono essere programmati per date passate.
- **Aggiungere il ritardo calcolato alla data del fabbisogno** (in **Ordini fornitore pianificati**) - Impostare questa opzione su **Sì** per aggiungere il ritardo calcolato ai fabbisogni.
- **Aggiungere il ritardo calcolato alla data del fabbisogno** (in **Ordini di produzione pianificati**) - Impostare questa opzione su **Sì** per aggiungere il ritardo calcolato ai fabbisogni.
- **Aggiungere il ritardo calcolato alla data del fabbisogno** (in **Trasferimento pianificato**) - Impostare questa opzione su **Sì** per aggiungere il ritardo calcolato ai fabbisogni.
- **Aggiungere il ritardo calcolato alla data del fabbisogno** (in **Kanban pianificato**) - Impostare questa opzione su **Sì** per aggiungere il ritardo calcolato ai fabbisogni.

Quando si impostano le opzioni **Aggiungere il ritardo calcolato alla data del fabbisogno** su **Sì** per aggiungere i ritardi ai fabbisogni, il sistema prende in considerazione la capacità delle risorse e creare ordini pianificati attuabili. Il ricalcolo delle date degli ordini pianificati aumenta il tempo di esecuzione per la pianificazione generale. Di conseguenza, se non è necessario utilizzare i ritardi, impostare le opzioni su **No**.

## <a name="positive-and-negative-days"></a>Giorni positivi e negativi

I giorni positivi e negativi determinano il modo in cui la pianificazione generale suggerisce azioni e ordini pianificati. I giorni positivi e negativi vengono impostati sul gruppo di copertura dell'articolo. È possibile definire vari gruppi di copertura e impostarne i parametri nella pagina **Gruppi di copertura** (**Pianificazione generale \> Impostazioni \> Copertura \> Gruppi di copertura**).

### <a name="positive-days"></a>Giorni positività

I giorni positivi indicano fino a quando la pianificazione generale prende in considerazione le entrate o le scorte correnti per soddisfare una domanda futura. Ad esempio, se i giorni positivi sono impostati su **100**, le scorte correnti possono essere utilizzate per soddisfare una domanda nei 100 giorni successivi. Se è presente un ordine di 150 giorni dalla data corrente, la pianificazione generale creerà un ordine pianificato per soddisfare quella domanda, anche se le scorte disponibili per l'articolo possono soddisfare l'ordine. Per gli articoli rapidi con un lead time breve, è possibile che non si intendano utilizzare le scorte disponibili per un ordine che è lontano nel futuro. In questo caso, le scorte disponibili correnti si esauriranno rapidamente e più ordini potrebbero essere eseguiti in futuro per soddisfare in tempo una domanda futura, cosa che sarebbe possibile a seguito del lead time breve dell'articolo.

I giorni positivi influiscono anche sui messaggi d'azione. Ad esempio, il sistema potrebbe suggerire di aumentare un ordine fornitore pianificato di modo che includa una domanda compresa nel numero di giorni positivi nel futuro. Se i giorni positivi sono impostati su **100** e se esiste una domanda per un articolo in 30 giorni a partire dalla data corrente, il sistema creerà un ordine pianificato per soddisfare la domanda. Se esiste una domanda per lo stesso articolo in 90 giorni a partire dalla data corrente, il sistema consiglierà di aumentare la quantità dell'ordine in 30 giorni a partire dalla data corrente, di modo che l'ordine copra anche la domanda in 90 giorni. Tuttavia, se si ha una domanda per l'articolo in 150 giorni a partire dalla data corrente, il sistema non suggerirà di aumentare la quantità dell'ordine che è già stato pianificato. Verrà invece creato un nuovo ordine pianificato.

In genere, i giorni positivi vengono impostati su un valore compreso tra il lead time più lungo degli articoli e l'intervallo temporale di copertura. Si consiglia di assegnare gli articoli che vengono regolarmente approvvigionati o prodotti a un gruppo di copertura in cui i giorni positivi eguagliano il lead time dell'articolo.

### <a name="negative-days"></a>Giorni negativi

I giorni negativi indicano il ritardo accettabile per le entrate degli articoli. Rappresentano il numero di giorni che si è disposti ad attendere prima di ordinare un nuovo rifornimento in caso di scorte negative o insufficienti. I giorni negativi consentono di rispondere alla domanda "Dobbiamo creare un nuovo ordine fornitore per l'articolo oppure utilizzare un acquisto esistente, anche sapendo che l'articolo sarà in ritardo?"

Ad esempio, si ha un ordine cliente per un articolo in 15 giorni dalla data corrente. Si ha inoltre un ordine fornitore per lo stesso articolo. Questo ordine fornitore verrà ricevuto in 20 giorni dalla data corrente. Il sistema deve creare un ordine fornitore per quell'ordine cliente oppure si desidera utilizzare l'ordine esistente, anche se non è possibile evadere l'ordine cliente in tempo? Se i giorni negativi sono impostati su un valore inferiore a **5** per indicare che l'articolo può essere ritardato al massimo di cinque giorni, il sistema crea un nuovo ordine fornitore pianificato per soddisfare l'ordine cliente. Se i giorni negativi sono impostati su un valore maggiore di **5**, il sistema utilizza l'ordine esistente per l'articolo.

I giorni negativi influiscono anche sulle prestazioni della pianificazione generale. Se i giorni negativi sono impostati su un numero superiore, verranno generati molti messaggi d'azione.

Si consiglia di impostare i giorni negativi su un numero inferiore al lead time dell'articolo.

### <a name="dynamic-negative-days"></a>Giorni negativi dinamici

I giorni negativi dinamici prendono in considerazione il lead time dell'articolo e i giorni negativi specificati. Il sistema creerà un nuovo ordine fornitore pianificato, in base all'intervallo temporale dei giorni negativi calcolato utilizzando la seguente formula:

Lead time + giorni negativi + data odierna – data fabbisogno

Il sistema utilizza solo gli ordini di fornitura pianificati compresi in questo intervallo temporale e crea un nuovo ordine pianificato al di fuori di tale intervallo. Il vantaggio dei giorni negativi dinamici è che includeranno il lead time del singolo prodotto per riutilizzare gli ordini esistenti e impedire la creazione di nuovi ordini pianificati che termineranno in un giorno successivo, a causa dei ritardi causati dal lead time. 

Per ulteriori informazioni, vedere [Giorni negativi e giorni negativi dinamici](/dynamics365/unified-operations/supply-chain/master-planning/more-about-dynamic-negative-days).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]