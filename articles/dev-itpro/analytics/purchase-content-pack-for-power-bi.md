---
title: Contenuto Power BI sull'analisi delle spese di acquisto
description: "In questo argomento viene descritto cosa è incluso nel contenuto di Power BI per l'analisi delle spese di acquisto. Viene descritto come accedere ai report inclusi nel contenuto e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il contenuto."
author: FrankDahl
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: aac6439bb54b3b9cab066b06c01763e880efef8e
ms.openlocfilehash: 07b6f433a8355d7f9ed6dce8e26f78d38a86a713
ms.contentlocale: it-it
ms.lasthandoff: 12/18/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a>Contenuto Power BI sull'analisi delle spese di acquisto

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto cosa è incluso nel contenuto di Microsoft Power BI **Analisi delle spese di acquisto**. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI **Analisi delle spese di acquisto** è stato progettato per consentire ai responsabili acquisti e i dirigenti responsabili di budget di tenere sotto controllo la spesa di acquisto. I responsabili possono analizzare la spesa d'acquisto nei seguenti modi:

-   Acquisto da inizio anno (per gruppo di fornitori e singoli fornitori, per categoria di approvvigionamento e singoli prodotti e per ubicazione del fornitore)
-   Modifica di acquisto da inizio anno (per gruppo di fornitori e categoria di approvvigionamento)

Il contenuto utilizza dati transazionali di acquisto e offre sia una visualizzazione aggregata delle cifre di acquisto a livello di società che una scomposizione dettagliata della spesa di acquisto per fornitore e prodotto. I report evidenziano le modifiche nella spesa di acquisto nel tempo. Di conseguenza, è possibile utilizzarli per avvisare i responsabili sulle tendenze positive e negative di spesa per singoli fornitori e prodotti. Inoltre, i grafici mostrano la spesa di acquisto per categorie di approvvigionamento e gruppi di fornitori diversi. Pertanto, i responsabili di categoria e regionali possono usare questi grafici per identificare i cambiamenti nel comportamento di spesa.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Il contenuto di Power BI **Analisi delle spese di acquisto** viene visualizzato nella pagina **Analisi delle spese di acquisto** (**Approvvigionamento** > **Richieste di informazioni e report** > **Analisi delle prestazioni di acquisto** > **Analisi di spesa e acquisto**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Metriche incluse nel contenuto Power BI
Il contenuto di Power BI **Analisi delle spese di acquisto** include un report costituito da un set di metriche. Queste metriche vengono visualizzate come grafici, riquadri e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Pagina di report</th>
<th>Grafici</th>
<th>Riquadri</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Acquisti per fornitore</td>
<td><ul>
<li>Primi 10 fornitori per acquisti (grafico a barre impilate)</li>
<li>Acquisti totali per gruppo di fornitori/paese/nome (grafico a torta)</li>
<li>Acquisti per gruppo di fornitori/paese/nome (istogramma)</li>
<li>Media degli acquisti per gruppo di fornitori/paese/nome (istogramma)</li>
</ul></td>
<td><ul>
<li>Totale acquisto</li>
<li>Crescita degli acquisti su base annua</li>
<li>N. totale fornitori</li>
<li>N. totale dei fornitori attivi</li>
</ul></td>
</tr>
<tr class="even">
<td>Acquisti per prodotto</td>
<td><ul>
<li>Acquisti per categoria di approvvigionamento/nome prodotto (istogramma)</li>
<li>Acquisti totali per categoria di approvvigionamento/nome prodotto (grafico a torta)</li>
<li>Primi 10 prodotti per acquisti (grafico a barre impilate)</li>
</ul></td>
<td><ul>
<li>N. totale di prodotti</li>
<li>Percentuale di prodotti attivi totali del numero totale di prodotti</li>
<li>Numero di prodotti che rappresentano l'80% degli acquisti</li>
</ul></td>
</tr>
<tr class="odd">
<td>Acquisti per periodo*</td>
<td><ul>
<li>Acquisti al mese/giorno (istogramma)</li>
<li>Scostamento di acquisti cumulativi su base annua (grafico a cascata)</li>
<li>Crescita degli acquisti totali su base annua (istogramma)</li>
<li>Rendiconto di approvvigionamento (matrice)</li>
</ul></td>
<td><ul>
<li>Crescita degli acquisti su base annua</li>
<li>% di crescita degli acquisti su base annua</li>
</ul></td>
</tr>
<tr class="even">
<td>Acquisti per ubicazione del fornitore</td>
<td><ul>
<li>Acquisti per città</li>
<li>% di crescita su base annua degli acquisti</li>
<li>Acquisti per paese</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Analisi delle spese di acquisto in base all'ora</td>
<td><ul>
<li>Acquisti nell'anno corrente al mese/giorno (grafico a linee)</li>
<li>Acquisti nell'anno corrente e nell'anno passato (grafico a linee e colonne)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Analisi delle spese di acquisto per fornitore</td>
<td><ul>
<li>% di acquisti dei primi 10 fornitori (grafico a imbuto)</li>
<li>Primi 10 fornitori con aumento delle spese su base annua</li>
<li>Primi 10 fornitori con diminuzione delle spese su base annua</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\* Acquisti nell'anno corrente e nell'anno passato e crescita per categoria di approvvigionamento

## <a name="data-model-and-entities"></a>Modello dati ed entità
I seguenti dati vengono utilizzati per compilare le pagine di report nel contenuto Power BI **Analisi delle spese di acquisto**. Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità. L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati. Per ulteriori informazioni, vedere [Panoramica dell'integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md).

Le misure di aggregazione in questo contenuto sono il sottoinsieme delle misure di aggregazione disponibili nel cubo Acquisti in Microsoft Dynamics AX 2012 e Microsoft Dynamics AX 2012 R3. Per rappresentare le misure di aggregazione del cubo nell'Archivio entità, è necessario renderle distribuibili. Per ulteriori informazioni, vedere la procedura per la rappresentazione delle misure di aggregazione nell'Archivio entità in [Panoramica dell'integrazione di Power BI con l'archivio entità](power-bi-integration-entity-store.md). Le seguenti misure di aggregazione chiave sono disponibili direttamente dall'entità delle righe della fattura e sono utilizzate come base del contenuto.

| Entità        | Misure di aggregazione chiave | Origine dati                                 | Campo              | descrizione                            |
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

