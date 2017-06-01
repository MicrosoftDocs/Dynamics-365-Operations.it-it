---
title: Versioni determinazione costi
description: "In questo articolo vengono fornite informazioni sulle versioni di determinazione costi, sul modo di gestirle e sui tipi di dati che è possibile includervi. Lo scopo principale è quello di includere i record dei costi per gli articoli, le categorie di costi e le formule di calcolo per i costi indiretti."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 54532
ms.assetid: cd239da5-f434-4d1b-8196-5414c888d76d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ce1f0c2107b701f12c18646ff4369e543bec7c97
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="costing-versions"></a>Versioni determinazione costi

[!include[banner](../includes/banner.md)]


In questo articolo vengono fornite informazioni sulle versioni di determinazione costi, sul modo di gestirle e sui tipi di dati che è possibile includervi. Lo scopo principale è quello di includere i record dei costi per gli articoli, le categorie di costi e le formule di calcolo per i costi indiretti.

Una versione di determinazione costi può avere una o più finalità, in base ai dati in essa contenuti. Lo scopo principale è quello di includere i record dei costi per gli articoli, le categorie di costi e le formule di calcolo per i costi indiretti. In una versione di determinazione costi può essere contenuto un insieme di record dei costi standard o un insieme di record dei costi pianificati basati sul tipo di determinazione costi assegnato alla versione di determinazione costi.

## <a name="costing-versions-for-standard-or-planned-costs"></a>Versioni di determinazione costi per i costi standard o pianificati.
### <a name="standard-costs"></a>Costi standard

Una versione di determinazione costi può supportare un modello inventariale di costi standard per gli articoli. In questo caso nella versione di determinazione costi è contenuto un insieme di record dei costi standard per gli articoli e i processi di fabbricazione. I dati relativi ai costi per i processi di fabbricazione sono espressi in termini di categorie di costi per le operazioni dei cicli di lavorazione e in termini di formule di calcolo per i costi generali di produzione.

### <a name="planned-costs"></a>Costi pianificati

In una versione di determinazione costi può essere contenuto un insieme di record dei costi pianificati per gli articoli e i processi di fabbricazione. Una versione di determinazione costi contenente costi pianificati viene utilizzata spesso per supportare le simulazioni di calcolo dei costi, ad esempio la simulazione dell'effetto prodotto da variazioni di costo dei materiali acquistati o dei processi di fabbricazione sui costi calcolati di articoli prodotti. È inoltre possibile utilizzare i record dei costi degli articoli per i costi pianificati per supportare un modello inventariale di costi effettivi fornendo i valori iniziali per i costi degli articoli. I valori includono il calcolo dei costi pianificati per gli articoli prodotti.

## <a name="entering-costs"></a>Immettere i costi
La gestione dei dati per i record dei costi in una versione di determinazione costi comporta l'immissione dei costi per gli articoli acquistati e per gli articoli trasferiti da un sito a un altro. Per i produttori sono previste ulteriori attività di gestione dei dati tramite l'immissione di costi per le categorie di costi associate alle operazioni dei cicli di lavorazione, l'immissione di formule di calcolo per i costi indiretti che riflettono i costi generali di produzione e il calcolo dei costi per gli articoli prodotti. 

I dati relativi ai costi degli articoli in una versione di determinazione costi sono costituiti da uno o più record dei costi per ciascun articolo. Quando un record di costo di un articolo viene immesso per la prima volta, ha uno stato **in sospeso** e una data di validità prevista. Quando si attiva il record del costo dell'articolo, lo stato viene aggiornato e diventa **attivo** e la data di validità viene aggiornata alla data di attivazione. Record dei costi degli articoli diversi possono riflettere siti, date di validità o stati diversi. Quando si calcolano i costi per gli articoli prodotti per una data futura, il calcolo DBA (distinta base) utilizza i record dei costi con data di validità pertinente, indipendentemente che lo stato sia in**in sospeso** o **attivo**. Verrà utilizzato il record del costo attivo corrente di un articolo per stimare i costi degli ordini di produzione e valutare le operazioni di magazzino secondo un modello inventariale di determinazione costi standard. La gestione dei record dei costi per le categorie di costi e per le formule di calcolo dei costi indiretti è simile alla gestione dei record dei costi degli articoli. 

Due criteri di bloccaggio per una versione di determinazione costi determinano se possono essere gestiti costi in sospeso e se il costo in sospeso può essere attivato. Utilizzare i criteri di bloccaggio per consentire la gestione dei dati e quindi per impedire la gestione dei dati per i record dei costi in una versione di determinazione costi. 

In una versione di determinazione costi possono essere contenuti inoltre dati relativi ai prezzi di vendita o di acquisto degli articoli ai fini del calcolo DBA.

## <a name="item-sales-prices-for-bom-calculations"></a>Prezzi di vendita degli articoli per i calcoli DBA
Il motivo principale per l'inclusione dei dati sui prezzi di vendita è di conservare il prezzo di vendita calcolato di un articolo prodotto. Il prezzo di vendita calcolato può quindi essere analizzato per determinare l'impatto di componenti, operazioni del ciclo di lavorazione e sovraccarico sui costi e sul prezzo di vendita. 

Un secondo motivo per l'inclusione dei dati sui prezzi di vendita è di definire i record del prezzo di vendita per gli articoli componente. Questi record possono quindi essere utilizzati per calcolare il prezzo di vendita degli articoli prodotti. È necessario definire il modello prezzo di vendita che è incorporato in un gruppo di calcolo DBA e assegnare il gruppo di calcolo DBA agli articoli acquistati. Quindi, quando si eseguono calcoli DBA che utilizzano costi pianificati, selezionare il modello prezzo di costo del gruppo di calcolo DBA. 

In caso contrario, i record del prezzo di vendita degli articoli vengono utilizzati unicamente come informazioni di riferimento, che siano calcolati automaticamente o immessi manualmente. Attivando il record del prezzo di vendita di un articolo, è possibile aggiornare il prezzo di vendita di base dell'articolo, il quale non è specifico del sito e può essere sostituito manualmente. Il prezzo di vendita base dell'articolo funge da prezzo di vendita predefinito negli ordini cliente e nelle offerte di vendita.

## <a name="item-purchase-prices-for-bom-calculations"></a>Prezzi di acquisto degli articoli per i calcoli DBA
Lo scopo principale per cui si abilita la visualizzazione dei dati sui prezzi di acquisto è definire i record dei prezzi di acquisto degli articoli componente, in modo da poterli utilizzare per calcolare il costo degli articoli prodotti. I record dei prezzi di acquisto degli articoli devono essere immessi manualmente. 

A tale scopo è necessario definire come prima cosa un gruppo di calcolo DBA contenente un modello di prezzo di costo del prezzo di acquisto dell'articolo, quindi assegnare il gruppo di calcolo DBA agli articoli acquistati È quindi necessario utilizzare un modello di prezzo di costo per il gruppo di calcolo DBA quando si eseguono i calcoli DBA che utilizzano costi pianificati per calcolare i prezzi di vendita degli articoli prodotti. 

I record dei prezzi di acquisto per gli articoli, inoltre, vengono utilizzati come informazioni di riferimento. Cambiando lo stato del record di un prezzo di acquisto di un articolo da **sospeso** ad **attivo** è possibile aggiornare il prezzo di acquisto base, il quale non è tuttavia specifico del sito e può essere sostituito manualmente. Il prezzo di acquisto base dell'articolo funge da prezzo di acquisto predefinito negli ordini fornitore.




