---
title: Configurazioni visive dell'interfaccia utente POS
description: Di seguito vengono fornite informazioni sui layout dello schermo per le esperienze di Dynamics 365 Commerce POS.
author: boycezhu
manager: annbe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 203d12956825286b77a107bb9fd91c451ecfd1e6
ms.sourcegitcommit: dc3deca942864c4a8354096183c9e1b9b88992f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "5032935"
---
# <a name="pos-user-interface-visual-configurations"></a>Configurazioni visive dell'interfaccia utente POS

[!include [banner](includes/banner.md)]


L'interfaccia utente (UI) del punto vendita (POS) di Microsoft Dynamics 365 Commerce può essere configurata utilizzando una combinazione di profili visivi e di layout dello schermo assegnati a negozi, registratori di cassa e/o utenti. Questo argomento fornisce informazioni su tali opzioni di configurazione.

La figura di seguito mostra le relazioni tra le varie entità che costituiscono gli aspetti configurabili dell'interfaccia utente POS.

![Entità layout schermo POS](../commerce/media/POS-layout-configuration-entities-diagram.png)

## <a name="visual-profile"></a>Profilo visivo

I profili visivi vengono assegnati ai registratori di cassa e specificano gli elementi visivi specifici del registratore e condivisi tra gli utenti. Ogni utente che accede al registro vede lo stesso tema, layout, colori e immagini.

![Schermo di benvenuto di POS con tema chiaro](../commerce/media/POS-Welcome-Screen-with-Light-theme.png)

![Schermo di transazione di POS con tema scuro](../commerce/media/POS-Transaction-Screen-with-Dark-theme.png)

- **Numero di profilo**: il numero di profilo costituisce l'identificatore univoco per il profilo visivo.
- **Descrizione**: è possibile specificare un nome significativo che contribuirà a identificare il profilo corretto per la specifica situazione.
- **Tema** – È possibile scegliere tra temi **Chiari** e **Scuri** dell'applicazione. Il tema ha effetto sui colori di sfondo sul carattere e dell'applicazione.
- **Colore accento**: il colore accento viene utilizzato nel POS per distinguere o evidenziare specifici elementi visivi ad esempio riquadri, pulsanti di comando e collegamenti ipertestuali. Questi elementi sono in genere elementi su cui è possibile eseguire azioni.
- **Colore dell'intestazione** - Consente di configurare il colore dell'intestazione di pagina per soddisfare i requisiti di branding del rivenditore.
- **Combinazione di tipi di carattere** - È possibile selezionare tra combinazioni di caratteri **Standard** e **Grande**. La combinazione di tipi di carattere, influisce sulla dimensione del carattere in tutta l'applicazione. La selezione predefinita è **Standard**.
- **Mostra sempre le etichette della barra dell'applicazione** - Quando questa opzione è attivata, il testo dell'etichetta è sempre visibile sotto i pulsanti della barra dell'applicazione.
- **Layout** - È possibile selezionare tra i layout **Centrato** e **Destra**. Il layout influenza l'allineamento della casella di accesso nella schermata di accesso. La selezione predefinita è **Centrato**.
- **Mostra data/ora** - Quando questa opzione è attivata, la data e l'ora correnti vengono visualizzate nell'intestazione POS e nella schermata di accesso.
- **Tastiera** - È possibile selezionare tra **Valore predefinito impostato su tastiera del sistema operativo** e **Mostra tastierino numerico** per specificare la tastiera predefinita utilizzata per l'input nella schermata di accesso. Il tastierino numerico è una tastiera virtuale utilizzata principalmente per i dispositivi basati sul tocco. La selezione predefinita è **Valore predefinito impostato su tastiera del sistema operativo**.
- **Immagine di logo** - È possibile specificare un'immagine del logo che viene visualizzata nella schermata di accesso. Si consiglia di utilizzare un'immagine con uno sfondo trasparente. La dimensione del file deve essere ridotta al minimo, poiché il comportamento e le prestazioni dell'applicazione possono essere influenzati quando i file di grandi dimensioni vengono archiviati e caricati.
- **Sfondo di accesso**: è possibile specificare un'immagine di sfondo per la schermata di accesso. La dimensione del file delle immagini di sfondo deve essere ridotta al minimo.
- **Sfondo**: è possibile specificare un'immagine di sfondo da utilizzare al posto del colore del tema in tutta l'applicazione. Per quanto riguarda le immagini di sfondo per la schermata di accesso, la dimensione del file deve essere ridotta al minimo.

