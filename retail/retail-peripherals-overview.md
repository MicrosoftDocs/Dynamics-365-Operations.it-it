---
title: Panoramica di articoli al dettaglio di periferiche
description: In questo argomento vengono descritti i concetti correlati alle vendite al dettaglio le periferiche. Sono descritti i vari modi che le periferiche possono essere collegate al POS (POS) e ai componenti responsabili della gestione della connessione al POS.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 268444
ms.assetid: 2ea93e43-8019-49a0-a7f8-325565ebc52d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 79a43c35691f16d773b88faad63c4ab79cb93f1f
ms.openlocfilehash: c6fb3922ba2c4b15f1043d0bcbac40ff2da9a469
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripherals-overview"></a>Panoramica di articoli al dettaglio di periferiche

In questo argomento vengono descritti i concetti correlati alle vendite al dettaglio le periferiche. Sono descritti i vari modi che le periferiche possono essere collegate al POS (POS) e ai componenti responsabili della gestione della connessione al POS.

<a name="concepts"></a>Concetti
--------

### <a name="pos-registers"></a>Registratori di cassa POS

Percorso: ** Fare clic su Retail e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** registrare **. Il registro di (POS) del POS rappresenta un'entità utilizzata per definire le caratteristiche di un'istanza specifica del POS. Le caratteristiche includono il profilo hardware o l'impostazione delle periferiche al dettaglio che verranno utilizzate nel registratore, il punto vendita dal registro è mappato a ed esperienza grafica dell'utente firmatario in a tale registro.

### <a name="devices"></a>Periferiche

Percorso: ** Fare clic su Retail e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** ** unità. Un dispositivo è un'entità che rappresenta un'istanza fisica di un dispositivo che viene mappato a un registratore di cassa POS. Se un'unità, è possibile mappata a un registratore di cassa POS. L'entità dispositivo tiene traccia delle informazioni sull'attivazione di un registratore di cassa POS, il tipo di client in uso e il pacchetto dell'applicazione che è stato distribuito in un dispositivo specifico. Le unità possono essere mappate ai seguenti tipi dell'applicazione: Moderno POS Retail POS, di cloud di Retail POS, moderno di Retail Store Inventory - Windows Phone POS, moderno di Retail Store Inventory - Android e POS moderno al dettaglio e Dynamic.

### <a name="retail-modern-pos"></a>Retail Modern POS

L'articolo è moderno il programma Retail POS di Microsoft Windows. Può essere distribuito in Windows 10 sistemi operativi (OSs).

### <a name="cloud-pos"></a>POS cloud

L'articolo di cloud a una versione browser in base al programma moderno POS che si è possibile accedere in un Web browser.

### <a name="modern-pos-for-ios"></a>POS moderno dell'IOS

In Retail POS moderno dell'IOS è una versione IOS IOS del programma moderno POS che si può essere distribuito nelle unità dell'IOS.

### <a name="modern-pos-for-android"></a>POS moderno per Android

In Retail POS moderno per Android a una versione basata su Android del programma moderno POS che si può essere distribuito nelle unità di Android.

### <a name="pos-peripherals"></a>Unità di tastiera POS

Le periferiche di Retail POS unità che sono supportate in modo esplicito le funzioni di Retail POS. Queste periferiche vengono suddivise in genere le classi specifiche. Per ulteriori informazioni sulle classi, vedere la sezione riguardante le classi di unità" in questo argomento.

### <a name="hardware-station"></a>Stazione hardware

Percorso: ** Fare clic su Retail e il commercio ** &gt; ** canali ** &gt; ** vendita al dettaglio ** &gt; ** tutte le vendite al dettaglio **. Selezionare un punto vendita, quindi fare clic sulla scheda dettaglio **Stazioni hardware**. ** Postazione hardware ** l'impostazione è di un'impostazione a livello di Manica utilizzata per definire i casi in cui la logica periferica al dettaglio viene contabilizzata. Queste impostazioni a livello di canale viene utilizzata per determinare le caratteristiche della propria postazione hardware. Sarà inoltre utilizzata per elencare le stazioni hardware disponibili per un'istanza moderna di POS in un punto vendita data. La propria postazione hardware viene generato nella programmazione moderno di Retail POS per Windows. La propria postazione hardware può essere indipendente contabilizzata come programma autonomo di Microsoft Internet Information Services (IIS). In questo caso, può accedere tramite una rete.

### <a name="hardware-profile"></a>Profilo hardware

Percorso: ** Fare clic su Retail e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** il POS profili ** &gt; ** profili hardware **. Profilo hardware è un elenco di unità configurate per un registratore di cassa POS o la propria postazione hardware. Il profilo hardware è possibile mappare direttamente a un registratore di cassa POS o alla propria postazione hardware.

## <a name="devices-classes"></a>Classi di unità
Le periferiche di Retail POS sono divise in genere le classi. In questa sezione viene descritto e assegnare a una panoramica delle periferiche supporti moderni del POS.

### <a name="printer"></a>Stampante

Le stampanti includono stampatrici tradizionali entrate di Retail POS e le stampanti a testo libero. Stampante è supportata al collegamento di oggetti e la incastonatura per Retail POS OPOS () e le interfacce del driver di Microsoft Windows. Con arrotondamento a due stampanti possono essere utilizzate contemporaneamente. La capacità supporta scenari in cui le entrate cliente in cash and carry vengono stampate sulle stampanti di entrata, mentre gli ordini cliente, contenenti ulteriori informazioni, vengono stampati su una stampante a testo libero. Le stampanti entrate possono essere collegate direttamente in un computer tramite l'interoperabilità USB, essere collegate a una rete Ethernet via, o da collegare mediante Bluetooth.

### <a name="scanner"></a>Scanner

Con arrotondamento a due lettori di codice a barre possono essere utilizzati contemporaneamente. La capacità supporta scenari in cui uno scanner maggiore cellulare è necessario eseguire la scansione di grandi dimensioni o articoli pesanti, mentre uno scanner incorporato fisso utilizzato nella maggior parte degli articoli di formato standard, per velocizzare le ore per il check out. Gli che possono essere supportati parti di cassa, la piattaforma (UWP) di Windows UTC, ovvero le interfacce di cuneo tastiera. In USB o Bluetooth può essere utilizzato per collegare uno scanner a una macchina.

### <a name="msr"></a>MSR

Il lettore di banda magnetica (MSR) di USB è possibile impostare utilizzando i conducenti OPOS. Se si desidera utilizzare un dispositivo MSR autonomo per le transazioni di pagamento (EFT) di bonifico, il dispositivo MSR deve essere gestito da un Connector di pagamento. I MSRs autonomi possono essere utilizzati per l'immissione di fedeltà del cliente, il dipendente e accesso nella voce della gift card, indipendentemente da connettori di pagamento.

### <a name="cash-drawer"></a>Cassetto di cassa

Due cassetti di cassa possono essere supportati per profilo hardware. Questa funzione consente a due turni attivi per ciascun registratore di essere disponibili contemporaneamente. Se un turno comune, oppure cassetto della cassa utilizzato da più unità mobili di Retail POS contemporaneamente, solo il cassetto della cassa è concesso profilo hardware. I cassetti di cassa possono essere collegati direttamente a un computer tramite l'interoperabilità USB, essere collegati a una rete, o essere collegati a una stampante delle ricevute tramite l'interfaccia RJ12. In alcuni casi, i cassetti di cassa possono anche essere collegati Bluetooth via.

### <a name="line-display"></a>Visualizzazione riga

Visualizza di riga vengono utilizzate per visualizzare i prodotti, i saldi delle transazioni e altre informazioni utili al cliente durante la transazione. Visualizzazione di riga può essere associata al computer tramite l'interoperabilità USB utilizzando i conducenti OPOS.

