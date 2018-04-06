---
title: "Creare documentazione o formazione utilizzando le registrazioni di attività"
description: "In questo argomento vengono illustrate la funzionalità Registrazione attività e le guide attività, viene descritto come creare file di Registrazione attività e come personalizzare le guide attività di Microsoft e includerle nella Guida."
author: josaw1
manager: AnnBe
ms.date: 10/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 9550faec1bbbdc233631e149c09b8e4faf25f5ff
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="create-documentation-or-training-using-task-recordings"></a>Creare documentazione o formazione utilizzando le registrazioni di attività

[!include[banner](../includes/banner.md)]

In questo argomento vengono illustrate la funzionalità Registrazione attività e le guide attività, viene descritto come creare file di Registrazione attività e come personalizzare le guide attività di Microsoft e includerle nella Guida.

> [!IMPORTANT]
> È possibile registrare le proprie guide attività per Dynamics 365 for Talent ma non sarà possibile salvarle in una libreria del Modellatore di processi aziendali o aprirle dal riquadro della Guida in questo momento. È possibile salvarle in locale o in un percorso di rete, quindi aprirle e riprodurle utilizzando Registrazione attività. 

<a name="learn-about-task-recorder"></a>Informazioni su Registrazione attività
-------------------------

Registrazione attività è uno strumento che è possibile utilizzare per registrare le azioni eseguite nell'interfaccia utente del prodotto. Quando si utilizza Registrazione attività, tutti eventi generati nell'interfaccia utente ed eseguiti nel server, tra cui l'aggiunta di valori, la modifica delle impostazioni, la rimozione di dati, vengono acquisiti. I passaggi registrati vengono collettivamente denominati *registrazione di attività*. Le registrazioni di attività possono essere utilizzate in molti modi:

-   **Le registrazioni di attività possono essere riprodotte come guide attività.** Le guide attività sono un pezzo integrale della Guida. Una guida attività è un'esperienza controllata, guidata e interattiva che guida attraverso i passaggi di un processo aziendale. All'utente vengono fornite istruzioni per completare ciascun passaggio mediante un messaggio popup (o "bolla") che si animerà nell'interfaccia utente e punterà all'elemento dell'interfaccia utente con cui l'utente deve interagire. La "bolla" fornisce inoltre informazioni su come interagire con l'elemento, ad esempio "Fare clic qui" o "In questo campo, immettere un valore". Una guida attività viene eseguita per il set di dati corrente dell'utente e i dati immessi vengono salvati nell'ambiente dell'utente.
-   **I file di Registrazione attività possono essere visualizzati come passaggi procedurali nel riquadro della Guida.** È possibile utilizzare il riquadro della Guida per cercare e visualizzare i file di Registrazione attività. È possibile accedere al riquadro della Guida facendo clic sull'icona **?** nella barra di navigazione superiore oppure è possibile utilizzare la combinazione di tasti di scelta rapida **CTRL+MAIUSC+?**. È possibile leggere i passaggi di una registrazione attività nel riquadro della Guida oppure scegliere di riprodurre la registrazione come guida attività, per essere guidati nell'interfaccia utente.
-   **Le registrazioni attività possono essere salvate in BPM.** È possibile salvare la propria registrazione attività in una riga di una gerarchia in una libreria del Modeler di processi aziendali in Lifecycle Services (LCS). Un elenco dei passaggi e un diagramma di flusso di processi aziendali verranno generati dalla registrazione. Le registrazioni attività che sono state salvate in una libreria BPM possono essere visualizzate come Guida.
-   **Le registrazioni attività possono essere salvate come documenti di Word.** Ciò consente di produrre con facilità guide di formazione stampabili.

