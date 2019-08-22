---
title: Regole dei criteri di controllo
description: È possibile utilizzare i criteri di controllo per valutare le note spese, le fatture fornitore e gli ordini fornitore per assicurare che siano conformi alle regole dei criteri create. Tutte le regole associate ai criteri di controllo vengono eseguite in modalità batch in base a una programmazione specificata.  Ciascuna regola dei criteri è un'istanza di un tipo di regola dei criteri. Può essere attiva solo una regola dei criteri per volta per ciascun tipo di regola dei criteri.
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: de6406029aa88424863dd9a47505f5b3ad27f237
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839595"
---
# <a name="audit-policy-rules"></a>Regole dei criteri di controllo

[!include [banner](../includes/banner.md)]

È possibile utilizzare i criteri di controllo per valutare le note spese, le fatture fornitore e gli ordini fornitore per assicurare che siano conformi alle regole dei criteri create. Tutte le regole associate ai criteri di controllo vengono eseguite in modalità batch in base a una programmazione specificata.  Ciascuna regola dei criteri è un'istanza di un tipo di regola dei criteri. Può essere attiva solo una regola dei criteri per volta per ciascun tipo di regola dei criteri. 

<a name="queries-and-query-types"></a>Query e tipi di query
-----------------------

Quando si crea una regola dei criteri di controllo, è necessario prima selezionare un tipo di regola dei criteri. Il tipo di regola dei criteri consente di specificare la struttura a oggetti applicativi (AOT) da utilizzare come punto di partenza per la creazione della regola dei criteri. Consente inoltre di specificare il tipo di query da utilizzare per la regola dei criteri. La query determina il documento di origine che valuta la regola dei criteri. Nella query vengono inoltre specificati i campi nel documento di origine che identificano la persona giuridica e la data da utilizzare quando i documenti vengono selezionati per il controllo. Il tipo di query gestisce i campi predefiniti nella pagina di query e nella pagina Regola dei criteri di controllo. Nella seguente tabella vengono visualizzati i tipi di query disponibili per le regole dei criteri di controllo.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di query</th>
<th>Scopo</th>
<th>Ulteriori informazioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Condizionale</td>
<td>Valutare gli attributi del documento di origine a fronte dei valori specificati.</td>
<td></td>
</tr>
<tr class="even">
<td>Aggrega</td>
<td>Valutare più documenti di origine o righe di documenti di origine a fronte di una regola dei criteri tramite l'aggregazione di valori numerici.</td>
<td></td>
</tr>
<tr class="odd">
<td>Campionamento</td>
<td>Effettuare la selezione casuale di una percentuale specificata dei documenti di origine da valutare a fronte delle violazioni dei criteri.</td>
<td>Quando si seleziona questa opzione, utilizzare la pagina Regola dei criteri di controllo per specificare la percentuale di documenti da selezionare in modo casuale per il controllo.</td>
</tr>
<tr class="even">
<td>Duplicato</td>
<td>Valutare i documenti di origine per determinare se contengono voci duplicate nei campi specificati.</td>
<td>Quando si seleziona questa opzione, utilizzare la pagina Regola dei criteri di controllo per specificare il numero di giorni da aggiungere all'inizio dell'intervallo date per la selezione dei documenti quando questi vengono valutati per la ricerca delle voci duplicate.</td>
</tr>
<tr class="odd">
<td>Elenca ricerca</td>
<td>Valutare i documenti di origine rispetto a entità specifiche.</td>
<td>Il documento principale della query definisce il documento in fase di controllo. La query deve essere una query elenco contenente un riferimento alla tabella dirpartytable. Questa opzione può essere utilizzata solo con le seguenti query AOT:
<ul>
<li><span class="ui">AuditPolicyExpenseList</span> (dipendenti con nota spese controllata)</li>
<li><span class="ui">AuditPolicyPurchList</span> (Fornitori con ordine acquisto controllato)</li>
<li><span class="ui">AuditPolicyVendInvoiceList</span> (fornitori con fattura fornitore monitorata)</li>
</ul>
Quando si seleziona questa opzione, specificare le entità monitorate nella pagina Regola dei criteri di controllo.</td>
</tr>
<tr class="even">
<td>Ricerca per parole chiave</td>
<td>Valutare i documenti di origine per stabilire se contengono determinate parole.</td>
<td>Quando si seleziona questa opzione, immettere i termini da cercare nella pagina Regola dei criteri di controllo. La pagina Regola dei criteri di controllo include opzioni che consentono di specificare le tabelle e i campi da valutare a fronte delle parole immesse.</td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a>Parametri comuni
Tutte le regole dei criteri per determinati criteri di controllo condividono gli stessi parametri di batch e lo stesso intervallo date per selezione documenti. Questi parametri sono specificati per i criteri nella pagina Opzioni aggiuntive.



<a name="additional-resources"></a>Risorse aggiuntive
--------

[Casi e violazioni dei criteri di controllo](audit-policy-violations-cases.md)
[Definire i criteri di controllo per i documenti di origine](tasks/define-audit-policies-source-documents.md)


