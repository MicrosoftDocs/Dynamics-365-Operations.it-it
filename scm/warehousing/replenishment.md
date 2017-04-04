---
title: Rifornimento
description: "In questo articolo vengono descritte le strategie di rifornimento disponibili per i magazzini che utilizzano la funzionalità disponibile in Gestione magazzino."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSReplenishmentTemplates
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 90043
ms.assetid: 49fa97eb-8e10-49a5-9261-1e393159f178
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 77b895e7f7edd6f22ee960ba2ec4bdd2931c29f8
ms.lasthandoff: 03/31/2017


---

# <a name="replenishment"></a>Rifornimento

In questo articolo vengono descritte le strategie di rifornimento disponibili per i magazzini che utilizzano la funzionalità disponibile in Gestione magazzino.

In questo articolo vengono descritte le strategie di rifornimento disponibili per i magazzini che utilizzano la funzionalità disponibile in Gestione magazzino. Le informazioni non sono applicabili alla soluzione di immagazzinaggio disponibile in Gestione articoli. Sono disponibili tre strategie di rifornimento:

-   **Rifornimento basato su domanda ondata**: questa strategia crea il lavoro di rifornimento per carichi o ordini in uscita se scorte non sono disponibili quando il lavoro viene creato dall'ondata. Ad esempio, se la quantità necessaria per un ordine cliente non è disponibile durante l'elaborazione di un'ondata, è possibile creare il lavoro di rifornimento.
-   **Rifornimento basato su quantità minima e massima**: questa strategia utilizza i limiti di stoccaggio minimo e massimo per determinare quando rifornire le ubicazioni. I criteri di articolo e di ubicazione definiscono il magazzino che viene valutato per il rifornimento. I modelli di rifornimento basato su quantità minima e massima sono il meccanismo principale per il mantenimento di livelli ottimali di ubicazioni di prelievo. Per aiutare la disponibilità di scorte accessibili sufficienti a soddisfare la domanda ondata, è possibile utilizzare il rifornimento basato sulla domanda come integrazione tra i cicli di rifornimento minimo/massimo.
-   **Rifornimento basato sulla domanda di carico**: questa strategia somma la domanda di diversi carichi e crea il lavoro di rifornimento necessario per lo stoccaggio delle ubicazioni di prelievo pertinenti. Questa strategia consente di garantire che i carichi creati possono essere prelevati nel magazzino dopo il rilascio.

Tutte e tre le strategie creano lavoro di rifornimento, basato su un modello di rifornimento.

## <a name="wave-demand-replenishment"></a>Rifornimento basato sulla domanda ondata
Il rifornimento basato sulla domanda ondata crea il lavoro di rifornimento in base alla domanda, se la quantità richiesta per carichi o ordini in uscita non è disponibile quando un'ondata crea il lavoro. Il modello di rifornimento contiene informazioni relative ai criteri degli articoli, l'unità di misura, l'incremento della domanda e l'ubicazione. 

Direttive di ubicazione vengono utilizzate per determinare l'ubicazione da rifornire. Per collegare queste direttive di ubicazione al modello di rifornimento, utilizzare il campo **Codice direttiva**. Se il campo **Codice direttiva** non è impostato, query vengono utilizzate per determinare quale direttiva di ubicazione deve essere utilizzata. Si noti che se non è specificato un codice di direttiva nel modello di rifornimento e la direttiva di ubicazione ha un codice direttiva, la direttiva di ubicazione verrà ignorata, anche se la query sulla direttiva di ubicazione è corretta. Le direttive di ubicazione prelievo vengono utilizzate per determinare dove ottenere le scorte per il rifornimento. 

Oltre a creare un modello, è necessario specificare alcune impostazioni di rifornimento nel modello di ondata. Il modello di ondata deve contenere un passaggio di ondata di rifornimento che viene eseguito solo se l'allocazione di un articolo non riesce. Questo passaggio di ondata di rifornimento utilizza un codice di passaggio ondata per determinare quale modello di rifornimento deve essere utilizzato. Oltre a disporre di un passaggio di ondata per il rifornimento, è necessario assicurarsi che **rifornisci** è selezionato nella sezione **Metodi** del modello di ondata. 

