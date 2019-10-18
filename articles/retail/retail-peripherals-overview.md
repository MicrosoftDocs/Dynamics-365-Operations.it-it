---
title: Periferiche di vendita al dettaglio
description: In questo argomento vengono descritti i concetti correlati alle periferiche di vendita al dettaglio.
author: rubencdelgado
manager: AnnBe
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice, RetailHardwareProfile
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cf4eb74acbd305eb67861ab3f09648bf8af8f86c
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025055"
---
# <a name="retail-peripherals"></a>Periferiche di vendita al dettaglio

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i concetti correlati alle periferiche di vendita al dettaglio. Sono descritti i vari modi che le periferiche possono essere collegate al POS e i componenti responsabili della gestione della connessione al POS.

## <a name="concepts"></a>Concetti

### <a name="pos-registers"></a>Registratori di cassa POS

Navigazione: Fare clic su **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Registratori di cassa**. Il registratore di cassa POS rappresenta un'entità utilizzata per definire le caratteristiche di un'istanza specifica del POS. Queste caratteristiche includono il profilo hardware o l'impostazione delle periferiche di vendita al dettaglio che verranno utilizzate nel registratore di cassa, il punto vendita a cui il registratore è mappato e l'esperienza visiva dell'utente che accede a tale registratore.

### <a name="devices"></a>Periferiche

Navigazione: Fare clic su **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Dispositivi**. Un dispositivo è un'entità che rappresenta un'istanza fisica di un dispositivo che viene mappato a un registratore di cassa POS. Quando viene creato un dispositivo, viene mappato a un registratore di cassa POS. L'entità dispositivo tiene traccia delle informazioni sull'attivazione di un registratore di cassa POS, il tipo di client in uso e il pacchetto dell'applicazione che è stato distribuito in un dispositivo specifico. I dispositivi possono essere mappati ai seguenti tipi di applicazione: Retail Modern POS, POS cloud vendita al dettaglio, Retail Modern POS – Windows Phone, Retail Modern POS – Android e Retail Modern POS – iOS.

### <a name="retail-modern-pos"></a>Retail Modern POS

Modern POS è il programma POS per Microsoft Windows. Può essere distribuito in sistemi operativi Windows 10.

### <a name="cloud-pos"></a>POS cloud

POS cloud è una versione browser del programma Modern POS a cui è possibile accedere in un Web browser.

### <a name="modern-pos-for-ios"></a>Modern POS per iOS

Modern POS per iOS è una versione basata su iOS del programma Modern POS che può essere distribuita su dispositivi iOS.

### <a name="modern-pos-for-android"></a>Modern POS per Android

Modern POS per Android è una versione basata su Android del programma Modern POS che può essere distribuita su dispositivi Android.

### <a name="pos-peripherals"></a>Periferiche POS

Le periferiche POS sono dispositivi supportati in modo esplicito per le funzioni POS. Queste periferiche vengono suddivise in genere in classi specifiche. Per ulteriori informazioni sulle classi, vedere la sezione "Classi di dispositivi" in questo argomento.

### <a name="hardware-station"></a>Hardware Station

Navigazione: fare clic su **Vendita al dettaglio** &gt; **Canali** &gt; **Punti vendita al dettaglio** &gt; **Tutti i punti vendita al dettaglio**. Selezionare un punto vendita, quindi fare clic sulla scheda dettaglio **Stazioni hardware**. L'impostazione **Stazione hardware** è un'impostazione a livello di canale utilizzata per definire le istanze in cui la logica della periferica di vendita al dettaglio viene distribuita. Questa impostazione a livello di canale viene utilizzata per determinare le caratteristiche della stazione hardware. Sarà inoltre utilizzata per elencare le stazioni hardware disponibili per un'istanza Modern POS in un punto vendita specifico. La stazione hardware è integrata nel programma Modern POS per Windows. La stazione hardware può essere anche distribuita in modo indipendente come programma Microsoft Internet Information Services (IIS) autonomo. In questo caso, vi si può accedere tramite una rete.

### <a name="hardware-profile"></a>Profilo hardware

Navigazione: fare clic su **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazione POS** &gt; **Profili POS** &gt; **Profili hardware**. Il profilo hardware è un elenco di dispositivi configurati per un registratore di cassa POS o una stazione hardware. Il profilo hardware può essere mappato direttamente a un registratore di cassa POS o a una stazione hardware.

## <a name="devices-classes"></a>Classi di dispositivi
Le periferiche POS vengono suddivise in genere in classi. Questa sezione descrive e offre una panoramica dei dispositivi supportati da Modern POS.

### <a name="printer"></a>Stampante

Le stampanti includono stampanti di ricevute POS tradizionali e stampanti a pagina intera. Stampante è supportata tramite OLE per Retail POS (OPOS) le interfacce driver di Microsoft Windows. Fino a due stampanti possono essere utilizzate contemporaneamente. Questa funzionalità supporta scenari in cui le ricevute dei clienti cash-and-carry vengono stampate sulle stampanti di ricevute, mentre gli ordini cliente, contenenti più informazioni, vengono stampati su una stampante a pagina intera. Le stampanti di ricevute possono essere connesse direttamente a un computer tramite USB, connesse a una rete via Ethernet o connesse mediante Bluetooth.

### <a name="scanner"></a>Scanner

