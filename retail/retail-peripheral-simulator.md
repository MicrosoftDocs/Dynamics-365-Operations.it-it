---
title: Retail peripheral simulator
description: In questo argomento viene descritto lo strumento periferica di simulatore fornito con Microsoft Dynamics 365 per le operazioni al dettaglio.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 266544
ms.assetid: 16f31e70-15fc-441e-9727-e6a31c3a48f5
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 42dc414ff2bb6359b47d89c3bd3c510e4258f816
ms.openlocfilehash: b2229466040351d8c2b9494b30b4c928651820b8
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripheral-simulator"></a>Retail peripheral simulator

In questo argomento viene descritto lo strumento periferica di simulatore fornito con Microsoft Dynamics 365 per le operazioni al dettaglio.

<a name="overview"></a>Panoramica
--------

Microsoft Dynamics 365 per le operazioni del simulatore remoto al dettaglio è uno strumento che consente alle collaudano, e risoluzione di eliminazione sulle periferiche utilizzate negli ambienti di vendita al dettaglio. È possibile utilizzare il simulatore remoto per aggiornare la verifica delle periferiche al dettaglio e per isolare eventuali problemi che sono dovute dall'impostazione non corretti o dai conducenti funzionanti male. Il simulatore remoto include un programma il desktop versioni virtuali delle funzionalità di unità che Dynamics 365 per le operazioni consente il supporto di vendita al dettaglio. Area per ogni unità vengono visualizzati virtuale l'interazione tra l'unità e il POS (POS). È inoltre possibile utilizzarlo per immettere l'input valido per scenari di Retail POS. Il simulatore dell'unità periferica supporta l'interazione tra il POS e le seguenti unità virtuali:

-   ** Stampante ** il simulatore remoto possibile visualizzare le entrate configurate per una stampante di Retail POS.
-   ** Visualizzazione di riga ** possibile configurare una visualizzazione riga virtuale per visualizzare l'attività in una visualizzazione riga effettiva.
-   ** Lettore di banda magnetica (MSR) ** possibile inviare gli eventi simulati di banda magnetica installato presso il simulatore remoto.
-   ** Cassetto ** possibile simulare un fisico cassetto della cassa.
-   ** Cassetto 2 - ** impostare un secondo cassetto della cassa nel simulatore remoto, è possibile simulare gli scenari che includono un singolo registratore di cassa POS con due turni attivi.
-   ** Scanner ** il scanner di codici a barre virtuale che supporti periferici di simulatore possono rilasciare gli eventi della scansione del codice a barre.
-   ** La scala ** - una scala virtuale consente di eseguire la simulazione dell'interazione di articoli con pesi elevati il POS.
-   ** Tastierino di (PIN) del numero di identificazione personale ** possibile simulare le operazioni di tastierino PIN. ** Nota: ** È necessario implementare il contributo di un tastierino PIN fisico da connettori del pagamento.
-   ** Il blocco di firma ** il simulatore remoto include un'unità virtuale di blocco di firma impostati per richiedere delle firme necessarie per alcune offerte, ad esempio le tariffe del conto cliente.

È inoltre possibile utilizzare il simulatore remoto per simulare gli eventi del cuneo tastiera di un scanner di codici a barre e dal dispositivo MSR. Il simulatore dell'unità periferica virtuale in modo da supportare il collegamento di oggetti e la incastonatura per le unità Retail POS OPOS ().

## <a name="key-scenarios"></a>Scenari chiave
### <a name="troubleshooting"></a>Risoluzione dei problemi

È possibile utilizzare il simulatore periferica per la risoluzione dell'impostazione di unità. Se non si dispone dei simulatore remoto o una seconda unità della stessa classe, può essere difficile determinare quale le uscite nascono. Tuttavia, quando il simulatore remoto, è possibile impostare unità virtuali ed eseguire gli stessi percorsi e regole business di codici utilizzati per le unità fisiche. Dal punto di vista di simulatore remoto, la differenza principale tra unità virtuali e unità fisiche dell'oggetto assistenza, o conducenti. Per unità fisiche, l'oggetto assistenza viene fornito dal produttore dell'unità. Di contro, per il simulatore remoto, gli oggetti assistenza sono disponibili come parte del simulatore remoto. Quando il simulatore remoto funzioni correttamente, se tale unità non viene eseguito correttamente dopo il nome di unità nel profilo hardware è impostato sul nome di un'unità effettivo è sì, la presenza di un problema con l'oggetto assistenza per il produttore fornito.