### <a name="signature-capture"></a>Acquisizione firma

Le unità di blocco di firma possono essere collegate direttamente in un computer tramite l'interoperabilità USB utilizzando i conducenti OPOS. Quando il blocco di firma è configurato, il cliente viene chiesto di firma sull'unità. Dopo che la firma viene fornita, indicato il cassiere dell'accettazione.

### <a name="scale"></a>Scala

Le scale possono essere collegate al computer mediante USP utilizzando i conducenti OPOS. Quando un prodotto che viene contrassegnato come "prodotto pesato" viene aggiunta a una transazione, il POS legge il peso dalla bilancia, aggiunge il prodotto alla transazione e utilizza la quantità che la scala fornito.

### <a name="pin-pad"></a>Tastierino PIN

I freni di (PIN) del numero di identificazione personale sono supportati con di cassa, ma dovranno essere gestiti da connettori di pagamento.

### <a name="secondary-display"></a>Visualizzazione secondaria

Quando una visualizzazione secondaria è configurata, la visualizzazione di Windows numero 2 viene utilizzato per visualizzare le informazioni di base. Lo scopo di visualizzazione è secondaria di supportare l'estensione di indipendente (ISV) del fornitore software, poiché la casella, la visualizzazione secondaria non è configurabile e non è visualizzato il contenuto limitato.

### <a name="payment-device"></a>Dispositivo di pagamento

Il supporto dell'unità di pagamento è implementato da connettori del pagamento. Le unità di pagamento possono eseguire una o più delle funzioni da altre classi di unità garantiscono. Ad esempio, un'unità di pagamento può essere eseguito come uno scanner del dispositivo/card, una visualizzazione di riga, un'unità di blocco di firma, o un tastierino PIN. Contributo alle unità di pagamento è implementato indipendentemente dal titolare autonomo di unità a cui viene fatto per altre unità incluse nel profilo hardware.

## <a name="supported-interfaces"></a>Interfacce supportati
### <a name="opos"></a>)

Per contribuire a garantire che il più ampio range di unità è possibile utilizzare Microsoft Dynamics 365 per le operazioni al dettaglio, viene installato per lo standard del settore di Retail POS viene la piattaforma al dettaglio primaria della periferica che è supportata in Microsoft Dynamics 365 per le operazioni al dettaglio. Viene installato per lo standard di Retail POS viene realizzata dalla federazione al dettaglio nazionale (NRF), che stabilisce i protocolli di comunicazione standard per le periferiche al dettaglio. In se è un'implementazione adottata da quelli di OLE per lo standard di Retail POS. Era nel della metà del 1990 è stato sviluppato ed è stato aggiornato più volte dal momento. In sono disponibili se un modello del driver che consente all'integrazione dell'hardware POS con sistemi basati su Windows di Retail POS. Comunicazione di manopola di controlli OPOS tra compatibile hardware e software di Retail POS. La presenza di cassa è presente in due parti:

