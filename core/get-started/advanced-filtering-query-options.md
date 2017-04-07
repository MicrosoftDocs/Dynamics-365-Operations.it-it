---
title: Sintassi avanzata di filtro e query
description: Questo articolo descrive le opzioni di filtro e query disponibili quando si utilizza l&quot;operatore &quot;corrisponde a&quot; nella finestra di dialogo Filtro/ordinamento avanzato.
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysQueryForm
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 5ee7a04572e350a7c08d0418bade6d332aa920c6
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-filtering-and-query-syntax"></a>Sintassi avanzata di filtro e query

Questo articolo descrive le opzioni di filtro e query disponibili quando si utilizza l'operatore "corrisponde a" nella finestra di dialogo Filtro/ordinamento avanzato.

<a name="advanced-query-syntax"></a>Sintassi di query avanzate
---------------------

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Sintassi</th>
<th>Descrizione carattere</th>
<th>descrizione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>valore</em></td>
<td>Uguale al valore immesso</td>
<td>Digitare il valore da trovare.</td>
<td><strong>Digitando Rossi</strong> Digitando&quot;Rossi si &quot;troveranno.</td>
</tr>
<tr class="even">
<td>!<em>valore</em> (punto esclamativo)</td>
<td>Non uguale al valore immesso</td>
<td>Digitare un punto esclamativo e poi il valore da escludere.</td>
<td><strong>! Digitando Rossi</strong> rileva tutti i valori tranne Rossi&quot;.</td>
</tr>
<tr class="odd">
<td><em>da valore</em>..<em>a valore</em> (due punti consecutivi)</td>
<td>Compreso tra i due valori separati da due punti consecutivi.</td>
<td>Digitare il valore iniziale, quindi due punti consecutivi e infine il valore finale.</td>
<td><strong>Digitando 1..10</strong> rileva tutti i valori da 1 a 10. Tuttavia, nel campo della stringa, <strong>A.C si troveranno</strong> vengono trovati tutti i valori che iniziano con &quot;A&quot; e &quot;B&quot; e i valori sono pari &quot; esattamente a C&quot;. Ad esempio, la query non &quot;troveranno il CA.&quot; Per trovare tutti i valori &quot;da A*&quot; con &quot;C*&quot;, digitare.</td>
</tr>
<tr class="even">
<td>..<em>valore</em> (due punti consecutivi)</td>
<td>Minore o uguale al valore immesso</td>
<td>Digitare i due punti consecutivi, quindi il valore.</td>
<td><strong>. .1000</strong> si troverà qualsiasi numero che è inferiore o uguale a 1000, ad &quot;&quot; esempio 100, &quot;999.95&quot; e &quot;1,000&quot;.</td>
</tr>
<tr class="odd">
<td><em>valore</em>.. (due punti consecutivi)</td>
<td>Maggiore o uguale al valore immesso</td>
<td>Digitare il valore, quindi i due punti consecutivi.</td>
<td><strong>1000..</strong> si troverà qualsiasi numero maggiore o uguale a 1000, ad &quot;&quot; esempio 1,000, &quot;1,000.01&quot; e &quot;1,000,000&quot;.</td>
</tr>
<tr class="even">
<td>&gt;<em>valore</em> (maggiore del segno)</td>
<td>Maggiore del valore immesso</td>
<td>Immettere un maggiore di apposizione della firma (<strong>&gt;</strong>) e quindi il valore.</td>
<td><strong>&gt;1000</strong> si troverà qualsiasi numero maggiore di 1000, ad &quot; esempio&quot;1000.01, &quot;20,000&quot; e &quot;1,000,000&quot;.</td>
</tr>
<tr class="odd">
<td>&lt;<em>valore</em> (minore di segno)</td>
<td>Minore del valore immesso</td>
<td>Digitare inferiore al segno (<strong>&lt;</strong>) e quindi il valore.</td>
<td><strong>&lt;1000</strong> si troverà qualsiasi numero minore di 1000, ad &quot;&quot; esempio 999.99, &quot;1&quot; e &quot;-200&quot;.</td>
</tr>
<tr class="even">
<td><em>valore</em>* (asterisco)</td>
<td>Inizia con il valore immesso</td>
<td>Digitare il valore iniziale e quindi un asterisco (<strong>*</strong>).</td>
<td><strong>S*</strong> si troverà qualsiasi stringa che inizia con &quot;S&quot;, ad &quot; esempio, &quot;Stoccolma&quot;Sydney&quot; e &quot;San&quot;Francisco.</td>
</tr>
<tr class="odd">
<td>*<em>value</em> (asterisk)</td>
<td>Finisce con il valore immesso</td>
<td>Digitare un asterisco, quindi il valore finale.</td>
<td><strong>*est</strong> si troverà qualsiasi stringa che termina all'&quot; est&quot;, ad &quot; esempio "&quot; Nordest " e &quot;"&quot;.</td>
</tr>
<tr class="even">
<td>*<em>valore</em>* (asterisco)</td>
<td>Contiene il valore immesso</td>
<td>Digitare un asterisco, quindi un valore e infine un altro asterisco.</td>
<td><strong>*th*</strong> si troverà qualsiasi stringa che contiene &quot;il de&quot;, ad &quot; esempio "&quot; Nordest " e &quot;"&quot;.</td>
</tr>
<tr class="odd">
<td>? (punto interrogativo)</td>
<td>Contiene uno o più caratteri sconosciuti.</td>
<td>Digitare un punto interrogativo in corrispondenza della posizione del carattere sconosciuto all'interno del valore.</td>
<td><strong>Digitando R? de</strong> Digitando&quot; Rossi si &quot;troveranno e &quot;Russi&quot;.</td>
</tr>
<tr class="even">
<td><em>valore</em>,<em>valore</em> (virgola)</td>
<td>Corrisponde ai valori separati da virgole</td>
<td>Digitare tutti i criteri e separarli con virgole.</td>
<td><strong>A, D, F, TRA</strong> si &quot;troveranno esattamente si&quot;&quot;troveranno esattamente 10&quot;,&quot;<strong>10, 20, 30, 100</strong> 20&quot;, 30 &quot;, 100 A &quot;, di D, di F e di G&quot;.</td>
</tr>
<tr class="odd">
<td>(<span class="code">Istruzione SQL</span>) (istruzione SQL tra parentesi)</td>
<td>Corrisponde a una query definita.</td>
<td>Digitare una query sotto forma di istruzione SQL racchiusa tra parentesi.</td>
<td><strong><span class="code">(origine dei dati. Fieldname! = &quot;A&quot;)</span></strong></td>
</tr>
<tr class="even">
<td>M</td>
<td>Data odierna</td>
<td>Digitare <strong>M</strong>.</td>
<td><strong>M</strong> corrisponde alla data odierna.</td>
</tr>
<tr class="odd">
<td>(nomeMetodo(parametri)) (metodo <strong>SysQueryRangeUtil</strong> tra parentesi)</td>
<td>Corrispondenza del valore o dell'intervallo di valori specificati dai parametri del metodo <strong>SysQueryRangeUtil</strong></td>
<td>Digitare un metodo <strong>SysQueryRangeUtil</strong> con parametri che specificano il valore o un intervallo di valori.</td>
<td><ol>
<li>Fare <strong>Contabilità clienti</strong> &gt; <strong>Fatture</strong> &gt; <strong>Fatture cliente aperte</strong>clic su.</li>
<li>Premere Ctrl+Maiusc+F3 per aprire la pagina <strong>Richiesta info</strong>.</li>
<li>Nella scheda <strong>Gamma</strong> scegliere <strong>Aggiungi</strong>.</li>
<li>Nel campo <strong>Tabella</strong> selezionare <strong>Transazioni cliente aperte</strong>.</li>
<li>Nel campo <strong>Campo</strong> selezionare <strong>Data di scadenza</strong>.</li>
<li>Nel campo <strong>Criteri</strong> immettere <strong>(yearRange(-2,0))</strong>.</li>
<li>Scegliere <strong>OK</strong>. La pagina verrà aggiornata per elencare le fatture che soddisfano i criteri immessi. Per questo esempio specifico, vengono elencate le fatture incluse in scadenza nei due anni precedenti.</li>
</ol>
Vedere la tabella nella sezione successiva per ulteriori dettagli sui metodi di data <strong>SysQueryRangeUtil</strong> e vari esempi.</td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a>Query di data avanzate che utilizzano metodi SysQueryRangeUtil
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metodo</th>
<th>Descrizione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Day (_relativeDays=0)</td>
<td>Trova una data in relazione alla data della sessione. I valori positivi indicano date future e i valori negativi indicano date passate.</td>
<td><ul>
<li><strong>Domani</strong> – immettere <strong>(Day(1))</strong>.</li>
<li><strong>Oggi</strong> – immettere <strong>(Day(0))</strong>.</li>
<li><strong>Ieri</strong> – Immettere <strong>(Day(-1))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>Trova un intervallo di date in relazione alla data della sessione. I valori positivi indicano date future e i valori negativi indicano date passate.</td>
<td><ul>
<li><strong>Ultimi 30 giorni</strong> – Immettere <strong>(DayRange(-30,0))</strong>.</li>
<li><strong>30 giorni precedenti e 30 giorni successivi</strong> – Immettere <strong>(DayRange(-30,30))</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>Trova tutte le date dopo la data relativa specificata.</td>
<td><ul>
<li><strong>Più di 30 giorni dalla data odierna</strong> - Immettere <strong>(GreaterThanDate(30))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>GreaterThanUtcNow ()</td>
<td>Trova tutte le voci data/ora dopo l'ora corrente.</td>
<td><ul>
<li><strong>Qualsiasi data/ora futura</strong> - Immettere <strong>(GreaterThanUtcNow())</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>Trova tutte le date precedenti alla data relativa specificata.</td>
<td><ul>
<li><strong>Meno di sette giorni dalla data odierna</strong> - Immettere <strong>(LessThanDate(7))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>LessThanUtcNow ()</td>
<td>Trova tutte le voci data/ora prima dell'ora corrente.</td>
<td><ul>
<li><strong>Tutte le date/ore passate</strong> - Immettere <strong>(LessThanUtcNow())</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Trova un intervallo di date, in base ai mesi rispetto al mese corrente.</td>
<td><ul>
<li><strong>Due mesi precedenti</strong> - Immettere <strong>(MonthRange(- 2,0))</strong>.</li>
<li><strong>Tre mesi successivi</strong> - Immettere <strong>(MonthRange(0,3))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Trova un intervallo di date, in base agli anni rispetto all'anno corrente.</td>
<td><ul>
<li><strong>Anno successivo</strong> - Immettere <strong>(YearRange(0, 1))</strong>.</li>
<li><strong>Anno precedente</strong> - Immettere <strong>(YearRange(-1,0))</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>




