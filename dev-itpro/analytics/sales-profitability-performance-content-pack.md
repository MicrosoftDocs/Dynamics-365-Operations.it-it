---
title: "Vendite e di redditività di prestazione di contenuto Power BI"
description: "In questo argomento sono descritti gli argomenti inclusi in Dynamics 365 per le operazioni di vendita e pacchetto del contenuto delle prestazioni di redditività per Microsoft Power BI. Descrive come accedere ai report inclusi nel collo e documentazione vengono fornite informazioni sul modello dati e sulle entità utilizzati per sviluppare un pacchetto di contenuto."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 3e6b48768bb8e69d46f1555d9300f3b878b01ff1
ms.lasthandoff: 03/31/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Vendite e di redditività di prestazione di contenuto Power BI

In questo argomento sono descritti gli argomenti inclusi in Dynamics 365 per le operazioni di vendita e pacchetto del contenuto delle prestazioni di redditività per Microsoft Power BI. Descrive come accedere ai report inclusi nel collo e documentazione vengono fornite informazioni sul modello dati e sulle entità utilizzati per sviluppare un pacchetto di contenuto.

<a name="overview"></a>Panoramica
--------

Il pacchetto di contenuto è stato creato per i controlli vendita vendita e la chiave di vendita dei ricavi, il profitto lordo e i margini di profitto. Usa dati transazionali di vendita da Dynamics 365 per le operazioni e offre sia una visualizzazione aggregata delle cifre delle vendite a livello di società una scomposizione delle prestazioni di vendita per i clienti e i prodotti. Evidenziando modifiche alla crescita di profitto e ricavi nel tempo, i report possono essere utilizzati per avvisare i responsabili sul valore positivo e negativa tende per singoli clienti e prodotti. Categoria e responsabili specifiche troveranno che utile disporre di grafici per la valutazione dei ricavi e della redditività delle categorie e dei clienti di prodotto diverse Gruppi l'una con l'altra per scegliere i ritardatari e i vendita. Un report completo di mapping dei singoli ricavi del cliente da margine di profitto offre al responsabile da un base supportato da dati per adattare le vendite e iniziative di marketing corrispondente al profilo di ciascun cliente. Vendite e il collo del contenuto delle prestazioni di redditività consente di vendita vendita di analizzare le prestazioni di vendita operazioni:

-   Ricavi, inizio anno (in base al gruppo di clienti e singoli clienti, categorie di vendita e singoli prodotti e geografie)
-   Modifica dei ricavi, di annuali ad aree e le categorie di vendita cliente)

La redditività può essere analizzati da:

-   Profitto e margine lordo dei profitti (per i gruppi di clienti e le categorie di vendita di prodotti)
-   Modifica di profitto lordo, di annuali
-   Redditività cliente (a fronte dei ricavi margine lordo)

## <a name="accessing-the-content-pack"></a>Accesso al collo di contenuto
Vendite e il collo del contenuto di potenza delle prestazioni di redditività BI viene emessa quando un cespite all'implementazione del ciclo di vita servizi (LCS) ed è possibile accedere da Dynamics 365 per le operazioni. Per ulteriori informazioni sull'accesso e avviare i report di Power BI, vedere [di Power BI nel contenuto LC da Microsoft e dai partner power-bi-content-microsoft-partners.md] ().

## <a name="metrics-included-in-the-content-pack"></a>In incluso nel collo di contenuto
Il pacchetto di contenuto è incluso un report costituito da un insieme di riepilogare visualizzata come i grafici, le mattonelle e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel collo di contenuto.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| ** Pagina del report **        | **Charts**                                 | ** Affianca **                                               |
| Ricavi dal cliente    | Clienti principale del 10 dei ricavi                | Totale ricavi                                           |
|                        | Ricavi totali in base al gruppo di clienti            | Crescita dei ricavi di YOY                                      |
|                        | Ricavi cliente media dal gruppo di clienti | Margine lordo                                            |
|                        | Ricavi e profitto lordo dal gruppo di clienti   |                                                         |
| Per prodotto ricavi     | Ricavi e profitto lordo per la categoria di vendita   | \# totale di prodotti                                    |
|                        | Prodotti principale del 10 dei ricavi                 | Numero totale di prodotti attivi e percentuale del totale |
|                        | Ricavi totali per la categoria di vendita            | Numero di prodotti che rappresentano i ricavi di 80%           |
| Ricavi per periodo\*    | Ricavi mensili                           | Crescita dei ricavi di YOY                                      |
|                        | Scostamento di trascinamento dei ricavi, YOY             | % Crescita dei ricavi di YOY                                    |
|                        | Scostamento di vendita totale area del cliente    |                                                         |
| Ricavi per ubicazione    | Rendita di vendita in base alla città                      |                                                         |
|                        | % Crescita dei ricavi di YOY                       |                                                         |
|                        | Rendita da vendite area                    |                                                         |
| Redditività cliente | Margine lordo e ricavi, dal cliente   | Profitto lordo, margine lordo, crescita dei ricavi di YOY          |
| Analisi redditività | Ricavi e profitto lordo mensili          |                                                         |
|                        | Clienti principale del 15 per margine lordo           |                                                         |
|                        | Profitto lordo mensili, YOY                 |                                                         |