> [!NOTE]
> Il layout di **Destra** e la visualizzazione data/ora non si applicano alla schermata di accesso in visualizzazione compatta.

Devi eseguire il processo di pianificazione distribuzione **1090** (**Registri**) per sincronizzare le ultime configurazioni del profilo visivo con il database del canale.

## <a name="screen-layouts"></a>Layout schermo

Le configurazioni del layout dello schermo determinano le azioni, il contenuto e il posizionamento dei controlli dell'interfaccia utente sulla schermata POS **Benvenuti** e **Transazione** .

![Vista layout schermo POS](../commerce/media/POS-Screen-Layout-View.png)

- **Schermata di benvenuto**: nella maggior parte dei casi, la schermata di benvenuto corrisponde alla pagina che gli utenti visualizzano al momento dell'accesso al POS. La schermata di benvenuto può essere costituita da un'immagine del marchio e da griglie dei pulsanti che consentono di accedere alle operazioni del POS. In genere, le operazioni non specifiche alla transazione corrente vengono posizionate in questa schermata.

    ![Schermata di benvenuto POS](../commerce/media/POS-Welcome-Screen.png)

- **Schermata transazione**: la schermata **transazione** è lo schermo principale nel POS per l'elaborazione di transazioni di vendita e ordini. Il contenuto e il layout sono configurati mediante la progettazione layout dello schermo.

    ![Schermata transazione POS](../commerce/media/POS-Transaction-Screen.png)

- **Schermata di avvio predefinita**: alcuni rivenditori preferiscono che il cassiere passi direttamente alla schermata delle **transazioni** dopo l'accesso. La **schermata di inizio predefinita** consente di specificare lo schermo predefinito che viene visualizzato dopo l'accesso per ogni layout dello schermo.

### <a name="assignment"></a>Assegnazione

I layout dello schermo possono essere assegnati a livello di punto vendita, registratore di cassa o utente. L'assegnazione dell'utente ha la priorità sulle assegnazioni dei punti vendita e del registratore di cassa e l'assegnazione del registratore ha la priorità sull'assegnazione del punto vendita. In uno scenario semplice in cui tutti gli utenti utilizzano lo stesso layout indipendentemente dal registratore o dal ruolo, il layout dello schermo può essere impostato solo al livello di punto vendita. Negli scenari in cui specifici registratori di cassa o utenti specifici richiedono i layout specializzati, questi possono essere assegnati.

A seconda del livello assegnato ai layout dello schermo, è necessario eseguire i processi di pianificazione distribuzione **1070** (**Configurazione del canale**), **1090** (**Registri**) e/o **1060** (**Personale**) per sincronizzare le ultime configurazioni del layout dello schermo con il database del canale.

### <a name="layout-sizes"></a>Dimensioni layout

La maggior parte degli aspetti dell'interfaccia utente POS è responsiva e il layout viene ridimensionato e regolato automaticamente in base alle dimensioni e all'orientamento della schermata. Tuttavia, la schermata **Transazione** di POS deve essere configurata per ogni risoluzione dello schermo prevista.

All'avvio, l'applicazione POS sceglierà automaticamente la dimensione del layout più vicina configurata per il dispositivo. Un layout dello schermo può inoltre contenere le configurazioni per modalità orizzontali e verticali e sia per dispositivi a schermo intero che compatti. Di conseguenza, un utente può essere assegnato a un singolo layout schermo utilizzabile con diverse dimensioni e fattori modulo nel punto vendita.

![Dimensioni layout POS](../commerce/media/POS-Screen-Layout-Sizes.png)

- **Nome** - È possibile immettere un nome significativo per identificare le dimensioni dello schermo.
- **Tipo di layout** - Retail POS può visualizzare la propria interfaccia utente in diversi modi per fornire la migliore esperienza utente su un dato dispositivo.

    - **POS moderno - Completo**: il layout completo in genere è più adatto per schermi di maggiori dimensioni, ad esempio di monitor di PC o tablet. Gli utenti possono selezionare gli elementi dell'interfaccia utente da includere, specificare la dimensione e la posizione di quegli elementi e configurarne le proprietà dettagliate. Il layout completo supporta entrambe le configurazioni orizzontale e verticale.
    - **POS moderno - Compatto**: il layout compatto in genere è migliore per telefoni o tablet di piccole dimensioni. Le opzioni di progettazione sono limitate per i dispositivi compatti. Gli utenti possono configurare le colonne e i campi per il riquadro ricevuta e il pannello totali.

