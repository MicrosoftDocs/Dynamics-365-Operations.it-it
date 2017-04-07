---
title: "Creare documentazione o formazione utilizzando le registrazioni di attività"
description: "In questo argomento sono descritti in Registrazione attività di questi processi di attività vengono, la creazione di registrazioni di attività e come personalizzare le aree di attività di Microsoft e comprenderle della Guida."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: 38bce4a843f0db575c8d1ba08b7dc2ece8366663
ms.lasthandoff: 03/31/2017


---

# <a name="create-documentation-or-training-using-task-recordings"></a>Creare documentazione o formazione utilizzando le registrazioni di attività
In questo argomento sono descritti in Registrazione attività di questi processi di attività vengono, la creazione di registrazioni di attività e come personalizzare le aree di attività di Microsoft e comprenderle della Guida.

<a name="learn-about-task-recorder"></a>Informazioni su Registrazione attività
-------------------------

In Registrazione attività viene Microsoft Dynamics 365 per lo strumento di operazioni che è possibile utilizzare per registrare le azioni contenente l'interfaccia utente del prodotto (UI). Quando si utilizza Registrazione attività, tutti eventi generati nell'interfaccia utente ed eseguiti nel server, tra cui l'aggiunta di valori, la modifica delle impostazioni, la rimozione di dati, vengono acquisiti. I passaggi registrati vengono collettivamente denominati *registrazione di attività*. Le registrazioni di attività possono essere utilizzate in molti modi:

-   **Le registrazioni di attività possono essere riprodotte come guide attività.** Consente di attività vengono un pezzo integrale di Dynamics 365 per esperienza della Guida delle operazioni. Guida di attività di esperienza è selezionata, la Guida, interattiva per i passaggi del processo aziendale. All'utente vengono fornite istruzioni per completare ciascun passaggio mediante un messaggio popup (o "bolla") che si animerà nell'interfaccia utente e punterà all'elemento dell'interfaccia utente con cui l'utente deve interagire. La bolla "" fornisce inoltre informazioni su come interagire con l'elemento, fare clic su come "in" o "in questo campo, immettere un valore". Guida di eseguito automaticamente in base al set di dati dell'utente e i dati immessi vengono salvati in caso di utilizzo.
-   ** Le registrazioni di attività possono essere visualizzati come passaggi procedura nel riquadro della Guida. ** È possibile utilizzare le registrazioni delle attività del riquadro della Guida per cercare e visualizzare. È possibile accedere al riquadro della Guida facendo **? ** l'icona nella barra di navigazione o si superiore può utilizzare la combinazione di tasti di scelta, ** Ctrl+Shift+? **. È possibile leggere i passaggi di un'attività registrata nel riquadro della Guida, oppure scegliere giocare la registrazione in una guida di attività che si Guida tramite l'interfaccia utente.
-   **Le registrazioni attività possono essere salvate in BPM.** È possibile salvare la propria registrazione attività in una riga di una gerarchia in una libreria BPM (Modellatore di processi aziendali) in Lifecycle Services (LCS). Un elenco dei passaggi e un diagramma di flusso di processi aziendali verranno generati dalla registrazione. Pagine delle registrazioni che sono state salvate a una raccolta di BPM possono essere visualizzate in Dynamics 365 per le operazioni come guida.
-   **Le registrazioni attività possono essere salvate come documenti di Word.** Ciò consente di produrre con facilità guide di formazione stampabili.

È possibile creare le proprie registrazioni di attività, registrazioni di attività di gioco fornite da Microsoft, o modificare fornite da Microsoft ha fornito le registrazioni di attività in base alla configurazione. Per ulteriori informazioni su Registrazione attività, vedere [Registrazione attività in Dynamics 365 per le operazioni task-recorder.md] ().

## <a name="plan-your-task-recording"></a>Pianificare la registrazione attività
Sia se si crea una nuova registrazione attività sia se si basa la registrazione su una registrazione attività Microsoft, considerare le seguenti informazioni.

-   Pianificare la registrazione come in un video. Prendere tutte le decisioni per tempo.
-   Eseguire una volta o due volte il processo aziendale senza registrarlo per comprendere i passaggi.
-   Durante l'esecuzione del processo prima di registrarlo, notare dove si utilizzano i tasti di scelta rapida o il tasto **INVIO**, in modo da evitare di utilizzarli durante la registrazione.
-   Identificare quanto segue:
    -   Si desidera raggruppare i passaggi in attività secondarie? Le attività secondarie suddividono visivamente le sezioni di un processo. Ad esempio, se si crea una registrazione per “Creare e rilasciare un prodotto", è possibile scegliere di raggruppare i passaggi necessari per creare un prodotto quindi di raggruppare i passaggi necessari di rilasciare il prodotto. le attività secondarie rendono inoltre i processi più lunghi facili leggere.
    -   Si desidera aggiungere annotazioni e, in tal caso, dove? Vedere “Comprendere i diversi tipi di annotazioni" di seguito per ulteriori informazioni.
    -   Quali valori si aggiungeranno nei diversi campi man mano che si completano i passaggi del processo aziendale? È buona idea conoscere cosa si selezionerà e immetterà man mano che si procede in modo che non sia necessario tornare indietro o correggere errori durante la registrazione.

