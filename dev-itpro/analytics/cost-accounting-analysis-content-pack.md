---
title: "La contabilità industriale di analisi di contenuto Power BI"
description: "In questo argomento vengono descritte viene incluso nel contenuto di potenza di analisi della contabilità industriale BI. Descrive come accedere i report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 50e7bd92ee693f59fd013226aee22bd1a54c81e2
ms.lasthandoff: 03/31/2017


---

# <a name="cost-accounting-analysis-power-bi-content"></a>La contabilità industriale di analisi di contenuto Power BI

In questo argomento vengono descritte viene incluso nel contenuto di potenza di analisi della contabilità industriale BI. Descrive come accedere i report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

<a name="overview"></a>Panoramica
--------

** Analisi di contabilità industriale ** il contenuto di potenza di Microsoft BI serve ai controller dei costi o qualsiasi utente responsabile di eseguire il controllo dei costi di un'organizzazione. Include metriche chiave, ad esempio costi, grandezza e il tasso di costo da costo effettivo, dei costi in budget e dai costi in budget flessibile. Utilizza i dati della transazione da Contabilità industriale in Microsoft Dynamics 365 per le operazioni e offre una visualizzazione di aggregazione dei costi per l'intera organizzazione in una valuta di dichiarazione. I responsabili possono filtrare i dati in base agli oggetti di costo per eseguire il controllo dei costi delle unità organizzative, anche se l'organizzazione può avere più persone giuridiche. Poiché ** analisi della contabilità industriale ** il contenuto di Power BI vengono evidenziati gli scostamenti tra i costi effettivi e i costi a budget, i responsabili possono essere inviata una notifica sul valore positivo e negativa tende per le relative unità operative. I responsabili possono eseguire il drill-down alle gerarchie dell'elemento di costi o alle singole voci dei costi per ottenere alla descrizione dettagliata degli scostamenti come costi sono verificate e quindi per eseguire l'azione effettivo. ** Analisi di contabilità industriale ** il contenuto di Power BI dei costi contabili analizzare come costo tra gli oggetti di costo dell'intera organizzazione. Per ulteriori informazioni sulla contabilità industriale, vedere [Contabilità industriale home page] (/dynamics365/operations/financials/cost di contabilità/contabilità industriale - home-page.md). Definizione della protezione a livello dell'Access nella contabilità industriale e combinandola alla protezione riga riga in l Power BI, è possibile assegnare tutti i proprietari dei costi che oggetti l'accesso a ** analisi della contabilità industriale ** alimenta BI il contenuto. Tutti i dati delle visualizzazioni verranno filtrati in base al livello di accesso che viene controllato nella contabilità industriale. Per ulteriori informazioni sulla protezione a livello di dell'Access e protezione riga riga, vedere [protezione per impostare il contenuto della contabilità industriale per Power BI setup-security-cost-accounting-content-pack.md] ().

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto di Power BI
È possibile che ** analisi della contabilità industriale ** alimenti BI il contenuto della raccolta delle risorse condivise nei servizi (LCS) del ciclo di vita di Microsoft Dynamics. Per ulteriori informazioni su come download del contenuto e collegarlo al Dynamics 365 per le operazioni dati, vedere [di Power BI nel contenuto LC da Microsoft e dai partner power-bi-content-microsoft-partners.md] (). ** Nota: ** KB4011327 ** ** è un prerequisito per ** analisi della contabilità industriale ** del contenuto Power BI.  Dopo avere accesso ai servizi di ciclo di vita, è possibile accedere a KB di seguito: <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>In inclusa contenuto di Power BI
Il contenuto include un insieme delle pagine del report. Ciascuna pagina è costituita da un insieme criteri di valutazione che viene visualizzata come i grafici, le mattonelle e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni in ** analisi della contabilità industriale ** alimenta BI il contenuto.