-   ** Oggetto di controllo ** - l'oggetto di controllo per una classe di unità (ad esempio le visualizzazioni di riga) costituisce l'interfaccia per il programma software. I servizi di consulenza di Monroe (www.monroecs.com [] (http://www.monroecs.com/)) è disponibile una serie standard degli oggetti di controllo OPOS che sono noti come direzione centrale oggetti (CCOs). Il CCOs viene utilizzato per monitorare il componente di Retail POS Microsoft Dynamics 365 a operazioni al dettaglio. Di conseguenza, guide di prova garantire che, se Microsoft Dynamics 365 per le operazioni al dettaglio supporta una classe di unità di cassa, molti tipi di unità è supportata e, a condizione che il produttore fornisce un oggetto assistenza che viene generato di cassa. Non è necessario esplicitamente verificare ogni tipo di unità.
-   ** Oggetto assistenza - ** l'oggetto assistenza vengono fornite le comunicazioni tra l'oggetto di controllo (CCO) e l'unità. In genere, l'oggetto assistenza per un'unità viene fornito dal produttore dell'unità. Tuttavia, in alcuni casi, potrebbe essere necessario scaricare l'oggetto assistenza dal sito Web del produttore. Ad esempio, un oggetto più recente di assistenza sia disponibile. Per trovare l'indirizzo del sito Web del produttore, vedere la documentazione hardware.

[oggetto![controllo![ e oggetti assistenza (]. /media/retail_peripherals_overview01.png)](. Il supporto di /media/retail_peripherals_overview01.png) all'implementazione di cassa di OLE per le aree di Retail POS garantisce che, se i produttori dell'unità e gli editori di Retail POS implementano correttamente predefinita, sistemi di Retail POS e unità supportati è possibile eseguire congiuntamente, anche se in precedenza non sono state specifica set. ** Nota: ** Il supporto di cassa non garantisce il contributo a tutte le unità con il OPOS. Microsoft Dynamics 365 per le operazioni consente il supporto di vendita al dettaglio selezionare il tipo di unità, o classe, all'cassa. Inoltre, gli oggetti assistenza potrebbero non essere sempre aggiornati con l'ultima versione del CCOs. È inoltre necessario tenere presente che, gli oggetti di controllo qualità di assistenza varia in genere.

### <a name="windows"></a>Windows

La stampa della ricevuta nel POS viene ottimizzata per la cassa. In tende a OPOS è estremamente utile per velocizzare la stampa con Windows. Di conseguenza, è consigliabile l'utilizzo di cassa, soprattutto negli ambienti di articoli al dettaglio in cui 40 entrate di colonna vengono stampate e l'ora della transazione deve essere veloce. Per la maggior parte delle unità, verranno utilizzati i controlli OPOS. Tuttavia, le stampanti entrate di cassa anche supporto dai conducenti di Windows. Utilizzando un driver di Windows, è possibile accedere agli ultimi due caratteri e stampa di una rete per i registri. Tuttavia, sono presenti svantaggi a tramite i conducenti di Windows. Di seguito sono riportati alcuni esempi di questi svantaggi:

-   Quando i conducenti di Windows vengono utilizzati, immagini vengono disabilitate prima che venga eseguita stampare. Di conseguenza, stampare tende a essere più lenta sia sulle stampanti che utilizzano i controlli OPOS.
-   Le unità collegate dalla stampante ("margherita- incatenato ") potrebbero non funzionare correttamente ai conducenti di Windows vengono utilizzati. Ad esempio, il cassetto della cassa non è o, aprire la stampa del documento non può esprimere come previsto.
-   È inoltre) supporta una serie di variabili esteso più specifiche delle vendite al dettaglio le stampanti entrate, ad esempio la stampa di carta della matrice o di taglio.

Se i controlli di cassa sono disponibili per la stampante Windows in uso, la stampante deve ancora essere eseguito correttamente Microsoft Dynamics 365 per le operazioni al dettaglio.

### <a name="universal-windows-platform"></a>Piattaforma di Windows UTC

UWP, nel caso di periferiche al dettaglio, è correlato a supporto di Windows alle unità pronto per l'utilizzo. Se un'unità pronta per l'utilizzo è collegata a una versione di OS di Windows che supportano il tipo di unità da, non è necessario per consentire l'unità da utilizzare come previsto. Ad esempio, se Windows rileva un'unità dell'oratore dell'Bluetooth, OS sa che l'unità ha ** oratore ** classi il tipo. Di conseguenza e gestisce tale unità come oratore. Nessuna impostazioni aggiuntive è obbligatoria. Nel caso di unità di Retail POS, vari dispositivi USB è possibile inserire e Windows le riconosciuti come unità (HIDs) dell'interfaccia umane. Tuttavia, non è possibile determinare dalle funzioni che l'unità attenzione, poiché l'unità non specifica la classe, o, tipo di unità. In Windows 10, classi di unità per i lettori di codice a barre e i MSRs sono stati aggiunti. Di conseguenza, se un'unità si dichiara a Windows 10 come unità dell'esecuzione di queste classi, Windows aspetterà di sentire gli eventi dall'unità appropriati al momento. In Retail POS moderno supporta UWP MSRs e scanner. Pertanto, quando è pronto per l'immissione di valori da una di queste unità e un'unità appartenente a una di queste classi effettuato l'accesso, l'unità utilizzo. Ad esempio, se uno scanner di codice a barre di UWP viene immesso un computer Windows 10 e codice a barre accesso in è configurato per il POS, il moderno scanner di codici a barre diventerà attivo su accesso in Management Reporter. Nessuna impostazioni aggiuntive è obbligatoria. Le classi di unità supplementari di unità di assistenza UWP vengono aggiunte a Windows. Queste classi includono le classi dei cassetti di cassa e le stampanti di entrata. Contributo alle nuove classi di unità in Retail moderno in corso.

### <a name="keyboard-wedge"></a>Cuneo tastiera

Le unità di cuneo tastiera inviare i dati nel computer come se tali dati siano immessi in una tastiera. Pertanto, per impostazione predefinita, il campo attiva al POS riceverà i dati da quelle personalizzate vengono esaminate o superati. In alcuni casi, questo comportamento può determinare la modifica il tipo errato di dati a essere letto nel campo errato. Ad esempio, un codice a barre può essere letto in un campo che viene utilizzato per l'entrata dei dati della carta di credito. In molti casi, viene installato presso logica che determina se i dati che quelle personalizzate vengono esaminate passati o è un codice a barre o una schermata della carta. Di conseguenza, i dati vengono gestiti correttamente. Tuttavia, quando le unità impostate come OPOS anziché le unità di cuneo tastiera, non è più possibile controllare la modalità di gestione dei dati dalle unità possono essere consumati, poiché più "è denominato" sull'unità da cui derivano i dati. Ad esempio, i dati da uno scanner di codice a barre vengono riconosciuti automaticamente come codice a barre e il record collegato nel database è possibile trovare più facilmente e più velocemente del previsto se una stringa di ricerca generica è stata utilizzata, come nel caso di unità di cuneo tastiera.

### <a name="native-printer"></a>Stampante native

Se il tipo è denominato nel profilo hardware) le stampanti indigene (unità "o" possibile configurare la richiesta all'utente di selezionare una stampante configurata per il computer. Quando una stampante ** unità ** di tipo è configurata, se il POS moderno rileva un comando di stampa, viene chiesto di selezionare una stampante in un elenco. Questo comportamento è diverso dal funzionamento dei conducenti di Windows, poiché ** Windows ** lo scrivente nel profilo hardware non viene visualizzato un elenco delle stampanti. A questo scopo, è necessario che una stampante denominata viene fornita ** nome di unità ** nel campo.

### <a name="windows"></a>Windows

** Windows ** il tipo di unità viene utilizzato per le stampanti specificato. Quando una stampante Windows è configurata nel profilo hardware, il nome della stampante specifica deve essere immessa. Quando agli moderni di Retail POS sono riportati gli eventi, se una stampante Windows è configurata, l'evento verrà inviato alla stampante specificata di Windows. L'utente non verrà chiesto di selezionare una stampante.

### <a name="network"></a>Rete

i cassetti di cassa, le stampanti ricevimento e i terminali Rete- indirizzabili di pagamento possono essere utilizzati in una rete, durante la generazione o successivamente direttamente nella propria postazione hardware di comunicazione tra IPC (processi) che viene generato in Retail moderno per l'applicazione Windows o tramite la propria postazione hardware di IIS per l'elaborazione da moderni di Retail POS.

## <a name="hardware-station-deployment-options"></a>Opzioni di distribuzione della propria postazione hardware
### <a name="ipc-built-in"></a>IPC (accessorio)

La propria postazione hardware di comunicazione tra IPC (processi) viene generato in Retail moderno per l'applicazione Windows. Per utilizzare la propria postazione hardware di IPC, assegnare un profilo hardware a un registro che utilizzerà il POS moderno per l'applicazione Windows. Quindi creare una propria postazione hardware di ** dedicato ** tipo per il punto vendita in cui il registro verrà utilizzato. Quando si avvia il POS moderno, la propria postazione hardware di IPC sarà attiva e le periferiche di Retail POS che sono stati configurati verranno pronto per l'utilizzo. Se non sono necessarie temporaneamente i componenti hardware locale per qualsiasiasi motivo, utilizzare ** gestire le stazioni hardware ** l'operazione per attivare o disattivare le funzionalità della propria postazione hardware. In Retail POS moderno può inoltre utilizzare la propria postazione hardware di IPC per comunicare direttamente alle periferiche di rete.

### <a name="iis"></a>IIS

La funzionalità di IIS la versione o autonoma della propria postazione hardware in due modi. Il descrittore "IIS" implica che l'applicazione di Retail POS di connettersi alla propria postazione hardware tramite Microsoft Internet Information Services. L'applicazione di Retail POS accede alla propria postazione hardware di IIS mediante servizi Web che vengono eseguiti in un computer in cui le unità sono associate. Se IIS viene utilizzato, le periferiche al dettaglio collegate alla propria postazione hardware possono essere utilizzate da qualsiasi registratore di cassa POS incluse nella stessa rete della propria postazione hardware di IIS. Poiché solo il POS moderno per Windows include il supporto per un le periferiche di articoli al dettaglio, tutte le altre applicazioni moderne di Retail POS devono utilizzare la propria postazione hardware di IIS per comunicare con le periferiche di Retail POS configurate nel profilo hardware. Di conseguenza, ciascuna istanza della propria postazione hardware di IIS richiede un computer che esegue il servizio Web e l'applicazione che comunica con unità. La propria postazione hardware di IIS è necessaria per tutte le applicazioni moderne di Retail POS non di Windows.

#### <a name="dedicated"></a>Dedicata

In Retail POS moderno utilizza le stazioni hardware di ** dedicato ** tipi per verificare che le periferiche direttamente collegati al computer in cui nell'app Approvazioni del modello prodotto. Tuttavia, ** dedicato ** il tipo può essere utilizzato per le stazioni hardware di IIS. In uno scenario tradizionale fisso e POS che si utilizza il POS cloud dell'applicazione di Retail POS, ** dedicato ** il tipo della propria postazione hardware utilizzato per le stazioni hardware di IIS che sono state contabilizzate nello stesso computer che esegue il POS su cloud. In una prospettiva al dettaglio delle periferiche, la propria postazione dedicata hardware di IIS è preferibile la periferica al dettaglio scenari tradizionali e impostare di Retail POS. Le stazioni dedicate hardware supportano tutte le periferiche che sono supportate nel profilo hardware.

#### <a name="shared"></a>Condiviso

Le stazioni comuni hardware sono destinate a essere utilizzate da più unità di Retail POS al corso della giornata. Le stazioni comuni hardware verranno ottimizzate per supportare solo i cassetti di cassa, le stampanti ricevimento e i terminali di pagamento. Non è possibile collegare direttamente i lettori di codice a barre autonomi, MSRs, in riga, scale, o altre unità. In caso contrario, i conflitti accadranno quando più unità di Retail POS tentano di reclamare le periferiche contemporaneamente. Ecco come i conflitti vengono gestiti per le unità supportati:

-   ** Il cassetto della cassa ** il cassetto della cassa viene aperto tramite un evento che verrà inviato all'unità. L'unica uscite che possono verificarsi quando il cassetto della cassa viene chiamato avviene se il cassetto della cassa è già aperto. Nel caso di stazioni comuni hardware, il cassetto della cassa deve essere impostato su ** condivisa ** nel profilo hardware. Questa impostazione impedisce l'accesso del controllo se il cassetto della cassa viene aperto quando si invia i controlli aperti.
-   ** La stampante delle ricevute ** se due controlli di stampa di ricevuta vengono inviati alla propria postazione hardware contemporaneamente, uno dei controlli può essere persa, a seconda dell'unità. Alcune unità con il punto vendita interna o riunione che potrà evitare questo problema. Se un comando di stampa non ha esito positivo, il cassiere riceve un messaggio di errore e riprovare può il comando di stampa dal POS.
-   ** Il terminale di pagamento ** se il cassiere tenta di offrire una transazione su un terminale di pagamento che è già utilizzato, un messaggio informa il cassiere con il terminale utilizzato e al cassiere viene chiesto di verificare nuovamente in un secondo momento. In genere, i cassieri possono visualizzare un terminale è già utilizzato e aspetterà fino al completamento di un'altra transazione prima di provino a offrire ancora.

La convalida viene applicata a una versione futura, per verificare se le unità non sostenute sono impostate per un profilo hardware mappato alla propria postazione comune hardware. Se di unità non si trovano sostenute, l'utente riceverà un messaggio indicante che le unità non sono supportati per le stazioni comuni hardware. Nel caso di stazioni comuni hardware, ** selezionato offrono ** l'opzione è impostata su Sì ** ** a livello del registro. All'utente di Retail POS verrà richiesto di selezionare la propria postazione hardware quando un'offerta è selezionata per una transazione nel POS. Quando la propria postazione hardware è selezionata solo al momento dell'offerta, la selezione della propria postazione hardware viene aggiunto direttamente al flusso di lavoro di Retail POS per scenari mobili. Come assegno complementare, la visualizzazione riga nel terminale di pagamento non viene utilizzata per scenari comuni. Se il terminale di pagamento viene utilizzato come visualizzazione di riga, altri utenti potrebbero essere bloccato dall'utilizzo di quel terminale fino al completamento della transazione. Negli scenari mobili, le righe possono essere aggiunti a una transazione in un periodo di tempo più lungo. Di conseguenza, ** selezionato offrono ** l'opzione è necessaria per garantire la disponibilità ottimale dell'unità.

### <a name="network-peripherals"></a>Unità periferiche di rete

Assegnazione di rete per le unità nel profilo hardware consente ai cassetti di cassa, alle stampanti entrate dalla sede di pagamento da collegare mediante una connessione di rete.

#### <a name="modern-pos-for-windows"></a>POS moderno per Windows

È possibile specificare i IP address per le periferiche di rete in due cifre. Se il client Windows moderno di Retail POS sta utilizzando un singolo insieme di periferiche di rete, è necessario impostare i IP address per tale unità tramite ** configurazione dell'IP ** l'opzione nel riquadro azioni per il registro stessa. Nel caso dei dispositivi di rete che verranno condivisi tra il POS, registra un profilo hardware che ha dispositivi di rete assegnati è possibile mappare direttamente nella propria postazione comune hardware. Per assegnare i IP l'indirizzo Internet, selezionare la propria postazione hardware ** vendita al dettaglio ** nella pagina quindi utilizzare ** configurazione dell'IP ** l'opzione ** stazioni hardware ** nell'area per specificare i dispositivi di rete assegnati alla propria postazione hardware. Per le stazioni hardware con solo dispositivi di rete, non è necessario distribuire la propria postazione stessa hardware. In questo caso, la propria postazione hardware è necessaria per raggruppare concettualmente solo le unità rete- indirizzabili in base alla relativa posizione nella vendita al dettaglio.

#### <a name="cloud-pos-modern-pos-for-ios-and-modern-pos-for-android"></a>Appanni il POS, il POS moderno dell'IOS e il POS moderno per Android

La logica che le unità sono associati fisicamente e le periferiche rete- indirizzabili è inclusa nella propria postazione hardware. Pertanto, per tutti i client di Retail POS al POS moderno per Windows, la propria postazione hardware di IIS deve essere attivo e la contabilizzazione per attivare il POS di comunicare con le periferiche, indipendentemente dalle periferiche vengono registrate fisicamente alla propria postazione hardware o sono previsti nella rete.

## <a name="setup-and-configuration"></a>Impostazione e configurazione
### <a name="hardware-station-installation"></a>Impostazione della propria postazione hardware

Per ulteriori informazioni, vedere [propria postazione della configurazione hardware e installazione di articoli al dettaglio retail-hardware-station-configuration-installation.md] ().

### <a name="modern-pos-for-windows-setup-and-configuration"></a>POS moderno per l'impostazione e la configurazione di Windows

Per ulteriori informazioni, vedere [configurazione di Retail POS e installazione moderne al dettaglio retail-modern-pos-device-activation.md] ().

### <a name="opos-device-setup-and-configuration"></a>Impostazione e configurazione di unità OPOS

Per ulteriori informazioni sui componenti di cassa, vedere la sezione delle interfacce di supporto" del documento. In genere, i conducenti di cassa vengono forniti dal produttore dell'unità. Quando un driver di cassa è installato, aggiunge una chiave il registro di budget di Windows in una delle seguenti posizioni:

-   ** sistema a 32 bit: ** LOCALE\_MACHINESOFTWAREOLEforRetailServiceOPOS di HKEY\_
-   ** sistema a 64 bit: ** LOCALE\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS di HKEY\_

Nella posizione di registrazione ServiceOPOS, unità configurate sono suddivise in base alla classe di unità di cassa. Nel più vengono salvati.

## <a name="supported-scenarios-by-hardware-station-type"></a>Scenari supportate dal tipo della propria postazione hardware
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Supporto del client - propria postazione hardware di IPC rispetto alla propria postazione hardware di IIS

Nella seguente tabella vengono illustrate le topologie e gli scenari di distribuzione che sono supportati.

| Cliente      | Postazione hardware di IPC | Postazione hardware di IIS |
|-------------|----------------------|----------------------|
| App di Windows | Sì                  | Sì                  |
| POS cloud   | No                   | Sì                  |
| Android     | No                   | Sì                  |
| IOS         | No                   | Sì                  |

### <a name="network-peripherals"></a>Unità periferiche di rete

Le periferiche di rete possono essere supportata direttamente nella propria postazione hardware che viene generato in Retail moderno per l'applicazione Windows. Per gli altri client, è necessario distribuire la propria postazione hardware di IIS.

| Cliente      | Postazione hardware di IPC | Postazione hardware di IIS |
|-------------|----------------------|----------------------|
| App di Windows | Sì                  | Sì                  |
| POS cloud   | No                   | Sì                  |
| Android     | No                   | Sì                  |
| IOS         | No                   | Sì                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Tipi di unità supportate dal tipo della propria postazione hardware
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>POS moderno per Windows con la propria postazione hardware di IPC (accessorio)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe di unità supportati</th>
<th>Interfacce supportati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Stampante</td>
<td><ul>
<li>)</li>
<li>Driver Windows</li>
<li>Dispositivo</li>
<li>Rete</li>
</ul></td>
</tr>
<tr class="even">
<td>Stampante 2</td>
<td><ul>
<li>)</li>
<li>Driver Windows</li>
<li>Dispositivo</li>
<li>Rete</li>
</ul></td>
</tr>
<tr class="odd">
<td>Visualizzazione riga</td>
<td>)</td>
</tr>
<tr class="even">
<td>Doppio schermo</td>
<td>Driver Windows</td>
</tr>
<tr class="odd">
<td>MSR</td>
<td><ul>
<li>)</li>
<li>UWP (alcuna impostazione è necessaria).</li>
<li>Cuneo tastiera (alcuna impostazione è necessaria).</li>
</ul></td>
</tr>
<tr class="even">
<td>Traente</td>
<td><ul>
<li>)</li>
<li>La rete <strong>Nota:</strong> un solo cassetto può essere impostata se <strong>Utilizzare il turno condiviso</strong> è configurato nel cassetto.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Cassetto 2</td>
<td><ul>
<li>)</li>
<li>La rete <strong>Nota:</strong> un solo cassetto può essere impostata se <strong>Utilizzare il turno condiviso</strong> è configurato nel cassetto.</li>
</ul></td>
</tr>
<tr class="even">
<td>Scanner</td>
<td><ul>
<li>)</li>
<li>UWP (alcuna impostazione è necessaria).</li>
<li>Cuneo tastiera (alcuna impostazione è necessaria).</li>
</ul></td>
</tr>
<tr class="odd">
<td>Scanner 2</td>
<td><ul>
<li>)</li>
<li>UWP (alcuna impostazione è necessaria).</li>
<li>Cuneo tastiera (alcuna impostazione è necessaria).</li>
</ul></td>
</tr>
<tr class="even">
<td>Scala</td>
<td>)</td>
</tr>
<tr class="odd">
<td>Tastierino PIN</td>
<td>OPOS (supporto viene fornito con personalizzazione di Connector di pagamento).</td>
</tr>
<tr class="even">
<td>Acquisizione firma</td>
<td>)</td>
</tr>
<tr class="odd">
<td>Terminale di pagamento </td>
<td><ul>
<li>Supporto unità personalizzato</li>
<li>Rete (per ulteriori informazioni, vedere la documentazione di Connector di pagamento).</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Tutti i client moderni di Retail POS con la propria postazione dedicata hardware di IIS

