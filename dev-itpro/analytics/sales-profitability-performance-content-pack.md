---
title: "Contenuto Power BI per le prestazioni di vendite e redditività"
description: "In questo argomento sono descritti gli argomenti inclusi in Dynamics 365 for Operations - Pacchetto di contenuti per le prestazioni di vendite e redditività per Microsoft Power BI. Viene descritto come accedere ai report inclusi nel pacchetto di contenuti e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il pacchetto di contenuti."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 357f7071d801b13518c83170f8d0e7946dd9dede
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Contenuto Power BI per le prestazioni di vendite e redditività

[!include[banner](../includes/banner.md)]


In questo argomento sono descritti gli argomenti inclusi in Dynamics 365 for Operations - Pacchetto di contenuti per le prestazioni di vendite e redditività per Microsoft Power BI. Viene descritto come accedere ai report inclusi nel pacchetto di contenuti e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il pacchetto di contenuti.

<a name="overview"></a>Panoramica
--------

Questo pacchetto di contenuti è stato creato per i manager delle vendite per monitorare le metriche delle vendite chiave relative a fatturato, profitto lordo e margini di profitto. Utilizza i dati transazionali delle vendite provenienti da Microsoft Dynamics 365 for Operations e offre sia una visualizzazione aggregata delle cifre delle vendite a livello di società che una scomposizione dettagliata delle prestazioni delle vendite per clienti e prodotti. Evidenziando le modifiche nel fatturato e nella crescita di profitto nel tempo, i report possono essere utilizzati per segnalare ai responsabili le tendenze positive e negative per singoli clienti e prodotti. I responsabili di categoria e regionali troveranno utile disporre di grafici che mettono a confronto il fatturato e la redditività di categorie di prodotti e gruppi di clienti diversi per individuare quelli con prestazioni scadenti e quelli con prestazioni ottimali. Un report completo che traccia i ricavi rispetto al margine di profitto di un singolo cliente offre agli account manager informazioni basate sui dati per adattare le attività di vendite e marketing al profilo specifico di ciascun cliente. Il pacchetto di contenuti per le prestazioni di vendite e redditività consente ai responsabili delle vendite di analizzare le prestazioni delle vendite in base ai seguenti elementi:

-   Ricavi, da inizio anno (per gruppo di clienti e singoli clienti, categorie di vendita, nonché singoli prodotti e aree geografiche)
-   Modifica nei ricavi, su base annua (per regioni dei clienti e categorie di vendita)

La redditività può essere analizzata in base ai seguenti elemento:

-   Profitto lordo e margine di profitto (per gruppi di clienti e categorie di vendita di prodotti)
-   Modifica nel profitto lordo, su base annua
-   Redditività del cliente (per ricavi rispetto a margine lordo)

## <a name="accessing-the-content-pack"></a>Accesso al pacchetto di contenuti
Il pacchetto di contenuti Power BI per le prestazioni di vendite e redditività viene pubblicato come risorsa di implementazione in Lifecycle Services (LCS) ed è possibile accedervi da Dynamics 365 for Operations. Per ulteriori informazioni su come accedere ai report Power BI e aprirli, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md).
**Nota**: l'articolo KB 4011327 è un prerequisito per questo contenuto Power BI. Dopo avere eseguito l'accesso a Lifecycle Services, è possibile accedere alla KB qui: : <a href="https://fix.lcs.dynamics.com/issue/results/?q=kb4011327">https://fix.lcs.dynamics.com/issue/results/?q=kb4011327</a>.

