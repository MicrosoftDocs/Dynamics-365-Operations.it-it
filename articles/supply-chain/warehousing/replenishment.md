---
title: Panoramica del rifornimento
description: In questo argomento vengono descritte le strategie di rifornimento disponibili per i magazzini che utilizzano la funzionalità disponibile in Gestione magazzino.
author: Mirzaab
manager: AnnBe
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 90043
ms.assetid: 49fa97eb-8e10-49a5-9261-1e393159f178
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7aa17df3c3632c89f35a69022084bbd9f4171f36
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076363"
---
# <a name="replenishment-overview"></a>Panoramica del rifornimento

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le strategie di rifornimento disponibili per i magazzini che utilizzano la funzionalità disponibile in Gestione magazzino. Le informazioni in questo argomento non sono applicabili alla soluzione di immagazzinaggio disponibile in Gestione articoli.

Sono disponibili le seguenti strategie di rifornimento:

- **Rifornimento basato su domanda ondata**: questa strategia crea il lavoro di rifornimento per carichi o ordini in uscita se scorte non sono disponibili quando il lavoro viene creato dall'ondata. Ad esempio, se la quantità necessaria per un ordine cliente non è disponibile durante l'elaborazione di un'ondata, è possibile creare il lavoro di rifornimento.
- **Rifornimento basato su quantità minima e massima**: questa strategia utilizza i limiti di stoccaggio minimo e massimo per determinare quando rifornire le ubicazioni. I criteri di articolo e di ubicazione definiscono il magazzino che viene valutato per il rifornimento. I modelli di rifornimento basato su quantità minima e massima sono il meccanismo principale per il mantenimento di livelli ottimali di ubicazioni di prelievo. Per aiutare la disponibilità di scorte accessibili sufficienti a soddisfare la domanda ondata, è possibile utilizzare il rifornimento basato sulla domanda come integrazione tra i cicli di rifornimento minimo/massimo.
- **Rifornimento basato sulla domanda di carico**: questa strategia somma la domanda di diversi carichi e crea il lavoro di rifornimento necessario per lo stoccaggio delle ubicazioni di prelievo pertinenti. Questa strategia consente di garantire che i carichi creati possono essere prelevati nel magazzino dopo il rilascio.
- **Rifornimento immediato**: questa strategia rifornisce il magazzino prima dell'eseuczione di un'ondata se l'allocazione non riesce per una riga della direttiva di ubicazione con un modello di rifornimento. 

Tutte e quattro le strategie creano lavoro di rifornimento, basato su un modello di rifornimento.

## <a name="wave-demand-replenishment"></a>Rifornimento basato sulla domanda ondata
Il rifornimento basato sulla domanda ondata crea il lavoro di rifornimento in base alla domanda, se la quantità richiesta per ordini di produzione, kanban, ordini in uscita o carichi non è disponibile quando un'ondata crea il lavoro. Il modello di rifornimento contiene informazioni relative ai criteri degli articoli, l'unità di misura, l'incremento della domanda e l'ubicazione. 

Direttive di ubicazione vengono utilizzate per determinare l'ubicazione da rifornire. Per collegare queste direttive di ubicazione al modello di rifornimento, utilizzare il campo **Codice direttiva**. Se il campo **Codice direttiva** non è impostato, query vengono utilizzate per determinare quale direttiva di ubicazione deve essere utilizzata. Si noti che se non è specificato un codice di direttiva nel modello di rifornimento e la direttiva di ubicazione ha un codice direttiva, la direttiva di ubicazione verrà ignorata, anche se la query sulla direttiva di ubicazione è corretta. Le direttive di ubicazione prelievo vengono utilizzate per determinare dove ottenere le scorte per il rifornimento. 

Oltre a creare un modello, è necessario specificare alcune impostazioni di rifornimento nel modello di ondata. Il modello di ondata deve contenere un passaggio di ondata di rifornimento che viene eseguito solo se l'allocazione di un articolo non riesce. Questo passaggio di ondata di rifornimento utilizza un codice di passaggio ondata per determinare quale modello di rifornimento deve essere utilizzato. Oltre a disporre di un passaggio di ondata per il rifornimento, è necessario assicurarsi che **rifornisci** sia selezionato nella sezione **Metodi** del modello di ondata. 

La pagina **Modello rifornimento** include una casella di controllo **Consenti domanda ondata per utilizzare le quantità non prenotate**. Selezionare questa casella di controllo se il rifornimento basato sulla domanda deve consentire la deduzione delle quantità non prenotate dal lavoro generato dal modello di rifornimento selezionato. Questa casella di controllo deve essere impostata per ogni modello di rifornimento esistente per consentire ai modelli di rifornimento basato sulla domanda di utilizzare questa logica. Quando il rifornimento basato sulla domanda è attivato nel magazzino, dedurrà la domanda dal lavoro di rifornimento esistente che ha quantità non prenotate, se il lavoro deriva dai modelli di rifornimento in cui la casella di controllo **Consenti domanda ondata per utilizzare le quantità non prenotate** è selezionata.