** Nota: ** Se la propria postazione hardware di IIS è dedicata "," esiste una relazione uno-a-uno tra il client di Retail POS e la propria postazione hardware.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe di unità supportati</th>
<th>Interfacce supportati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Stampante</td>
<td><ul>
<li>)</li>
<li>Il driver di Windows <strong>Nota:</strong> per le stampanti di Windows di una rete, l'utente della propria postazione hardware deve disporre delle autorizzazioni di accesso alla stampante.</li>
<li>Rete</li>
</ul></td>
</tr>
<tr class="even">
<td>Stampante 2</td>
<td><ul>
<li>)</li>
<li>Driver Windows</li>
<li>Rete</li>
</ul></td>
</tr>
<tr class="odd">
<td>Visualizzazione riga</td>
<td>)</td>
</tr>
<tr class="even">
<td>MSR</td>
<td>)</td>
</tr>
<tr class="odd">
<td>Traente</td>
<td><ul>
<li>)</li>
<li>La rete <strong>Nota:</strong> solo cassetto per un profilo hardware può essere impostata se <strong>Utilizzare il turno condiviso</strong> è configurato nel cassetto.</li>
</ul></td>
</tr>
<tr class="even">
<td>Cassetto 2</td>
<td><ul>
<li>)</li>
<li>Rete</li>
</ul></td>
</tr>
<tr class="odd">
<td>Scanner</td>
<td>)</td>
</tr>
<tr class="even">
<td>Scanner 2</td>
<td>)</td>
</tr>
<tr class="odd">
<td>Scala</td>
<td>)</td>
</tr>
<tr class="even">
<td>Tastierino PIN</td>
<td>OPOS (supporto viene fornito con personalizzazione di Connector di pagamento).</td>
</tr>
<tr class="odd">
<td>Sig. acquisizione</td>
<td>)</td>
</tr>
<tr class="even">
<td>Terminale di pagamento </td>
<td><ul>
<li>Supporto unità personalizzato</li>
<li>Rete (per ulteriori informazioni, vedere la documentazione di Connector di pagamento).</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Tutti i client moderni di Retail POS con la propria postazione comune hardware di IIS