**Scrivere la descrizione e le annotazioni prima del tempo**

-   All'inizio di ogni registrazione attività, è presente un campo di descrizione che consente di immettere un'introduzione alla registrazione. È buona idea scrivere e salvare la descrizione prima del tempo in un documento separato in modo da poterla copiare e incollare nella registrazione attività durante la registrazione. In questo modo, è possibile passare del tempo a migliorare il testo quando non si è nel processo di registrazione. Tagliare e incollare del testo rende il processo di registrazione più rapido e semplice.
-   Per ogni passaggio in una registrazione attività, è possibile creare le annotazioni. Durante la riproduzione della guida attività, le annotazioni vengono visualizzati nella "bolla" come note sopra o sotto al testo per il passaggio. Una volta considerate come testo nel riquadro della Guida, le annotazioni vengono visualizzate come testo nelle righe dell'ordine. Come con la descrizione è buona idea scrivere e salvare le annotazioni in un documento separato. Durante la registrazione della registrazione attività, tagliare e incollare le annotazioni dal documento.

**Comprender i diversi tipi di annotazioni** Tutte le annotazioni sono facoltative. Aggiungerle solo quando forniranno informazioni utili all'utente.

-   ** ** Titolo: In annotazione del titolo verrà visualizzato prima del testo del passaggio delle attività che la registrazione genera automaticamente. Nella guida all'attività, annotazione di titolo viene visualizzato sul testo generato automaticamente. Utilizzare questo tipo di annotazione per spiegare perché l'utente esegue il passaggio o per fornire contesto aggiuntivo.

Questo è il riquadro di modifica visualizzato quando si aggiunge un'annotazione durante la creazione della registrazione. Immettere un'annotazione del titolo nella casella **Titolo**. 

![[] (screen1. /media/screen1.png)](. /media/screen1.png) 

Questo è come l'annotazione del titolo apparirà nel "bolla" della guida attività. 

![[] (screen2. /media/screen2.png)](. /media/screen2.png)

-   **Note:** Un'annotazione delle note verrà visualizzata dopo il testo del passaggio che la registrazione attività genera automaticamente. Nella guida attività sarà visibile solo se l'utente fa clic sul collegamento **Visualizzare altro** nella "bolla" della Guida attività. Utilizzare questo tipo di annotazione per descrivere tutto ciò l'utente necessita di sapere per completare il passaggio.

Questo è il riquadro di modifica visualizzato quando si aggiunge un'annotazione durante la creazione della registrazione. Immettere un'annotazione per le note nella casella **Note**. 

![[] (screen3. /media/screen3.png)](. /media/screen3.png) 

Si tratta dell'annotazione di note sarà simile bolla "in" nella Guida di attività.

![[] (screen4. /media/screen4.png)](. /media/screen4.png)

-   ** Passaggio di informazioni **: Queste annotazioni vengono create dalla destra che fa clic su un controllo o in un punto qualsiasi in &lt; un modulo ** Registrazione attività ** &lt; ** aggiunti il passaggio di informazioni. ** La procedura di informazioni verranno visualizzati come un passaggio numerati a qualsiasi punto lo immesse, anche se non è registrata in installata. È possibile aggiungere un passaggio informativo a livello di modulo o un passaggio informativo associato a un controllo. Quando un passaggio informativo è associato a un modulo, quando la guida attività viene riprodotta la relativa “bolla" verrà visualizzata in qualche parte del modulo, senza puntatore. Quando un passaggio di informazioni è associato a un controllo, guida "" bolla di attività indica il controllo se la Guida di attività è giocata. Nel riquadro della Guida, verrà annotazione del passaggio di informazioni verrà visualizzata come passaggio numerati al testo immesso. Le informazioni relative all'utilizzo di un passaggio per preparare all'utente delle opzioni riportate di seguito, per descrivere i passaggi che devono essere eseguiti esternamente a Dynamics 365 per le operazioni, o per fare riferimento ad altre registrazioni (sebbene non sia possibile creare i hyperinks in annotazioni.).

**Determinare la lunghezza della registrazione**

