---
title: "Contenuto Power BI per l'analisi della contabilità industriale"
description: "In questo argomento viene descritto cosa è incluso nel contenuto di Power BI per l'analisi della contabilità industriale. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto."
author: AndersGirke
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: aac6439bb54b3b9cab066b06c01763e880efef8e
ms.openlocfilehash: 2d0fb4de84838f1778625d977bdd2ceeaac61f8c
ms.contentlocale: it-it
ms.lasthandoff: 12/18/2017

---

# <a name="cost-accounting-analysis-power-bi-content"></a>Contenuto Power BI per l'analisi della contabilità industriale

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto cosa è incluso nel contenuto **Analisi della contabilità industriale** di Microsoft Power BI. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI **Analisi della contabilità industriale** è destinato ai controller di costo o qualsiasi utente responsabile di eseguire il controllo dei costi di un'organizzazione. Include metriche chiave, ad esempio costi, grandezza e il tasso di costo per costo effettivo, costo a budget e costo a budget flessibile. Utilizza i dati delle transazioni del modulo **Contabilità industriale** e offre una visualizzazione aggregata dei costi per l'intera organizzazione in un'unica valuta di dichiarazione. I responsabili possono filtrare i dati in base agli oggetti di costo per eseguire il controllo dei costi delle unità organizzative, anche se l'organizzazione può avere più persone giuridiche. 

Poiché il contenuto **Analisi della contabilità industriale** evidenzia gli scostamenti tra i costi effettivi e i costi a budget, i responsabili possono ricevere una notifica delle tendenze positive e negative per le relative unità operative. I responsabili possono eseguire il drill-down delle gerarchie degli elementi di costo o dei singoli elementi di costo. In questo modo, i responsabili possono ottenere informazioni dettagliate sugli scostamenti di costo e intraprendere l'azione opportuna. 

Il contenuto **Analisi della contabilità industriale** consente ai contabili di analizzare come i costi fluiscono attraverso gli oggetti di costo dell'intera organizzazione. 

Per ulteriori informazioni sulla contabilità industriale, vedere [Home page di contabilità industriale](../../financials/cost-accounting/cost-accounting-home-page.md). 

Definendo la sicurezza a livello di accesso nella contabilità industriale e combinandola alla sicurezza a livello di riga in Power BI, è possibile concedere a tutti i proprietari degli oggetti di costo l'accesso al contenuto Power BI per l'**analisi della contabilità industriale**. Tutti i dati delle visualizzazioni verranno filtrati in base al livello di accesso che viene controllato nella contabilità industriale. Per ulteriori informazioni sulla sicurezza a livello di accesso e a livello di riga, vedere [Impostare la sicurezza del contenuto della contabilità industriale per Power BI](setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
È possibile trovare il contenuto Power BI per l'**analisi della contabilità industriale** nella libreria delle risorse di condivise in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni su come scaricare il contenuto e implementarlo nell'organizzazione, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/). Per guardare una demo che mostra come implementare il contenuto di Power BI, vedere [Contenuto di Power BI da Microsoft e partner in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).

Assicurarsi di scaricare il contenuto **Analisi della contabilità industriale** applicabile alla versione di Microsoft Dynamics 365 in uso.

> [!NOTE]
> KB 4011327 è un prerequisito per questo contenuto di Power BI. Dopo avere eseguito l'accesso a LCS, è possibile accedere alla KB all'indirizzo <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Metriche incluse nel contenuto Power BI
Il contenuto include un set di pagine di report. Ciascuna pagina è costituita da un set di metriche visualizzate come grafici, riquadri e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel contenuto Power BI per l'**analisi della contabilità industriale**.

