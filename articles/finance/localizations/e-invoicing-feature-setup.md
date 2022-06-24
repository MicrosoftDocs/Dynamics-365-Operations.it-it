---
title: Utilizzare le configurazioni delle funzionalità
description: Questo articolo spiega come configurare le funzionalità di fatturazione elettronica.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 23466a53bb8ba597503aaa12d41395fc82b9f14e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904327"
---
# <a name="work-with-feature-setups"></a>Utilizzare le configurazioni delle funzionalità

[!include [banner](../includes/banner.md)]

Per configurare la generazione di file elettronici e altre fasi di elaborazione (ad esempio, file di firma digitale, invio al servizio Web governativo e ricezione di una risposta o archiviazione), configura la pipeline di elaborazione, le regole di applicabilità e le variabili per la funzionalità di fatturazione elettronica.

Le informazioni di configurazione sono combinate nel concetto *configurazione della funzionalità* e possono essere create, eliminate e modificate. Per le versioni complete delle funzionalità di fatturazione elettronica, è possibile visualizzare anche le informazioni.

È possibile creare tutti gli elementi di configurazione delle funzionalità necessari per definire diversi scenari per la generazione, l'elaborazione e la ricezione di file elettronici. Sebbene questi elementi di configurazione della funzionalità dispongano di azioni di elaborazione e condizioni di esecuzione indipendenti, vengono creati come parte di un'unica funzionalità di fatturazione elettronica ed ereditano il ciclo di vita e il processo di distribuzione.

## <a name="add-a-feature-setup"></a>Aggiungere una configurazione della funzionalità

1. Accedi al tuo account Regulatory Configuration Service (RCS).
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
3. Nella pagina **Funzionalità di fatturazione elettronica**, seleziona la versione della funzionalità di fatturazione elettronica con stato **Bozza**.
4. Nella scheda **Configurazioni**, seleziona **Aggiungi**.
5. Nella finestra di dialogo a discesa **Crea configurazione funzionalità**, nel gruppo di campi **Nuovo**, seleziona una delle seguenti opzioni.
 
    - **Configurazione personalizzata** – Crea una nuova configurazione di funzionalità con canali vuoti, un elenco di pipeline di elaborazione vuoto, una sezione vuota per le regole di applicabilità e un insieme predefinito di variabili, a seconda del tipo di configurazione.
    - **Dalla configurazione delle funzioni** – Crea una copia di un'altra configurazione di funzionalità nell'ambito della funzionalità di fatturazione elettronica corrente.

6. Se hai selezionato l'opzione **Configurazione personalizzata** nell'ultimo passaggio, immetti un nome e una descrizione dell'elemento di configurazione della funzione, quindi, nel gruppo di campi **Tipo di configurazione**, seleziona una delle seguenti opzioni:

    - **Pipeline di elaborazione** – Seleziona questa opzione per generare ed elaborare documenti elettronici in uscita. Per questo tipo di configurazione, il sistema crea un elenco di pipeline di elaborazione vuoto, una sezione vuota per le regole di applicabilità e un insieme predefinito di variabili. Non potrai lavorare con i canali per i documenti elettronici in entrata.
    - **Canale dati** – Seleziona questa opzione per configurare il processo di ricezione dei documenti elettronici in entrata da uno dei canali definiti e di passarli direttamente a Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management senza azioni aggiuntive. Per questo tipo di configurazione, il sistema crea un elenco di parametri predefinito per i canali di dati, una sezione vuota per le regole di applicabilità e un insieme di variabili predefinite. Non potrai aggiungere alcuna azione nella pipeline di elaborazione.
    - **Canale dati e pipeline di elaborazione** – Questo tipo di configurazione è simile al tipo di configurazione **Canale dati**. Tuttavia, prima che un documento elettronico in entrata venga passato a Finance o Supply Chain Management, è possibile configurare azioni aggiuntive nella pipeline di elaborazione.

7. Se hai selezionato l'opzione **Canale dati** o **Canale dati e pipeline di elaborazione** nell'ultimo passaggio, nel campo **Seleziona canale dati** è necessario selezionare il canale con cui eseguire l'integrazione.
8. Selezionare **Crea**.

Dopo aver creato una configurazione di funzionalità, è possibile selezionare **Modifica** per configurarla.

## <a name="edit-a-feature-setup"></a>Modificare una configurazione della funzionalità

A seconda del tipo di configurazione della funzionalità, è possibile configurare il processo di generazione di file elettronici in uscita e di invio a canali esterni oppure di ricezione di documenti in entrata e di invio all'applicazione Finance o Supply Chain Management.

### <a name="data-channel"></a>Canale dati

Un *canale dati* prende il file elettronico e lo elabora o lo passa direttamente a Finance o Supply Chain Management. Questa opzione non è disponibile per le configurazioni delle funzionalità di tipo **Pipeline di elaborazione**.

