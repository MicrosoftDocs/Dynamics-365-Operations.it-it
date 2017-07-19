---
title: Modellizzazione di un'organizzazione snella
description: L'articolo fornisce informazioni sui concetti chiave della modellazione di un'organizzazione snella.
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53141
ms.assetid: 4f272f2f-ec2c-4b0d-a652-00a63b719b9e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: c5bb642df692451e975be74bd8aa7d856b964a68
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="modeling-a-lean-organization"></a>Modellizzazione di un'organizzazione snella

[!include[banner](../includes/banner.md)]


L'articolo fornisce informazioni sui concetti chiave della modellazione di un'organizzazione snella. 

In genere uno scenario di lean manufacturing è più di una raccolta di regole kanban non correlate o di criteri di fornitura materiali. Il flusso di materiale e prodotti attraverso le celle di lavoro e le ubicazioni per uno specifico scenario di fornitura o produzione può essere descritto come una sequenza o una piccola rete di attività di trasferimento o elaborazione. Questa sequenza o rete è conosciuta come flusso di produzione.

## <a name="production-flows-in-lean-manufacturing"></a>Flussi di produzione nella lean manufacturing
Negli scenari di produzione basati su ordini di produzione, il materiale viene rilasciato a un ordine di produzione specifico. Durante una sequenza di operazioni basata su una distinta base (DBA) e cicli di lavorazione, i prodotti vengono creati e infine ricevuti presso l'ubicazione fornita. Il tempo di produttività degli ordini di produzione varia da minuti a settimane. Tutti i costi, i materiali e la manodopera correlati vengono accumulati nell'ordine di produzione. 

Per ridurre i lead time di consegna e l'eccesso di magazzino tra centri di lavoro causati dalla produzione in batch, la lean manufacturing introduce il rifornimento kanban e le aree di deposito nella produzione e nel rifornimento magazzino. In genere, ciò interrompe la produzione di cicli di lavorazione kanban parzialmente indipendenti. Il rifornimento di un kanban per un prodotto semilavorato non viene più attivato da un ordine per un prodotto finito. 

Per ristabilire un contesto di costi e di produzione per i diversi scenari kanban proposti in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, i flussi di produzione basati su attività sono stati introdotti come spina dorsale della lean manufacturing. Tutte le regole kanban fanno riferimento a questa struttura predefinita. Il modello basato su attività supporta l'impostazione di una più vasta gamma di scenari supportati dalle versioni precedenti di lean manufacturing per Dynamics AX. Tuttavia, il modello non aggiunge complessità per i lavoratori del reparto produzione, in quanto tutti gli scenari utilizzano la stessa interfaccia utente basata sulle attività.

## <a name="semi-finished-products-non-bom-levels"></a>Prodotti semilavorati (livelli non DBA)
La lean manufacturing per Dynamics AX integra i kanban per i prodotti inventariati e i prodotti semilavorati in un unico framework, offrendo in tal modo un'interfaccia utente unificata per tutte le situazioni. A causa dell'architettura, i livelli aggiuntivi DBA non devono più essere introdotti per attivare i kanban da utilizzare per i prodotti semilavorati. Questa architettura contribuisce anche a ridurre al minimo le operazioni di magazzino.

## <a name="products-and-material-in-work-in-progress"></a>Prodotti e materiali nel WIP (Work-in-Progress)
La riduzione delle dimensioni batch allo stato ideale di un unico flusso nella lean manufacturing può causare un notevole aumento delle operazioni di magazzino se ogni processo di prelievo o registrazione kanban causa transazioni per gli articoli utilizzati. L'architettura del flusso di produzione prevede il trasferimento di materiale al flusso di produzione insieme ai kanban di prelievo nelle dimensioni dell'unità movimentazione di trasporto o di conservazione. Il valore del materiale rilasciato viene aggiunto al conto WIP correlato al flusso di produzione. Questo comportamento è simile al comportamento per il materiale che viene rilasciato a un ordine di produzione. Lo stesso principio può essere applicato a prodotti e prodotti semilavorati. A meno questi prodotti non vengano creati, trasferiti o utilizzati all'interno di un flusso di produzione, le operazioni di magazzino sono facoltative. Una volta che i prodotti sono registrati in magazzino, il conto WIP per il flusso di produzione viene ridotto deducendo il costo standard correlato.

## <a name="value-streams-and-value-stream-mapping"></a>Flussi di valori e mapping dei flussi di valori
L'architettura di Lean Manufacturing per Dynamics AX è ispirata ai cinque principi Lean formulati da Womack e Jones: Valore del cliente, Flusso del valore, flusso, pull e perfezione. Un metodo approvato per implementare le soluzioni di lean manufacturing nel mondo fisico di produzione è il mapping dei flussi dei valori (VSM). Questo metodo è stato introdotto da Rother e Shook nella pubblicazione “Learning to See" presso il Lean Manufacturing Institute. 

In Dynamics AX, il flusso del valore di stato futuro può essere modellato come versione del flusso di produzione. Tutti i processi del flusso del valore sono modellati come attività del processo. I movimenti o trasferimenti possono essere modellati come attività di trasferimento se deve essere registrato lo stato di trasferimento o se occorre un'integrazione al prelievo da magazzino o alle spedizioni consolidate. 

Il flusso del valore stesso è modellato come unità operativa in Dynamics AX. Di conseguenza, il flusso del valore può essere utilizzato come dimensione finanziaria.

## <a name="costing-for-lean-manufacturing-based-on-the-production-flow"></a>Determinazione dei costi della lean manufacturing in base al flusso di produzione
Il consolidamento periodico dei costi per un flusso di produzione corregge il conto WIP correlato e consente la determinazione degli scostamenti per i prodotti forniti dal flusso di produzione.

## <a name="continuous-improvement"></a>Miglioramento continuo
Per supportare al meglio il miglioramento continuo, i flussi di produzione vengono implementati in versioni efficaci nel tempo. Di conseguenza, una versione del flusso di produzione esistente, insieme a tutte le regole kanban correlate, può essere copiata in una versione futura del flusso di produzione. Inoltre, il flusso di produzione dello stato futuro può essere modellato prima di essere convalidato e attivato per la produzione. Per assicurare un flusso di materiale senza problemi alla data di transizione e oltre, i kanban esistenti dalle versioni del flusso di produzione obsolete sono automaticamente correlati alla nuova versione.

## <a name="simplicity"></a>Semplicità
Per l'implementazione di Lean Manufacturing per Dynamics AX, scegliamo l'approccio di un flusso di produzione e di un'attività che consente di modellare scenari di produzione semplici e complessi in un'unica architettura scalabile. Uno sguardo più attento al concetto di attività rivela una nuova semplicità per gli utenti che ne hanno necessità: i lavoratori dei reparti shop floor e logistica. Con la segnalazione rispetto ai processi basati su attività anziché la segnalazione delle transazioni di magazzino, un'interfaccia utente unificata per tutte le varianti di lean manufacturing trasferisce la complessità aziendale dall'interfaccia utente all'area a cui appartiene: il flusso di produzione come spina dorsale della lean manufacturing.




