---
title: Sintassi di filtro e query avanzata
description: Questo articolo descrive le opzioni di filtro e query disponibili quando si utilizza la finestra di dialogo Filtro/ordinamento avanzato o l'operatore **corrisponde a** nel riquadro Filtro o nei filtri di intestazione di colonna.
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: edff2fba7e231ae52abf7828d55c1fe4841ccd7f
ms.openlocfilehash: 3e7127a9412dcf9324872c06fbf6cc3cf61bf063
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="c0ff3-103">Sintassi di query e filtro avanzata</span><span class="sxs-lookup"><span data-stu-id="c0ff3-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0ff3-104">Questo articolo descrive le opzioni di filtro e query disponibili quando si utilizza la finestra di dialogo Filtro/ordinamento avanzato o l'operatore **corrisponde a** nel riquadro Filtro o nei filtri di intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-104">This article describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span> 

<a name="advanced-query-syntax"></a><span data-ttu-id="c0ff3-105">Sintassi di query avanzata</span><span class="sxs-lookup"><span data-stu-id="c0ff3-105">Advanced query syntax</span></span>
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
<th><span data-ttu-id="c0ff3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0ff3-106">Syntax</span></span></th>
<th><span data-ttu-id="c0ff3-107">Descrizione carattere</span><span class="sxs-lookup"><span data-stu-id="c0ff3-107">Character description</span></span></th>
<th><span data-ttu-id="c0ff3-108">descrizione</span><span class="sxs-lookup"><span data-stu-id="c0ff3-108">Description</span></span></th>
<th><span data-ttu-id="c0ff3-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0ff3-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c0ff3-110"><em>valore</em></span><span class="sxs-lookup"><span data-stu-id="c0ff3-110"><em>value</em></span></span></td>
<td><span data-ttu-id="c0ff3-111">Uguale al valore immesso</span><span class="sxs-lookup"><span data-stu-id="c0ff3-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="c0ff3-112">Digitare il valore da trovare.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="c0ff3-113">Digitando <strong>Rossi</strong> si troverà &quot;Rossi&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-114">!<em>valore</em> (punto esclamativo)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="c0ff3-115">Non uguale al valore immesso</span><span class="sxs-lookup"><span data-stu-id="c0ff3-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="c0ff3-116">Digitare un punto esclamativo e poi il valore da escludere.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="c0ff3-117">Digitando <strong>!Rossi</strong> si troveranno tutti i valori tranne &quot;Rossi&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c0ff3-118"><em>da valore</em>..<em>a valore</em> (due punti consecutivi)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="c0ff3-119">Compreso tra i due valori separati da due punti consecutivi.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="c0ff3-120">Digitare il valore iniziale, quindi due punti consecutivi e infine il valore finale.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="c0ff3-121">Digitando <strong>1..10</strong> si troveranno tutti i valori da 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="c0ff3-122">In un campo stringa, tuttavia, digitando <strong>A..C</strong> si troveranno tutti i valori che iniziano con &quot;A&quot; e &quot;B&quot; e i valori che corrispondono esattamente a &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="c0ff3-123">Ad esempio, questa query non troverà &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-123">For example, this query won&#39;t find &quot;Ca&quot;.</span></span> <span data-ttu-id="c0ff3-124">Per trovare tutti i valori da &quot;A<em>&quot; a &quot;C</em>&quot;, digitare <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-125">..<em>valore</em> (due punti consecutivi)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="c0ff3-126">Minore o uguale al valore immesso</span><span class="sxs-lookup"><span data-stu-id="c0ff3-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="c0ff3-127">Digitare i due punti consecutivi, quindi il valore.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="c0ff3-128">Digitando <strong>..1000</strong> si troverà qualsiasi numero minore o uguale a 1000, ad esempio &quot;100&quot;, &quot;999,95&quot; e &quot;1.000&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c0ff3-129"><em>valore</em>..</span><span class="sxs-lookup"><span data-stu-id="c0ff3-129"><em>value</em>..</span></span> <span data-ttu-id="c0ff3-130">(due punti consecutivi)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-130">(double period)</span></span></td>
<td><span data-ttu-id="c0ff3-131">Maggiore o uguale al valore immesso</span><span class="sxs-lookup"><span data-stu-id="c0ff3-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="c0ff3-132">Digitare il valore, quindi i due punti consecutivi.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="c0ff3-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="c0ff3-133"><strong>1000..</strong></span></span> <span data-ttu-id="c0ff3-134">troverà qualsiasi numero maggiore o uguale a 1000, ad esempio &quot;1.000&quot;, &quot;1.000,01&quot; e &quot;1.000.000&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-135">&gt;<em>valore</em> (segno di maggiore)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="c0ff3-136">Maggiore del valore immesso</span><span class="sxs-lookup"><span data-stu-id="c0ff3-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="c0ff3-137">Digitare un segno di maggiore(<strong>&gt;</strong>), quindi il valore.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="c0ff3-138">Digitando <strong>&gt;1000</strong> si troverà qualsiasi numero maggiore di 1000, ad esempio &quot;1000,01&quot;, &quot;20.000&quot; e &quot;1.000.000&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c0ff3-139">&lt;<em>valore</em> (segno di minore)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="c0ff3-140">Minore del valore immesso</span><span class="sxs-lookup"><span data-stu-id="c0ff3-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="c0ff3-141">Digitare un segno di minore (<strong>&lt;</strong>), quindi il valore.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="c0ff3-142">Digitando <strong>&lt;1000</strong> si troverà qualsiasi numero minore di 1000, ad esempio &quot;999,99&quot;, &quot;1&quot; e &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-143"><em>valore</em>\* (asterisco)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="c0ff3-144">Inizia con il valore immesso</span><span class="sxs-lookup"><span data-stu-id="c0ff3-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="c0ff3-145">Digitare il valore iniziale, quindi un asterisco (<strong><em></strong>).</span><span class="sxs-lookup"><span data-stu-id="c0ff3-145">Type the starting value and then an asterisk (<strong><em></strong>).</span></span></td>
<td><span data-ttu-id="c0ff3-146">Digitando <strong>S</em></strong> si troverà qualsiasi stringa che inizia con &quot;S&quot;, ad esempio &quot;Stoccolma&quot;, &quot;Sydney&quot; e &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-146"><strong>S</em></strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c0ff3-147"><em><em>valore</em> (asterisco)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-147"><em><em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="c0ff3-148">Finisce con il valore immesso</span><span class="sxs-lookup"><span data-stu-id="c0ff3-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="c0ff3-149">Digitare un asterisco, quindi il valore finale.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="c0ff3-150">Digitando <strong></em>est</strong> si troverà qualsiasi stringa che finisce con &quot;est&quot;, ad esempio &quot;Nordest&quot; e &quot;Sudest&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-150"><strong></em>east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-151"><em><em>valore</em></em> (asterisco)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-151"><em><em>value</em></em> (asterisk)</span></span></td>
<td><span data-ttu-id="c0ff3-152">Contiene il valore immesso</span><span class="sxs-lookup"><span data-stu-id="c0ff3-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="c0ff3-153">Digitare un asterisco, quindi un valore e infine un altro asterisco.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="c0ff3-154">Digitando <strong><em>de</em></strong> si troverà qualsiasi stringa che contiene &quot;de&quot;, ad esempio &quot;Nordest&quot; e &quot;Sudest&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-154"><strong><em>th</em></strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c0ff3-155">?</span><span class="sxs-lookup"><span data-stu-id="c0ff3-155">?</span></span> <span data-ttu-id="c0ff3-156">(punto interrogativo)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-156">(question mark)</span></span></td>
<td><span data-ttu-id="c0ff3-157">Contiene uno o più caratteri sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="c0ff3-158">Digitare un punto interrogativo in corrispondenza della posizione del carattere sconosciuto all'interno del valore.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="c0ff3-159">Digitando <strong> R?ssi</strong> si troverà &quot;Rossi&quot; e &quot;Russi&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-160"><em>valore</em>,<em>valore</em> (virgola)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="c0ff3-161">Corrisponde ai valori separati da virgole</span><span class="sxs-lookup"><span data-stu-id="c0ff3-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="c0ff3-162">Digitare tutti i criteri e separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="c0ff3-163">Digitando <strong>A, D, F, G</strong> si troveranno esattamente &quot;A&quot;, &quot;D&quot;, &quot;F&quot; e &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="c0ff3-164">Digitando <strong>10, 20, 30, 100</strong> si troveranno esattamente &quot;10, 20, 30, 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c0ff3-165">(<span class="code">Istruzione SQL</span>) (istruzione SQL tra parentesi)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-165">(<span class="code">SQL statement</span>) (SQL statement between parentheses)</span></span></td>
<td><span data-ttu-id="c0ff3-166">Corrisponde a una query definita.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-166">Matching a defined query</span></span></td>
<td><span data-ttu-id="c0ff3-167">Digitare una query sotto forma di istruzione SQL racchiusa tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-167">Type a query as an SQL statement between parentheses.</span></span></td>
<td><span data-ttu-id="c0ff3-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span><span class="sxs-lookup"><span data-stu-id="c0ff3-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-169">T</span><span class="sxs-lookup"><span data-stu-id="c0ff3-169">T</span></span></td>
<td><span data-ttu-id="c0ff3-170">Data odierna</span><span class="sxs-lookup"><span data-stu-id="c0ff3-170">Today&#39;s date</span></span></td>
<td><span data-ttu-id="c0ff3-171">Digitare <strong>M</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-171">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="c0ff3-172"><strong>T</strong> corrisponde alla data odierna.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-172"><strong>T</strong> matches today&#39;s date.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c0ff3-173">(nomeMetodo(parametri)) (metodo <strong>SysQueryRangeUtil</strong> tra parentesi)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-173">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="c0ff3-174">Corrispondenza del valore o dell'intervallo di valori specificati dai parametri del metodo <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="c0ff3-174">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="c0ff3-175">Digitare un metodo <strong>SysQueryRangeUtil</strong> con parametri che specificano il valore o un intervallo di valori.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-175">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td><ol>
<li><span data-ttu-id="c0ff3-176">Fare clic su <strong>Contabilità clienti</strong> &gt; <strong>Fatture</strong> &gt; <strong>Fatture cliente aperte</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-176">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="c0ff3-177">Premere Ctrl+Maiusc+F3 per aprire la pagina <strong>Richiesta info</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-177">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="c0ff3-178">Nella scheda <strong>Gamma</strong> scegliere <strong>Aggiungi</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-178">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="c0ff3-179">Nel campo <strong>Tabella</strong> selezionare <strong>Transazioni cliente aperte</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-179">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="c0ff3-180">Nel campo <strong>Campo</strong> selezionare <strong>Data di scadenza</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-180">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="c0ff3-181">Nel campo <strong>Criteri</strong> immettere <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-181">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="c0ff3-182">Scegliere <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-182">Click <strong>OK</strong>.</span></span> <span data-ttu-id="c0ff3-183">La pagina verrà aggiornata per elencare le fatture che soddisfano i criteri immessi.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-183">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="c0ff3-184">Per questo esempio specifico, vengono elencate le fatture incluse in scadenza nei due anni precedenti.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-184">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="c0ff3-185">Vedere la tabella nella sezione successiva per ulteriori dettagli sui metodi di data <strong>SysQueryRangeUtil</strong> e vari esempi.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-185">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="c0ff3-186">Query di data avanzate che utilizzano metodi SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="c0ff3-186">Advanced date queries that use SysQueryRangeUtil methods</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0ff3-187">Metodo</span><span class="sxs-lookup"><span data-stu-id="c0ff3-187">Method</span></span></th>
<th><span data-ttu-id="c0ff3-188">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0ff3-188">Description</span></span></th>
<th><span data-ttu-id="c0ff3-189">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0ff3-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c0ff3-190">Day (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-190">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="c0ff3-191">Trova una data in relazione alla data della sessione.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-191">Find a date relative to the session date.</span></span> <span data-ttu-id="c0ff3-192">I valori positivi indicano date future e i valori negativi indicano date passate.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-192">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="c0ff3-193"><strong>Domani</strong> – immettere <strong>(Day(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-193"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="c0ff3-194"><strong>Oggi</strong> – immettere <strong>(Day(0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-194"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="c0ff3-195"><strong>Ieri</strong> – Immettere <strong>(Day(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-195"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="c0ff3-197">Trova un intervallo di date in relazione alla data della sessione.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-197">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="c0ff3-198">I valori positivi indicano date future e i valori negativi indicano date passate.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-198">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="c0ff3-199"><strong>Ultimi 30 giorni</strong> – Immettere <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-199"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="c0ff3-200"><strong>30 giorni precedenti e 30 giorni successivi</strong> – Immettere <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-200"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c0ff3-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="c0ff3-202">Trova tutte le date dopo la data relativa specificata.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-202">Find all dates after the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="c0ff3-203"><strong>Più di 30 giorni dalla data odierna</strong> - Immettere <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-203"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-204">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="c0ff3-204">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="c0ff3-205">Trova tutte le voci data/ora dopo l'ora corrente.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-205">Find all date/time entries after the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="c0ff3-206"><strong>Qualsiasi data/ora futura</strong> - Immettere <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-206"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c0ff3-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="c0ff3-208">Trova tutte le date precedenti alla data relativa specificata.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-208">Find all dates before the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="c0ff3-209"><strong>Meno di sette giorni dalla data odierna</strong> - Immettere <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-209"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-210">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="c0ff3-210">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="c0ff3-211">Trova tutte le voci data/ora prima dell'ora corrente.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-211">Find all date/time entries before the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="c0ff3-212"><strong>Tutte le date/ore passate</strong> - Immettere <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-212"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c0ff3-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="c0ff3-214">Trova un intervallo di date, in base ai mesi rispetto al mese corrente.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-214">Find a range of dates, based on months relative to the current month.</span></span></td>
<td><ul>
<li><span data-ttu-id="c0ff3-215"><strong>Due mesi precedenti</strong> - Immettere <strong>(MonthRange(- 2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-215"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="c0ff3-216"><strong>Tre mesi successivi</strong> - Immettere <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-216"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c0ff3-217">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="c0ff3-217">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="c0ff3-218">Trova un intervallo di date, in base agli anni rispetto all'anno corrente.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-218">Find a range of dates, based on years relative to the current year.</span></span></td>
<td><ul>
<li><span data-ttu-id="c0ff3-219"><strong>Anno successivo</strong> - Immettere <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-219"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="c0ff3-220"><strong>Anno precedente</strong> - Immettere <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-220"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






