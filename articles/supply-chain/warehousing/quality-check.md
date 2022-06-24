---
title: Controllo qualità
description: In questo articolo vengono fornite informazioni sulla funzionalità di controllo di qualità. Questa funzionalità consente ai magazzinieri di effettuare rapidi controlli a campione sulla qualità mentre ricevono articoli nell'area della banchina di entrata.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: ceb01205edc269690fda306bc90f465dbccc563b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855059"
---
# <a name="quality-check"></a>Controllo qualità

[!include [banner](../includes/banner.md)]

La funzionalità *Controllo qualità* consente ai magazzinieri di effettuare rapidi controlli a campione sulla qualità mentre ricevono articoli nell'area della banchina di entrata. Questi controlli a campione sono utili quando gli operatori ispezionano l'imballaggio o altre parti facilmente riconoscibili di un articolo. La funzionalità guida gli operatori durante un il rapido esame per vedere se qualcosa è chiaramente difettoso o danneggiato prima di immagazzinare le scorte nell'ubicazione di stoccaggio.

Questa funzionalità è un'alternativa al processo di controllo di qualità standard. Offre maggiore flessibilità e elaborazione più rapida.

Quando si utilizza questa funzione, l'arrivo e il controllo di qualità si svolgono nel modo seguente:

1. Quando arriva una spedizione, un addetto al magazzino registra l'arrivo. Lo stesso addetto esegue inoltre la scansione di una targa per registrare l'ubicazione.
1. L'operatore effettua un rapido controllo di qualità e registra il risultato (positivo o negativo) per quella targa.
1. Si verifica una delle seguenti azioni:

    - Se il controllo di qualità viene superato, la targa viene accettata e indirizzata normalmente verso un'ubicazione di ricezione.
    - Se il controllo di qualità non viene superato, la targa viene rifiutata e il lavoro di stoccaggio esistente per la stessa viene reindirizzato verso un'ubicazione alternativa per un'ulteriore ispezione. Viene creato un nuovo ordine di controllo qualità. Per visualizzare l'ordine di controllo qualità creato dal controllo di qualità non superato, andare a **Gestione inventario \> Attività periodiche \> Gestione della qualità \> Ordini di controllo qualità**.

Questo processo può anche essere configurato in modo tale che tutte le targhe acquisite vengano immediatamente trasferite nell'ubicazione di controllo della qualità.

## <a name="turn-the-quality-check-feature-on-or-off"></a>Attivare o disattivare la funzionalità Controllo qualità

Per utilizzare le funzionalità descritte in questo articolo, è necessario attivare la funzionalità *Controllo qualità* per il sistema. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.25, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Controllo qualità* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-the-feature-for-the-example-scenario"></a>Configurare la funzionalità per lo scenario di esempio

Questa sezione fornisce linee guida e un esempio che mostra come configurare la funzionalità *Controllo qualità* e preparare i dati di esempio per lo scenario di esempio illustrato più avanti in questo articolo.

### <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per elaborare lo [scenario di esempio](#example-scenario) utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

### <a name="quality-check-template"></a><a name="quality-template"></a>Modello di controllo qualità

Il modello di controllo della qualità definisce le regole per eseguire controlli a campion rapidi per la qualità al momento della ricezione.

1. Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modello di controllo di qualità**.
1. Seleziona **Nuovo** per aggiungere un modello alla griglia.
1. Definire il nuovo modello impostando i seguenti valori:

    - **Nome modello di controllo qualità:** *Controllo banchina*

        Immettere un nome che identifichi i criteri applicati per questo modello.

    - **Criteri di accettazione:** *Richiedi conferma all'utente*

        Specificare se agli utenti deve essere richiesto di accettare o rifiutare la qualità dell'inventario mentre elaborano il lavoro o se la qualità deve essere automaticamente rifiutata. Le opzioni disponibili sono *Rifiuto automatico* e *Richiedi conferma all'utente*.

    - **Criteri di elaborazione controllo qualità:** *Crea ordine di controllo qualità*

        Selezionare i criteri da utilizzare quando la qualità dell'inventario viene rifiutata. Di seguito vengono illustrate le opzioni disponibili.

        - *Crea solo lavoro*: creare il lavoro solo per facilitare la movimentazione delle scorte.
        - *Crea ordine di controllo qualità*: creare un ordine di controllo qualità per facilitare i test di qualità.

    - **Gruppo di test:** *Sistemi di chiusura*

        Specificare il gruppo di test che deve essere utilizzato nell'ordine di controllo qualità creato. I gruppi di test vengono configurati nel modulo **Gestione inventario**.

        Lasciare l'opzione **Test distruttivo** disattivata per il gruppo di test. Questa opzione definisce se il campione verrà distrutto come parte dei test del gruppo di test. Se viene utilizzato un test distruttivo, il sistema genera una transazione di magazzino quando un ordine di controllo qualità viene creato per un articolo. La nuova operazione di magazzino stima la riduzione delle scorte per la quantità da testare. La riduzione delle scorte si verifica quanto l'ordine di controllo qualità viene completato attraverso la fase di convalida. L'operazione di magazzino viene identificata come un ordine di controllo qualità.

### <a name="work-class--quality-check"></a><a name="work-class"></a>Classe di lavoro: controllo di qualità

Le classi di lavoro vengono utilizzate per indirizzare e/o limitare il tipo di righe ordine di lavoro che gli addetti al magazzino possono elaborare in un dispositivo mobile.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.
1. Selezionare **Nuovo** per creare una classe di lavoro.
1. Nell'intestazione, imposta i seguenti valori:

    - **ID classe lavoro:** *Controllo di qualità*

        Immettere un nome che identifichi la classe di lavoro.

    - **Descrizione:** *Controllo di qualità*

        Immettere una breve descrizione che indichi a cosa serve la classe di lavoro.

    - **Tipo di ordine di lavoro:** *Qualità nel controllo qualità*

        Selezionare il tipo di ordine di lavoro creato dalla classe di lavoro. Quando si imposta il lavoro di controllo qualità, selezionare sempre *Qualità nel controllo qualità*.

1. Nella Scheda dettaglio **Tipi di ubicazione inseriti validi**, lasciare vuoto il campo **Tipo di ubicazione**.

    Se si seleziona un tipo di ubicazione, si limitano le ubicazioni in cui gli articoli possono essere stoccati dopo che sono stati prelevati. Questo campo viene utilizzato quando una direttiva ubicazione prova a risolvere l'ubicazione o quando un addetto al magazzino specifica manualmente l'ubicazione per la voce di menu del dispositivo mobile.

Per altre informazioni sulle classi di lavoro e su come crearle, vedere [Creare una classe di lavoro](tasks/create-work-class.md).

### <a name="work-template"></a>Modello di lavoro

Modelli di lavoro consente di definire le operazioni di lavoro che devono essere eseguite nel magazzino. In genere, le operazioni di lavoro sono costituite da una coppia di azioni: un lavoratore di magazzino preleva le scorte disponibili da un'ubicazione quindi colloca le scorte prelevate in un'altra ubicazione. Un modello di lavoro per il controllo di qualità definisce le operazioni di lavoro per l'esecuzione dei controlli di qualità.

#### <a name="purchase-orders"></a>Ordine fornitore

1. Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Nell'intestazione, Impostare il campo **Tipo ordine di lavoro** su *Ordini fornitore*.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Selezionare un modello di lavoro che dovrebbe includere una fase di controllo della qualità. Nella sezione **Panoramica**, nel campo **Modello di lavoro**, selezionare *Ricevuta ordine d'acquisto 51*.
1. Nella sezione **Dettagli del modello di lavoro**, notare che la griglia ha due righe esistenti: una per *Preleva* e una per *Inserisci*.
1. Nella sezione **Dettagli del modello di lavoro**, selezionare **Nuovo** per aggiungere una riga per il controllo di qualità alla griglia. Si noti che il campo **Numero di riga** per la nuova riga è impostato su *3*.
1. Nella nuova riga, imposta i seguenti valori. Accettare i valori predefiniti per i campi rimanenti.

    - **Tipo di lavoro:** *Controllo qualità*
    - **ID classe lavoro:** *Acquisto*
    - **Nome modello di controllo qualità:** *Controllo banchina*

        Selezionare l'ID univoco per la classe di lavoro. Utilizzare questo valore per configurare le voci di menu nel dispositivo mobile e i tipi di lavoro che le voci di menu possono elaborare.

