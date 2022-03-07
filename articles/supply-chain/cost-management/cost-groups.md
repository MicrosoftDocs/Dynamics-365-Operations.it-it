---
title: Gruppi di costi
description: I gruppi di costi rappresentano la base per la segmentazione e l'analisi dei contributi costi nel costo calcolato di un articolo prodotto, ad esempio i contributi costi per il materiale, la manodopera e i costi generali. Per la segmentazione per gruppi di costi vengono utilizzati diversi sinonimi negli ambienti di produzione, ad esempio scomposizione dei costi o classificazione dei costi.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCostGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 50871
ms.assetid: 1855f744-f73f-4fa8-8290-a7ee126d368b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b60c8a353a4c545cf5c1f1b1e5565d0d7e2a5bb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572148"
---
# <a name="cost-groups"></a>Gruppi di costi

[!include [banner](../includes/banner.md)]

I gruppi di costi rappresentano la base per la segmentazione e l'analisi dei contributi costi nel costo calcolato di un articolo prodotto, ad esempio i contributi costi per il materiale, la manodopera e i costi generali. Per la segmentazione per gruppi di costi vengono utilizzati diversi sinonimi negli ambienti di produzione, ad esempio scomposizione dei costi o classificazione dei costi. 

Per la segmentazione per gruppi di costi vengono utilizzati diversi sinonimi negli ambienti di produzione, ad esempio scomposizione dei costi o classificazione dei costi. La segmentazione per gruppi di costi si rivela utile per diversi scopi. Di seguito sono riportati alcuni esempi.

-   Può segmentare i costi dei diversi tipi di materiale, ad esempio gli ingredienti e il materiale di imballaggio di un alimento in scatola, in base ai gruppi di costi assegnati agli articoli.
-   Può segmentare i costi dei diversi tipi di risorse operative, ad esempio i diversi tipi di manodopera o di macchine, in base ai gruppi di costi assegnati alle categorie di costi correlate alle risorse operative e alle operazioni dei cicli di lavorazione.
-   Può segmentare i costi del tempo di impostazione ed esecuzione nelle operazioni dei cicli di lavorazione in base ai gruppi di costi assegnati alle categorie di costi correlate alle operazioni dei cicli di lavorazione.
-   Può segmentare i costi dei diversi tipi di costi generali, ad esempio i costi generali correlati alla manodopera e alle macchine, in base ai gruppi di costi assegnati ai costi indiretti nell'impostazione della scheda di determinazione costi.
-   Può fungere come base per il calcolo dei vari tipi di costi generali di produzione nell'impostazione della scheda di determinazione costi, ad esempio i diversi tipi di costi generali correlati alle informazioni di cicli di lavorazione relative alle risorse operative o al tempo di impostazione ed esecuzione. I costi generali di produzione possono inoltre essere correlati ai contributi costi del materiale componente, in modo da riflettere una politica di lean manufacturing in cui le informazioni del ciclo di lavorazione sono superflue.

La segmentazione per gruppi di costi si applica al costo calcolato di un articolo prodotto, indipendentemente dal fatto che tale costo sia basato su costi standard o su costi pianificati. La pagina **Riepilogo** visualizza questa segmentazione per gruppi di costi, per livello, o sia per gruppo di costi che per livello. 

Il termine *divisione* fa riferimento a questa capacità di mantenere la segmentazione in base a gruppi di costi in più livelli. La divisione si applica solo agli articoli prodotti che utilizzano un modello inventariale di costo standard. Se la divisione non viene utilizzata, il costo di un componente prodotto viene gestito come contributo costi materiale. Il parametro di Gestione articolo per la scomposizione dei costi per contabilità ausiliaria indica che la segmentazione per gruppi di costi verrà mantenuta in più livelli nei calcoli di costi standard, Di contro, se un criterio è impostato su nessun livello, la segmentazione per gruppi di costi si applica solo al calcolo di un singolo livello. Nella pagina **Rollup costo per gruppo di costi** ad esempio viene visualizzata la segmentazione per gruppi di costi in più livelli per voci di costo standard. 

La segmentazione per gruppi di costi può applicarsi inoltre a scostamenti per una voce di costo standard. Un secondo parametro di Gestione articolo definisce se gli scostamenti vengono identificati per gruppo di costi o verranno semplicemente riepilogati. 

È possibile assegnare a un gruppo di costi un tipo di gruppo di costi e un comportamento sempre ai fini della segmentazione.

-   **Tipo gruppo di costi**: a ciascun gruppo di costi deve essere assegnato un tipo di gruppo di costi, a indicare che il gruppo di costi si applica a materiale diretto, fabbricazione diretta o esternalizzazione diretta oppure per designarlo come indiretto o non definito. Un gruppo di costi designato come materiale diretto può essere assegnato agli articoli. Un gruppo di costi di fabbricazione diretta può essere assegnato alle categorie di costi. Un gruppo di costi di esternalizzazione diretta può essere assegnato a un tipo di prodotto di servizio che consente di classificare i costi associati all'acquisto del servizio alle attività in conto lavoro. Un gruppo di costi indiretto può essere assegnato a costi indiretti per supplementi o tariffe. Un gruppo di costi designato come non definito può essere assegnato ad articoli, categorie di costi o costi indiretti. L'assegnazione di un tipo di gruppi di costi ha diverse finalità. Consente innanzitutto di limitare la capacità di assegnare un gruppo di costi e di visualizzare un elenco di gruppi di costi applicabili. In secondo luogo consente di eseguire un'ulteriore segmentazione per il reporting. Può essere utilizzata infine per assegnare conti CoGe per scostamenti.
-   **Comportamento**: è possibile assegnare facoltativamente a ciascun gruppo di costi un comportamento, a indicare che il gruppo di costi si applica a costi fissi o a costi variabili. Un gruppo di costi con valore nullo per il comportamento viene gestito come costo variabile. L'assegnazione di un comportamento serve esclusivamente per il reporting. I costi ad esempio possono essere visualizzati con la segmentazione di costi fissi e variabili nella scheda di determinazione costi e nella pagina **Rollup costo per gruppo di costi**. Se si assegna una percentuale di impostazione del profitto a ciascun gruppo di costi, il calcolo della distinta base (DBA) fornisce un prezzo di vendita consigliato basato su un approccio comprendente una percentuale di ricarico.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]