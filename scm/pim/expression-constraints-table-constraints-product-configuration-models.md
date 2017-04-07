---
title: Vincoli di espressione e vincoli di tabella nei modelli di configurazione prodotto
description: "In questo argomento viene descritto l&quot;utilizzo dei vincoli di espressione e dei vincoli di tabella. I vincoli consentono di controllare i valori di attributo da selezionare quando si configurano i prodotti per un ordine cliente, un&quot;offerta di vendita, un ordine fornitore o un ordine di produzione. È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-02-24 15 - 08 - 06
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 1fe8a0d90a3f707fa7b0fea0310c819ce5040a42
ms.lasthandoff: 03/30/2017


---

# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a>Vincoli di espressione e vincoli di tabella nei modelli di configurazione prodotto

In questo argomento viene descritto l'utilizzo dei vincoli di espressione e dei vincoli di tabella. I vincoli consentono di controllare i valori di attributo da selezionare quando si configurano i prodotti per un ordine cliente, un'offerta di vendita, un ordine fornitore o un ordine di produzione. È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli. 

I vincoli consentono di controllare i valori di attributo da selezionare quando si configurano i prodotti per un ordine cliente, un'offerta di vendita, un ordine fornitore o un ordine di produzione. È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli.

## <a name="what-are-expression-constraints"></a>Cosa sono i vincoli di espressione?
I vincoli di espressione sono caratterizzati da un'espressione che utilizza funzioni e operatori aritmetici e booleani. Un vincolo di espressione viene scritto per un componente specifico nel modello di configurazione prodotto e non può essere riutilizzato o condiviso con un altro componente. Può tuttavia fare riferimento ad attributi di sottocomponenti del componente per cui è scritto.

## <a name="what-are-table-constraints"></a>Cosa sono i vincoli di tabella?
I vincoli di tabella elencano le combinazioni di valori consentiti per gli attributi quando si configura un prodotto. Le definizioni dei vincoli di tabella possono essere utilizzate genericamente. Quando si crea un vincolo di tabella per un componente in un modello di configurazione prodotto, selezionare una definizione di vincolo di tabella. Per creare le combinazioni consentite, si aggiungono attributi di tipi specifici ai componenti. Ogni tipo di attributo ha un valore specifico.

### <a name="example-of-a-table-constraint"></a>Esempio di vincolo di tabella

In questo esempio viene illustrato come è possibile limitare la configurazione di un altoparlante a rivestimenti e frontali specifici del cabinet. Nella prima tabella vengono illustrati i rivestimenti e i frontali del cabinet che sono in genere disponibili per la configurazione. I valori sono definiti per ** il fine del Governo ** e ** fronteggi la griglia ** l'attributo i tipi.

| Tipo di attributo | Valori                      |
|----------------|-----------------------------|
| Rivestimento del cabinet | Nero, Quercia, Palissandro, Bianco |
| Griglia anteriore    | Nero, Metallo, Bianco         |

Nella tabella seguente vengono illustrate le combinazioni definite dal vincolo di tabella **Colore e rivestimento**. Utilizzando questo vincolo di tabella, è possibile configurare un altoparlante con un rivestimento di quercia e una griglia nera, un rivestimento di palissandro e una griglia bianca, ecc.

| Fine         | Griglia                       |
|----------------|-----------------------------|
| Quercia            | Nero                       |
| Palissandro       | Bianco                       |
| Bianco          | Nero                       |
| Bianco          | Bianco                       |
| Nero          | Nero                       |
| Nero          | Metallo                       | 

È possibile creare vincoli di tabella definiti dal sistema e vincoli di tabella definiti dall'utente. Per ulteriori informazioni, vedere [Vincoli di tabella definiti dall'utente e dal sistema](system-defined-user-defined-table-constraints.md).

## <a name="what-syntax-should-be-used-to-write-constraints"></a>Sintassi che dovrà essere utilizzata per scrivere i vincoli?
Per scrivere i vincoli, è necessario utilizzare la sintassi OML (Optimization Modeling Language). Il sistema utilizza risolutore del vincolo di Solver Foundation di Microsoft per risolvere i vincoli.

## <a name="should-i-use-table-constraints-or-expression-constraints"></a>È meglio utilizzare i vincoli di tabella o i vincoli di espressione?
È possibile utilizzare i vincoli di espressione o i vincoli di tabella, a seconda di come si preferisce creare i vincoli. Si sviluppa un vincolo di tabella come matrice, mentre un vincolo di espressione è una singola istruzione. Quando si configura un prodotto, non importa il tipo di vincolo utilizzato. Nel seguente esempio è mostrato in che modo i due metodi differiscono.  

