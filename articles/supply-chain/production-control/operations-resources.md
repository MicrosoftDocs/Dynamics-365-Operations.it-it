---
title: Risorse Operations
description: Le risorse operative eseguono le attività di un progetto o di un processo di produzione. Possono essere di diversi tipi e possono avere capacità diverse.
author: sorenva
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifecycleManagementWorkspace, WrkCtrCapability
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e11d64ec37775f4fe2fc113af238a6294b459454
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "366606"
---
# <a name="operations-resources"></a>Risorse Operations

[!include [banner](../includes/banner.md)]

Le risorse operative eseguono le attività di un progetto o di un processo di produzione. Possono essere di diversi tipi e possono avere capacità diverse. 

<a name="operations-resources"></a>Risorse Operations
--------------------

Le risorse operative sono i computer, gli strumenti, i lavoratori, le attrezzature, le aree fisiche o i fornitori che eseguono le attività di un progetto o di un processo di produzione. Possono essere di diversi tipi e possono essere capacità diverse.

-   **Fornitore**: risorsa esterna che esegue le attività di un progetto o le operazioni di produzione. Un esempio è un terzista. Collegando le risorse del fornitore a un conto fornitore è possibile generare acquisti per terzisti in base alle righe DBA o alle righe di produzione.
-   **Risorse umane**: addetto a un progetto o alla produzione che esegue un'attività, da solo o come operatore di uno strumento o di un computer. Se si utilizza la funzionalità Risorse umane, è possibile collegare le risorse umane a un lavoratore. Il motore di programmazione può quindi allocare le risorse in base alle competenze definite per il lavoratore corrispondente.
-   **Computer**: macchina o altra attrezzature di produzione necessaria nella produzione.
-   **Strumento**: strumento o dispositivo che in genere viene utilizzato insieme a un'altra risorsa per eseguire un'attività in un progetto o nella produzione.
-   **Ubicazione**: posizione fisica di una dimensione specifica necessaria per eseguire un'attività. Un esempio è un'area di montaggio.
-   **Struttura**: edificio o struttura fissa necessaria per eseguire un'attività.

## <a name="calendars"></a>Calendari
Un calendario può essere assegnato a una risorsa operativa e descrive la capacità (in ore) della risorsa. Gli orari di lavoro della risorsa operativa vengono determinati dal calendario assegnato al gruppo di risorse cui la risorsa operativa fa parte. È inoltre possibile impostare una data di validità e una data di scadenza per il calendario assegnato. È possibile quindi assegnare più di un calendario a una risorsa operativa. Tuttavia, le date dei calendari assegnati non possono sovrapporsi e alla risorsa operativa può essere assegnato solo un calendario alla volta. **Nota:** se non è presente ed efficace alcun calendario per un gruppo di risorse (ad esempio, se l'ultimo calendario assegnato oppure l'unico calendario assegnato è scaduto), non sarà possibile accedere alle risorse operative assegnate al gruppo di risorse per la pianificazione della produzione o per la programmazione delle operazioni. È inoltre possibile assegnare un calendario a un gruppo di risorse per specificare l'orario di lavoro per il gruppo di risorse e tutte le risorse operative assegnate al gruppo di risorse. La capacità del gruppo di risorse viene calcolata come la somma delle capacità di ciascuna risorsa operativa assegnata a quel gruppo di risorse. Il calendario assegnato a un gruppo di risorse può cambiare nel tempo.

## <a name="resource-capabilities"></a>Capacità risorsa
Si definisce capacità l'idoneità di una risorsa operativa di eseguire un'attività specifica. È possibile assegnare una o più capacità a una risorsa operativa. Il motore di programmazione allocherà quindi le risorse abbinando i requisiti risorsa di ogni attività alle capacità delle risorse operative disponibili. È possibile assegnare capacità a tutti i tipi di risorse operative: (**Strumento**, **Fornitore**, **Macchina**, **Risorse umane**, **Ubicazione** o **Struttura**). Per assegnare capacità a risorse operative per un tempo limitato, definire una data di inizio e una di scadenza durante l'assegnazione delle capacità. Per ulteriori informazioni, vedere [Capacità risorsa](resource-capabilities.md).

