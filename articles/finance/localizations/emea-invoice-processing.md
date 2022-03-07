---
title: Elaborazione fattura
description: In questo argomento vengono fornite informazioni sull'elaborazione delle fatture per l'Europa orientale.
author: EvgenyPopovMBS
ms.date: 02/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, VendParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia, Italy
ms.author: epopov
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 9eb4f3ace8c6295e82ba9ab44ef49baa0d10e96b
ms.sourcegitcommit: 2aca3a95d42403c7f5d80dcd5e3ee958dca5c894
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2022
ms.locfileid: "8087817"
---
# <a name="invoice-processing"></a>Elaborazione fattura

[!include [banner](../includes/banner.md)]

Questo argomento descrive brevemente alcuni scenari specifici del paese, come l'imposta sul valore aggiunto (IVA) intracomunitaria e l'imposta differita. I requisiti legali per alcuni paesi europei influenzano il processo di fatturazione. Questo argomento fornisce anche informazioni su come vengono elaborate le fatture dei clienti e dei fornitori per questi paesi. 
<table>
<thead>
<tr>
<th>Scenario</th>
<th>Paesi</th>
<th>Descrizione delle modifiche della funzionalità</th>
</tr>
</thead>
<tbody>
<tr>
<td>Date di Contabilità fornitori e Contabilità clienti per IVA</td>
<td>Repubblica Ceca, Polonia</td>
<td>
<p>Quando le merci vengono acquistate da paesi dell'Unione Europea (UE), c'è l'obbligo di autovalutazione dell'IVA:</p>
<ul>
<li>L'IVA a debito deve essere pagata nel periodo IVA in cui è stata emessa la fattura (data del documento).</li>
<li>L'IVA a credito non può essere detratta prima del ricevimento del documento (data del registro IVA).</li>
</ul>
<p>Le seguenti impostazioni devono essere configurate per supportare questo scenario:</p>
<ul>
<li>Nella pagina <strong>Parametri contabilità fornitori</strong> abilitare i parametri <strong>IVA intracomunitaria</strong> e <strong>Data documento per IVA intracomunitaria</strong>.</li>
<li>Impostare due codici IVA, uno con una percentuale di IVA positiva e uno con una percentuale di IVA negativa.</li>
<li>Impostare una fascia IVA che include il codice IVA positiva e negativa. Per il codice IVA negativa, impostare il parametro <strong>IVA intracomunitaria</strong> su <strong>Sì</strong>.</li>
</ul>
<p>Dopo la corretta configurazione, gli acquisti avranno due transazioni IVA registrate:</p>
<ul>
<li>Una transazione positiva che ha una direzione di <strong>IVA a credito</strong> e una data del registro IVA che sia uguale alla data dalla pagina di registrazione della fattura.</li>
<li>Una transazione negativa che ha una direzione di <strong>IVA a debito</strong> e una data del registro IVA che sia uguale alla data del documento.</li>
</ul>
</td>
</tr>
<tr>
<td>Modificare una data del documento di vendita.</td>
<td>Tutti i paesi dell'Europa orientale</td>
<td><p>È possibile modificare il campo <strong>Data documento</strong> su una fattura di progetto. Questa data appare sulla fattura stampata.</p>
<p>C'è anche un campo <strong>Data documento</strong> nelle pagine <strong>Registrazione fattura</strong> e <strong>Fattura a testo libero</strong>. Dopo la registrazione di una fattura, la data del documento viene visualizzata nell'intestazione della fattura.</p>
</td>
</tr>
<tr>
<td>Data documento per tasso di cambio</td>
<td>Polonia, Ungheria, Repubblica Ceca, Italia</td>
<td>
<p>La legislazione prevede regole diverse per la selezione di tassi di cambio validi per le transazioni commerciali. Nel campo <strong>Data tasso di cambio</strong> nelle pagine <strong>Parametri contabilità clienti</strong> e <strong>Parametri contabilità fornitori</strong> è possibile selezionare la data da utilizzare per gli importi nel calcolo della valuta contabile sui documenti di acquisto e di vendita. Durante l'immissione dei dati, il sistema recupera il tasso di cambio per la transazione, in base a questo parametro.</p>
<blockquote>[!NOTE]<br>Per l'Italia, questa funzionalità è applicabile solo nel modulo Contabilità fornitori. Nei parametri della contabilità fornitori, un utente può selezionare <strong>Data registrazione</strong> o <strong>Data documento</strong> nel campo <strong>Data tasso di cambio</strong>.   </blockquote>
<blockquote><br>Quando si imposta il campo <strong>Data tasso di cambio</strong> su <strong>Data documento (solo per il commercio UE)</strong>, il sistema utilizza la fascia IVA. Per la fascia IVA, esiste un parametro <strong>Commercio UE</strong> nella scheda <strong>Generale</strong>. Se l'opzione <strong>Commercio UE</strong> è impostata su <strong>Sì</strong> per la fascia IVA e se questa fascia IVA esiste nell'intestazione del documento, il sistema recupera il tasso di cambio in base alla data del documento. Se l'opzione <strong>Commercio UE</strong> è impostata su <strong>No</strong> per questa fascia IVA, il sistema recupera il tasso di cambio in base alla data di registrazione del documento.</blockquote>
  <blockquote><br>Per la Polonia, nel modulo <strong>Contabilità clienti</strong>, è disponibile un altro valore <strong> Determinazione automatica della data</strong> di questo parametro. Se selezionata, il sistema seleziona automaticamente la prima data dalla data di registrazione della fattura, dalla data di vendita e dalle date di pagamento.</blockquote>
