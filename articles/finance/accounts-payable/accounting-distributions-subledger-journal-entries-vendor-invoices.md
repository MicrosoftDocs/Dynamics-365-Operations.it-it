---
title: Distribuzioni contabili e scritture contabili per le fatture fornitore
description: Le distribuzioni contabili vengono utilizzate per definire il modo in cui un importo verrà conteggiato, ad esempio le spese e le tasse vengono conteggiate in una fattura fornitore. Ogni importo che deve essere conteggiato quando la fattura fornitore viene immessa nel giornale di registrazione avrà una o più distribuzioni contabili.
author: sunfzam
ms.date: 02/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f10ddf113f59da4800a97a48300ab1310bfb42dd
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358183"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a>Distribuzioni contabili e scritture contabili per le fatture fornitore

[!include [banner](../includes/banner.md)]

Le distribuzioni contabili vengono utilizzate per definire il modo in cui un importo verrà conteggiato, ad esempio le spese e le tasse vengono conteggiate in una fattura fornitore. Ogni importo che deve essere conteggiato quando la fattura fornitore viene immessa nel giornale di registrazione avrà una o più distribuzioni contabili. 

## <a name="accounting-distributions"></a>Distribuzioni contabili 

È possibile utilizzare i pulsanti riportati di seguito nella pagina Fattura fornitore per visualizzare ed eventualmente modificare le distribuzioni contabili per ogni importo nella fattura fornitore.
-   **Distribuisci importi**: consente di visualizzare e modificare le distribuzioni contabili per una singola riga e tutte le righe figlio, ad esempio imposte o spese. È inoltre possibile visualizzare e modificare le distribuzioni contabili per la riga figlio direttamente dalla pagina **Transazioni VAT** o **Transazioni spese**.
    -   Modificare gli importi intestazione della fattura fornitore, ad esempio le spese o gli importi di arrotondamento valuta.
    -   Modificare gli importi delle righe della fattura fornitore.
-   **Visualizza distribuzioni**: visualizza le distribuzioni contabili per tutte le righe del documento. Non è possibile modificare le distribuzioni contabili da questa visualizzazione.
    -   Visualizzare importi di riga e intestazione.

Se la fattura fornitore fa riferimento a un ordine fornitore, è possibile dividere e modificare le distribuzioni contabili per le righe contenenti un articolo non stoccato. Se la riga della fattura fornitore non fa riferimento a una riga dell'ordine fornitore, è possibile anche eliminare una distribuzione contabile. Non è possibile dividere o eliminare le righe per spese, imposte e sconti riga. È possibile modificare il conto CoGe, ma non è consentita la modifica di importi o percentuali.
> [!NOTE]                                                                                                                                 
> Se la riga padre contiene un articolo non stoccato e le distribuzioni contabili vengono suddivise, la riga figlio verrà automaticamente suddivisa per corrispondere alle dimensioni finanziarie della riga padre. Le distribuzioni contabili per la riga figlio non possono inoltre essere suddivise o eliminate, ma in base all'impostazione della riga figlio potrebbe essere possibile modificare il conto CoGe per le distribuzioni contabili della riga figlio.

