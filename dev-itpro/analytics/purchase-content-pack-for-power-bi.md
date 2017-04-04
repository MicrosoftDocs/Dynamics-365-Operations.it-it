---
title: Inserisci acquisto spese di analisi di contenuto Power BI
description: "In questo argomento sono descritti gli argomenti inclusi nel collo del contenuto di analisi spese di acquisto relativa potenza di Microsoft BI. Descrive come accedere ai report inclusi nel collo e documentazione vengono fornite informazioni sul modello dati e sulle entità utilizzati per sviluppare un pacchetto di contenuto."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-12-30 09 - 40 - 51
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 8cb928cbf1316e63a8c7de833587168cd36a455c
ms.lasthandoff: 03/29/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Inserisci acquisto spese di analisi di contenuto Power BI

In questo argomento sono descritti gli argomenti inclusi nel collo del contenuto di analisi spese di acquisto relativa potenza di Microsoft BI. Descrive come accedere ai report inclusi nel collo e documentazione vengono fornite informazioni sul modello dati e sulle entità utilizzati per sviluppare un pacchetto di contenuto.

<a name="overview"></a>Panoramica
--------

Il pacchetto del contenuto di analisi spese di acquisto relativa potenza di Microsoft BI è stato creato per i responsabili acquisti e i dirigenti responsabili di budget. Pianificato per aiutarli per gestire un occhio alla spesa di acquisto. Usa dati transazionali di acquisto da Microsoft Dynamics 365 per le operazioni e offre sia una visualizzazione aggregata di cifre livello di acquisto che il totale della spesa di acquisto dal fornitore e prodotto. Modifiche dei culminante dei report nell'acquisto di spesa nel tempo. Di conseguenza, è possibile utilizzare per avvisare i responsabili sulle tendenze positive e negative di spesa per singoli fornitori e prodotti. I grafici mostrano l'importo dell'acquisto per le categorie di approvvigionamento e i diversi gruppi di fornitori. Categoria e responsabili specifiche possono essere utile avvalersi utilizzare i grafici che consentono di identificare le modifiche al comportamento di spesa. Il pacchetto del contenuto dei responsabili acquisti e i dirigenti responsabili di budget analizzano la spesa di acquisto nei seguenti modi:

-   acquisto da inizio anno fino data (per gruppo di fornitori e singoli fornitori, categoria di approvvigionamento e i prodotti e percorso del fornitore)
-   Modifica di annuali di acquisto (per il gruppo e la categoria di approvvigionamento fornitori)

## <a name="accessing-the-content-pack"></a>Accesso al collo di contenuto
Il pacchetto del contenuto di analisi spese di acquisto viene rilasciato come cespite all'implementazione del ciclo di vita di Microsoft Dynamics fornisce assistenza (LCS) ed è possibile accedere da Microsoft Dynamics 365 per le operazioni. Per ulteriori informazioni sull'accesso a e i report aperti di Power BI, vedere [di Power BI nel contenuto LC da Microsoft e dai partner power-bi-content-microsoft-partners.md] ().

## <a name="metrics-that-are-included-in-the-content-pack"></a>In inclusa pacchetto di contenuto
Il pacchetto del contenuto di analisi spese di acquisto è incluso un report costituito da un insieme di stato. Questa e viene visualizzata come i grafici, le mattonelle e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel collo di contenuto.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Pagina del report</th>
<th>Grafici</th>
<th>Tiles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Acquisto dal fornitore</td>
<td><ul>
<li>Fornitori di principale 10 dall'acquisto (grafico a barre impilato)</li>
<li>Acquisti totale dal gruppo/paese nome (grafico a torta) fornitore</li>
<li>Acquisti per gruppo/paese nome (grafico del fornitore di colonna)</li>
<li>Acquisti medio per gruppo/paese nome (grafico del fornitore di colonna)</li>
</ul></td>
<td><ul>
<li>Totale acquisto</li>
<li>Crescita di acquisto di YOY</li>
<li>Totale # fornitori</li>
<li>Totale # dei fornitori attivi</li>
</ul></td>
</tr>
<tr class="even">
<td>Per prodotto di acquisto</td>
<td><ul>
<li>Acquisto dalla categoria di approvvigionamento/nome prodotto (istogramma)</li>
<li>Acquisti totale dalla categoria di approvvigionamento/nome prodotto (grafico a torta)</li>
<li>Prodotti principale del 10 dall'acquisto (grafico a barre impilato)</li>
</ul></td>
<td><ul>
<li>Totale # dei prodotti</li>
<li>Percentuale attiva totale di prodotti del numero totale di prodotti</li>
<li>Numero di prodotti che rappresentano un acquisto di 80%</li>
</ul></td>
</tr>
<tr class="odd">
<td>Acquisto da period*</td>
<td><ul>
<li>Acquisti mensili/giorno (istogramma)</li>
<li>Scostamento cumulativo di acquisto YOY (grafico a cascata)</li>
<li>Crescita acquisti totale YOY (istogramma)</li>
<li>Rendiconto di approvvigionamento (matrice)</li>
</ul></td>
<td><ul>
<li>Crescita di acquisto di YOY</li>
<li>% Crescita di acquisto di YOY</li>
</ul></td>
</tr>
<tr class="even">
<td>Acquisti per ubicazione fornitore</td>
<td><ul>
<li>Acquisti la città</li>
<li>% Crescita di acquisto YOY</li>
<li>Acquisti per paese</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Analisi di spesa di acquisto in base all'ora</td>
<td><ul>
<li>Anno di acquisto corrente in base al mese/giorno (grafico a linee)</li>
<li>Corrente di acquisto e lo scorso anno (grafico riga e di colonna)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Analisi di spesa di acquisto dal fornitore</td>
<td><ul>
<li>Acquisti % del fornitore principale 10 - Fornitori (imbuto)</li>
<li>Fornitori di principale 10 con YOY di spesa aumentato</li>
<li>Fornitori di principale 10 con YOY di spesa di riduzione</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

