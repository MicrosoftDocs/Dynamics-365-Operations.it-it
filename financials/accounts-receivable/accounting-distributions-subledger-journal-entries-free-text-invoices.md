---
title: Distribuzioni contabili e sugli inserimenti nel giornale di registrazione secondario per le fatture a testo libero
description: "Le distribuzioni contabili vengono utilizzate per definire il modo in cui importo verrà conteggiato, ad esempio i ricavi, le tasse o le spese vengono conteggiate in una fattura a testo libero. Ogni importo che deve essere conteggiato quando la fattura a testo libero viene immessa nel giornale di registrazione avrà una o più distribuzioni contabili."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b530b5c8b5e252efb253dcf5b4ad080e2f646e5f
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="accounting-distributions-and-subledger-journal-entries-for-free-text-invoices"></a>Distribuzioni contabili e sugli inserimenti nel giornale di registrazione secondario per le fatture a testo libero

[!include[banner](../includes/banner.md)]


Le distribuzioni contabili vengono utilizzate per definire il modo in cui importo verrà conteggiato, ad esempio i ricavi, le tasse o le spese vengono conteggiate in una fattura a testo libero. Ogni importo che deve essere conteggiato quando la fattura a testo libero viene immessa nel giornale di registrazione avrà una o più distribuzioni contabili.

<a name="accounting-distributions"></a>Distribuzioni contabili
------------------------

È possibile utilizzare i pulsanti riportati di seguito nella pagina Fattura testo libero per visualizzare ed eventualmente modificare le distribuzioni contabili per ogni importo nella fattura testo libero.

-   **Distribuisci importi**: consente di visualizzare e modificare le distribuzioni contabili per una singola riga e tutte le righe figlio, ad esempio imposte o spese. È inoltre possibile visualizzare e modificare le distribuzioni contabili per la riga figlio direttamente dalla pagina Transazioni VAT o Transazioni spese.
    -   Modificare gli importi intestazione della fattura a testo libero, ad esempio le spese o gli importi di arrotondamento valuta.
    -   Modificare importi riga fattura a testo libero.
-   **Visualizza distribuzioni**: visualizza le distribuzioni contabili per tutte le righe del documento. Non è possibile modificare le distribuzioni contabili da questa visualizzazione.
    -   Visualizzare importi di riga e intestazione.

## <a name="distributing-amounts"></a>Distribuzione degli importi
Quando si immette una fattura a testo libero, ogni importo viene distribuito come indicato di seguito.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di importo monetario</th>
<th>Determina da dove viene visualizzato il conto principale</th>
<th>Ordine di priorità che determina la dimensione finanziaria predefinita visualizzata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Riga fattura a testo libero</td>
<td>Conto CoGe nella riga della fattura a testo libero.</td>
<td><ol>
<li>Se il conto principale è un conto di allocazione, utilizzare il valore predefinito dalla definizione del conto di allocazione.</li>
<li>Se il conto principale non è un conto allocazione, utilizzare il modello predefinito delle dimensioni finanziarie nella riga fattura a testo libero.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti nella riga fattura a testo libero.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto CoGe nella pagina Piano dei conti.</li>
</ol></td>
</tr>
<tr class="even">
<td>Riga fattura a testo libero per una combinazione di modello di valore e numero cespite
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>Nota </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Il conto principale nella riga fattura a testo libero sarà il conto di dismissione cespiti.</td>
</tr>
</tbody>
</table>
</div></td>
<td>Conto CoGe nella riga della fattura a testo libero.</td>
<td><ol>
<li>Utilizzare i valori di dimensione finanziaria predefiniti nella riga fattura a testo libero.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto CoGe nella pagina Piano dei conti.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Importo dello sconto fattura a testo libero</td>
<td>Il campo Conto principale per sconti cliente nella pagina Sconti di cassa.</td>
<td><ol>
<li>Se il conto principale è un conto di allocazione, utilizzare il valore predefinito dalla definizione del conto di allocazione.</li>
<li>Se il conto principale non è un conto allocazione, utilizzare il modello predefinito delle dimensioni finanziarie nella riga fattura a testo libero.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti nella riga fattura a testo libero.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto CoGe nella pagina Piano dei conti.</li>
</ol></td>
</tr>
<tr class="even">
<td>Importo IVA della fattura a testo libero</td>
<td>Il campo IVA a debito nella pagina dei gruppi di registrazione contabile.</td>
<td><ol>
<li>Utilizzare le dimensioni finanziarie definite nell'importo della riga fattura a testo libero o le distribuzioni per l'importo della riga addebito.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti nella riga fattura a testo libero.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto CoGe nella pagina Piano dei conti.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Importo della riga addebito fattura a testo libero</td>
<td>Il campo Conto in avere nella pagina Codice spese.</td>
<td><ol>
<li>Se il conto principale è un conto di allocazione, utilizzare il valore predefinito dalla definizione del conto di allocazione.</li>
<li>Se il conto principale non è un conto allocazione, utilizzare il modello predefinito delle dimensioni finanziarie nella riga fattura a testo libero.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti nella riga fattura a testo libero.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto CoGe nella pagina Piano dei conti.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a>Distribuzione di imposte
impossibile creare distribuzioni contabili per imposte fino a quando queste ultime non verranno calcolate. Per calcolare l'IVA, è necessario completare una delle seguenti attività nel modulo Fattura testo libero:
-   Visualizzare l'IVA.
-   Visualizzare il totale fattura.
-   Visualizzare il flusso di cassa.
-   Visualizzare le distribuzioni contabili per l'intera fattura a testo libero.
-   Visualizzare il giornale di registrazione secondario.

## <a name="subledger-journals-for-free-text-invoices"></a>Giornali di registrazione secondari per fatture a testo libero.
Prima di registrare una fattura a testo libero, è possibile visualizzare l'intera voce contabile della fattura, che include i debiti e gli accrediti, per verificare che la fattura venga registrata nei conti corretti. Questa visualizzazione della voce contabile completa viene chiamata giornale di registrazione secondario. L'inserimento nel giornale di registrazione secondario non può essere modificato se non è corretto quando lo si visualizza in anteprima prima di inserire nel giornale di registrazione la fattura a testo libero. È invece necessario modificare le distribuzioni contabili o il profilo registrazione. Le distribuzioni contabili vengono utilizzate per definire un lato della voce contabile, dare o avere. La voce contabile giornale di registrazione secondario in contropartita viene creata dai profili registrazione, ad esempio il conto client o le imposte.