** Nota: ** Se la propria postazione hardware di IIS è suddivisa "," più unità possono utilizzare la propria postazione hardware contemporaneamente. Per questo scenario, è necessario utilizzare solo le unità che vengono elencate nella seguente tabella. Se si tenta di condividere le unità che non sono elencate, ad esempio i lettori di codice a barre e i MSRs errori, accadranno quando più unità tentano di reclamare la stessa unità periferica. In futuro, tale configurazione verrà impedita esplicitamente.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe di unità supportati</th>
<th>Interfacce supportati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Stampante</td>
<td><ul>
<li>)</li>
<li>Il driver di Windows <strong>Nota:</strong> per le stampanti di Windows di una rete, l'utente della propria postazione hardware deve disporre delle autorizzazioni di accesso alla stampante.</li>
<li>Rete</li>
</ul></td>
</tr>
<tr class="even">
<td>Stampante 2</td>
<td><ul>
<li>)</li>
<li>Driver Windows</li>
<li>Rete</li>
</ul></td>
</tr>
<tr class="odd">
<td>Traente</td>
<td><ul>
<li>)</li>
<li>La rete <strong>Nota:</strong> solo cassetto per un profilo hardware può essere impostata se <strong>Utilizzare il turno condiviso</strong> è configurato nel cassetto.</li>
</ul></td>
</tr>
<tr class="even">
<td>Cassetto 2</td>
<td><ul>
<li>)</li>
<li>Rete</li>
</ul></td>
</tr>
<tr class="odd">
<td>Terminale di pagamento </td>
<td><ul>
<li>Supporto unità personalizzato</li>
<li>Rete (per ulteriori informazioni, vedere la documentazione di Connector di pagamento).</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Configurazione per scenari supportati
Per ulteriori informazioni sulla creazione di profili hardware, vedere [definire e gestire i client un canale, inclusi i registratori di cassa e le stazioni] hardware (define-maintain-channel-clients-registers-hw-stations.md). ** Nota: ** Per Microsoft Dynamics 365 per la versione 1611 delle operazioni, il profilo della propria postazione hardware non verrà più utilizzato. Gli attributi precedentemente impostate nel profilo della propria postazione hardware ora fanno parte della propria postazione hardware stesso.

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>POS moderno per Windows con la propria postazione hardware di IPC (accessorio)

Questa configurazione è la configurazione più tipica dei registri tradizionali e impostare di Retail POS. Per questo scenario, le informazioni del profilo hardware sono tracciate direttamente al registro stesso. Numero punto vendita EFT deve essere inserito il registro stesso. Per impostare questa configurazione, effettuare le seguenti operazioni.

1.  Creare un profilo hardware in cui tutte le periferiche richieste vengono configurate.
2.  Mappare il profilo hardware al registratore di cassa POS.
3.  Creare una propria postazione hardware di ** dedicato ** tipo per la vendita al dettaglio in cui il registratore di cassa POS verrà utilizzato. Descrizione è facoltativa. ** Nota: ** Non è necessario impostare alcune altre proprietà nella propria postazione hardware. Tutte le altre informazioni obbligatorie, ad esempio il profilo hardware, verranno dal registro stesso.
4.  ** Fare clic su Retail e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione **.
5.  Selezionare ** 1090 ** la programmazione di distribuzione la sincronizzazione il nuovo profilo hardware al punto vendita. Fare clic su ** esecuzione ora ** la sincronizzazione delle modifiche a Retail POS.
6.  Selezionare ** 1040 ** la programmazione di distribuzione alla nuova la propria postazione hardware al punto vendita. Fare clic su ** esecuzione ora ** la sincronizzazione delle modifiche a Retail POS.
7.  Impostare e attivare il POS moderno per Windows.
8.  Avviare il POS moderno per Windows e iniziare a utilizzare le periferiche associate.

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Tutti i client moderni di Retail POS con la propria postazione dedicata hardware di IIS

