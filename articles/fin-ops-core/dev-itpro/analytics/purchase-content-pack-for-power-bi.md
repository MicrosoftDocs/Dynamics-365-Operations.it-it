---
title: Contenuto Analisi delle spese di acquisto di Power BI
description: In questo articolo viene descritto cosa è incluso nel contenuto Analisi delle spese di acquisto di Power BI.
author: FrankDahl
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.form: PurchaseSpendAnalysisPowerBI
ms.openlocfilehash: 757b782131617104422e15f3ceec747b92d96666
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276662"
---
# <a name="purchase-spend-analysis-power-bi-content"></a>Contenuto Analisi delle spese di acquisto di Power BI

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto cosa è incluso nel contenuto **Analisi delle spese di acquisto** di Microsoft Power BI. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI **Analisi delle spese di acquisto** è stato progettato per consentire ai responsabili acquisti e ai dirigenti responsabili di budget di tenere sotto controllo la spesa di acquisto. I responsabili possono analizzare la spesa d'acquisto nei seguenti modi:

- Acquisto da inizio anno (per gruppo di fornitori e singoli fornitori, per categoria di approvvigionamento e singoli prodotti e per ubicazione del fornitore)
- Modifica di acquisto da inizio anno (per gruppo di fornitori e categoria di approvvigionamento)

Il contenuto utilizza dati transazionali di acquisto e offre sia una visualizzazione aggregata delle cifre di acquisto a livello di società che una scomposizione dettagliata della spesa di acquisto per fornitore e prodotto. I report evidenziano le modifiche nella spesa di acquisto nel tempo. Di conseguenza, è possibile utilizzarli per avvisare i responsabili sulle tendenze positive e negative di spesa per singoli fornitori e prodotti. Inoltre, i grafici mostrano la spesa di acquisto per categorie di approvvigionamento e gruppi di fornitori diversi. Pertanto, i responsabili di categoria e regionali possono usare questi grafici per identificare i cambiamenti nel comportamento di spesa.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Il contenuto di Power BI **Analisi delle spese di acquisto** viene mostrato nella pagina **Analisi di spesa e acquisto** (**Approvvigionamento** \> **Richieste di informazioni e report** \> **Analisi delle prestazioni di acquisto** \> **Analisi delle prestazioni di acquisto**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Metriche incluse nel contenuto Power BI
Il contenuto di Power BI **Analisi delle spese di acquisto** include un report costituito da un set di metriche. Queste metriche vengono visualizzate come grafici, riquadri e tabelle. 

Nelle seguenti sezioni viene fornita una panoramica delle visualizzazioni.

### <a name="purchase-by-vendor-report-page"></a>Pagina del report sugli acquisti per fornitore
**Grafici**
- Primi 10 fornitori per acquisti (grafico a barre impilate)
- Acquisti totali per gruppo di fornitori/paese/nome (grafico a torta)
- Acquisti per gruppo di fornitori/paese/nome (istogramma)
- Media degli acquisti per gruppo di fornitori/paese/nome (istogramma)

**Riquadri**
- Totale acquisto
- Crescita degli acquisti su base annua
- N. totale fornitori
- N. totale dei fornitori attivi

**Esempio**
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a>Pagina del report sugli acquisti per prodotto

**Grafici**
- Acquisti per categoria di approvvigionamento/nome prodotto (istogramma)
- Acquisti totali per categoria di approvvigionamento/nome prodotto (grafico a torta)
- Primi 10 prodotti per acquisti (grafico a barre impilate)

**Riquadri**
- N. totale di prodotti</li>
- Percentuale di prodotti attivi totali del numero totale di prodotti
- Numero di prodotti che rappresentano l'80% degli acquisti

**Esempio**


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a>Pagina del report sugli acquisti per periodo
Questa pagina nostra gli acquisti nell'anno corrente e nell'anno passato e crescita per categoria di approvvigionamento.

**Grafici** 
- Acquisti al mese/giorno (istogramma)
- Scostamento di acquisti cumulativi su base annua (grafico a cascata)
- Crescita degli acquisti totali su base annua (istogramma)
- Rendiconto di approvvigionamento (matrice)

**Riquadri**
- Crescita degli acquisti su base annua
- % di crescita degli acquisti su base annua

**Esempio**
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a>Pagina del report sugli acquisti per ubicazione del fornitore

**Grafici**
- Acquisti per città
- % di crescita su base annua degli acquisti
- Acquisti per paese

**Esempio**
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a>Pagina del report sull'analisi delle spese di acquisto in base all'ora

**Grafici** 
- Acquisti nell'anno corrente al mese/giorno (grafico a linee)
- Acquisti nell'anno corrente e nell'anno passato (grafico a linee e colonne)

**Esempio**
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a>Pagina del report sull'analisi delle spese di acquisto in base fornitore

**Grafici** 
- % di acquisti dei primi 10 fornitori (grafico a imbuto)
- Primi 10 fornitori con aumento delle spese su base annua
- Primi 10 fornitori con diminuzione delle spese su base annua

**Esempio** 
<img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a>Modello dati ed entità
I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Analisi delle spese di acquisto**. Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità. L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati. Per ulteriori informazioni, vedere [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).

Le misure di aggregazione in questo pacchetto di contenuti sono il sottoinsieme delle misure di aggregazione disponibili nel cubo Acquisiti in Microsoft Dynamics AX 2012 e Microsoft Dynamics AX 2012 R3. Per rappresentare le misure di aggregazione del cubo nell'Archivio entità, è necessario renderle distribuibili. Per ulteriori informazioni, vedere la procedura per la rappresentazione delle misure di aggregazione nell'Archivio entità in [Integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md). Le seguenti misure di aggregazione chiave sono disponibili direttamente dall'entità delle righe della fattura e sono utilizzate come base del contenuto.

| Entità        | Misure di aggregazione chiave | Origine dati                                 | Campo              | Descrizione                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| Righe fattura | Acquisti                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Importo nella valuta di contabilizzazione. |

Nella seguente tabella vengono illustrate le misurazioni chiave nel contenuto calcolate dall'entità delle righe della fattura.

| Unità di misura               | Calcolo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Acquisti nell'anno corrente | Acquisto nell'anno corrente = SUM('Righe fattura'\[Acquisti\])                                            |
| Acquisti nell'anno passato    | Acquisti nell'anno passato = CALCULATE(SUM('Righe fattura'\[Acquisti\]), SAMEPERIODLASTYEAR(Dates\[Data\])) |
| Crescita degli acquisti su base annua   | Crescita degli acquisti su base annua = \[Acquisti nell'anno corrente\] - \[Acquisti nell'anno passato\]                            |

Le seguenti dimensioni chiave nel contenuto vengono utilizzate come filtri per dividere le misure di aggregazione in modo da poter ottenere una maggiore granularità e fornire informazioni analitiche più approfondite.

| Entità                 | Esempi di attributi                                |
|------------------------|-------------------------------------------------------|
| Fornitori                | Gruppi di fornitori, paese o regioni del fornitore, nome del fornitore |
| Prodotti               | Numero prodotto, nome prodotto, nome dei gruppi di articoli        |
| Categorie di approvvigionamento | Categoria di approvvigionamento, nomi delle categorie di approvvigionamento      |
| Persone giuridiche         | Nome persona giuridica                                     |
| Appuntamenti                  | Date, offset anno                                    |

Per impostazione predefinita, il contenuto mostra i dati dell'anno di calendario corrente. Tuttavia, è possibile modificare il filtro della data nella sezione relativa ai filtri di report. È inoltre possibile modificare il filtro della società.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
