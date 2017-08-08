---
title: "Terminologia della contabilità industriale"
description: "In questo argomento vengono definiti i termini principali utilizzati in Contabilità industriale."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 1f12e8e82430c79ee93f2284e5fdf47ac559525d
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---

# <a name="cost-accounting-terminology"></a>Terminologia della contabilità industriale

[!include[banner](../includes/banner.md)]


In questo argomento vengono definiti i termini principali utilizzati in Contabilità industriale.

**Contabilità industriale**

La contabilità industriale consente di raccogliere dati da diverse origini, ad esempio dalla contabilità generale, dalle contabilità ausiliarie, dai budget e dalle informazioni statistiche. È quindi possibile analizzare, riepilogare e valutare i dati sui costi, in modo che la gestione possa prendere le migliori decisioni possibili per gli aggiornamenti dei prezzi, i budget, il controllo dei costi e così via. I dati di origine utilizzati per l'analisi dei costi vengono gestiti in modo indipendente nella contabilità industriale. Di conseguenza, gli aggiornamenti della contabilità industriale non hanno effetto sui dati di origine. Tuttavia, quando si raccolgono i dati sui costi da diverse origini e soprattutto quando si importano i conti principali dalla contabilità generale in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition come elementi dei costi, vi è ridondanza di dati, poiché gli stessi dati esistono sia in contabilità generale che in contabilità industriale. Questa ridondanza è necessaria, poiché si utilizza la gestione finanziaria per la creazione di report esterni e la contabilità industriale per la creazione di report interni.

**Movimento CoGe di contabilità industriale**

Il movimento CoGe di contabilità industriale è un framework specializzato che determina come i processi, i valori e le quantità vengano immessi e presentati per un'area specifica della contabilità industriale. Il movimento CoGe di contabilità industriale definisce i processi e le regole per la misurazione dei costi sugli oggetti di costo. Tratta le transazioni costi e gestisce i documenti che registrano le modifiche apportate ai valori e alle quantità generati dalle transazioni costi.

**Voce di costo**

Le voci di costo sono il risultato di un trasferimento tramite connettori di dati dalle voci di contabilità generale, dalle allocazioni di costi e dalle voci dei costi registrate nei giornali di registrazione costi.

**Oggetto di costo**

Gli oggetti di costo sono qualsiasi tipo di oggetto cui vengono allocati i costi. Di seguito sono riportati alcuni oggetti di costo normali:

-   Prodotti
-   Progetti
-   Risorse
-   Reparti
-   Centri di costo
-   Aree geografiche

La gestione utilizza gli oggetti di costo per quantificare i costi, ma anche per determinare l'analisi di redditività.

**Elemento di costo**

Gli elementi di costo vengono utilizzati come una funzione per tenere traccia e classificare il flusso dei costi. Sono disponibili due tipi di elementi di costo: costi primari e costi secondari. **Costi primari** Gli elementi di costo primari rappresentano il flusso dei costi dalla contabilità finanziaria alla contabilità industriale. La struttura degli elementi di costo corrisponde alla struttura dei conti profitti e perdite in contabilità generale, dove un elemento di costo può corrispondere a un conto principale. Non tutti i conti principali devono essere rappresentati come elementi di costo in base ai requisiti aziendali. Ecco alcuni esempi di elementi di costo primari:

-   I costi delle merci vendute (COGs)
-   Costi indiretti materiali
-   Costi del personale
-   Costi energetici

**Elemento di costo secondario** 

Gli elementi di costo secondari rappresentano il flusso interno dei costi, perché tali costi vengono creati e utilizzati solo nella contabilità industriale. Gli elementi di costo secondari aiutano a garantire la possibilità di tenere traccia dell'origine dei costi. Questi elementi di costo vengono utilizzati nelle allocazioni dei costi e nei calcoli dei costi generali. Ecco alcuni esempi di elementi di costo secondari:

-   Costi di produzione
-   Costi generali di produzione, materiali e marketing

**Unità di controllo costi**

Un'unità di controllo dei costi rappresenta la struttura dei costi. Deve essere associata alle dimensioni relative a oggetti in un movimento CoGe di contabilità industriale.

**Versione**

Le versioni vengono utilizzate per simulare, visualizzare e confrontare i diversi risultati. Per impostazione predefinita, tutti i costi effettivi vengono visualizzati in una versione base nota come *effettiva*. Per i budget e i calcoli è possibile utilizzare tutte le versioni necessarie. Ad esempio, è possibile importare i dati del budget in una versione originale e quindi modificare il budget in una versione riveduta. Per i calcoli è possibile creare più versioni. In queste varie versioni è possibile creare calcoli utilizzando diverse regole di calcolo che verranno applicate per l'allocazione dei costi.

**Rendiconto**

I rendiconti sono visualizzazioni utilizzate dai manager responsabili del controllo dei costi. I rendiconti vengono definiti da un supervisore dei costi e offrono una breve panoramica dei costi effettivi e di quelli a budget e persino le deviazioni e le versioni di calcolo. Per contribuire a garantire che i responsabili visualizzino solo i dati di cui sono responsabili, i dati mostrati nei rendiconti devono essere conformi alle regole di accesso.

**Connettore dati**

I dati possono essere inclusi nella contabilità industriale da sistemi esterni tramite connettori di dati. Ad esempio, è possibile importare le strutture dei conti, le dimensioni, le voci di contabilità generale e di budget. È possibile utilizzare i connettori preconfigurati di dati o i connettori personalizzati per importare i dati e creare le connessioni ai dati.

**Classificazione costi**

I gruppi di classificazione dei costi costano in base alle relative caratteristiche comuni. Ad esempio, i costi possono essere raggruppati in base agli elementi, alla tracciabilità e al comportamento.

