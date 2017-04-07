---
title: Consente di definire e gestire i client un canale, i registratori di cassa e le stazioni hardware
description: Questo wiki illustra come connettere periferiche al Retail POS.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: dee5745670ad86000795f2913f99f49c0f123a00
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-maintain-channel-clients-registers-and-hardware-stations"></a>Consente di definire e gestire i client un canale, i registratori di cassa e le stazioni hardware

Questo wiki illustra come connettere periferiche al Retail POS.

**Nota:** per le istruzioni di installazione specifiche, vedere [Installazione e configurazione di una stazione hardware Retail](retail-hardware-station-configuration-installation.md) e [Download/installazione self-service di Retail Modern POS e attivazione dispositivi di Modern POS e POS cloud](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Componenti principali
Diversi componenti vengono utilizzati per definire le relazioni tra un punto vendita, i registratori di cassa POS (Point of Sale) o i canali all'interno del punto vendita e le periferiche di vendita al dettaglio che tali registratori o canali utilizzano per elaborare le transazioni. In questa sezione viene descritto ciascun componente e illustrato come deve essere utilizzato in una distribuzione di punti vendita al dettaglio.

### <a name="pos-registers"></a>Registratori di cassa POS

Percorso: ** Fare clic su Retail e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** registrare **. Il registratore di cassa POS rappresenta un'entità utilizzata per definire le caratteristiche di un'istanza specifica del POS. Le caratteristiche includono il profilo hardware o l'impostazione delle periferiche al dettaglio che verranno utilizzate nel registratore, il punto vendita dal registro è mappato a ed esperienza grafica dell'utente connesso a tale registro.

### <a name="devices"></a>Periferiche

Percorso: ** Fare clic su Retail e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** ** unità. Un dispositivo è un'entità che rappresenta un'istanza fisica di un dispositivo che viene mappato a un registratore di cassa POS. Quando viene creato un dispositivo, viene mappato a un registratore di cassa POS. L'entità dispositivo tiene traccia delle informazioni sull'attivazione di un registratore di cassa POS, il tipo di client in uso e il pacchetto dell'applicazione che è stato distribuito in un dispositivo specifico. I dispositivi possono essere di due tipi: **Retail Modern POS** (MPOS) o **POS cloud vendita al dettaglio** (POS cloud).

#### <a name="mpos"></a>MPOS

MPOS è un'applicazione client POS che è installata su Windows 8.1 o un sistema operativo successivo basato su PC. Se il tipo di applicazione **Retail Modern POS** viene mappato a un dispositivo, è possibile specificare il pacchetto di download per un determinato dispositivo. Il pacchetto di download può essere personalizzato per includere diverse versioni del pacchetto di installazione. La possibilità di distribuire pacchetti diversi offre flessibilità nei casi in cui diversi registratori di cassa POS potrebbero richiedere diverse integrazioni. MPOS viene distribuito con una stazione hardware integrata.

#### <a name="cloud-pos"></a>POS cloud

L'articolo di cloud a un POS basato su browser. Poiché viene eseguito nel browser, il POS su cloud non richiede Windows 8.1 o un sistema operativo in base al PC successivo. Se il tipo di applicazione **POS cloud vendita al dettaglio** viene mappato a un determinato dispositivo nel back office, il dispositivo può essere utilizzato tramite il browser senza che sia necessario scaricare o installare un pacchetto. POS cloud richiede che una stazione hardware utilizzi hardware oltre la scansione di codice a barre basata su lettore collegato alla tastiera.

### <a name="hardware-profile"></a>Profilo hardware

Percorso: Fare clic su commercio ** ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** il POS profili ** &gt; ** profili hardware **. Un profilo hardware identifica l'hardware connesso a un registratore di cassa POS o una stazione hardware. Il profilo hardware viene inoltre utilizzato per specificare i parametri del processore di pagamento che devono essere utilizzati durante la comunicazione con il kit di sviluppo software (SDK) per il pagamento. (L'SDK per il pagamento viene distribuito come parte della stazione hardware).

### <a name="hardware-station"></a>Stazione hardware

Percorso: ** Fare clic su Retail e il commercio ** &gt; ** canali ** &gt; ** vendita al dettaglio ** &gt; ** tutte le vendite al dettaglio **. Selezionare un punto vendita, quindi fare clic sulla scheda dettaglio **Stazioni hardware**. Una stazione di hardware è un'istanza della logica di business che guida le periferiche POS. Una stazione hardware viene automaticamente installata con MPOS. In alternativa, la stazione hardware può essere installata come componente autonomo e quindi accessibile a MPOS o POS cloud tramite un servizio Web. La stazione hardware deve essere definita a livello di canale.

