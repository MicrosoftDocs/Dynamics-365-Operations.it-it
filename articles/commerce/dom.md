---
title: Gestione ordini distribuiti (DOM)
description: In questo articolo viene descritta la funzionalità per la gestione ordini distribuiti (DOM) in Dynamics 365 Commerce.
author: josaw1
ms.date: 02/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 26817321753c8e39d61957b4ea2004f20daf1b2f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878514"
---
# <a name="distributed-order-management-dom"></a>Gestione ordini distribuiti (DOM)

[!include [banner](includes/banner.md)]

In questo articolo viene descritta la funzionalità per la gestione ordini distribuiti (DOM) in Microsoft Dynamics 365 Commerce.

DOM è una soluzione multicanale che consente di ottimizzare l'evasione degli ordini in una rete di supply chain. DOM aiuta a garantire che i prodotti vengano consegnati ai clienti nelle quantità, dalle fonti e nei tempi corretti. DOM consente anche di massimizzare i profitti, ridurre i costi e soddisfare i requisiti del livello di servizio.

DOM utilizza la programmazione intera mista (MIP, Mixed Integer Programming) e modelli di analisi predittiva per eseguire ottimizzazioni sia a livello di batch sia a livello di singoli ordini. Questa capacità consente ai rivenditori di utilizzare regole definite per bilanciare numerose esigenze di evasione degli ordini in conflitto. In una moderna rete di fornitura in cui l'evasione dei prodotti può provenire da più canali, le organizzazioni devono adattarsi rapidamente ai cambiamenti degli ordini, ai problemi di disponibilità dei fornitori e ai picchi della domanda. DOM consente di ottimizzare l'evasione degli ordini e di trovare le fonti corrette per la consegna dei prodotti, in base a vincoli e obiettivi aziendali, ad esempio ridurre i costi evadendo gli ordini dalle fonti più vicine. DOM utilizza la distanza tra le fonti di evasione dei prodotti e le destinazioni di spedizione, i fattori di costo definiti come obiettivi di ottimizzazione e le regole definite come vincoli, ad esempio l'inventario nei nodi di evasione per ottimizzare l'evasione degli ordini. DOM consente la definizione di più profili che permettono alle aziende di eseguire diverse strategie di ottimizzazione, in base al tipo di attività o del segmento di consumo. 

Nella figura seguente è illustrato il ciclo di vita di un ordine cliente in un sistema DOM.