## <a name="metrics-included-in-the-content-pack"></a>Metriche incluse nel pacchetto di contenuti
Il pacchetto di contenuti include un report costituito da un set di metriche visualizzate come grafici, riquadri e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel pacchetto di contenuti.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| **Pagina di report**        | **Grafici**                                 | **Riquadri**                                               |
| Ricavi per cliente    | Primi 10 clienti in base ai ricavi                | Totale ricavi                                           |
|                        | Totale ricavi per gruppo di clienti            | Crescita dei ricavi su base annua                                      |
|                        | Media dei ricavi del cliente per gruppo di clienti | Margine lordo                                            |
|                        | Ricavi e profitto lordo per gruppo di clienti   |                                                         |
| Ricavi per prodotto     | Ricavi e profitto lordo per categoria di vendita   | \# totale di prodotti                                    |
|                        | Primi 10 prodotti in base ai ricavi                 | Numero totale di prodotti attivi e percentuale del totale |
|                        | Totale ricavi per categoria di vendita            | Numero di prodotti che rappresentano l'80% dei ricavi           |
| Ricavi per periodo\*    | Ricavi al mese                           | Crescita dei ricavi su base annua                                      |
|                        | Scostamento finale dei ricavi, su base annua             | % di crescita dei ricavi su base annua                                    |
|                        | Scostamento totale delle vendite per regione del cliente    |                                                         |
| Ricavi per ubicazione    | Ricavi di vendita per città                      |                                                         |
|                        | % di crescita dei ricavi su base annua                       |                                                         |
|                        | Ricavi di vendita per regione                    |                                                         |
| Redditività del cliente | Margine lordo rispetto a ricavi, per cliente   | Profitto lordo, margine lordo, crescita dei ricavi su base annua          |
| Analisi redditività | Ricavi e profitto lordo al mese          |                                                         |
|                        | Primi 15 clienti per margine lordo           |                                                         |
|                        | Profitto lordo al mese, su base annua                 |                                                         |

\* Ricavi nell'anno corrente e nell'anno passato e crescita per categoria di vendita.

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
I dati di Dynamics 365 for Operations vengono utilizzati per compilare il report nel pacchetto di contenuti per le prestazioni di vendite e redditività. Questi dati sono rappresentati come misure aggregate che vengono collocate nell'Archivio entità, ovvero un database di Microsoft SQL ottimizzato per l'analisi. Ulteriori informazioni sono disponibili nel blog [Integrazione di Power BI con l'Archivio entità in Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Le misure di aggregazione in questo pacchetto di contenuti sono il sottoinsieme delle misure di aggregazione disponibili nel cubo Vendite in Dynamics AX 2012 e AX 2012 R3. Per rappresentare le misure di aggregazione del cubo nell'Archivio entità, è necessario renderle distribuibili. Per ulteriori informazioni, vedere la procedura su come rappresentare le misure di aggregazione nell'Archivio entità nel blog [Integrazione di Power BI con l'Archivio entità in Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Le seguenti misure di aggregazione chiave dell'entità delle righe della fattura sono utilizzate come base del pacchetto di contenuti.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entità**    | **Misure di aggregazione chiave**               | **Origine dati per Dynamics 365 for Operations** | **Campo**                                    | **Descrizione**                          |
| Righe fattura | Ricavi                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Importo nella valuta di contabilizzazione            |
|               | Costo del venduto                           | InventTrans                                     | SUM(CostAmountPosted + CostAmountAdjustment) | Importo costi + correzione                 |
|               | Importo riga commissione - valuta di contabilizzazione | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | Importo commissione nella valuta di contabilizzazione |

Nella tabella seguente vengono illustrate le misure di aggregazione chiave dell'entità delle righe della fattura utilizzate per creare diverse misure calcolate nel set di dati del pacchetto di contenuti.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Unità di misura**       | **Calcolato come**                                                                                |
| Profitto lordo      | SUM(Ricavi - COGS - Commissione - IVA (inclusa nell'importo della riga fattura cliente))          |
| Margine lordo      | SUM(Profitto lordo/(Ricavi - IVA (inclusa nell'importo della riga fattura cliente)))             |
| Ricavi nell'anno passato | Ricavi nell'anno passato = CALCULATE(SUM('Righe fattura'\[Ricavi\]), SAMEPERIODLASTYEAR(Dates\[Data\]) |

Le dimensioni chiave seguenti nel **cubo Vendite** vengono utilizzate come filtri per dividere le misure di aggregazione per ottenere una maggiore granularità e informazioni analitiche più approfondite.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entità**       | **Esempi di attributi**                           |
| Clienti        | Gruppi di clienti, regioni dei clienti, indirizzo, settore |
| Prodotti         | Numero prodotto, nome prodotto, nome dei gruppi di articoli       |
| Categorie di vendita | Nomi di categorie di vendita                                 |
| Persone giuridiche   | Nomi di persone giuridiche                                   |
| Appuntamenti            | Appuntamenti                                                |

Per impostazione predefinita, il pacchetto di contenuti visualizza i dati dell'anno di calendario corrente, ma è possibile aprire la sezione relativa ai filtri di report e modificare il filtro della data. È inoltre possibile modificare il filtro della società.

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](..\data-entities\data-entities.md)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](configure-power-bi-integration.md)