-   L'utente in genere leggerà o riprodurrà la registrazione dall'inizio alla fine, pertanto non combinare i passaggi o le attività che è meglio eseguire separatamente.
-   Provare a non registrare uno scenario lungo che riguarda più processi secondari. Ad esempio, “Gestire postazioni servizio clienti in punto vendita" è troppo ampio; suddividerlo pertanto in attività brevi attività ad esempio “Accetta resi" e "Aggiungi alla gift card".
-   Se un'attività può essere svolta come parte di diversi processi aziendali, creare una registrazione separata, a cui possibile fare riferimento in altre registrazioni.
-   Se il processo comprende più attività che la persona probabilmente effettua contemporaneamente, è possibile mantenere le attività in un'unica registrazione, ad esempio “Impostare e assegnare profili funzionalità".
-   In caso di un'attività eseguita una solo volta (come la configurazione), quindi di un'altra attività che può essere effettuata subito dopo ma più volte e in modo autonomo, suddividere tali attività in due registrazioni attività.

** Specificare in cui, installata nel, per avviare una registrazione ** la pagina che attivo nel momento iniziare a registrare le modifiche di registrazione di un'attività che impaginano la Guida di attività visualizzato. Ad esempio, se si desidera che la propria attività che registra da elencare nel riquadro della Guida quando un utente sulla Guida sui parametri pagina della contabilità generale, è necessario eseguire la registrazione nella pagina dei parametri di contabilità generale. **Salvare le registrazioni come file axtr** Quando si finisce di creare o modificare una registrazione attività, vengono visualizzate diverse opzioni per scaricare o salvare la registrazione. È possibile scaricare il file come pacchetto di registrazione attività (axtr), scaricarlo come file di registrazione non elaborato (XML), scaricarlo come documento di Word o salvare il file come una libreria LCS. È buona idea salvare sempre la registrazione attività come file di pacchetto di registrazione attività (axtr). Che contribuirà a rendere la gestione del file più semplice se è necessario cambiare le procedure o le annotazioni in un secondo momento. Se si desidera scaricare il file come documento di Word, salvarlo anche come file di pacchetto di registrazione attività.

## <a name="create-your-task-recording"></a>Creare la registrazione attività
Per i passaggi dettagliati di serie progressiva, vedere [la creazione di un'attività registrata task-recorder.md] ().

## <a name="copy-and-customize-microsofts-task-recordings"></a>Copiare e personalizzare le registrazioni attività di Microsoft
È possibile scaricare e modificare le registrazioni dell'attività da Microsoft per utilizzarli per i propri materiali della documentazione o una formazione della Guida. Per scaricare una registrazione attività di Microsoft, effettuare i passaggi seguenti:

1.  In Dynamics 365 per le operazioni, aprire la funzione Registrazione attività. Registrazione attività si trova nel menu **Impostazioni**.
2.  Nel riquadro Registrazione attività, fare clic su **Gestisci una registrazione.**
3.  In **Dove è la registrazione**, fare clic su **È presente in una libreria LCS**.
4.  fare clic su **Selezionare la libreria LCS**.
5.  Selezionare la libreria globale Microsoft.
6.  Nella struttura, selezionare il nodo libreria processi aziendali a cui è associata la registrazione attività.
7.  Scegliere **OK**.
8.  Fare clic su **Inizia**.
9.  A questo punto, passaggio tramite la registrazione, la modifica delle operazioni come andate eseguirne di nuovo. ** ** Nota: Se è necessario modificare solo il testo di una registrazione, è possibile aprire la registrazione in ** modificare le annotazioni di una registrazione ** modalità e il giorno salvate.
10. Dopo che la registrazione è stata riprodotta fino alla fine, fare clic su **Interrompi** sulla barra di registrazione attività nella parte superiore della schermata.
11. Scegliere come salvare la registrazione attività.

## <a name="include-your-task-recordings-in-the-help-pane"></a>Includere le registrazioni delle attività nel riquadro della Guida
Per visualizzare le proprie registrazioni in ordinazione di attività nel riquadro della Guida in modo che possano essere riprodotte come consente di visualizzare l'attività o impostato come testo, è necessario salvare le registrazioni di attività alla specifica raccolta di BPM e quindi si aggiorna i parametri di sistema relativi alla Guida per indicare la libreria di BPM. Per ulteriori informazioni, vedere [collegare il file della Guida.]. (. /get-started/help-connect.md)

<a name="see-also"></a>Vedere anche
--------

[Dynamics 365 per ottenere di operazioni. (]. \ \ iniziano help-overview.md)

[Collegare la Guida (]. \ \ iniziano help-connect.md)

[Registrazione attività in Dynamics 365 per le operazioni task-recorder.md] ()

[Funzionalità inoltre aggiunte Registrazione attività] (\ \ centro inizia \ recente-aggiungere-modificare-funzionalità-in-attività- registrazione)

[La creazione di nuove librerie di formazione per Dynamics AX all'interno dei servizi del ciclo di vita tramite Registrazione attività (collegamento esterno)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)

[Creare gli argomenti della Guida complessi alla funzione Registrazione attività (collegamento esterno)](https://mbspartner.microsoft.com/AX/Videos/970)