Questa configurazione può essere utilizzata per tutti i client moderni di Retail POS con la propria postazione hardware utilizzato esclusivamente da un registratore di cassa POS. Per impostare questa configurazione, effettuare le seguenti operazioni.

1.  Creare un profilo hardware in cui tutte le periferiche richieste vengono configurate.
2.  Creare una propria postazione hardware di ** dedicato ** tipo per la vendita al dettaglio in cui il registratore di cassa POS verrà utilizzato.
3.  Nella propria postazione dedicata hardware, impostare le proprietà seguenti:
    -   ** Nome host ** il nome del computer host in cui la propria postazione hardware aziendale. ** Nota: ** Del POS cloud possibile risolvere ** localhost ** determinare il computer locale in cui il POS su cloud in esecuzione. Tuttavia, il certificato necessario per accoppiare del POS cloud con la propria postazione hardware deve poter Localhost "" come nome computer. Per evitare problemi, è consigliabile possibile elencare un'istanza di ogni propria postazione dedicata hardware per il punto vendita, a seconda delle esigenze. Per ogni propria postazione hardware, il nome host necessario specificare il nome computer specifico in cui la propria postazione hardware verrà distribuita.
    -   ** Porta ** la porta da utilizzare per la propria postazione hardware comunichino con il client moderno di Retail POS.
    -   ** Il profilo hardware ** ovvero il profilo hardware non viene indicato nella propria postazione stessa hardware, il profilo hardware assegnato al registro verrà utilizzato.
    -   ** Numero di cassa POS EFT ** - ID del terminale EFT da utilizzare quando le autorizzazioni EFT vengono inviate. Questo ID viene fornita dal sistema di elaborazione delle carte di credito.
    -   ** Nome del collo ** il collo della propria postazione hardware da utilizzare per la propria postazione hardware contabilizzata.

4.  ** Fare clic su Retail e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione **.
5.  Selezionare ** 1090 ** la programmazione di distribuzione la sincronizzazione il nuovo profilo hardware al punto vendita. Fare clic su ** esecuzione ora ** la sincronizzazione delle modifiche a Retail POS.
6.  Selezionare ** 1040 ** la programmazione di distribuzione alla nuova la propria postazione hardware al punto vendita. Fare clic su ** esecuzione ora ** la sincronizzazione delle modifiche a Retail POS.
7.  Impostare la propria postazione hardware. Per ulteriori informazioni su come impostare la propria postazione hardware, vedere [propria postazione della configurazione hardware e installazione di articoli al dettaglio retail-hardware-station-configuration-installation.md] ().
8.  Impostare e attivare il POS moderno. Per ulteriori informazioni su come impostare il POS, vedere moderno [configurazione di Retail POS e installazione moderne al dettaglio retail-modern-pos-device-activation.md] ().
9.  Accesso al POS e selezionare moderno ** eseguire le operazioni di non cassetto **.
10. Avviare ** gestire le stazioni hardware ** l'operazione.
11. Fare clic su ** gestire **.
12. Nella pagina della gestione della propria postazione hardware, impostare l'opzione per attivare la propria postazione hardware.
13. Selezionare la propria postazione hardware da utilizzare e fare clic su ** coppia **.
14. Dopo che la propria postazione hardware è accoppiata, fare clic su ** ** chiusura.
15. Nella pagina di selezione della propria postazione hardware, fare clic sulla propria postazione di recente hardware selezionata in modo che venga attive.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Tutti i client moderni di Retail POS con la propria postazione comune hardware di IIS

Questa configurazione può essere utilizzata per tutti i client moderni di Retail POS che condividono le stazioni hardware con altre unità. Per impostare questa configurazione, effettuare le seguenti operazioni.

1.  Creare un profilo hardware in cui le periferiche richieste vengono configurate.
2.  Creare una propria postazione hardware di ** condivisa ** tipo per la vendita al dettaglio in cui il registratore di cassa POS verrà utilizzato.
3.  Nella propria postazione comune hardware, impostare le proprietà seguenti:
    -   ** Nome host ** il nome del computer host in cui la propria postazione hardware aziendale.
    -   ** Descrizione ** - e di cui verrà inserita di identificare la propria postazione hardware, come ** resi ** o ** parte precedente del punto vendita **.
    -   ** Porta ** la porta da utilizzare per la propria postazione hardware comunichino con il client moderno di Retail POS.
    -   ** Il profilo hardware ** - per le stazioni comuni hardware, ogni propria postazione hardware deve disporre di un profilo hardware. I profili hardware possono essere condivisi tra le stazioni hardware, ma devono essere mappati a ogni propria postazione hardware. Inoltre, si consiglia di utilizzare i turni comuni quando più unità viene utilizzata la stessa propria postazione comune hardware. Per impostare un turno comune, fare clic su ** al dettaglio e il commercio ** &gt; ** il Manica impostato ** &gt; ** POS configurato ** &gt; ** profili Retail POS ** &gt; ** profili hardware **. Per ciascun profilo hardware comune, selezionare il cassetto della cassa e impostare ** cassetto comune di turno ** l'opzione ** Sì **.
    -   ** Numero di cassa POS EFT ** - ID del terminale EFT da utilizzare quando le autorizzazioni EFT vengono inviate. Questo ID viene fornita dal sistema di elaborazione delle carte di credito.
    -   ** Nome del collo ** il collo della propria postazione hardware da utilizzare per la propria postazione hardware contabilizzata.

4.  Ripetere i passaggi 2 e 3 per ogni propria postazione aggiuntiva dell'hardware necessaria nel punto vendita.
5.  ** Fare clic su Retail e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione **.
6.  Selezionare ** 1090 ** la programmazione di distribuzione la sincronizzazione il nuovo profilo hardware al punto vendita. Fare clic su ** esecuzione ora ** la sincronizzazione delle modifiche a Retail POS.
7.  Selezionare ** 1040 ** la programmazione di distribuzione alla nuova la propria postazione hardware al punto vendita. Fare clic su ** esecuzione ora ** la sincronizzazione delle modifiche a Retail POS.
8.  Impostare la propria postazione hardware in ogni computer host impostato nel passaggio 2 e 3. Per ulteriori informazioni su come impostare la propria postazione hardware, vedere [propria postazione della configurazione hardware e installazione di articoli al dettaglio retail-hardware-station-configuration-installation.md] ().
9.  Impostare e attivare il POS moderno. Per ulteriori informazioni su come impostare il POS, vedere moderno [configurazione di Retail POS e installazione moderne al dettaglio retail-modern-pos-device-activation.md] ().
10. Accesso al POS e selezionare moderno ** eseguire le operazioni di non cassetto **.
11. Avviare ** gestire le stazioni hardware ** l'operazione.

12. Fare clic su ** gestire **.
13. Nella pagina della gestione della propria postazione hardware, impostare l'opzione per attivare la propria postazione hardware.
14. Selezionare la propria postazione hardware da utilizzare e fare clic su ** coppia **.
15. Ripetere il passaggio 14 per ogni propria postazione hardware che il POS verrà moderno.
16. A tutte le richieste stazioni hardware sono accoppiate, fare clic su ** ** chiusura.
17. Nella pagina di selezione della propria postazione hardware, fare clic sulla propria postazione di recente hardware selezionata in modo che venga attive. ** Nota: ** Se le unità vengono utilizzati spesso le diverse stazioni hardware, si consiglia di configurare il POS moderno per il trasferimento ai cassieri selezionare la propria postazione hardware per avviare il processo di offerta. ** Fare clic su Retail e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** registrare **. Selezionare Registro quindi impostare ** selezionare su offerta ** l'opzione ** Sì **. Utilizzare ** 1090 ** la programmazione di distribuzione alle modifiche di sincronizzazione nel database del canale.