Quando si configura un prodotto tramite le seguenti impostazioni del vincolo, sono consentite queste combinazioni:

-   Un prodotto di colore nero e con dimensioni 30 o 50
-   Un prodotto di colore rosso e con dimensioni 20

### <a name="table-constraint-setup"></a>Impostazione del vincolo di tabella

| Colore | Dimensione |
|-------|------|
| Nero | 30   |
| Nero | 50   |
| Rosso   | 20   |

### <a name="expression-constraint-setup"></a>Impostazione del vincolo di espressione

(Color == "Nero" & (size == "30" | size == "50")) | (color == "Rosso" & size = "20")

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a>È necessario utilizzare gli operatori o la notazione di infisso quando si scrivono i vincoli di espressione?
È possibile scrivere un vincolo di espressione utilizzando gli operatori di prefisso disponibili o la notazione di infisso. Per gli operatori **Min**, **Max** e **Abs **non è possibile utilizzare una notazione di infisso. Questi operatori sono inclusi come operatori standard nella maggior parte dei linguaggi di programmazione.

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a>Quali operatori e notazione di infisso è possibile utilizzare quando si scrivono i vincoli di espressione?
Nelle tabelle seguenti sono elencati gli operatori e la notazione di infisso che è possibile utilizzare per scrivere un vincolo di espressione per un componente in un modello di configurazione prodotto. Negli esempi della prima tabella è possibile vedere come scrivere un'espressione utilizzando la notazione di infisso o gli operatori.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Operatore</th>
<th>Descrizione</th>
<th>Sintassi</th>
<th>Esempi</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implies</td>
<td>È true se la prima condizione è false, la seconda condizione è true o entrambi.</td>
<td>Implies[a, b], infix: a -: b</td>
<td><ul>
<li><strong>Operatore:</strong> [Implica x! = 0, Y &gt;= 0]</li>
<li><strong>Notazione di infisso:</strong> x! = 0 -: X &gt;= 0</li>
</ul></td>
</tr>
<tr class="even">
<td>E</td>
<td>È true solo se tutte le condizioni sono true. Se il numero di condizioni è 0 (zero), viene generato il valore <strong>True</strong>.</td>
<td>In args [], infisso: &amp; è &amp; una z... &amp;</td>
<td><ul>
<li><strong>Operatore:</strong> In [==, Y 2 x &lt;2 =]</li>
<li><strong>Notazione di infisso:</strong> x == Y &lt;2 &amp; = 2</li>
</ul></td>
</tr>
<tr class="odd">
<td>O</td>
<td>È true se qualsiasi condizione è true. Se il numero di condizioni è 0 (zero), viene generato il valore <strong>False</strong>.</td>
<td>In args [], infisso: a _=_ b _=_ _=_... z</td>
<td><ul>
<li><strong>Operatore:</strong> In [==, Y 2 x &lt;2 =]</li>
<li><strong>Notazione di infisso:</strong> == x 2 _=_ X &lt;= 2</li>
</ul></td>
</tr>
<tr class="even">
<td>Più</td>
<td>Questa espressione somma le condizioni. Se il numero di condizioni è 0 (zero), viene generato il valore <strong>0</strong>.</td>
<td>In args [], infisso: + a quanto + + z...</td>
<td><ul>
<li><strong>Operatore:</strong> Plus[x, y, 2] == z</li>
<li><strong>Notazione di infisso:</strong> x + y + 2 == z</li>
</ul></td>
</tr>
<tr class="odd">
<td>Meno</td>
<td>Nega il proprio argomento. Questa espressione deve avere esattamente una condizione.</td>
<td>Minus[expr], infix: -expr</td>
<td><ul>
<li><strong>Operatore:</strong> Minus[x] == y</li>
<li><strong>Notazione di infisso:</strong> -x == y</li>
</ul></td>
</tr>
<tr class="even">
<td>Abs</td>
<td>Questa espressione accetta il valore assoluto della propria condizione. Questa espressione deve avere esattamente una condizione.</td>
<td>Abs[expr]</td>
<td><strong>Operatore:</strong> Abs[x]</td>
</tr>
<tr class="odd">
<td>Tempi</td>
<td>questa espressione accetta il prodotto delle proprie condizioni. Se il numero di condizioni è 0 (zero), viene generato il valore <strong>1</strong>.</td>
<td>Periodi args [], infisso: a quanto * * * z...</td>
<td><ul>
<li><strong>Operatore:</strong> Times[x, y, 2] == z</li>
<li><strong>Notazione di infisso:</strong> x * y * 2 == z</li>
</ul></td>
</tr>
<tr class="even">
<td>Potenza</td>
<td>Questa espressione accetta un valore esponenziale. Questa espressione applica l'elevamento a potenza da destra a sinistra. (Ovvero è diritto- associativa). Di conseguenza, <strong>[Potenza su, B, è]</strong> è equivalente. <strong>Elevamento a potenza</strong> può essere utilizzato solo se l'esponente è una costante positiva.</td>
<td>Potenza args [], infisso: ^ un z di ^ di ^ b...</td>
<td><ul>
<li><strong>Operatore:</strong> Power[x, 2] == y</li>
<li><strong>Notazione di infisso:</strong> x ^ 2 == y</li>
</ul></td>
</tr>
<tr class="odd">
<td>Max.</td>
<td>Questa espressione genera la maggiore condizione. Se il numero di condizioni è 0 (zero), viene generato il valore <strong>Infinity</strong>.</td>
<td>Max[args]</td>
<td><strong>Operatore:</strong> Max[x, y, 2] == z</td>
</tr>
<tr class="even">
<td>Min.</td>
<td>Questa espressione genera la condizione minore. Se il numero di condizioni è 0 (zero), viene generato il valore <strong>Infinity</strong>.</td>
<td>Min[args]</td>
<td><strong>Operatore:</strong> Min[x, y, 2] == z</td>
</tr>
<tr class="odd">
<td>Non</td>
<td>Questa espressione genera l'inverso logico della propria condizione. Questa espressione deve avere esattamente una condizione.</td>
<td>Not[expr], infix: !expr</td>
<td><ul>
<li><strong>Operatore:</strong> Non x [] &amp; [non == di Y 3]</li>
<li><strong>Notazione di infisso:</strong> !x!(y == 3)</li>
</ul></td>
</tr>
</tbody>
</table>