-   **In base agli elementi** - Materiali, manodopera e costi.
-   **In base alla tracciabilità** - Costi diretti e indiretti. I costi diretti sono assegnati direttamente agli oggetti di costo. I costi indiretti non sono direttamente riconducibili agli oggetti di costo. I costi indiretti vengono allocati agli oggetti di costo.
-   **In base al comportamento** - Fisso, variabile e semi variabile.

**Comportamento costo**

Il comportamento costo classifica i costi in base al loro comportamento in relazione alle modifiche apportate alle principali attività economiche. Per controllare i costi in modo efficace, la gestione deve comprendere il comportamento costo. Sono disponibili tre tipi di modelli di comportamento costo: fisso, variabile e semi-variabile.

- **Costo fisso** Un costo fisso è un costo che non varia nel breve termine, indipendentemente dalle modifiche apportate al livello di attività. Ad esempio, un costo fisso può essere un costo operativo di base di una società, ad esempio l'affitto, che non subirà modifiche anche se il livello di attività aumenta o diminuisce.

- **Costo variabile** - Un costo variabile varia a seconda delle modifiche apportate al livello di attività. Ad esempio, un costo specifico dei materiali diretti è associato a ciascun prodotto che viene venduto. Più prodotti vengono venduti, più sono i costi dei materiali diretti.

- **Costo semi-variabile** - I costi semi-variabili sono costi parzialmente fissi e parzialmente variabili. Ad esempio, una commissione di accesso a Internet include una commissione mensile standard di accesso e una commissione di utilizzo della banda larga. La commissione mensile standard di accesso è un costo fisso, mentre la commissione per l'utilizzo della banda larga è un costo variabile.

**Costi generali**

I costi generali si riferiscono alle spese in corso per la gestione di un'azienda. Sono i costi che non possono essere collegati direttamente ad attività economiche specifiche. Di seguito sono riportati alcuni esempi di costi generali:

-   Spese contabili
-   Ammortamenti
-   Assicurazione
-   Interessi
-   Spese notarili
-   Imposte
-   Costi di utilità

**Distribuzione costi**

La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante. La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.

**Allocazione costi**

L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione. Finance and Operations supporta il metodo di allocazione reciproco. Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti. Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni. Il saldo di un oggetto costo viene assegnato da una singola base di allocazione. Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate. L'ordine di allocazione è controllato dall'unità di controllo dei costi.

**Criteri di allocazione costi**

I criteri di allocazione costi consentono di definire gli importi e le quantità da allocare. Le regole di allocazione includono le regole di origine allocazione, che determinano i costi che vengono allocati, e le regole di destinazione allocazione, che determinano la destinazione in cui vengono allocati i costi. Ad esempio, tutti i costi dei servizi della struttura sono un'origine allocazione che può essere assegnata a diversi reparti di un'organizzazione, ovvero gli obiettivi di allocazione.

**Base di allocazione**

La base di allocazione costituisce la base da utilizzare per misurare e quantificare le attività, ad esempio le ore-macchina utilizzate, i kilowattora consumati, le ore di manodopera spese o la metratura occupata. Viene utilizzata per allocare i costi a uno o più oggetti di costo.

**Principio di allocazione**

Uno dei principi di allocazione è quello di allocare i costi in base al tasso di costo. È possibile scegliere di allocare i costi utilizzando il tasso effettivo del periodo o un tasso storico. L'allocazione che utilizza il metodo reciproco consente di garantire che la base di un'allocazione sia determinata da una serie di equazioni simultanee prima che l'allocazione venga eseguita usando il tasso effettivo del periodo.

**Rollup costi**

Lo scopo di eseguire il rollup dei costi è includere tutti i costi di un oggetto di costo specifico. Il livello di aggregazione viene definito dall'utente. Utilizzando il rollup costi, è possibile aggregare gli elementi dei costi che devono essere allocati da un oggetto di costo a un altro. Quando il rollup costi non viene utilizzato, ogni singolo elemento dei costi viene assegnato da un oggetto di costo a un altro.

**Criteri di tasso di costo**

Il tasso di costo viene utilizzato per calcolare il prezzo per oggetto di costo. Per conoscere gli elementi del prezzo, definire i criteri di tasso di costo. Sono disponibili due tipi di tasso di costo: tasso di costo storico e tasso di costo pianificato. Un tasso di costo storico è un tasso calcolato, utilizzato come moltiplicatore per la base di allocazione di un oggetto di costo. Il tasso viene calcolato in base alle allocazioni dei costi nel periodo precedente. Un tasso previsto è un tasso definito dall'utente.

**Gerarchia dimensioni**

Le gerarchie di dimensioni vengono utilizzate come strutture di reporting quando si definiscono regole di allocazione, tassi di costo e rollup costi, si visualizzano rendiconti o dati in Microsoft Excel e si definisce l'accesso ai dati aggregati. Sono disponibili due gerarchie di dimensioni: gerarchia di categorie e gerarchia di classificazione. Una gerarchia di categoria è definita in base agli elementi di costo, mentre una gerarchia di classificazione è definita in base agli oggetti di costo.

**Dimensione statistica**

Una dimensione statistica è l'espressione di un numero o di una somma di un oggetto che può essere utilizzato come base per le allocazioni o i calcoli dei tassi di costo. Viene creata manualmente o importata dai sistemi di origine. Esempi di dimensioni statistiche includono il numero di dipendenti, il numero di prodotti software concessi in licenza per ciascun dispositivo, il consumo di energia di ciascun computer o la metratura di un centro di costo.

**Voce statistica**

Le voci statistiche contengono il valore registrato del numero o della somma di una determinata dimensione statistica. Il valore registrato del numero o della somma viene denominato anche grandezza.