![Ciclo di vita dell'ordine cliente nel contesto della gestione degli ordini distribuiti.](./media/flow.png "Ciclo di vita dell'ordine cliente nel contesto della gestione degli ordini distribuiti")

## <a name="set-up-dom"></a>Impostare DOM

1. Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**.
2. Nella scheda **Chiavi di configurazione**, espandere il nodo **Commerce**, quindi selezionare la casella di controllo **Gestione ordini distribuiti**.
3. Accedere a **Retail e Commerce \> Gestione ordini distribuiti \> Imposta \> Parametri DOM**.
4. Nella scheda **Generale**, impostare i seguenti valori:

    - **Abilita gestione ordini distribuiti**: impostare questa opzione su **Sì**.
    - **Confermare l'utilizzo di Bing Mappe per DOM**: impostare questa opzione su **Sì**.

        > [!NOTE]
        > È possibile impostare questa opzione su **Sì** solo se anche l'opzione **Abilita Bing Mappe** della scheda **Bing Mappe** della pagina **Parametri condivisi di Commerce** (**Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri condivisi di Commerce**) è impostata su **Sì** e se una chiave valida viene immessa nel campo **Chiave Bing Mappe**.
        >
        > Il portale [Bing Mappe Dev Center](https://www.bingmapsportal.com/) consente di limitare l'accesso alle chiavi API di Bing Mappe a un set di domini specificato. Con questa funzionalità, i clienti possono definire un set limitato di valori referrer o intervalli di indirizzi IP in base ai quali la chiave verrà convalidata. Le richieste provenienti dall'elenco Consenti verranno elaborate normalmente, mentre le richieste provenienti dall'esterno dell'elenco restituiranno una risposta di accesso negato. L'aggiunta della sicurezza del dominio alla chiave API è facoltativa e le chiavi lasciate inalterate continueranno a funzionare. L'elenco Consenti per una chiave è indipendente da tutte le altre chiavi in quanto permette di avere regole distinte per ciascuna chiave. La Gestione ordini distribuiti non supporta l'impostazione di proprietà correlate al dominio.

    - **Periodo di ritenuta in giorni**: specificare per quanto tempo i piani di evasione generati dalle esecuzioni DOM vengono conservati nel sistema. Il processo batch **Impostazione processo di eliminazione dati di evasione DOM** eliminerà qualsiasi piano di evasione precedente al numero di giorni specificato qui.
    - **Periodo di rifiuto (in giorni)**: specificare il tempo che deve trascorrere prima che una riga di ordine rifiutata possa essere assegnata alla stessa ubicazione.

5. Nella scheda **Risolutore**, impostare i seguenti valori:

    - **Numero massimo di tentativi di evasione automatica**: specificare il numero di volte in cui il motore DOM tenterà di associare una riga ordine a un'ubicazione. Se il motore DOM non associa una riga ordine a un'ubicazione entro il numero specificato di tentativi, la riga odine verrà contrassegnata come eccezione. Tale riga verrà quindi ignorata nelle esecuzioni future fino alla reimpostazione manuale dello stato.
    - **Raggio regione punto vendita locale**: immettere un valore. Questo campo consente di determinare come le posizioni vengono raggruppate e considerate uguali in termini di distanza. Ad esempio, se si immette **100**, ogni punto vendita o centro di distribuzione entro un raggio di 160 km dall'indirizzo di evasione verrà considerato equivalente in termini di distanza.
    - **Tipo di risolutore**: selezionare un valore. Con Commerce sono inclusi due tipi di risolutore: **Risolutore di produzione** e **Risolutore semplificato**. Per tutti i computer che eseguiranno la gestione degli ordini distribuiti (ovvero tutti i server che fanno parte del gruppo DOMBatch), è necessario che **Risolutore di produzione** sia selezionato. Il risolutore di produzione richiede la chiave di licenza speciale che, per impostazione predefinita, viene concessa e distribuita negli ambienti di produzione. Nei nuovi ambienti di livello 2 o superiore, il risolutore di produzione sarà già abilitato. Per gli ambienti non di produzione, la chiave di licenza deve essere distribuita manualmente. Per distribuire manualmente la chiave di licenza, effettuare le seguenti operazioni:

        1. In Microsoft Dynamics Lifecycle Services, aprire la raccolta Risorse condivise, selezionare **Modello** come tipo di cespite e scaricare il file **Licenza DOM**.
        1. Avviare Gestione Microsoft Internet Information Services (IIS), fare clic con il pulsante destro del mouse su **Sito Web di AOSService**, quindi selezionare **Esplora**. Viene visualizzata una finestra di Esplora risorse aperta su **\<AOS service root\>\\webroot**. Prendere nota del percorso \<AOS Service root\> perché verrà utilizzato nel passaggio successivo.
        1. Copiare il file di configurazione nella directory **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin**.
        1. Passare al client di Headquarters, quindi aprire la pagina **Parametri DOM**. Nella scheda **Risolutore**, nel campo **Tipo di risolutore**, selezionare **Risolutore di produzione**, quindi verificare che non venga visualizzato alcun messaggio di errore.

        > [!NOTE]
        > Il risolutore semplificato viene fornito in modo che i rivenditori al dettaglio possano provare la funzionalità DOM senza dover distribuire la licenza speciale. È consigliabile che le organizzazioni non utilizzino il risolutore semplificato negli ambienti di produzione.
        >
        > Il Risolutore di produzione migliora le prestazioni (il numero di ordini e righe ordine che è possibile gestire durante un'esecuzione) e la convergenza dei risultati (dal momento che un batch di ordini potrebbe non produrre il migliore risultato in alcuni scenari). Alcune regole come **Ordini parziali** e **Numero massimo di ubicazioni** richiedono il Risolutore di produzione.

6. Tornare a **Retail e Commerce \> Gestione ordini distribuiti \> Imposta \> Parametri DOM**.
7. Nella scheda **Sequenze numeriche**, assegnare le sequenze numeriche richieste alle diverse entità DOM.

    > [!NOTE]
    > Prima che le sequenze numeriche possano essere assegnate alle entità, devono essere definite nella pagina **Sequenze numeriche** (**Amministrazione organizzazione \> Sequenze numeriche \> Sequenze numeriche**).

8. La funzionalità DOM supporta la definizione di vari tipi di regole DOM e le organizzazioni possono configurare più regole, a seconda delle esigenze aziendali. Le regole DOM possono essere definite per un gruppo di posizioni o singole posizioni e per una categoria di prodotti, un prodotto o una variante specifica. Per raggruppare le posizioni che devono essere utilizzate per le regole DOM, effettuare le seguenti operazioni:

    1. Accedere a **Retail e Commerce \> Impostazione canale \> Gruppi di adempimento**.
    2. Selezionare **Nuovo** e immettere un nome e una descrizione per il nuovo gruppo.
    3. Selezionare **Salva**.
    4. Selezionare **Aggiungi riga** per aggiungere una singola ubicazione al gruppo. In alternativa, selezionare **Aggiungi righe** per aggiungere più ubicazioni.

    > [!NOTE]
    > In Commerce, versione 10.0.12 e successive, l'opzione **Possibilità di specificare le ubicazioni come "Spedizione" o "Ritiro" abilitata nel gruppo di evasione** deve essere abilitata nell'area di lavoro **Gestione funzionalità**.
    >
    > Questa funzionalità aggiunge nuove configurazioni nella pagina **Gruppo di evasione** in modo che sia possibile definire se il magazzino può essere utilizzato per la spedizione o se la combinazione magazzino/archivio può essere utilizzata per la spedizione, il ritiro o per entrambi. 
    >
    > Se si abilita la funzionalità, le opzioni disponibili per la selezione delle ubicazioni quando si creano gli ordini di spedizione o ritiro nel POS verranno aggiornate.
    >
    > L'abilitazione della funzionalità determina anche l'aggiornamento delle pagine nel POS quando sono selezionate le operazioni "spedisci tutto" o "spedisci selezionati".

9. Per definire le regole, accedere a **Retail e Commerce \> Gestione ordini distribuiti \> Imposta \> Gestisci regole**. Attualmente sono supportate le seguenti regole DOM:

    - **Regola fabbisogno minimo di scorte**: questo tipo di regola consente alle organizzazioni di "stanziare" una determinata quantità di prodotto per scopi diversi dall'evasione dell'ordine. Ad esempio, le organizzazioni potrebbero non desiderare che la gestione degli ordini distribuiti tenga in considerazione tutte le scorte disponibili in un punto vendita per l'evasione dell'ordine. Potrebbero invece decidere di riservare una parte delle scorte per i clienti occasionali. Quando viene utilizzato questo tipo di regola, è possibile definire le scorte minime da conservare per una categoria di prodotti, un unico prodotto o una variante prodotto per l'ubicazione o di gruppo di ubicazioni. È inoltre possibile definire l'inventario minimo tramite una gerarchia di categorie supplementare. Se un prodotto rientra in più categorie, viene data la massima importanza a una categoria supplementare per tutte le regole in cui è possibile utilizzare le categorie.
    - **Regola priorità ubicazione di evasione**: questo tipo di regola consente alle organizzazioni di definire una gerarchia di ubicazioni per stabilire la priorità che il motore DOM prende in considerazione quando tenta di identificare le ubicazioni di evasione per i prodotti specifici. L'intervallo valido delle priorità va da 1 a 10, dove 1 corrisponde alla priorità massima e 10 la priorità minima. Le ubicazioni con priorità più elevata verranno prese in considerazione prima delle ubicazioni con priorità più bassa. Se la regola viene definita come regola con vincolo non condizionale, gli ordini vengono associati solo a ubicazioni per cui sono definite le priorità. DOM dà la preferenza alla spedizione degli ordini completamente da un'unica ubicazione. Di conseguenza, se un intero ordine e le relative righe non sono disponibili in un'ubicazione con priorità 1, DOM tenta di evaderlo in un'ubicazione con priorità 2.
    - **Regola ordini parziali**: in Retail versione 10.0.5, il parametro **Evadere ordine solo da un'ubicazione** è stato modificato in **Numero massimo ubicazioni di evasione**. Il parametro precedente consentiva agli utenti di decidere se gli ordini possono essere evasi da una sola ubicazione o da quante più ubicazioni possibili. Il nuovo parametro consente agli utenti di specificare se l'evasione può provenire da un insieme definito di ubicazioni (fino a cinque) o da quante più ubicazioni possibile. Per tutte le opzioni, ad eccezione dell'evasione da un'ubicazione, DOM divide la riga, perché l'elaborazione dell'ordine avviene per riga. Questa regola funziona solo con il Risolutore di produzione.
    - **Regola ubicazione di evasione offline**: questa regola consente alle organizzazioni di specificare un'ubicazione o gruppo di ubicazioni come offline o non disponibile per la gestione degli ordini distribuiti, in modo che non sia possibile assegnare ordini da evadere a tali ubicazioni.
    - **Regola numero massimo di rifiuti**: questa regola consente alle organizzazioni di definire una soglia per i rifiuti. Quando la soglia viene raggiunta, il processore DOM contrassegna un ordine o una riga ordine come un'eccezione e li esclude da ulteriori elaborazioni. Per garantire le prestazioni, DOM non esamina la cronologia di tutti i rifiuti. 

        Una volta che le righe ordine sono assegnate a un'ubicazione, l'ubicazione può rifiutare una riga ordine assegnata, poiché per qualche motivo potrebbe non essere in grado di evadere tale riga. Le righe rifiutate vengono contrassegnate come un'eccezione e vengono inviate nuovamente nel pool per essere elaborate nell'esecuzione successiva. Durante l'esecuzione successiva, la gestione degli ordini distribuiti tenterà di assegnare la riga rifiutata a un'ubicazione diversa. Anche la nuova ubicazione può rifiutare la riga ordine assegnata. Il ciclo dell'assegnazione e del rifiuto può verificarsi più volte. Quando il numero di rifiuti raggiunge la soglia specificata, la gestione degli ordini distribuiti contrassegna la riga ordine come eccezione permanente e non selezionerà più tale riga per l'assegnazione. La riga ordine verrà presa in considerazione per una nuova assegnazione dalla gestione degli ordini distribuiti solo se un utente reimposta manualmente lo stato della riga ordine.

    - **Regola distanza massima**: questa regola consente alle organizzazioni di definire la distanza massima che può avere un'ubicazione o un gruppo di ubicazioni per evadere l'ordine. Se vengono definite regole per la distanza massima sovrapposte per un'ubicazione, la gestione degli ordini distribuiti applicherà la distanza massima inferiore definita per tale ubicazione.
    - **Regola numero massimo di ordini**: questa regola consente alle organizzazioni di definire il numero massimo di ordini che un'ubicazione o gruppo di ubicazioni può elaborare. Durante il processo di ottimizzazione, il sistema prende in considerazione gli ordini non spediti da tali ubicazioni. Questo controllo viene eseguito tra i profili. Di conseguenza, se i numeri massimi di ordini sovrapposti sono definiti tra i profili per la stessa ubicazione, il sistema prende in considerazione il numero massimo di ordini definito in tutti i profili. 

    Di seguito vengono riportati alcuni attributi comuni che possono essere definiti per tutti i tipi di regola precedenti:

    - **Data di inizio** e **Data di fine**: puoi utilizzare questi campi per definire la validità della data di ogni regola.
    - **Disabilitata**: solo le regole con valore **No** in questo campo vengono prese in considerazione durante un'esecuzione DOM.
    - **Vincolo rigido**: una regola può essere definita come un vincolo rigido o meno. Ogni esecuzione DOM passa attraverso due iterazioni. Nella prima interazione, ogni regola viene trattata come una regola di vincolo rigido, indipendentemente dall'impostazione di questo campo. In altre parole, viene applicata ogni regola. La sola eccezione è rappresentata dalla regola **Priorità ubicazione**. Nella seconda iterazione, le regole che non sono state definite come regole di vincolo rigido vengono rimosse e l'ordine o le righe ordine che non erano assegnati a ubicazioni quando tutte le regole erano applicate vengono ora assegnati alle ubicazioni.

10. I profili di evasione vengono utilizzati per raggruppare una raccolta di regole, persone giuridiche, origini di ordini cliente e modalità di consegna. Ogni esecuzione DOM è dedicata a un profilo di evasione specifico. In questo modo, le organizzazioni possono definire ed eseguire un set di regole per un set di persone giuridiche, sugli ordini che includono origini di ordini cliente e modalità di consegna specifiche. Pertanto, se set di regole diversi devono essere eseguiti per diversi set di origini di ordine cliente o modalità di consegna, i profili di evasione possono essere definiti di conseguenza. Per impostare i profili di evasione, effettuare le seguenti operazioni:  

    1. Accedere a **Retail e Commerce \> Gestione ordini distribuiti \> Imposta \> Profili di evasione**.
    2. Selezionare **Nuovo**.
    3. Immettere valori nei campi **Profilo** e **Descrizione**.
    4. Impostare l'opzione **Applica automaticamente il risultato**. Se si imposta questa opzione su **Sì**, i risultati dell'esecuzione DOM per il profilo verranno automaticamente applicati alle righe di ordine cliente. Se viene impostata su **No**, i risultati possono essere visualizzati solo nel piano di evasione. Non verranno applicati alle righe di ordine cliente.
    5. Se si desidera che il profilo DOM venga eseguito per gli ordini che includono ogni origine di ordine cliente, ad esempio quelli in cui l'origine dell'ordine cliente non è definita, impostare l'opzione **Elabora ordini con origine vendite vuota** su **Sì**. Per eseguire il profilo solo per alcune origini di ordini cliente, è possibile definirle nella pagina **Origini di vendita**, come descritto più avanti.

        > [!NOTE]
        > In Commerce versione 10.0.12, l'opzione **Possibilità di assegnare un gruppo di evasione a un profilo di evasione** deve essere impostata nell'area di lavoro **Gestione funzionalità**. Questa funzionalità consente di specificare un elenco di magazzini che DOM deve prendere in considerazione quando l'ottimizzazione viene eseguita con un profilo di evasione ordini. Se l'elenco di magazzini non è specificato, DOM esamina tutti i magazzini delle persone giuridiche definite nel profilo.
        >
        > Questa funzionalità aggiunge una nuova configurazione nella pagina **Profilo di evasione** che può essere associata a un singolo gruppo di evasione. 
        >
        > Se si seleziona il gruppo di evasione, le regole DOM per il profilo di evasione corrispondente verranno applicate in modo efficiente rispetto ai magazzini di spedizione inclusi nel gruppo di evasione. 
        > 
        > Per utilizzare in modo efficace questa funzionalità, verificare che esista un gruppo di evasione che contenga tutti i magazzini di spedizione, quindi associare tale gruppo al profilo di evasione.

    6. Nella Scheda dettaglio **Persone giuridiche**, selezionare **Aggiungi**, quindi selezionare una persona giuridica.
    7. Nella Scheda dettaglio **Regole**, selezionare **Aggiungi**, quindi selezionare la regola da collegare al profilo.
    8. Ripetere i due passaggi precedenti fino a che tutte le regole obbligatorie non vengono associate al profilo.
    9. Selezionare **Salva**.
    10. Nel riquadro Azioni, nella scheda **Imposta**, selezionare **Modalità di consegna**.
    11. Nella pagina **Modalità di consegna**, selezionare **Nuovo**.
    12. Nel campo **Società**, selezionare la persona giuridica. L'elenco delle società è limitato alle persone giuridiche aggiunte in precedenza.
    13. Nel campo **Modalità di consegna**, selezionare la modalità di consegna da associare a questo profilo. La modalità di consegna non può essere associata a più profili attivi.
    14. Ripetere i due passaggi precedenti fino a che tutte le modalità di consegna obbligatorie non vengono associate al profilo.
    15. Chiudere la pagina **Modalità di consegna**.
    16. Nel riquadro Azioni, nella scheda **Imposta**, selezionare **Origini ordini cliente**.
    17. Nella pagina **Origini vendite**, selezionare **Nuovo**.
    18. Nel campo **Società**, selezionare la persona giuridica. L'elenco delle società è limitato alle persone giuridiche aggiunte in precedenza.
    19. Nel campo **Origine vendite**, selezionare l'origine vendita da associare a questo profilo. L'origine della vendita non può essere associata a più profili attivi.
    20. Ripetere i due passaggi precedenti fino a che tutte le origini di vendita obbligatorie non vengono associate al profilo.
    21. Chiudere la pagina **Origini vendite**.
    22. Impostare l'opzione **Abilita profilo** su **Sì**. Se sono presenti errori nell'impostazione, viene visualizzato un messaggio di avviso.

## <a name="dom-processing"></a>Elaborazione DOM

La gestione degli ordini distribuiti verrà eseguita solo in un processo batch. Per configurare il processo batch per le esecuzioni DOM, effettuare le seguenti operazioni.

1. Accedere a **Retail e Commerce \> Gestione ordini distribuiti \> Elaborazione batch \> Impostazione elaborazione del processore DOM**.
1. Nella Scheda dettaglio **Parametri**, nel campo **Profilo di evasione**, selezionare un profilo a fronte del quale eseguire la gestione degli ordini distribuiti.
1. Nella Scheda dettaglio **Esecuzione in background**, nel campo **Gruppo batch**, selezionare un gruppo batch configurato.
1. Nel campo **Descrizione attività**, immettere un nome per il processo batch.
1. Selezionare **Ricorrenza** e definire la ricorrenza del processo batch.
1. Selezionare **OK**.

Al momento dell'elaborazione, la gestione degli ordini distribuiti prenderà in considerazione l'ordine e le righe ordine come descritto di seguito:

- Le righe ordine che soddisfano i criteri per le origini degli ordini cliente, le modalità di consegna e la persona giuridica come definito nel profilo DOM e che soddisfano inoltre uno di questi criteri:

    - Vengono create dai canali di commercio.
    - Non sono state mai associate dalla gestione degli ordini distribuiti.
    - Sono state già associate dalla gestione degli ordini distribuiti, ma sono contrassegnate come eccezioni e il numero di tentativi è inferiore alla soglia massima.
    - La modalità di consegna non corrisponde al prelievo o alla consegna elettronica.
    - Non sono contrassegnate per la consegna.
    - Non vengono escluse manualmente.

- Ordini che non sono in attesa

Dopo aver applicano le regole, i vincoli delle scorte e l'ottimizzazione, la gestione degli ordini distribuiti seleziona l'ubicazione più vicina all'indirizzo di consegna del cliente. DOM converte gli indirizzi di tipo **Consegna** in valori di latitudine e longitudine. La soluzione converte quindi l'indirizzo di consegna nell'ordine cliente in valori di latitudine e longitudine e aggiorna tali valori dell'indirizzo per un uso futuro. Per determinare valori precisi di latitudine e longitudine in base a informazioni su indirizzo, città e codice postale, DOM dipende da Bing Maps.

DOM utilizza l'API Bing Maps per calcolare la distanza aerea o stradale, a seconda delle impostazioni, quindi utilizza queste informazioni per determinare il costo della spedizione. Il modello di ottimizzazione dà la priorità all'evasione di un ordine completo in un'unica ubicazione. Anche se parte di un ordine è disponibile nella stessa città o codice postale, il modello è stato ottimizzato per ridurre il numero di spedizioni. 

DOM cerca le scorte disponibili visualizzando l'inventario nelle entità Magazzino V2. Durante ogni esecuzione batch, DOM suddivide gli ordini in batch, a seconda del valore del parametro **Processore DOM** delle attività definite nel profilo. Tale parametro ha un valore predefinito pari a **2000**. Ad esempio, se 10.000 righe ordine vengono ottimizzate in un'esecuzione e il parametro **Processore DOM** è impostato sul valore predefinito **2000**, DOM crea cinque batch elaborati contemporaneamente. I piani di adempimento vengono quindi ottenuti dallo strumento di ottimizzazione e applicati alla riga. Se la riga ordine deve essere suddivisa tra due ubicazioni, DOM garantisce che i prezzi e le imposte siano ripartiti in modo adeguato tra le righe.

![Criteri dell'ordine cliente.](./media/ordercriteria.png "Criteri dell'ordine cliente")

## <a name="results-of-dom-runs"></a>Risultati delle esecuzioni DOM

Se il profilo di evasione è impostato su **Applicazione automatica**, i risultati dell'esecuzione verranno automaticamente applicati alle righe ordine cliente e il piano di evasione può essere visualizzato separatamente. Tuttavia, se il profilo di evasione non è impostato su **Applicazione automatica**, i risultati dell'esecuzione possono essere visualizzati solo dalla vista del piano di evasione. 

Per visualizzare tutti i piani di evasione generati, effettuare le operazioni indicate di seguito.

1. Accedere a **Retail e Commerce \> Gestione ordini distribuiti \> Gestione ordini distribuiti**.
2. Nell'area di lavoro **Gestione ordini distribuiti**, selezionare il riquadro **Piani di evasione**.
3. Selezionare l'ID del relativo piano di evasione degli ordini per visualizzare il piano di evasione.

    Nella sezione dei dettagli dell'ordine del piano di esecuzione vengono mostrate le righe ordine cliente originali che facevano parte dell'esecuzione. Oltre ai campi standard della riga ordine cliente, la sezione dei dettagli dell'ordine include anche i seguenti tre campi correlati a DOM:

    - **Tipo di evasione**: questo campo indica se la riga ordine cliente è interamente associata, parzialmente associata o non associata affatto a un'ubicazione.
    - **Dividi**: questo campo indica se una riga ordine cliente è stata divisa e associata a ubicazioni diverse.
    - **Numero di ubicazioni di evasione**: questo campo indica il numero di righe di evasione create per una riga ordine cliente (in base al numero di ubicazioni a cui la riga ordine cliente originale era associata).

    Nella sezione dei dettagli di evasione dell'ordine viene mostrata l'assegnazione delle righe ordine cliente originali a ubicazioni diverse, con le rispettive quantità.

## <a name="order-line-actions-and-statuses"></a>Azioni e stati delle righe ordine

Di seguito vengono descritte le impostazioni della riga ordine. Per aprire la riga ordine, accedere a **Retail e Commerce \> Clienti \> Tutti gli ordini cliente**.

- Se si imposta l'opzione **Escludi dall'elaborazione DOM** nella scheda **Generale** della riga ordine cliente su **Sì**, l'ordine o la riga ordine verrà escluso dall'elaborazione DOM.
- Il campo **Stato DOM** nella scheda **Generale** della riga ordine cliente può essere impostato su uno dei seguenti valori:

    - **Nessuno**: la riga ordine non è stata mai associata.
    - **Completo**: la riga ordine è stata associata e assegnata a un'ubicazione.
    - **Eccezione**: la riga ordine è stata associata ma non può essere assegnata a un'ubicazione. Le eccezioni sono più sottotipi che possono essere visualizzati dall'area di lavoro DOM:

        - **Nessuna quantità disponibile**: non sono presenti scorte disponibili a cui assegnare l'ordine nelle ubicazioni.
        - **Numero massimo di rifiuti**: la riga ordine ha raggiunto la soglia massima del numero di rifiuti.
        - **Conflitto di modifica dei dati**: la riga ordine cliente è stata modificata dal momento dell'associazione dell'ordine. Di conseguenza, il piano di evasione non può essere applicato all'ordine.
        - **Eccezione specifica della riga ordine**: sono presenti più eccezioni sulla riga ordine.

- Durante la registrazione dell'ordine cliente, la gestione degli ordini distribuiti può essere eseguita in una modalità interattiva. Quando si registra una riga ordine, dopo aver specificato il prodotto e la quantità, è possibile selezionare **Aggiorna riga**, quindi in **DOM**, selezionare **Suggerimento ubicazione di evasione**. Quindi viene visualizzato un elenco di ubicazioni basato sulle regole DOM in grado di evadere la quantità della riga ordine. L'elenco è ordinato per distanza. Selezionare un'ubicazione per impostare il sito e magazzino corrispondenti nella riga ordine cliente. Per utilizzare al meglio questa funzionalità, è necessario un profilo di evasione attivo che corrisponda all'origine vendita e alla modalità di consegna sulla riga vendita.
- Per visualizzare i registri di esecuzione DOM per una riga ordine cliente, selezionare **Riga ordine cliente**, quindi in **DOM**, selezionare **Visualizza log DOM**. I registri DOM mostrano tutti gli eventi e i registri generati dall'esecuzione DOM. I registri consentono di capire perché un'ubicazione specifica è stata assegnata alla riga ordine e quali regole e vincoli sono stati considerati come parte dell'assegnazione. Nella scheda **Gestire**, i registri DOM sono disponibili anche a livello di intestazione dell'ordine cliente.

## <a name="run-a-clean-up-job-for-dom-fulfillment-plans"></a>Eseguire un processo di pulitura per i piani di evasione DOM

Durante l'elaborazione DOM vengono creati piani di evasione. Il sistema conserva nel tempo numerosi piani di evasione. Per gestire il numero di piani di evasione che devono essere conservati dal sistema, è possibile configurare un processo batch per l'eliminazione dei piani di evasione più datati, in base al valore **Periodo di ritenuta in giorni**.

1. Accedere a **Retail e Commerce \> Gestione ordini distribuiti \> Elaborazione batch \> Impostazione processo di eliminazione dati di evasione DOM**. 
1. Nel campo **Gruppo batch** selezionare un gruppo batch configurato.
1. Selezionare **Ricorrenza** e definire la ricorrenza del processo batch.
1. Selezionare **OK**.

## <a name="more-information"></a>Ulteriori informazioni

Di seguito vengono illustrati alcuni aspetti da considerare quando si utilizza la funzionalità DOM:

- Attualmente, la gestione degli ordini distribuiti cerca solo gli ordini creati dai canali di commercio. Gli ordini cliente vengono identificati come ordini cliente se l'opzione **Vendita Commerce** è impostata su **Sì**.
- Microsoft non ha testato la gestione degli ordini distribuiti con funzionalità avanzate di gestione del magazzino. Di conseguenza, i clienti e partner devono prestare attenzione a determinare se la gestione degli ordini distribuiti è compatibile con le funzionalità avanzate di gestione del magazzino e i processi a esse pertinenti. I processi di magazzino avanzati consentono di utilizzare dimensioni configurabili, ad esempio lo stato dell'inventario, che non forniscono una comprensione accurata dell'inventario disponibile. DOM fornisce un metodo estensibile per configurare l'inventario disponibile per le implementazioni che utilizzano processi di magazzino avanzati. Tale metodo può essere utilizzato per lavorare con valori personalizzati di stato dell'inventario e con altre dimensioni.

    L'estendibilità in DOM è limitata perché l'ottimizzazione viene messa in atto nel modello MIP predefinito che prende in considerazione l'ottimizzazione e i suoi vincoli. Sono già disponibili diversi punti estendibili per la configurazione dell'inventario e l'ottimizzazione della post-elaborazione. I profili DOM possono differire in base all'origine delle vendite e alla modalità di consegna. L'origine dell'ordine cliente può essere configurata durante l'inserimento dell'ordine stesso e, in base a tali valori, possono essere utilizzate diverse strategie di ottimizzazione. DOM supporta anche la creazione di processi batch personalizzati in grado di accettare l'attività del processore DOM come input e consentire il passaggio del profilo come parametro. Di conseguenza, è possibile eseguire ottimizzazioni in sequenza per supportare diversi scenari aziendali.

- La gestione degli ordini distribuiti sarà disponibile solo nella versione cloud di Commerce. Non è supportata nelle distribuzioni locali.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
