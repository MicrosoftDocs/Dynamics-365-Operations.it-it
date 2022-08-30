---
title: Codici a barre GS1
description: Questo articolo descrive come impostare i codici a barre GS1 e i codici QR in modo che le etichette possano essere scansionate in un magazzino.
author: Mirzaab
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: e1c1c274054ed1c14c9b3fc0595baa029bf3124d
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336367"
---
# <a name="gs1-bar-codes"></a>Codici a barre GS1

[!include [banner](../includes/banner.md)]

I lavoratori del magazzino devono spesso completare diversi compiti quando usano uno scanner per dispositivi mobili per registrare i movimenti di un articolo, una paletta o un contenitore. Questi compiti possono includere sia la scansione di codici a barre che l'inserimento manuale di informazioni sul dispositivo mobile. I codici a barre utilizzano un formato specifico dell'azienda che si definisce e si gestisce utilizzando Microsoft Dynamics 365 Supply Chain Management.

I codici a barre GS1 per le etichette di spedizione sono stati sviluppati per fornire uno standard globale per lo scambio di dati tra le aziende. Sono disponibili sia in simbologie lineari (1D) (formati di codici a barre), come GS1-128, sia in simbologie 2D, come GS1 DataMatrix e codici QR GS1. I codici a barre GS1 non solo codificano i dati, ma permettono anche di utilizzare un elenco predefinito di *identificatori di applicazione* per definire il significato dei dati. Lo standard GS1 definisce il formato dei dati e i vari tipi di dati che possono essere utilizzati per codificare. A differenza dei vecchi codici a barre standard, i codici a barre GS1 possono avere più elementi di dati. Pertanto, una singola scansione del codice a barre può catturare diversi tipi di informazioni sul prodotto, come il lotto e la data di scadenza.

Il supporto GS1 nel Supply Chain Management semplifica drasticamente il processo di scansione nei magazzini dove i pallet e i contenitori sono etichettati utilizzando i codici a barre in formato GS1. I magazzinieri possono estrarre tutte le informazioni necessarie attraverso una singola scansione di un codice a barre GS1. Eliminando la necessità di fare più scansioni e/o inserire manualmente le informazioni, i codici a barre GS1 aiutano a ridurre il tempo associato alle attività. Allo stesso tempo, aiutano anche a migliorare la precisione.

I responsabili della logistica devono impostare l'elenco richiesto di identificatori di applicazioni e associare ciascuno di essi alle voci di menu appropriate del dispositivo mobile. Gli identificatori dell'applicazione possono poi essere usati in tutti i magazzini come impostazione globale per gli spostamenti e l'imballaggio. Pertanto, tutte le etichette di spedizione avranno una forma unificata.

Se non diversamente specificato, questo articolo usa il termine *codice a barre* per riferirsi sia ai codici a barre lineari (1D) che ai codici a barre 2D.

## <a name="the-gs1-bar-code-format"></a>Il formato del codice a barre GS1

Le Specifiche Generali GS1 specificano quali simbologie possono essere utilizzate per i codici a barre GS1 e come codificare i dati nel codice a barre. Questa sezione fornisce una breve introduzione all'articolo. Per tutti i dettagli, vedi le [Specifiche generali GS1](https://www.gs1.org/docs/barcodes/GS1_General_Specifications.pdf) che sono pubblicate da GS1. Il documento delle specifiche GS1 viene aggiornato regolarmente e le informazioni che fornisce sono aggiornate con le specifiche generali GS1 versione 22.0.

I codici a barre GS1 utilizzano le seguenti simbologie:

- **Codici a barre lineari o 1D** – GS1-128 e GS1 DataBar
- **Codici a barre 2D** – GS1 DataMatrix, GS1 QR Code e GS1 Dotcode

Ci sono menzioni speciali di GS1 in GS1-128, che è un caso speciale del codice a barre lineare Code-128 ordinario, GS1 DataMatrix e GS1 QR Code. La differenza tra la versione GS1 e la versione non GS1 è la presenza di un carattere speciale (FNC1) come primo carattere nei dati del codice a barre. La presenza di un carattere FNC1 indica che i dati nel codice a barre devono essere interpretati secondo la specifica GS1.

I dati nel codice a barre stesso sono costituiti da più elementi di dati, ciascuno dei quali è identificato da un identificatore dell'applicazione all'inizio del campo. Di solito, i dati vengono presentati anche sotto il codice a barre in un formato leggibile, dove l'identificatore dell'applicazione è mostrato tra parentesi. Ecco un esempio: `(01) 09521101530001 (17) 210119 (10) AB-123`. Questo codice a barre contiene tre elementi:

- **Identificatore dell'applicazione 01** – Il codice GTIN (Global Trade Item Number) GS1 dell'articolo.
- **Identificatore dell'applicazione 17** – Data di scadenza.
- **Identificatore dell'applicazione 10** – Il numero di batch.

Per ogni elemento, i dati possono avere una lunghezza predefinita o una lunghezza variabile. Esiste un elenco fisso di identificatori di applicazioni con lunghezze predefinite. Tutti gli altri identificatori dell'applicazione hanno una lunghezza variabile e l'elenco degli identificatori dell'applicazione GS1 specifica la lunghezza e il formato massimi dei dati. Ad esempio, l'identificatore dell'applicazione 01 ha una lunghezza predefinita di 16 caratteri (due per l'identificatore dell'applicazione stesso e 14 per il GTIN) e l'identificatore dell'applicazione 17 ha una lunghezza predefinita di otto caratteri (due per l'identificatore dell'applicazione stesso e sei per la data). Tuttavia, l'identificatore dell'applicazione 10 ha due numeri per l'identificatore dell'applicazione stesso e quindi fino a 20 caratteri alfanumerici.

Quando gli elementi vengono messi insieme, se un elemento segue un elemento di lunghezza variabile, è necessario utilizzare un carattere separatore. Questo separatore può essere il carattere speciale FNC1 o il carattere separatore di gruppo (un carattere non stampabile con codice ASCII 29 e codice esadecimale 1D). Il separatore non deve essere utilizzato dopo l'ultimo elemento. Sebbene il separatore non debba essere utilizzato dopo elementi che hanno una lunghezza predefinita, la sua presenza non è un errore critico.

Nei dati del codice a barre dell'esempio precedente di codice a barre che contiene gli identificatori dell'applicazione 01, 17 e 10, i dati in un simbolo Code-128, QR Code o DataMatrix verranno codificati come `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` (gli identificatori dell'applicazione sono mostrati in grassetto). Come procedura consigliata, qualsiasi elemento con lunghezza variabile deve essere inserito alla fine, per eliminare la necessità di un carattere separatore di gruppo aggiuntivo. Tuttavia, il codice a barre può anche avere un ordine di elementi diverso, dove il separatore è obbligatorio. Ecco un esempio: `<FNC1>`**`01`**`09521101530001`**`10`**`AB-123<GS>`**`17`**`210119`.

### <a name="dates-and-decimal-numbers"></a>Date e numeri decimali

Le date sono sempre rappresentate nel formato *AAMMGG* dove il secolo dell'anno è determinato dalle specifiche GS1. Possono essere rappresentate solo date da 49 anni nel passato a 50 anni nel futuro (rispetto all'anno in corso).

Alcuni elementi di dati contengono numeri decimali. Ad esempio, gli identificatori dell'applicazione 3100, 3101, ... 3105 rappresentano un peso netto in chilogrammi. Poiché questi identificatori di applicazione hanno una lunghezza predefinita di 10, sono disponibili sei numeri per la quantità. La posizione del punto decimale è specificata dall'ultimo numero dell'identificatore dell'applicazione. Pertanto, questa famiglia di identificatori di applicazione può anche essere rappresentata come *310n*. Poiché lo standard GS1 specifica che deve esserci sempre almeno un numero a sinistra della virgola decimale, è consentito un massimo di cinque cifre decimali.

Ecco alcuni esempi che mostrano come il numero *123456* sarà interpretato da diversi identificatori di applicazione (mostrati in grassetto):

- **`3100`**`123456` &rarr; 123456 (intero)
- **`3101`**`123456` &rarr; 12345,6 (una cifra decimale)
- **`3102`**`123456` &rarr; 1234,56 (due cifre decimali)
- **`3103`**`123456` &rarr; 123,456 (tre cifre decimali)
- **`3104`**`123456` &rarr; 12,3456 (quattro cifre decimali)
- **`3105`**`123456` &rarr; 1,23456 (cinque cifre decimali)

## <a name="scanning-gs1-bar-codes-in-supply-chain-management"></a>Scansione dei codici a barre GS1 in Supply Chain Management