La pagina **Modello rifornimento** include una casella di controllo **Consenti domanda ondata per utilizzare le quantità non prenotate**. Questa deve essere selezionata se si desidera consentire al rifornimento basato sulla domanda di dedurre le quantità non prenotate dal lavoro generato dal modello di rifornimento selezionato. Questa casella di controllo deve essere impostata per ogni modello di rifornimento esistente per consentire ai modelli di rifornimento basato sulla domanda di utilizzare questa logica. Quando il rifornimento basato sulla domanda è attivato nel magazzino, dedurrà la domanda dal lavoro di rifornimento esistente che ha quantità non prenotate, se il lavoro deriva dai modelli di rifornimento in cui la casella di controllo **Consenti domanda ondata per utilizzare le quantità non prenotate** è selezionata.

## <a name="minmax-replenishment"></a>Rifornimento basato su quantità minima e massima
Nel rifornimento basato su quantità minima e massima, le scorte vengono rifornite in modo da rientrare nei limiti minimo e massimo impostati. In genere, questo processo si verifica una volta al giorno per aiutare a garantire che tutte le ubicazioni di prelievo vengono rifornite al livello massimo prima dell'avvio di prelievo. 

Le quantità minima e massima vengono impostate in un modello di rifornimento. Molte delle altre impostazioni nel modello sono simili alle impostazioni nei modelli utilizzati nel rifornimento basato sulla domanda ondata. Il modello deve contenere una riga per ogni articolo e ubicazione. Quando si effettua il rifornimento mediante il processo batch, Microsoft Dynamics 365 for Operations valuterà se il rifornimento è necessario, nella sequenza in cui sono organizzate le righe. 

Si noti che la strategia di rifornimento basato su quantità minima e massima non può rifornire un'ubicazione vuota, a meno che l'ubicazione è impostata come ubicazione fissa per l'articolo. Se l'ubicazione da rifornire non è un'ubicazione fissa, Dynamics 365 for Operations non può determinare quale articolo rifornire. Pertanto, almeno una certa quantità di scorte è necessaria prima del rifornimento.

## <a name="load-demand-replenishment"></a>Rifornimento domanda di carico
Il rifornimento basato sulla domanda di carico somma la domanda di diversi carichi e crea il lavoro di rifornimento necessario per lo stoccaggio delle ubicazioni di prelievo pertinenti. Il rifornimento basato sulla domanda di carico è simile al rifornimento basato sulla domanda ondata in molti modi. La differenza principale è come e quando vengono eseguiti i due tipi di rifornimento. Come per rifornimento basato su quantità minima e massima, il rifornimento basato sulla domanda di carico viene eseguito utilizzando un processo batch. Per impostare il processo batch, nella pagina **Rifornimento domanda di carico**, selezionare il modello di rifornimento da utilizzare e impostare una query di filtro per specificare quali carichi vengono utilizzati per determinare la domanda. La query di ubicazione definisce le ubicazioni da cui sottrarre le quantità disponibili per soddisfare la domanda aggregata dei carichi.

## <a name="replenishment-prerequisites"></a>Prerequisiti di rifornimento
| Prerequisito            | Descrizione                                                                                                                                                                                                                                        |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Articolo                    | Gli articoli devono essere abilitati per i processi di gestione magazzino.                                                                                                                                                                                       |
| Magazzino               | Il magazzino deve essere abilitato per i processi di gestione magazzino. Per abilitare il magazzino per i processi di gestione magazzino, nella pagina **Magazzino** selezionare il magazzino, quindi selezionare l'opzione **Usa processi di gestione magazzino**. |
| Modelli rifornimento | Almeno un modello di rifornimento deve essere impostato per il rifornimento basato su quantità minima e massima, rifornimento basato sulla domanda ondata o rifornimento basato sulla domanda di carico.                                                                                                             |
| Percorsi               | Le ubicazioni devono essere create e connesse a un profilo ubicazione.                                                                                                                                                                                     |
| Profili ubicazione       | I profili ubicazione sono necessari per creare le ubicazioni.                                                                                                                                                                                       |
| Direttive ubicazione     | Le direttive di ubicazione sono necessarie per guidare il lavoro nelle ubicazioni in cui è richiesto il rifornimento e nelle ubicazioni da cui provengono le scorte.                                                                                     |
| Modelli di lavoro          | Modelli di lavoro di tipo **Rifornimento** sono necessari per creare il lavoro di rifornimento in modo che le scorte possano essere spostate nell'ubicazione desiderata.                                                                                           |