### <a name="hardware-station-profile"></a>Profilo stazione hardware

Percorso: Fare clic su commercio ** ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** il POS profili ** &gt; ** propria postazione di profili hardware **. Mentre la stazione hardware in sé specificata al livello del canale include informazioni specifiche dell'istanza, ad esempio l'URL per la stazione hardware, il profilo stazione hardware include informazioni che possono essere statiche o condivise tra più stazioni hardware. Le informazioni statiche includono la porta che deve essere utilizzata, il pacchetto di stazione hardware e il profilo hardware. Le informazioni statiche includono anche una descrizione del tipo di stazione hardware che si sta distribuendo, ad esempio **Check out **o **Resi**, a seconda dell'hardware necessario per ogni stazione hardware specifica.

## <a name="scenarios"></a>Scenari
### <a name="mpos-with-connected-peripheral-devices"></a>MPOS con i dispositivi periferici collegati

[POS tradizionale e fisso![(]. /media/traditional-300x279.png)](. /media/traditional.png) Per collegare MPOS le periferiche di POS in uno scenario tradizionale e fisso di Retail POS, è innanzitutto traversano al registro stesso e assegnare un profilo hardware. Per i registri di Retail POS ** al dettaglio e il commercio ** &gt; ** al Manica impostato ** &gt; ** POS configurato ** &gt; ** registrare **. Dopo aver assegnato il profilo hardware, sincronizzare le modifiche al database di canale utilizzando la programmazione della distribuzione "Registratori di cassa". Per le programmazioni di distribuzione ** al dettaglio e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione **. Successivamente, impostazione una stazione "locale" sul canale. ** Fare clic su Retail e il commercio ** &gt; ** canali ** &gt; ** vendita al dettaglio ** &gt; ** tutte le vendite al dettaglio ** e selezionare un punto vendita. Quindi, nella scheda dettaglio **Stazioni hardware**, fare clic su **Aggiungi** per aggiungere una stazione hardware. Immettere una descrizione, immettere **localhost** come nome host e quindi sincronizzare le modifiche al canale utilizzando la programmazione di distribuzione "Configurazione canale". Per le programmazioni di distribuzione ** al dettaglio e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione **. Infine, in MPOS, utilizzare l'operazione **Seleziona stazione hardware** per selezionare la stazione hardware **localhost**. Impostare la stazione hardware su **Attivo**. Il profilo hardware utilizzato in questo scenario deve provenire dal registratore di cassa POS stesso. Un profilo di stazione hardware non è necessario per questo scenario. **Nota:** per alcune modifiche al profilo hardware, quali cambiamenti di registratori di cassa, è necessario aprire un nuovo turno dopo che le modifiche sono state sincronizzate al canale. **Nota:** POS cloud deve utilizzare la stazione hardware autonoma per comunicare con periferiche di vendita al dettaglio.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>MPOS o POS cloud con una stazione hardware autonoma

alignleft" width= " 300 "di align= " a " id= del titolo\[con\_340041 "\][periferiche comuni![(]. /media/shared-300x254.png)](. Le periferiche\[/caption comuni di\] /media/shared.png) in questo scenario, la propria postazione autonoma hardware viene diviso tra i client del POS cloud e di MPOS. Per questo scenario è necessario creare un profilo di stazione hardware per specificare il pacchetto di download, la porta e il profilo hardware che utilizza la stazione hardware. Per trovare il profilo della propria postazione hardware ** al dettaglio e il commercio ** &gt; ** al Manica impostato ** &gt; ** POS configurato ** &gt; ** profili Retail POS ** &gt; ** propria postazione di profili hardware **. Dopo avere creato il profilo della propria postazione hardware, individuare il canale al dettaglio specifico (** al dettaglio e il commercio ** &gt; ** canali ** &gt; ** vendita al dettaglio ** &gt; ** tutte le vendite al dettaglio **) e aggiungere una nuova propria postazione hardware. Mappare la nuova stazione hardware al profilo stazione hardware creato in precedenza. A questo punto, fornire una descrizione che consenta al cassiere di identificare la stazione hardware. ** Nome host ** nel campo, immettere il computer URL ospite il formato seguente: ** https://MachineName:Port/HardwareStation**&lt;&gt;. Sostituisci (**&lt;MachineName: Porta&gt;** con il nome della macchina della propria postazione hardware e la porta specificata nel profilo della propria postazione hardware.) Per la propria postazione autonoma hardware, è necessario specificare anche ID terminale di (EFT) di bonifico. Questo valore identifica il terminale EFT connesso alla stazione hardware quando il connettore pagamenti comunica con il provider di pagamenti. Successivamente, dal computer stazione hardware effettivo, passare al canale e selezionare la stazione hardware. Fare clic su **Download**e installare la stazione hardware. Successivamente, da MPOS o POS cloud, utilizzare l'operazione **Seleziona stazione hardware** per selezionare la stazione hardware installata in precedenza. Selezionare **Associa** per stabilire una relazione protetta tra il POS e la stazione hardware. Questo passaggio deve essere completato una volta per ogni combinazione di POS e stazione hardware. Dopo che la stazione hardware è associata, viene utilizzata la stessa operazione per rendere attiva la stazione hardware mentre viene utilizzata. Per questo esempio, il profilo hardware deve essere assegnato al profilo della propria postazione hardware anziché il registro stesso. Se per qualsiasiasi motivo la propria postazione hardware non dispone di un profilo hardware direttamente assegnato, il profilo hardware assegnato al registro viene utilizzato

