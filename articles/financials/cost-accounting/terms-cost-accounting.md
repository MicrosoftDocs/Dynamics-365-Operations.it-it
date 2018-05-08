---
title: "Terminologia della contabilità industriale"
description: "In questo argomento vengono definiti i termini principali utilizzati in Contabilità industriale."
author: YuyuScheller
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostAccountingLedger
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 1ec2f4a407c705fb37681f5593d0f7ea31f4cf0f
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="cost-accounting-terminology"></a>Terminologia della contabilità industriale

[!include [banner](../includes/banner.md)]

In questo argomento vengono definiti i termini principali utilizzati in Contabilità industriale.

**Base di allocazione**

La base di allocazione viene utilizzata per misurare e quantificare le attività, ad esempio le ore-macchina utilizzate, i kilowattora (kWh) consumati o la metratura occupata. Viene utilizzata come base per allocare i costi a uno o più oggetti di costo.

**Contabilità industriale**

La contabilità industriale consente di raccogliere dati da diverse origini, ad esempio dalla contabilità generale, dalle contabilità ausiliarie, dai budget e dalle informazioni statistiche. È quindi possibile analizzare, riepilogare e valutare i dati sui costi, in modo che la gestione possa prendere le migliori decisioni possibili per gli aggiornamenti dei prezzi, i budget, il controllo dei costi e così via. I dati di origine utilizzati per l'analisi dei costi vengono gestiti in modo indipendente nella contabilità industriale. Di conseguenza, gli aggiornamenti della contabilità industriale non hanno effetto sui dati di origine. Tuttavia, quando si raccolgono i dati sui costi da diverse origini e soprattutto quando si importano i conti principali dalla contabilità generale in Microsoft Dynamics 365 for Finance and Operations come elementi dei costi, vi è ridondanza di dati, poiché gli stessi dati esistono sia in contabilità generale che in contabilità industriale. Questa ridondanza è necessaria, poiché si utilizza la gestione finanziaria per la creazione di report esterni e la contabilità industriale per la creazione di report interni.

**Movimento CoGe di contabilità industriale**

Definito da calendario, valuta e dimensione elemento di costo, definisce processi e criteri per la misurazione dei costi. 

**Voce di costo**

Le voci di costo sono il risultato di un trasferimento tramite connettori di dati dalle voci di contabilità generale, dalle allocazioni di costi e dalle voci dei costi registrate nei giornali di registrazione costi.

**Oggetto di costo**

Qualsiasi tipo di oggetto selezionato per il controllo dei costi. Costi o ricavi vengono direttamente registrati o allocati agli oggetti di costo. Alcuni oggetti di costo tipici sono:

-  Prodotti
-  Progetti
-  Reparti
-  Centri di costo

La gestione utilizza gli oggetti di costo per quantificare i costi, ma anche per determinare l'analisi di redditività.

**Elemento di costo**

Utilizzato come funzione per classificare e tenere traccia dei costi. Sono disponibili due tipi di elementi di costo: primari e secondari.

Gli elementi di costo primari rappresentano il flusso dei costi dalla contabilità finanziaria alla contabilità industriale. La struttura corrisponde alla struttura dei conti profitti e perdite in contabilità generale dove un elemento di costo può corrispondere a un conto principale. Non tutti i conti principali devono essere rappresentati come elementi di costo in base ai requisiti aziendali. 

Gli elementi di costo secondari rappresentano il flusso interno dei costi, perché tali costi vengono utilizzati solo nella contabilità industriale. Sono utilizzati nelle regole di rollup dei costi per aggregare i costi in intervalli significativi utilizzati nel calcolo dei costi generali. 

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

**Unità di controllo costi**

L'unità di controllo costi rappresenta la struttura dei costi. La struttura determina il flusso dei costi in un ordine gerarchico tra le dimensioni oggetto di costo e i rispettivi oggetti di costo. 

**Distribuzione costi**