È possibile creare i propri file di Registrazione attività, riprodurre i file di Registrazione attività forniti da Microsoft o modificarli in base alla configurazione in uso. Per ulteriori informazioni su Registrazione attività, vedere [Registrazione attività](task-recorder.md).

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
-   Per ogni passaggio in una registrazione attività, è possibile creare le annotazioni. Durante la riproduzione della guida attività, le annotazioni vengono visualizzati nella "bolla" come note sopra o sotto al testo per il passaggio. Quando vengono visualizzate come testo nel riquadro della Guida, le annotazioni appaiono come testo incorporato nel passaggio. Come con la descrizione è buona idea scrivere e salvare le annotazioni in un documento separato. Durante la registrazione della registrazione attività, tagliare e incollare le annotazioni dal documento.

**Comprender i diversi tipi di annotazioni** Tutte le annotazioni sono facoltative. Aggiungerle solo quando forniranno informazioni utili all'utente.

-   **Titolo**: un'annotazione del titolo verrà visualizzata prima del testo del passaggio che Registrazione attività genera automaticamente. Nella guida attività, l'annotazione del titolo viene visualizzata sopra il testo generato automaticamente. Utilizzare questo tipo di annotazione per spiegare perché l'utente esegue il passaggio o per fornire contesto aggiuntivo.

Questo è il riquadro di modifica visualizzato quando si aggiunge un'annotazione durante la creazione della registrazione. Immettere un'annotazione del titolo nella casella **Titolo**. 

[![schermata1](./media/screen1.png)](./media/screen1.png) 

Questo è come l'annotazione del titolo apparirà nel "bolla" della guida attività. 

[![schermata2](./media/screen2.png)](./media/screen2.png)

-   **Note:** Un'annotazione delle note verrà visualizzata dopo il testo del passaggio che la registrazione attività genera automaticamente. Nella guida attività sarà visibile solo se l'utente fa clic sul collegamento **Visualizzare altro** nella "bolla" della Guida attività. Utilizzare questo tipo di annotazione per descrivere tutto ciò l'utente necessita di sapere per completare il passaggio.

Questo è il riquadro di modifica visualizzato quando si aggiunge un'annotazione durante la creazione della registrazione. Immettere un'annotazione per le note nella casella **Note**. 

[![schermata3](./media/screen3.png)](./media/screen3.png) 

Così apparirà l'annotazione per le note nella "bolla" della guida attività.

[![schermata4](./media/screen4.png)](./media/screen4.png)

-   **Passaggio informativo**: queste annotazioni vengono create facendo clic con il pulsante destro del mouse su un controllo o in un punto qualsiasi su un modulo &lt; **Registrazione attività** &lt; **Aggiungi passaggio informativo. **I passaggi informativi verranno visualizzati come un passaggio numerato in qualsiasi punto vengano immessi, anche se non è stata registrata alcuna azione nell'interfaccia utente. È possibile aggiungere un passaggio informativo a livello di modulo o un passaggio informativo associato a un controllo. Quando un passaggio informativo è associato a un modulo, quando la guida attività viene riprodotta la relativa “bolla" verrà visualizzata in qualche parte del modulo, senza puntatore. Quando un passaggio informativo è associato a un controllo, la "bolla" della guida attività punterà al controllo quando la guida attività viene riprodotta. Nel riquadro della Guida, un'annotazione del passaggio informativo verrà visualizzata come passaggio numerato con il testo immesso. Utilizzare i passaggi informativi per preparare l'utente per i passaggi successivi, per descrivere i passaggi che devono essere effettuati al di fuori di Microsoft Dynamics 365 for Finance and Operations o per fare riferimento ad altre registrazioni (sebbene non sia possibile creare collegamenti ipertestuali nelle annotazioni).

**Determinare la lunghezza della registrazione**

-   L'utente in genere leggerà o riprodurrà la registrazione dall'inizio alla fine, pertanto non combinare i passaggi o le attività che è meglio eseguire separatamente.
-   Provare a non registrare uno scenario lungo che riguarda più processi secondari. Ad esempio, “Gestire postazioni servizio clienti in punto vendita" è troppo ampio; suddividerlo pertanto in attività brevi attività ad esempio “Accetta resi" e "Aggiungi alla gift card".
-   Se un'attività può essere svolta come parte di diversi processi aziendali, creare una registrazione separata, a cui possibile fare riferimento in altre registrazioni.
-   Se il processo comprende più attività che la persona probabilmente effettua contemporaneamente, è possibile mantenere le attività in un'unica registrazione, ad esempio “Impostare e assegnare profili funzionalità".
-   In caso di un'attività eseguita una solo volta (come la configurazione), quindi di un'altra attività che può essere effettuata subito dopo ma più volte e in modo autonomo, suddividere tali attività in due registrazioni attività.