1. Nel riquadro azioni selezionare **Salva** per salvare il lavoro eseguito finora.

    Si riceverà un messaggio informativo che indica "Non valido: Il controllo di qualità deve essere eseguito direttamente dopo un prelievo". Pertanto, è necessario modificare il valore **Numero di riga** per la riga appena aggiunta.

1. Seguire questi passaggi per modificare il valore di **Numero di riga** per la nuova riga:

    1. Nella sezione **Dettagli del modello di lavoro**, selezionare la riga in cui il campo **Tipo di lavoro** è impostato su *Controllo qualità*.
    2. Selezionare il pulsante **Sposta su** o **Sposta giù** per spostare la riga *Controllo qualità* in modo che sia dopo la riga *Preleva*.

1. Nel riquadro azioni selezionare **Salva**.

#### <a name="quality-in-quality-check"></a>Qualità nel controllo qualità

Quindi, creare un modello di lavoro per il controllo di qualità.

1. Nell'intestazione della pagina **Modelli di lavoro**, modifica il valore del campo **Tipo di ordine di lavoro** su *Qualità nel controllo qualità*.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia nella sezione **Panoramica**.
1. Nella nuova riga, imposta i seguenti valori:

    - **Modello di lavoro:** *Controllo qualità 51*

        Immettere un nome per il modello.

    - **Descrizione modello di lavoro:** *Controllo qualità 51*

