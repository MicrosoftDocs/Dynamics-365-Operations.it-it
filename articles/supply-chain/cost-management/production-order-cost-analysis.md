---
title: Analisi del costo ordine di produzione
description: Questo articolo fornisce informazioni sull'analisi dei costi che è possibile effettuare per gli ordini di produzione completati e correnti. È possibile analizzare i costi stimati ed effettivi utilizzando la pagina Calcolo dei prezzi o il report Stima e determinazione dei costi. Vengono visualizzate informazioni sui costi e sulle quantità effettivi e stimati di ogni articolo componente, sull'operazione di ciclo di lavorazione e sul costo indiretto.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage, ProdSetupHistoricalCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79634
ms.assetid: ded5da04-f787-49f7-b5e5-75c2a2b92930
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d0a298a8f782ae318971e99c03e864fa5a4ef88
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6343652"
---
# <a name="production-order-cost-analysis"></a>Analisi del costo ordine di produzione

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sull'analisi dei costi che è possibile effettuare per gli ordini di produzione completati e correnti. È possibile analizzare i costi stimati ed effettivi utilizzando la pagina Calcolo dei prezzi o il report Stima e determinazione dei costi. Vengono visualizzate informazioni sui costi e sulle quantità effettivi e stimati di ogni articolo componente, sull'operazione di ciclo di lavorazione e sul costo indiretto.

I costi effettivi di un ordine di produzione sono basati sul consumo dichiarato di materiale e operazioni dei cicli di lavorazione. Per accedere alle transazioni dettagliate sul consumo dichiarato di materiale, alle operazioni dei cicli di lavorazione e ai costi indiretti di un ordine di produzione, è possibile utilizzare la pagina **Registrazione produzione**.

## <a name="variance-analysis-for-a-completed-production-order"></a>Analisi degli scostamenti per un ordine di produzione completato
Gli scostamenti riflettono un confronto tra le attività di produzione rilevate e il calcolo dei costi standard per l'articolo in produzione. Non riflettono invece un confronto con i costi stimati dell'ordine di produzione. Nelle attività di produzione rilevate sono inclusi il consumo di materiale e le operazioni di distribuzione, insieme ai costi indiretti associati, nonché la quantità dichiarata finita. Vengono calcolati i seguenti quattro tipi di scostamento:

-   Scostamento dimensioni lotto
-   Scostamento quantità produzione
-   Scostamento prezzi di produzione
-   Scostamento sostitutivo produzione

Nel diagramma di seguito riportato sono illustrati i quattro scostamenti che rappresentano la differenza tra i costi effettivi di un ordine di produzione e i costi calcolati all'interno del record di costo dell'articolo al momento di terminare l'ordine di produzione. 

![Scostamenti che rappresentano le differenze in un ordine di produzione completato.](./media/control.jpg) 

È possibile analizzare gli scostamenti di produzione utilizzando la pagina **Scostamento** o il report **Scostamento produzione**. Utilizzare le opzioni di visualizzazione per visualizzare gli scostamenti dettagliati per articolo e risorsa operativa o per gruppo di costi. Il criterio di scomposizione dei costi nei parametri di magazzino determina se viene tenuta traccia degli scostamenti per gruppo di costi. È inoltre possibile utilizzare le opzioni di visualizzazione **singolo**, **multiplo** e **totale** per visualizzare gli scostamenti riepilogati. Le informazioni sugli scostamenti dettagliati sono utili per comprendere l'origine di ciascuno scostamento. Per prevedere gli scostamenti prima di terminare un ordine di produzione, analizzare le informazioni dettagliate fornite nel report **Stima e determinazione dei costi**.

## <a name="cost-analysis-for-current-production-orders"></a>Analisi dei costi per ordini di produzione correnti
Le informazioni relative a ciascun tipo di transazione vengono fornite in report separati. Utilizzare questi report per analizzare i costi per le attività di produzione segnalate. Vengono visualizzate informazioni solo per gli ordini di produzione correnti con stato **Iniziato** o **Dichiarato finito**.

-   **Materiali in lavorazione**: in questo report vengono elencate le transazioni di distinta di prelievo dichiarate a fronte degli ordini di produzione correnti per una data di transazione specificata. Nel report viene indicata la quantità del componente prelevata e l'importo costi di ciascuna transazione. Utilizzare i criteri di selezione per un singolo articolo componente. È possibile, ad esempio, stampare informazioni sulla quantità prelevata del componente a fronte degli ordini di produzione applicabili. Poiché la quantità prelevata non viene aggiornata in base alle quantità dichiarate finite dell'articolo principale, è possibile che la quantità effettiva delle materie prime in lavorazione venga sovrastimata.
-   **Semilavorato**: in questo report vengono elencate le transazioni cicli di lavorazione (o transazioni processi) dichiarate a fronte degli ordini di produzione correnti per una data di transazione specificata. Il report indica orari, importo e quantità (sia quantità idonea sia quantità difettosa) che vengono dichiarati per ciascuna transazione. Sono inoltre incluse informazioni quali numero di operazione, ID operazione e risorsa operativa. In aggiunta, nel report vengono visualizzati il tempo totale e l'importo per tutte le transazioni a fronte dell'ordine di produzione, nonché la quantità dichiarata finita.
-   **Costi indiretti in esecuzione**: in questo report vengono elencati i costi indiretti sostenuti a fronte degli ordini di produzione. Questi dati si basano sul consumo dichiarato delle operazioni dei cicli di lavorazione e dei componenti per una data di transazione specificata. Nel report vengono indicati il tipo di costo indiretto (supplemento o tariffa), il codice della scheda di determinazione costi per il costo indiretto e l'importo costi di ciascuna transazione. Questo report non fornisce informazioni sulla transazione della scheda del ciclo di lavorazione o di distinta di prelievo che ha generato il costo indiretto.
-   **Costi di produzione in fase di elaborazione**: in questo report viene elencato il consumo combinato di materiale, operazioni dei cicli di lavorazione e costo indiretto a fronte degli ordini di produzione per una data di transazione specificata.
-   **Articoli in lavorazione finiti**: in questo report vengono elencati gli ordini di produzione correnti e le transazioni dichiarate finite per una data di transazione specificata.


## <a name="additional-resources"></a>Risorse aggiuntive

[Origini comuni degli scostamenti di produzione](common-sources-of-production-variances.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]