| Pagina di report                      | Grafico                                                                                                                         | Riquadro                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Controllo costi per periodo fiscale    | Costo effettivo e costo a budget per livello di gerarchia di elementi di costo                                                                   | Costo effettivo rispetto a costo a budget                    |
|                                  | Scostamento dal budget per livello di gerarchia di elementi di costo                                                                               | Tasso di costo effettivo rispetto a tasso di costo a budget          |
|                                  | Primi 10 scostamenti da budget in percentuale per elemento di costo                                                                          | Grandezza effettiva rispetto a grandezza a budget          |
| Controllo costi per da inizio anno     | Costo effettivo e costo a budget per periodo anno di calendario                                                                           | Costo effettivo rispetto a costo a budget                    |
|                                  | Scostamento budget per periodo anno di calendario                                                                                       | Tasso di costo effettivo rispetto a tasso di costo a budget          |
|                                  | Primi 10 scostamenti da budget in percentuale per elemento di costo                                                                          | Grandezza effettiva rispetto a grandezza a budget          |
| Tasso di costo per anno fiscale         | Tasso di costo effettivo per comportamento costo                                                                                             | Tasso di costo effettivo rispetto a tasso di costo a budget          |
|                                  | Tasso di costo effettivo, scostamento del tasso di costo a budget, percentuale del tasso di costo a budget e tasso di costo a budget per livello di gerarchia degli elementi di costo | Grandezza effettiva rispetto a grandezza a budget          |
|                                  | Scostamento dal budget per livello di gerarchia di elementi di costo                                                                               |                                               |
|                                  | Primi 10 scostamenti da budget in percentuale per elemento di costo                                                                          |                                               |
| Budget flessibile per periodo fiscale | Costo effettivo, costo a budget e costo a budget flessibile per livello di gerarchia di elementi di costo                                             | Grandezza effettiva rispetto a grandezza a budget          |
|                                  | Scostamento dal budget e scostamento dal budget flessibile per livello di gerarchia di elementi di costo                                                  | Costo effettivo rispetto a costo a budget flessibile           |
|                                  | Costo effettivo, costo a budget e costo a budget flessibile per comportamento costo e livello di gerarchia di elementi di costo                                  | Tasso di costo effettivo rispetto a tasso di costo a budget flessibile |
| Rendiconto costi per periodo fiscale  | Costo effettivo per livello di gerarchia di elementi di costo e nome membro dimensione oggetto di costo                                             |                                               |
|                                  | Costo effettivo per nome membro dimensione oggetto di costo e nome membro dimensione elemento di costo                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Analisi della contabilità industriale**. Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità. L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati. Per ulteriori informazioni, vedere [Panoramica dell'integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md). 

Le seguenti misure aggregazione chiave vengono utilizzate come base del contenuto.

| Entità                  | Misura di aggregazione chiave | Origine dati per Dynamics 365      | Campo     | descrizione                                        |
|-------------------------|---------------------------|-----------------------------------|-----------|----------------------------------------------------|
| Voci contabilità industriale | SUM(Importo)               | CAMDATAAggregatedCostEntry        | Importo    | Importo nella valuta di contabilità industriale. |
| Voci statistiche     | SUM(Grandezza)            | CAMDATAAggregatedStatisctialEntry | Grandezza |                                                    |

Nella tabella seguente vengono illustrate le misure di aggregazione chiave utilizzate per creare diverse misure calcolate nel set di dati del contenuto.

| Unità di misura                                       | Come la misura viene calcolata                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Costo effettivo                                   | CALCULATE('Voci contabilità industriale'\[Misura\], 'Versioni transazione'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 0)            |
| Costo budget                                   | CALCULATE('Voci contabilità industriale'\[Misura\], 'Versioni transazione'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 1)            |
| Scostamento dal costo a budget                          | \[Costo a budget\] - \[Costo effettivo\]                                                                                      |
| Percentuale di scostamento budget                    | IF(\[Costo a budget\] = 0, blank(), \[Scostamento budget\] / \[Costo a budget\])                                                |
| Grandezza effettiva                              | CALCULATE('Voci statistiche'\[FullMagnitude\], 'Versioni transazione'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 0)          |
| Grandezza budget                              | CALCULATE(\[FullMagnitude\], 'Versioni transazione'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 1)                               |
| Scostamento da budget statistico                   | \[Grandezza budget\] - \[Grandezza effettiva\]                                                                            |
| Percentuale di scostamento budget statistico        | IF(\[Grandezza budget\] = 0, blank(), \[Scostamento budget statistico\] / \[Grandezza budget\])                          |
| Tasso di costo effettivo                              | IF(\[Grandezza effettiva\] = 0, BLANK(), \[Costo effettivo\] / \[Grandezza effettiva\])                                          |
| Tasso di costo in budget                              | IF(\[Grandezza budget\] = 0, BLANK(), \[Costo budget\] / \[Grandezza budget\])                                          |
| Scostamento tasso di costo budget                     | \[Tasso di costo budget\] - \[Tasso di costo effettivo\]                                                                            |
| Percentuale scostamento tasso di costo budget          | IF(\[Costo a budget\] = 0, blank(), \[Scostamento tasso di costo budget\] / \[Tasso di costo a budget\])                                 |
| Costo a budget cespiti                             | CALCULATE(\[Costo a budget\], 'Voci contabilità industriale'\[COSTBEHAVIOR\] = 1)                                              |
| Costo a budget variabile                          | CALCULATE(\[Costo a budget\], 'Voci contabilità industriale'\[COSTBEHAVIOR\] = 2)                                              |
| Costo a budget flessibile cespiti                    | \[Costo a budget cespiti\]                                                                                                  |
| Costo a budget flessibile variabile                 | IF(\[Grandezza budget\] = 0, BLANK(), (\[Costo a budget variabile\] / \[Grandezza budget\]) \* \[Grandezza effettiva\])       |
| Costo a budget flessibile                          | \[Costo a budget flessibile cespiti\] + \[Costo a budget flessibile variabile\]                                                     |
| Scostamento budget flessibile                      | \[Costo budget flessibile\] - \[Costo effettivo\]                                                                             |
| Percentuale di scostamento budget flessibile           | IF(\[Costo a budget flessibile\] = 0, BLANK(), \[Scostamento budget flessibile\] / \[Costo a budget flessibile\])                     |
| Tasso di costo a budget flessibile                     | IF(\[Grandezza effettiva\] = 0, BLANK(), \[Costo a budget flessibile\] / \[Grandezza effettiva\])                                 |
| Scostamento tasso di costo budget flessibile            | \[Tasso di costo budget flessibile\] - \[Tasso di costo effettivo\]                                                                   |
| Percentuale scostamento tasso di costo budget flessibile | IF(\[Tasso di costo a budget flessibile\] = 0, BLANK(), \[Scostamento tasso di costo a budget flessibile\] / \[Tasso di costo a budget flessibile\]) |

Le dimensioni chiave seguenti vengono utilizzate come filtri per dividere le misure di aggregazione e ottenere una maggiore granularità e fornire informazioni analitiche più approfondite.

| Entità                             | Esempi di attributi                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Movimenti CoGe di contabilità industriale            | Movimento CoGe di contabilità industriale                                                                                               |
| Unità di controllo costi                 | Nome unità di controllo costi                                                                                               |
| Dimensioni elemento di costo            | Nome dimensione elementi di costo, Nome membro dimensione elementi di costo, Descrizione membro dimensione elementi di costo          |
| Dimensioni oggetto di costo             | Nome dimensione oggetti di costo, Nome membro dimensione oggetti di costo, Descrizione membro dimensione oggetti di costo              |
| Dimensioni statistiche             | Nome dimensione statistica, Nome membro dimensione statistica, Descrizione membro dimensione statistica              |
| Gerarchie dimensioni di oggetto di costo  | Nome gerarchia di dimensioni oggetti di costo, Livello di gerarchia di dimensioni oggetti di costo, Struttura gerarchica di dimensioni oggetti di costo    |
| Gerarchie dimensioni di elementi di costo | Nome gerarchia di dimensioni elementi di costo, Livello di gerarchia di dimensioni elementi di costo, Struttura gerarchica di dimensioni elementi di costo |
| Gerarchie di dimensioni statistiche  | Nome gerarchia di dimensioni statistiche, Livello di gerarchia di dimensioni statistiche, Struttura gerarchica di dimensioni statistiche    |
| Versioni transazione               | Nome versione                                                                                                         |
| Calendari fiscali                   | Calendario, Descrizione del calendario                                                                                       |
| Anni fiscali                       | Anno di calendario                                                                                                        |
| Periodi fiscali                     | Periodo anno di calendario                                                                                                 |