Per eseguire la scansione dei codici a barre GS1, i magazzinieri utilizzano uno scanner integrato o connesso a un dispositivo mobile. Lo scanner trasmette quindi il codice a barre scansionato all'app per dispositivi mobili Warehouse Management come una serie di eventi della tastiera. Questa modalità di funzionamento è anche nota come *lettore collegato alla tastiera* o *lettore*. L'app per dispositivi mobili invia quindi il testo ricevuto così com'è a Supply Chain Management. Quando il sistema riceve i dati di input, determina prima se i dati iniziano con uno dei prefissi configurati che indicano che i dati sono effettivamente un codice a barre GS1 (vedi la sezione [Impostare le opzioni GS1 globali](#set-gs1-options)). Se i dati scansionati iniziano con uno di questi prefissi, il sistema utilizza un parser GS1 per analizzare i dati ed estrarre i singoli elementi di dati in base ai loro identificatori di applicazione. Dopo che i dati sono stati analizzati, il campo di input corrente o più campi verranno compilati con i dati scansionati.

### <a name="configuration-of-bar-code-scanner-hardware-and-software"></a>Configurazione hardware e software dello scanner di codici a barre

Affinché Supply Chain Management riconosca e decodifichi correttamente i codici a barre GS1, lo scanner hardware o il software di supporto devono essere configurati per eseguire le seguenti azioni:

- Aggiungere un prefisso ai codici a barre scansionati, in modo che il sistema possa riconoscere un codice a barre GS1.
- Convertire il carattere separatore di gruppo ASCII non stampabile (codice ASCII 29 o codice esadecimale 1D) in un carattere stampabile, ad esempio una tilde (~).

Sebbene sia possibile aggiungere qualsiasi prefisso al codice a barre scansionato, un'opzione consiste nell'aggiungere un identificatore di simbologia ISO/IEC 15424, noto anche come *Identificatore AIM*. Questo identificatore di tre caratteri inizia con `]`, quindi ha un carattere che identifica la simbologia utilizzata e ha un numero che viene utilizzato come ulteriore modificatore. Ad esempio, l'identificatore AIM `]C1` specifica un codice a barre Code 128 (a causa del carattere `C`), e il modificatore `1` specifica che nella prima posizione dei dati è presente un carattere FNC1. D'altra parte, `]C0` è un codice a barre Code 128 che ha qualsiasi altro carattere come primo carattere dei dati.

I seguenti cinque identificatori di simbologia corrispondono ai codici a barre GS1 che hanno elementi di identificazione dell'applicazione:

- `]C1` – Codice 128 (`C`) con il carattere FNC1 in prima posizione (`1`), noto anche come GS1-128.
- `]e0` – GS1 DataBar.
- `]d2` – Data Matrix (`d`) con ECC 200 e FNC1 in prima posizione (`2`), noto anche come GS1 DataMatrix.
- `]Q3` - QR Code (`Q`) Simbolo modello 2 con FNC1 in prima posizione (`3`), noto anche come codice QR GS1.
- `]J1` – Codice punto GS1.

Se usi questi identificatori, la compatibilità con codici a barre non GS1 richiede che gli scanner o il software di scansione siano configurati per rimuovere eventuali identificatori che non corrispondono agli identificatori GS1. Ad esempio, se esegui la scansione di un codice a barre Code 39 "normale", il prefisso `]A0` sarà aggiunto. Poiché il sistema non comprenderà questo prefisso come uno dei prefissi GS1, lo interpreterà come un dato e produrrà risultati imprevisti.

> [!NOTE]
> Per comodità, la versione 2.0.17.0 e successive dell'app per dispositivi mobili Warehouse Management rimuoveranno tutti i prefissi AIM non inclusi nell'elenco precedente. Questo comportamento supporta i casi in cui è possibile configurare lo scanner per aggiungere il prefisso AIM ma non per rimuovere i prefissi indesiderati.

### <a name="single-and-multiple-field-scanning"></a>Scansione a campo singolo e multiplo

Dopo che i dati sono stati analizzati dal codice a barre, verranno inseriti nei controlli di flusso del dispositivo mobile. Ci sono due metodi che verranno elaborati a turno:

- **Scansione a campo singolo** – Questo metodo compila solo il campo in cui è stato scansionato il codice a barre. Ad esempio, se scansioni il codice a barre `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` mentre il cursore è nel campo **Articolo**, il GTIN `09521101530001` dal codice a barre verrà inserito in quel campo. Se scansioni lo stesso codice a barre mentre il cursore è nel campo **ID batch**, il numero batch `AB-123` dal codice a barre verrà inserito. Questa modalità funziona per tutti i campi in tutti i flussi e richiede solo la configurazione dell'impostazione generica GS1. Se un codice a barre contiene più elementi, deve comunque essere scansionato più volte, perché solo una parte del codice a barre alla volta verrà inserita nel flusso del dispositivo mobile. Questo comportamento è controllato dall'impostazione generica GS1, come descritto nella sezione [Stabilire la configurazione GS1 generica](#generic-gs1-setup).
- **Scansione di più campi** – Questo metodo compila più campi quando viene scansionato un codice a barre, inserendo dati aggiuntivi nello stato di flusso del dispositivo mobile. Ad esempio, il criterio è configurato per inserire l'identificatore dell'applicazione 01 nel controllo `ItemId` e l'identificatore dell'applicazione 10 nel campo `InventBatchId`. In questo caso, se scansioni il codice a barre `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123`, i dati per entrambe le variabili verranno inviati contemporaneamente. Pertanto, il sistema non richiederà l'articolo e/o il numero di batch nel flusso. Questo comportamento è controllato dai criteri GS1 che sono collegati alle voci di menu, come descritto nella sezione [Impostare i criteri GS1 in modo che siano voci di menu del dispositivo mobile](#policies-for-menus).

> [!WARNING]
> I criteri GS1 predefiniti sono state testati per funzionare senza comportamenti imprevisti. Tuttavia, la personalizzazione dei criteri GS1 collegati alle voci di menu può causare comportamenti imprevisti, poiché il flusso potrebbe non aspettarsi che alcuni dati siano disponibili in un determinato momento.

## <a name="turn-on-the-gs1-feature"></a>Attivare la funzionalità GS1

Per poter utilizzare la funzionalità, è necessario attivarla per il sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome della funzione:** *Scansione di codici a barre GS1*

### <a name="turn-on-the-enhanced-parser-for-gs1-barcodes-feature"></a>Attivare la funzione parser avanzato per codici a barre GS1

Se utilizzi codici a barre GS1, ti consigliamo di attivare anche la funzionalità *Parser avanzato per codici a barre GS1*. Questa funzione fornisce una migliore implementazione del parser di codici a barre GS1. Aggiunge i seguenti miglioramenti:

- Segue l'algoritmo delle specifiche generali GS1 per l'analisi dei dati dei simboli e convalida che i dati nel simbolo siano validi secondo la specifica.
- Non richiede l'impostazione di un valore **Lunghezza massima dell'identificatore** e utilizza la corrispondenza del prefisso più lungo dagli identificatori dell'applicazione configurati.
- Ti consente di configurare più facilmente gli identificatori di applicazione decimali utilizzando la lettera *n* per abbinare qualsiasi numero. Ad esempio, puoi configurare un solo identificatore di applicazione (*310n*) invece di identificatori di applicazione separati (*3101*, *3102*, *3103* e così via).
- Risolve un problema per cui i dati codificati in modo errato vengono interpretati come dati di campo.
- Si presenta come una classe separata che può essere riutilizzata in altri contesti e consente di utilizzare un punto di estendibilità per manipolare i dati scansionati prima che i campi di flusso vengano compilati.

## <a name="set-up-global-gs1-options"></a><a name="set-gs1-options"></a>Impostare le opzioni globali GS1

La pagina dei **parametri di gestione del magazzino** fornisce alcune impostazioni che stabiliscono opzioni globali GS1.

Per impostare le opzioni globali GS1, segui questi passi.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Sulla FastTab **Codici a barre**, imposta i seguenti campi:

    - **Carattere FNC1**, **Carattere Datamatrix**, e **Carattere codice QR** – Specifica i caratteri che devono essere interpretati come prefisso per ogni tipo di codice a barre GS1.
    - **Separatore di gruppo** – Specifica il carattere che sostituisce il carattere separatore di gruppo ASCII.
    - **Lunghezza massima dell'identificatore** - Specifica il numero massimo di caratteri consentito per l'identificatore dell'applicazione. Questo campo non è obbligatorio se la funzionalità *Parser avanzato GS1* è attivata per il sistema.

> [!NOTE]
> I prefissi dicono al sistema che un codice a barre è codificato secondo lo standard GS1. Fino a tre prefissi **(carattere FNC1**, **carattere Datamatrix** e **carattere QR code**) possono essere usati simultaneamente e per vari scopi.

## <a name="gs1-application-identifiers"></a>Identificatori applicazione GS1

I formati GS1 non solo codificano i dati, ma permettono anche di utilizzare un elenco predefinito di identificatori di applicazione per definire il significato dei dati. I responsabili della logistica devono impostare l'elenco richiesto di identificatori di applicazioni e associare ciascuno di essi alle voci di menu appropriate del dispositivo mobile. Gli identificatori possono poi essere usati in tutti i magazzini come impostazione globale per il trasloco e l'imballaggio. Pertanto, tutte le etichette di spedizione avranno una forma unificata.

Il sistema utilizza i dati, specialmente gli identificatori di applicazione predefiniti, per stabilire le regole che devono essere applicate al pezzo di informazione scannerizzato pertinente.

Ogni identificatore di applicazione segnala al sistema che i caratteri successivi nel codice a barre scansionato devono essere considerati un blocco di informazioni criptate. L'impostazione degli identificatori dell'applicazione definisce come il sistema deve interpretare un codice a barre e salvarlo come valore nel sistema.

I responsabili della logistica possono usare identificatori di applicazioni internazionali standard e/o crearne di propri.

### <a name="load-the-standard-application-identifiers"></a>Caricare gli identificatori di applicazioni standard

Per iniziare rapidamente, puoi caricare una lista di identificatori di applicazioni internazionali comuni. Puoi poi estendere o modificare l'elenco in seguito, secondo le tue esigenze.

Per caricare gli identificatori di applicazioni standard, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> GS1 \> GS1 application identifier**.
1. Nel riquadro azioni, selezionare **Crea impostazione predefinita**.

> [!WARNING]
> Il comando **Crea impostazione predefinita** cancella tutti gli identificatori di applicazione attualmente definiti e li sostituisce con la lista standard. Tuttavia, dopo aver caricato la configurazione predefinita, è possibile personalizzare la lista come si desidera.

### <a name="set-up-custom-application-identifiers"></a>Impostare identificatori di applicazioni personalizzati

Se alcuni o tutti gli identificatori di applicazione che la vostra azienda usa differiscono dal set standard, potete creare i vostri codici da zero o personalizzare il set standard come volete.

Per impostare e personalizzare i vostri identificatori di applicazione GS1, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> GS1 \> GS1 application identifier**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Per creare un nuovo identificatore: Nel riquadro Azione, selezionare **Nuovo**.
    - Per modificare un identificatore esistente: Seleziona l'identificatore e poi, sul pannello delle azioni, seleziona **Modifica**.

1. Imposta i seguenti campi per l'identificatore nuovo o selezionato:

    - **Identificatore** dell'applicazione - Inserire il codice di identificazione dell'identificatore dell'applicazione. In genere, questo codice è un numero intero di due cifre, ma può essere più lungo. Per i valori decimali, l'ultima cifra indica il numero di cifre decimali. Per maggiori informazioni, vedi la descrizione della casella di controllo **Decimale** più avanti in questo elenco. Se la funzione *Parser avanzato per codici a barre GS1* è abilitata, è possibile creare un unico identificatore di applicazione per tutte le varianti di cifre decimali utilizzando la lettera *n* come ultimo carattere nell'identificatore dell'applicazione. Ad esempio, puoi configurare un solo identificatore di applicazione (*310n*) invece di un identificatore di applicazione separato per ogni numero delle posizioni decimali (*3101*, *3102*, *3103* e così via).
    - **Descrizione** - Inserisci una breve descrizione dell'identificatore.
    - **Lunghezza fissa** - Selezionate questa casella di controllo se i valori che vengono analizzati utilizzando questo identificatore di applicazione hanno un numero fisso di caratteri. Deselezionare questa casella di controllo se la lunghezza dei valori è variabile. In questo caso, devi indicare la fine del valore usando il carattere separatore di gruppo che hai specificato nella pagina dei **parametri di gestione del magazzino** .
    - **Lunghezza** - Inserisci il numero massimo di caratteri che possono apparire nei valori che vengono scansionati usando questo identificatore di applicazione. Se la casella di controllo **Lunghezza fissa** è selezionata, ci si aspetta esattamente questo numero di caratteri.
    - **Tipo** - Selezionate il tipo di valore che viene analizzato usando questo identificatore di applicazione *(numerico*, *alfanumerico* o *data*). Per ulteriori informazioni su come le date e i numeri sono rappresentati nei dati dei codici a barre, vedi la sezione [Date e numeri decimali](#dates-and-decimal-numbers).
    - **Decimale** - Seleziona questa casella di controllo se il valore include un punto decimale implicito. Se questa casella è selezionata, il sistema userà l'ultima cifra dell'identificatore dell'applicazione per determinare il numero di cifre decimali. Per ulteriori informazioni su come le date e i numeri sono rappresentati nei dati dei codici a barre, vedi la sezione [Date e numeri decimali](#dates-and-decimal-numbers).

> [!WARNING]
> Sebbene il sistema ti consentirà di impostare la casella di controllo **Lunghezza fissa** per qualsiasi identificatore di applicazione, deve essere utilizzato solo per il sottoinsieme di identificatori di applicazione che hanno una lunghezza predefinita in base alle Specifiche generali GS1. Il parser GS1 avanzato contiene già l'elenco di tutti gli identificatori di applicazione che hanno lunghezze predefinite.

> [!NOTE]
> Il valore **Separatore di gruppo** specificato nella pagina **Parametri di gestione del magazzino** è facoltativo se un valore seguito da un identificatore di applicazione ha una lunghezza fissa.

## <a name="establish-the-generic-gs1-setup"></a><a name="generic-gs1-setup"></a>Stabilire la configurazione generica GS1

La configurazione generica GS1 stabilisce un insieme di mappature comuni. Queste mappature corrispondono ad ogni campo di input rilevante nell'applicazione mobile all'identificatore dell'applicazione che controlla come i valori dai codici a barre scansionati devono essere interpretati e memorizzati in quel campo. Per impostazione predefinita, queste impostazioni si applicano a tutte le scansioni per tutte le voci di menu del dispositivo mobile. Tuttavia, possono essere sovrascritti per uno o più campi specifici da una politica GS1 che è assegnata a una voce di menu specifica.

L'impostazione generica di GS1 permette la scansione di un solo valore alla volta. Pertanto, se volete caricare più valori di campo da una singola scansione, dovete impostare una politica GS1 per le voci di menu pertinenti.

Per ulteriori informazioni sulle politiche GS1, vedere la sezione successiva.

### <a name="load-the-standard-generic-gs1-setup"></a>Caricare il setup generico standard GS1

La pagina di **impostazione generica GS1** permette di caricare un set standard di mappature tra i campi del dispositivo mobile e gli identificatori standard dell'applicazione che sono creati dall'impostazione predefinita.

Per stabilire il setup generico di GS1, vai a **Gestione magazzino \> Impostazione \> GS1 \> Impostazione generica GS1**. Poi selezionate **Crea impostazione predefinita** per assegnare automaticamente un identificatore di applicazione adatto ad ogni campo che è tipicamente usato dalle voci di menu dei dispositivi mobili.

> [!WARNING]
> Se esiste già un setup generico GS1, il comando **Crea impostazione predefinita** lo cancella completamente e carica il setup standard.

### <a name="customize-the-standard-generic-gs1-setup"></a>Personalizzare la configurazione standard generica GS1

Per personalizzare la configurazione generica di GS1, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> GS1 \> Impostazione generica GS1**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Per creare una nuova mappatura: Nel riquadro Azione, selezionare **Nuovo**.
    - Per modificare una mappatura esistente: Seleziona la mappatura e poi, sul pannello delle azioni, seleziona **Modifica**.

1. Imposta i seguenti campi per la mappatura nuova o selezionata:

    - **Campo** - Seleziona o inserisci il campo di input dell'applicazione mobile a cui il valore in entrata dovrebbe essere assegnato. Il valore non è il nome visualizzato dai lavoratori. Invece, è il nome della chiave che viene assegnato al campo nel codice sottostante. L'impostazione predefinita fornisce un insieme di campi che probabilmente saranno utili, e include nomi chiave intuitivi per ogni campo e funzionalità programmate corrispondenti. Tuttavia, potreste dover parlare con i vostri partner di sviluppo per trovare le selezioni corrette per la vostra implementazione.
    - **Identificatore** di applicazione - Selezionare l'identificatore di applicazione applicabile, come definito nella pagina degli **identificatori di applicazione GS1** . L'identificatore stabilisce come il codice a barre sarà interpretato e memorizzato come valore per il campo nominato. Dopo aver selezionato un identificatore di applicazione, il campo **Descrizione** mostra la descrizione di esso.

## <a name="set-up-gs1-policies-to-be-to-mobile-device-menu-items"></a><a name="policies-for-menus"></a>Impostare i criteri GS1 come voci di menu dei dispositivi mobili

Lo scopo dello standard GS1 è di permettere ai lavoratori di caricare diversi valori quando scansionano un solo codice a barre una sola volta. Per raggiungere questo scopo, i manager della logistica devono impostare le politiche GS1 che dicono al sistema come interpretare i codici a barre multi-valore. In seguito, è possibile assegnare criteri alle voci di menu dei dispositivi mobili per controllare come un codice a barre sarà interpretato quando i lavoratori lo scansionano mentre stanno usando una specifica voce di menu.

Se nessun criterio GS1 è assegnato a una voce di menu, il sistema può catturare solo un singolo valore. Questo valore viene applicato all'input dell'app mobile che viene selezionato quando il lavoratore fa la scansione, come specificato dalla configurazione generica GS1. Se un criterio GS1 è assegnato alla voce di menu, il sistema usa ancora la configurazione generica GS1 per mappare il primo valore del codice a barre al campo selezionato. Tuttavia, può poi catturare valori di campo aggiuntivi, come specificato dalla politica applicabile.

### <a name="load-the-standard-specific-gs1-policies"></a>Caricare le politiche GS1 specifiche dello standard

Per iniziare rapidamente, si può caricare un set di politiche GS1. Potete poi estendere o modificare le politiche in seguito, secondo le vostre esigenze.

Per caricare gli identificatori di applicazioni standard, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> GS1 \> Criteri GS1**.
1. Nel riquadro azioni, selezionare **Crea impostazione predefinita**.

> [!WARNING]
> Il comando **Crea impostazione predefinita** cancella tutte le politiche attualmente definite e le sostituisce con l'insieme standard di politiche. Tuttavia, dopo che la configurazione predefinita è stata caricata, è possibile personalizzare le politiche come si desidera.

### <a name="set-up-custom-specific-gs1-policies"></a>Impostare politiche GS1 specifiche e personalizzate

> [!WARNING]
> Alcuni criteri GS1 potrebbero non funzionare con tutti i flussi mobili che utilizzi. Quando configuri i criteri GS1 personalizzati, è necessario testare il flusso del dispositivo mobile utilizzando diverse informazioni che vengono scansionate in punti diversi del flusso. In questo modo, è possibile determinare se il flusso si comporta come previsto.

Per impostare e personalizzare le tue politiche GS1, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> GS1 \> Criteri GS1**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Per creare una nuova politica: Nel riquadro Azione, selezionare **Nuovo**.
    - Per modificare un criterio esistente: Seleziona il criterio nel pannello dell'elenco.

1. Nell'intestazione della politica nuova o selezionata, imposta i seguenti campi:

    - **Nome** della politica - Inserisci un nome per la politica.
    - **Descrizione** - Inserisci una breve descrizione della politica.

1. Nella FastTab sotto l'intestazione, mappate i nomi dei campi agli identificatori dell'applicazione come richiesto per la politica corrente. Usa i pulsanti sulla barra degli strumenti per aggiungere o rimuovere le righe secondo le tue esigenze. Per ciascuna riga, imposta i seguenti campi:

    - **Campo** - Seleziona o inserisci il campo di input dell'applicazione mobile a cui il valore in entrata dovrebbe essere assegnato. Il valore non è il nome visualizzato dai lavoratori. Invece, è il nome della chiave che viene assegnato al campo nel codice sottostante. L'impostazione predefinita fornisce un insieme di campi che probabilmente saranno utili, e include nomi chiave intuitivi per ogni campo e funzionalità programmate corrispondenti. Tuttavia, potreste dover parlare con i vostri partner di sviluppo per trovare le selezioni corrette per la vostra implementazione.
    - **Identificatore** di applicazione - Selezionare l'identificatore di applicazione applicabile, come definito nella pagina degli **identificatori di applicazione GS1** . L'identificatore stabilisce come il codice a barre sarà interpretato e memorizzato come valore per il campo nominato. Dopo aver selezionato un identificatore di applicazione, il campo **Descrizione** mostra la descrizione di esso.
    - **Ordinamento** - Ogni codice a barre multi-valore include una serie di identificatori di applicazione, ognuno dei quali è seguito da un valore. La politica GS1 applicabile identifica quale identificatore di applicazione è mappato ad ogni campo del database. Tuttavia, se un codice a barre usa lo stesso identificatore di applicazione più di una volta, il sistema usa l'ordine in cui gli identificatori di applicazione appaiono nel codice per mapparli ai campi. Per le righe che condividono un identificatore di applicazione con una o più altre righe, usa questo campo per stabilire l'ordine in cui le righe corrispondenti sono processate. La riga che ha il valore di ordinamento più basso sarà elaborata per prima.

> [!NOTE]
> Per i codici a barre che includono più di un identificatore di applicazione identico, *dovete* usare il campo **Ordinamento** per stabilire l'ordine dei campi.

## <a name="assign-gs1-policies-to-mobile-device-menu-items"></a>Assegnare i criteri GS1 alle voci di menu dei dispositivi mobili

Per impostazione predefinita, tutte le voci di menu dei dispositivi mobili forniscono campi di input dove i lavoratori possono scansionare un singolo valore, secondo la configurazione generica GS1. Se volete che i lavoratori siano in grado di scansionare più di un valore di campo in una singola scansione per qualsiasi voce di menu del dispositivo mobile, dovete assegnare una politica GS1 seguendo questi passi.

1. Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Creare o aprire una voce di menu.
1. Nella FastTab **Generale**, imposta il campo **Criteri GS1** sulla policy che si applica alla voce di menu.

## <a name="gs1-setup-example"></a>Esempio di impostazione GS1

Questo esempio si applica a un sistema in cui le opzioni GS1 sono impostate nel modo seguente:

- Nella pagina dei **parametri di gestione del magazzino** , vengono stabilite le seguenti impostazioni globali:

    - **Carattere FNC1:** *\]C1*
    - **Separatore di gruppo:** *\~*

- Nella pagina degli **identificatori di applicazione GS1** , i seguenti identificatori di applicazione sono rilevanti per questo esempio.

    | Identificatore applicazione | descrizione | Lunghezza fissa | Durata | Tipo | Decimali |
    |---|---|---|---|---|---|
    | 01 | GTIN | Selezionate | 14 | Numerico | Liquidata |
    | 10 | Numero batch | Liquidata | 20 | Alfanumerico | Liquidata |
    | 17 | Data di scadenza | Selezionate | 6 | Data | Liquidata |
    | 30 | Quantità di ricezione | Liquidata | 8 | Numerico | Liquidata |

- Nella pagina **di impostazione generica GS1** , le seguenti impostazioni per la politica generica GS1 sono rilevanti per questo esempio.

    | Campo | Identificatore applicazione | descrizione |
    |---|---|---|
    | ItemId | 01 | GTIN |

- Nella pagina dei **criteri GS1** , c'è un criterio in cui il campo del **nome del criterio** è impostato su *Acquisto in ricezione*. Questa polizza include le seguenti linee.

    | Campo | Identificatore applicazione | descrizione | Ordinamento |
    |---|---|---|---|
    | ExpDate | 17 | Data di scadenza | 0 |
    | InventBatchId | 10 | Numero batch | 0 |
    | Quantità | 30 | Quantità di ricezione | 0 |

- Nella pagina delle **voci di menu del dispositivo mobile** , c'è una voce di menu che si chiama *Acquisto di ricezione*. Il suo campo di **politica GS1** è impostato su *Acquisto in ricezione*.

Dopo che la merce per un ordine di acquisto arriva al magazzino, il lavoratore segue questi passi.

1. Sul dispositivo mobile, selezionare la voce di menu **Acquisto in ricezione** .
1. Inserisci il numero dell'ordine di acquisto.
1. Seleziona il campo **Articolo** ed esegui la scansione del seguente codice a barre: `]C10100000012345678~3030~10b1~17220215`.

A causa delle impostazioni stabilite per questo esempio, il sistema analizza il codice a barre scansionato nel modo seguente.

| Chiave di campo | ID domanda di lavoro | Valore | Nota |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Poiché il lavoratore ha scansionato il campo **Articolo** , il primo valore del codice a barre è mappato su quel campo. La mappatura è presa dal setup generico GS1. |
| Quantità | 30 | 30 | Poiché diversi valori di campo vengono catturati in una singola scansione, questa mappatura e tutte le altre mappature sono prese dalla politica GS1 che è assegnata alla voce del menu **Ricevimento acquisto** . Questo valore è la quantità che è stata ricevuta. |
| InventBatchId | 10 | b1 | Questo valore è l'ID del lotto. |
| ExpDate | 17 | 220215 | Il formato della data è YYMMDD. Pertanto, la data di scadenza è il 15 febbraio 2022. |

La ricevuta viene poi registrata e i valori del database rilevanti vengono inseriti dopo la singola scansione.
