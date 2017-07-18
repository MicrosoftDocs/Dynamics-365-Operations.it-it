---
title: Previsioni e budget di progetto
description: 
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ForecastModel, ProjYearEndProcess
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23501
ms.assetid: 4e6d1384-19a2-4232-b3f3-d2590c218bd7
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 835a92a8f95c7d75b02f5991cc2528c6a209540a
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="project-forecasts-and-budgets"></a>Previsioni e budget di progetto

[!include[banner](../includes/banner.md)]




Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition offre due modi per gestire e controllare i progetti: previsioni di progetto e budget di progetto. 

Utilizzare le previsioni di progetto se l'organizzazione si basa su una prospettiva operativa ed è incentrata su ricavi e costi derivati da transazioni specifiche. Utilizzare l'impostazione del budget se l'organizzazione è incentrata maggiormente sugli importi finanziari. 

Sia le previsioni di progetto che i budget di progetto utilizzano modelli previsionali per includere gli importi delle transazioni previste. 

Ciascun metodo ha i relativi vantaggi. È necessario considerare i seguenti punti prima di selezionare un metodo per l'organizzazione.

|                           |                                                                                                                                                                                                                                                         |                                                                                                                                                                         |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           | **Previsioni per il progetto**                                                                                                                                                                                                                                 | **Budget di progetto**                                                                                                                                                   |
| **Allocazione periodo**     | Non è possibile allocare in modo esplicito le transazioni in un periodo fiscale. La previsione e il relativo controllo si basano invece sulla durata del progetto. Poiché le previsioni si basano su una data specifica, è necessario derivare il periodo dalla data. | Non è possibile allocare le transazioni nell'intero progetto o in un periodo fiscale. Se si esegue l'allocazione in un periodo, è possibile riportare nel periodo fiscale successivo gli importi inutilizzati. |
| **Visualizzazione di transazioni**  | Le transazioni possono essere visualizzate nei moduli previsionali, in cui vengono mostrate le previsioni per l'intera società per tutti i progetti, indipendentemente dalla gerarchia. Per focalizzare l'attenzione su un determinato progetto, è necessario filtrare i dati.                                       | È possibile visualizzare le transazioni a budget per una singola gerarchia di progetto. È pertanto possibile visualizzare i dettagli relativi alla transazione per un progetto principale o per i relativi sottoprogetti.                 |
| **Variabili di transazione** | Quando si immettono le transazioni previsionali, è possibile utilizzare ogni attributo esistente per una transazione effettiva. Ciò garantisce un livello di dettaglio maggiore nella previsione. Ad esempio, è possibile immettere i dettagli relativi a quantità, lavoratori, articoli o proprietà riga.         | Quando si immettono i dettagli relativi al budget, è possibile utilizzare solo importi, categorie e attività.                                                                                    |
| **Sicurezza**              | Le previsioni si basano sulle transazioni immesse nei moduli previsionali e non prevedono un meccanismo di controllo dei processi. Qualsiasi lavoratore con autorizzazioni per un modulo previsionale può effettuare revisioni delle informazioni senza necessità di approvazione.                                        | L'impostazione del budget utilizza il sistema per la gestione del flusso di lavoro, che consente di gestire le modifiche e di mantenere uno storico delle revisioni.                                                       |
| **Tipi di voce**           | Le voci delle transazioni previsionali si basano sul numero di unità e sui prezzi di costo e di unità di vendita.                                                                                                                                                       | I dettagli relativi al budget si basano sugli importi, che vengono suddivisi tra costi e ricavi.                                                                                        |
| **Modelli previsionali**       | Poiché è necessario associare ogni previsione a un modello, è possibile creare più modelli previsionali e impostare dei sottomodelli.                                                                                                                               | L'impostazione del budget di progetto impone dei limiti per i modelli previsionali utilizzati per il budget. Un numero limitato di modelli previsionali consente di aumentare la coerenza delle proiezioni.                           |
| **Sovraccarichi di costo**         | È possibile consentire o impedire solo l'immissione di transazioni che determinerebbero un sovraccarico di costo.                                                                                                                                                                | L'impostazione del budget di progetto rende disponibili opzioni aggiuntive di controllo per gli utenti. È possibile consentire avvisi e sovraccarichi di costo.                                                                   |
| **Controllo**               | Il controllo previsionale viene eseguito tramite la riduzione previsionale. Gli importi effettivi vengono sottratti dai saldi delle transazioni previsionali senza audit trail. Ciò può complicare l'individuazione del punto in cui hanno avuto luogo le transazioni effettive.                   | Nel controllo del budget di progetto, gli importi effettivi vengono sottratti agli importi del budget residuo. Ciò consente un audit trail più chiaro.                                   |