ricavi\* questi e lo scorso anno e crescita per la categoria di vendita.

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
Dynamics 365 per i dati delle operazioni viene utilizzato per popolare il report in Vendite e nel collo del contenuto delle prestazioni di redditività. Questo è rappresentata come misure aggregate che sono con stato Approntato nella memoria di entità, ovvero un database di Microsoft SQL ricerca per l'analisi dei dati. Legge più in blog [di Integrazione di Power BI al punto vendita dell'entità in Dynamics] (https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Le misure aggregate in questo Service Pack sono contenuti il sottoinsieme delle misurazioni aggregate cui è già disponibili nel cubo di vendita in Dynamics AX 2012 e AX 2012 R3. Per impostare in scenae le misure del cubo aggregate nel punto vendita dell'entità è necessario renderli schierabili. Per ulteriori informazioni, vedere la procedura su come impostare in scenae le misurazioni aggregate nel punto vendita dell'entità in blog [di Integrazione di Power BI al punto vendita dell'entità in Dynamics] (https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Le seguenti misure aggregate chiave di entità delle righe fattura vengono utilizzate come base del collo di contenuto.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entity**    | ** Misurazioni aggregate chiave **               | ** Origine dati per Dynamics 365 per le operazioni ** | **Field**                                    | **Description**                          |
| Righe fattura | Ricavi                                      | CustInvoiceTrans                                | SUM (LineAmountMST)                           | Importo nella valuta di contabilizzazione            |
|               | Costo del venduto                           | InventTrans                                     | SUM CostAmountPosted (+) CostAmountAdjustment | Importo di costo + rettifica                 |
|               | Importo della provvigione in valuta di contabilizzazione | CustInvoiceTrans                                | SUM (CommissAmountMST)                        | Importo della provvigione nella valuta di contabilizzazione |

Nella seguente tabella vengono illustrate le misurazioni aggregate chiave di entità delle righe fattura utilizzate per creare diverse misure calcolate nel set di dati del contenuto del collo.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Measure**       | ** Spese calcolate come **                                                                                |
| Profitto lordo      | SUM ricavi - (COGS - imposta vendite con provvigione (inclusa nell'importo della riga di fattura cliente)          |
| Margine lordo      | SUM (profitto lordo/(ricavi - (VAT inclusa nell'importo della riga di fattura cliente)( report)             |
| Ricavi lo scorso anno | I ricavi lo scorso CALCOLANO = (SUM di ricavi (\]), SAMEPERIODLASTYEAR (data di lines'entity_PLACEHOLDER\]\ [\[di date) |

Nelle dimensioni chiave in ** cubo di vendita ** vengono utilizzate come filtri per affettare le misurazioni aggregate per ottenere una maggiore granularità e le comprensioni analitiche più contrassegnate.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entity**       | ** Esempi di attributi **                           |
| Clienti        | Gruppi di clienti, il cliente, indirizzo, settore |
| Prodotti         | Numero prodotto, nome prodotto, il nome di gruppi di articoli       |
| Categorie di vendita | Nomi di categoria di vendita                                 |
| Persone giuridiche   | Nomi di persona giuridica                                   |
| Appuntamenti            | Appuntamenti                                                |

Per impostazione predefinita, il collo di contenuto visualizzare i dati dell'anno di calendario corrente, ma è possibile aprire la sezione relativa ai filtri report e modificare il filtro dalla data. È inoltre possibile modificare il filtro dalla società.

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](..\data-entities\data-entities.md)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](configure-power-bi-integration.md)