## <a name="client-maintenance"></a>Manutenzione client
### <a name="registers"></a>Registri

I registratori di cassa POS sono gestiti principalmente tramite i registratori di cassa stessi, nonché attraverso i profili assegnati ai registratori. Attributi specifici di un singolo registratore di cassa vengono gestiti a livello di registro. Questi attributi includono il punto vendita in cui viene utilizzato il registratore, il numero del registratore, la descrizione e l'ID terminale EFT specifico per il registratore di cassa.

### <a name="pos-profiles"></a>Profili POS

Per i profili Retail POS ** al dettaglio e il commercio ** &gt; ** al Manica impostato ** &gt; ** POS configurato ** &gt; ** profili Retail POS **. È utile gestire molti aspetti di un registratore tramite profili, in quanto i profili possono essere condivisi tra più registratori. I profili possono essere mappati a un singolo registratore o, se un profilo è valido a livello di intero punto vendita, al punto vendita al dettaglio. Le sezioni seguenti descrivono i profili POS e le modalità di utilizzo.

#### <a name="offline-profile"></a>Profilo offline

Il profilo offline è impostato a livello di punto vendita. Viene utilizzato per specificare le impostazioni di caricamento per le transazioni che vengono eseguite in un registratore di cassa POS mentre non è connesso al database di canale.

#### <a name="functionality-profile"></a>Profilo funzionalità

Il profilo funzionalità è impostato a livello di punto vendita. È stata utilizzato per specificare le impostazioni a livello del punto vendita relativi alle funzioni eseguibili nel POS. Nelle capacità vengono gestite tramite il profilo funzionalità. Queste funzionalità sono organizzate per scheda dettaglio.

-   Scheda dettaglio **Generale**:
    -   Organizzazione internazionale per la standardizzazione (ISO)
    -   Crea cliente in modalità offline
    -   Invia profilo ricevuta per posta elettronica
    -   Autenticazione personale centralizzata
-   Scheda dettaglio **Funzioni**:
    -   Gestione dell'accesso e accesso esteso.
    -   Aspetti finanziari e relativi alla valuta del POS, come la possibilità di inserire prezzi e se decimali sono necessari per la valuta secondaria.
    -   Abilitazione della registrazione dell'orario tramite il POS.
    -   Come prodotti e pagamenti appaiono nel POS e sulle ricevute.
    -   Gestione del riepilogo giornaliero
    -   Parametri di memorizzazione transazioni del database del canale.
    -   Come i clienti sono ricercati e creati dal POS.
    -   Come sono calcolati gli sconti.
-   Scheda dettaglio **Importo**:
    -   Prezzi massimi e minimi consentiti.
    -   Applicazione di sconti e calcolo.
-   Scheda dettaglio **Codici informativi**:
    -   Tutti gli aspetti dell'impostazione dei codici di informazioni vengono gestiti al POS. Per informazioni dettagliate, vedere [] codici di informazioni information-codes-retail.md ().
-   Scheda dettaglio **Numerazione ricevute**:
    -   Specificare le maschere di numerazione ricevute, che potrebbero includere segmenti per il numero di punto vendita, numero di terminale, costanti, e se stampare vendite, resi, ordini cliente e offerte in sequenze separate, o se devono tutti seguire la stessa sequenza.