Gli esempi nella seguente tabella illustrano come scrivere una notazione di infisso.

| Notazione di infisso    | descrizione                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| x + y + z         | Addizione                                                                                      |
| Y x \* \* z       | Moltiplicazione                                                                                |
| x - y             | La sottrazione binaria è tradotta come l'addizione binaria nei casi in cui esiste un secondo valore negato. |
| x ^ y ^ z         | Elevamento a potenza con associatività a destra                                                   |
| !x                | Booleano not                                                                                   |
| x -: y            | Implicazione booleana                                                                           |
|  interno  | y | z         | Booleano or                                                                                    |
| x & y & z         | Booleano and                                                                                   |
| x == y == z       | Uguaglianza                                                                                      |
| x != y != z       | Distinto                                                                                      |
| Y x &lt; &lt; z   | Minore di                                                                                     |
| Y x &gt; &gt; z   | Maggiore di                                                                                  |
| x &lt;= X &lt;= z | Uguale o minore di                                                                         |
| x &gt;= X &gt;= z | Uguale o maggiore di                                                                      |
| (x)               | Le parentesi hanno precedenza sulla priorità predefinita.                                                      |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a>Perché i vincoli di espressione non vengono convalidati correttamente?
Non è possibile utilizzare le parole chiave riservate come nomi di risoluzione per gli attributi, i componenti o i sottocomponenti nel modello di configurazione prodotto. Di seguito è riportato un elenco delle parole chiave prenotate non è possibile utilizzare:

-   Arrotonda eccesso
-   Elemento
-   Uguale
-   Piano
-   Se
-   Minore di
-   Maggiore di
-   Implies
-   Registro
-   Max.
-   Min.
-   Meno
-   Più
-   Potenza
-   Tempi
-   Fascia oraria
-   Modello
-   Potere decisionale
-   Obiettivo


<a name="see-also"></a>Vedere anche
--------

[Creare un vincolo di espressioni della Guida (attività)](http://ax.help.dynamics.com/en/wiki/create-an-expression-constraint/)

[Aggiungere un calcolo a un modello di configurazione prodotto (Guida di attività)](http://ax.help.dynamics.com/en/wiki/add-a-calculation-to-a-product-configuration-model/)