È utilizzata per ridistribuire i costi da un oggetto di costo a uno o più oggetti di costo applicando una base di allocazione rilevante. La distribuzione costi e l'allocazione costi differiscono per il fatto che la distribuzione costi si verifica sempre a livello dell'elemento di costo primario del costo originale e senza elaborazione reciproca.

**Allocazione costi**

È utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione. Finance and Operations supporta il metodo di allocazione reciproco. Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti. Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni e lo reitera. Il saldo di un oggetto costo viene assegnato da una singola base di allocazione. Le allocazioni in più dimensioni di oggetto costo e i rispettivi membri sono supportate. L'ordine di allocazione è controllato dall'unità di controllo dei costi.

**Criteri di allocazione costi**

I criteri di allocazione costi consentono di definire gli importi e le quantità da allocare. Le regole di allocazione includono le regole di origine allocazione, che determinano i costi che vengono allocati, e le regole di destinazione allocazione, che determinano la destinazione in cui vengono allocati i costi. Ad esempio, tutti i costi dei servizi della struttura sono un'origine allocazione che può essere assegnata a diversi reparti di un'organizzazione, ovvero gli obiettivi di allocazione.

**Rollup costi**

Lo scopo delle regole di rollup costi è aggregare i costi in intervalli significativi. Il livello di aggregazione viene definito dall'utente e comporta l'assegnazione di un elemento di costo secondario. Se il rollup costi non viene utilizzato, ogni elemento di un costo viene assegnato da un oggetto di costo a un altro.

**Criteri di tasso di costo**

Il tasso di costo viene utilizzato per calcolare il prezzo per oggetto di costo. Per conoscere gli elementi del prezzo, definire i criteri di tasso di costo. Sono disponibili due tipi di tasso di costo: tasso di costo storico e tasso di costo pianificato. Un tasso di costo storico è un tasso calcolato, utilizzato come moltiplicatore per la base di allocazione di un oggetto di costo. Il tasso viene calcolato in base alle allocazioni dei costi nel periodo precedente. Un tasso previsto è un tasso definito dall'utente.

**Gerarchia dimensioni**

Sono disponibili due gerarchie di dimensioni: gerarchia di categorie e gerarchia di classificazione. Il tipo Gerarchia di categorie di dimensioni viene utilizzato per il reporting. Supporta solo le dimensioni elemento di costo. Il tipo Gerarchia classificazioni dimensione viene utilizzato per definire i criteri e per il reporting. Supporta tutte le dimensioni, quali gli oggetti di costo, gli elementi di costo e le dimensioni statistiche. 

**Connettore dati**

La contabilità industriale supporta l'integrazione dei dati da sistemi di origine tramite un insieme di connettori dati. Sono disponibili i seguenti connettori dati:

-  Transazioni importate (preconfigurate)
-  Dynamics 365 for Finance and Operations (pre-configurato)
-  Dynamics AX (configurazione obbligatoria)

**Nota:** il connettore dati Transazioni importate è basato sulle entità di dati.

**Provider dati**

La maggior parte dei sistemi di origine possono fornire dati che corrispondono a una o più origini dati nella contabilità industriale. Per allineare i dati dei sistemi di origine all'origine dati nella contabilità industriale, è necessario configurare un provider dati. Nella seguente tabella è elencata la disponibilità dei provider dati per connettore dati e origine dati.

|  **Origini dati** |  **Connettore dati Transazioni importate** | **Connettore dati Dynamics 365 for Finance and Operations**  | **Connettore dati Dynamics AX**  |
|---|---|---|---|
| Membri di dimensione elemento di costo  |  Sì | Sì  | Sì  |
|  Membri di dimensione oggetto di costo |  Sì | Sì  | Sì  |
|  Membri di dimensione statistica | Sì  | No  | No  |
|  Contabilità generale | Sì  | Sì  | Sì  |
|  Voci di budget  | Sì  | Sì  | Sì  |
|  Misure statistiche | Sì  | Sì  | Sì  |

