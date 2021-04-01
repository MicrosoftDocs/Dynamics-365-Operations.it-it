---
title: Programmazione processo
description: Questo articolo fornisce informazioni sulla programmazione processi, ovvero una forma più dettagliata di programmazione della programmazione operazioni. È possibile utilizzare la programmazione processi per pianificare i singoli processi o ordini di lavorazione e controllare l'ambiente di produzione.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19431
ms.assetid: aef37341-91d8-4263-80eb-35d9584be156
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c71f85cac11c4f11d63ba8f55932ec8f0520d924
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246119"
---
# <a name="job-scheduling"></a>Programmazione processo

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulla programmazione processi, ovvero una forma più dettagliata di programmazione della programmazione operazioni. È possibile utilizzare la programmazione processi per pianificare i singoli processi o ordini di lavorazione e controllare l'ambiente di produzione.

È possibile utilizzare la programmazione processi per pianificare i singoli processi o ordini di lavorazione e controllare l'ambiente di produzione. La programmazione processi consente di suddividere ciascuna operazione in singoli processi o singole attività. I processi vengono quindi assegnati alle risorse operative che li eseguiranno. La programmazione processi consente inoltre di sincronizzare tutti i processi a cui fa riferimento il processo selezionato. È possibile specificare una data e un'ora di inizio o fine per il processo, quindi eseguire la programmazione. L'ora specificata può essere l'ora di inizio o di fine a seconda della direzione di programmazione. Questa funzionalità viene utilizzata, ad esempio, quando un processo può essere eseguito solo in un computer alla volta o quando si desidera ottimizzare il processo che viene eseguito per ciascuna risorsa.

## <a name="tasks-in-the-job-scheduling-process"></a>Attività nella programmazione processi
La programmazione processi include le seguenti attività:

-   Suddividere le operazioni in processi.
-   Programmare i processi in base alle date e alle ore per le risorse specificate per l'operazione correlata.
-   Calcolare le ore di inizio e di fine per ciascun processo. È possibile utilizzare la funzione di capacità limitata per assicurarsi che non si verifichi una sovrapposizione di orari.
-   Stabilire in quali risorse nel gruppo di risorse eseguire il processo. Questa attività richiede che un gruppo di risorse venga specificato per un'operazione. La programmazione processi consente di selezionare le risorse o i gruppi di risorse in base al lead time più breve e di considerare tutte le prenotazioni precedenti delle risorse.
-   Esplodere le operazioni in processi quando si esegue la programmazione processi. I processi vengono programmati per data e ora in base all'ordine specificato dal ciclo di lavorazione produzione. L'impostazione dell'operazione determina i processi da esplodere durante la fase di programmazione. Il gruppo di cicli di lavorazione assegnato all'operazione determina se i processi vengono generati. Un processo viene generato solo se ha una durata specifica. Ad esempio, un processo di tempo di trasporto viene generato se il tempo di trasporto è stato specificato per l'operazione selezionata.

## <a name="scheduling-direction"></a>Direzione della programmazione
È possibile programmare i processi in avanti o a ritroso.

-   **In avanti**: utilizzare la direzione di programmazione in avanti per iniziare la produzione il prima possibile. Tale metodo è noto anche come metodo push perché forza l'esecuzione delle diverse fasi del processo di produzione. La produzione è programmata per iniziare e terminare il più presto possibile.
-   **A ritroso**: utilizzare la direzione di programmazione a ritroso per iniziare la produzione il più tardi possibile. Tale metodo è noto anche come metodo pull perché è basato sulla data in cui la produzione deve essere completata. Con la programmazione a ritroso si effettuano i calcoli a partire dalla data più tarda possibile di inizio della produzione che non compromette la scadenza finale.

## <a name="finite-capacity"></a>Capacità limitata
È possibile programmare i processi utilizzando la capacità limitata. Quando si utilizza la capacità limitata, la capacità programmata non può essere maggiore della capacità disponibile per la risorsa. Per tempo disponibile si intende l'intervallo di tempo durante il quale la risorsa è disponibile e non sono previste prenotazioni sulla capacità. La programmazione in base alla capacità limitata garantisce che le ore di inizio e di fine per un'operazione in una data specifica non si sovrappongano. La capacità della risorsa già prenotata viene considerata, come pure le sovrapposizioni tra le ore di inizio e di fine. La capacità limitata determina la quantità di capacità che deve essere disponibile per una risorsa affinché sia utilizzata nel modo ottimale. La determinazione è bilanciata con un calcolo del lead time più breve possibile tra le operazioni.