## <a name="extensibility"></a>Estendibilità
Per informazioni sugli scenari di Microsoft per la propria postazione hardware, vedere [Microsoft] della propria postazione hardware (sviluppatore - itpro/hardware-station-extensibility.md).

## <a name="security"></a>Sicurezza
A seconda delle impostazioni predefinite di sicurezza correnti, le seguenti impostazioni devono essere utilizzati negli ambienti di produzione: ** Nota: ** Il installatore della propria postazione hardware automaticamente renderà tali modifiche di registrazione durante l'installazione di tramite Self Service.

-   Secure Sockets Layer (SSL) deve essere disabilitati.
-   Solo la versione 1.2 a Transport Security Layer (TLS) o un maggiore è la versione corrente) deve essere attivata e utilizzata. ** Nota: ** Per impostazione predefinita, SSL e le versioni di TLS tranne TLS 1.2 viene inserito non valido. Per modificare o consentire a questi valori, effettuare le seguenti operazioni:
    1.  Premere il logo key+R di Windows per aprire una data in esecuzione ** ** finestra.
    2.  In ** aprire ** sistemi, digitare ** Regedit ** quindi fare clic su OK ** **.
    3.  Se alla ** controllo dell'account utente ** finestra di messaggio visualizzata, fare clic su Sì ** **.
    4.  ** Editor di registrazione ** nella finestra, individuare ** LOCALE\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols di\_HKEY **. Le seguenti chiavi sono state immesse automaticamente per consentire solo TLS 1.2:
        -   TLS 1.2Server: Enabled=1
        -   TLS 1.2Server: DisabledByDefault=0
        -   TLS 1.2Client: Enabled=1
        -   TLS 1.2Client: DisabledByDefault=0
        -   TLS 1.1Server: Enabled=0
        -   TLS 1.1Client: Enabled=0
        -   TLS 1.0Server: Enabled=0
        -   TLS 1.0Client: Enabled=0
        -   SSL 3.0Server: Enabled=0
        -   SSL 3.0Client: Enabled=0
        -   SSL 2.0Server: Enabled=0
        -   SSL 2.0Client: Enabled=0
-   Nessuna porta di rete aggiuntiva devono essere aperta, a meno che non siano necessarie per A, motivi specificati.
-   la condivisione delle risorse di origine Inter- deve essere disabilitata e deve specificare le origini che verranno accettate.
-   Solo le autorità del certificato attendibili devono essere utilizzate per ottenere i certificati che verranno utilizzati nei computer che eseguono la propria postazione hardware.

** Nota: ** È molto importante che rivedere le istruzioni di protezione di IIS e i requisiti di (PCI) di settore della carta di pagamento.

## <a name="peripheral-simulator"></a>Simulatore periferica
Per ulteriori informazioni, vedere [simulatore remoto al dettaglio retail-peripheral-simulator.md] ().

## <a name="microsofttested-peripheral-devices"></a>Periferiche di Microsofttested
### <a name="ipc-built-in-hardware-station"></a>Postazione hardware di IPC (accessorio)

Nelle periferiche sono state collaudate utilizzando la propria postazione hardware di IPC che viene generato in Retail moderno per Windows.

#### <a name="printer"></a>Stampante

| Produttore | Modello    | Interfaccia | Commenti                |
|--------------|----------|-----------|-------------------------|
| Epson        | Tm-T88IV | )      |                         |
| Epson        | TM-T88V  | )      |                         |
| Stella         | TSP650II | )      |                         |
| Stella         | TSP650II | Personalizzata    | Collegato tramite la rete   |
| Stella         | mPOP     | )      | Collegato tramite Bluetooth |
| HP           | F7M67AA  | )      | Alimentato USB             |

#### <a name="bar-code-scanner"></a>Lettore di codice a barre

| Produttore  | Modello         | Interfaccia | Commenti |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | )      |          |
| Honeywell     | 1900          | UWP       |          |
| Simbolo        | LS2208        | )      |          |
| HP integrato | E1L07AA       | )      |          |
| Datalogic     | Magellan 8400 | )      |          |

#### <a name="pin-pad"></a>Tastierino PIN

| Produttore | Modello  | Interfaccia | Commenti                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | )      | È richiesta la personalizzazione di Connector di pagamento |

#### <a name="payment-terminal"></a>Terminale di pagamento 

| Produttore | Modello | Interfaccia | Commenti                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Personalizzata    | È richiesta la personalizzazione di Connector di pagamento                                |
| VeriFone     | MX925 | Personalizzata    | È richiesta la personalizzazione di Connector di pagamento; collegata tramite la rete e di USB |
| VeriFone     | MX915 | Personalizzata    | È richiesta la personalizzazione di Connector di pagamento; collegata tramite la rete e di USB |

#### <a name="cash-drawer"></a>Cassetto di cassa

| Produttore | Modello     | Interfaccia | Commenti                |
|--------------|-----------|-----------|-------------------------|
| Stella         | mPOP      | )      | Collegato tramite Bluetooth |
| APG          | Atwood    | Personalizzata    | Collegato tramite la rete   |
| Stella         | SMD2-1317 | )      |                         |
| HP           | QT457AA   | )      |                         |

#### <a name="line-display"></a>Visualizzazione riga

| Produttore  | Modello   | Interfaccia | Commenti |
|---------------|---------|-----------|----------|
| HP integrato | G6U79AA | )      |          |
| Epson         | M58DC   | )      |          |

#### <a name="signature-capture"></a>Acquisizione firma

| Produttore | Modello  | Interfaccia | Commenti |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | )      |          |

#### <a name="scale"></a>Scala

| Produttore | Modello         | Interfaccia | Commenti |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | )      |          |

#### <a name="msr"></a>MSR

| Produttore | Modello       | Interfaccia | Commenti |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | )      |          |
| HP           | IDRA-334133 | )      |          |

### <a name="dedicated-iis-hardware-station"></a>Postazione dedicata hardware di IIS

Nelle periferiche sono state collaudate utilizzando la propria postazione (condivisa) dedicata hardware di IIS insieme al POS moderno per Windows e si appannano il POS.

#### <a name="printer"></a>Stampante

| Produttore | Modello    | Interfaccia | Commenti                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | )      |                           |
| Epson        | TM-T88V  | )      |                           |
| Stella         | TSP650II | )      |                           |
| Stella         | TSP650II | Personalizzata    | Collegato tramite la rete     |
| Stella         | TSP100   | )      | Richiede i conducenti di TSP650II |
| HP           | F7M67AA  | )      | Alimentato USB               |

#### <a name="bar-code-scanner"></a>Lettore di codice a barre

| Produttore  | Modello   | Interfaccia | Commenti |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | )      |          |
| Simbolo        | LS2208  | )      |          |
| HP integrato | E1L07AA | )      |          |

#### <a name="pin-pad"></a>Tastierino PIN

| Produttore | Modello  | Interfaccia | Commenti                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | )      | È richiesta la personalizzazione di Connector di pagamento |

#### <a name="payment-terminal"></a>Terminale di pagamento 

| Produttore | Modello | Interfaccia | Commenti                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Personalizzata    | È richiesta la personalizzazione di Connector di pagamento                                |
| VeriFone     | MX925 | Personalizzata    | È richiesta la personalizzazione di Connector di pagamento; collegata tramite la rete e di USB |
| VeriFone     | MX915 | Personalizzata    | È richiesta la personalizzazione di Connector di pagamento; collegata tramite la rete e di USB |

