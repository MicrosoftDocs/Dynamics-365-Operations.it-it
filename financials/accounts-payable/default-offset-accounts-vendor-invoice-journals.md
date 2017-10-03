---
title: Conti di contropartita predefiniti per i giornali di registrazione fatture fornitore e giornali di registrazione di approvazione fatture
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4691ac4456b08084bcd93f7a8447719a15299c93
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a>Conti di contropartita predefiniti per i giornali di registrazione fatture fornitore e giornali di registrazione di approvazione fatture

[!include[banner](../includes/banner.md)]




I conti di contropartita predefiniti vengono utilizzati nelle pagine seguenti del giornale di registrazione fatture fornitore:

-   Giornale di registrazione fatture
-   Giornale di approvazione fatture

Utilizzare la seguente tabella per consentire di decidere se assegnare i conti predefiniti per i giornali di registrazione fatture.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostare i conti di contropartita predefiniti qui</th>
<th>Punto in cui i conti predefiniti sono forniti</th>
<th>Influenza sull'elaborazione</th>
<th>Momento in cui è necessario utilizzare questa opzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Gruppo di fornitori</strong>: impostare i conti di contropartita predefiniti per i gruppi di fornitori nella pagina <strong>Impostazione conto predefinito</strong> che è possibile aprire nella pagina <strong>Gruppi di fornitori</strong>.</td>
<td><ul>
<li>Account fornitore</li>
<li>Inserimenti nel giornale di registrazione per i conti fornitore nel gruppo di fornitori se i conti predefiniti non vengono specificati per i conti fornitore</li>
</ul></td>
<td>I conti di contropartita predefiniti per i gruppi di fornitori vengono visualizzati come conti predefiniti per i fornitori nella pagina <strong>Impostazione conto predefinito</strong>. È possibile aprire questa pagina dalla pagina elenco <strong>Tutti i fornitori</strong>.</td>
<td>Utilizzare questa opzione se in genere si pagano gli stessi tipi di articoli dagli stessi gruppi di fornitori nel tempo.</td>
</tr>
<tr class="even">
<td><strong>Conto fornitore</strong>: impostare i conti predefiniti per i conti fornitore nella pagina <strong>Impostazione conto predefinito</strong> che è possibile aprire nella pagina <strong>Fornitori</strong>.</td>
<td>Inserimenti nel giornale di registrazione per il conto fornitore</td>
<td>I conti di contropartita predefiniti per i conti fornitore vengono visualizzati come conti di contropartita predefiniti per gli inserimenti nel giornale di registrazione per il conto fornitore.</td>
<td>Utilizzare questa opzione se in genere si pagano gli stessi tipi di articoli dagli stessi fornitori nel tempo.</td>
</tr>
<tr class="odd">
<td><strong>Nomi giornale di registrazione</strong>: impostare i conti di contropartita predefiniti per i giornali di registrazione nella pagina <strong>Nomi giornale di registrazione</strong>. Selezionare <strong>Conto di contropartita fisso</strong>. Si noti che non è possibile specificare i conti di contropartita predefiniti nei nomi del giornale di registrazione se il tipo di giornale di registrazione dei nomi è <strong>Registro fatture</strong> o <strong>Approvazione</strong>.</td>
<td><ul>
<li>Intestazione giornale di registrazione che utilizza il nome del giornale di registrazione</li>
<li>Inserimenti nei giornali di registrazione che utilizzano il nome del giornale di registrazione</li>
</ul></td>
<td>Se viene selezionata la casella di controllo <strong>Conto di contropartita fisso</strong> nella pagina <strong>Nomi giornale di registrazione</strong>, il conto di contropartita per il nome del giornale di registrazione sostituisce il conto di contropartita predefinito per il fornitore o per il gruppo di fornitori.</td>
<td>Utilizzare questa opzione per impostare i giornali di registrazione per costi e spese specifici che vengono addebitati a conti specifici, indipendentemente dal fornitore o dal gruppo di fornitori di cui il fornitore fa parte.</td>
</tr>
<tr class="even">
<td><strong>Nomi giornale di registrazione</strong>: impostare i conti di contropartita predefiniti per i giornali di registrazione nella pagina <strong>Nomi giornale di registrazione</strong>. Deselezionare l'opzione <strong>Conto di contropartita fisso</strong>. Si noti che non è possibile specificare i conti di contropartita predefiniti nei nomi del giornale di registrazione se il tipo di giornale di registrazione dei nomi è <strong>Registro fatture</strong> o <strong>Approvazione</strong>.</td>
<td><ul>
<li>Intestazione giornale di registrazione</li>
<li>Inserimenti nei giornali di registrazione che utilizzano il nome del giornale di registrazione</li>
</ul></td>
<td>Questi valori predefiniti vengono utilizzati nelle pagine di intestazione del giornale di registrazione e il conto di contropartita nella pagina di intestazione del giornale di registrazione viene utilizzato come valore predefinito nelle pagine di giustificativo del giornale di registrazione. I conti predefiniti della pagina <strong>Nomi giornale di registrazione</strong> vengono utilizzati solo se i conti predefiniti non sono impostati per il conto fornitore.</td>
<td>Utilizzare questa opzione per impostare i conti predefiniti da utilizzare quando un conto di contropartita predefinito del fornitore non è assegnato.</td>
</tr>
<tr class="odd">
<td><strong>Intestazione giornale di registrazione</strong>: impostare un conto di contropartita predefinito per un giornale di registrazione da utilizzare come valore predefinito nelle pagine di giustificativo giornale di registrazione. Si noti che non è possibile specificare i conti di contropartita predefiniti nell'intestazione del giornale di registrazione se il tipo di giornale di registrazione dei nomi è <strong>Registro fatture</strong> o <strong>Approvazione</strong>.</td>
<td>Inserimenti nel giornale di registrazione</td>
<td>Il conto di contropartita predefinito per un giornale di registrazione viene utilizzato come valore predefinito nelle pagine del giustificativo giornale di registrazione.</td>
<td>Utilizzare questa opzione per velocizzare l'immissione di dati se la maggior parte delle voci in un giornale di registrazione hanno lo stesso conto di contropartita.</td>
</tr>
</tbody>
</table>






