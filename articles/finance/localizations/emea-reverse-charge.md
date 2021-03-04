---
title: Meccanismo di reverse charge per schema IVA/GST
description: In questo argomento viene descritto come configurare l'imposta sul valore aggiunto (IVA) in reverse charge per i paesi europei, l'Arabia Saudita e Singapore.
author: epodkolz
manager: AnnBe
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom, Singapore, Bahrain, Kuwait, Oman, Qatar
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 247bc64bf0b90a641ead8a21971a6043691762fa
ms.sourcegitcommit: f12ce34cc08cf1fa205c67f48669ea9a6566b526
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "4515052"
---
# <a name="reverse-charge-mechanism-for-vatgst-scheme"></a>Meccanismo di reverse charge per schema IVA/GST

[!include [banner](../includes/banner.md)]

Questo argomento descrive un approccio generico per l'impostazione della funzionalità di reverse charge per paesi/aree geografiche che adottano gli schemi IVA o GST.
                                                                                 
La disponibilità della funzionalità nel paese/area geografica è gestita dalle seguenti funzionalità nell'area di lavoro **Gestione funzionalità**.

| Funzionalità                                              | Paese/area geografica                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nessuna funzionalità specifica                                | Austria </br>Belgio </br>Bulgaria </br>Croazia </br>Cipro </br>Repubblica Ceca </br>Danimarca  </br>Estonia  </br>Finlandia  </br>Francia  </br>Germania  </br>Ungheria  </br>Islanda  </br>Irlanda  </br>Italia  </br>Lettonia  </br>Liechtenstein  </br>Lituania  </br>Lussemburgo  </br>Paesi Bassi  </br>Norvegia Polonia </br>Portogallo </br>Romania  </br>Arabia Saudita </br>Singapore  </br>Slovacchia  </br>Slovenia  </br>Spagna  </br>Svezia  </br>Svizzera  </br>Regno Unito  </br>Emirati Arabi Uniti |
| Reverse charge per altri paesi            | Bahrein  </br>Kuwait  </br>Oman  </br>Qatar                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Abilitare il meccanismo di reverse charge per schema IVA/GST | Tutti gli altri paesi/aree geografiche tranne:  </br>Brasile  </br>India  </br>Russia                                                                                                                                                                                                                                                                                                                                                                                         |
 
 Per ulteriori informazioni, vedere la sezione [Abilitare il meccanismo di reverse charge per la funzionalità schema IVA/GST](#enable-reverse-charge) più avanti in questo argomento.

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

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><a name="sales-tax-item-sales-tax-groups"></a>Impostare fasce IVA e fasce IVA articoli
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

## <a name="set-up-reverse-charge-item-groups"></a><a name="reverse-charge-item-group"></a>Impostare i gruppi di articoli di reverse charge
Nella pagina **Gruppi di articoli reverse charge** (**Imposta** &gt; **Impostazioni** &gt; **IVA** &gt; **Gruppi di articoli reverse charge**), è possibile definire i gruppi di prodotti o di servizi o prodotti o servizi singoli a cui è possibile applicare la reverse charge. Per ciascun gruppo di articoli soggetti a reverse charge, definire l'elenco di articoli, i gruppi di articoli e le categorie per le vendite e/o gli acquisti.

## <a name="set-up-reverse-charge-rules"></a><a name="reverse-charge-rules"></a>Impostare le regole reverse charge
Nella pagina **Regole reverse charge** (**Imposta** &gt; **Impostazioni** &gt; **IVA** &gt; **Regole reverse charge**), è possibile definire le regole di applicabilità per gli acquisti e le vendite. È possibile configurare un set di regole di applicabilità reverse charge. Per ciascuna regola, impostare i seguenti campi:

- **Tipo di documento** - Selezionare **Ordine fornitore**, **Giornale di registrazione fatture fornitore**, **Ordine cliente**, **Fattura a testo libero**, **Giornale di registrazione fatture cliente** e/o **Fattura fornitore**.
- **Tipo di paese/area geografica partner** – Selezionare **Nazionale**, **UE**, **GCC** o **Straniero**. In alternativa, se la regola può essere applicata a tutti i partner commerciali, indipendentemente dal paese o dall'area dell'indirizzo, selezionare **Tutti**.
- **Indirizzo di consegna nazionale** - Selezionare questa casella di controllo per applicare la regola alle consegne all'interno dello stesso paese. Questa casella di controllo non può essere selezionata per i tipi documento **Giornale di registrazione fatture cliente** e **Giornale di registrazione fatture fornitore**.
- **Gruppo di articoli reverse charge** - Selezionare il gruppo a cui può essere applicata la regola.
- **Importo soglia** - Lo schema reverse charge viene applicato a una fattura solo se il valore degli articoli e/o dei servizi inclusi nel gruppo di articoli soggetti a reverse charge supera il limite specificato in questo campo.

È inoltre possibile utilizzare i campi **Data di scadenza** e **Data di validità** per definire il periodo in cui la regola diventa valida.

Inoltre, è possibile specificare se una notifica viene visualizzata e la riga del documento viene aggiornata con la fascia IVA reverse charge predefinita se la condizione della riga del documento viene soddisfatta. Sono disponibili le seguenti opzioni:

- **Nessuno** - La riga del documento non viene aggiornata.
- **Richiesta** - Una notifica viene visualizzata per confermare che l'IVA reverse charge può essere applicata.
- **Imposta** - La riga del documento viene aggiornata senza ulteriore notifica.

## <a name="set-up-countryregion-properties"></a><a name="Set-up-Country/region-properties"></a>Impostare le proprietà del paese/area geografica
Nella pagina **Parametri per il commercio estero** ( **Imposta** &gt; **Impostazione** &gt; **Imposta sulle vendite** &gt; **Commercio estero** &gt; **Parametri per il commercio estero**), nella scheda **Proprietà paese/area geografica** impostare il paese o l'area geografica della persona giuridica corrente su *Nazionale*. Impostare il **tipo di paese/area geografica** dei paesi/aree geografiche UE che partecipano al commercio UE con la persona giuridica corrente su *UE*. Impostare il **tipo di paese/area geografica** dei paesi/aree geografiche GCC che partecipano al commercio GCC con la persona giuridica corrente su *GCC*.

## <a name="set-up-default-parameters"></a>Impostazione dei parametri predefiniti
Per attivare la funzionalità per l'IVA in reverse charge, nella pagina **Parametri di contabilità generale**, nella scheda **Reverse charge**, impostare l'opzione **Abilita reverse charge** su **Sì**. Nei campi **Fascia IVA ordine fornitore** e **Fascia IVA ordine cliente**, selezionare le fasce IVA predefinite. Quando una condizione di applicabilità del reverse charge viene soddisfatta, la riga ordine cliente o ordine fornitore viene aggiornata con queste fasce IVA.

## <a name="reverse-charge-on-a-sales-invoice"></a><a name="reverse-charge-sale"></a>Reverse charge su una fattura di vendita
Per le vendite effettuate con lo schema reverse charge, il venditore non addebita l'IVA. La fattura indica gli articoli soggetti a IVA reverse charge e l'importo totale dell'IVA reverse charge.

Quando una fattura di vendita viene registrata con la reverse charge, le transazioni IVA hanno il tipo di IVA **IVA a debito** e l'IVA pari a zero e le caselle di controllo **Reverse charge** e **Esente** sono selezionate.

## <a name="reverse-charge-on-a-purchase-invoice"></a><a name="reverse-charge-purchase"></a>Reverse charge su una fattura di acquisto
Per gli acquisti nello schema reverse charge, l'acquirente che riceve la fattura con l'IVA reverse charge funge da acquirente e venditore per la contabilità dell'IVA.

Se una fattura di acquisto con l'IVA reverse charge viene registrata, due transazioni IVA vengono create. Una transazione ha il tipo di IVA **IVA a credito**. L'altra transazione ha il tipo di IVA **IVA a debito** e la casella di controllo **Reverse charge** è selezionata.

Nella schermata seguente, una transazione ha la direzione **IVA a credito** e un'altra transazione ha la direzione **IVA a debito**. 

![IVA registrata](media/apac-sau-posted-sales-tax.png)

## <a name="enable-reverse-charge-mechanism-for-vatgst-scheme-feature"></a><a name="enable-reverse-charge"></a>Abilitare il meccanismo di reverse charge per la funzionalità schema IVA/GST
Nell'area di lavoro **Gestione funzionalità** trovare la funzionalità e selezionare **Abilita**.

Dopo aver abilitato la funzionalità, la scheda **Reverse charge** è disponibile in tutte le persone giuridiche. Abilitare la funzionalità Reverse charge per una persona giuridica impostando l'opzione **Abilita reverse charge** su **Sì**.

Saranno disponibili le seguenti pagine e voci di menu relative all'impostazione della funzionalità:
 - **Gruppi di articoli reverse charge** (**Imposta** > **Impostazione** > **IVA** > **Gruppi di articoli reverse charge**). Per ulteriori informazioni, vedere la sezione [Impostare i gruppi di articoli di reverse charge](#reverse-charge-item-group).
 - **Regole reverse charge** (**Imposta** > **Impostazione** > **IVA** > **Regole reverse charge**). Vedere [Impostare le regole reverse charge](#reverse-charge-rules).
 - **Parametri per il commercio estero** (**Imposta** > **Impostazione** > **IVA** > **Commercio estero** > **Parametri per il commercio estero**). Vedere [Impostare le proprietà del paese/area geografica](#Set-up-Country/region-properties).

La casella di controllo **Reverse charge** sarà disponibile nelle pagine **Gruppo IVA** e **IVA registrata**. Per ulteriori informazioni, vedere le sezioni [Impostare fasce IVA e fasce IVA articoli](#sales-tax-item-sales-tax-groups), [Reverse charge su una fattura di vendita](#reverse-charge-sale) e [Reverse charge su una fattura di acquisto](#reverse-charge-purchase).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]