- **Larghezza/altezza** - Questi valori effettivi rappresentano le dimensioni della schermata, in pixel, previste per il layout. Tenere presente che alcuni sistemi operativi utilizzano la scalabilità per le visualizzazioni ad alta definizione.

> [!TIP]
> È possibile ottenere la dimensione del layout necessaria per uno schermo di Retail POS vedendo la risoluzione nell'app. Avviare il POS e passare a **Impostazioni \> Informazioni sulla sessione**. In POS verrà visualizzato il layout dello schermo attualmente caricato, la dimensione del layout e la risoluzione della finestra nell'app.

![Pagina delle informazioni della sessione POS che visualizza il layout dello schermo attualmente caricato, la dimensione del layout e la risoluzione della finestra nell'app](../commerce/media/POS-Session-Information.png)

### <a name="button-grids"></a>Griglie dei pulsanti

Per ogni dimensione di layout in un layout di schermata, è possibile configurare e assegnare griglie di pulsanti per la schermata di benvenuto del POS e **Transazione**. Le griglie dei pulsanti per la schermata di benvenuto vengono automaticamente disposte da sinistra a destra, dal numero più basso (schermata di benvenuto 1) al numero più alto.

Nei layout POS completi il posizionamento delle griglie dei pulsanti è specificato nel layout dello schermo.

Nei layout POS compatti le griglie dei pulsanti sono automaticamente disposte dall'alto verso il basso, dal numero più basso (schermata Transazione 1) al numero più alto. È possibile accedervi dal menu **Azioni**.

![Griglie dei pulsanti layout compatti](../commerce/media/Compact-View-Button-Grids.png)

> [!NOTE]
> Le dimensioni dei pulsanti nella finestra di progettazione verranno ridimensionate per adattarsi alle dimensioni della finestra, pertanto potrebbero non riflettere accuratamente i pulsanti effettivi visualizzati in POS. Per simulare al meglio il layout della griglia dei pulsanti, adatta le finestre di progettazione alle stesse dimensioni del POS.

### <a name="images"></a>Immagini

Per ciascuna dimensione del layout in un layout dello schermo, è possibile specificare le immagini da includere nell'interfaccia utente POS. Per i layout POS completi, è possibile specificare una singola immagine per la schermata di benvenuto. Questa immagine appare come il primo elemento dell'interfaccia utente a sinistra. Nella schermata **Transazione**, le immagini possono essere utilizzate come immagini di schede o come logo. Nei layout compatti di POS non vengono utilizzate queste immagini.

### <a name="screen-layout-designer"></a>Progettazione layout schermo

Lo screen layout designer permette di configurare vari aspetti della schermata **Transazione** di POS per ogni dimensione di layout, sia in modalità verticale che orizzontale, e per i layout Compatti e Completi. La progettazione del layout dello schermo utilizza la tecnologia di distribuzione ClickOnce per scaricare, installare e avviare la versione più recente dell'applicazione ogni volta che gli utenti vi accedono. Assicurarsi di verificare i requisiti del browser di ClickOnce. Alcuni browser, ad esempio Google Chrome, richiedono estensioni.

> [!IMPORTANT]
> È necessario configurare un layout di schermo per ogni dimensione di layout definita e utilizzata dal POS.

### <a name="full-layout-designer"></a>Progettazione layout completo

Il Designer completo del layout consente agli utenti di trascinare i controlli dell'interfaccia utente sullo schermo **Transazione** di POS e configurare le impostazioni di tali controlli.

![Designer layout POS completo (modalità orizzontale)](../commerce/media/POS-Full-Layout-Designer-Landscape.png)

- **Layout di importazione/layout di esportazione** - L'utente può esportare e importare i design del layout dello schermo di POS come file XML, in modo da poter condividerli e riutilizzarli facilmente negli ambienti. È importante che si importino i design del layout per le dimensioni appropriate del layout. In caso contrario, gli elementi dell'interfaccia utente potrebbero non adattarsi correttamente sullo schermo.
- **Orizzontale/verticale** - Se il dispositivo POS consente agli utenti di passare da modalità orizzontale a verticale e viceversa, è necessario definire un layout dello schermo per ciascuna modalità. POS rileva automaticamente la rotazione dello schermo e mostra il layout corretto.
- **Griglia del layout** - Il designer di layout POS utilizza una griglia di 4 pixel. I controlli dell'interfaccia utente "si agganciano" alla griglia per aiutare l'utente ad allinearsi correttamente al contenuto.
- **Zoom di progettazione** - La vista del designer può essere ingrandita o ridotta per vedere meglio il contenuto sullo schermo di POS. Questa funzionalità è utile se la risoluzione dello schermo su POS differisce notevolmente dalla risoluzione dello schermo utilizzato nel designer.
- **Mostra/nascondi barra di navigazione** - Per i layout completi di POS è possibile specificare se la barra di navigazione sinistra verrà visualizzata sullo schermo **Transazione**. Questa funzionalità è utile per i display con una risoluzione inferiore. Per impostare la visibilità, fare clic con il pulsante destro del mouse sulla barra di navigazione nel designer e selezionare o deselezionare la casella di controllo **Sempre visibile**. Se la barra di navigazione è nascosta, gli utenti POS possono comunque accedervi utilizzando il menu in alto a sinistra.

    ![Mostra/nascondi la barra di spostamento](../commerce/media/Navigation-Bar.PNG)

- **Comandi di POS** - Il designer di layout di POS supporta i comandi seguenti. È possibile configurare molti controlli facendo clic con il pulsante destro del mouse e utilizzando il menu di scelta rapida.

    ![Controlli dell'interfaccia utente di POS](../commerce/media/POS-UI-Controls.png)

    - **Tastierino numerico** - Il tastierino numerico è il meccanismo principale per l'input utente sulla schermata **Transazione** di POS. È possibile configurare il controllo in modo che venga mostrato il tastierino numerico completo. Questa opzione è ideale per i dispositivi touchscreen. In alternativa, è possibile configurarlo in modo da visualizzare solo il campo di immissione. In questo caso, per l'immissione viene utilizzata una tastiera fisica. Le impostazioni del tastierino numerico sono disponibili solo nei layout completi. Per i layout compatti, il tastierino numerico completo è sempre visualizzato sulla schermata **Transazione**.
    - **Pannello totali**: è possibile configurare il pannello totali in una o due colonne per visualizzare i valori come ad esempio conteggio righe, importo di sconto, addebiti, subtotale e imposta. I layout compatti supportano solo una singola colonna.
    - **Pannello Ricevuta**: il riquadro ricevuta contiene righe di vendita, pagamento e le informazioni di consegna per i prodotti e i servizi elaborati nel POS. È possibile specificare colonne, larghezze e posizione. Nei layout compatti, è possibile configurare informazioni aggiuntive visualizzate nella riga nella riga principale.
    - **Scheda cliente**: vengono visualizzate le informazioni relative al cliente attualmente associato alla transazione. La scheda cliente può essere configurata per nascondere o visualizzare informazioni aggiuntive.
    - **Controllo scheda**: può essere inserito nel layout dello schermo, altri comandi ad esempio il tastierino numerico, la carta cliente o le griglie dei pulsanti. Controllo scheda è un contenitore che consente agli utenti di inserire ulteriore contenuto nello schermo. Controllo scheda è disponibile solo per i layout completi.
    - **Immagine**: il controllo immagine può essere utilizzato per visualizzare il logo del punto vendita o un'altra immagine del marchio nello schermo di **transazione**. Controllo immagine è disponibile solo per i layout completi.
    - **Prodotti consigliati**: se configurato per l'ambiente, il controllo prodotti consigliati visualizza suggerimenti sul prodotto basati su Machine Learning.
    - **Controllo personalizzato**: il controllo personalizzato agisce come segnaposto nel layout dello schermo e consente agli utenti di prenotare lo spazio per contenuto personalizzato. Controllo personalizzato è disponibile solo per i layout completi.

### <a name="compact-layout-designer"></a>Progettazione layout compatto

Come la progettazione di layout completo, la progettazione di layout compatto consente di configurare il layout dello schermo del POS per i telefoni e i tablet di piccole dimensioni. Tuttavia, in questo caso, il layout stesso è fisso. È possibile configurare i controlli nel layout facendo clic con il pulsante destro del mouse e utilizzando il menu di scelta rapida. Tuttavia, non è possibile utilizzare le operazioni di trascinamento per il contenuto aggiuntivo.

![Progettazione layout compatto](../commerce/media/Compact-Layout-Designer.png)

### <a name="button-grid-designer"></a>Progettazione griglia dei pulsanti

La progettazione della griglia dei pulsanti consente di configurare le griglie dei pulsanti che possono essere utilizzate nella schermata di benvenuto del POS e nella schermata **Transazione** sia per layout completi che compatti. La stessa griglia di pulsanti può essere utilizzata per i layout e i tipi di layout. Come la progettazione del layout dello schermo, la griglia di pulsanti utilizza la tecnologia di distribuzione ClickOnce per scaricare, installare e avviare la versione più recente dell'applicazione ogni volta che gli utenti vi accedono. Assicurarsi di verificare i requisiti del browser di ClickOnce. Alcuni browser, ad esempio Google Chrome, richiedono estensioni.

![Progettazione griglia dei pulsanti](../commerce/media/Button-Grid-Designer.png)

- **Nuovo pulsante** - Fare clic per aggiungere un nuovo pulsante nella griglia. Per impostazione predefinita, i nuovi pulsanti vengono visualizzati nell'angolo in alto a sinistra della griglia. Tuttavia, è possibile organizzare i pulsanti trascinandoli nel layout.

    > [!IMPORTANT]
    > Il contenuto della griglia dei pulsanti può sovrapporsi. Quando si organizzano i pulsanti, accertarsi che non nascondano altri pulsanti.

- **Nuova progettazione** - Fare clic per impostare automaticamente un layout di griglia dei pulsanti specificando il numero di pulsanti per riga e colonna.
- **Proprietà pulsanti** - È possibile configurare le proprietà dei pulsanti facendo clic con il pulsante destro del mouse e utilizzando il menu di scelta rapida.

    > [!IMPORTANT]
    > Alcune impostazioni della griglia dei pulsanti sono applicabili solo a Enterprise POS, non a Modern POS o Cloud POS.

    ![Proprietà dei pulsanti della griglia dei pulsanti](../commerce/media/Button-grid-button-properties.png)

    - **Azione** - Nell'elenco delle operazioni POS applicabili, selezionare l'operazione che viene richiamata quando si fa clic sul pulsante nel POS.

        Per l'elenco delle operazioni POS supportate, vedere [Operazioni POS online e offline](pos-operations.md).

    - **Parametri di azione** - Alcune operazioni POS utilizzano parametri aggiuntivi quando vengono richiamate. Ad esempio, per l'operazione Aggiungi prodotto, gli utenti possono specificare il prodotto da aggiungere.
    - **Testo pulsante** – Specificare il testo che appare sul pulsante nel POS.
    - **Nascondere il testo dei pulsanti** - Utilizzare questa casella di controllo per nascondere o mostrare il testo del pulsante. Il testo dei pulsanti è spesso nascosto per i pulsanti di piccole dimensioni che mostrano solo un'icona.
    - **Descrizione comando** – Specificare il testo aggiuntivo della Guida che viene visualizzato quando gli utenti si spostano con il mouse sul pulsante.
    - **Dimensione in colonne/Dimensione in righe** – Può essere specificata l'altezza e la larghezza del pulsante.

        ![Dimensioni dei pulsanti di POS nelle righe e colonne](../commerce/media/POS-Button-Sizes-In-Rows-And-Columns.png)

    - **Carattere personalizzato** – Quando si seleziona la casella di controllo **Abilita tipo di carattere personalizzato per POS**, è possibile specificare un font diverso da quello di sistema predefinito per il POS.
    - **Tema personalizzato** - Per impostazione predefinita, i pulsanti POS utilizzano il colore d'accento del profilo visivo. Quando si seleziona la casella di controllo **Utilizzare il contenuto personalizzato**, è possibile specificare i colori aggiuntivi.

        > [!NOTE]
        > Modern POS e Cloud POS usano solo i valori **Colore sfondo** e **Colore carattere**.

    - **Immagine pulsante** - I pulsanti possono includere immagini o icone. Scegliere tra le immagini disponibili specificate **Retail e Commerce \> Impostazione canale \> Impostazione di POS \> POS \> Immagini**.

![Griglia dei pulsanti di esempio in POS](../commerce/media/Example-Button-Grid-In-POS.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Installare lo strumento di progettazione layout di POS di Retail](install-pos-layout-designer.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]