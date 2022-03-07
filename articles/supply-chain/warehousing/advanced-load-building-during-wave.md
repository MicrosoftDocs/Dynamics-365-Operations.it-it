---
title: Allestimento del carico avanzato durante un'ondata
description: Questo argomento fornisce informazioni sull'allestimento del carico avanzato durante un'ondata, che assegna automaticamente le spedizioni alle ondate esistenti durante l'esecuzione dell'ondata. Pertanto, è possibile creare carichi significativi che rappresentano i camion senza dover utilizzare il workbench di pianificazione del carico.
author: mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod,WHSWaveTemplateTable,WHSLoadMixGroup,WHSLoadBuildTemplate, WHSWaveTableListPage, TMSLoadBuildTemplateApply, TMSLoadBuildTemplates, TMSLoadBuildTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 08e44b4e37f28ec91eeb8e53930de5133607bd66
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574739"
---
# <a name="advanced-load-building-during-wave"></a>Allestimento del carico avanzato durante un'ondata

[!include [banner](../includes/banner.md)]

L'allestimento del carico avanzato durante un'ondata assegna automaticamente le spedizioni alle ondate esistenti durante l'esecuzione dell'ondata. Pertanto, è possibile creare carichi significativi che rappresentano i camion senza dover utilizzare il workbench di pianificazione del carico. Questa funzionalità è utile per le aziende che desiderano utilizzare il concetto di carichi per tracciare e pianificare la spedizione di merci in un camion/rimorchio, ma che non desiderano creare manualmente tali carichi ogni giorno.

Durante l'elaborazione delle ondate, il sistema di solito crea un nuovo carico per ogni spedizione a cui non è assegnato alcun carico. Tuttavia, quando viene attivato l'allestimento del carico avanzato durante un'ondata, il sistema assegna ogni spedizione non assegnata a un carico esistente (se esiste un carico appropriato) e i nuovi carichi vengono creati solo quando sono richiesti. L'Allestimento del carico avanzato durante un'ondata crea automaticamente i nuovi carichi, in base a criteri definiti dall'utente.

Per utilizzare la funzionalità, è necessario configurare il sistema nel modo seguente:

- Crea *modelli d'ondata* che includono il nuovo metodo **buildLoads**. Questo metodo rende disponibile l'allestimento del carico avanzato durante un'ondata per le ondate che utilizzano tali modelli.
- Configura *modelli di allestimento del carico*, ognuno dei quali è collegato a un modello e metodo di ondata specifici. I modelli di allestimento del carico controllano a quale carico (esistente o nuovo) vengono aggiunte le righe di carico in ondata. È possibile combinare o separare le spedizioni, in base a criteri quali modello di carico, attrezzature e altri valori di campo sulla riga di carico.
- Definisci i *gruppi combinati di carico* per controllare quali elementi devono e non devono essere combinati su un singolo carico. Specifica inoltre se la restrizione deve produrre un avviso o un errore e se la restrizione volumetrica del modello di carico deve essere valutata.

## <a name="turn-on-advanced-wave-load-building-in-your-system"></a>Attiva l'allestimento del carico avanzato durante un'ondata nel tuo sistema

Prima di poter utilizzare l'allestimento del carico avanzato durante un'ondata, è necessario attivare due funzioni nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato di queste funzionalità e attivarle se sono obbligatorie. Nell'area di lavoro **Gestione funzionalità**, le funzionalità sono elencate nel modo seguente:

- Funzionalità di allestimento del carico durante l'ondata

    - **Modulo:** *Gestione Magazzino*
    - **Nome della funzionalità:** *Funzionalità di allestimento del carico durante l'ondata*

- Codice passaggio ondata a livello di organizzazione:

    - **Modulo:** *Gestione Magazzino*
    - **Nome funzionalità:** *Codice passaggio ondata a livello di organizzazione*

### <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per utilizzate questa demo utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

È inoltre possibile utilizzare questa demo come indicazioni per l'utilizzo di questa funzione quando si lavora su un sistema di produzione. Tuttavia, in questo caso, è necessario sostituire i propri valori e potrebbero mancare alcuni tipi di record richiesti forniti dai dati demo standard.

### <a name="make-sure-that-the-scenario-setup-includes-enough-available-inventory"></a>Verificare che la configurazione dello scenario includa sufficienti scorte disponibili