**Decidere dove, nell'interfaccia utente, avviare una registrazione** La pagina in cui ci si trova quando si avvia la registrazione di un file di Registrazione attività influisce sulla pagina per cui è visualizzata la guida attività. Ad esempio, se si desidera che il file di Registrazione attività venga elencato nel riquadro della Guida quando un utente fa clic sulla Guida nella pagina Parametri di contabilità generale, è necessario avviare la registrazione nella pagina Parametri di contabilità generale. **Salvare le registrazioni come file axtr** Quando si finisce di creare o modificare una registrazione attività, vengono visualizzate diverse opzioni per scaricare o salvare la registrazione. È possibile scaricare il file come pacchetto di registrazione attività (axtr), scaricarlo come file di registrazione non elaborato (XML), scaricarlo come documento di Word o salvare il file come una libreria LCS. È buona idea salvare sempre la registrazione attività come file di pacchetto di registrazione attività (axtr). Che contribuirà a rendere la gestione del file più semplice se è necessario cambiare le procedure o le annotazioni in un secondo momento. Se si desidera scaricare il file come documento di Word, salvarlo anche come file di pacchetto di registrazione attività.

## <a name="create-your-task-recording"></a>Creare la registrazione attività
Per i passaggi dettagliati della procedura, vedere [Come creare un file di Registrazione attività](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>Copiare e personalizzare le registrazioni attività di Microsoft
È possibile scaricare e modificare i file di Registrazione attività di Microsoft per utilizzarli per la documentazione della Guida o i materiali di formazione. Per scaricare una registrazione attività di Microsoft, effettuare i passaggi seguenti:

1.  Aprire Registrazione attività. Registrazione attività si trova nel menu **Impostazioni**.
2.  Nel riquadro Registrazione attività, fare clic su **Gestisci una registrazione.**
3.  In **Dove è la registrazione**, fare clic su **È presente in una libreria LCS**.
4.  fare clic su **Selezionare la libreria LCS**.
5.  Selezionare la libreria globale di Microsoft.
6.  Nella struttura, selezionare il nodo libreria processi aziendali a cui è associata la registrazione attività.
7.  Scegliere **OK**.
8.  Fare clic su **Inizia**.
9.  A questo punto, procedere con la registrazione, modificando i passaggi man mano che si registra di nuovo. **Nota**: se è necessario modificare solo il testo di una registrazione, è possibile aprire la registrazione in modalità **Modifica annotazioni di una registrazione**, quindi salvarla.
10. Dopo che la registrazione è stata riprodotta fino alla fine, fare clic su **Interrompi** sulla barra di registrazione attività nella parte superiore della schermata.
11. Scegliere come salvare la registrazione attività.

## <a name="include-your-task-recordings-in-the-help-pane"></a>Includere i file di Registrazione attività nel riquadro della Guida
Per visualizzare i file di Registrazione attività personalizzati nel riquadro della Guida in modo che possano essere riprodotti come guide attività o visualizzati come testo, è necessario salvare i file di Registrazione attività nella libreria BPM, quindi aggiornare i parametri di sistema della Guida in modo che puntino alla libreria BPM. Per ulteriori informazioni, vedere [Collegamento alla Guida](../../fin-and-ops/get-started/help-connect.md).

<a name="see-also"></a>Vedere anche
--------

[Panoramica della Guida](../../fin-and-ops/get-started/help-overview.md)

[Collegarsi alla Guida](../../fin-and-ops/get-started/help-connect.md)

[Registrazione attività](task-recorder.md)

[Creare argomenti dettagliati della Guida con Registrazione attività (collegamento esterno)](https://mbspartner.microsoft.com/AX/Videos/970)