Per configurare un canale dati, immetti il nome del canale. Quindi definisci i parametri, in base al tipo di canale selezionato. L'identificatore del canale dati deve fare riferimento alla variabile creata specificamente per identificare il canale dati. Sarà utilizzato come riferimento in Finance o Supply Chain Management.

Nella scheda **Filtro allegati**, è consigliabile definire una serie di filtri per ottenere file specifici dal canale. È possibile creare più righe se si prevede che i file abbiano estensioni di nomi file diverse o se i file devono essere elaborati in modo diverso a seconda del nome file. Ecco i parametri principali:

- **Nome** – Immettere il nome del file a cui il sistema farà riferimento durante l'elaborazione. Nelle applicazioni Finance e Supply Chain Management, potrai vedere i file nel registro di invio.
- **Filtro** – Definire il filtro per selezionare i file.
- **Facoltativo** – Se questa casella di controllo è deselezionata, il file è richiesto. In questo caso, il sistema mostrerà un messaggio di errore se i canali non contengono file che corrispondono al filtro. Questo parametro è applicabile ai messaggi e-mail.

Se il canale è una cassetta postale e un messaggio e-mail in entrata contiene diversi allegati, è possibile configurare regole per definire come il servizio deve gestire gli allegati. Il servizio può considerare ogni allegato come una fattura elettronica separata, oppure può trattare un allegato come fattura principale e tutti gli altri allegati come integrazioni.

### <a name="processing-pipeline"></a>Pipeline di elaborazione

Una *pipeline di elaborazione* è un insieme di *azioni* che vengono eseguite in sequenza finché non vengono completate con successo. È possibile utilizzare una pipeline di elaborazione per impostare il processo per la generazione di file elettronici e l'esecuzione di altri passaggi (ad esempio, firma digitale dei file, invio a servizi Web esterni e analisi della risposta e ricezione ed elaborazione di documenti in entrata).

L'elenco delle azioni è predefinito. Puoi usare i pulsanti **Nuovo** ed **Elimina** per specificare la combinazione di azioni che definisce logicamente il processo richiesto per l'invio o la ricezione dei documenti.

L'ordine delle azioni è importante. È possibile regolare l'ordine tramite i pulsanti **Su** e **Giù**.

Ogni azione ha una serie di parametri che puoi configurare o regolare. L'insieme specifico di parametri dipende dal tipo di azione.

- **Azione** – Selezionare il tipo di azione.
- **Nome azione** - Immettere il nome dell'azione. Questo nome apparirà nei registri di invio e nei messaggi nelle applicazioni Finance e Supply Chain Management.
- **Descrizione** – Fornire maggiori dettagli sullo scopo dell'azione nel processo.
- **Abilita nuovo tentativo** – Se si seleziona questa casella di controllo, è possibile selezionare un'azione nel campo **Riprova azione** e configurare parametri aggiuntivi nella scheda **Riprova parametri**.

    La funzionalità Riprova consente di configurare il comportamento del servizio se non è possibile eseguire un'azione specifica. Ad esempio, se il servizio Web esterno a cui stai tentando di connetterti non risponde, puoi specificare quante volte il sistema deve ritentare la connessione, a quale intervallo e da quale azione nella pipeline di elaborazione.

- **Esporta risultati** – È possibile selezionare questa casella di controllo per *una* azione nella pipeline di elaborazione. Il file elettronico prodotto dall'azione nell'applicazione Finance o Supply Chain Management può quindi essere esportato dalla pagina **Registro di invio documenti elettronici**.

### <a name="applicability-rules"></a>Regole di applicabilità

Le *regole di applicabilità* sono clausole configurabili per fornire un contesto per l'esecuzione delle funzionalità di fatturazione elettronica tramite il set di funzionalità Fatturazione elettronica.
I documenti aziendali inviati da Finance o Supply Chain Management alla fatturazione elettronica non contengono un riferimento esplicito che consente al set di funzionalità Fatturazione elettronica impostata per chiamare una particolare funzionalità di fatturazione elettronica per elaborare l'invio. Tuttavia, se correttamente configurato, il documento aziendale contiene gli elementi necessari che consentono alla fatturazione elettronica di stabilire quale versione della funzionalità di fatturazione elettronica e della pipeline di elaborazione deve essere selezionata ed eseguita.

Le regole di applicabilità consentono al servizio di fatturazione elettronica di trovare le caratteristiche esatte di fatturazione elettronica che devono essere utilizzate per elaborare l'invio. Per trovare le funzionalità corrette, i campi **Contesto** del documento commerciale inviato vengono confrontati con le clausole delle regole di applicabilità.

Puoi utilizzare le regole di applicabilità nei seguenti modi:

- Seleziona **Nuovo** per aggiungere una nuova clausola a una serie di regole di applicabilità.
- Seleziona **Elimina** per eliminare una clausola.
- Seleziona diversi record e usa il pulsante **Raggruppa** o **Separa** per creare una combinazione di elementi o istruzioni logiche. Ad esempio, seleziona le righe che desideri raggruppare, quindi seleziona **Raggruppa clausola**. Quando le clausole sono raggruppate, una nuova colonna viene aggiunta alla griglia. Questa colonna specifica l'operatore logico per la clausola raggruppata. Attualmente sono supportati i seguenti tipi di operatori:

    - Equal
    - Not equal
    - Maggiore di/Minore di
    - Maggiore di o uguale a/Minore di o uguale a
    - Contiene
    - Inizia con

    > [!NOTE]
    > Quando si separa una clausola, inizia sempre dal livello di raggruppamento più interno.

### <a name="variables"></a>Variabili

Le *variabili* offrono maggiore flessibilità quando si configura una pipeline di elaborazione e il flusso di dati tra le azioni. È possibile fare riferimento a una variabile in alcuni parametri di azione per memorizzare temporaneamente dati o file elettronici. Alcune variabili vengono utilizzate per trasferire i dati tra le applicazioni Finance o Supply Chain Management e il servizio di fatturazione elettronica.

Il sistema crea alcune variabili per impostazione predefinita. Ad esempio, la variabile **BusinessDocumentDataModel** contiene dati aziendali in una struttura JavaScript Object Notation (JSON) che arriva nella chiamata dall'applicazione connessa durante il processo di invio.

Sono disponibili i seguenti tipi di variabili:

- **Costante** – Un contenitore per l'archiviazione di dati temporanei utilizzati nell'elaborazione delle azioni della pipeline.
- **Dal client**: il contenuto della variabile viene acquisito dal client Dynamics 365 durante l'esecuzione del processo di invio.
- **Al client**: il contenuto della variabile viene reso disponibile per l'importazione dal client Dynamics 365 durante l'esecuzione del processo di invio.
- **Tipo di dati** – Selezionare il tipo di dati delle informazioni memorizzate nella variabile.

### <a name="parameters"></a>Parametri

L'opzione **Disabilita riduzione dei dati aziendali** viene utilizzata per ottimizzare la struttura del payload dei dati aziendali che proviene dall'applicazione Finance o Supply Chain Management durante l'invio di documenti elettronici. L'ottimizzazione aiuta a ridurre i dati che entrano nel servizio di fatturazione elettronica per un'ulteriore trasformazione nel file elettronico richiesto. Il valore predefinito è **No**.

- **Sì** – Finance o Supply Chain Management invieranno un file JSON della struttura **Modello di fattura** o **Modello fiscale** (per il Brasile) definita nel modulo **Creazione di report elettronici**. Tutti gli elementi del modello sono riempiti con dati aziendali sul lato dell'applicazione, indipendentemente dalla struttura del file elettronico finale. I modelli in genere contengono più dati aziendali di quelli richiesti dalla struttura del file di destinazione e può essere necessario più tempo per generare questi dati nell'applicazione. Un valore **Sì** per questa opzione è richiesto nel raro caso in cui si desidera generare file di output diverso in una funzione di fatturazione elettronica e configurazione della funzione. Un valore **Sì** è utile quando si risolvono i problemi relativi ai propri scenari, la struttura dei file elettronici e la completezza dei dati aziendali.
- **No** – Finance o Supply Chain Management effettueranno la prima chiamata al servizio senza dati aziendali. Lo scopo di questa chiamata è ottenere informazioni sulla configurazione dei report elettronici (ER) che verrà utilizzata per la trasformazione dei file elettronici nella pipeline di elaborazione. Queste informazioni vengono restituite all'applicazione, che le utilizza per determinare il sottoinsieme di dati aziendali da includere nel file JSON della struttura **Modello di fattura** o **Modello fiscale** (per il Brasile). Un valore **No** per questa opzione consente di ridurre il volume dei dati aziendali che l'applicazione invia al servizio, poiché l'applicazione può inviare solo i dati aziendali necessari per generare correttamente un file elettronico.

### <a name="validate-a-feature-setup"></a>Convalidare una configurazione della funzionalità

Puoi eseguire la convalida per verificare la coerenza dell'intera configurazione. Ad esempio, se un parametro obbligatorio per un'azione è stato lasciato vuoto, la convalida rileva questa incoerenza e viene visualizzato un messaggio di avviso.

- Nella pagina **Configurazione versione funzionalità**, nel riquadro azioni seleziona **Convalida**.

## <a name="delete-a-feature-setup"></a>Eliminare una configurazione della funzionalità

1. Nella pagina **Funzionalità di fatturazione elettronica**, seleziona la versione della funzionalità di fatturazione elettronica con stato **Bozza**.
2. Nella scheda **Configurazioni**, selezionare **Elimina**.
3. Nella finestra del messaggio che appare, seleziona **Sì** per confermare che vuoi eliminare la configurazione della funzionalità.