</td>
</tr>
<tr>
<td>Date commerciali, date del registro IVA e controllo della data di documenti e IVA</td>
<td>Polonia, Ungheria, Repubblica Ceca</td>
<td>
<p>La data di vendita e la data di entrata del documento sono obbligatorie per il report IVA:</p>
<ul>
<li>La data di vendita è la data di evasione della transazione nella contabilità clienti.</li>
<li>La data di entrata del documento è una data che dimostra diritti di reclamare la detrazione dell'IVA nella contabilità fornitori. Ogni documento ricevuto ha una data a fini del controllo.</li>
</ul>
<p>La funzionalità ungherese per le date di scadenza, la funzionalità ceca per le date di evasione e la funzionalità polacca per la data di registrazione dell'IVA includono il requisito per la dichiarazione fiscale che si basa su una data differente dalla data di registrazione.</p>
<p>Il campo <strong>Data registro IVA</strong> supporta questo requisito e appare in più di 20 pagine. Queste pagine includono giornali di registrazione, ordini cliente, ordini fornitore, fatture a testo libero, giornali di registrazione fatture fornitore e fatture di progetto. Quando si aggiornano o registrano i documenti, tutte le imposte vengono registrate con la data corrispondente del registro IVA e la data è inclusa nelle pagine quali le pagine dei giornali di registrazione fatture cliente e fornitore.</p>
<p>In particolare, per la Repubblica Ceca, il campo <strong>Data registro IVA</strong> può essere vuoto durante la registrazione, in caso di registrazione IVA posticipata. In caso contrario, il campo è obbligatorio e deve essere compilato.</p>
<p>I parametri di convalida della data possono essere impostati nella pagina <strong>Fasce IVA</strong>:</p>
<ul>
<li>I parametri <strong>Data di compilazione registro IVA</strong> e <strong>Compilazione data di vendita</strong> vengono utilizzati come metodo di compilazione predefinito per le date appropriate. Sono inoltre disponibili l'inserimento manuale e diversi metodi di immissione automatizzati.</li>
<li>Il campo <strong>Data di vendita obbligatoria</strong> indica se la data di vendita deve essere inserita prima che venga registrata una fattura di vendita.</li>
</ul>
<p>Nella pagina <strong>Transazioni registro IVA</strong> è possibile inserire date vuote per il registro IVA per le transazioni fiscali registrate.</p>
</td>
</tr>
<tr>
<td>Date del registro IVA che includono l'imposta differita</td>
<td>Ungheria</td>
<td>
<p>Le normative fiscali ungheresi richiedono che le fatture vengano create al momento dell'evasione o non oltre 15 giorni dopo l'evasione.</p>
<p>La data di evasione è la data in cui sono stati forniti i servizi ordinati o la data in cui gli articoli ordinati sono stati consegnati. Quando si aggiornano o si registrano i documenti, tutte le imposte vengono registrate utilizzando la data corrispondente del registro IVA e la data viene visualizzata nelle pagine pertinenti. Inoltre, le normative richiedono che l'IVA sulla fornitura continua di servizi, quali affitto, leasing, consulenza e riscaldamento, soddisfi i seguenti criteri:</p>
<ul>
<li>L'IVA deve essere registrata in un conto di contabilità generale dedicato alla data della fattura.</li>
<li>L'IVA deve essere trasferita dai conti speciali a un conto contabilità clienti IVA o a un conto fornitori e deve essere inclusa nella dichiarazione IVA alla data di scadenza.</li>
</ul>
<p>Per supportare questi requisiti, è possibile trasferire le registrazioni di contabilità generale al conto imposta differita in entrata e al conto imposta differita in uscita. Tuttavia, è necessario prima completare i seguenti prerequisiti:</p>
<ul>
<li>Impostare i conti contabilità clienti e fornitori IVA differita nei gruppi di registrazione contabile.</li>
<li>Abilitare il parametro <strong>IVA differita</strong> per le fasce IVA articolo.</li>
</ul>
</td>
</tr>
<tr>
<td>Data IVA obbligatoria</td>
<td>Polonia</td>
<td>
<p>È possibile richiedere che la data del registro IVA sia inclusa nei record delle transazioni di acquisto e vendita. Pertanto, la data del registro IVA può essere acquisita prima della registrazione di una transazione. Questa funzionalità consente di evitare di dover gestire più transazioni alla fine del periodo.</p>
<p>È possibile rendere il campo <strong>Data del registro IVA</strong> obbligatorio quando vengono registrate le transazioni cliente o fornitore. Per rendere obbligatorio questo campo, abilitare l'opzione <strong>Data IVA obbligatoria</strong> per il conto cliente o fornitore correlato.</p>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