acquisto\* questo anno e lo scorso anno e crescita per la categoria di approvvigionamento

## <a name="data-model-and-entities"></a>Modello dati e entità
Dynamics 365 per i dati delle operazioni viene utilizzato per il report nel collo del contenuto di analisi spese di acquisto. Questi dati sono rappresentate come misure aggregate che sono con stato Approntato nella memoria di entità, ovvero un database di Microsoft SQL che viene ricerca per l'analisi dei dati. Per ulteriori informazioni sul record di entità, vedere [di Integrazione di Power BI al punto vendita dell'entità in Dynamics] (blog di registrazione dell'indirizzo https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Le misure aggregate in questo Service Pack sono contenuti il sottoinsieme delle misurazioni aggregate cui è già disponibili nel cubo di acquisto in Microsoft Dynamics AX 2012 e Microsoft Dynamics 365 per le operazioni 2012 R3. Per impostare in scenae le misure del cubo aggregate nella memoria di entità, è necessario renderli schierabili. Per ulteriori informazioni, vedere la procedura per impostare in scenae le misurazioni aggregate nel punto vendita dell'entità nel campo [di Integrazione di Power BI al punto vendita dell'entità in Dynamics] (blog di registrazione dell'indirizzo https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Le seguenti misure aggregate chiave sono disponibili direttamente dalle righe entità fatture e utilizzate come base del collo di contenuto.

| Entità        | Key aggregate measurements | Origine dati per Dynamics 365 per le operazioni | Campo              | descrizione                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Righe fattura | Acquisti                   | VendInvoiceTrans                            | SUM (LineAmountMST) | Importo nella valuta di contabilizzazione |

Nella seguente tabella vengono illustrate le misurazioni chiave calcolate nel collo di contenuto dall'entità delle righe fattura.

| Unità di misura               | Calcolo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Anno di acquisto corrente | Anno di acquisto corrente SUM = ('acquisto di\]lines'entity_PLACEHOLDER [\ fatture)                                            |
| Acquisti lo scorso anno    | L'acquisto lo scorso CALCOLA = (SUM di acquisto (\]), SAMEPERIODLASTYEAR (data di lines'entity_PLACEHOLDER\]\ [\[di date) |
| Crescita di acquisto di YOY   | Crescita di acquisto di YOY =\] anno corrente \[acquisto \[- acquisto lo scorso\]\[                            |

Nelle dimensioni del collo documentazione vengono utilizzate come filtri per affettare le misurazioni aggregate, in modo che sia possibile ottenere ulteriori granularità e comprensioni analitiche più contrassegnate.

| Entità                 | Esempi di attributi                                |
|------------------------|-------------------------------------------------------|
| Fornitori                | Gruppi di fornitori, paese del fornitore o le regioni, nome del fornitore |
| Prodotti               | Numero prodotto, nome prodotto, il nome di gruppi di articoli        |
| Categorie di approvvigionamento | Categoria di approvvigionamento, nomi di categoria di approvvigionamento      |
| Persone giuridiche         | Nome persona giuridica                                     |
| Appuntamenti                  | Date, contropartita di anno                                    |

Per impostazione predefinita, il collo documentazione indicati i dati dell'anno di calendario corrente. Tuttavia, è possibile modificare il filtro per date nella sezione relativa ai filtri report. È inoltre possibile modificare il filtro dalla società.

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](..\data-entities\data-entities.md)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](configure-power-bi-integration.md)