#### <a name="receipt-profiles"></a>Profili ricevuta

I profili ricevuta vengono assegnati alle stampanti nel profilo hardware. Vengono utilizzati per specificare i tipi di ricevuta che vengono stampati su una stampante specifica. I profili includono impostazioni relative ai formati e le impostazioni che determinano se la ricevuta viene sempre stampata o se al cassiere viene richiesto di decidere se la ricevuta deve essere stampata. Stampanti diverse possono inoltre utilizzare profili ricevuta diversi. Ad esempio, stampante 1 è una stampante per ricevute termica standard e pertanto ha formati più piccoli. Tuttavia, stampante 2 è una stampante per ricevute in dimensioni reali che consente di stampare solo ricevute di ordini cliente, che richiedono più spazio.

#### <a name="hardware-profiles"></a>Profili hardware

I profili hardware sono descritti come componenti dell'impostazione client in precedenza in questo articolo. I profili hardware vengono assegnati direttamente al registratore di cassa POS o a un profilo di stazione hardware. Vengono utilizzati per specificare i tipi di dispositivi utilizzati da un determinato registratore di cassa POS o una stazione hardware. I profili hardware vengono utilizzati anche per specificare le impostazioni EFT utilizzate per comunicare con l'SDK per il pagamento.

#### <a name="visual-profiles"></a>Profili visivi

I profili visivi vengono assegnati a livello di registratore di cassa. Vengono utilizzati per specificare il tema per un registratore di cassa specifico. I profili includono le impostazioni per il tipo di applicazione che viene utilizzato (MPOS o POS cloud), il colore e tema, la combinazione di tipi di carattere, lo sfondo di accesso e lo sfondo di POS.

### <a name="custom-fields"></a>Campi personalizzati

È possibile creare i campi personalizzati per aggiungere i campi che non fanno riferimento dalla casella al POS. Per ulteriori informazioni sull'utilizzo dei campi personalizzati, vedere [utilizza il registrare] di blog dei campi personalizzati (https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Testo lingua

Utilizzando le voci di testo di lingua, è possibile ignorare le stringhe predefinite nel POS. Per ignorare una stringa nel POS, aggiungere una nuova riga di testo di lingua. Quindi specificare un ID, la stringa predefinita che deve essere ignorata e il testo che deve essere visualizzato presso il POS anziché la stringa predefinita.

### <a name="hardware-station-profiles"></a>Profili stazione hardware

I profili stazione hardware sono descritti in precedenza in questo articolo. Vengono utilizzati per assegnare informazioni non specifiche di istanza a stazioni hardware.

### <a name="channel-reports-configuration"></a>Configurazione dei report del canale

Impostare i report disponibili per il canale di vendita al dettaglio nella pagina **Configurazione dei report del canale di vendita al dettaglio**. È possibile creare nuovi report fornendo la definizione XML del report e assegnando il report a un gruppo di autorizzazioni specifiche presso il POS.

### <a name="devices"></a>Dispositivi

I dispositivi sono descritti in precedenza in questo articolo. Vengono utilizzati per gestire l'attivazione di uno specifico registratore di cassa POS. I dispositivi vengono utilizzati anche per specificare l'applicazione utilizzata per un registratore di cassa specifico e il pacchetto di installazione che deve essere utilizzato per installare il client MPOS. Di seguito sono elencati gli stati di attivazione del dispositivo:

-   **In sospeso** : il dispositivo è pronto per essere attivato.
-   **Attivato** : il dispositivo è stato attivato.
-   **Disattivato**: il dispositivo è stato disattivato nel back office o tramite il POS.
-   **Disabilitato**: il dispositivo è stato disabilitato.

Ulteriori informazioni relative alla attivazione includono il lavoratore che ha modificato lo stato di attivazione per il dispositivo, un timestamp per l'attivazione, e se la configurazione del dispositivo è stata convalidata.

### <a name="client-data-synchronization"></a>Sincronizzazione dei dati client

Tutte le modifiche apportate a un client POS, ad eccezione delle modifiche dello stato di attivazione del dispositivo, devono essere sincronizzate nel database di canale per essere effettive. Alla sincronizzazione delle modifiche al database di canale, traversano ** al dettaglio e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione ** ed eseguire la programmazione richiesta di distribuzione. Per le modifiche del client, è necessario eseguire le programmazioni di distribuzione "Registratori di cassa" e "Configurazione canale".