Fino a due scanner di codici a barre possono essere utilizzate contemporaneamente. Questa funzionalità supporta scenari in cui uno scanner più mobile è necessario per la scansione di articoli di grandi dimensioni o pesanti, mentre uno scanner incorporato fisso viene utilizzato per la maggior parte degli articoli di formato standard, per velocizzare i tempi di check out. Gli scanner possono essere supportati tramite OPOS, piattaforma UWP (Universal Windows Platform o interfacce di lettori collegati alla tastiera. USB o Bluetooth può essere utilizzato per connettere uno scanner a un computer.

### <a name="msr"></a>MSR

Il lettore di banda magnetica (MSR) USB è possibile impostare utilizzando i driver OPOS. Se si desidera utilizzare un dispositivo MSR autonomo per le transazioni di pagamento di bonifici(EFT), il dispositivo MSR deve essere gestito da un connettore pagamenti. I MSRs autonomi possono essere utilizzati per l'immissione di programmi fedeltà, accesso dei dipendenti e immissione gift card, indipendentemente dal connettore pagamenti.

### <a name="cash-drawer"></a>Cassetto della cassa

Due cassetti di cassa possono essere supportati per profilo hardware. Questa funzione consente a due turni attivi per ciascun registratore di cassa di essere disponibili contemporaneamente. In caso di turno condiviso oppure di cassetto della cassa utilizzato da più dispositivi POS mobili contemporaneamente, un solo cassetto della cassa è consentito per profilo hardware. I cassetti della cassa possono essere connesse direttamente a un computer tramite USB, connesse a una rete o connesse a una stampante di ricevute mediante interfaccia RJ12.. In alcuni casi, i cassetti di cassa possono anche essere connessi via Bluetooth.

### <a name="line-display"></a>Visualizzazione riga

Le Visualizzazioni riga vengono utilizzate per visualizzare i prodotti, i saldi delle transazioni e altre informazioni utili al cliente durante la transazione. La visualizzazione di riga può essere connessa al computer tramite USB utilizzando i driver OPOS.

### <a name="signature-capture"></a>Acquisizione firma

I dispositivi di acquisizione firma possono essere connessi direttamente a un computer tramite USB utilizzando i driver OPOS. Quando l'acquisizione firma è configurata, il cliente viene chiesto di firmare sul dispositivo. Dopo che la firma viene fornita, è mostrato al cassiere per l'accettazione.

### <a name="scale"></a>Scala

Le bilance possono essere connessa al computer tramite USP utilizzando i driver OPOS. Quando un prodotto contrassegnato come prodotto "pesato" viene aggiunto a una transazione, il POS legge il peso dalla bilancia, aggiunge il prodotto alla transazione e utilizza la quantità che la bilancia ha fornito.

### <a name="pin-pad"></a>Tastierino PIN

I tastierini PIN sono supportati tramite OPOS, ma dovranno essere gestiti tramite un connettore pagamenti.

### <a name="secondary-display"></a>Schermo secondario

Quando uno schermo secondario è configurata, lo schermo Windows numero 2 viene utilizzato per visualizzare le informazioni di base. Lo scopo dello schermo secondario è supportare l'estensione del fornitore di software indipendente (ISV), poiché lo schermo secondario predefinito non è configurabile e mostra contenuto limitato.

### <a name="payment-device"></a>Dispositivo di pagamento

Il supporto del dispositivo di pagamento è implementato tramite il connettore pagamenti. I dispositivi di pagamento possono eseguire una o più delle funzioni fornite da altre classi di dispositivi. Ad esempio, un dispositivo di pagamento può funzionare come MSR/lettore di carte, visualizzazione riga, dispositivo di acquisizione firma, o un tastierino PIN. Il supporto per i dispositivi di pagamento è implementato indipendentemente dal supporto dei dispositivi autonomi che è fornito per altri dispositivi inclusi nel profilo hardware.

## <a name="supported-interfaces"></a>Interfacce supportate

### <a name="opos"></a>OPOS

Per contribuire a garantire che il più ampio range di dispositivi possa essere utilizzato con Retail, lo standard del settore OLE per POS è la principale piattaforma per le periferiche di vendita al dettaglio supportata. Lo standard OLE per POS è stato realizzato dalla National Retail Federation (NRF), che stabilisce i protocolli di comunicazione standard di settore per le periferiche di vendita al dettaglio. OPOS è un'implementazione largamente adottata dello standard OLE per POS. È stato sviluppato a metà degli anni '90 ed è stato aggiornato più volte da allora. OPOS fornisce un'architettura di driver di dispositivo che consente la facile integrazione dell'hardware POS con sistemi POS basati su Windows. I controlli OPOS gestiscono la comunicazione tra compatibile hardware e software POS. Un controllo OPOS consiste di due parti:

- **Oggetto controllo**  - l'oggetto controllo per una classe di dispositivi (ad esempio le visualizzazioni di riga) costituisce l'interfaccia per il programma software. Monroe Consulting Services ([www.monroecs.com](http://www.monroecs.com/)) offre un set standardizzato di oggetti controllo OPOS che sono noti come oggetti controlli comuni (CCO). I CCO vengono utilizzati per testare il componente POS di Retail. Di conseguenza, il test consente di assicurare che, se Retail supporta una classe di dispositivi tramite OPOS, molti tipi di dispositivi possono essere supportati, a condizione che il produttore fornisce un oggetto assistenza sviluppato per OPOS. Non è necessario esplicitamente verificare ogni tipo di dispositivo.
- **Oggetto assistenza** –  l'oggetto assistenza fornisce le comunicazioni tra l'oggetto controllo (CCO) e il dispositivo. In genere, l'oggetto assistenza per un dispositivo viene fornito dal produttore del dispositivo. Tuttavia, in alcuni casi, potrebbe essere necessario scaricare l'oggetto assistenza dal sito Web del produttore. Ad esempio, un oggetto assistenza più recente potrebbe essere disponibile. Per trovare l'indirizzo del sito Web del produttore, vedere la documentazione hardware.

[![Oggetto controllo e oggetto assistenza](./media/retail_peripherals_overview01.png)](./media/retail_peripherals_overview01.png)

Il supporto per l'implementazione OPOS di OLE per POS aiuta a garantire che, se i produttori di dispositivi e gli autori di software POS implementano correttamente lo standard, i sistemi POS e i dispositivi supportati possono funzionare congiuntamente, anche se in precedenza non sono stati testati insieme.

> [!NOTE]
> Il supporto OPOS non garantisce il supporto per tutti i dispositivi con driver OPOS. Retail deve prima supportare il tipo o classe di dispositivo tramite OPOS. Inoltre, gli oggetti assistenza potrebbero non essere sempre aggiornati con l'ultima versione dei CCO. È inoltre necessario tenere presente che, in generale, la qualità degli oggetti assistenza varia.

### <a name="windows"></a>Windows

La stampa della ricevuta nel POS viene ottimizzata per OPOS. OPOS tende a essere molto più veloce della stampa con Windows. Di conseguenza, è consigliabile l'utilizzo di OPOS, soprattutto negli ambienti di vendita al dettaglio in cui ricevute a 40 colonne vengono stampate e il tempo delle transazioni deve essere veloce. Per la maggior parte dei dispositivi, verranno utilizzati i controlli OPOS. Tuttavia, alcune stampanti di ricevute OPOS supportano anche i driver Windows. Utilizzando un driver di Windows, è possibile accedere agli caratteri più recenti e collegare in rete una sola stampante per più registratori di cassa. Tuttavia, sono presenti svantaggi nell'uso di driver Windows. Di seguito sono riportati alcuni esempi di svantaggi:

- Quando i driver di Windows vengono utilizzati, immagini vengono rese in rendering prima della stampa. Di conseguenza, la stampa tende a essere più lenta rispetto alle stampanti che utilizzano i controlli OPOS.
- I dispositivi connessi tramite la stampante ("connessione a catena") potrebbero non funzionare correttamente quando i driver di Windows vengono utilizzati. Ad esempio, il cassetto della cassa potrebbe non aprirsi o la stampante delle distinte potrebbe non funzionare come previsto.
- OPOS inoltre supporta una serie di variabili più estesa, specifica delle stampanti di ricevute di vendita al dettaglio, ad esempio la stampa di ritagli e distinte.

Se i controlli OPOS sono disponibili per la stampante Windows in uso, la stampante deve comunque funzionare correttamente con Retail.

### <a name="universal-windows-platform"></a>Piattaforma UWP (Universal Windows Platform)

UWP, nel caso di periferiche di vendita al dettaglio, è correlato a supporto di Windows per i dispositivi Plug and Play. Se un dispositivo Plug and Play è connesso a una versione di sistema operativo Windows che supporta quel tipo di dispositivo, non è necessario un driver per usare il dispositivo come previsto. Ad esempio, se Windows rileva un altoparlante Bluetooth, il sistema operativo sa che il dispositivo è del tipo di classe **Altoparlante**. Di conseguenza gestisce tale dispositivo come altoparlante. Non sono necessarie configurazioni aggiuntive. Nel caso di dispositivi POS, molti dispositivi USB possono essere collegati e Windows li riconoscerà come Human Interface Device (HID). Tuttavia, potrebbe non riuscire a determinare le funzionalità fornite dal dispositivo, poiché il dispositivo non specifica la classe o il tipo. In Windows 10, classi di dispositivi per i lettori di codice a barre e i MSR sono state aggiunte. Di conseguenza, se un dispositivo si dichiara a Windows 10 come di una di queste classi, Windows aspetterà gli eventi dal dispositivo nei momenti appropriati. Modern POS supporta MSR e scanner UWP. Pertanto, quando è pronto per l'input da uno di questi dispositivi e un dispositivo appartenente a una di queste classi è connesso, il dispositivo può essere utilizzato. Ad esempio, se uno scanner di codice a barre UWP viene collegato a un computer Windows 10 e l'accesso con codice a barre è configurato per Modern POS, lo scanner di codici a barre diventerà attivo nella schermata di accesso. Non sono necessarie configurazioni aggiuntive. Ulteriori classi di dispositivi UWP punto di servizio sono in corso di aggiunta a Windows. Queste classi includono le classi dei cassetti di cassa e le stampanti di ricevute. IL supporto per queste nuove classi di dispositivi in Modern POS è in sospeso.

### <a name="keyboard-wedge"></a>Lettore collegato alla tastiera

I lettori collegati alla tastiera inviano i dati nel computer come se tali dati fossero digitati su una tastiera. Pertanto, per impostazione predefinita, il campo attivo nel POS riceverà i dati sottoposti a scansione o passati. In alcuni casi, questo comportamento può determinare la scansione del tipo errato di dati nel campo errato. Ad esempio, un codice a barre può essere letto in un campo che viene utilizzato per l'entrata dei dati della carta di credito. In molti casi, esiste una logica nel POS che determina se i dati letti o passati sono un codice a barre o un passaggio di carta. Di conseguenza, i dati vengono gestiti correttamente. Tuttavia, quando i dispositivi sono impostati come OPOS anziché come lettori collegati alla tastiera, c'è più controllo su come i dati da queu dispositivi possono essere consumati, poiché si "sa" di più del dispositivo da cui derivano i dati. Ad esempio, i dati da uno scanner di codice a barre vengono riconosciuti automaticamente come codice a barre e il record associato nel database viene trovato più facilmente e più velocemente rispetto a se una stringa di ricerca generica fosse utilizzata, come nel caso dei lettori collegati alla tastiera.

### <a name="native-printer"></a>Stampante nativa

Le stampanti native (o "Dispositivo" come il tipo denominato nel profilo hardware) possono essere configurate per la richiesta all'utente di selezionare una stampante configurata per il computer. Quando una stampante del tipo **Dispositivo** è configurata, se Modern POS rileva un comando di stampa, all'utente viene chiesto di selezionare una stampante in un elenco. Questo comportamento è diverso dal funzionamento dei driver di Windows, poiché il tipo di stampante **Windows** nel profilo hardware non mostra un elenco delle stampanti. Invece, richiede che una stampante denominata viene fornita nel campo **Nome dispositivo**.

### <a name="windows"></a>Windows

Il tipo di dispositivo **Windows** è usato solo per le stampanti. Quando una stampante Windows è configurata nel profilo hardware, il nome della stampante specifica deve essere fornito. Quando Modern POS rileva eventi di stampa, se una stampante Windows è configurata, l'evento verrà inviato alla stampante Windows specificata. L'utente non verrà chiesto di selezionare una stampante.

### <a name="network"></a>Rete

i cassetti di cassa, le stampanti di ricevute e i terminali di pagamento indirizzabili in rete possono essere utilizzati in una rete, direttamente tramite la stazione hardware Interprocess Communications (IPC) integrata in Modern POS per Windows e Modern POS per le applicazioni Android o tramite la stazione hardware IIS per altri client Modern POS.

## <a name="hardware-station-deployment-options"></a>Opzioni di distribuzione delle stazioni hardware

### <a name="ipc-built-in"></a>IPC (integrata)

La stazione hardware Interprocess Communications (IPC) è integrata nel Modern POS per Windows e nel Modern POS per l'applicazione Android. Per utilizzare la stazione hardware IPC, assegnare un profilo hardware a un registratore di cassa che utilizzerà Modern POS per l'applicazione Windows. Quindi creare una stazione hardware di tipo **Dedicato** per il punto vendita in cui il registratore di cassa verrà utilizzato. Quando si avvia Modern POS, la stazione hardware IPC sarà attiva e le periferiche POS che sono stati configurati saranno pronto per l'utilizzo. Se non sono necessari temporaneamente i componenti hardware locali per qualsiasiasi motivo, utilizzare l'operazione  **Gestisci stazioni hardware** per disabilitare le funzionalità della stazione hardware. Modern POS può inoltre utilizzare la stazione hardware IPC per comunicare direttamente con le periferiche di rete.

### <a name="iis"></a>IIS

Puoi usare la versione IIS o autonoma della stazione hardware in due modi. Il descrittore "IIS" implica che l'applicazione POS si connette alla stazione hardware tramite Microsoft Internet Information Services. L'applicazione POS si connette alla stazione hardware IIS mediante servizi Web che vengono eseguiti in un computer in cui i dispositivi sono connessi. Se IIS viene utilizzato, le periferiche di vendita al dettaglio connesse alla stazione hardware possono essere utilizzate da qualsiasi registratore di cassa POS incluso nella stessa rete della stazione hardware IIS. Poiché solo Modern POS per Windows include il supporto integrato per le periferiche di vendita al dettaglio, tutte le altre applicazioni Modern POS devono utilizzare la stazione hardware IIS per comunicare con le periferiche POS configurate nel profilo hardware. Di conseguenza, ciascuna istanza della stazione hardware IIS richiede un computer che esegue il servizio Web e l'applicazione che comunica con i dispositivi. La stazione hardware IIS è necessaria per tutte le applicazioni Modern POS non Windows.

#### <a name="dedicated"></a>Dedicata

Modern POS utilizza le stazioni hardware di tipo **Dedicato** per verificare che le periferiche sono direttamente connesse al computer in cui l'app viene utilizzata. Tuttavia, il tipo **Dedicato** può essere utilizzato anche per le stazioni hardware IIS. In uno scenario tradizionale di POS fisso che utilizza il POS cloud come applicazione POS, il tipo **Dedicato** di stazione hardware viene utilizzato per le stazioni hardware IIS che sono state distribuite nello stesso computer che esegue il POS cloud. Dal punto di vista delle periferiche di vendita al dettaglio, la stazione hardware IIS dedicata offre migliore supporto per scenari tradizionali di POS fisso. Le stazioni dedicate hardware supportano tutte le periferiche che sono supportate nel profilo hardware.

#### <a name="shared"></a>Condiviso

Le stazioni hardware condivise sono destinate a essere utilizzate da più dispositivi POS nel corso della giornata. Le stazioni hardware condivise sono ottimizzate per supportare solo i cassetti di cassa, le stampanti di ricevute e i terminali di pagamento. Non è possibile connettere direttamente scanner di codici a barre, MSR, visualizzazioni riga, bilance o altri dispositivi autonomi. In caso contrario, conflitti accadranno quando più dispositivi POS tentano di usare le periferiche contemporaneamente. Ecco come i conflitti vengono gestiti per i dispositivi supportati:

- **Il cassetto della cassa** il cassetto della cassa viene aperto tramite un evento che verrà inviato al dispositivo. L'unico problema che può verificarsi quando il cassetto della cassa viene chiamato avviene se il cassetto della cassa è già aperto. Nel caso di stazioni hardware condivise, il cassetto della cassa deve essere impostato su **Condiviso** nel profilo hardware. Questa impostazione impedisce al POS di controllare se il cassetto della cassa è già aperto quando invia i comandi di apertura.
- **Stampante di ricevute**  se due controlli di stampa di ricevute vengono inviati alla stazione hardware contemporaneamente, uno dei controlli può essere perso, a seconda del dispositivo. Alcuni dispositivi hanno memoria interna o pooling che può evitare questo problema. Se un comando di stampa non ha esito positivo, il cassiere riceve un messaggio di errore e può riprovare il comando di stampa dal POS.
- **Terminale di pagamento** se il cassiere tenta di incassare una transazione su un terminale di pagamento già in uso, un messaggio informa il cassiere con il terminale è in uso e al cassiere viene chiesto di provare nuovamente in un secondo momento. In genere, i cassieri possono visualizzare che un terminale è già utilizzato e aspetterà fino al completamento di un'altra transazione prima di provare ancora.

La convalida è pianificata per una versione futura, per rilevare se i dispositivi non supportati sono configurati per un profilo hardware mappato a una stazione hardware condivisa. Se sono rilevati dispositivi non supportati, l'utente riceverà un messaggio indicante che i dispositivi non sono supportati per le stazioni hardware condivise. Nel caso di stazioni hardware condivise, l'opzione **Seleziona al momento del pagamento** è impostata su **Sì**  a livello del registratore di cassa. All'utente POS verrà richiesto di selezionare una stazione hardware quando un incasso viene selezionato per una transazione nel POS. Quando la stazione hardware è selezionata solo al momento dell'incasso, la selezione della stazione hardware viene aggiunta direttamente al flusso di lavoro POS per scenari mobili. Come vantaggio aggiuntivo, la visualizzazione riga nel terminale di pagamento non viene utilizzata per scenari comuni. Se il terminale di pagamento viene utilizzato come visualizzazione riga, altri utenti potrebbero essere bloccati dall'utilizzo di quel terminale fino al completamento della transazione. Negli scenari mobili, le righe possono essere aggiunti a una transazione in un periodo di tempo più lungo. Di conseguenza, l'opzione **Seleziona al momento del pagamento** è necessaria per garantire la disponibilità ottimale del dispositivo.

### <a name="network-peripherals"></a>Periferiche di rete

La designazione della rete per i dispositivi nel profilo hardware consente ai cassetti di cassa, alle stampanti di ricevute e ai terminali di pagamento di essere connessi mediante una connessione di rete.

#### <a name="modern-pos-for-windows"></a>Modern POS per Windows

È possibile specificare indirizzi IP per le periferiche di rete in due posti. Se il client Windows di Modern POS sta utilizzando un singolo insieme di periferiche di rete, è necessario impostare gli indirizzi IP per questi dispositivi tramite l'opzione **Configurazione IP** nel riquadro azioni per il registratore di cassa stesso. Nel caso dei dispositivi di rete che verranno condivisi tra i registratori POS, un profilo hardware che ha dispositivi di rete assegnati può essere mappato direttamente a una stazione hardware condivisa. Per assegnare gli indirizzi IP, selezionare la stazione hardware nella pagina **Punti vendita al dettaglio** quindi utilizzare l'opzione **Configurazione IP** nella sezione **Stazioni hardware** per specificare i dispositivi di rete assegnati a quella stazione hardware. Per le stazioni hardware con solo dispositivi di rete, non è necessario distribuire la stazione hardware. In questo caso, la stazione hardware è necessaria solo per raggruppare concettualmente i dispositivi indirizzabili in rete in base alla relativa posizione nel punto vendita al dettaglio.

#### <a name="modern-pos-for-android"></a>Modern POS per Android

A partire da Retail versione 8.1.3, il Modern POS per l'applicazione Android include una stazione hardware IPC incorporata. Questa stazione hardware supporta le comunicazioni con le stampanti di rete e i connettori di pagamento. Per ulteriori informazioni, visitare l'[articolo sulla documentazione dell'app Hybrid per Android](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/hybridapp#dedicated-hardware-station-support-for-the-hybrid-android-app). 

#### <a name="cloud-pos-and-modern-pos-for-ios"></a>POS cloud e Modern POS per IOS

La logica che controlla le periferiche rete connesse fisicamente e indirizzabili in rete è inclusa nella stazione hardware. Pertanto, per tutti i client POS tranne Modern POS per Windows, una stazione hardware IIS deve essere distribuita e attiva per consentire al POS di comunicare con le periferiche, indipendentemente da se le periferiche sono fisicamente connesse alla stazione hardware o indirizzate in rete.

## <a name="setup-and-configuration"></a>Impostazione e configurazione

### <a name="hardware-station-installation"></a>Installazione della stazione hardware

Per informazioni, vedere [Configurazione e installazione di una stazione hardware per la vendita al dettaglio](retail-hardware-station-configuration-installation.md).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Installazione e configurazione di Modern POS per Windows

Per informazioni, vedere [Configurazione e installazione di Retail Modern POS](retail-modern-pos-device-activation.md).

### <a name="opos-device-setup-and-configuration"></a>Installazione e configurazione di dispositivi OPOS

Per ulteriori informazioni sui componenti OPOS, vedere la sezione "Interfacce supportate" di questo documento. In genere, i driver OPOS vengono forniti dal produttore del dispositivo. Quando un driver di dispositivo OPOS viene installato, aggiunge una chiave al Registro di sistema di Windows in uno dei seguenti percorsi:

- **Sistema a 32 bit:** HKEY\_LOCAL\_MACHINESOFTWAREOLEforRetailServiceOPOS
- **Sistema a 64 bit:** HKEY\_LOCAL\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS

Nel percorso del registro ServiceOPOS, i dispositivi configurati sono organizzati in base alla classe di dispositivo OPOS. Più driver di dispositivo vengono salvati.

## <a name="supported-scenarios-by-hardware-station-type"></a>Scenari supportati per tipo di stazione hardware

### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Supporto client - stazione hardware IPC rispetto a stazione hardware IIS

Nella seguente tabella vengono illustrate le topologie e gli scenari di distribuzione che sono supportati.

| Cliente      | Stazione hardware IPC | Stazione hardware IIS |
|-------------|----------------------|----------------------|
| App Windows | Sì                  | Sì                  |
| POS cloud   | Nessuno                   | Sì                  |
| Android     | Sì                  | Sì                  |
| iOS         | Nessuno                   | Sì                  |

### <a name="network-peripherals"></a>Periferiche di rete

Le periferiche di rete possono essere supportata direttamente tramite la stazione hardware integrata nell'applicazione Modern POS per Windows. Per tutti gli altri client, è necessario distribuire una stazione hardware IIS.

| Cliente      | Stazione hardware IPC | Stazione hardware IIS |
|-------------|----------------------|----------------------|
| App Windows | Sì                  | Sì                  |
| POS cloud   | Nessuno                   | Sì                  |
| Android     | Sì                  | Sì                  |
| iOS         | Nessuno                   | Sì                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Tipi di dispositivi supportati per tipo di stazione hardware

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS per Windows con una stazione hardware IPC (integrata)

<table>
<thead>
<tr>
<th>Classe di dispositivo supportata</th>
<th>Interfacce supportate</th>
</tr>
</thead>
<tbody>
<tr>
<td>Stampante</td>
<td>
<ul>
<li>OPOS</li>
<li>Driver Windows</li>
<li>Dispositivo</li>
<li>Rete</li>
</ul>
</td>
</tr>
<tr>
<td>Stampante 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Driver Windows</li>
<li>Dispositivo</li>
<li>Rete</li>
</ul>
</td>
</tr>
<tr>
<td>Visualizzazione riga</td>
<td>OPOS</td>
</tr>
<tr>
<td>Doppio schermo</td>
<td>Driver Windows</td>
</tr>
<tr>
<td>MSR</td>
<td>
<ul>
<li>OPOS</li>
<li>UWP (nessuna impostazione richiesta.)</li>
<li>Lettore collegato alla tastiera (nessuna impostazione richiesta).</li>
</ul>
</td>
</tr>
<tr>
<td>Traente</td>
<td>
<ul>
<li>OPOS</li>
<li>Rete
<p><strong>Note:</strong> un solo cassetto può essere impostato se <strong>Consenti uso turno condiviso</strong> è configurato per il cassetto.</p>
</li>
</ul>
</td>
</tr>
<tr>
<td>Cassetto 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Rete
<p><strong>Note:</strong> un solo cassetto può essere impostato se <strong>Consenti uso turno condiviso</strong> è configurato per il cassetto.</p>
</li>
</ul>
</td>
</tr>
<tr>
<td>Scanner</td>
<td>
<ul>
<li>OPOS</li>
<li>UWP (nessuna impostazione richiesta.)</li>
<li>Lettore collegato alla tastiera (nessuna impostazione richiesta).</li>
</ul>
</td>
</tr>
<tr>
<td>Scanner 2</td>
<td>
<ul>
<li>OPOS</li>
<li>UWP (nessuna impostazione richiesta.)</li>
<li>Lettore collegato alla tastiera (nessuna impostazione richiesta).</li>
</ul>
</td>
</tr>
<tr>
<td>Scala</td>
<td>OPOS</td>
</tr>
<tr>
<td>Tastierino PIN</td>
<td>OPOS (supporto fornito tramite personalizzazione del connettore pagamenti).</td>
</tr>
<tr>
<td>Acquisizione firma</td>
<td>OPOS</td>
</tr>
<tr>
<td>Terminale di pagamento </td>
<td>
<ul>
<li>Supporto dispositivi personalizzato</li>
<li>Rete (Per ulteriori informazioni, vedere la documentazione del connettore pagamenti).</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Tutti i client Modern POS hanno una stazione hardware IIS dedicata

> [!NOTE]
> Se la stazione hardware IIS è "dedicata", esiste una relazione uno-a-uno tra il client POS e la stazione hardware.

<table>
<thead>
<tr>
<th>Classe di dispositivo supportata</th>
<th>Interfacce supportate</th>
</tr>
</thead>
<tbody>
<tr>
<td>Stampante</td>
<td>
<ul>
<li>OPOS</li>
<li>Driver Windows
<p><strong>Nota:</strong> per le stampanti di Windows in una rete, l'utente della stazione hardware deve disporre delle autorizzazioni di accesso alla stampante.</p>
</li>
<li>Rete</li>
</ul>
</td>
</tr>
<tr>
<td>Stampante 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Driver Windows</li>
<li>Rete</li>
</ul>
</td>
</tr>
<tr>
<td>Visualizzazione riga</td>
<td>OPOS</td>
</tr>
<tr>
<td>MSR</td>
<td>OPOS</td>
</tr>
<tr>
<td>Traente</td>
<td>
<ul>
<li>OPOS</li>
<li>Rete
<p><strong>Nota:</strong> un solo cassetto per profilo hardware può essere impostato se <strong>Consenti uso turno condiviso</strong> è configurato per il cassetto.</p>
</li>
</ul>
</td>
</tr>
<tr>
<td>Cassetto 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Rete</li>
</ul>
</td>
</tr>
<tr>
<td>Scanner</td>
<td>OPOS</td>
</tr>
<tr>
<td>Scanner 2</td>
<td>OPOS</td>
</tr>
<tr>
<td>Scala</td>
<td>OPOS</td>
</tr>
<tr>
<td>Tastierino PIN</td>
<td>OPOS (supporto fornito tramite personalizzazione del connettore pagamenti).</td>
</tr>
<tr>
<td>Firma - acquisizione</td>
<td>OPOS</td>
</tr>
<tr>
<td>Terminale di pagamento </td>
<td>
<ul>
<li>Supporto dispositivi personalizzato</li>
<li>Rete (Per ulteriori informazioni, vedere la documentazione del connettore pagamenti).</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Tutti i client Modern POS hanno una stazione hardware IIS condivisa

> [!NOTE]
> Se la stazione hardware IIS è "condivisa ", più dispositivi possono utilizzare la stazione hardware contemporaneamente. Per questo scenario, è necessario utilizzare solo i dispositivi elencati nella seguente tabella. Se si tenta di condividere dispositivi che non sono elencati, ad esempio scanner di codice a barre e i MSR, errori accadranno quando più dispositivi tentano di utilizzare la stessa periferica. In futuro, tale configurazione verrà impedita esplicitamente.

<table>
<thead>
<tr>
<th>Classe di dispositivo supportata</th>
<th>Interfacce supportate</th>
</tr>
</thead>
<tbody>
<tr>
<td>Stampante</td>
<td>
<ul>
<li>OPOS</li>
<li>Driver Windows
<p><strong>Nota:</strong> per le stampanti di Windows in una rete, l'utente della stazione hardware deve disporre delle autorizzazioni di accesso alla stampante.</p>
</li>
<li>Rete</li>
</ul>
</td>
</tr>
<tr>
<td>Stampante 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Driver Windows</li>
<li>Rete</li>
</ul>
</td>
</tr>
<tr>
<td>Traente</td>
<td>
<ul>
<li>OPOS</li>
<li>Rete
<p><strong>Nota:</strong> un solo cassetto per profilo hardware può essere impostato se <strong>Consenti uso turno condiviso</strong> è configurato per il cassetto.</p>
</li>
</ul>
</td>
</tr>
<tr>
<td>Cassetto 2</td>
<td>
<ul>
<li>OPOS</li>
<li>Rete</li>
</ul>
</td>
</tr>
<tr>
<td>Terminale di pagamento </td>
<td>
<ul>
<li>Supporto dispositivi personalizzato</li>
<li>Rete (Per ulteriori informazioni, vedere la documentazione del connettore pagamenti).</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Configurazione per scenari supportati

Per ulteriori informazioni sulla creazione di profili hardware, vedere [Definire e gestire i client di canale, inclusi i registratori di cassa e le stazioni hardware](define-maintain-channel-clients-registers-hw-stations.md).

> [!NOTE]
> Per Retail versione 1611, il profilo della stazione hardware non è più usato. Gli attributi precedentemente impostati nel profilo della stazione hardware ora fanno parte della stazione hardware stessa.

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS per Windows con una stazione hardware IPC (integrata)

Questa configurazione è la configurazione più tipica per i registratori di cassa POS fissi tradizionali. Per questo scenario, le informazioni del profilo hardware sono mappate direttamente al registratore stesso. Il numero di terminale EFT deve anche essere impostato sul registratore stesso. Per impostare questa configurazione, attenersi alla procedura seguente.

1. Creare un profilo hardware in cui tutte le periferiche richieste sono configurate.
2. Mappare il profilo hardware al registratore di cassa POS.
3. Creare una stazione hardware di tipo **Dedicato** per il punto vendita al dettaglio in cui il registratore di cassa POS verrà utilizzato. Una descrizione è facoltativa.

    > [!NOTE]
    > Non è necessario impostare alcuna altra proprietà nella stazione hardware. Tutte le altre informazioni obbligatorie, ad esempio il profilo hardware, verranno dal registratore di cassa stesso.

4. Fare clic su **Vendita al dettaglio** &gt; **IT vendita al dettaglio** &gt; **Programmazione della distribuzione**.
5. Selezionare la programmazione di distribuzione **1090** per sincronizzare il nuovo profilo hardware al punto vendita. Fare clic su **Esegui adesso** per sincronizzare le modifiche al POS.
6. Selezionare la programmazione di distribuzione **1070** per sincronizzare la nuova stazione hardware al punto vendita. Fare clic su **Esegui adesso** per sincronizzare le modifiche al POS.
7. Installare e attivare Modern POS per Windows.
8. Avviare Modern POS per Windows e iniziare a utilizzare le periferiche connesse.

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Tutti i client Modern POS hanno una stazione hardware IIS dedicata

Questa configurazione può essere utilizzata per tutti i client Modern POS con la stazione hardware utilizzato esclusivamente da un solo registratore di cassa POS. Per impostare questa configurazione, attenersi alla procedura seguente.

1. Creare un profilo hardware in cui tutte le periferiche richieste sono configurate.
2. Creare una stazione hardware di tipo **Dedicato** per il punto vendita al dettaglio in cui il registratore di cassa POS verrà utilizzato.
3. Nella stazione hardware dedicata, impostare le proprietà seguenti:

    - **Nome host** il nome del computer host in cui la stazione hardware viene eseguita.

        > [!NOTE]
        > Il POS cloud può risolvere **localhost** per determinare il computer locale in cui il POS cloud è in esecuzione. Tuttavia, il certificato necessario per associare il POS cloud con la stazione hardware deve anche avere "Localhost" come nome computer. Per evitare problemi, è consigliabile elencare un'istanza di ogni stazione dedicata hardware per il punto vendita, a seconda delle esigenze. Per ogni stazione hardware, il nome host deve essere il nome computer specifico in cui la stazione hardware verrà distribuita.

    - **Porta** – la porta da utilizzare per la stazione hardware comunicare con il client Modern POS.
    - **Profilo hardware**  il profilo hardware non viene fornito nella stazione hardware in sé, il profilo hardware assegnato al registratore di cassa verrà utilizzato.
    - **Numero POS EFT** - ID del terminale EFT da utilizzare quando le autorizzazioni EFT vengono inviate. Questo ID viene fornito dal sistema di elaborazione delle carte di credito.
    - **Nome pacchetto**: il pacchetto della stazione hardware da utilizzare per la stazione hardware è distribuita.

4. Fare clic su **Vendita al dettaglio** &gt; **IT vendita al dettaglio** &gt; **Programmazione della distribuzione**.
5. Selezionare la programmazione di distribuzione **1090** per sincronizzare il nuovo profilo hardware al punto vendita. Fare clic su **Esegui adesso** per sincronizzare le modifiche al POS.
6. Selezionare la programmazione di distribuzione **1040** per sincronizzare la nuova stazione hardware al punto vendita. Fare clic su **Esegui adesso** per sincronizzare le modifiche al POS.
7. Installare la stazione hardware. Per ulteriori informazioni su come installare la stazione hardware, vedere [Configurazione e installazione di una stazione hardware per la vendita al dettaglio](retail-hardware-station-configuration-installation.md).
8. Installare e attivare Modern POS, Per ulteriori informazioni su come installare Modern POS, vedere [Configurazione e installazione di Retail Modern POS](retail-modern-pos-device-activation.md).
9. Accedere Modern POS e selezionare **Eseguire operazioni non relative al cassetto**.
10. Avviare l'operazione **Gestisci stazioni hardware**
11. Fare clic su **Gestisci**.
12. Nella pagina della gestione della stazione hardware, impostare l'opzione per abilitare la stazione hardware.
13. Selezionare la stazione hardware da utilizzare e fare clic su **Associa**.
14. Dopo che la stazione hardware è associata, fare clic su **Chiudi**.
15. Nella pagina di selezione della stazione hardware, fare clic sulla stazione hardware appena selezionata in modo che diventi attiva.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Tutti i client Modern POS hanno una stazione hardware IIS condivisa

Questa configurazione può essere utilizzata per tutti i client Modern POS che condividono le stazioni hardware con altri dispositivi. Per impostare questa configurazione, attenersi alla procedura seguente.

1. Creare un profilo hardware in cui le periferiche richieste sono configurate.
2. Creare una stazione hardware di tipo **Condiviso** per il punto vendita al dettaglio in cui il registratore di cassa POS verrà utilizzato.
3. Nella stazione hardware condivisa, impostare le proprietà seguenti:

    - **Nome host** il nome del computer host in cui la stazione hardware viene eseguita.
    - **Descrizione** - Testo che consente di identificare la stazione hardware, come **Resi** o **Fronte negozio**.
    - **Porta** – la porta da utilizzare per la stazione hardware comunicare con il client Modern POS.
    - **Profilo hardware**  - per le stazioni hardware condivise, ogni stazione hardware deve disporre di un profilo hardware. I profili hardware possono essere condivisi tra le stazioni hardware, ma devono essere mappati a ogni stazione hardware. Inoltre, si consiglia di utilizzare i turni condivisi quando più dispositivi usano la stessa stazione hardware condivisa. Per impostare un turno condiviso, fare clic su **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Profili POS** &gt; **Profili hardware**. Per ciascun profilo hardware condiviso, selezionare il cassetto della cassa e impostare l'opzione **Cassetto turno condiviso** su **Sì**.
    - **Numero POS EFT** - ID del terminale EFT da utilizzare quando le autorizzazioni EFT vengono inviate. Questo ID viene fornito dal sistema di elaborazione delle carte di credito.
    - **Nome pacchetto**: il pacchetto della stazione hardware da utilizzare per la stazione hardware è distribuita.

4. Ripetere i passaggi 2 e 3 per ciascuna stazione hardware aggiuntiva necessaria nel punto vendita.
5. Fare clic su **Vendita al dettaglio** &gt; **IT vendita al dettaglio** &gt; **Programmazione della distribuzione**.
6. Selezionare la programmazione di distribuzione **1090** per sincronizzare il nuovo profilo hardware al punto vendita. Fare clic su **Esegui adesso** per sincronizzare le modifiche al POS.
7. Selezionare la programmazione di distribuzione **1040** per sincronizzare la nuova stazione hardware al punto vendita. Fare clic su **Esegui adesso** per sincronizzare le modifiche al POS.
8. Installare la stazione hardware in ogni computer host impostato nel passaggio 2 e 3. Per ulteriori informazioni su come installare la stazione hardware, vedere [Configurazione e installazione di una stazione hardware per la vendita al dettaglio](retail-hardware-station-configuration-installation.md).
9. Installare e attivare Modern POS, Per ulteriori informazioni su come installare Modern POS, vedere [Configurazione e installazione di Retail Modern POS](retail-modern-pos-device-activation.md).
10. Accedere Modern POS e selezionare **Eseguire operazioni non relative al cassetto**.
11. Avviare l'operazione **Gestisci stazioni hardware**
12. Fare clic su **Gestisci**.
13. Nella pagina della gestione della stazione hardware, impostare l'opzione per abilitare la stazione hardware.
14. Selezionare la stazione hardware da utilizzare e fare clic su **Associa**.
15. Ripetere il passaggio 14 per ogni stazione hardware che Modern POS userà.
16. Dopo avere associato tutte le stazioni hardware richieste, fare clic su **Chiudi**.
17. Nella pagina di selezione della stazione hardware, fare clic sulla stazione hardware appena selezionata in modo che diventi attiva.

    > [!NOTE]
    > Se i dispositivi usano spesso diverse stazioni hardware, si consiglia di configurare Modern POS per chiedere ai cassieri di selezionare una stazione hardware quando avviano il processo di incasso. Fare clic su **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Registratori di cassa**. Selezionare il registratore di cassa quindi impostare l'opzione **Seleziona al momento del pagamento** su **Sì**. Utilizzare la programmazione di distribuzione **1090** per sincronizzare le modifiche nel database del canale.

## <a name="extensibility"></a>Estendibilità

Per informazioni sugli scenari di estendibilità per la stazione hardware, vedere [Estendibilità delle stazioni hardware](dev-itpro/hardware-station-extensibility.md).

## <a name="security"></a>Sicurezza

A seconda degli standard di sicurezza correnti, le seguenti impostazioni devono essere utilizzate in un ambiente di produzione:

> [!NOTE]
> Il programma di installazione della stazione hardware eseguirà automaticamente tali modifiche nel Registro di sistema durante l'installazione tramite Self Service

- Secure Sockets Layer (SSL) deve essere disabilitato.
- Solo Transport Layer Security (TLS) versione 1.2 (o la versione corrente superiore) deve essere abilitato e usato.

    > [!NOTE]
    > Per impostazione predefinita, SSL e tutte le versioni di TLS tranne TLS 1.2 sono disabilitati.

    Per modificare o abilitare questi valori, effettuare le operazioni seguenti:

    1. Premere il tasto WINDOWS + R per aprire la finestra **Esegui**
    2. Nel campo **Open** digitare **Regedit** quindi scegliere **OK**.
    3. Se appare una finestra di messaggio **Controllo account utente** fare clic su **Sì**.
    4. Nella finestra **Editor del Registro di sistema**, passare a **HKEY\_LOCAL\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols**. Le seguenti chiavi sono state immesse automaticamente per consentire solo TLS 1.2:

        - TLS 1.2Server:Enabled=1
        - TLS 1.2Server:DisabledByDefault=0
        - TLS 1.2Client:Enabled=1
        - TLS 1.2Client:DisabledByDefault=0
        - TLS 1.1Server:Enabled=0
        - TLS 1.1Client:Enabled=0
        - TLS 1.0Server:Enabled=0
        - TLS 1.0Client:Enabled=0
        - SSL 3.0Server:Enabled=0
        - SSL 3.0Client:Enabled=0
        - SSL 2.0Server:Enabled=0
        - SSL 2.0Client:Enabled=0

- Nessuna porta di rete aggiuntiva devono essere aperta, a meno che non siano necessarie per motivi noti e specificati.
- La condivisione delle risorse interorigine deve essere disabilitata e deve specificare le origini consentite accettate.
- Solo le autorità di certificazione attendibili devono essere utilizzate per ottenere i certificati che verranno utilizzati nei computer che eseguono la stazione hardware.

> [!NOTE]
> È molto importante rivedere le linee guida di sicurezza di IIS e i requisiti PCI (Payment Card Industry).

## <a name="peripheral-simulator"></a>Simulatore periferica

Per ulteriori informazioni, vedere [Simulatore periferica di vendita al dettaglio](dev-itpro/retail-peripheral-simulator.md).

## <a name="microsoft-tested-peripheral-devices"></a>Periferiche testate da Microsoft

### <a name="ipc-built-in-hardware-station"></a>Stazione hardware IPC (integrata)

Le periferiche seguenti sono state testate utilizzando la stazione hardware IPC integrata in Modern POS per Windows.

#### <a name="printer"></a>Stampante

| Produttore | Modello      | Interfaccia | Commenti                |
|--------------|------------|-----------|-------------------------|
| Epson        | Tm-T88IV   | OPOS      |                         |
| Epson        | TM-T88V    | OPOS      |                         |
| Epson        | ePOS-Print | Personalizzata    | Collegato tramite la rete   |
| Star         | TSP650II   | OPOS      |                         |
| Star         | TSP650II   | Personalizzata    | Collegato tramite la rete   |
| Star         | mPOP       | OPOS      | Collegato tramite Bluetooth |
| HP           | F7M67AA    | OPOS      | USB alimentato             |

#### <a name="bar-code-scanner"></a>Scanner di codice a barre

| Produttore  | Modello         | Interfaccia | Commenti |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| Simbolo        | LS2208        | OPOS      |          |
| Integrato HP | E1L07AA       | OPOS      |          |
| Datalogic     | Magellan 8400 | OPOS      |          |

#### <a name="pin-pad"></a>Tastierino PIN

| Produttore | Modello  | Interfaccia | Commenti                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | È richiesta la personalizzazione del connettore pagamenti |

#### <a name="payment-terminal"></a>Terminale di pagamento 

| Produttore | Modello        | Interfaccia | Commenti                                                                       |
|--------------|--------------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300        | Personalizzata    | È richiesta la personalizzazione del connettore pagamenti                                |
| VeriFone     | MX925        | Personalizzata    | È richiesta la personalizzazione del connettore pagamenti; collegata tramite la rete e USB |
| VeriFone     | MX915        | Personalizzata    | È richiesta la personalizzazione del connettore pagamenti; collegata tramite la rete e USB |
| VeriFone     | Vedere i commenti | Adyen     | Il connettore Adyen supporta tutti i dispositivi elencati [qui](https://www.adyen.com/pos-payments/terminals) |

#### <a name="cash-drawer"></a>Cassetto della cassa

| Produttore | Modello     | Interfaccia | Commenti                |
|--------------|-----------|-----------|-------------------------|
| Star         | mPOP      | OPOS      | Collegato tramite Bluetooth |
| APG          | Atwood    | Personalizzata    | Collegato tramite la rete   |
| Star         | SMD2-1317 | OPOS      |                         |
| HP           | QT457AA   | OPOS      |                         |

#### <a name="line-display"></a>Visualizzazione riga

| Produttore  | Modello   | Interfaccia | Commenti |
|---------------|---------|-----------|----------|
| Integrato HP | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Acquisizione firma

| Produttore | Modello  | Interfaccia | Commenti |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Scala

| Produttore | Modello         | Interfaccia | Commenti |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>MSR

| Produttore | Modello       | Interfaccia | Commenti |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="dedicated-iis-hardware-station"></a>Stazione hardware IIS dedicata

Le periferiche seguenti sono state testate utilizzando una stazione hardware IIS dedicata (non condivisa) insieme a Modern POS per Windows e il POS cloud.

#### <a name="printer"></a>Stampante

| Produttore | Modello    | Interfaccia | Commenti                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Star         | TSP650II | OPOS      |                           |
| Star         | TSP650II | Personalizzata    | Collegato tramite la rete     |
| HP           | F7M67AA  | OPOS      | USB alimentato               |

#### <a name="bar-code-scanner"></a>Scanner di codice a barre

| Produttore  | Modello   | Interfaccia | Commenti |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | OPOS      |          |
| Simbolo        | LS2208  | OPOS      |          |
| Integrato HP | E1L07AA | OPOS      |          |

#### <a name="pin-pad"></a>Tastierino PIN

| Produttore | Modello  | Interfaccia | Commenti                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | È richiesta la personalizzazione del connettore pagamenti |

#### <a name="payment-terminal"></a>Terminale di pagamento 

| Produttore | Modello | Interfaccia | Commenti                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Personalizzata    | È richiesta la personalizzazione del connettore pagamenti                                |
| VeriFone     | MX925 | Personalizzata    | È richiesta la personalizzazione del connettore pagamenti; collegata tramite la rete e USB |
| VeriFone     | MX915 | Personalizzata    | È richiesta la personalizzazione del connettore pagamenti; collegata tramite la rete e USB |

#### <a name="cash-drawer"></a>Cassetto della cassa

| Produttore | Modello     | Interfaccia | Commenti              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizzata    | Collegato tramite la rete |
| Star         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

#### <a name="line-display"></a>Visualizzazione riga

| Produttore  | Modello   | Interfaccia | Commenti |
|---------------|---------|-----------|----------|
| Integrato HP | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Acquisizione firma

| Produttore | Modello  | Interfaccia | Commenti |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Scala

| Produttore | Modello         | Interfaccia | Commenti |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>MSR

| Produttore | Modello       | Interfaccia | Commenti |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="shared-iis-hardware-station"></a>Stazione hardware IIS condivisa

Le periferiche seguenti sono state testate utilizzando una stazione hardware IIS condivisa insieme a Modern POS per Windows e il POS cloud.

> [!NOTE]
> Solo una stampante, un terminale di pagamento e un cassetto della cassa sono supportati.

#### <a name="printer"></a>Stampante

| Produttore | Modello    | Interfaccia | Commenti                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Star         | TSP650II | OPOS      |                           |
| Star         | TSP650II | Personalizzata    | Collegato tramite la rete     |
| HP           | F7M67AA  | OPOS      | USB alimentato               |

#### <a name="payment-terminal"></a>Terminale di pagamento 

| Produttore | Modello | Interfaccia | Commenti                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Personalizzata    | È richiesta la personalizzazione del connettore pagamenti; collegata tramite la rete e USB |
| VeriFone     | MX915 | Personalizzata    | È richiesta la personalizzazione del connettore pagamenti; collegata tramite la rete e USB |

#### <a name="cash-drawer"></a>Cassetto della cassa

| Produttore | Modello     | Interfaccia | Commenti              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizzata    | Collegato tramite la rete |
| Star         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>Modern POS può individuare la stazione hardware nel proprio elenco per la selezione, ma non può eseguire l'associazione

**Soluzione:** Verificare il seguente elenco dei punti di errore potenziali:

- Il computer su cui è in esecuzione Modern POS considera attendibile il certificato utilizzato nel computer in cui viene eseguita la stazione hardware.

    - Per verificare questa impostazione, in un Web browser, spostarsi all'URL seguente: `https://<Computer Name>:<Port Number>/HardwareStation/ping`.
    - L'URL utilizza un ping per verificare che al computer è possibile accedere e il browser indica se il certificato è attendibile. Ad esempio, in Internet Explorer, verrà visualizzata un'icona lucchetto sulla barra degli indirizzi. Quando si fa clic su questa icona, Internet Explorer verifica se il certificato è attualmente attendibile. È possibile installare il certificato nel computer locale visualizzando i dettagli del certificato indicato.

- Nel computer in cui viene eseguita la stazione hardware, la porta utilizzata dalla stazione hardware viene aperta nel firewall.
- La stazione hardware è installato correttamente le informazioni sull'account esercente tramite lo strumento Installa le informazioni sull'esercente che viene eseguito alla fine dell'installazione della stazione hardware.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>Modern POS non può rilevare la stazione hardware nel proprio elenco di selezione

**Soluzione:** Uno dei seguenti fattori può causare questo problema:

- La stazione hardware non è stata impostata correttamente nella sede centrale. Utilizzare la procedura descritta in precedenza in questo argomento per verificare che il profilo della stazione hardware e la stazione hardware siano immessi correttamente.
- I processi non sono stati eseguiti per aggiornare la configurazione di canale. In questo caso, eseguire il processo 1070 per la configurazione di canale.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>Modern POS non riflette le nuove impostazioni del cassetto della cassa

**Soluzione:** Chiudere il batch corrente. Le modifiche apportate al cassetto della cassa non vengono aggiornate in Modern POS fino alla chiusura del batch corrente.

### <a name="modern-pos-is-reporting-an-issue-with-a-retail-peripheral"></a>Modern POS segnala un problema con una periferica di vendita al dettaglio

**Soluzione:**  Di seguito alcune tipiche cause del problema:

- Verificare che altre utilità di configurazione di driver di dispositivo siano chiuse. Se le utilità sono aperte, potrebbero impedire a Modern POS o alla stazione hardware di utilizzare il dispositivo.
- Se la periferica di vendita al dettaglio è condivisa in più dispositivi POS, verificare che appartenga a una delle seguenti categorie:

    - Cassetto della cassa
    - Stampante di ricevute
    - Terminale di pagamento 

    Se la periferica non appartiene a una di queste categorie, la stazione hardware non è progettata per consentire all'unità periferica di essere condivisa tra più dispositivi POS.

- Talvolta, i driver di dispositivo possono determinare che gli oggetti controlli comuni (CCO) smettano di funzionare correttamente. Se un dispositivo è stato installato di recente ma non funziona bene o si notano altri problemi, è spesso possibile risolvere il problema reinstallando i CCO. Per scaricare i CCO, visitare <http://monroecs.com/oposccos_current.htm>.
- Se si fanno frequenti modifiche alle periferiche durante il test o la risoluzione dei problemi, potrebbe essere necessario reimpostare IIS anziché attendere che la cache si aggiorni. Per reimpostare IIS, attenersi alla seguente procedura:

    1. Dal menu **Start** digitare **CMD**.
    2. Nei risultati della ricerca, fare clic con il pulsante destro del mouse su **Prompt dei comandi** quindi fare clic su **Esegui come amministratore**.
    3. Nella finestra **Prompt dei comandi**, digitare **iisreset /Restart** quindi premere Invio.
    4. Dopo che IIS è stato riavviato, riavviare Modern POS.

- Mentre si fanno frequenti modifiche alle periferiche, se si fanno anche frequenti avvii e uscite dal client POS, il processo dllhost di una sessione POS precedente può interferire con la sessione corrente. In questo caso, un dispositivo potrebbe non essere utilizzabile fino a che si chiude l'host della libreria di collegamento dinamico (DLL) che gestisce la sessione precedente. Seguire questi passaggi per chiudere l'host DLL.

    1. Dal menu **Start** digitare **Gestione attività**.
    2. Nei risultati della ricerca, fare clic su  **Gestione attività**.
    3. In Gestione attività, nella scheda **Dettagli**, fare clic sull'intestazione di colonna etichettata  **Nome** per mettere in ordine alfabetico la tabella per nome.
    4. Scorrere fino a che non si individua dllhost.exe.
    5. Selezionare ogni host DLL quindi fare clic su **Termina attività**.
    6. Dopo che gli host DLL sono stati chiusi, riavviare Modern POS.

## <a name="additional-resources"></a>Risorse aggiuntive

[Simulatore di periferica Retail](dev-itpro/retail-peripheral-simulator.md)