### <a name="training"></a>Formazione

È possibile utilizzare il simulatore remoto per aggiungere un livello realistico alla formazione dal cassiere quando un'impostazione fisica hardware non è disponibile. Quando il simulatore remoto viene incluso negli scenari di formazione, il cassiere può più efficace interagire con il POS immettendo l'input ad esempio per la scansione del codice a barre dei prodotti e i battute gift card e visualizzando le entrate vengono stampate per una transazione specifica.

### <a name="testing"></a>Test

È possibile utilizzare il simulatore remoto per verificare i codici a barre del prodotto, formati di entrata, e così via, senza dover distribuire i componenti hardware fisico in un ambiente virtuale. Poiché i componenti hardware fisico non è obbligatorio e non è necessario distribuire un client di POS nella propria postazione hardware o in un computer fisico, è possibile verificare più rapidamente le modifiche apportate in back office.

## <a name="set-up-the-peripheral-simulator"></a>Impostare il simulatore remoto
### <a name="set-up-a-hardware-profile"></a>Impostare un profilo hardware

1.  Per impostare il simulatore remoto, passare ** al dettaglio e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** profili Retail POS ** &gt; ** profili hardware **.
2.  Per creare un nuovo profilo, fare clic su ** nuovo **.
3.  Immettere i valori ** numero di profilo ** e ** descrizione ** campi.
4.  Utilizzare la seguente tabella per impostare le unità virtuali che devono essere collaudate. Ecco una descrizione delle colonne nella tabella:
    -   ** Unità ** questa colonna per nome della scheda dettaglio che si espande per impostare le unità.
    -   ** Il tipo di unità ** questa colonna dal valore selezionato nel campo in è contrassegnata con il nome dell'unità.
    -   ** Il nome di unità ** questa colonna esatto dal valore specificato per il nome di unità. ** Importante: ** I nomi di unità che vengono calcolati in questo campo sono necessari, poiché la propria postazione hardware Questi nomi specifici per eliminare le unità. Se non si utilizzano i nomi specifici, l'unità non verrà utilizzabile.

    | Dispositivo            | Tipo di dispositivo | Nome periferica              |
    |-------------------|-------------|--------------------------|
    | Stampante           | )        | MockOPOSPrinter          |
    | Visualizzazione riga      | )        | MockOPOSLineDisplay      |
    | MSR               | )        | MockOPOSMSR              |
    | Traente            | )        | MockOPOSDrawer1          |
    | Drawer2           | )        | MockOPOSDrawers          |
    | Scanner           | )        | MockOPOSScanner          |
    | Scala             | )        | MockOPOSScale            |
    | Tastierino PIN           | )        | MockOPOSPinPad           |
    | Acquisizione firma | )        | MockOPOSSignatureCapture |

** Nota: ** Se l'impostazione specifica nel profilo hardware è necessaria per simulare gli eventi del cuneo tastiera tramite scanner di codici a barre e dal dispositivo MSR.

### <a name="assign-the-hardware-profile-to-a-register"></a>Assegnare il profilo hardware a un registro

1.  Dopo che il profilo hardware, viene diventano ** al dettaglio e il commercio ** &gt; ** il Manica impostato ** &gt; ** POS configurato ** &gt; ** registrare **.
2.  In ** registri di Retail POS ** elenchi, fare clic sul collegamento in ** numero di registro ** il campo del registro di budget che deve utilizzare il simulatore remoto.
3.  Fare clic su **Modifica**.
4.  In ** profili ** aree, in ** profilo hardware ** il campo, selezionare il profilo hardware create per le periferiche virtuali.
5.  Click **Save**.

### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizzare le modifiche apportate al database del canale

1.  ** Va al dettaglio e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione **.
2.  Selezionare ** 1090 ** la programmazione di distribuzione.
3.  Fare clic su ** esecuzione ora ** per sincronizzare le modifiche al POS.

Dopo che i dati vengono sincronizzati, il nuovo profilo hardware e variazioni nel registro sono disponibili nel database del canale.

## <a name="install-the-peripheral-simulator"></a>Impostare il simulatore remoto
1.  ** Va al dettaglio e il commercio ** &gt; ** il Manica impostato ** &gt; ** POS configurato ** &gt; ** profili Retail POS ** &gt; ** profili hardware **.
2.  Fare clic su Download Center ** ** quindi fare clic su PeripheralSimulator ** **. ** Nota: ** È necessario disattivare gli stampare popup poter scaricare il simulatore remoto.
3.  Dopo che il download, aprire ** download ** la cartella e fare doppio clic VirtualPeripherals.msi ** ** per iniziare la installatore.
4.  Impostare il simulatore remoto utilizzando le impostazioni predefinite.