| Pagina del report                      | Grafico                                                                                                                         | Riquadro                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Controllo costi del budget    | Costo effettivo e i costi in budget dal livello della gerarchia articoli di costo                                                                   | Costo effettivo dei costi in budget                    |
|                                  | Scostamento del budget del livello della gerarchia articoli di costo                                                                               | Tasso di costo effettivo in base al tasso di costo in budget          |
|                                  | Scostamento di budget principale 10 la percentuale dalla voce di costo                                                                          | Grandezza grandezza Effettivi rispetto al budget          |
| Controllo costi per anno finale     | Costo effettivo e i costi in budget per periodo di un anno di calendario                                                                           | Costo effettivo dei costi in budget                    |
|                                  | Scostamento di budget per il periodo di un anno di calendario                                                                                       | Tasso di costo effettivo in base al tasso di costo in budget          |
|                                  | Scostamento di budget principale 10 la percentuale dalla voce di costo                                                                          | Grandezza grandezza Effettivi rispetto al budget          |
| Tariffa costo per anno fiscale         | Tasso di costo effettivo tramite comportamento di costo                                                                                             | Tasso di costo effettivo in base al tasso di costo in budget          |
|                                  | Tasso di costo effettivo, scostamento dei tassi di costo in budget, percentuale del tasso di costo in budget e i costi in budget derivante dal livello della gerarchia articoli di costo | Grandezza grandezza Effettivi rispetto al budget          |
|                                  | Scostamento del budget del livello della gerarchia articoli di costo                                                                               |                                               |
|                                  | Scostamento di budget principale 10 la percentuale dalla voce di costo                                                                          |                                               |
| Budget flessibile del budget | Costo effettivo, costi in budget e i costi in budget flessibile dal livello della gerarchia articoli di costo                                             | Grandezza grandezza Effettivi rispetto al budget          |
|                                  | Scostamento di budget e scostamento di budget flessibile dal livello della gerarchia articoli di costo                                                  | Costo effettivo dei costi in budget flessibile           |
|                                  | Costo effettivo, costi in budget flessibile e costo da comportamento di costo e al livello della gerarchia articoli di costo                                  | Tasso di costi effettivi rispetto alla flessibile di costi in budget |
| Rendiconto dei costi del budget  | Il costo effettivo dal livello della gerarchia articoli costi e il costo obiettano il nome del membro di dimensioni                                             |                                               |
|                                  | Costo effettivo dal nome del membro del nome del membro delle dimensioni dell'oggetto e delle dimensioni dell'elemento di costo                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
Dynamics 365 per le operazioni che i dati vengono utilizzati per caricare le pagine del report in ** analisi della contabilità industriale ** alimentano BI il contenuto. Questi dati sono rappresentate come misure aggregate che sono con stato Approntato nella memoria di entità, ovvero un database di Microsoft SQL che viene ricerca per l'analisi dei dati. Per ulteriori informazioni, vedere [panoramica dei gruppi Administrators e Power Users di integrazione BI al punto vendita] dell'entità (power-bi-integration-entity-store.md). Le seguenti misure aggregate chiave vengono utilizzate come base del contenuto.

| Entità                  | Misura aggregata chiave | Origine dati per Dynamics 365 per le operazioni | Campo     | descrizione                                   |
|-------------------------|---------------------------|---------------------------------------------|-----------|-----------------------------------------------|
| Voci di contabilità industriale | SUM (importo)               | CAMDATAAggregatedCostEntry                  | Importo    | Importo nella valuta della contabilità generale della contabilità industriale |
| Voci statistiche     | SUM (grandezza)            | CAMDATAAggregatedStatisctialEntry           | Grandezza |                                               |

Nella tabella seguente vengono illustrate le misurazioni aggregate chiave vengono utilizzate per creare diverse misure calcolate nel set di dati del contenuto.

