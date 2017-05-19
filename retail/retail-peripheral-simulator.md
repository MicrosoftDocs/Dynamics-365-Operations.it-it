---
title: Simulatore periferica di vendita al dettaglio
description: In questo argomento viene descritto lo strumento simulatore periferica fornito con Microsoft Dynamics 365 for Operations - Retail.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 266544
ms.assetid: 16f31e70-15fc-441e-9727-e6a31c3a48f5
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: 11a4633b0a1254f3a8cbdcba8d7aa99bb7c936c1
ms.contentlocale: it-it
ms.lasthandoff: 04/26/2017


---

# <a name="retail-peripheral-simulator"></a>Simulatore periferica di vendita al dettaglio

[!include[banner](includes/banner.md)]


In questo argomento viene descritto lo strumento simulatore periferica fornito con Microsoft Dynamics 365 for Operations - Retail.

<a name="overview"></a>Panoramica
--------

Il simulatore periferica di Microsoft Dynamics 365 for Operations - Retail è uno strumento che consente di impostare, testare e risolvere i problemi delle periferiche utilizzate negli ambienti di vendita al dettaglio. È possibile utilizzare il simulatore periferica per ottimizzare il test delle periferiche per la vendita al dettaglio e per isolare eventuali problemi dovuti dall'impostazione non corretta o di driver funzionanti male. Il simulatore periferica include un programma desktop con versioni virtuali delle funzionalità di dispositivi supportati da Dynamics 365 for Operations - Retail. Un'area per ogni dispositivo virtuale mostra l'interazione tra il dispositivo e il POS. È inoltre possibile utilizzarlo per fornire input valido per diversi scenari POS. Il simulatore periferica supporta l'interazione tra il POS e i seguenti dispositivi virtuali:

-   **Stampante**: il simulatore periferica consente di visualizzare le ricevute configurate per una stampante POS.
-   **Visualizzazione riga**: è possibile configurare una visualizzazione riga virtuale per visualizzare l'attività in una visualizzazione riga fisica.
-   **Lettore di banda magnetica (MSR)**: è possibile inviare eventi simulati di banda magnetica al POSI tramite il simulatore periferica.
-   **Cassetto**: è possibile simulare un cassetto fisico della cassa.
-   **Cassetto 2**: impostando un secondo cassetto della cassa nel simulatore periferica, è possibile simulare gli scenari che includono un singolo registratore di cassa POS con due turni attivi.
-   **Scanner** ** lo scanner virtuale di codici a barre supportato dal simulatore periferica può rilasciare eventi di scansione del codice a barre.
-   **Scala**: una scala virtuale consente di eseguire la simulazione dell'interazione di articoli con peso con il POS.
-   **Tastierino PIN**: consente die simulare le operazioni con tastierino PIN. **Nota**: è necessario implementare il supporto per un tastierino PIN fisico tramite connettore pagamenti.
-   **Acquisizione firma**: il simulatore periferica include un dispositivo virtuale di acquisizione firma che è possibile impostare per richiedere delle firme necessarie per alcuni metodi di pagamento, ad esempio per pagamenti su conto cliente.

È inoltre possibile utilizzare il simulatore periferica per simulare gli eventi di lettori collegati alla tastiera che hanno origine da uno scanner di codici a barre e dal dispositivo MSR. Il simulatore periferica virtuale supporta in modo specifico OLE per dispositivi Retail POS (OPOS).

## <a name="key-scenarios"></a>Scenari principali
### <a name="troubleshooting"></a>Risoluzione dei problemi

È possibile utilizzare il simulatore periferica per la risoluzione di problemi di impostazione di dispositivi. Se non si dispone dei simulatore periferica o di un secondo dispositivo della stessa classe, può essere difficile determinare quali problemi si verificano. Tuttavia, quando si dispone dei simulatore periferica, è possibile impostare i dispositivi virtuali ed eseguire gli stessi percorsi di codice e regole business di codici utilizzati per le unità fisiche. Dal punto di vista di simulatore periferica, la differenza principale tra unità virtuali e unità fisiche consiste nell'oggetto assistenza o driver del dispositivo. Per i dispositivi fisici, l'oggetto assistenza viene fornito dal produttore del dispositivo. Di contro, per il simulatore periferica, gli oggetti assistenza vengono forniti come parte del simulatore periferica. Quando il simulatore periferica funziona correttamente, se un dispositivo non funziona correttamente dopo che il nome del dispositivo nel profilo hardware viene modificato nel nome di un dispositivo reale, si può dedurre la presenza di un problema relativo all'oggetto assistenza fornito dal produttore.