## <a name="distributing-amounts"></a>Distribuzione degli importi
Quando si immette una fattura fornitore, ogni importo viene distribuito come indicato di seguito.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di riga della fattura fornitore</th>
<th>Ordine di priorità che determina da dove viene visualizzato il conto principale</th>
<th>Ordine di priorità che determina la dimensione finanziaria predefinita visualizzata</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Prodotto stoccato</td>
<td><ol>
<li>La distribuzione contabile per la riga dell'ordine fornitore.</li>
<li>Campo <strong>Conto principale</strong> se la spesa di acquisto per il prodotto è selezionata nella pagina <strong>Registrazione</strong>.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti nella fattura fornitore.</li>
</ol></td>
</tr>
<tr class="even">
<td>Una categoria di approvvigionamento o un prodotto non stoccato</td>
<td><ol>
<li>Se la riga della fattura fornitore fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</li>
<li>Campo <strong>Conto principale</strong> se la spesa di acquisto per la spesa è selezionata nella pagina <strong>Registrazione</strong>.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Se il conto principale è un conto di allocazione, utilizzare il valore predefinito dalla definizione del conto di allocazione.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti nella fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina <strong>Piano dei conti</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Cespite</td>
<td><ol>
<li>Se la riga della fattura fornitore fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</li>
<li>Se l'opzione <strong>Acquisizione</strong> è selezionata nel campo <strong>Tipo di transazione</strong> della pagina <strong>Fatture fornitore</strong>, il campo <strong>Conto principale</strong> quando l'opzione <strong>Acquisizione</strong> è selezionata nella pagina <strong>Profili registrazione cespiti</strong>.</li>
<li>Se l'opzione <strong>Rettifica acquisizione</strong> è selezionata nel campo <strong>Tipo di transazione</strong>, il campo <strong>Conto principale</strong> quando l'opzione <strong>Rettifica acquisizione</strong> è selezionata nella pagina <strong>Profili registrazione cespiti</strong>.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina <strong>Piano dei conti</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Progetto definito nella riga fattura fornitore</td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</li>
<li>Se <strong>Saldo</strong> è selezionato nel campo <strong>Registra costi - Articolo</strong> nella pagina <strong>Gruppi di progetti</strong>, il campo <strong>Conto principale</strong> quando <strong>Costo</strong> è selezionato nella pagina <strong>Impostazioni registrazione contabile</strong>.</li>
<li>Se l'opzione <strong>Profitti e perdite</strong> è selezionata nel campo <strong>Registra costi - Articolo</strong> nella pagina <strong>Gruppi di progetti</strong>, il campo <strong>Conto principale</strong> quando l'opzione <strong>Costo - Articolo</strong> è selezionata nella pagina <strong>Impostazioni registrazione contabile</strong>.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Sconto riga</td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</li>
<li>Il campo <strong>Conto principale</strong> quando <strong>Sconto</strong> è selezionato nella pagina <strong>Registrazione</strong>.</li>
<li>Se nel profilo registrazione non è definito un conto principale per uno sconto, la distribuzione contabile del prezzo esteso nella riga ordine fornitore.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Utilizzare le dimensioni finanziarie delle distribuzioni contabili per il prezzo esteso nella riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria per la riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina <strong>Piano dei conti</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Spese di acquisto, immesse nella scheda <strong>Prezzo e sconto</strong> della riga ordine fornitore</td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</li>
<li>La distribuzione contabile del prezzo esteso nella riga ordine fornitore.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Utilizzare le dimensioni finanziarie delle distribuzioni contabili per il prezzo esteso nella riga fattura fornitore.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Spese riga</td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</li>
<li>Se il conto <strong>CoGe</strong> è selezionato nel campo <strong>Tipo di addebito</strong> nel modulo <strong>Codice spese</strong>, il campo <strong>Conto in Dare</strong> nella pagina <strong>Codice spese</strong>.</li>
<li>Se l'opzione <strong>Articolo</strong> è selezionata nel campo <strong>Tipo di addebito</strong> della pagina <strong>Codice spese</strong>, la distribuzione contabile per il prezzo esteso nella riga ordine fornitore.</li>
<li>Se l'opzione <strong>Cliente/Fornitore</strong> è selezionata nel campo <strong>Tipo di addebito</strong> nella pagina <strong>Codice spese</strong>, il campo <strong>Conto in Avere</strong> nella pagina <strong>Codice spese</strong>.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Utilizzare le dimensioni finanziarie delle distribuzioni contabili per il prezzo esteso nella riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina <strong>Piano dei conti</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Imposta, con la seguente condizione:
<ul>
<li>L'opzione <strong>Applica regole di tassazione statunitensi</strong> è selezionata nella pagina <strong>Parametri di contabilità generale</strong>.</li>
</ul></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</li>
<li>La distribuzione contabile della spesa o del prezzo esteso.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Utilizzare le dimensioni finanziarie delle distribuzioni contabili per il prezzo esteso nella riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Imposta, con le seguenti condizioni:
<ul>
<li>L'opzione <strong>Applica regole di tassazione statunitensi</strong> è deselezionata nella pagina <strong>Parametri di contabilità generale</strong>.</li>
<li>Il campo <strong>IVA intracomunitaria</strong> per la fascia IVA è deselezionata nella pagina <strong>Fasce IVA</strong>.</li>
</ul></td>
<td><ol>
<li>Se l'importo IVA è recuperabile, il campo <strong>IVA a credito</strong> nella pagina <strong>Gruppi registrazione contabile</strong>.</li>
<li>Se l'importo delle imposte non è recuperabile, il prezzo esteso o la distribuzione contabile per la spesa.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Utilizzare le dimensioni finanziarie del prezzo esteso o delle distribuzioni contabili per la spesa nella riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina <strong>Piano dei conti</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Imposta, con le seguenti condizioni:
<ul>
<li>L'opzione Applica regole di tassazione statunitensi è deselezionata nella pagina <strong>Parametri di contabilità generale</strong>.</li>
<li>Il campo <strong>IVA intracomunitaria</strong> per la fascia IVA è selezionata nella pagina <strong>Fasce IVA</strong>.</li>
</ul></td>
<td><ol>
<li>Se l'importo IVA è recuperabile, il campo <strong>IVA a credito</strong> nella pagina <strong>Gruppi registrazione contabile</strong>.</li>
<li>Se l'importo IVA non è recuperabile, il campo <strong>Importo IVA intracomunitaria</strong> nella pagina <strong>Gruppi registrazione contabile</strong>.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Utilizzare le dimensioni finanziarie del prezzo esteso o delle distribuzioni contabili per la spesa nella riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina <strong>Piano dei conti</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Spesa intestazione</td>
<td><ol>
<li>Se il conto <strong>CoGe</strong> è selezionato nel campo <strong>Tipo di addebito</strong> nel modulo <strong>Codice spese</strong>, il campo <strong>Conto in Dare</strong> nella pagina <strong>Codice spese</strong>.</li>
<li>Se l'opzione <strong>Cliente/Fornitore</strong> è selezionata nel campo <strong>Tipo di addebito</strong> nella pagina <strong>Codice spese</strong>, il campo <strong>Conto in Avere</strong> nella pagina <strong>Codice spese</strong>.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Se il conto principale è un conto di allocazione, utilizzare il valore predefinito dalla definizione del conto di allocazione.</li>
<li>Utilizzare i valori del modello predefinito di dimensione finanziaria dell'intestazione della fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina <strong>Piano dei conti</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Sconto intestazione</td>
<td><ol>
<li>Il campo <strong>Conto principale</strong> per il <strong>tipo di registrazione dello sconto fatture fornitore</strong> nella pagina <strong>Conti per transazioni automatiche</strong>.</li>
</ol></td>
<td><ol>
<li>Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</li>
<li>Utilizzare le dimensioni finanziarie delle distribuzioni contabili per il prezzo esteso nella riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</li>
<li>Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina <strong>Piano dei conti</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="distributing-taxes"></a>Distribuzione di imposte