| Unità di misura                                       | Funzionamento di misura viene calcolata                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Costo effettivo                                   | CALCOLI ("VALORE\] di versions'entity_PLACEHOLDER [\\_ISSOURCEVERSIONBUDGET di misura\], "transazione del entries'entity_PLACEHOLDER \ [Contabilità industriale = 0)            |
| Costo budget                                   | CALCOLI ("misura\]Sales \ entries'entity_PLACEHOLDER [Contabilità industriale, "VALORE\] di versions'entity_PLACEHOLDER [\\_ISSOURCEVERSIONBUDGET di transazione = 1)            |
| Scostamento dei costi in budget                          | costo effettivo\]\] - \[dei costi in budget\[                                                                                      |
| Percentuale di scostamento di budget                    | IF (costi in budget\]\[= 0, vuota), costi in budget\]\] / \[di scostamento budget \[)                                                |
| Grandezza effettiva                              | CALCOLI ("entries'entity_PLACEHOLDER [\ statistico FullMagnitude\],\] "VALORE di versions'entity_PLACEHOLDER [\\_ISSOURCEVERSIONBUDGET di transazione = 0)          |
| Numero della grandezza                              | CALCOLI (FullMagnitude\[,\]a\] VALORE di versions'entity_PLACEHOLDER [\\_ISSOURCEVERSIONBUDGET di transazione = 1)                               |
| Scostamento di budget statistico                   | grandezza di\]\] - \[grandezza di budget\[                                                                            |
| Percentuale di scostamento statistiche di budget        | IF (grandezza del budget\]\[= 0, vuota), grandezza statistica\]\]budget\] / \[di scostamento budget \[)                          |
| Tasso di costo effettivo                              | IF (grandezza di\]\[= 0, VUOTO (), grandezza di\]\] / \[di costo effettivo \[)                                          |
| Tasso di costo in budget                              | IF (grandezza del budget\]\[= 0, VUOTO (),\]grandezza\]budget\] / \[dei costi in budget \[)                                          |
| Scostamento di tasso di costo in budget                     | \]tasso di costo effettivo\] - \[di tasso di costo in budget\[                                                                            |
| Percentuale di scostamento di tasso di costo in budget          | IF (costi in budget\]\[= 0, vuota),\]tasso di costo in budget\] / \[di scostamento percentuale dei costi in budget \[)                                 |
| Costo in budget fisso                             | (CALCOLI i costi in budget\]\[, a entries'entity_PLACEHOLDER [\\] COSTBEHAVIOR di contabilità industriale = 1)                                              |
| Costo in budget variabile                          | (CALCOLI i costi in budget\]\[, a entries'entity_PLACEHOLDER [\\] COSTBEHAVIOR di contabilità industriale = 2)                                              |
| Costo in budget flessibile fisso                    | \[Costo in budget fisso\]                                                                                                  |
| Costo in budget flessibile variabile                 | IF (grandezza del budget\]\[= 0, VUOTO (), (grandezza variabile del budget\]\] / \[dei costi in budget\[) grandezza di\]\* \[)       |
| Costo in budget flessibile                          | \[è stato riparato i costi in budget flessibile variabile flessibile\]\] + \[dei costi in budget                                                     |
| Scostamento di budget flessibile                      | costo effettivo flessibile\]\] - \[dei costi in budget\[                                                                             |
| Percentuale di scostamento flessibile di budget           | IF (costi in budget flessibile\]\[= 0, VUOTO (), costi in budget flessibile flessibile\]\] / \[di scostamento budget \[)                     |
| Tasso flessibile di costi in budget                     | IF (grandezza di\]\[= 0, VUOTO (), grandezza effettivo flessibile\]\] / \[dei costi in budget \[)                                 |
| Scostamento flessibile di tasso di costo in budget            | \]flessibile tasso di costo effettivo\] - \[di tasso di costo in budget\[                                                                   |
| Percentuale di scostamento flessibile di tasso di costo in budget | IF (tariffa flessibile\] dei costi in budget\[= 0, VUOTO (), il tasso flessibile flessibile\]dei costi in budget\] / \[di scostamento percentuale dei costi in budget \[) |

Nelle dimensioni chiave vengono utilizzate come filtri per affettare le misurazioni aggregate per ottenere una maggiore granularità e immettere le comprensioni analitiche più contrassegnate.

| Entità                             | Esempi di attributi                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Movimenti CoGe di contabilità industriale            | Movimento CoGe di contabilità industriale                                                                                               |
| Unità di controllo costi                 | Nome unità di controllo costi                                                                                               |
| Dimensioni elemento di costo            | Elementi di costo dimensionano il nome, il nome del membro di dimensioni articolo di costo, descrizione del membro di dimensioni articolo di costo          |
| Dimensioni oggetto di costo             | Nome di costo delle dimensioni dell'oggetto, il nome del membro di dimensione oggetti, descrizione dei membri della dimensione oggetti              |
| Dimensioni statistiche             | Nome statistico di dimensione, nome del membro statistico di dimensione, descrizione statistiche dei membri della dimensione              |
| Gerarchie di dimensioni relative a oggetti  | Nome di costo di gerarchia di dimensioni oggetti, il livello di gerarchia di dimensioni oggetti, di albero di gerarchia di dimensioni oggetti    |
| Gerarchie di dimensioni articolo di costo | Nome della gerarchia di dimensioni articolo, il livello di gerarchia di dimensioni articolo, di albero di gerarchia di dimensioni articolo di costo |
| Gerarchie di dimensioni statistiche  | Nome statistico di gerarchia di dimensioni, livello statistico di gerarchia di dimensioni, albero statistico di gerarchia di dimensioni    |
| Versioni transazione               | Nome versione                                                                                                         |
| Calendari fiscali                   | Calendario, descrizione del calendario                                                                                       |
| Chiudere gli anni fiscali                       | Anno di calendario                                                                                                        |
| Periodi fiscali                     | Periodo di anno di calendario                                                                                                 |

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](..\data-entities\data-entities.md)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](configure-power-bi-integration.md)
-   [Protezione di installazione e il contenuto della contabilità industriale per Power BI] () setup-security-cost-accounting-content-pack.md


