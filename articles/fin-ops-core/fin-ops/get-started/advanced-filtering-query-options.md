---
title: Sintassi di query e filtro avanzata
description: Questo argomento descrive le opzioni di filtro e query disponibili quando si utilizza la finestra di dialogo Filtro/ordinamento avanzato o l'operatore corrisponde a nel riquadro Filtro o nei filtri di intestazione di colonna.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15805e24c46603afd34d40c5f94c1422b01cab4c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566068"
---
# <a name="advanced-filtering-and-query-syntax"></a>Sintassi di query e filtro avanzata

[!include [banner](../includes/banner.md)]

Questo argomento descrive le opzioni di filtro e query disponibili quando si utilizza la finestra di dialogo Filtro/ordinamento avanzato o l'operatore **corrisponde** a nel riquadro Filtro o nei filtri di intestazione di colonna.

## <a name="advanced-query-syntax"></a>Sintassi di query avanzata

<table>
<thead>
<tr>
<th>Sintassi</th>
<th>Descrizione carattere</th>
<th>Descrizione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr>
<td><em>valore</em></td>
<td>Uguale al valore immesso</td>
<td>Digitare il valore da trovare.</td>
<td>Digitando <strong>Rossi</strong> si troverà &quot;Rossi&quot;.</td>
</tr>
<tr>
<td>!<em>valore</em> (punto esclamativo)</td>
<td>Non uguale al valore immesso</td>
<td>Digitare un punto esclamativo e poi il valore da escludere.</td>
<td>Digitando <strong>!Rossi</strong> si troveranno tutti i valori tranne &quot;Rossi&quot;.</td>
</tr>
<tr>
<td><em>da valore</em>..<em>a valore</em> (due punti consecutivi)</td>
<td>Compreso tra i due valori separati da due punti consecutivi.</td>
<td>Digitare il valore iniziale, quindi due punti consecutivi e infine il valore finale.</td>
<td>Digitando <strong>1..10</strong> si troveranno tutti i valori da 1 a 10. In un campo stringa, tuttavia, digitando <strong>A..C</strong> si troveranno tutti i valori che iniziano con &quot;A&quot; e &quot;B&quot; e i valori che corrispondono esattamente a &quot;C&quot;. Ad esempio, questa query non troverà &quot;Ca&quot;. Per trovare tutti i valori da &quot;A<em>&quot; a &quot;C</em>&quot;, digitare <strong>A..D</strong>.</td>
</tr>
<tr>
<td>..<em>valore</em> (due punti consecutivi)</td>
<td>Minore o uguale al valore immesso</td>
<td>Digitare i due punti consecutivi, quindi il valore.</td>
<td>Digitando <strong>..1000</strong> si troverà qualsiasi numero minore o uguale a 1000, ad esempio &quot;100&quot;, &quot;999,95&quot; e &quot;1.000&quot;.</td>
</tr>
<tr>
<td><em>valore</em>.. (due punti consecutivi)</td>
<td>Maggiore o uguale al valore immesso</td>
<td>Digitare il valore, quindi i due punti consecutivi.</td>
<td><strong>1000..</strong> troverà qualsiasi numero maggiore o uguale a 1000, ad esempio &quot;1.000&quot;, &quot;1.000,01&quot; e &quot;1.000.000&quot;.</td>
</tr>
<tr>
<td>&gt;<em>valore</em> (segno di maggiore)</td>
<td>Maggiore del valore immesso</td>
<td>Digitare un segno di maggiore(<strong>&gt;</strong>), quindi il valore.</td>
<td>Digitando <strong>&gt;1000</strong> si troverà qualsiasi numero maggiore di 1000, ad esempio &quot;1000,01&quot;, &quot;20.000&quot; e &quot;1.000.000&quot;.</td>
</tr>
<tr>
<td>&lt;<em>valore</em> (segno di minore)</td>
<td>Minore del valore immesso</td>
<td>Digitare un segno di minore (<strong>&lt;</strong>), quindi il valore.</td>
<td>Digitando <strong>&lt;1000</strong> si troverà qualsiasi numero minore di 1000, ad esempio &quot;999,99&quot;, &quot;1&quot; e &quot;-200&quot;.</td>
</tr>
<tr>
<td><em>valore</em>* (asterisco)</td>
<td>Inizia con il valore immesso</td>
<td>Digitare il valore iniziale, quindi un asterisco (<strong>*</strong>).</td>
<td>Digitando <strong>S*</strong> si troverà qualsiasi stringa che inizia con &quot;S&quot;, ad esempio &quot;Stoccolma&quot;, &quot;Sydney&quot; e &quot;San Francisco&quot;.</td>
</tr>
<tr>
<td>*<em>valore</em> (asterisco)</td>
<td>Finisce con il valore immesso</td>
<td>Digitare un asterisco, quindi il valore finale.</td>
<td>Digitando <strong>*est</strong> si troverà qualsiasi stringa che finisce con &quot;est&quot;, ad esempio &quot;Nordest&quot; e &quot;Sudest&quot;.</td>
</tr>
<tr>
<td>*<em>valore</em>* (asterisco)</td>
<td>Contiene il valore immesso</td>
<td>Digitare un asterisco, quindi un valore e infine un altro asterisco.</td>
<td>Digitando <strong>*de*</strong> si troverà qualsiasi stringa che contiene &quot;de&quot;, ad esempio &quot;Nordest&quot; e &quot;Sudest&quot;.</td>
</tr>
<tr>
<td>? (punto interrogativo)</td>
<td>Contiene uno o più caratteri sconosciuti.</td>
<td>Digitare un punto interrogativo in corrispondenza della posizione del carattere sconosciuto all'interno del valore.</td>
<td>Digitando <strong> R?ssi</strong> si troverà &quot;Rossi&quot; e &quot;Russi&quot;.</td>
</tr>
<tr>
<td><em>valore</em>,<em>valore</em> (virgola)</td>
<td>Corrisponde ai valori separati da virgole</td>
<td>Digitare tutti i criteri e separarli con virgole.</td>
<td>Digitando <strong>A, D, F, G</strong> si troveranno esattamente &quot;A&quot;, &quot;D&quot;, &quot;F&quot; e &quot;G&quot;. Digitando <strong>10, 20, 30, 100</strong> si troveranno esattamente &quot;10, 20, 30, 100&quot;.</td>
</tr>
<tr>
<td>"" (due virgolette doppie)</td>
<td>Corrispondenza di un valore vuoto</td>
<td>Digitare due virgolette doppie consecutive per filtrare i valori vuoti in quel campo.</td>
<td>Due doppie virgolette consecutive ( <strong> "" </strong>) trova le righe senza valore per la colonna corrente.</td>
</tr>
<tr>
<td>(<span class="code">Query Finance and Operations</span>) (Query Finance and Operations tra parentesi)</td>
<td>Corrisponde a una query definita.</td>
<td>Digitare una query come un'istruzione SQL tra parentesi utilizzando il linguaggio di query Finance and Operations.</td>
  <td><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong><br><br> 
       come esempio di sintassi per una condizione di filtro su un campo dall'origine dati radice e un campo da un'origine dati diversa (per la pagina Tutti i clienti)</td>