Se stai lavorando con dati dimostrativi **USMF**, devi prima assicurarti che il tuo sistema sia configurato in modo che ci siano scorte sufficienti in ogni ubicazione rilevante. Per questa demo, ci si aspetta che le seguenti scorte siano disponibile in magazzino *62*:

- **Articolo A0001:** 10 pezzi
- **Articolo A0002:** 10 pezzi
- **Articolo M9200:** 10 unità

L'articolo **M9200** deve essere aggiunto al magazzino. Completa le procedure nelle seguenti sottosezioni per aggiungere le scorte degli articoli.

#### <a name="create-a-new-license-plate-id"></a>Creare un nuovo ID targa

1. Vai a **Gestione magazzino** \> **Impostazione** \> **Magazzino** \> **Targhe**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella nuova riga, nel campo **Targa**, inserisci *LP6203*.
1. Selezionare **Salva**.

#### <a name="create-a-standard-cost-for-item-m9200-in-site-6"></a>Creare un costo standard per l'articolo M9200 nel sito 6

1. Selezionare **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**.
1. Cerca su **M9200**.
1. Seleziona la riga per l'articolo, quindi, nel riquadro azioni, nella scheda **Gestisci costi** e nel gruppo **Impostare**, seleziona **Prezzo articolo**.
1. Nella pagina **Prezzo articolo**, seleziona la scheda **Prezzi in sospeso**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tipo di costo:** *Costo pianificato*
    - **Tipo di prezzo:** *Costo*
    - **Versione:** *10*
    - **Sito:** *6*
    - **Prezzo:** *1,60*

1. Nel riquadro azioni selezionare **Salva**.
1. Nel riquadro azioni seleziona **Attiva prezzo/i in sospeso**.
1. Seleziona la scheda **Prezzi attivi** per verificare che il nuovo prezzo di costo per il sito *6* sia stato aggiunto.

#### <a name="create-inventory-in-warehouse-62"></a>Creare scorte nel magazzino 62

1. Vai a **Gestione articoli** \> **Inserimenti nel giornale di registrazione** \> **Articoli** \> **Rettifica magazzino**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea giornale di registrazione magazzino**, nella scheda Dettaglio **Panoramica**, nel campo **Magazzino**, inserisci *62*. Accetta i valori predefiniti in tutti gli altri campi.
1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Viene aperta la pagina **Rettifica magazzino**. Nella Scheda dettaglio **Righe giornale di registrazione** seleziona **Nuova** per aggiungere una riga.
1. Nella nuova riga, imposta i seguenti valori. Accetta i valori predefiniti in tutti gli altri campi.

    - **Numero articolo:** *M9200*
    - **Ubicazione:** *bulk-003*
    - **Quantità:** cambiare il valore in *10*.

1. Nel riquadro azioni selezionare **Salva**.
1. Nel riquadro azioni seleziona **Convalida** per verificare la presenza di errori.
1. Nella finestra di dialogo **Verifica giornale di registrazione**, seleziona **OK** per avviare il controllo. Riceverai un messaggio al termine della verifica.
1. Nel riquadro azioni seleziona **Registra** per effettuare il commit della rettifica di magazzino.
1. Nella finestra di dialogo **Registra giornale**, seleziona **OK** per avviare la registrazione. Riceverai un messaggio al termine della registrazione.

## <a name="set-up-advanced-wave-load-building"></a>Configurare l'allestimento del carico avanzato durante un'ondata

### <a name="regenerate-wave-process-methods"></a>Rigenerare i metodi di elaborazione ondata

Potrebbe essere necessario rigenerare i metodi di elaborazione ondata per rendere disponibile il metodo di allestimento del carico (**buildLoads**).

1. Vai a **Gestione magazzino** \> **Impostazione** \> **Ondate** \> **Metodi di elaborazione ondata**.
2. Verifica che **buildLoads** sia presente nell'elenco. Se non è presente, seleziona **Rigenera metodi** nel riquadro azioni per aggiungerlo.

### <a name="set-up-wave-templates"></a>Impostare modelli di ondata