**Formula**

Le base di allocazione della formula consente di definire le formule avanzate per ottenere una corretta base di allocazione. È possibile creare manualmente le basi di allocazione della formula. È possibile utilizzare i seguenti operatori per definire la formula.

|  **Simboli** | **Testo**  |
|---|---|
|  ( ) | Parentesi  |
|  < |  Minore di |
|  > |  Maggiore di |
|  + |  Addizione |
|  – |  Sottrazione |
| *  | Moltiplicazione  |

Le istruzioni tradizionali IF non sono supportate. Tuttavia, è possibile creare istruzioni e convalidare se sono true.

|  **Convalida rendiconto** | **Risultato**  |
|---|---|
|  a > b| True  |
|  a > b |  False |

**Costi generali**

I costi generali si riferiscono alle spese in corso per la gestione di un'azienda. Sono i costi che non possono essere collegati direttamente ad attività economiche specifiche. Di seguito sono riportati alcuni esempi di costi generali:

-   Spese contabili
-   Ammortamenti
-   Assicurazione
-   Interessi
-   Spese notarili
-   Imposte
-   Costi di utilità

**Tasso generale**

I tassi vengono definiti per oggetto di costo ed elemento di costo. Sono disponibili due tipi di tassi: periodo fiscale e specifico dell'utente. I tassi del periodo fiscale sono calcolati mediante il calcolo dei costi generali. Un tasso specifico dell'utente è definito dall'utente e può essere utilizzato per allocare i costi tra oggetti di costo ad un tasso predeterminato nel calcolo dei costi generali.

**Pubblicate**

Se si imposta il campo su Sì, un utente con uno dei seguenti ruoli può visualizzare il report nell'area di lavoro Controllo costi:

-  Responsabile contabilità industriale
-  Contabile
-  Addetto contabilità
-  Controller oggetto di costo

Se si imposta il campo su No, solo gli utenti assegnati a uno dei seguenti ruoli può visualizzare il report nell'area di lavoro Controllo costi:

-  Responsabile contabilità industriale
-  Contabile
-  Addetto contabilità

**Dimensione statistica**

Una dimensione statistica e i relativi membri vengono utilizzati per registrare e monitorare le voci non monetarie nella contabilità industriale. I membri di dimensione statistica possono essere utilizzati per due scopi:

-  Come base di allocazione nei criteri quali la distribuzione costi o l'allocazione costi.
-  Per la dichiarazione del consumo non monetario.

Una dimensione statistica è l'espressione di un numero o di una somma di un'attività che può essere utilizzato come base per le allocazioni o i calcoli dei tassi di costo. Viene creata manualmente o importata dai sistemi di origine. Esempi di dimensioni statistiche includono il numero di dipendenti, il numero di prodotti software concessi in licenza per ciascun dispositivo, il consumo di energia di ciascun computer o la metratura di un centro di costo.

**Istruzione**

I rendiconti sono visualizzazioni utilizzate dai manager responsabili del controllo dei costi. I rendiconti sono definiti da un supervisore dei costi e forniscono una rapida panoramica dei costi effettivi, dei costi a budget e delle deviazioni. Un responsabile può visualizzare dati ancor più dettagliati se necessario. Per essere certi che i responsabili visualizzano solo i dati di cui sono responsabili, i dati mostrati nei rendiconti devono essere conformi alle regole di accesso.

**Versione**

Le versioni vengono utilizzate per simulare, visualizzare e confrontare i diversi risultati. Per impostazione predefinita, tutti i costi effettivi vengono visualizzati in una versione base nota come *effettiva*. Per i budget e i calcoli è possibile utilizzare tutte le versioni necessarie. Ad esempio, è possibile importare i dati del budget in una versione originale e quindi modificare il budget in una versione riveduta. Per i calcoli è possibile creare più versioni. In queste varie versioni è possibile creare calcoli utilizzando diverse regole di calcolo che verranno applicate per l'allocazione dei costi.



