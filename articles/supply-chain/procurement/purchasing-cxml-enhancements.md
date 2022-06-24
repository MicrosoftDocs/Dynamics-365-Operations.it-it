---
title: Miglioramenti cXML per gli acquisti
description: La funzionalità Miglioramenti cXML per gli acquisti si basa sulla funzionalità del catalogo esterno esistente, PunchOut, utilizzata per le richieste di acquisto.
author: GalynaFedorova
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatCXMLParameters, CatCXMLPurchRequest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2020-08-03
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 87dccd19ade1b27db9a6d454659fec6142de4c65
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890917"
---
# <a name="purchasing-cxml-enhancements"></a>Miglioramenti cXML per gli acquisti

[!include [banner](../includes/banner.md)]

La funzionalità _Miglioramenti cXML per gli acquisti_ si basa sulla [funzionalità del catalogo esterno esistente](set-up-external-catalog-for-punchout.md) utilizzata per le richieste di acquisto. Questa funzionalità esistente è nota come _PunchOut_. Sebbene un ordine fornitore non debba avere origine da una richiesta di acquisto, deve esserci una connessione tra il fornitore in un ordine fornitore e i parametri utilizzati per inviare il documento dell'ordine fornitore.

## <a name="turn-on-the-purchasing-cxml-enhancements-feature"></a>Attivare la funzionalità Miglioramenti cXML per gli acquisti

