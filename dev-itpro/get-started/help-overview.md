---
title: Panoramica della Guida
description: "Questo articolo fornisce una panoramica dei componenti della Guida di Microsoft Dynamics 365 for Operations. Viene illustrato come è possibile fornire documentazione personalizzata e formazione all&quot;organizzazione."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16381
ms.assetid: 018c148c-9cbd-41e0-8186-d75dbf66288f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 181ad9a7ab4e83ce9eb34312e93b1ebdeb2e04eb
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="help-overview"></a>Panoramica della Guida

[!include[banner](../includes/banner.md)]


Questo articolo fornisce una panoramica dei componenti della Guida di Microsoft Dynamics 365 for Operations. Viene illustrato come è possibile fornire documentazione personalizzata e formazione all'organizzazione. 

Dynamics 365 for Operations include una Guida basata su due componenti principali:

-   Sito di documentazione
-   Guide attività

È possibile accedere agli articoli e alle guide attività dal riquadro Guida in Dynamics 365 for Operations, come illustrato nel seguente screenshot.

![Riquadro della Guida](./media/help-pane-ops-task-guides-1024x741.png)

Questo articolo descrive la Guida e spiega come creare documentazione e risorse di formazione personalizzate per l'organizzazione.

## <a name="help-on-docsmicrosoftcom"></a>Guida sul sito docs.microsoft.com
Il sito docs.microsoft.com ([docs.microsoft.com/dynamics365/operations](/dynamics365/#pivot=solutions&panel=solutions_operations)) rappresenta la fonte principale di documentazione sul prodotto Dynamics 365 for Operations. Il sito offre le seguenti funzionalità:

-   **Accesso a contenuti più aggiornati**: il sito offre modi più veloci e più flessibili per creare, fornire e aggiornare la documentazione del prodotto. Di conseguenza, aiuta a garantire l'accesso alle ultime informazioni tecniche.
-   **Contenuto scritto da esperti**: il sito fornisce un set più dettagliato di documentazione del prodotto che può essere aggiornato da membri della community interni ed esterni a Microsoft.
-   **Accesso a diversi tipi di contenuto**: il sito consente di accedere rapidamente a diversi tipi di contenuto su Dynamics 365 for Operations, ad esempio presentazioni di Microsoft Office Mix, guide attività, video e argomenti.
-   **Contenuto che supporta i processi aziendali**: il sito include contenuto incentrato su processi aziendali che sfrutta i vantaggi offerti dal Modellatore di processi aziendali in Microsoft Dynamics Lifecycle Services (LCS).

Tutto il contenuto della guida precedente è stato migrato sul sito docs. Siamo molto soddisfatti del nostro nuovo sito e speriamo che lo siano anche i nostri utenti.

### <a name="searching-on-docsmicrosoftcom"></a>Ricerca in docs.microsoft.com
Diverse sono le domande ricevute sulla modalità di ricerca del contenuto. Nel sito, se si inizia da una pagina su Dynamics 365 for Operations, si suppone che l'ambito della ricerca sia per il contenuto di Dynamics 365 for Operations. È possibile rimuovere l'ambito facendo clic sulla X accanto a Operations nella casella di ricerca. 
![Cerca ordini](./media/search-scope.png)

È possibile trovare il contenuto con un qualsiasi motore di ricerca. Per i risultati ottimali si consiglia di utilizzare una ricerca del tipo site:docs.microsoft.com "termine di ricerca"  
![Ricerca nel sito](./media/site-search.png)

![Risultati della ricerca nel sito](./media/site-search-results.png)


### <a name="how-can-i-contribute"></a>Come è possibile contribuire? 

Scrivere un commento. 

1 Fare clic su **Commenti** per passare al riquadro dei commenti nell'area inferiore della pagina.

![Commenti](./media/comments.png)

2 Iniziare a digitare i commenti quindi fare clic su **Pubblica un commento**.

![Pubblica un commento](./media/before-signin.png)

3 Selezionare il tipo di account con cui si desidera accedere:  
Fare clic su una delle icone a sinistra per associare questo sito a un account esistente, ad esempio un account di Twitter, Facebook o Microsoft. 

O 

A destra, immettere l'indirizzo di posta elettronica e una nuova password per creare un nuovo account per il sito. 

![Opzioni di accesso](./media/signin-options.png)


## <a name="task-guides"></a>Guide attività
Una guida attività è un'esperienza controllata, guidata e interattiva che guida l'utente attraverso i passaggi di un'attività o di un processo aziendale. È possibile aprire (riprodurre) una guida attività dal riquadro Guida. Quando si fa clic per la prima volta su una guida attività, nel riquadro Guida vengono visualizzate le istruzioni dettagliate per l'attività. Ora sono disponibili guide attività localizzate. 

![Visualizzazione lettura delle guide attività](./media/task-guide-ops-1024x742.png)

Per avviare l'esperienza guidata e interattiva, fare clic su **Avvia guida attività** nella parte inferiore del riquadro Guida. Un puntatore nero si apre e indica l'azione che è necessario eseguire. Seguire le indicazioni visualizzate nell'interfaccia utente e immettere i dati come richiesto. 
![Istruzione dettagliata della guida attività](./media/task-guide-step-1-ops.png)

> [!IMPORTANT] 
> I dati immessi quando si riproduce una guida attività sono reali. Se si è in un ambiente di produzione, i dati verranno immessi nella società attualmente utilizzata.

### <a name="it-all-begins-with-task-recorder"></a>Tutto ciò ha inizio con Registrazione attività

Le guide attività vengono create mediante Registrazione attività. Quando si utilizza Registrazione attività, tutte le azioni eseguite nell'interfaccia utente di Dynamics 365 for Operations, ad esempio il clic sui menu, la modifica delle impostazioni e l'immissione dei dati, vengono registrate. I passaggi registrati vengono collettivamente denominati registrazione di attività. Come spiegato nella sezione precedente, le registrazioni attività possono essere visualizzate nel riquadro Guida e riprodotte come guide attività. Tuttavia, è possibile utilizzare le registrazioni di attività in altri modi:

-   **Salvare le registrazioni attività in BPM** È possibile salvare una registrazione attività in una riga di gerarchia in una libreria BPM in LCS. Quando si salva una registrazione attività in BPM, un diagramma di flusso viene generato e visualizzato, insieme ai passaggi di registrazione. **Nota:** Per visualizzare una registrazione attività nel riquadro Guida di Dynamics 365 for Operations e riprodurla come una guida attività, si dovrà salvare la registrazione in una libreria BPM.
-   **Salvare le registrazioni attività come documenti di Word** Salvando una registrazione attività come documento di Microsoft Word, è possibile produrre con facilità guide di formazione stampabili per l'organizzazione.

Per ulteriori informazioni su Registrazione attività, vedere [Registrazione attività in Dynamics 365 for Operations](../user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Creare registrazioni attività personalizzate

È possibile creare registrazioni attività personalizzate oppure scaricare e personalizzare le registrazioni attività fornite da Microsoft. Di conseguenza, è possibile creare la Guida personalizzata per l'organizzazione in base alla specifica implementazione di Dynamics 365 for Operations. Per visualizzare una registrazione attività nel riquadro Guida di Dynamics 365 for Operations e riprodurla come una guida attività, si dovrà salvare la registrazione in una libreria BPM in LCS. Per i partner, se si promuove una libreria a libreria aziendale e si include in una soluzione, sarà disponibile per i clienti. Per le istruzioni complete, vedere [Utilizzo delle registrazioni attività per creare documentazione o formazione](../user-interface/task-recorder.md).

## <a name="in-product-help"></a>Guida nel prodotto
Per accedere al contenuto della Guida all'interno di Dynamics 365 for Operations, fare clic sull'icona **Guida** (**?**) oppure scegliere Guida o premere CTRL+MAIUSC+?. In entrambi i casi, verrà aperto il riquadro della Guida. Dal riquadro Guida è possibile accedere ad articoli o guide attività. 

![Riquadro della Guida](./media/help-pane-wiki-1024x684.png)

### <a name="accessing-articles-from-the-help-pane"></a>Accesso agli articoli dal riquadro Guida

Dal riquadro della Guida è possibile accedere ad articoli applicabili al client Dynamics 365 for Operations. Quando si apre il riquadro della Guida e si fa clic sulla scheda **Wiki**, vengono visualizzati gli articoli applicabili alla pagina attualmente aperta in Dynamics 365 for Operations. Se non viene trovato alcun articolo, è possibile immettere le parole chiave per ridefinire la ricerca. Quando si fa clic su un articolo nel riquadro Guida, una nuova scheda viene visualizzata nel browser e viene visualizzato l'articolo. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Accesso alle guide attività dal riquadro Guida

Affinché si possa accedere alle guide attività dal riquadro Guida, è necessario che un amministratore di sistema acceda alla pagina **Parametri di sistema** in Dynamics 365 for Operations e configuri alcune impostazioni. 

> [!NOTE]
> -   Per configurare la Guida, è necessario essere connessi con un account nello stesso tenant di distribuzione di Dynamics 365 for Operations.
> -   Non è possibile connettersi a una libreria LCS da un'istanza di Dynamics 365 for Operations in esecuzione in un'unità disco rigido virtuale (VHD) locale.

![Modulo Parametri di sistema con impostazioni per la Guida](./media/system-parameters_ops-1024x437.png)

Nella pagina **Parametri di sistema** effettuare i seguenti passaggi:

1.  **Importante:**La prima volta che si apre la scheda della Guida, è necessario connettersi a Lifecycle Services. Assicurarsi di fare clic sul collegamento al centro del modulo, attendere la connessione, chiudere la finestra di dialogo quindi scegliere OK per ottenere il modulo dei parametri.
![Connetti a LCS](./media/connect-to-lcs-crop-1024x365.png)
2.  Selezionare il progetto Lifecycle Services a cui connettersi.
3.  Selezionare le librerie BPM (nel progetto selezionato) da cui recuperare le registrazioni attività.
4.  Impostare l'ordine di visualizzazione delle librerie BPM. Ciò determina l'ordine in cui le registrazioni attività delle librerie verranno visualizzate nel riquadroGuida.

Dopo che un amministratore di sistema ha completato questi passaggi, è possibile aprire il riquadro della guida e fare clic sulla scheda **Guide attività**. Verranno visualizzate le guide attività applicabili alla pagina attualmente aperta in Dynamics 365 for Operations. Se non viene trovata alcuna guida attività, è possibile immettere le parole chiave per ridefinire la ricerca. Dopo ave fatto clic su una guida attività, nel riquadro Guida vengono visualizzate le istruzioni dettagliate ed è possibile riprodurre la guida attività. 
![Visualizzazione lettura delle guide attività](./media/task-guide-ops-1024x742.png)

### <a name="where-are-the-translated-task-guides"></a>Dove sono le guide attività tradotte?

Le guide attività tradotte vengono rilasciate nelle librerie con "tutte le lingue" nel titolo. In Dynamics 365 for Operations, per visualizzare la guida attività localizzata, assicurarsi di essere connessi alla libreria appropriata. La lingua in cui viene visualizzata una Guida attività è controllata per ogni utente dalle impostazioni di lingua in **Opzioni** &gt; **Preferenze**. 
-   Se una guida attività è stata tradotta, quando la si apre tutto il testo appare nella lingua selezionata.
-   Se una guida attività non è stata ancora tradotta, quando la si apre, solo parte del testo (quello dei controlli) appare nella lingua selezionata.

## <a name="additional-resources"></a>Risorse aggiuntive
Nella tabella di seguito sono elencati i siti Web che forniscono il contenuto di Dynamics 365 for Operations. I nostri siti Web di contenuti sono organizzati per supportare il ciclo di vita del cliente. Ogni fase è supportata da una serie di siti diversi. I siti con un asterisco (\*) accanto al nome richiedono che venga eseguito l'accesso mediante un account associato a un piano di servizio.

| Sito                                                                     | descrizione                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Docs.microsoft.com](/dynamics365/#pivot=solutions&panel=solutions_operations) | Host o collegamenti a tutta la documentazione del prodotto per Dynamics 365 for Operations.                                                                                                                                                               |
| [Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Offre un'area di lavoro collaborativa basata sul cloud che i clienti e i partner possono utilizzare per gestire i progetti Dynamics 365 for Operations dalle prevendite all'implementazione e alle operazioni. Questo sito è utile in tutte le fasi dell'implementazione. |
| [CustomerSource](http://www.customersource.com/)\*                       | Ospita risorse di formazione estese e rappresenta il sito di supporto primario per Dynamics 365 for Operations. L'accesso potrebbe essere necessario per visualizzare risorse specifiche del sito.                                                                      |
| [Blog di supporto](http://aka.ms/AXSupportBlog)                              | Fornisce suggerimenti pubblicati dal team del supporto di Dynamics 365 for Operations.                                                                                                                                                  |
| [MSDN](http://aka.ms/AXMSDN)                                             | Ospita contenuto delle versioni precedenti scritto per gli sviluppatori.                                                                                                                                                                       |
| [TechNet](http://aka.ms/TechNet)                                         | Ospita contenuti delle versioni precedenti scritti per i professionisti IT e gli utenti di applicazioni.                                                                                                                                           |
| [Community di Dynamics](http://community.dynamics.com/)                  | Ospita blog, i forum e video.                                                                                                                                                                                                           |
| [Microsoft.com/Dynamics/](http://www.microsoft.com/dynamics/)                 | Fornisce informazioni su vendite e valutazione.                                                                                                                                                                                                 |



<a name="see-also"></a>Vedere anche
--------

[Guida in linea di Dynamics 365 for Operations (scheda informativa scaricabile)](https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Registrazione attività in Microsoft Dynamics 365 for Operations](../user-interface/task-recorder.md)

[Creare documentazione o formazione utilizzando le registrazioni di attività](../user-interface/task-recorder.md)

[Guide attività nuove o aggiornate (novembre 2016)](new-task-guides-november-2016.md)
[Guide attività nuove o aggiornate (agosto 2016)](new-updated-task-guides-available-august-2016.md)
[Guide attività nuove o aggiornate (maggio 2016)](new-updated-task-guides-available-may-2016.md)
[Nuove guide attività (febbraio 2016)](new-task-guides-available-february-2016.md)








