---
title: Contenuto Power BI sull&quot;analisi delle spese di acquisto
description: "In questo argomento viene descritto cosa è incluso nel pacchetto di contenuti sull&quot;analisi delle spese di acquisto per Microsoft Power BI. Viene descritto come accedere ai report inclusi nel pacchetto di contenuti e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il pacchetto di contenuti."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d392b88942f4b7d7365b000df1cd69809060b910
ms.openlocfilehash: e39b1677038037cd91cfad8d104d0130bc20fb9b
ms.contentlocale: it-it
ms.lasthandoff: 04/26/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Contenuto Power BI sull'analisi delle spese di acquisto

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto cosa è incluso nel pacchetto di contenuti sull'analisi delle spese di acquisto per Microsoft Power BI. Viene descritto come accedere ai report inclusi nel pacchetto di contenuti e vengono fornite informazioni sul modello dati e sulle entità utilizzati per creare il pacchetto di contenuti.

<a name="overview"></a>Panoramica
--------

Il pacchetto di contenuti sull'analisi delle spese di acquisto per Microsoft Power BI è stato creato per i responsabili degli acquisti e dei budget. È progettato per aiutare tali responsabili a controllare la spesa di acquisto. Usa dati transazionali di acquisto provenienti da Microsoft Dynamics 365 for Operations e offre sia una visualizzazione aggregata delle cifre di acquisto a livello di società che una scomposizione dettagliata della spesa di acquisto per fornitore e prodotto. I report evidenziano le modifiche nella spesa di acquisto nel tempo. Di conseguenza, è possibile utilizzarli per avvisare i responsabili sulle tendenze positive e negative di spesa per singoli fornitori e prodotti. I grafici mostrano la spesa di acquisto per categorie di approvvigionamento e gruppi di fornitori diversi. I responsabili di categoria e regionali possono trovare utile avvalersi di questi grafici per identificare i cambiamenti nel comportamento di spesa. Il pacchetto di contenuti consente ai responsabili degli acquisti e dei budget di analizzare la spesa di acquisto nei seguenti modi:

-   Acquisto da inizio anno (per gruppo di fornitori e singoli fornitori, per categoria di approvvigionamento e singoli prodotti e per ubicazione del fornitore)
-   Modifica di acquisto da inizio anno (per gruppo di fornitori e categoria di approvvigionamento)

## <a name="accessing-the-content-pack"></a>Accesso al pacchetto di contenuti
Il pacchetto di contenuti sull'analisi delle spese di acquisto viene pubblicato come risorsa di implementazione in Microsoft Dynamics Lifecycle Services (LCS) ed è possibile accedervi da Microsoft Dynamics 365 for Operations. Per ulteriori informazioni su come accedere ai report Power BI e aprirli, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](power-bi-content-microsoft-partners.md).
Nota: l'articolo KB 4011327 è un prerequisito per questo contenuto Power BI. Dopo avere eseguito l'accesso a Lifecycle Services, è possibile accedere alla KB qui: : https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="metrics-that-are-included-in-the-content-pack"></a>Metriche incluse nel pacchetto di contenuti
Il pacchetto di contenuti sull'analisi delle spese di acquisto include un report costituito da un set di metriche. Queste metriche vengono visualizzate come grafici, riquadri e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel pacchetto di contenuti.

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
I dati di Dynamics 365 for Operations vengono utilizzati per il report nel pacchetto di contenuti sull'analisi delle spese di acquisto. Questi dati sono rappresentati come misure aggregate che vengono collocate nell'archivio entità, ovvero un database di Microsoft SQL ottimizzato per l'analisi. Per ulteriori informazioni sull'Archivio entità, vedere il post di blog [Integrazione di Power BI con l'Archivio entità in Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Le misure di aggregazione in questo pacchetto di contenuti sono il sottoinsieme delle misure di aggregazione disponibili nel cubo Acquisti in Microsoft Dynamics AX 2012 e Microsoft Dynamics AX 2012 R3. Per rappresentare le misure di aggregazione del cubo nell'Archivio entità, è necessario renderle distribuibili. Per ulteriori informazioni, vedere la procedura per la rappresentazione delle misure di aggregazione nell'Archivio entità nel post di blog [Integrazione di Power BI con l'Archivio entità in Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Le seguenti misure di aggregazione chiave sono disponibili direttamente dall'entità delle righe della fattura e sono utilizzate come base del pacchetto di contenuti.

| Entità        | Misure di aggregazione chiave | Origine dati per Dynamics 365 for Operations | Campo              | descrizione                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Righe fattura | Acquisti                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Importo nella valuta di contabilizzazione |

Nella seguente tabella vengono illustrate le misurazioni chiave calcolate nel pacchetto di contenuti dall'entità delle righe della fattura.

| Unità di misura               | Calcolo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Acquisti nell'anno corrente | Acquisto nell'anno corrente = SUM('Righe fattura'\[Acquisti\])                                            |
| Acquisti nell'anno passato    | Acquisti nell'anno passato = CALCULATE(SUM('Righe fattura'\[Acquisti\]), SAMEPERIODLASTYEAR(Dates\[Data\])) |
| Crescita degli acquisti su base annua   | Crescita degli acquisti su base annua = \[Acquisti nell'anno corrente\] - \[Acquisti nell'anno passato\]                            |

Le seguenti dimensioni chiave nel pacchetto di contenuti vengono utilizzate come filtri per dividere le misure di aggregazione in modo da poter ottenere una maggiore granularità e fornire informazioni analitiche più approfondite.

| Entità                 | Esempi di attributi                                |
|------------------------|-------------------------------------------------------|
| Fornitori                | Gruppi di fornitori, paese o regioni del fornitore, nome del fornitore |
| Prodotti               | Numero prodotto, nome prodotto, nome dei gruppi di articoli        |
| Categorie di approvvigionamento | Categoria di approvvigionamento, nomi delle categorie di approvvigionamento      |
| Persone giuridiche         | Nome persona giuridica                                     |
| Appuntamenti                  | Date, offset anno                                    |

Per impostazione predefinita, il pacchetto di contenuti mostra i dati dell'anno di calendario corrente. Tuttavia, è possibile modificare il filtro della data nella sezione relativa ai filtri di report. È inoltre possibile modificare il filtro della società.

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](..\data-entities\data-entities.md)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](configure-power-bi-integration.md)