## <a name="project-forecasts"></a>Previsioni progetto
Quando si utilizzano le previsioni di progetto, è possibile immettere le transazioni previsionali nei moduli di previsione per ciascun tipo di transazione. Ogni attributo disponibile per una transazione effettiva può essere utilizzato per una transazione previsionale, ad esempio la redditività della riga, gli attributi della riga, i lavoratori o le descrizioni. È inoltre possibile prevedere quanto tempo dopo aver sostenuto un costo verrà emessa la fattura a un cliente. 

Le transazioni relative alle previsioni di progetto si basano su unità e importi. 

È necessario associare ogni previsione di progetto a un modello previsionale. Quando si immette una transazione previsionale, viene suggerito automaticamente un modello previsionale. Il modello previsionale agisce come contenitore per le transazioni previsionali. 

È possibile definire i modelli previsionali come sottomodelli di un modello. In questo modo è possibile effettuare previsioni per area, periodo di tempo o reparto. È possibile copiare le transazioni previsionali in un modello per creare un nuovo modello e trasferire le transazioni nella contabilità generale. Poiché esiste una relazione uno-a-uno tra una previsione e un modello, ogni modello previsionale dà origine a un budget separato per un progetto. 

I modelli previsionali possono utilizzare la riduzione di previsione come meccanismo di controllo per i progetti. Con la riduzione di previsione, le transazioni effettive riducono i saldi delle transazioni previsionali. Tuttavia, poiché la riduzione di previsione viene applicata al progetto più alto nella gerarchia, viene fornita una visibilità limitata delle modifiche nella previsione. Ad esempio, se un lavoratore è associato a un sottoprogetto, le transazioni effettive per il lavoratore vengono registrate nel progetto principale. Ciò può rendere difficile tenere traccia delle modifiche, perché non è possibile determinare con facilità quale transazione in quale sottoprogetto ha causato una riduzione all'importo previsto Di conseguenza, è una buona idea creare una copia di un modello previsionale per la riduzione di previsioni da utilizzare. È quindi possibile utilizzare i report per visualizzare gli elementi previsti in origine. 

Le previsioni di progetto possono essere riviste, copiate, eliminate oppure trasferite a un budget di contabilità generale. Non è tuttavia previsto alcun controllo dei processi. Qualsiasi lavoratore con autorizzazione per un modulo di previsione può effettuare revisioni senza ulteriore verifica.

-   **Rivedi:** consente di effettuare la revisione di una transazione previsionale negli stessi moduli in cui erano state create le voci originali.
-   **Copia o elimina**: quando si copiano transazioni previsionali, vengono copiate le righe di transazione di un modello previsionale in un altro modello previsionale. Quando si eliminano previsioni, vengono eliminate le transazioni previsionali da un modello previsionale. Per limitare le transazioni previsionali copiate o eliminate, selezionare i tipi di transazione e le date specifici. Ciò consente di copiare o eliminare solo parti specifiche di una previsione.
-   **Trasferisci**: quando si trasferisce una previsione di progetto a un budget di contabilità generale, vengono trasferite le transazioni previsionali di un modello previsionale a un budget di contabilità generale. È possibile sovrascrivere tutte le transazioni trasferite in precedenza nel budget di contabilità generale nel quale si trasferisce la previsione di progetto in uso.

## <a name="project-budgets"></a>Budget progetto
Sebbene si integri con modelli previsionali, l'impostazione del budget di progetto è un metodo più semplice rispetto alla previsione poiché viene utilizzato un singolo modulo di immissione per i dettagli relativi al budget originali e per le revisioni ed è possibile effettuare previsioni basate solo su importo, categoria o attività. 

Per i budget di progetto, tutti i budget e le revisioni originali devono essere inviati al flusso di lavoro del progetto per l'approvazione. I flussi di lavoro consentono un controllo maggiore sul processo e creano un record di storico modifiche. 

L'attività di budget di progetto è simile a quella di budget per la contabilità generale ma è più facile e semplice da impostare. Molte delle opzioni disponibili per il budget della contabilità generale, ad esempio le sequenze numeriche o la valuta, non devono essere impostate separatamente per i progetti.

I budget di progetto vengono associati automaticamente con due modelli previsionali, uno per il budget originale e uno per quello residuo. In questo modo i report basati su modelli previsionali possono utilizzare i dati di budget. Quando un budget di progetto è impegnato, vengono create transazioni di previsione sulla base dei modelli associati, che vengono utilizzati a scopo di reporting e di controllo.

## <a name="forecast-models"></a>Modelli previsionali
I modelli previsionali dispongono di una gerarchia a un solo livello. Pertanto, ogni previsione di progetto deve essere associata a un modello previsionale.

Se si utilizzano le previsioni di progetto, è possibile identificare i modelli come sottomodelli. In questo modo è possibile creare previsioni per reparto, periodo di tempo o area. Ad esempio, è possibile creare un modello previsionale per un anno e quindi creare sottomodelli per le previsioni relative alle aree del Nordest, Sudest, Sudovest e Nordovest inviate su base regionale. Scegliendo opzioni diverse nei report disponibili, è possibile visualizzare le informazioni per previsione totale o per sottomodello.