Per sfruttare l'allestimento del carico avanzato durante un'ondata, è necessario includere il metodo **buildLoads** in relativo [modello d'ondata](tasks/configure-wave-processing.md).

1. Vai a **Gestione magazzino** \> **Impostazione** \> **Ondate** \> **Modelli ondata**.
1. Seleziona un modello di ondata.

    Se stai lavorando con dati dimostrativi **USMF**, seleziona il modello **62 Spedizione predefinita**.

1. Nel riquadro azioni seleziona **Modifica** per mettere la pagina in modalità modifica.
1. Nella scheda Dettaglio **Metodi**, nella griglia **Metodi rimanenti**, seleziona il metodo **buildLoads**.
1. Seleziona il pulsante freccia DESTRA per spostare il metodo **buildLoads** nella griglia **Metodi selezionati**.
1. Per assegnare un valore **buildLoads** per il metodo **buildLoads**, è innanzitutto necessario creare un codice nella pagina **Codici passaggio ondata**. Puoi usare qualsiasi valore tu voglia, ma assicurati di prenderne nota, perché ne avrai bisogno in seguito. Attieniti alla procedura seguente per creare il codice **WSC2112**.

    1. Nella riga per il metodo **buildLoads**, fai clic con il tasto destro del mouse sulla freccia GIÙ nel campo **Codice passaggio ondata**, quindi seleziona **Visualizza dettagli**.
    1. Nella pagina **Codici passaggio ondata**, nel riquadro azioni, seleziona **Nuovo**.
    1. Nel campo **Codice passaggio ondata**, immetti *WSC2112*.
    1. Nel campo **Descrizione passaggio ondata**, immetti *WSC2112*.
    1. Nel campo **Tipo di passaggio ondata**, seleziona *Allestimento del carico*.

1. Selezionare **Salva**, quindi chiudere la pagina.
1. Nella riga per il metodo **buildLoads**, nel campo **Codice passaggio ondata**, seleziona il codice che hai appena creato (**WSC2112**).
1. Nel riquadro azioni selezionare **Salva**.

> [!NOTE]
> I codici passaggio ondata sono codici che gli utenti possono impostare e utilizzare per collegare istanze specifiche di metodi ondata a modelli corrispondenti. I modelli includono modelli per rifornimento, containerizzazione, stampa di etichette, creazione di carichi e ordinamento.
>
> Quando non vengono utilizzati i codici passaggio ondata, gli utenti devono inserire il testo libero per fare riferimento a un modello specifico dall'istanza del metodo ondata. Il testo libero è soggetto a errori, poiché gli utenti devono assicurarsi che il testo del passaggio ondata che aggiungono per un metodo di passaggio ondata specifico in un modello ondata corrisponda esattamente al testo del passaggio ondata nel modello di destinazione.
>
> I codici passaggio ondata per uno specifico tipo di passaggio ondata vengono impostati in una pagina separata. Per ogni istanza del metodo del passaggio ondata in un modello di ondata che richiede un codice passaggio ondata, il codice passaggio ondata deve essere selezionato in un elenco a discesa. La selezione in un elenco a discesa sostituisce l'immissione di testo libero e aiuta a ridurre il rischio e l'impatto dell'errore umano. I codici di impostazione vengono utilizzati per collegare un metodo del passaggio ondata in un modello ondata a un modello di destinazione per il metodo.

### <a name="set-up-load-mix-groups"></a>Impostare gruppi combinati di carico

I gruppi combinati di carico stabiliscono regole per i tipi di articoli che possono essere combinati su un singolo carico. È possibile impostare tutti i gruppi combinati di carico necessari. Tuttavia, per utilizzare l'allestimento del carico avanzato durante un'ondata, è necessario averne almeno uno a disposizione. Segui questa procedura per creare un gruppo combinato di carico.

1. Vai a **Gestione magazzino** \> **Impostazione** \> **Carico** \> **Gruppi combinati di carico**.
1. Nel riquadro azioni seleziona **Nuova** per creare un gruppo di carico.
1. Nel campo **ID gruppo combinato di carico**, immetti un nome per il nuovo gruppo.

    Se stai lavorando con dati dimostrativi **USMF**, imposta i seguenti valori:

    - **ID gruppo combinato di carico:** *TV*
    - **Descrizione:** *TV*

1. Nel riquadro azioni seleziona **Salva** per rendere la scheda Dettaglio **Criteri gruppo combinato di carico** disponibile.
1. Nella Scheda dettaglio **Criteri gruppo combinato di carico**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i valori desiderati in ciascun campo. Questi valori determinano i gruppi di articoli considerati per il carico combinato.

    Se stai lavorando con dati dimostrativi **USMF**, seleziona *TV e video* nel campo **Gruppo di articoli**.

1. Nel riquadro azioni seleziona **Salva** per rendere la scheda Dettaglio **Vincoli gruppo combinato di carico** disponibile.
1. Nella Scheda dettaglio **Vincoli gruppo combinato di carico**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i valori desiderati in ciascun campo.

    Se stai lavorando con dati dimostrativi **USMF**, imposta i seguenti valori:

    - **Gruppo di articoli:** *CarAudio*
    - **Azione di allestimento del carico:** *Limita* (Questo valore eviterà agli oggetti che appartengono al gruppo di articoli **CarAudio** di appartenere allo stesso carico degli articoli che appartengono al gruppo di articoli **TV e video**).

1. Continua a lavorare con le regole fino a quando non sono stati aggiunti tutti i criteri e i vincoli richiesti per il gruppo combinato di carico.

Se stai lavorando con dati dimostrativi **USMF**, ora hai terminato questa configurazione.

### <a name="set-up-load-build-templates"></a>Impostare modelli di allestimento del carico

È possibile impostare tutti i modelli di allestimento del carico necessari. Tuttavia, per utilizzare l'allestimento del carico avanzato durante un'ondata, è necessario averne almeno uno a disposizione. Per creare un modello di allestimento del carico, attieniti alla procedura seguente.

1. Vai a **Gestione magazzino** \> **Impostazione** \> **Carico** \> **Modelli di allestimento del carico ondata**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori.

    | Campo | Descrizione | Valore nei dati dimostrativi USMF |
    |---|---|---|
    | Numero progressivo | L'ordine in cui verrà valutato il modello. | *1* |
    | Nome modello di allestimento del carico | Immetti l'identificatore univoco del modello di allestimento del carico. È consigliabile immettere il nome del modello creato o aggiornato in precedenza in questa configurazione. | *62 Spedizione predefinita* |
    | Codice del passaggio ondata | Immetti il codice di passaggio ondata da utilizzare per collegare il modello a un metodo di ondata. È consiglibile immettere il codice selezionato per il metodo **buildLoads** quando imposti il modello di ondata in precedenza in questa configurazione. | *WSC2112* |
    | ID modello carico | Seleziona il modello di carico da utilizzare quando si creano nuovi carichi e da confrontare quando si esegue l'assegnazione a carichi esistenti. Il modello di carico definisce il peso e il volume massimi consentiti per l'intero carico. | *Modello di caricamento stnd* |
    | Attrezzature | L'attrezzatura da confrontare quando si esegue l'assegnazione a carichi esistenti e da immettere su nuovi carichi creati. | Lascia vuoto il campo. |
    | ID gruppo misto di carico | Seleziona il gruppo combinato di carico da utilizzare se l'articolo è consentito nel carico. Il gruppo combinato stabilisce regole per i tipi di articoli che possono essere combinati su un singolo carico. È consigliabile selezionare uno dei gruppi combinati creati in precedenza in questa configurazione. | *TV* |
    | Utilizza carichi aperti | Scegli se è necessario aggiungere carichi aperti esistenti. Di seguito vengono illustrate le opzioni disponibili.<ul><li>**Nessuno**: non aggiungere carichi aperti a carichi esistenti.</li><li>**Tutti**: aggiungi carichi aperti a tutti i carichi esistenti validi per la riga.</li><li>**Assegnato**: aggiungi carichi aperti al carico assegnato all'ondata.</li></ul> | *Alcune* |
    | Crea carichi | Specifica se è necessario creare nuovi carichi se nessun carico esistente soddisfa i criteri. | Selezionato (= *Sì*) |
    | Consenti divisione riga spedizione | Specifica se una singiola riga di carico può essere essere suddivisa tra più carichi se la riga intera supera la capacità massima del livello di carico. | Deselezionata (= *No*) |
    | Convalida metriche volume | Specifica se l'allestimento del carico deve controllare il peso e il volume in modo che ogni riga del carico venga aggiunta per garantire che i limiti volumetrici del modello di carico vengano rispettati. | Deselezionata (= *No*) |

1. Nel riquadro azioni seleziona **Salva** per rendere l'opzione **Modifica query** disponibile.
1. Nel riquadro azioni, seleziona **Modificare query** per aprire una finestra di dialogo per la modifica della query.
1. Nella finestra di dialogo, nella scheda **Ordinamento**, seleziona **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, definisci le regole di ordinamento che desideri utilizzare. Ad esempio, imposta i seguenti valori per ordinare i risultati della ricerca in ordine crescente in base al numero dell'ordine:

    - **Tabella:** *Carica dettagli*
    - **Tabella derivata:** *Carica dettagli*
    - **Campo:** *Numero d'ordine*
    - **Direzione di ricerca:** *Crescente*

1. Seleziona **OK** per salvare le modifiche e chiudere la finestra di dialogo.
1. Nella Scheda dettagli **Suddividi per**, imposta le regole per controllare la suddivisione dei carichi. In genere, è possibile suddividere i campi personalizzati che sono stati estesi sulla riga di carico, ad esempio **Ciclo**, **Presentazione** o **Esecuzione**. Ad esempio, per creare un carico per numero di ordine, seleziona la casella di controllo **Suddividi per** per la riga con i seguenti valori:

    - **Nome tabella di riferimento:** *Dettagli carico*
    - **Nome campo di riferimento:** *Numero d'ordine*

## <a name="scenario"></a>Scenario

Questo scenario mostra in che modo le impostazioni descritte in precedenza in questo argomento influiscono sulle operazioni di magazzino durante l'elaborazione di un ordine cliente. Questo scenario utilizza i dati dimostrativi **USMF** insieme ad altri valori dimostrativi forniti in tali istruzioni di installazione.

### <a name="create-sales-orders"></a>Creare ordini cliente

1. Andare a **Vendite e marketing** \> **Ordini cliente** \> **Tutti gli ordini cliente**.
1. Nel riquadro azioni, scegli **Nuovo** per aprire la finestra di dialogo **Crea ordine cliente**.
1. Nella finestra di dialogo, imposta i seguenti valori:

    - Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-007*.
    - Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona *62*.

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Dovrebbe includere una nuova riga vuota nella griglia della Scheda dettaglio **Righe ordine cliente**. Su questa nuova riga, imposta il campo **Codice articolo** su *A0001* e il campo **Quantità** su *1*.
1. Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, nel riquadro azioni, seleziona **Prenota lotto**.
1. Seleziona il pulsante **Chiudi** (**X**) nell'angolo in alto a destra della pagina per tornare all'ordine cliente.
1. Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**. Il sistema crea una spedizione e la aggiunge a un nuovo carico, poiché nessun carico esistente contiene righe di carico con questo numero di ordine.

    Ricevi messaggi informativi che indicano il lavoro, l'ondata e la spedizione creati per questo ordine.

1. Per confermare i dettagli di carico, spedizione e lavoro sulla riga di vendita, seleziona la riga, quindi sul menu **Magazzino** sopra la griglia, seleziona **Dettagli carico**, **Dettagli spedizione** o **Dettagli lavoro**.
1. Nell'ordine cliente appena creato, nella Scheda dettaglio **Righe ordine cliente**, seleziona **Aggiungi riga** per aggiungere un'altra riga.
1. Su questa nuova riga, imposta il campo **Codice articolo** su *A0002* e il campo **Quantità** su *1*.
1. Ripetere le righe da 6 a 9 per prenotare la riga e rilasciarla nel magazzino. Il sistema crea una **nuova** spedizione per la riga aggiunta. Tuttavia, poiché stai utilizzando l'allestimento avanzato del carico di ondata, il sistema aggiunge quella spedizione e la riga di carico all'ondata esistente. Se non stavi utilizzando l'allestimento avanzato del carico d'ondata, il sistema avrebbe creato un nuovo carico per la spedizione.
1. Nell'ordine cliente appena creato, nella Scheda dettaglio **Righe ordine cliente**, seleziona **Aggiungi riga** per aggiungere un'altra riga.
1. Su questa nuova riga, imposta il campo **Codice articolo** su *M9200* e il campo **Quantità** su *1*.
1. Ripetere le righe da 6 a 9 per prenotare la riga e rilasciarla nel magazzino. Come in precedenza, il sistema crea una **nuova** spedizione per la riga aggiunta. Tuttavia, poiché l'articolo proviene dal gruppo di articoli **CarAudio**, **non riesce a superare i vincoli impostati per il gruppo combinato di carico**. Pertanto, viene **aggiunto a un nuovo carico**. Se non avessi specificato un gruppo combinato di carico nel modello di allestimento del carico, questa spedizione sarebbe stata aggiunta al primo carico.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]