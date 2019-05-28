---
title: Reverse charge
description: In questo argomento viene descritto come configurare l'imposta sul valore aggiunto (IVA) in reverse charge per i paesi europei e l'Arabia Saudita.
author: epodkolz
manager: AnnBe
ms.date: 04/05/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 627b90659ce4e285667492e37be203cd9dbb7c9c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538010"
---
# <a name="reverse-charge-vat"></a>Reverse charge


[!include [banner](../includes/banner.md)]


In questo argomento viene descritto un approccio generico per l'impostazione dell'imposta sul valore aggiunto (IVA) in reverse charge per i paesi europei e l'Arabia Saudita.

Reverse charge è uno schema di imposta che sposta la responsabilità per la contabilità e la dichiarazione dell'IVA dal venditore all'acquirente delle merci e/o dei servizi. Di conseguenza, i destinatari delle merci e/o dei servizi dichiarano sia l'IVA in uscita (nel ruolo del venditore) che l'IVA in entrata (nel ruolo dell'acquirente) nella dichiarazione IVA.

In alcuni paesi lo schema reverse charge è implementato solo per alcune merci e/o servizi e sono presenti condizioni o limiti aggiuntivi sull'importo di vendita. In altri paesi, la responsabilità del pagamento dell'IVA dipende dallo stato del fornitore e dell'acquirente. Se la responsabilità del pagamento dell'IVA ricade sull'acquirente, questo deve essere chiaramente indicato nella fattura emessa dal fornitore. Ad esempio, la fattura deve includere la dicitura "Reverse charge" e deve indicare le ubicazioni incluse nello schema reverse charge. 

Per applicare l'IVA reverse charge, è necessario completare le seguenti impostazioni.

## <a name="set-up-sales-tax-codes"></a>Imposta i codici IVA
Si consiglia di utilizzare codici IVA separati per le operazioni di vendita e le operazioni di acquisto.

<table>
<body>
<tr>
<td><strong>Codice IVA per le vendite</strong></td>
<td>Creare un codice IVA per le operazioni di vendita in reverse charge (<strong>Imposta</strong> &gt; <strong>Imposte indirette</strong> &gt; <strong>IVA</strong> &gt; <strong>Codici IVA</strong>).
</td>
</tr>
<tr>
<td><strong>Codice IVA per gli acquisti</strong></td>
<td><p>Creare i codici IVA positivi e negativi per l'IVA in reverse charge per gli acquisti (<strong>Imposta</strong> &gt; <strong>Imposte indirette</strong> &gt; <strong>IVA</strong> &gt; <strong>Codici IVA</strong>).</p>
<ol>
<li>Creare un codice IVA con un valore positivo.</li>
<li>Creare un codice IVA con un valore negativo. Impostare l'opzione <strong>Consenti aliquota IVA negativa</strong> su <strong>Sì</strong>.
Il codice IVA negativo deve essere assegnato a una fascia IVA articoli, che verrà quindi assegnata agli articoli soggetti all'IVA in reverse charge.</li>
</ol>
<p>Per ulteriori informazioni, vedere la sezione successiva &quot;Impostare fasce IVA e fasce IVA articoli.&quot;</p>
</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a>Impostare fasce IVA e fasce IVA articoli
Si consiglia di utilizzare le fasce IVA separate per le operazioni di vendita e le operazioni di acquisto.

<table>
<tr>
<td><strong>Fasce IVA per le vendite</strong></td>
<td>Creare una fascia IVA per le operazioni di vendita con reverse charge (<strong>Imposta</strong> &gt; <strong>Imposte indirette</strong> &gt; <strong>IVA</strong> &gt; <strong>Fasce IVA</strong>). Nella scheda <strong>Impostazione</strong>, includere il codice IVA per il reverse charge di questa fascia. Selezionare le caselle di controllo <strong>Esente</strong> e <strong>Reverse charge</strong> per il codice IVA.</td>
</tr>
<tr>
<td><strong>Fasce IVA per gli acquisti</strong></td>
<td>Creare una fascia IVA per le operazioni di acquisto con reverse charge (<strong>Imposta</strong> &gt; <strong>Imposte indirette</strong> &gt; <strong>IVA</strong> &gt; <strong>Fasce IVA</strong>). Nella scheda <strong>Impostazione</strong>, includere i codici IVA negativi e positivi in questa fascia. Selezionare la casella di controllo <strong>Reverse charge</strong> per indicare che il codice IVA ha un valore negativo.</td>
</tr>
<tr>
<td><strong>Fasce IVA articoli</strong></td>
<td>Creare o aggiornare la fascia IVA articoli con il codice IVA che ha un valore negativo (<strong>Imposta</strong> &gt; <strong>Imposte indirette</strong> &gt; <strong>IVA</strong> &gt; <strong>Fasce IVA articoli</strong>). È necessario assegnare la fascia IVA articoli predefinita ai prodotti e alle categorie soggette a reverse charge.</td>
</tr>
</table>

## <a name="set-up-reverse-charge-groups"></a>Impostare i gruppi reverse charge
Nella pagina **Gruppi di articoli reverse charge** (**Imposta** &gt; **Impostazioni** &gt; **IVA** &gt; **Gruppi di articoli reverse charge**), è possibile definire i gruppi di prodotti o di servizi o prodotti o servizi singoli a cui è possibile applicare la reverse charge. Per ciascun gruppo di articoli soggetti a reverse charge, definire l'elenco di articoli, i gruppi di articoli e le categorie per le vendite e/o gli acquisti.

## <a name="set-up-reverse-charge-rules"></a>Impostare le regole reverse charge
Nella pagina **Regole reverse charge** (**Imposta** &gt; **Impostazioni** &gt; **IVA** &gt; **Regole reverse charge**), è possibile definire le regole di applicabilità per gli acquisti e le vendite. È possibile configurare un set di regole di applicabilità reverse charge. Per ciascuna regola, impostare i seguenti campi:

- **Tipo di documento** - Selezionare **Ordine fornitore**, **Giornale di registrazione fatture fornitore**, **Ordine cliente**, **Fattura a testo libero**, **Giornale di registrazione fatture cliente** e/o **Fattura fornitore**.
- **Tipo di paese partner** - Selezionare **Nazionale**, **UE** o **Straniero**. In alternativa, se la regola può essere applicata a tutti i partner commerciali, indipendentemente dal paese o dall'area dell'indirizzo, selezionare **Tutti**.
- **Indirizzo di consegna nazionale** - Selezionare questa casella di controllo per applicare la regola alle consegne all'interno dello stesso paese. Questa casella di controllo non può essere selezionata per i tipi  documento **Giornale di registrazione fatture cliente** e **Giornale di registrazione fatture fornitore**.
- **Gruppo di articoli reverse charge** - Selezionare il gruppo a cui può essere applicata la regola.
- **Importo soglia** - Lo schema reverse charge viene applicato a una fattura solo se il valore degli articoli e/o dei servizi inclusi nel gruppo di articoli soggetti a reverse charge supera il limite specificato in questo campo.

È inoltre possibile utilizzare i campi **Data di scadenza** e **Data di validità** per definire il periodo in cui la regola diventa valida.

Inoltre, è possibile specificare se una notifica viene visualizzata e la riga del documento viene aggiornata con la fascia IVA reverse charge predefinita se la condizione della riga del documento viene soddisfatta. Sono disponibili le seguenti opzioni:

- **Nessuno** - La riga del documento non viene aggiornata.
- **Richiesta** - Una notifica viene visualizzata per confermare che l'IVA reverse charge può essere applicata.
- **Imposta** - La riga del documento viene aggiornata senza ulteriore notifica.

## <a name="set-up-default-parameters"></a>Impostazione dei parametri predefiniti
Per attivare la funzionalità per l'IVA in reverse charge, nella pagina **Parametri di contabilità generale**, nella scheda **Reverse charge**, impostare l'opzione **Abilita reverse charge** su **Sì**. Nei campi **Fascia IVA ordine fornitore** e **Fascia IVA ordine cliente**, selezionare le fasce IVA predefinite. Quando una condizione di applicabilità del reverse charge viene soddisfatta, la riga ordine cliente o ordine fornitore viene aggiornata con queste fasce IVA.

## <a name="reverse-charge-on-a-sales-invoice"></a>Reverse charge su una fattura di vendita
Per le vendite effettuate con lo schema reverse charge, il venditore non addebita l'IVA. La fattura indica gli articoli soggetti a IVA reverse charge e l'importo totale dell'IVA reverse charge.

Quando una fattura di vendita viene registrata con la reverse charge, le transazioni IVA hanno il tipo di IVA **IVA a debito** e l'IVA pari a zero e la casella di controllo **Reverse charge** è selezionata.

## <a name="reverse-charge-on-a-purchase-invoice"></a>Reverse charge su una fattura di acquisto
Per gli acquisti nello schema reverse charge, l'acquirente che riceve la fattura con l'IVA reverse charge funge da acquirente e venditore per la contabilità dell'IVA.

Se una fattura di acquisto con l'IVA reverse charge viene registrata, due transazioni IVA vengono create. Una transazione ha il tipo di IVA **IVA a credito**. L'altra transazione ha il tipo di IVA **IVA a debito** e la casella di controllo **Reverse charge** è selezionata.

Nella schermata seguente, una transazione ha la direzione **IVA a credito** e un'altra transazione ha la direzione **IVA a debito**. 

![IVA registrata](media/apac-sau-posted-sales-tax.png)
