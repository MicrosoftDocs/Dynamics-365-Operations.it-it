---
title: Contenuto Power BI per prestazioni di vendite e redditività
description: In questo argomento viene descritto cosa è incluso nel contenuto Power BI Prestazioni di vendita e redditività.
author: ShylaThompson
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesProfitabilityPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6eb5a78c6ac4ad13ad1d263c557359ad2f789cc0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569914"
---
# <a name="sales-and-profitability-performance-power-bi-content"></a>Contenuto Power BI per prestazioni di vendite e redditività

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto cosa è incluso nel contenuto **Prestazioni di vendita e redditività** di Microsoft Power BI. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI **Prestazioni di vendita e redditività** è stato creato in modo che i responsabili delle vendite possano controllare le metriche chiave relative alle vendite di ricavi, profitto lordo e margini di profitto. Utilizza i dati transazionali delle vendite e offre sia una visualizzazione aggregata delle cifre delle vendite a livello di società che una scomposizione dettagliata delle prestazioni delle vendite per clienti e prodotti.

I report evidenziano le modifiche nel tempo di ricavi e profitto. Di conseguenza, è possibile utilizzarli per avvisare i responsabili sulle tendenze positive e negative per singoli clienti e prodotti. Inoltre, i grafici mettono a confronto ricavi e redditività delle diverse categorie dei prodotti e gruppi di clienti. Di conseguenza, i responsabili di categoria e area possono identificare prestazioni scadenti e prestazioni ottimali. Infine, un report completo mette a confronto i ricavi di un singolo cliente con il margine di profitto. Di conseguenza, i responsabili del conto hanno una base supportata da dati che possono utilizzare per ottimizzare le vendite e le iniziative di marketing per ogni profilo cliente.

Il contenuto **Prestazioni di vendita e redditività** consente ai responsabili delle vendite di analizzare le prestazioni nei seguenti modi:

- Ricavi, da inizio anno (per gruppo di clienti e singoli clienti, categorie di vendita, nonché singoli prodotti e aree geografiche)
- Modifica nei ricavi, su base annua (per regioni dei clienti e categorie di vendita)

La redditività può essere analizzata nei seguenti modi:

- Profitto lordo e margine di profitto (per gruppi di clienti e categorie di vendita di prodotti)
- Modifica nel profitto lordo, su base annua
- Redditività del cliente (per ricavi rispetto a margine lordo)

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Il contenuto di Power BI **Prestazioni di vendita e redditività** viene mostrato nella pagina **Prestazioni di vendita e redditività** (**Vendite e marketing** \> **Richieste di informazioni e report** \> **Analisi delle prestazioni di vendita** \> **Prestazioni di vendita e redditività**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Metriche incluse nel contenuto Power BI
Il contenuto di Power BI **Prestazioni di vendita e redditività** include un report costituito da un set di metriche. Queste metriche vengono visualizzate come grafici, riquadri e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel contenuto.

| Pagina di report            | Grafici                                     | Riquadri                                                   |
|------------------------|--------------------------------------------|---------------------------------------------------------|
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
I seguenti dati vengono utilizzati per compilare il report nel contenuto Power BI **Prestazioni di vendita e redditività**. Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità. L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati. Per ulteriori informazioni, vedere [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).

Le misure di aggregazione in questo pacchetto di contenuti sono il sottoinsieme delle misure di aggregazione disponibili nel cubo Vendite in Microsoft Dynamics AX 2012 e Microsoft Dynamics AX 2012 R3. Per rappresentare le misure di aggregazione del cubo nell'Archivio entità, è necessario renderle distribuibili. Per ulteriori informazioni, vedere la procedura per la rappresentazione delle misure di aggregazione nell'Archivio entità nel post del blog [Integrazione di  Power BI con l'Archivio entità in Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/).

Le seguenti misure di aggregazione chiave dell'entità delle righe della fattura sono utilizzate come base del contenuto.

| Entità        | Misure di aggregazione chiave                   | Origine dati per Dynamics 365 | Campo                                        | Descrizione                                       |
|---------------|----------------------------------------------|------------------------------|----------------------------------------------|---------------------------------------------------|
| Righe fattura | Ricavi                                      | CustInvoiceTrans             | SUM(LineAmountMST)                           | Importo nella valuta di contabilizzazione.            |
|               | Costo del venduto                           | InventTrans                  | SUM(CostAmountPosted + CostAmountAdjustment) | La somma dell'importo costi e della correzione.    |
|               | Importo riga commissione - valuta di contabilizzazione | CustInvoiceTrans             | SUM(CommissAmountMST)                        | Importo commissione espresso nella valuta di contabilizzazione. |

Nella tabella seguente vengono illustrate le misure di aggregazione chiave dell'entità delle righe della fattura utilizzate per creare diverse misure calcolate nel set di dati del pacchetto di contenuti.

| Unità di misura           | Calcolo                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| Profitto lordo      | SUM(Ricavi - COGS - Commissione - IVA (inclusa nell'importo della riga fattura cliente))          |
| Margine lordo      | SUM(Profitto lordo/(Ricavi - IVA (inclusa nell'importo della riga fattura cliente)))             |
| Ricavi nell'anno passato | Ricavi nell'anno passato = CALCULATE(SUM('Righe fattura'\[Ricavi\]), SAMEPERIODLASTYEAR(Dates\[Data\]) |

La seguenti dimensioni chiave nel cubo vendite vengono utilizzate come filtri per dividere le misure di aggregazione in modo da poter ottenere una maggiore granularità e informazioni analitiche più approfondite.

| Entità           | Esempi di attributi                               |
|------------------|------------------------------------------------------|
| Clienti        | Gruppi di clienti, regioni dei clienti, indirizzo, settore |
| Prodotti         | Numero prodotto, nome prodotto, nome dei gruppi di articoli       |
| Categorie di vendita | Nomi di categorie di vendita                                 |
| Persone giuridiche   | Nomi di persone giuridiche                                   |
| Appuntamenti            | Appuntamenti                                                |

Per impostazione predefinita, il contenuto mostra i dati dell'anno di calendario corrente. Tuttavia, è possibile modificare il filtro della data nella sezione relativa ai filtri di report. È inoltre possibile modificare il filtro della società.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]