#### <a name="cash-drawer"></a>Cassetto di cassa

| Produttore | Modello     | Interfaccia | Commenti              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizzata    | Collegato tramite la rete |
| Stella         | SMD2-1317 | )      |                       |
| HP           | QT457AA   | )      |                       |

#### <a name="line-display"></a>Visualizzazione riga

| Produttore  | Modello   | Interfaccia | Commenti |
|---------------|---------|-----------|----------|
| HP integrato | G6U79AA | )      |          |
| Epson         | M58DC   | )      |          |

#### <a name="signature-capture"></a>Acquisizione firma

| Produttore | Modello  | Interfaccia | Commenti |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | )      |          |

#### <a name="scale"></a>Scala

| Produttore | Modello         | Interfaccia | Commenti |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | )      |          |

#### <a name="msr"></a>MSR

| Produttore | Modello       | Interfaccia | Commenti |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | )      |          |
| HP           | IDRA-334133 | )      |          |

### <a name="shared-iis-hardware-station"></a>Postazione comune hardware di IIS

Nelle periferiche sono state collaudate utilizzando la propria postazione comune hardware di IIS insieme al POS moderno per Windows e si appannano il POS. ** Nota: ** Solo una stampante, un terminale di pagamento e il cassetto della cassa sono supportati.

#### <a name="printer"></a>Stampante

| Produttore | Modello    | Interfaccia | Commenti                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | )      |                           |
| Epson        | TM-T88V  | )      |                           |
| Stella         | TSP650II | )      |                           |
| Stella         | TSP650II | Personalizzata    | Collegato tramite la rete     |
| Stella         | TSP100   | )      | Richiede i conducenti di TSP650II |
| HP           | F7M67AA  | )      | Alimentato USB               |

#### <a name="payment-terminal"></a>Terminale di pagamento 

| Produttore | Modello | Interfaccia | Commenti                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Personalizzata    | È richiesta la personalizzazione di Connector di pagamento; collegata tramite la rete e di USB |
| VeriFone     | MX915 | Personalizzata    | È richiesta la personalizzazione di Connector di pagamento; collegata tramite la rete e di USB |

#### <a name="cash-drawer"></a>Cassetto di cassa

| Produttore | Modello     | Interfaccia | Commenti              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizzata    | Collegato tramite la rete |
| Stella         | SMD2-1317 | )      |                       |
| HP           | QT457AA   | )      |                       |

## <a name="troubleshooting"></a>Risoluzione dei problemi
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>L'articolo può moderno individuare la propria postazione hardware nel proprio elenco per la selezione, ma non può eseguire l'abbinamento

** Offerta: ** Verificare il seguente elenco dei punti di errore potenziale:

-   Il computer su cui è in moderno corrente deve fida del certificato utilizzato nel computer in cui viene eseguita la propria postazione hardware.
    -   Per verificare questa impostazione, in un Web browser, spostarsi all'URL seguente: nome&lt;di l&gt;'indirizzo https://Computer:&lt;Numero&gt;della porta HardwareStation//ping.
    -   L'URL viene utilizzato un ping per verificare che il computer è possibile accedere e il browser indica se il certificato del fida. Se ad esempio, in Internet Explorer, verrà visualizzata un'icona di blocchi viene visualizzata sulla barra degli indirizzi. Quando si fa clic su questa icona, Internet Explorer verifica se il certificato attualmente si di fidi. È possibile impostare il certificato nel computer locale visualizzano i dettagli del certificato indicato).
-   Nel computer in cui viene eseguita la propria postazione hardware, la porta utilizzata dalla propria postazione hardware viene aperta nel firewall.
-   La propria postazione hardware è impostato correttamente le informazioni sul conto mercantili dallo strumento mercantile Informazioni di installazione che opera alla fine di l installatore della propria postazione hardware.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>In Retail POS moderno non è possibile individuare la propria postazione hardware nel proprio elenco di selezione

** Offerta: ** Può essere effettuare una delle seguenti fattori può causare questo problema:

-   La propria postazione hardware non è stata impostata correttamente nella sede centrale. Utilizzare la procedura descritta in precedenza in questo argomento per verificare che il profilo della propria postazione hardware e la propria postazione hardware vengano immesse correttamente.
-   I processi non sono stati eseguiti aggiornare la configurazione di un canale. In questo caso, eseguire il processo 1070 per la configurazione di un canale.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>In Retail POS moderno non riflette le nuove impostazioni del cassetto della cassa

** Offerta: ** Chiudere il batch corrente. Le modifiche apportate al cassetto della cassa non vengono aggiornate al POS moderno fino alla chiusura del batch corrente.

### <a name="modern-pos-is-reporting-an-issue-with-a-retail-peripheral"></a>L'articolo è disponibile il reporting moderno un problema con un'unità periferica di vendita al dettaglio

** Offerta: ** Di seguito sono tipiche le cause di problema:

-   Verificare che le utilità di configurazione del driver da chiudere. Se le utilità sono aperte, potrebbero impedire l'accesso di moderno o la propria postazione hardware la reclamazione dell'unità.
-   Se l'unità periferica al dettaglio è suddivisa in più unità di Retail POS, verificare che appartenga a una delle seguenti categorie:
    -   Cassetto di cassa
    -   Ricevimento la stampante
    -   Terminale di pagamento 

    Se l'unità periferica non appartiene a una di queste categorie, la propria postazione hardware non è progettata per consentire all'unità periferica di essere diviso tra più unità di Retail POS.
-   Talvolta, i conducenti possono determinare gli oggetti (CCOs) della direzione centrale a interrompere l'utilizzo di funzionare correttamente. Se un'unità ultimi sono state impostate rettifiche, ma non corretto funzionamento corrente o altre situazioni, è spesso risolvere il problema reinstallando il CCOs. Per scaricare il CCOs, visitare http://monroecs.com/oposccos_current.htm>.
-   Se si frequenti variazioni periferiche nell'intervallo o la risoluzione, potrebbe essere necessario reimpostare IIS anziché attendere la cache per rinfrescarti. Per ripristinare IIS, effettuare le seguenti operazioni:
    1.  ** Inizio ** dal menu, digitare ** CMD **.
    2.  Nei risultati della ricerca, fare clic con il pulsante destro del mouse ** prompt dei comandi ** quindi fare clic su ** funziona come amministratore **.
    3.  ** Prompt dei comandi ** nella finestra, il tipo iisreset ** /Restart ** quindi premere Invio.
    4.  Dopo che IIS è stato riavviato, riavviare il POS moderno.
-   Durante la frequenti apportate le modifiche alle periferiche, se ¨¨ di avvio ed chiude il client di Retail POS, il processo di dllhost di una sessione precedente di Retail POS è interferire con la sessione corrente. In questo caso, un'unità non sia utilizzabile fino al chiudeste host di (DLL) della libreria di collegamento dinamico il file gestione la sessione precedente. Per chiudere il DLL dell'host, effettuare le seguenti operazioni:
    1.  ** Inizio ** dal menu, digitare ** task Manager **.
    2.  Nei risultati della ricerca, fare clic su ** task Manager **.
    3.  In task Manager, ** dettagli ** nella scheda, fare clic sull'intestazione di colonna in cui viene contrassegnata ** ** nome per mettere in ordine alfabetico la tabella per nome.
    4.  Scorrere fino a meno che non si ne individua dllhost.exe.
    5.  Selezionare ogni host del DLL quindi fare clic su ** attività finali **.
    6.  Dopo che i host del DLL ancora chiusi, riavviare il POS moderno.


<a name="see-also"></a>Vedere anche
--------

[Simulatore remoto al dettaglio retail-peripheral-simulator.md] ()