## <a name="finite-materials"></a>Materiale limitati
La programmazione processi basata sui materiali limitati garantisce che i materiali richiesti siano disponibili quando inizia l'operazione. Le regole di copertura per gli articoli definiscono i limiti. Nella programmazione viene utilizzata l'esplosione del fabbisogno per determinare quando gli articoli componente sono disponibili. Se si esegue la programmazione senza materiali limitati, il sistema presupporrà che tutti gli articoli siano disponibili quando richiesti.

## <a name="finite-properties"></a>Proprietà limitate
La programmazione processi basata su proprietà speciali richiede che vengano specificate alcune proprietà per le operazioni del ciclo di lavorazione produzione. Tali proprietà devono essere soddisfatte affinché venga riservata la capacità richiesta.

## <a name="references"></a>Riferimenti
La programmazione processi consente di programmare tutte le produzioni a cui fa riferimento la produzione corrente. Se a una produzione sono associate una o più produzioni secondarie, queste dovrebbero essere programmate contemporaneamente alla produzione principale perché la produzione principale non potrà essere avviata prima che siano completate le produzioni secondarie correlate.

## <a name="schedule-resources"></a>Programma risorse
Il motore di programmazione esamina le combinazioni di risorse per identificare quelle adatte a soddisfare i requisiti. È possibile specificare dei criteri di selezione selezionando uno dei seguenti valori nel campo **Selezione risorsa primaria** nella pagina **Parametri di programmazione**:

-   **Durata** - Il motore di programmazione seleziona la risorse che ha il lead time più breve. **Nota:** la programmazione in base alla durata può causare una riduzione delle prestazioni quando lo stesso gruppo di risorse contiene molte risorse e vengono utilizzate operazioni secondarie. È possibile programmare un massimo di 32 risorse per operazione. Se si supera questa quantità, viene visualizzato un messaggio del Registro informazioni e la programmazione processi non trova la risorsa alternativa migliore.
-   **Priorità** - Se due o più risorse hanno uguali capacità e livello, il motore di programmazione sceglierà la risorsa con priorità più alta. La risorsa con il valore numerico più basso in questo campo ha la priorità più alta.

Durante l'esecuzione della programmazione processi, il sistema pianifica le risorse in base alle limitazioni definite nei parametri delle risorse. È possibile controllare la capacità delle risorse utilizzando le impostazioni del calendario. Il sistema calcolerà i carichi per le risorse durante il processo di programmazione. **Nota:** per le produzioni che utilizzano la funzione di programmazione delle operazioni, è possibile eseguire la programmazione processi dopo la programmazione delle operazioni. Se invece non si utilizza la programmazione delle operazioni, è possibile eseguire la sola programmazione processi.

## <a name="maximum-capacities-for-resources-per-job-order"></a>Capacità massime per le risorse per commessa
Le risorse vengono assegnate ai processi con la programmazione processi. È possibile definire le capacità massime delle risorse per commessa. Ad esempio, è possibile impostare il sistema per programmare non più del 50% di capacità totale per un ordine di produzione. Questa impostazione offre un maggiore controllo sulla programmazione delle risorse a livello di programmazione processi. Di conseguenza, può contribuire a evitare problemi in caso di capacità insufficiente per eseguire le produzioni simultanee.

## <a name="resource-efficiency"></a>Efficienza delle risorse
La programmazione processi considera le percentuali di efficienza specificate per le risorse. Le percentuali di efficienza riducono o aumentano il tempo prenotato per la risorsa. Di conseguenza, anche il lead time aumenterà o diminuirà. Per il calcolo viene utilizzata la seguente formula: Tempo di programmazione = Tempo × 100 ÷ Percentuale efficienza. In questa formula, *Tempo* indica sia il tempo di esecuzione che il tempo di attrezzaggio.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]