1. Nel riquadro azioni, selezionare **Salva** per rendere disponibile la sezione **Dettagli modello di lavoro**.
1. Mentre il nuovo modello è ancora selezionato nella sezione **Panoramica**, selezionare **Nuovo** nella sezione **Dettagli del modello di lavoro** per aggiungere una riga alla griglia in quel punto.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tipo di lavoro:** *Prelevare*
    - **ID classe lavoro:** *Controllo di qualità*

        Selezionare il nome della [classe di lavoro](#work-class) creata in precedenza per il lavoro di controllo della qualità.

1. Nella sezione **Dettagli del modello di lavoro**, selezionare ancora **Nuovo** per aggiungere un'altra riga.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tipo di lavoro:** *Inserire*
    - **ID classe lavoro:** *Controllo di qualità*

        Selezionare il nome della [classe di lavoro](#work-class) creata in precedenza per il lavoro di controllo della qualità.

1. Nel riquadro azioni selezionare **Salva**.

Per ulteriori informazioni sui modelli di lavoro, vedere [Controllo del lavoro di magazzino con modelli di lavoro e direttive di ubicazione](control-warehouse-location-directives.md).

### <a name="location-directive--quality-failures"></a>Direttiva ubicazione: errori di qualità

Le direttive ubicazione sono regole che aiutano a identificare le ubicazioni di prelievo e stoccaggio per il movimento scorte. Ad esempio, in una transazione dell'ordine cliente, la direttiva ubicazione determina il punto di prelievo e il punto di stoccaggio degli articoli. È necessario configurare una regola della direttiva ubicazione per definire come verranno gestiti i controlli di qualità non superati.

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel riquadro sinistro, impostare il campo **Tipo di ordine di lavoro** su *Ordini fornitore* per lavorare con le direttive ubicazioni di quel tipo.
1. Nel riquadro azioni selezionare **Nuovo** per creare una direttiva ubicazione per i controlli di qualità.
1. Nell'intestazione, imposta i seguenti valori:

    - **Numero sequenza:** accetta il valore predefinito.
    - **Nome:** *51 a qualità*

1. Nella Scheda dettaglio **Direttive ubicazione**, imposta i seguenti valori. Accettare i valori predefiniti per i campi rimanenti.

    - **Tipo di lavoro:** *Inserire*
    - **Sito:** *5*
    - **Magazzino:** *51*

1. Nel riquadro azioni, selezionare **Salva** per salvare la direttiva e rendere disponibile la Scheda dettaglio **Righe**.
1. Nella Scheda dettaglio **Righe**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori. Accettare i valori predefiniti per i campi rimanenti.

    - **Da quantità:** *1*
    - **A quantità:** *1000000*

1. Nel riquadro azioni, selezionare **Salva** per salvare la nuova riga e rendere disponibile la Scheda dettaglio **Azioni direttiva ubicazione**.
1. Mentre la nuova riga è ancora selezionata nella Scheda dettaglio **Righe**, selezionare **Nuova** nella Scheda dettaglio **Azioni direttiva ubicazione** per aggiungere una riga alla griglia in quel punto, in modo da poter configurare un'azione per la riga.
1. Nella nuova riga, impostare il campo **Nome** su *Qualità*. Accettare i valori predefiniti per i campi rimanenti.
1. Nel riquadro azioni, selezionare **Salva** per rendere disponibile il pulsante **Modifica query** nella Scheda dettaglio **Azioni direttiva ubicazione**.
1. Mentre la riga appena aggiunta è ancora selezionata nella Scheda dettaglio **Azioni direttiva ubicazione**, selezionare **Modifica query** per aprire una finestra di dialogo in cui è possibile modificare la query per l'azione.
1. Nella scheda **Intervallo**, selezionare **Aggiungi** per aggiungere una riga alla query.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** *Ubicazioni*
    - **Tabella derivata:** *Ubicazioni*
    - **Campo:** *Ubicazione*
    - **Criteri:** *QMS*

    L'ubicazione *QMS* è un'ubicazione di magazzino per la qualità.

1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Ora è necessario modificare la sequenza delle direttive di ubicazione dell'ordine fornitore per il magazzino *51*. Salvare la nuova direttiva ubicazione *51 alla qualità*, aggiornare la pagina e selezionare la direttiva ubicazione nell'elenco. Quindi utilizzare i pulsanti **Sposta su** e **Sposta giù** nel riquadro azioni per inserire la direttiva ubicazione per il magazzino *51* nel seguente ordine. (Prima di selezionare **Sposta su** o **Sposta giù**, è necessario selezionare una direttiva ubicazione nell'elenco).

    1. Da 51 a qualità
    2. 51 PO Diretto
    3. 51 QMS

### <a name="mobile-device-menu-items"></a>Voci di menu del dispositivo mobile

Configurare una voce di menu in modo che i dispositivi mobili possano eseguire la funzione **Controllo qualità**.

#### <a name="purchase-putaway"></a>Stoccaggio di acquisto

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nell'elenco, selezionare la voce d menu **Stoccaggio acquisto**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella sezione **Classi di lavoro**, selezionare **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **ID classe lavoro:** *Controllo di qualità*

        Immettere il nome della [classe di lavoro](#work-class) creata in precedenza per il lavoro di controllo della qualità.

    - **Tipo di ordine di lavoro:** *Qualità nel controllo qualità*

1. Nel riquadro azioni selezionare **Salva**.

#### <a name="purchase-order-line-receiving"></a>Ricevimento riga ordine acquisto

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione, imposta i seguenti valori:

    - **Nome voce di menu:** *Ricezione riga PO*
    - **Titolo:** *Ricezione riga PO*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *No*

1. Nella Scheda dettaglio **Generale**, impostare i seguenti valori. Accettare i valori predefiniti per i campi rimanenti.

    - **Processo di creazione lavoro:** *Ricevimento e stoccaggio riga ordine acquisto*
    - **Genera targa:** *Sì*
    - **Modello di lavoro:** *51 PO ricevuta*

1. Nel riquadro azioni selezionare **Salva**.

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Aggiungere la voce di menu a un menu per dispositivo mobile

1. Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Nel riquadro sinistro, selezionare il menu **In entrata**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella colonna **Menu e voci di menu disponibili**, selezionare la nuova voce di menu **Ricezione riga PO**.
1. Selezionare il pulsante freccia DESTRA per spostare **Ricezione riga PO** nella colonna **Struttura menu**.
1. Nella colonna **Struttura menu**, selezionare **Ricezione riga PO**, quindi selezionare il pulsante freccia SU o freccia GIÙ per spostare la voce di menu nella posizione desiderata nel menu del dispositivo mobile.
1. Nel riquadro azioni selezionare **Salva**.

## <a name="example-scenario"></a><a name="example-scenario"></a>Scenario di esempio

Dopo aver reso disponibili tutti i dati di esempio precedentemente descritti e averli configurati, è possibile utilizzare questo scenario per provare la funzionalità *Controllo qualità*. I valori mostrati in questo scenario presuppongono che si stia lavorando con i dati dimostrativi standard, che sia stata selezionata la persona giuridica **USMF** e che sono stati preparati i record di esempio descritti in precedenza in questo articolo. Questo scenario serve anche come esempio che mostra come la funzionalità può essere utilizzata in uno scenario di produzione.

### <a name="create-a-purchase-order"></a>Creare un ordine fornitore

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:

    - **Conto fornitore:** *104*
    - **Magazzino:** *51*

1. Scegliere **OK** per chiudere la finestra di dialogo e aprire il nuovo ordine fornitore.
1. Nella Scheda dettaglio **Righe ordine fornitore**, la griglia contiene una nuova riga vuota. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** *M9203*
    - **Quantità:** *3*
    - **Unità:** *PALLET*

1. Nel riquadro azioni selezionare **Salva**.

### <a name="process-quality-check-receiving"></a>Elaborare la ricezione del controllo di qualità

Dopo che l'ordine fornitore è stato creato, può essere ricevuto utilizzando la voce di menu **Ricezione riga PO** e la funzionalità di *Controllo di qualità*.

#### <a name="receive-pallet-1"></a>Ricevere il pallet 1

1. Accedi all'app per dispositivi mobili Gestione magazzino come utente nel magazzino *51*. (Immettere *51* come ID utente e *1* come password).
1. Passare a **In entrata \> Ricezione riga PO**.
1. Nel campo **PONUM**, immettere il numero dell'ordine fornitore.
1. Confermare il numero dell'ordine fornitore.
1. Nel campo **LINENUM**, immettere il numero della riga dell'ordine fornitore che viene ricevuta. Poiché l'ordine include solo una riga in questo scenario, sarà necessario immettere *1* nel campo **LINENUM** per ogni passaggio di ricezione.
1. Confermare il numero della riga.
1. Nel campo **QUANTITÀ** immettere la quantità da ricevere. Poiché l'ordine fornutore è per tre pallet (*PL*) in questo scenario e sono presenti tre passaggi di ricezione, sarà necessario immettere *1* nel campo **QUANTITÀ** per ogni passaggio di ricezione.
1. Confermare la quantità.

    La pagina **Controllo qualità** visualizzata non ha campi di immissione. Ha solo il pulsante di conferma (segno di spunta) in basso e il pulsante Menu (**≡**) in cima. (Il pulsante Menu viene talvolta definito hamburger o pulsante hamburger). Per accelerare il processo di controllo qualità, quando il pallet supera il controllo qualità, l'utente conferma la pagina **Controllo qualità**.

    ![Pagina Controllo qualità.](media/quality-check.png "Pagina Controllo qualità")

1. Selezionare il pulsante di conferma per superare il controllo di qualità per il pallet 1 dalla riga 1.

    La pagina **Ordini fornitore: inserimento** che appare mostra i dettagli del lavoro di inserimento:

    - **UBICAZIONE:** l'ubicazione determinata dal sistema

        Questa ubicazione è l'ubicazione di stoccaggio designata per la ricezione dell'ordine fornitore.

    - **TARGA:** l'ID targa generato dal sistema
    - **Articolo:** *M9203*
    - **Quantità:** *1 PL: 100 ea*

    Viene anche mostrata la descrizione dell'articolo.

1. Confermare il lavoro di stoccaggio.

    Nella pagina **Attività** per la ricezione della riga ordine fornitore, viene visualizzato il messaggio "Lavoro completato". Il campo **LINENUM** è disponibile in modo da poter iniziare a ricevere il pallet successivo.

#### <a name="receive-pallet-2"></a>Ricevere il pallet 2

Per questo scenario, il pallet 2 verrà rifiutato.

1. Nel campo **LINENUM**, immettere *1* e confermare il numero di riga.
1. Il campo **QUANTITÀ** è ora disponibile. Immettere *1* e confermare la quantità.

    Viene visualizzata la pagina **Controllo qualità**. Per questa ricezione, il pallet verrà rifiutato per la qualità e verrà inserito nell'ubicazione di qualità *QMS*.

1. Selezionare il pulsante Menu (**≡**) nella parte superiore della pagina, quindi dal menu selezionare **Rifiuta**.
1. Nella pagina **Attività** che appare, immettere **QMS** come ubicazione *Inserisci* a cui inviare il pallet per ulteriori ispezioni.

    La pagina **Qualità nel controllo qualità: inserimento** che appare mostra i dettagli del lavoro di inserimento:

    - **UBICAZIONE:** *QMS*

        Questa ubicazione è l'ubicazione di stoccaggio designata per la ricezione della qualità rifiutata.

    - **TARGA:** l'ID targa generato dal sistema
    - **Articolo:** *M9203*
    - **Quantità:** *1 PL: 100 ea*

    Viene anche mostrata la descrizione dell'articolo.

1. Confermare il lavoro di stoccaggio.

    Nella pagina **Attività** per la ricezione della riga ordine fornitore, viene visualizzato il messaggio "Lavoro completato". Il campo **LINENUM** è disponibile in modo da poter iniziare a ricevere il pallet successivo.

Le operazioni di controllo di qualità e creazione di un ordine di controllo qualità per il pallet rifiutato sono state completate. Per visualizzare l'ordine di controllo qualità creato, andare a **Gestione inventario \> Attività periodiche \> Gestione della qualità \> Ordini di controllo qualità**.

Ora è possibile elaborare il test dell'ordine di controllo qualità. Il test di qualità non viene illustrato in questo articolo.

Per ulteriori informazioni sulla gestione della qualità, vedere [Panoramica della gestione della qualità](../inventory/enable-quality-management.md).

#### <a name="receive-pallet-3"></a>Ricevere il pallet 3

Per questo scenario, il pallet 3 verrà accettato.

1. Nel campo **LINENUM**, immettere *1* e confermare il numero di riga.
1. Il campo **QUANTITÀ** è ora disponibile. Immettere *1* e confermare la quantità.

    Viene visualizzata la pagina **Controllo qualità**. Per questa ricezione, il pallet verrà accettato per la qualità e verrà inserito in un'ubicazione di stoccaggio in blocco.

1. Selezionare il pulsante di conferma per superare il controllo di qualità.

    La pagina **Ordini fornitore: inserimento** che appare mostra i dettagli del lavoro di inserimento:

    - **UBICAZIONE:** l'ubicazione determinata dal sistema

        Questa ubicazione è l'ubicazione di stoccaggio designata per la ricezione dell'ordine fornitore.

    - **TARGA:** l'ID targa generato dal sistema
    - **Articolo:** *M9203*
    - **Quantità:** *1 PL: 100 ea*

    Viene anche mostrata la descrizione dell'articolo.

1. Confermare il lavoro di stoccaggio.

    Nella pagina **Attività** per la ricezione della riga ordine fornitore, viene visualizzato il messaggio "Lavoro completato". Il campo **LINENUM** è disponibile in modo da poter iniziare a ricevere il pallet successivo.

1. Selezionare il pulsante Menu (**≡**) nella parte superiore della pagina, quindi dal menu selezionare **Annulla** per tornare al menu.

Ora è possibile chiudere l'app per dispositivi mobili.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]