### <a name="training"></a>Formazione

È possibile utilizzare il simulatore periferica per aggiungere un livello realistico alla formazione dal cassiere quando un'impostazione fisica hardware non è disponibile. Quando il simulatore periferica viene incluso negli scenari di formazione, il cassiere può interagire in modo più efficace con il POS immettendo input come ad esempio scansioni del codice a barre dei prodotti o strisciate di gift card e osservando quali ricevute vengono stampate per una transazione specifica.

### <a name="testing"></a>Test

È possibile utilizzare il simulatore periferica per verificare codici a barre del prodotto, formati di ricevute e così via, senza dover distribuire hardware fisico in un ambiente virtuale. Poiché l'hardware fisico non è obbligatorio e non è necessario distribuire un client di POS in una stazione hardware o in un computer fisico, è possibile verificare più rapidamente le modifiche apportate nel back office.

## <a name="set-up-the-peripheral-simulator"></a>Impostare il simulatore periferica
### <a name="set-up-a-hardware-profile"></a>Impostare un profilo hardware

1.  Per impostare un simulatore periferica, fare clic su **Vendita al dettaglio e commercio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Profili POS** &gt; **Profili hardware**.
2.  Fare clic su **Nuovo** per creare un nuovo profilo.
3.  Immettere i valori nei campo **Numero profilo** e **Descrizione**.
4.  Utilizzare la seguente tabella per impostare le unità virtuali che devono essere testate. Di seguito vengono descritte le colonne della tabella:
    -   **Dispositivo** – questa colonna include il nome della scheda dettaglio che si espande per impostare il dispositivo.
    -   **Tipo di dispositivo** – questa colonna include il valore selezionato nel campo contrassegnato con il nome del dispositivo.
    -   **Nome dispositivo** – questa colonna fornisce il valore esatto immesso per il nome del dispositivo. **Importante:** i nomi di dispositivi che vengono forniti in questo campo sono obbligatori, poiché la stazione hardware utilizza questi nomi specifici per comunicare con i dispositivi. Se non si utilizzano i nomi specifici, il dispositivo non sarà utilizzabile.

    | Dispositivo            | Tipo di dispositivo | Nome periferica              |
    |-------------------|-------------|--------------------------|
    | Stampante           | OPOS        | MockOPOSPrinter          |
    | Visualizzazione riga      | OPOS        | MockOPOSLineDisplay      |
    | MSR               | OPOS        | MockOPOSMSR              |
    | Traente            | OPOS        | MockOPOSDrawer1          |
    | Drawer2           | OPOS        | MockOPOSDrawers          |
    | Scanner           | OPOS        | MockOPOSScanner          |
    | Scala             | OPOS        | MockOPOSScale            |
    | Tastierino PIN           | OPOS        | MockOPOSPinPad           |
    | Acquisizione firma | OPOS        | MockOPOSSignatureCapture |

**Nota:** non è necessaria nessuna impostazione specifica nel profilo hardware per simulare gli eventi di lettori collegati alla tastiera da scanner di codici a barre ed MSR.

### <a name="assign-the-hardware-profile-to-a-register"></a>Assegnare il profilo hardware a un registratore di cassa

1.  Dopo avere creato il profilo hardware, andare a **Vendita al dettaglio e commercio** &gt; **Impostazione canale** &gt; **Impostazione POS** &gt; **Registratori di cassa**.
2.  Nell'elenco **Registratori di cassa POS** fare clic sul collegamento nel campo **Numero registratore di cassa** del registratore di cassa che deve utilizzare il simulatore periferica.
3.  Fare clic su **Modifica**.
4.  Nella sezione **Profili** nel campo **Profilo hardware** selezionare il profilo hardware creato per le periferiche virtuali.
5.  Fare clic su **Salva**.

### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizzare le modifiche apportate al database del canale

1.  Passare a **Vendita al dettaglio e commercio** &gt; **IT vendita al dettaglio** &gt; **Programmazione della distribuzione**.
2.  Selezionare la programmazione distribuzione **1090**.
3.  Fare clic su **Esegui adesso** per sincronizzare le modifiche al POS.

Dopo che i dati vengono sincronizzati, il nuovo profilo hardware e le modifiche nel registratore di cassa sono disponibili nel database del canale.