Per attivare la funzionalità, apri la pagina **[Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e cerca la funzionalità denominata *Miglioramenti cXML per gli acquisti*. Seleziona la funzionalità, quindi seleziona **Abilita ora** per attivarla. (A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita.)

Dopo aver attivato la funzionalità, è necessario configurare le impostazioni nelle tre aree seguenti:

- **[Parametri cXML](#cxml-parameters)**: utilizza queste impostazioni per configurare alcuni parametri globali per la funzionalità di invio degli ordini fornitore.
- **[Configurazione del fornitore](#vendor-setup)**: se commerce eXtensible Markup Language (cXML) deve essere utilizzato per impostazione predefinita per tutti i nuovi ordini fornitore creati per qualsiasi fornitore, imposta l'opzione **Invia ordine fornitore tramite cXML** su _Sì_ per tale fornitore.
- **[Cataloghi esterni](#external-catalog-setup)**: utilizza le nuove impostazioni **Proprietà ordine** per definire il formato del documento dell'ordine fornitore e come viene inviato.

La figura seguente riepiloga questa configurazione.

![Aree per la configurazione delle funzionalità cXML.](media/cxml-settings-areas.png "Aree per la configurazione delle funzionalità cXML")

Inoltre, è necessario configurare il [processo batch di richiesta dell'ordine fornitore](#po-batch). Questo processo batch viene utilizzato per inviare gli ordini fornitore confermati.

## <a name="set-up-global-cxml-parameters"></a><a name="cxml-parameters"></a>Configurare i parametri cXML globali

Utilizza la pagina **Parametri cXML** per effettuare alcune impostazioni globali che si applicano alla funzionalità di invio degli ordini fornitore.

![Pagina dei parametri cXML.](media/cxml-parameters.png "Pagina dei parametri cXML")

Vai a **Approvvigionamento \> Impostazione \> Gestione cXML \> Parametri cXML** e imposta i seguenti parametri:

- **Modalità di test cXML**: questo parametro globale influisce sul modo in cui gli ordini fornitore vengono inviati fisicamente dal processo batch. Selezionare uno dei seguenti valori:

    - **Test**: in questa modalità, il processo batch può essere in esecuzione e il documento XML per il messaggio viene generato, ma non viene inviato. Viene invece salvato nella richiesta di ordine fornitore a scopo di revisione. Questa modalità è utile quando ti trovi in un'implementazione iniziale e vuoi vedere come vengono immessi i dati nel messaggio cXML. Potresti anche voler generare messaggi di esempio da inviare ai fornitori per la convalida iniziale.
    - **Live**: in questa modalità, la funzionalità utilizza le [impostazioni del catalogo esterno](#external-catalog-setup) per trasmettere fisicamente ogni documento al fornitore.

- **Invia aggiornamenti richiesta di acquisto**: imposta questa opzione su *Sì* per inviare un messaggio di aggiornamento per gli ordini fornitore. Impostala su *No* per impedire che il messaggio venga inviato. La maggior parte dei fornitori preferisce non ricevere messaggi di aggiornamento. Richiedono invece che i clienti li contattino per telefono o e-mail se un ordine fornitore deve essere modificato. Questo parametro è un parametro globale e non è possibile specificare alcuna sostituzione nel catalogo esterno per ciascun fornitore. Un ordine fornitore verrà contrassegnato come aggiornato se registri una seconda conferma su un ordine fornitore, ma la prima conferma è già stata inviata e riconosciuta dal fornitore. Se c'è una seconda conferma, ma la prima conferma non è stata inviata, la seconda conferma sarà trattata come un nuovo documento. Puoi confermare un ordine fornitore tutte le volte che vuoi finché non viene inviata una conferma. La successiva conferma verrà quindi considerata come un messaggio di aggiornamento.
- **Invia eliminazione richiesta di acquisto**: imposta questa opzione su *Sì* per inviare un messaggio di eliminazione per gli ordini fornitore. Impostala su *No* per impedire che il messaggio venga inviato. La maggior parte dei fornitori preferisce non ricevere messaggi di eliminazione. Richiedono invece che i clienti li contattino per telefono o e-mail se un ordine fornitore è stato inviato per errore. Questo parametro è un parametro globale e non è possibile specificare alcuna sostituzione nel catalogo esterno per ciascun fornitore. Un ordine fornitore verrà contrassegnato come eliminato se annulli l'ordine fornitore in Supply Chain Management.
- **File di archivio**: specifica il percorso del file in cui vuoi esportare e salvare i documenti cXML archiviati. Il percorso viene utilizzato quando esegui la funzione di eliminazione dalla pagina **Richiesta ordine fornitore**.
- **Numero massimo di caratteri per riga della via**: immetti il numero massimo di caratteri che possono essere utilizzati nel campo della via per gli indirizzi nel documento cXML. Questo parametro globale influisce su tutti i fornitori a meno che non venga specificato un override nelle proprietà del catalogo esterno.

## <a name="set-up-vendor-purchase-orders-to-use-cxml"></a><a name="vendor-setup"></a>Configurare ordini fornitore per utilizzare cXML

Ogni volta che confermi un ordine fornitore in cui l'opzione **Invia ordine fornitore tramite cXML** è impostata su _Sì_, il sistema genera automaticamente il messaggio cXML e lo consegna al fornitore associato a quell'ordine fornitore. Esistono due modi per controllare questa opzione per i tuoi ordini fornitore:

- Per configurare un fornitore in modo che utilizzi automaticamente cXML per tutti i nuovi ordini fornitore creati da una richiesta, vai a **Approvvigionamento \> Fornitori \> Tutti i fornitori** e seleziona o crea un fornitore per aprire la relativa pagina dei dettagli. Quindi, nella Scheda dettaglio **Impostazioni predefinite ordini fornitore**, imposta l'opzione **Invia ordine fornitore tramite cXML** su _Sì_. Se cXML deve essere utilizzato automaticamente anche per i nuovi ordini fornitore che **non** sono creati a partire da una richiesta, è necessario impostare anche la proprietà dell'ordine **ENABLEMANUALPO** su _True_ per il relativo catalogo esterno, come descritto nella sezione [Impostare le proprietà dell'ordine](#set-order-properties) più avanti in questo articolo.
- Per singoli ordini fornitore, vai a **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore** e seleziona o crea un ordine fornitore per aprire la relativa pagina dei dettagli. Passa alla visualizzazione **Intestazione**, quindi, nella Scheda dettaglio **Impostazione**, imposta l'opzione **Invia ordine fornitore tramite cXML** come richiesto.

![Impostazioni predefinite per gli ordini fornitore.](media/cxml-order-defaults.png "Impostazioni predefinite per gli ordini fornitore")

## <a name="set-up-an-external-catalog-to-use-cxml"></a><a name="external-catalog-setup"></a>Configurazione di un catalogo esterno per utilizzare cXML

Nella pagina **Cataloghi esterni**, per ciascuno dei tuoi cataloghi, puoi configurare la funzionalità PunchOut e la funzionalità per l'invio degli ordini fornitore. Per trovare le impostazioni pertinenti, vai a **Approvvigionamento \> Cataloghi \> Cataloghi esterni**. Inizia mediante la [configurazione di ogni catalogo come al solito](set-up-external-catalog-for-punchout.md). Questo processo include l'assegnazione di un fornitore, la selezione delle categorie che il fornitore è autorizzato a fornire e l'attivazione del catalogo. Quindi configura le impostazioni aggiuntive descritte in questa sezione.

> [!NOTE]
> Quando confermi un ordine fornitore che può essere inviato tramite cXML, il sistema cerca il fornitore associato all'ordine fornitore e quindi trova il primo catalogo esterno attivo associato a quel fornitore. Il sistema utilizza quindi le impostazioni di quel catalogo esterno per inviare l'ordine fornitore. Se sono configurati più cataloghi esterni, il sistema utilizza solo il primo catalogo esterno che trova, in base al fornitore nell'ordine fornitore. Pertanto, è consigliabile creare un solo catalogo esterno per ogni fornitore.

![Impostazioni del catalogo esterno.](media/cxml-supplier-catalog.png "Impostazioni del catalogo esterno")

### <a name="set-the-punchout-protocol-type"></a>Impostare il tipo di protocollo PunchOut

Nella Scheda dettaglio **Generale** della pagina **Cataloghi esterni**, imposta il campo **Tipo di protocollo Punchout** su _cXML_. Questa opzione sarà l'unica opzione disponibile, a meno che un partner non abbia esteso la funzionalità e fornisca un'opzione aggiuntiva nell'estensione.

Se stai usando anche il catalogo per PunchOut, devi anche [configurare il formato del messaggio](set-up-external-catalog-for-punchout.md). Il formato del messaggio viene utilizzato per stabilire la connessione al fornitore nella transazione PunchOut dalla richiesta. Quando viene inviato un ordine fornitore, le proprietà dell'ordine verranno utilizzate per stabilire la connessione con un fornitore.

### <a name="set-the-order-properties"></a><a name="set-order-properties"></a>Impostare le proprietà dell'ordine

La funzionalità _Miglioramenti cXML per gli acquisti_ aggiunge una nuova Scheda dettaglio **Proprietà dell'ordine** per cataloghi esterni. Questa Scheda dettaglio fornisce una griglia in cui è possibile definire le proprietà dell'ordine. Fornisce inoltre una barra degli strumenti. Questa barra degli strumenti contiene i seguenti tre pulsanti che puoi utilizzare per gestire le proprietà dell'ordine:

- **Proprietà predefinite**: quando configuri un nuovo catalogo, seleziona questo pulsante per aggiungere una raccolta predefinita di proprietà di uso comune alla griglia.
- **Nuova**: aggiungi una nuova proprietà alla griglia.
- **Elimina**: elimina la proprietà attualmente selezionata dalla griglia. Se elimini accidentalmente una proprietà predefinita, seleziona **Proprietà predefinite** per ripristinare tutte le proprietà mancanti.

Ogni volta che aggiungi una o più proprietà alla griglia, utilizza la colonna di destra per specificare un valore per ciascuna.

Utilizza le proprietà predefinite nel modo seguente:

- **BUYER\_COOKIE**: questo campo di monitoraggio può essere utilizzato per indicare informazioni specifiche per la tua azienda. A meno che tu non abbia un accordo con il venditore su come viene utilizzata questa proprietà, non ha molto significato quando si invia un ordine fornitore. Pertanto, è consigliabile impostarla su un valore semplice.
- **DELIVERTO**: quando l'indirizzo di spedizione viene inserito nel documento dall'ordine fornitore, il campo **Informazioni di avviso** viene utilizzato per impostare il campo **DeliverTo** nel messaggio XML. Se hai bisogno che questo valore sia un nome di richiedente e imposterai il campo del richiedente nell'intestazione dell'ordine fornitore, immetti il valore _REQUESTER_ per questa proprietà, in modo che il nome del richiedente venga inserito nel campo **DeliverTo** nell'XML. In questo caso, l'indirizzo e-mail principale e il numero di telefono utilizzati proverranno dal richiedente anziché dall'ordinante.
- **DEPLOYMENTMODE**: imposta questa proprietà come richiesto dal fornitore. I valori sono generalmente _PRODUCTION_ o _TEST_. Imposta il valore in base alla tua comunicazione con il fornitore. In genere deve corrispondere al sistema previsto dietro il valore **ORDERCHECKURL** che il fornitore indica come sistema di test o di produzione.
- **FIXEDBILLADDRESSID**: quando il campo **addressID** nel messaggio XML è impostato, importa la posizione specificata nell'indirizzo. Se il valore ID che hai comunicato al fornitore differisce dal valore nella posizione dell'indirizzo per qualche motivo, puoi forzare una sostituzione specificando il valore qui. Il presupposto è che utilizzerai un solo indirizzo con il fornitore e che l'indirizzo sia configurato nel sistema del fornitore. L'indirizzo di fatturazione è l'indirizzo di fatturazione principale specificato per la persona giuridica in Supply Chain Management.
- **FIXEDSHIPADDRESSID**: quando il campo **addressID** nel messaggio XML è impostato, importa la posizione specificata nell'indirizzo. Se il valore ID che hai comunicato al fornitore differisce dal valore nella posizione dell'indirizzo per qualche motivo, puoi forzare una sostituzione specificando il valore qui. Il presupposto è che utilizzerai un solo indirizzo con il fornitore e che l'indirizzo sia configurato nel sistema del fornitore. L'indirizzo di spedizione è l'indirizzo specificato nell'intestazione dell'ordine fornitore. La maggior parte dei fornitori accetta solo indirizzi di intestazione, non indirizzi di riga. Sebbene nell'XML siano presenti campi per gli indirizzi di riga, verranno impostati sull'indirizzo dell'intestazione.
- **FROM\_DOMAIN**: immetti il valore utilizzato per inviare i documenti dell'ordine fornitore. Questo valore viene fornito dal fornitore.
- **FROM\_IDENTITY**: immetti il valore utilizzato per inviare i documenti dell'ordine fornitore. Questo valore viene fornito dal fornitore.
- **ORDERCHECKURL**: immetti l'URL su cui trasmettere i documenti dell'ordine fornitore. Questo URL inizia con `https://` ed è fornito dal fornitore.
- **PAYLOAD\_ID**: immetti un valore di prefisso per l'ID payload, come richiesto per i processi aziendali in atto per il fornitore corrente.
- **SENDER\_DOMAIN**: immetti il valore utilizzato per inviare i documenti dell'ordine fornitore. Questo valore viene fornito dal fornitore.
- **SENDER\_IDENTITY**: immetti il valore utilizzato per inviare i documenti dell'ordine fornitore. Questo valore viene fornito dal fornitore.
- **SHARED\_SECRET**: immetti il valore utilizzato per inviare i documenti dell'ordine fornitore. Questo valore viene fornito dal fornitore.
- **STREETLENGTH**: immetti un numero che rappresenta il numero massimo di caratteri che il fornitore accetterà come nome della via. Se un valore viene immesso qui, sostituisce il valore specificato nella pagina **Parametri cXML**. Il sistema rimuoverà le interruzioni di riga e gli spazi per cercare di adattare l'indirizzo standard in Supply Chain Management al numero di caratteri qui specificato. Eventuali caratteri aggiuntivi verranno troncati.
- **TO\_DOMAIN**: immetti il valore utilizzato per inviare i documenti dell'ordine fornitore. Questo valore viene fornito dal fornitore.
- **TO\_IDENTITY**: immetti il valore utilizzato per inviare i documenti dell'ordine fornitore. Questo valore viene fornito dal fornitore.
- **USERAGENT**: inserisci un valore per identificare il sistema che stai utilizzando. Ad esempio immetti _Dynamics 365 Supply Chain Management_.
- **VERSION**: immetti un numero di versione cXML, se il fornitore richiede queste informazioni. La versione predefinita è *1.2.008*. Questa versione è stabile ed è accettata dalla maggior parte dei fornitori.
- **RESPONSETEXT**: immetti il testo personalizzato che prevedi il fornitore restituisca nel messaggio di risposta cXML dopo che l'ordine è stato inviato. In questo modo, il sistema può contrassegnare il messaggio come _Riconosciuto_. Se la risposta non corrisponde al testo standard o al testo del cliente che inserisci qui, la richiesta verrà contrassegnata come _Errore_.
- **RESPONSETEXTSUB**: imposta questa proprietà su _TRUE_ se vuoi cercare nel testo della risposta del fornitore i valori specificati nel campo **RESPONSETEXT**. Ad esempio, il fornitore potrebbe restituire una stringa lunga che include "OK" nella risposta. In questo caso puoi immettere _OK_ nel campo **RESPONSETEXT** e impostare **RESPONSETESTSUB** su _TRUE_ per cercare "OK" in qualsiasi punto della risposta. L'ordine può quindi essere impostato su _Riconosciuto_.
- **CONTENTTYPE**: in una tipica configurazione di catalogo, non è necessario impostare questa proprietà. Se ricevi un errore 500 del server dal sistema di un fornitore quando invii un ordine fornitore, puoi eseguire il test impostando questa proprietà su _FALSE_. Tale valore cambierà un'impostazione nella richiesta Web e potrebbe consentire l'invio del messaggio per alcune piattaforme.
- **ENABLEHEADERS**: imposta questa proprietà su _TRUE_ per inviare intestazioni insieme all'ordine fornitore. È necessario impostare questa proprietà solo se il fornitore lo richiede. Se imposti questa proprietà su _TRUE_, aggiungi proprietà personalizzate extra basate sui nomi forniti dal fornitore e aggiungi il prefisso _H\__. Esempi tipici includono **H\_USERID**, **H\_PASSWORD**, **H\_RECEIVERID** e **H\_ACTIONREQUEST**. Le seguenti proprietà personalizzate sono incluse nelle proprietà predefinite:

    - **H\_USERID**: se il partner commerciale richiede che tu invii un ID utente come parte dell'URL per inviare un ordine fornitore, inserisci il valore qui.
    - **H\_PASSWORD**: se il partner commerciale richiede che tu invii una password come parte dell'URL per inviare un ordine fornitore, inserisci il valore qui.

- **ENABLEMANUALPO**: se questa proprietà è impostata su _TRUE_, quando gli utenti creano manualmente ordini fornitore (ovvero, quando non iniziano da una richiesta), tali ordini fornitore erediteranno l'impostazione dell'opzione **Invia ordine fornitore tramite cXML** dal fornitore. Se questa proprietà non è impostata o se è impostata su _FALSE_, l'opzione **Invia ordine fornitore tramite cXML** non verrà impostata nell'intestazione dell'ordine fornitore per gli ordini fornitore creati manualmente. Per gli ordini fornitore creati da una richiesta, l'impostazione dell'opzione **Invia ordine fornitore tramite cXML** è sempre ereditata dal fornitore, indipendentemente dall'impostazione di questa proprietà. Per ulteriori informazioni, vedi la sezione [Configurare ordini fornitore per utilizzare cXML](#vendor-setup) precedente in questo articolo.
- **PUNCHOUTPOONLY**: se questa proprietà è impostata su _TRUE_, solo le righe della richiesta di acquisto create dal processo PunchOut imposteranno l'opzione **Invia ordine fornitore tramite cXML** nell'intestazione dell'ordine fornitore. Inoltre, il tipo di riga della richiesta di acquisto di tutte le righe dell'ordine fornitore deve essere _Articolo di catalogo esterno_. In caso contrario, non è possibile creare l'ordine fornitore cXML.
- **PUNCHOUTSHIPTO**: se questa proprietà è impostata su _TRUE_, l'indirizzo predefinito della persona giuridica verrà aggiunto al messaggio di richiesta di configurazione di PunchOut quando l'utente apre un catalogo esterno. Questo indirizzo viene aggiunto come indirizzo **ShipTo**. I fornitori useranno l'indirizzo **ShipTo** per mostrare i prezzi in base alla posizione dell'azienda.
- **TRACEPUNCHOUT**: imposta questa proprietà su _TRUE_ se viene visualizzato un messaggio di errore quando tenti di accedere a un catalogo esterno dalla richiesta. Le informazioni sulla traccia verranno quindi inserite per i messaggi **PunchOutSetupRequest** e **PunchOutResponse** inviati tra Supply Chain Management e il sito del fornitore. È possibile visualizzare queste informazioni nella pagina su **Registro messaggi carrello cXML**, che puoi aprire dalla pagina **Configurazione catalogo esterno** per il catalogo del fornitore con cui hai problemi. È consigliabile impostare questa proprietà su _TRUE_ solo se stai risolvendo i problemi, perché crea un grande sovraccarico delle prestazioni sul database per ogni PunchOut. Per ulteriori informazioni, vedi la sezione [Visualizzare il registro dei messaggi del carrello cXML per il PunchOut del catalogo esterno](#message-log) più avanti in questo articolo.
- **REPLACENEWLINE**: imposta questa proprietà su _TRUE_ se stai riscontrando un problema perché il sistema di un fornitore invia un messaggio **PunchOutResponse** che include caratteri di nuova riga (\\n). Questo problema potrebbe verificarsi se i messaggi del fornitore vengono analizzati tramite middleware o un hub di approvvigionamento. Se hai un problema con una nuova configurazione del fornitore, imposta la proprietà **TRACEPUNCHOUT** su _TRUE_ per visualizzare il messaggio **PunchOutResponse** e determinare se i tag XML sono suddivisi in caratteri di nuova riga.
- **POCOMMENTS**: imposta questa proprietà su _TRUE_ se vuoi che il documento cXML includa note allegate all'ordine fornitore in Supply Chain Management. Il testo dell'allegato è incluso nei commenti di intestazione nel messaggio dell'ordine fornitore. Per ulteriori informazioni su come il sistema seleziona ed elabora questi allegati, vedi la sezione [Allegare note a un ordine fornitore](#attach-po-notes) più avanti in questo articolo.
- **VENDCOMMENTS**: imposta questa proprietà su _TRUE_ se vuoi che il documento cXML includa note allegate all'ordine fornitore in Supply Chain Management. Il testo dell'allegato è incluso nei commenti di intestazione nel messaggio dell'ordine fornitore. Per ulteriori informazioni su come il sistema seleziona ed elabora questi allegati, vedi la sezione [Allegare note a un ordine fornitore](#attach-po-notes).
- **CLEANAMP**: imposta questa proprietà su _TURE_ se ricevi un messaggio di errore quando tenti di eseguire un PunchOut a un fornitore e l'URL di ritorno del fornitore include e commerciali codificate in modo errato (\&).
- **PUNCHOUTTZ**: imposta questa proprietà su _TRUE_ se il fornitore con cui stai lavorando utilizza lo standard International Organization for Standardization (ISO) 8601 per eseguire una convalida specifica della data/ora del messaggio di richiesta PunchOut. Supply Chain Management utilizza la data UTC (Coordinated Universal Time) nel messaggio **PunchOutSetupRequest**. Pertanto, quando imposti questa proprietà su _TRUE_, *+00: 00* viene aggiunto al formato di data/ora.
- **WMSADDRESSID**: imposta questa proprietà su _TRUE_ per utilizzare il numero di magazzino nell'intestazione dell'ordine fornitore come valore **addressID** nell'indirizzo **ShipTo** per la richiesta di ordine fornitore inviata al fornitore. Se imposti un valore per la proprietà **FIXEDSHIPADDRESSID**, tale valore ha la precedenza su questo valore. Pertanto, è consigliabile utilizzare una proprietà o l'altra per impostare il valore **addressID** nell'indirizzo **ShipTo** per il documento.
- **PUNCHOUTSHIPTOUSER**: questa proprietà funziona insieme alla proprietà **PUNCHOUTSHIPTO**. Se **PUNCHOUTSHIPTO** è impostata su _TRUE_, viene prelevato l'indirizzo della persona giuridica. Se **PUNCHOUTSHIPTOUSER** è impostata su _TRUE_, viene utilizzato l'indirizzo principale dell'utente PunchOut al posto dell'indirizzo della persona giuridica.

### <a name="activate-the-external-catalog"></a>Attivare il catalogo esterno

Quando hai finito di configurare tutte le proprietà e la configurazione delle altre impostazioni per il tuo catalogo esterno, torna alla Scheda dettaglio **Generale** della pagina **Cataloghi esterni** e imposta l'opzione **Attivo** su *Sì*.

### <a name="attach-notes-to-a-purchase-order"></a><a name="attach-po-notes"></a>Allegare note a un ordine fornitore

Come è stato accennato nella sezione [Impostare le proprietà dell'ordine](#set-order-properties), se desideri che il file cXML consegnato includa il testo delle note allegate all'ordine fornitore e/o ai record del fornitore, puoi impostare la proprietà **POCOMMENTS** e/o **VENDCOMMENTS** su _TRUE_ nella configurazione del catalogo esterno. Questa sezione fornisce maggiori dettagli su come il sistema seleziona ed elabora questi allegati, se vengono utilizzati.

Per impostare i tipi di note che il sistema cercherà, vai a **Approvvigionamento \> Impostazione \> Moduli \> Impostazione moduli**. Quindi, nella scheda **Ordine fornitore**, imposta il campo **Includi documenti di tipo** al tipo di nota che vuoi essere in grado di includere. Verranno incluse solo note di testo, non allegati di documenti.

![Pagina di configurazione del modulo.](media/cxml-form-setup.png "Pagina di configurazione del modulo")

Gli allegati verranno inclusi con un ordine fornitore solo se il loro campo **Tipo** è impostato sul valore selezionato nel campo **Includi documenti di tipo** e se il loro campo **Restrizione** è impostato su _Esterno_. Per creare, visualizzare o modificare gli allegati per un ordine fornitore, vai a **Approvvigionamento \> Tutti gli ordini fornitore**, seleziona o crea un ordine fornitore, quindi seleziona il pulsante **Allegati** (simbolo della graffetta) nell'angolo in alto a destra.

![Nota allegata configurata per essere inviata a un fornitore.](media/cxml-note-to-vendor.png "Nota allegata configurata per essere inviata a un fornitore")

## <a name="view-the-cxml-cart-message-log-for-external-catalog-punchout"></a><a name="message-log"></a>Visualizzare il registro dei messaggi del carrello cXML per il PunchOut del catalogo esterno

Quando imposti il campo **Tipo di protocollo Punchout** su _cXML_ per un catalogo esterno, il sistema acquisirà un registro dei messaggi dei carrelli che tornano indietro dai fornitori. Questo registro può essere utilizzato per la risoluzione dei problemi e altri scopi relativi ai dati.

Per aprire il registro per un catalogo esterno, seleziona il catalogo pertinente, quindi, nel riquadro azioni, seleziona **Registro messaggi carrello cXML**. La pagina **Registro messaggi carrello cXML** mostra un elenco dei carrelli che sono stati restituiti, l'XML correlato a tali carrelli e le righe che sono state create nella richiesta di acquisto correlata.

![Pagina Registro messaggi carrello cXML.](media/cxml-cart-message-log.png "Pagina Registro messaggi carrello cXML")

## <a name="set-the-extrinsic-elements-for-external-catalog-punchout"></a>Impostare gli elementi estrinseci per il PunchOut del catalogo esterno

Quando imposti il campo **Tipo di protocollo Punchout** su *cXML* per un catalogo esterno, è possibile aggiungere elementi estrinseci personalizzati che verranno inseriti nella posizione corretta nel messaggio XML di richiesta.

Per aggiungere elementi estrinseci a un catalogo esterno, segui questi passaggi.

1. Vai ad **Approvvigionamento \> Cataloghi \> Cataloghi esterni**.
1. Seleziona il relativo catalogo.
1. Nella Scheda dettaglio **Formato messaggio**, nella sezione **Estrinseci**, seleziona **Aggiungi** per aggiungere una riga alla griglia per ogni elemento estrinseco che desideri includere. Su ciascuna riga, imposta i seguenti campi:

    - **Nome**: immetti un nome per l'elemento. Questo valore diventerà il valore dell'attributo **name** per l'elemento XML **Estrinseco** creato da ogni riga. In genere, lavorerai con il tuo fornitore per concordare il nome di ogni elemento estrinseco.
    - **Valore**: seleziona un valore per l'elemento. Questo valore diventerà il valore dell'elemento XML creato da ogni riga. Sono disponibili i valori seguenti:

        - **Nome utente**: utilizza il nome dell'utente che sta effettuando il PunchOut. Questo nome è il nome di accesso per Supply Chain Management.
        - **E-mail utente**: utilizza l'indirizzo e-mail dell'utente che sta effettuando il PunchOut. Questo indirizzo è l'indirizzo che l'utente ha configurato nella scheda **Account** della pagina **Opzioni utente**.
        - **Valore casuale**: utilizza un valore casuale univoco.
        - **Nome completo dell'utente**: utilizza il nome completo della persona di contatto associata all'utente che accede al catalogo esterno.
        - **Nome**: utilizza il nome della persona di contatto associata all'utente che accede al catalogo esterno.
        - **Cognome**: utilizza il cognome della persona di contatto associata all'utente che accede al catalogo esterno.
        - **Numeto di telefono**: utilizza il numero di telefono principale della persona di contatto associata all'utente che accede al catalogo esterno.

![Impostazioni degli elementi estrinseci.](media/cxml-extrinsics.png "Impostazioni degli elementi estrinseci")

L'utente o l'amministratore non vedrà gli elementi estrinseci, perché non vengono aggiunti finché l'utente non esegue un PunchOut. Verranno automaticamente inseriti tra gli elementic **BuyerCookie** e **BrowserFromPost** nel messaggio di richiesta di configurazione cXML. Pertanto, non è necessario impostarli manualmente nell'XML quando si configura il catalogo esterno.

![Elementi estrinseci aggiunti all'XML.](media/cxml-extrinsics-xml.png "Elementi estrinseci aggiunti all'XML")

## <a name="create-and-process-a-purchase-order"></a><a name="create-po"></a>Creare ed elaborare un ordine fornitore

Quando crei un ordine fornitore per un fornitore, erediterà l'impostazione dell'opzione **Invia ordine fornitore tramite cXML** da quel fornitore. Tuttavia, l'impostazione rimane disponibile nella Scheda dettaglio **Impostazione** della visualizzazione **Intestazione** dell'ordine fornitore, in modo da poterlo modificare successivamente secondo necessità.

![Ordine fornitore impostato per utilizzare cXML.](media/cxml-purchase-order.png "Ordine fornitore impostato per utilizzare cXML")

Quando crei un ordine fornitore da una richiesta di acquisto proveniente da un flusso PunchOut, verranno compilati tutti i dettagli della riga richiesti. È quindi possibile aggiungere manualmente righe di ordine fornitore o copiarle da altri ordini fornitore. Assicurati di impostare tutti i campi obbligatori. Questi campi obbligatori includono il numero di riferimento esterno, che è il numero del fornitore che verrà utilizzato nel messaggio cXML.

![Esempio di un numero di riferimento esterno.](media/cxml-line-details.png "Esempio di un numero di riferimento esterno")

Quando hai finito di compilare tutti i dettagli per l'ordine fornitore, assicurati di confermarlo. Nessun messaggio viene inviato a meno che l'ordine fornitore non venga confermato. Per confermare un ordine fornitore, nella scheda **Acquisti** del riquadro azioni, nel gruppo **Azioni**, seleziona **Conferma** . 

Dopo la conferma dell'ordine fornitore, è possibile visualizzare lo stato della conferma tramite i giornali di registrazione **Conferme ordini fornitore**. Nella scheda **Acquisti** del riquadro azioni fai clic su **Conferme ordini fornitore** nel gruppo **Giornali di registrazione**.

Ogni ordine fornitore può avere molte conferme. Ogni conferma è contrassegnata da un numero incrementale. Nella figura seguente, l'ordine fornitore è *00000275* e la conferma è *00000275-1*. Questa numerazione riflette la funzionalità standard di Supply Chain Management, in cui le modifiche in un ordine fornitore, e quindi il tipo di messaggio cXML che deve essere inviato al fornitore, vengono identificate in base alla conferma. Come mostra l'illustrazione, la pagina **Conferme ordini fornitore** include anche i campi **Stato invio ordine** e **Stato fornitore richiesta ordine**. Per ulteriori informazioni sui vari valori di stato che potresti vedere in questa pagina, consulta la sezione [Monitorare le richieste di ordini fornitore](#monitor-po-requests) più avanti in questo articolo.

![Pagine delle conferme degli ordini fornitore.](media/cxml-po-confirmations.png "Pagine delle conferme degli ordini fornitore")

Per visualizzare ulteriori informazioni sul documento, seleziona **Richiesta ordine fornitore** sopra la griglia.

La pagina **Richiesta ordine fornitore** include due griglie. La griglia nella parte superiore della pagina ha un record per ogni ordine fornitore contrassegnato per l'invio. La griglia nella scheda **Cronologia richieste ordini fornitore** nella parte inferiore della pagina potrebbe contenere diversi record per l'ordine fornitore selezionato, per indicare lo stato di ciascuna conferma. La figura seguente mostra l'ordine fornitore 00000275 nella griglia superiore e il documento 00000275-1 nella griglia sulla scheda **Cronologia richieste di ordine fornitore**.

![Pagina di richiesta ordine fornitore.](media/cxml-po-request.png "Pagina richieste ordini fornitore")

Se il processo batch è configurato e in esecuzione, il documento verrà inviato. È possibile visualizzare la modifica dello stato dopo che il documento è stato inviato. Nella figura seguente, il campo **Stato invio ordine** è impostato su _Inviato_. Il campo **Stato fornitore richiesta ordine** è impostato su _Riconosciuto_ per indicare che il fornitore ha ricevuto il documento ed è stato in grado di leggerlo e memorizzarlo nel proprio sistema. La griglia nella scheda **Cronologia richieste ordine fornitore** mostra l'ora in cui il documento è stato inviato. Per ulteriori informazioni sui vari valori di stato che potresti vedere in questa pagina, consulta la sezione [Monitorare le richieste di ordini fornitore](#monitor-po-requests).

![Messaggi di stato nella pagina di richiesta ordine fornitore.](media/cxml-po-request-2.png "Messaggi di stato nella pagina di richiesta ordine fornitore")

## <a name="schedule-the-purchase-order-request-batch-job"></a><a name="po-batch"></a>Pianificarere il processo batch di richiesta dell'ordine fornitore

Per attivare il processo batch per l'invio di richieste di ordini fornitore, vai a **Approvvigionamento \> Impostazione \> Gestione cXML \> Richiesta ordine fornitore**, quindi, nel riquadro azioni, nella scheda **Richiesta ordine fornitore**, nel gruppo **Batch**, seleziona **Invia lavoro** per aprire la finestra di dialogo **Preparazione e invio della richiesta di acquisto**. È possibile utilizzare questa finestra di dialogo per configurare la ricorrenza, proprio come si fa normalmente per i processi batch in Supply Chain Management. Seleziona un intervallo, in base al volume dell'ordine. Sebbene sia possibile eseguire il processo batch ogni minuto, probabilmente è meglio inviare batch nell'arco della giornata lavorativa, in base alle finestre di ricezione degli ordini che corrispondono alle pianificazioni dei fornitori.

Ad esempio, il tuo fornitore dispone di criteri secondo cui tutti gli ordini ricevuti entro le 13:00 verranno spediti lo stesso giorno. In questo caso, potresti dover eseguire il batch solo poche volte durante la mattina per comunicare eventuali ordini che hai. Gli ordini rimanenti verranno quindi inviati il giorno successivo. Questa decisione è puramente una decisione aziendale. Puoi esaminarlo e impostarne i parametri di conseguenza.

Il processo cercherà i documenti di richiesta di ordine fornitore con stato *In attesa*. Se hai un ordine che devi inviare immediatamente a un fornitore, puoi selezionare **Invia lavoro** e impostare l'opzione **Elaborazione batch** su *No*.

## <a name="monitor-purchase-order-requests"></a><a name="monitor-po-requests"></a>Monitorare le richieste di ordini fornitore

### <a name="view-the-status-of-a-purchase-order"></a>Visualizzare lo stato di un ordine fornitore

Quando gli ordini che possono essere inviati tramite cXML vengono confermati, entrano nello stato _In attesa_. Come è stato descritto nella sezione [Creare ed elaborare un ordine fornitore](#create-po), è possibile visualizzare lo stato dell'ordine fornitore nella pagina **Richiesta ordine fornitore**. Ogni richiesta di ordine fornitore può avere uno tra diversi stati, a seconda dei suoi parametri e dati. Questa sezione descrive i vari tipi di stato e i valori che possono avere. Queste informazioni possono aiutarti a gestire i problemi e comprendere lo stato dei tuoi ordini fornitore.

![Stato dell'ordine fornitore nella pagina di richiesta ordine fornitore.](media/cxml-monitor-po-request.png "Stato dell'ordine fornitore nella pagina di richiesta ordine fornitore")

La griglia nella parte superiore della pagina **Richiesta ordine fornitore** potrebbe mostrare i seguenti valori di stato:

- **Stato invio ordine**: questo campo può contenere uno dei valori seguenti:

    - **In attesa**: il documento è in attesa di essere inviato.
    - **Inviato**: il documento è stato inviato.
    - **Interrotto**: il documento è stato contrassegnato come _Interrotto_ prima che fosse inviato. (Per contrassegnare un documento come _Interrotto_, seleziona **Interrompi** nel riquadro azioni della pagina **Richiesta d'acquisto**).
    - **Archivio**: il documento è stato eliminato. (Per eliminare un documento, seleziona **Elimina** nel riquadro azioni della pagina **Richiesta d'acquisto**).

- **Stato fornitore richiesta ordine**: questo campo può contenere uno dei valori seguenti:

    - **In attesa**: il documento è in attesa di essere inviato.
    - **Riconosciuto**: il documento è stato riconosciuto come ricevuto dal fornitore. È possibile esaminare il messaggio XML dettagliato restituito dal fornitore selezionando la scheda **XML di risposta** nella parte inferiore della pagina.
    - **Errore**: il documento è stato inviato al fornitore, ma si è verificato un errore. È possibile rivedere il messaggio di errore selezionando la scheda **XML di risposta** nella parte inferiore della pagina.

La griglia sulla scheda **Cronologia richieste ordine fornitore** nella parte inferiore della pagina **Richiesta ordine fornitore** potrebbe mostrare i seguenti valori:

- **Tipo richiesta ordine**: questo campo può contenere uno dei valori seguenti:

    - **Nuovo**: la riga viene contrassegnata come nuova subito dopo la conferma dell'ordine fornitore.
    - **Aggiornamento**: se una conferma è già stata inviata e riconosciuta dal fornitore, la conferma successiva sarà contrassegnata come _Aggiornamento_. Gli aggiornamenti verranno inviati solo se l'opzione **Invia aggiornamenti richiesta acquisto** è impostata su *Sì* nei [parametri cXML globali](#cxml-parameters).
    - **Elimina**: se una conferma è già stata inviata e riconosciuta dal venditore, ma l'ordine fornitore viene annullato, la conferma in attesa sarà contrassegnata come _Elimina_. Le eliminazioni verranno inviati solo se l'opzione **Invia eliminazioni richiesta acquisto** è impostata su *Sì* nei [parametri cXML globali](#cxml-parameters).

- **Ora richiesta**: l'ora in cui è stata creata la conferma dell'ordine. È possibile confrontare l'ora della richiesta con l'ora dello stato dell'ordine per determinare il tempo tra la conferma e il riconoscimento del fornitore.
- **Stato invio ordine**: questo campo è uguale al campo **Stato invio ordine** nella parte superiore della pagina. Viene ripetuto qui per semplificare la visualizzazione dello stato a livello di conferma. Se il campo **Tipo di richiesta ordine** è impostato su *Nuovo* e l'ordine fornitore viene riconfermato prima dell'invio di una conferma, il campo **Stato invio ordine** è impostato su *Archivio*.
- **Ora di stato ordine**: l'ora in cui il record della cronologia delle richieste di ordine fornitore è stato aggiornato l'ultima volta. (Gli aggiornamenti includono modifiche di stato).
- **Stato fornitore richiesta ordine**: questo campo è uguale al campo **Stato fornitore richiesta ordine** nella parte superiore della pagina. Viene ripetuto qui per semplificare la visualizzazione dello stato a livello di conferma.
- **Ora nuovo invio**: l'ora in cui il record è stato ripresentato.
- **Conteggio nuovo invio**: il numero di volte in cui il record è stato inviato nuovamente. Un numero alto indica più errori e quindi potrebbe indicare un problema con la configurazione dei dati o con la configurazione dei dati del fornitore.

### <a name="view-the-xml-for-a-purchase-order-request-message"></a>Visualizzare l'XML per un messaggio di richiesta di ordine fornitore

Per visualizzare l'XML per il messaggio di richiesta dell'ordine fornitore, seleziona la scheda **Testo XML richiesta** nella parte inferiore della pagina **Richiesta ordine fornitore**. Le informazioni in questa scheda possono essere utili durante il test o la convalida degli errori. Per rendere le informazioni più facili da leggere, puoi visualizzarle come un messaggio formattato. Copia il contenuto della scheda in un file di testo e quindi visualizzalo in un editor XML.

![Scheda Testo XML richiesta.](media/cxml-request-xml-text.png "Scheda Testo XML richiesta")

### <a name="view-the-details-of-the-vendor-response"></a>Visualizzare i dettagli della risposta del fornitore

Per visualizzare il contenuto di un riconoscimento del fornitore o di una risposta all'errore, seleziona la scheda **XML risposta** nella parte inferiore della pagina **Richiesta ordine fornitore**.

![Scheda XML risposta.](media/cxml-response-xml.png "Scheda XML risposta")

## <a name="additional-resources"></a>Risorse aggiuntive

- [Impostare un catalogo esterno per eProcurement PunchOut](set-up-external-catalog-for-punchout.md)
- [Usare cataloghi esterni per PunchOut e-procurement](use-external-catalogs-for-punchout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