**Unità di rifornimento** è l'unità minima da rifornire. Deve essere un numero intero multiplo dell'unità. Il sistema arrotonda all'unità massima possibile durante la creazione del lavoro.

Il rifornimento della domanda è supportato per ordini cliente, ordini di trasferimento, ordini di produzione e kanban. 

## <a name="minmax-replenishment"></a>Rifornimento basato su quantità minima e massima
Nel rifornimento basato su quantità minima e massima, le scorte vengono rifornite in modo da rientrare nei limiti minimo e massimo impostati. In genere, questo processo si verifica una volta al giorno per aiutare a garantire che tutte le ubicazioni di prelievo vengono rifornite al livello massimo prima dell'avvio di prelievo. 

Le quantità minima e massima vengono impostate in un modello di rifornimento. Molte delle altre impostazioni nel modello sono simili alle impostazioni nei modelli utilizzati nel rifornimento basato sulla domanda ondata. Il modello deve contenere una riga per ogni articolo e ubicazione. Quando si effettua il rifornimento mediante il processo batch, il sistema valuta se il rifornimento è necessario utilizzando la sequenza in cui sono organizzate le righe. 

Si noti che la strategia di rifornimento basato su quantità minima e massima non può rifornire un'ubicazione vuota, a meno che l'ubicazione è impostata come ubicazione fissa per l'articolo. Se l'ubicazione da rifornire non è un'ubicazione fissa, il sistema non può determinare quale articolo deve essere rifornito. Pertanto, almeno una certa quantità di scorte è necessaria prima del rifornimento.

## <a name="load-demand-replenishment"></a>Rifornimento domanda di carico
Il rifornimento basato sulla domanda di carico somma la domanda di diversi carichi e crea il lavoro di rifornimento necessario per lo stoccaggio delle ubicazioni di prelievo pertinenti. Il rifornimento basato sulla domanda di carico è simile al rifornimento basato sulla domanda ondata in molti modi. La differenza principale è come e quando vengono eseguiti i due tipi di rifornimento. Come per rifornimento basato su quantità minima e massima, il rifornimento basato sulla domanda di carico viene eseguito utilizzando un processo batch. Per impostare il processo batch, nella pagina **Rifornimento domanda di carico**, selezionare il modello di rifornimento da utilizzare e impostare una query di filtro per specificare quali carichi vengono utilizzati per determinare la domanda. La query di ubicazione definisce le ubicazioni da cui sottrarre le quantità disponibili per soddisfare la domanda aggregata dei carichi.

## <a name="immediate-replenishment"></a>Rifornimento immediato
Anziché sommare la domanda alla fine di un processo di allocazione ed effettuare il rifornimento in base alla quantità sommata, è possibile applicare la strategia di rifornimento immediato. Quando si utilizza questa strategia, il magazzino può essere rifornito immediatamente dopo l'allocazione per una riga della direttiva di ubicazione non riuscita. Di conseguenza, è possibile impostare il rifornimento in modo che sia limitato da specifiche unità e che utilizzi le quantità impostate per specifiche ubicazioni.

## <a name="replenishment-prerequisites"></a>Prerequisiti di rifornimento

|      Prerequisito       |                                                                                                                                descrizione                                                                                                                                 |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          Articolo           |                                                                                                        Gli articoli devono essere abilitati per i processi di gestione magazzino.                                                                                                        |
|        Magazzino        | Il magazzino deve essere abilitato per i processi di gestione magazzino. Per abilitare un magazzino per i processi di gestione magazzino, nella pagina <strong>Magazzino</strong> selezionare il magazzino, quindi selezionare l'opzione <strong>Usa processi di gestione magazzino</strong>. |
| Modelli rifornimento |                                                                   Almeno un modello di rifornimento deve essere impostato per il rifornimento basato su quantità minima e massima, rifornimento basato sulla domanda ondata o rifornimento basato sulla domanda di carico.                                                                   |
|        Percorsi        |                                                                                                       Le ubicazioni devono essere create e connesse a un profilo ubicazione.                                                                                                       |
|    Profili ubicazione    |                                                                                                        I profili ubicazione sono necessari per creare le ubicazioni.                                                                                                        |
|   Direttive ubicazione   |                                                       Le direttive di ubicazione sono necessarie per guidare il lavoro nelle ubicazioni in cui è richiesto il rifornimento e nelle ubicazioni da cui provengono le scorte.                                                        |
|     Modelli di lavoro      |                                                   Modelli di lavoro di tipo <strong>Rifornimento</strong> sono necessari per creare il lavoro di rifornimento in modo che le scorte possano essere spostate nell'ubicazione desiderata.                                                    |