## <a name="install-the-peripheral-simulator"></a>Installare il simulatore periferica
1.  Andare a **Vendita al dettaglio e commercio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Profili POS** &gt; **Profili hardware**.
2.  Fare clic su **Scarica** quindi fare clic su **PeripheralSimulator**. **Nota:** è necessario disattivare i blocchi pop-up per poter scaricare il simulatore periferica.
3.  Al termine del download, aprire la cartella **Download** e fare doppio clic su **VirtualPeripherals.msi** per iniziare l'installazione.
4.  Impostare il simulatore periferica utilizzando le impostazioni predefinite.

Oltre al simulatore periferica, è necessario impostare gli oggetti controlli comuni di Monroe Consulting Services. In caso contrario, il simulatore periferica non verrà eseguito correttamente. Per scaricare gli oggetti controlli comuni, andare a <http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Utilizzare il simulatore periferica
Per avviare il simulatore periferica, fare clic su **Start** nel computer, digitare **Simulatore periferica di vendita al dettaglio** quindi selezionare l'app quando viene visualizzata nell'elenco dei risultati di ricerca. Una volta avviato il simulatore periferica, fare clic sul nome di un dispositivo per visualizzare i dispositivi supportati. Questi dispositivi verranno elencati nella scheda nella parte sinistra della finestra. Per visualizzare un dispositivo specifico, fare clic sulla scheda per tale dispositivo.

### <a name="line-display-capabilities"></a>Funzionalità di visualizzazione riga

Il dispositivo di visualizzazione riga è il primo dispositivo elencato nel simulatore periferica. Quando la visualizzazione riga virtuale è configurata, vengono visualizzate le voci in base alla scansione nella transazione POS. Oltre alle voci, viene visualizzato il totale dovuto quando un metodo di pagamento viene selezionato nel POS. Viene inoltre mostrato il saldo dovuto se il metodo di pagamento è stata immesso ma un saldo è ancora dovuto per la transazione. Quando il POS non viene utilizzato, può essere visualizzato un messaggio per indicare che il cassetto è chiuso. È necessario configurare il messaggio nella scheda dettaglio **Visualizzazione riga** nel profilo hardware.

### <a name="cash-drawer-capabilities"></a>Funzionalità del cassetto della cassa

Il cassetto della cassa è il secondo dispositivo elencato nel simulatore periferica. Quando il profilo hardware è configurato per l'utilizzo dei cassetti di cassa virtuali, il POS apre il cassetto della cassa per il turno attivo in risposta a operazioni del cassetto quali ad esempio riepiloghi incassi, in modo da consentire al cassiere la modifica o il deposito di contanti durante le transazioni cash-and-carry standard. I cassetti virtuali di cassa hanno le etichette **Cassetto principale** e **Cassetto secondario**. Queste etichette nel profilo hardware rappresentano rispettivamente Cassetto e Cassetto 2. Quando un cassetto è chiuso, viene mostrata un'immagine di un cassetto della cassa chiuso e il pulsante del cassetto della cassa chiuso è contrassegnato **Apri cassetto**. Se si fa clic su questo pulsante, l'immagine verrà sostituita con un'immagine di un cassetto della cassa aperto per indicare che il cassetto è aperto. Il pulsante del cassetto della cassa aperto è contrassegnato **Cassetto chiuso**. Più operazioni POS possono determinare l'apertura del cassetto della cassa. La maggior parte delle operazioni non può continuare mentre il cassetto della cassa è aperto. Fanno eccezione alcune procedure di riepilogo giornaliero. Se l'utente POS riceve un messaggio di errore in cui viene indicato che un'operazione non può essere eseguita quando il cassetto della cassa è aperto, l'utente deve chiudere il cassetto virtuale o fisico della cassa per continuare. Se un cassetto della cassa viene contrassegnato come **Condiviso** nel profilo hardware, il sistema non verifica che nel cassetto sia chiuso prima di un'operazione. L'operazione continua normalmente, anche se il cassetto della cassa è aperto. Questo comportamento supporta scenari in cui i cassetti di cassa sono condivisi tra più addetti alle vendite e in cui un addetto alle vendite utilizza un cassetto della cassa mentre un altro esegue attività indipendenti nel proprio dispositivo POS. Le modifiche apportate al cassetto della cassa non sono evidenti fino alla chiusura del turno corrente e all'apertura di un nuovo turno.

### <a name="msr-capabilities"></a>Funzionalità MSR

Il simulatore periferica offre supporto efficace per le operazioni MSR virtuali funzionando in modalità OPOS oppure in modalità tramite lettori collegati alla tastiera. La modalità OPOS richiede che il dispositivo MSR sia configurato nel profilo hardware per il funzionamento come dispositivo OPOS. modalità tramite lettori collegati alla tastiera invia eventi dati tramite lettori collegati alla tastiera a Microsoft Windows. Oltre alle differenze nell'impostazione, le modalità OPOS e modalità lettori collegati alla tastiera differiscono nei seguenti modi:

-   Il client di Retail POS supporta dispositivi MSR OPOS per scenari specifici, ad esempio scenari che consentono la raccolta di dati della banda magnetica per programmi fedeltà o gift card.
-   In modalità di lettori collegati alla tastiera, il simulatore periferica invia dati al lettore collegato alla tastiera nel campo che è attivo quando i dati vengono inviati. Questo comportamento è simile al comportamento che si verifica quando i dati vengono immessi tramite una tastiera. Per utilizzare il dispositivo MSR come lettore collegato alla tastiera, l'utente deve passare a Retail Modern POS (MPOS) per assicurarsi che i dati siano ricevuti nel campo corretto. Di conseguenza, è possibile configurare un ritardo, in modo che l'utente abbia tempo di assicurarsi che i dati vengano inviati al campo corretto.

#### <a name="testing-gift-and-payment-card-swipes"></a>Test della scansione di gift card e carte di pagamento

Il dispositivo MSR virtuale utilizzata dal simulatore periferica consente inoltre di configurare i dati specifici del dispositivo MSR per il test di scenari di scansione di gift card e carte di pagamento. Per creare una carta, fare clic sul pulsante del segno più (**+**) e selezionare il tipo di carta. Specificare quindi il numero di carta o dati di registrazione che devono essere inviati al POS, nonché il mese e l'anno di scadenza per la carta da definire. Il valore selezionato nel campo **Tipo di carta** è solo un'etichetta che può essere mappata a una carta. Questa etichetta facilita l'identificazione delle carte quando viene effettuata la scansione tramite il simulatore periferica. È possibile selezionare le carte configurate nel simulatore periferica utilizzando i pulsanti freccia sinistra (**&lt;**) e freccia destra (**&gt;**) sopra all'immagine della carta. È possibile modificare ed eliminare le carte utilizzando i pulsanti **Modifica** ed **Elimina** accanto al pulsante con segno più (**+**).

### <a name="pin-pad"></a>Tastierino PIN

È possibile configurare il simulatore di tastierino PIN per simulare un tastierino PIN OPOS. Quando una transazione di bonifico (EFT) viene eseguita nel POS e richiede la voce PIN, la stazione hardware chiama il dispositivo PIN per richiedere per l'immissione del PIN. Per funzionare, il tastierino PIN nel simulatore periferica richiede il supporto connettore di pagamento EFT.

### <a name="printer"></a>Stampante

La stampante periferica virtuale visualizza solo le ricevute come vengono stampate dal POS. Se un'operazione di stampa produce più ricevute, è possibile scorrere tra le ricevute.

#### <a name="configure-receipt-printing"></a>Configurare la stampa di ricevute

1.  Andare a **Vendita al dettaglio e commercio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Profili POS** &gt; **Profili hardware**.
2.  Selezionare il profilo hardware creato per le periferiche virtuali.
3.  Nella scheda dettaglio **Stampante** fare clic su **Modifica**.
4.  Nel campo **ID profilo ricevuta** selezionare un profilo ricevuta.
5.  Fare clic su **Salva**.

### <a name="scale"></a>Scala

Quando un prodotto correlato alla bilancia viene aggiunto alla transazione POS e viene configurata una bilancia, il POS recupera il peso dalla bilancia. Sia per la bilancia virtuale che fisica, il prodotto o peso deve essere specificato prima di aggiungere il prodotto alla transazione. Prima di aggiungere il prodotto per bilancia alla transazione, passare alla bilancia nel simulatore periferica e utilizzare i pulsanti con segno più (**+**) e meno (**–**) per regolare il peso che la bilancia deve dichiarare. È inoltre possibile immettere il peso desiderato direttamente nel campo **Valore corrente**. È possibile regolare le unità di peso per la bilancia utilizzando ii pulsanti con segno più (**+**), **Modifica** ed **Elimina**. In questo modo, le unità possono essere specificate in base ai prodotti che vengono pesati o alla bilancia utilizzata.

#### <a name="configure-a-scale-product"></a>Configurare un prodotto scala

1.  Passare a **Vendita al dettaglio e** **commercio** &gt; **Prodotti e categorie** &gt; **Prodotti rilasciati per categoria**.
2.  Aprire il record del prodotto.
3.  Selezionare il prodotto da pesare.
4.  Nella scheda dettaglio **Vendita al dettaglio** impostare l'opzione **Prodotto scala** da **No** a **Sì**.

#### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizzare le modifiche apportate al database del canale

1.  Passare a **Vendita al dettaglio e commercio** &gt; **IT vendita al dettaglio** &gt; **Programmazione della distribuzione**.
2.  Selezionare la programmazione distribuzione **1040**.
3.  Fare clic su **Esegui adesso** per sincronizzare le modifiche al POS.

Dopo la sincronizzazione dei dati, quando un prodotto scala viene aggiunto alla transazione POS, il POS verifica la bilancia per il peso.

### <a name="signature-capture"></a>Acquisizione firma

Il dispositivo virtuale di acquisizione della firma richiede all'utente di immettere una firma sul tastierino virtuale di acquisizione della firma quando il metodo di pagamento utilizzato richiede una firma. L'utente può accettare la firma per mostrarla al POS. Il cassiere può quindi accettare la firma. La firma verrà salvata insieme al metodo di pagamento e sincronizzata nel back office con altri dati della transazione.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Impostare un metodo di pagamento per richiedere una firma

1.  Passare a **Vendita al dettaglio e commercio** &gt; **Canali** &gt; **Punti vendita al dettaglio** &gt; **Tutti i punti vendita al dettaglio**.
2.  Selezionare il punto vendita al dettaglio
3.  Fare clic su **Modifica**.
4.  Fare clic su **Impostazione**, quindi nella sezione **Impostazione** fare clic su **Metodi di pagamento**.
5.  Fare clic su **Modifica**.
6.  Selezionare il metodo di pagamento che richiede una firma.
7.  Nella sezione **Generale** in **Acquisizione firma**, impostare l'opzione **Utilizza dispositivo per acquisizione firma** su **Sì**.
8.  Nel campo **Importo minimo per acquisizione firma** immettere l'importo minimo che attiva l'acquisizione firma.

#### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizzare le modifiche apportate al database del canale

1.  Passare a **Vendita al dettaglio e commercio** &gt; **IT vendita al dettaglio** &gt; **Programmazione della distribuzione**.
2.  Selezionare la programmazione distribuzione **1070**.
3.  Fare clic su **Esegui adesso** per sincronizzare le modifiche al POS.

Dopo che i dati vengono sincronizzati, quando viene utilizzato un metodo di pagamento che richiede una firma e l'importo corrisponde al valore soglia di firma, il POS richiede una firma sul dispositivo virtuale di acquisizione firma.

## <a name="additional-configuration"></a>Configurazione aggiuntiva
È possibile modificare il file di configurazione del simulatore periferica per gestire in modo più efficiente gli scenari di cui viene eseguito il test. Cercare il file di configurazione in C:\\Programmi (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Il file di configurazione definisce le unità disponibili per i test relativi a bilancia, tipi di carta disponibili per il test e tipi di codice a barre. Ad esempio, modificando i valori di test nel file di configurazione, è possibile aggiungere un nuovo tipo di carta o unità di misura che possono essere selezionati in fase di esecuzione. I nuovi valori verranno visualizzati dopo il riavvio dell'app.

## <a name="troubleshooting"></a>Risoluzione dei problemi
Le attività per il simulatore periferica vengono registrate nel simulatore periferica. Cercare il file di log in C:\\Programmi (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Il simulatore periferiche fornisce anche un report dei problemi tramite il registro eventi di Windows, a cui è possibile accedere tramite i **log dei servizi e dell'applicazione** &gt; **Microsoft** &gt; **DynamicsAX**. Se le modifiche apportate al profilo hardware o ad altre aree non sono evidenti quando si utilizza MPOS o il simulatore periferica, verificare i processi di distribuzione di Retail Scheduler utilizzati per sincronizzare i dati nel database del canale. Se le modifiche sono state sincronizzate ma non sono ancora evidenti nel POS, riavviare il client di Retail POS. Le modifiche apportate ai cassetti della cassa configurati non sono effettive fino alla creazione di un nuovo turno. Pertanto, si apportano modifiche ai cassetti della cassa, assicurarsi di chiudere sempre il turno esistente per verificare la nuova impostazione del cassetto della cassa. Talvolta, se il driver di un produttore viene installato dopo gli oggetti controlli comuni di Monroe Consulting Services, il driver può avere un impatto sul corretto funzionamento degli oggetti controlli comuni. In questo caso, è necessario reinstallare gli oggetti controlli comuni.

<a name="see-also"></a>Vedere anche
--------

[Panoramica sulle periferiche di vendita al dettaglio](retail-peripherals-overview.md)