## <a name="resource-groups"></a>Gruppi di risorse
Un gruppo di risorse è un gruppo di risorse operative che rappresenta la granularità con cui si desidera programmare le risorse quando si utilizza il metodo di programmazione delle operazioni. Di conseguenza, i gruppi di risorse corrispondono in genere all'organizzazione fisica delle celle di lavoro, che è demarcata dalle righe gialle nello shop floor di produzione. Il gruppo di risorse definisce il contesto di sito, unità di produzione e magazzino per le risorse operative assegnate al gruppo. Quando si assegna una risorsa operativa a un gruppo di risorse, la risorsa può essere programmata nel sito in cui si trova il gruppo. Non occorre assegnare le risorse operative create a un gruppo di risorse. Tuttavia, una risorsa operativa deve essere assegnata a un gruppo di risorse prima che possa essere programmata per eseguire un lavoro. È possibile assegnare una risorsa operativa a un gruppo di risorse per un periodo di tempo limitato. È inoltre possibile assegnare una risorsa operativa a più gruppi di risorse, in modo da poter condividere la risorsa tra più siti. Tuttavia, le date di validità e di scadenza non possono sovrapporsi. In altre parole, non è possibile assegnare una risorsa operativa a due gruppi di risorse allo stesso tempo. Le modifiche nelle assegnazioni del gruppo di risorse sono valide solo per le nuove allocazioni di risorse. Le prenotazioni di capacità per i processi, le operazioni e le previsioni ore di progetto già programmate non saranno interessate. **Nota:** quando si assegnano risorse operative di tipo **Fornitore** a un gruppo di risorse, tutte le risorse operative assegnate a quel gruppo di risorse devono essere di tipo **Fornitore** e devono essere collegate allo stesso conto fornitore.

## <a name="production-units"></a>Unità di produzione
Un'unità di produzione è un'unità amministrativa che raccoglie gruppi di risorse. Può contenere più gruppi di risorse, ma un gruppo di risorse può essere assegnato a una sola unità di produzione. L'unità di produzione riflette il layout fisico delle risorse di produzione e non influisce in alcun modo sulle transazioni o sulla modalità in cui queste vengono elaborate. È necessario associare un'unità di produzione a un sito. A un'unità di produzione è inoltre possibile assegnare un magazzino di prelievo e un magazzino di deposito. È possibile utilizzare un'unità di produzione per consolidare e filtrare dati correlati alla produzione. Un capo reparto, ad esempio, può visualizzare una panoramica del carico di lavoro arretrato e la capacità disponibile di una determinata unità di produzione. È possibile modificare l'unità di produzione assegnata a un gruppo di risorse. È inoltre possibile eliminare un'unità di produzione. Queste modifiche all'unità di produzione, tuttavia, sono effettive soltanto per i nuovi ordini creati dopo l'esecuzione della programmazione generale. Se si desidera apportare la modifica dell'unità di produzione agli ordini esistenti, è necessario operare manualmente.

## <a name="resource-scheduling"></a>Programmazione risorse
Le risorse operative sono assegnate alle attività quando viene programmato un progetto o una produzione. Sono disponibili due metodi di programmazione: programmazione operazioni e programmazione processi. Quando si utilizza la programmazione operazioni, ogni operazione o attività di progetto viene programmata nel gruppo di risorse che contiene le risorse operative che soddisfano i requisiti risorsa specificati per l'operazione. Se una risorsa operativa specifica è necessaria per l'operazione, la programmazione consente di prenotare la capacità solo di una risorsa operativa specifica del gruppo. La programmazione processi è una forma di programmazione più dettagliata della programmazione operazioni. Suddivide ciascuna operazione nei diversi processi o attività. I processi vengono quindi assegnati alle risorse operative che li eseguiranno. La programmazione consente di prenotare capacità dei gruppi di risorse in base agli orari operativi definiti nel ciclo di lavorazione produzione o nelle attività di progetto. Se si utilizza la capacità limitata, la programmazione dipende dalla disponibilità delle risorse operative necessarie per completare l'attività. Per la programmazione delle operazioni, la capacità del gruppo di risorse è la somma della capacità disponibile delle risorse operative che fanno parte di tale gruppo. Le prenotazioni delle capacità già presenti per le risorse operative vengono considerate come capacità non disponibile. Se la capacità disponibile è insufficiente per la produzione, gli ordini di produzione possono essere ritardati o persino interrotti. Nella pagina **Risorse**è possibile definire più proprietà che controllano la modalità di assegnazione delle prenotazioni delle capacità:

-   **Capacità**: consente di specificare la capacità della risorsa operativa all'ora in termini di unità di misura della capacità.
-   **Capacità batch**: consente di specificare il numero massimo di pezzi che la risorsa operativa può lavorare per elaborazione.
-   **Percentuale efficienza**: consente di specificare l'efficienza che ci si attende dalla risorsa operativa. La percentuale di efficienza consente di rettificare la produttività di una risorsa operativa e influisce sul tempo riservato per la risorsa. I lead time per le operazioni che utilizzano la risorsa operativa vengono pertanto rettificati. Viene utilizzata la seguente formula per il calcolo: Tempo di programmazione = Tempo × 100 ÷ Percentuale efficienza. Nella formula, *Tempo indica* sia il tempo di esecuzione che il tempo di attrezzaggio.
-   **Percentuale programmazione operazioni**: consente di specificare la percentuale massima di capacità della risorsa operativa che si desidera utilizzare nella programmazione delle operazioni. Per consentire un'adeguata flessibilità della capacità durante la programmazione dei processi, questo valore deve essere inferiore al 100%.
-   **Capacità limitata**: impostare questa opzione su **Sì** se la risorsa operativa deve essere programmata in base all'effettiva capacità disponibile e se devono essere considerate le prenotazioni esistenti della capacità. Se l'opzione è impostata su **No**, si presuppone che la risorsa operativa abbia una capacità illimitata e la risorsa può essere di conseguenza prenotata in eccesso.
-   **Proprietà limitata**: consente di impostare questa opzione su **Sì** se si desidera programmare la risorsa operativa sulla base della capacità effettiva disponibile relativamente alle proprietà di programmazione dell'orario di lavoro obbligatorio.
-   **Esclusivo**: impostare questa opzione su **Sì** se non si desidera che la risorsa operativa venga utilizzata per un altro processo o un'altra operazione fino al completamento della produzione corrente. In questo caso, la risorsa operativa non può essere utilizzata neppure in presenza di interruzioni nel tempo di esecuzione della risorsa.
-   **Risorsa collo di bottiglia**: consente di definire la risorsa operativa come risorsa collo di bottiglia. Una risorsa di questo tipo viene programmata utilizzando la capacità limitata quando sono selezionate le opzioni **Capacità limitata** e **Programmazione colli di bottiglia** della pagina **Piani generali**.

Per programmare più risorse operative contemporaneamente per eseguire, ad esempio, un'operazione nella produzione, è necessario specificare i requisiti per le diverse risorse utilizzando le operazioni primarie e secondarie. È quindi possibile prenotare più risorse operative con capacità diverse. La risorsa operativa che è programmata per l'operazione primaria determina la durata dell'attività.

## <a name="lean-work-cells"></a>Celle di lavoro di produzione snella
È possibile specificare che un gruppo di risorse sia una cella di lavoro per la produzione snella. Il gruppo di risorse può fare parte di un flusso di produzione. Specificando un gruppo di risorse come cella di lavoro per la produzione snella, si impedisce anche che il gruppo di risorse e le risorse operative assegnate siano allocati alle operazioni di un ordine di produzione o alla previsione di ore per un progetto. Per ciascun gruppo di risorse che viene utilizzato come cella di lavoro per la produzione snella, è necessario specificare le seguenti informazioni:

-   **Calendario**: calendario lavorativo della cella di lavoro, che deve avere la proprietà di un giorno lavorativo standard.
-   **Magazzino e ubicazione di entrata**: ubicazione predefinita utilizzata per prelevare il materiale per un'attività.
-   **Magazzino e ubicazione di uscita**: ubicazione predefinita dove vengono collocati tutti i prodotti della cella di lavoro.
-   **Categoria dei costi dei tempi di esecuzione**: categoria che deve essere definita per la cella di lavoro se si tiene traccia dei costi della manodopera diretta.

Quando un gruppo di risorse viene utilizzato come cella di lavoro produzione snella, la capacità della cella di lavoro viene specificata direttamente nel gruppo di risorse. Di conseguenza, non occorre assegnare le risorse operative al gruppo di risorse. Solo quando la cella di lavoro viene gestita da un terzista, una risorsa operativa di tipo **Fornitore** deve essere assegnata alla cella di lavoro. Se si assegna una risorsa operativa a un gruppo di risorse che viene contrassegnato come cella di lavoro, la capacità della cella di lavoro resta invariata.

## <a name="costing-resources"></a>Risorsa per la determinazione costi
Quando si definisce un'attività, ad esempio un'operazione del ciclo di lavorazione o una previsione di ore per il progetto, è possibile specificare il fabbisogno di una risorsa operativa o di un gruppo di risorse specifico. Tuttavia, è inoltre possibile specificare il fabbisogno di una risorsa operativa di un tipo specifico o di una risorsa operativa con una funzione o una competenza specifica. Per questo motivo, l'effettiva assegnazione della risorsa non viene effettuata fino a quando l'attività non è stata programmata e la capacità non è stata prenotata. Di conseguenza, in un'operazione del ciclo di lavorazione è possibile specificare che la stima e il calcolo DBA devono essere basati su una risorsa operativa specifica. Questa risorsa operativa viene definita come la risorsa per la determinazione dei costi. È inoltre possibile trasferire le categorie costi e i tempi operativi dalla risorsa per la determinazione dei costi all'attività. Se l'operazione è programmata, per la stima e il calcolo DBA viene utilizzata la risorsa operativa effettivamente programmata.