</tr>
<tr>
<td>M</td>
<td>Data odierna</td>
<td>Digitare <strong>M</strong>.</td>
<td><strong>M</strong> corrisponde alla data odierna.</td>
</tr>
<tr>
<td>(nomeMetodo(parametri)) (metodo <strong>SysQueryRangeUtil</strong> tra parentesi)</td>
<td>Corrispondenza del valore o dell'intervallo di valori specificati dai parametri del metodo <strong>SysQueryRangeUtil</strong></td>
<td>Digitare un metodo <strong>SysQueryRangeUtil</strong> con parametri che specificano il valore o un intervallo di valori.</td>
<td>
<ol>
<li>Fare clic su <strong>Contabilità clienti</strong> &gt; <strong>Fatture</strong> &gt; <strong>Fatture cliente aperte</strong>.</li>
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
<thead>
<tr>
<th>Metodo</th>
<th>Descrizione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr>
<td>Day (_relativeDays=0)</td>
<td>Trova una data in relazione alla data della sessione. I valori positivi indicano date future e i valori negativi indicano date passate.</td>
<td>
<ul>
<li><strong>Domani</strong> – immettere <strong>(Day(1))</strong>.</li>
<li><strong>Oggi</strong> – immettere <strong>(Day(0))</strong>.</li>
<li><strong>Ieri</strong> – Immettere <strong>(Day(-1))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>Trova un intervallo di date in relazione alla data della sessione. I valori positivi indicano date future e i valori negativi indicano date passate.</td>
<td>
<ul>
<li><strong>Ultimi 30 giorni</strong> – Immettere <strong>(DayRange(-30,0))</strong>.</li>
<li><strong>30 giorni precedenti e 30 giorni successivi</strong> – Immettere <strong>(DayRange(-30,30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>Trova tutte le date dopo la data relativa specificata.</td>
<td>
<ul>
<li><strong>Più di 30 giorni dalla data odierna</strong> - Immettere <strong>(GreaterThanDate(30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanUtcNow ()</td>
<td>Trova tutte le voci data/ora dopo l'ora corrente.</td>
<td>
<ul>
<li><strong>Qualsiasi data/ora futura</strong> - Immettere <strong>(GreaterThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>Trova tutte le date precedenti alla data relativa specificata.</td>
<td>
<ul>
<li><strong>Meno di sette giorni dalla data odierna</strong> - Immettere <strong>(LessThanDate(7))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanUtcNow ()</td>
<td>Trova tutte le voci data/ora prima dell'ora corrente.</td>
<td>
<ul>
<li><strong>Tutte le date/ore passate</strong> - Immettere <strong>(LessThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Trova un intervallo di date, in base ai mesi rispetto al mese corrente.</td>
<td>
<ul>
<li><strong>Due mesi precedenti</strong> - Immettere <strong>(MonthRange(- 2,0))</strong>.</li>
<li><strong>Tre mesi successivi</strong> - Immettere <strong>(MonthRange(0,3))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Trova un intervallo di date, in base agli anni rispetto all'anno corrente.</td>
<td>
<ul>
<li><strong>Anno successivo</strong> - Immettere <strong>(YearRange(0, 1))</strong>.</li>
<li><strong>Anno precedente</strong> - Immettere <strong>(YearRange(-1,0))</strong>.</li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]