impossibile creare distribuzioni contabili per imposte fino a quando queste ultime non verranno calcolate. Per calcolare l'IVA, è necessario completare una delle seguenti attività nella pagina **Fattura fornitore**:
-   Visualizzare il totale fattura.
-   Visualizzare l'IVA.
-   Visualizzare il giornale di registrazione secondario.
-   Visualizzare le distribuzioni contabili per la fattura fornitore completa.
-   Mettere in attesa la fattura fornitore
-   Registrare la fattura fornitore.

## <a name="subledger-journals-for-vendor-invoices"></a>Giornali di registrazione secondari per le fatture fornitore
Prima di registrare una fattura fornitore, è possibile visualizzare l'intera voce contabile della fattura, che include i debiti e gli accrediti, per verificare che venga registrata nei conti corretti. Questa visualizzazione della voce contabile completa viene chiamata giornale di registrazione secondario. 

L'inserimento nel giornale di registrazione secondario non può essere modificato se non è corretto quando lo si visualizza in anteprima prima di inserire nel giornale la fattura fornitore. È invece necessario modificare le distribuzioni contabili o il profilo registrazione. Le distribuzioni contabili vengono utilizzate per definire un lato della voce contabile, dare o avere. La voce contabile giornale di registrazione secondario in contropartita viene creata utilizzando i profili registrazione, ad esempio il conto fornitore o le imposte.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