Oltre al simulatore remoto, è necessario impostare gli oggetti di tipo centrale da servizi di consulenza di Monroe. In caso contrario, il simulatore remoto non verrà eseguito correttamente. Per scaricare gli oggetti di tipo centrale, passare all'> indirizzo http://monroecs.com/oposccos_current.htm.

## <a name="using-the-peripheral-simulator"></a>Utilizzo del simulatore remoto
Per attivare il simulatore remoto, fare clic su ** inizio ** nel computer, il tipo simulatore ** remoto al dettaglio ** quindi selezionare il app quando viene visualizzato nella ricerca i risultati. Una volta avviate il simulatore remoto, fare clic sul nome di unità per visualizzare le unità di supporto. Queste unità verranno elencate le schede nella parte sinistra della finestra. Per visualizzare un'unità specifica, fare clic sulla scheda per tale unità.

### <a name="line-display-capabilities"></a>Capacità di visualizzazione riga

La visualizzazione riga è la prima unità elencata nel simulatore remoto. Quando la visualizzazione riga virtuale è configurata, vengono visualizzate le voci mentre quelle personalizzate vengono esaminate la transazione da Retail POS. Oltre alle voci della visualizzazione, viene visualizzato il totale dovuto a un'offerta è selezionata nel POS. Viene inoltre illustrato il saldo dovuto se l'offerta è stata immessa ma un saldo è ancora dovuto per la transazione. Quando il POS non viene utilizzata, un messaggio può essere visualizzato per indicare che il massimo è chiuso. È necessario configurare il messaggio ** visualizzazione riga ** clic nel profilo hardware.

### <a name="cash-drawer-capabilities"></a>Capacità del cassetto della cassa

Il cassetto della cassa è la seconda unità elencata nel simulatore remoto. Quando il profilo hardware è configurato per utilizzare i cassetti virtuali di cassa, il POS aprire il cassetto della cassa per slittamento attivo in risposta a operazioni del cassetto ad esempio le dichiarazioni relative e gestire in modo da consentire la modifica o depositare il cassiere contanti durante le transazioni standard di e cash carry. I cassetti virtuali di cassa con le etichette ** cassetto ** principale e ** cassetto ** secondario. Le etichette per il cassetto e il cassetto 2 nel profilo hardware, rispettivamente. Quando un cassetto è bloccato, un'immagine del cassetto della cassa chiuso il caso e il pulsante del cassetto della cassa chiuso è contrassegnata ** cassetto ** aperto. Se si fa clic su questo pulsante, l'immagine verrà sostituita con un'immagine di aprire il cassetto della cassa per indicare che il cassetto verrà aperto. Il pulsante del cassetto della cassa aperto è contrassegnata ** cassetto ** vicino. È possibile associare più operazioni Retail POS possono determinare il cassetto della cassa a l. La maggior parte delle operazioni non possono continuare al cassetto della cassa è aperto. Le eccezioni presenti alcune riepiloghi giornalieri. Se l'utente di Retail POS verrà inviato un messaggio di errore in cui viene indicato che un'operazione non può essere eseguita quando il cassetto della cassa è aperto, l'utente deve chiudere il cassetto virtuale o fisico di cassa per continuare. Se il cassetto della cassa viene contrassegnato come ** condivisa ** nel profilo hardware, il sistema non verifica che nel cassetto venga chiuso prima di un'operazione. L'operazione continua normalmente, anche se il cassetto della cassa è aperto. Questo comportamento supporta scenari in cui i cassetti di cassa sono condivisi tra i partner di vendita a un punto vendita viene utilizzato un cassetto della cassa durante un altro punto eseguite le attività indipendenti in un'apposita unità di Retail POS. Le modifiche apportate al cassetto della cassa non vengono evidenti fino alla chiusura del turno corrente e un nuovo turno sia aperta.

### <a name="msr-capabilities"></a>Capacità del dispositivo

Il simulatore remoto offre supporto robusto per le operazioni virtuali del dispositivo lavora in modalità OPOS oppure in modalità di cuneo tastiera. La modalità di cassa viene richiesto al dispositivo MSR sia configurato nel profilo hardware di lavorare come unità OPOS. La modalità di cuneo tastiera invia appena gli eventi dati del cuneo tastiera a Microsoft Windows. Oltre alle differenze nell'impostazione, le modalità di cuneo tastiera OPOS e differiscono nei seguenti modi:

-   Client di Retail POS consente ad descrizione del dispositivo OPOS per gli scenari specifici, ad esempio gli scenari che consentono i dati di banda magnetica fedeltà o per l'immissione con gift card.
-   In modalità di cuneo tastiera, il simulatore remoto invia dati del cuneo tastiera nel campo che è attivo quando i dati vengono inviati. Questo comportamento è simile al comportamento che si verifica quando i dati vengono immessi tramite una tastiera. Per utilizzare il dispositivo MSR come cuneo tastiera, quest'ultimo deve essere installato presso moderno al dettaglio) (MPOS per assicurarsi che siano stati ricevuti nel campo corretto. Di conseguenza, è possibile configurare eseguita, in modo che l'utente ha tempo in modo che i dati vengono inviati al campo corretto.

#### <a name="testing-gift-and-payment-card-swipes"></a>Battute della scheda della gift e pagamento di test

Il MSR virtuale utilizzata dal simulatore remoto garantisce consente inoltre di configurare i dati specifici del dispositivo per verificare gli scenari alla gift il pagamento per i cardare battute. Per creare una scheda, fare clic sul pulsante del segno più (**+**) e selezionare il tipo di carta. Specificare quindi il numero di carta o dati di traccia che devono essere inviati al POS, nonché il mese di inizio e all'anno della scheda da definire. Il valore selezionato ** tipo di carta ** nel campo sarà sufficiente un'etichetta che può essere mappate a un foglio. Questa etichetta facilita l'identificazione le schede quando vengono si passa dal simulatore remoto. È possibile selezionare le schede in cui sono stati configurati nel simulatore remoto utilizzando i pulsanti freccia sinistra (&lt;) **** e la freccia destra (&gt;****) all'immagine della carta. È possibile modificare ed eliminare le schede utilizzando ** ** modifica e l'eliminazione ** ** i pulsanti accanto al segno più (**+**) viene subito.

### <a name="pin-pad"></a>Tastierino PIN

È possibile configurare il simulatore di tastierino PIN per simulare un tastierino PIN OPOS. Quando una transazione di (EFT) di bonifico viene eseguita al POS e richiede la voce PIN, la propria postazione hardware chiama l'unità PIN per richiedere per l'immissione PIN. Per lavorare, il tastierino PIN nel simulatore remoto richiede il supporto di Connector di pagamento EFT.

### <a name="printer"></a>Stampante

Stampante dell'unità periferica virtuale viene visualizzato solo le ricevute come vengono stampate da Retail POS. Se un'operazione di stampa vengono prodotti più entrate, è possibile spostarsi tra le entrate.

#### <a name="configure-receipt-printing"></a>Configurare la stampa di entrata

1.  ** Va al dettaglio e il commercio ** &gt; ** il Manica impostato ** &gt; ** POS configurato ** &gt; ** profili Retail POS ** &gt; ** profili hardware **.
2.  Selezionare il profilo hardware create per le periferiche virtuali.
3.  ** Stampante ** clic su, ** ** modifica.
4.  In ** ID profilo ricevuta ** sistemi, selezionare un profilo ricevuta.
5.  Click **Save**.

### <a name="scale"></a>Scala

Quando un prodotto di scala viene aggiunto alla transazione di Retail POS e una bilancia è configurata, il POS recupera il peso dalla bilancia. Sia la scala virtuale in cui fisica, il prodotto o peso deve essere specificato prima che il prodotto da aggiungere alla transazione. Prima di aggiungere il prodotto una bilancia alla transazione, passare alla scala nel simulatore periferica e utilizzare il segno più (**+**) e i pulsanti del segno meno (- ** **) per rettificare il peso che la scala deve riferire. È inoltre possibile immettere il peso desiderato direttamente ** ** valore corrente del campo. È possibile registrare le unità di peso per ottenere la scala utilizzando il segno di addizione (** **+), ** ** modifica e l'eliminazione ** ** i pulsanti. In questo modo, le unità possono essere specificate basate su prodotti che sono pesi elevati o le impostazioni locali in cui la scala utilizzata.

#### <a name="configure-a-scale-product"></a>Configurare un prodotto di scala

1.  ** Va al dettaglio e ** ** il commercio ** &gt; ** prodotti e categorie ** &gt; ** prodotti rilasciati per la categoria **.
2.  Apre il record del prodotto.
3.  Selezionare il prodotto per pesare.
4.  ** Il dettaglio ** clic, impostare ** prodotto di pesatura ** l'opzione di ** non ** su Sì ** **.

#### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizzare le modifiche apportate al database del canale

1.  ** Va al dettaglio e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione **.
2.  Selezionare ** 1040 ** la programmazione di distribuzione.
3.  Fare clic su ** esecuzione ora ** per sincronizzare le modifiche al POS.

Dopo che i dati vengono sincronizzati, quando un prodotto di pesatura viene aggiunto alla transazione di Retail POS, il POS controlla la scala per il peso.

### <a name="signature-capture"></a>Acquisizione firma

Unità virtuale di blocco di firma richiesta all'utente di immettere una firma sul tastierino virtuale di blocco di firma quando l'offerta utilizzata è richiesta una firma. L'utente può accettare la firma per mostrarla al POS. Il cassiere può quindi accettare la firma. La firma verrà salvato insieme all'offerta e viene sincronizzata a back office con altri dati della transazione.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Impostare un'offerta per richiedere una firma

1.  Vanno ** al dettaglio e il commercio ** &gt; ** i canali ** &gt; ** vendita al dettaglio ** &gt; ** tutte le vendite al dettaglio **.
2.  Selezionare la vendita al dettaglio.
3.  Fare clic su **Modifica**.
4.  Fare clic su ** impostazione **, quindi ** impostazione ** nell'area, fare clic su ** metodi di pagamento **.
5.  Fare clic su **Modifica**.
6.  Selezionare il metodo di pagamento per il quale è richiesta una firma.
7.  In ** dettagli relativi all'identificazione ** aree, ** in blocco di firma **, impostare ** utilizzare l'unità di blocco di firma ** l'opzione ** Sì **.
8.  ** Importo minimo di blocco di firma ** nel campo, immettere l'importo minimo che genera il blocco di firma.

#### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizzare le modifiche apportate al database del canale

1.  ** Va al dettaglio e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione **.
2.  Selezionare ** 1070 ** la programmazione di distribuzione.
3.  Fare clic su ** esecuzione ora ** per sincronizzare le modifiche al POS.

Dopo che i dati vengono sincronizzati, quando un'offerta viene utilizzata per il quale è richiesta una firma e l'importo corrisponde al valore soglia di firma, richieste di Retail POS per una firma sull'unità virtuale di blocco di firma.

## <a name="additional-configuration"></a>Configurazione aggiuntivo
Per modificare più correttamente il file di configurazione del simulatore remoto all'indirizzo gli scenari di cui viene eseguito il test. Per trovare il file di configurazione C: Programmi\\(x86)\\Microsoft Dynamics 365\\70 VirtualPeripherals\\\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Il file di configurazione definisce le unità disponibili per i tentativi sulla bilancia, tipi di carta disponibili per verificare e i tipi di codice a barre. Ad esempio, modificando i valori di testo nel file di configurazione, è possibile aggiungere un nuovo tipo di carta o unità che possono essere selezionati in fase di esecuzione. I nuovi valori verranno visualizzate dopo il app la rimessa in caso.

## <a name="troubleshooting"></a>Risoluzione dei problemi
Le attività per il simulatore remoto vengono registrate nel simulatore remoto. Per trovare il registro C: Programmi\\(x86)\\Microsoft Dynamics 365\\70 VirtualPeripherals\\\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. I report periferici di simulatore anche uscite nel registro eventi di Windows, in cui è possibile accedere ** l'applicazione e i servizi registra ** &gt; ** a Microsoft DynamicsAX ** &gt; ** **. Se le modifiche apportate al profilo hardware o ad altre aree non sono evidenti si utilizza MPOS o il simulatore remoto, verificare i processi Retail Scheduler di distribuzione utilizzato per sincronizzare i dati nel database del canale. Se le modifiche sono state sincronizzate ma non ancora evidenti al POS, riavviare il client di Retail POS. Le modifiche apportate ai cassetti configurati di cassa non sono valide fino a creare un nuovo turno. Pertanto, si apportano modifiche ai cassetti di cassa, assicurarsi di chiudere sempre il turno esistente per verificare la nuova impostazione del cassetto della cassa. Talvolta, se il driver di un produttore è installato dopo gli oggetti di tipo centrale da servizi di consulenza di Monroe, il conducente può determinare la modifica degli oggetti di tipo centrale a smettere di lavorare correttamente. In questo caso, è necessario reinstallare gli oggetti di tipo centrale.

<a name="see-also"></a>Vedere anche
--------

[Retail peripherals overview](retail-peripherals-overview.md)


