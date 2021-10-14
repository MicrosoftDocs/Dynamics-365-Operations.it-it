---
title: Associazioni di controllo qualità
description: In questo argomento viene descritto come utilizzare le associazioni di controllo qualità in Microsoft Dynamics 365 Supply Chain Management per generare automaticamente ordini di controllo qualità relativi ai processi di vendita, acquisto e produzione.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28984730e5660414eec1ba087eb5de1eba4cbbb8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571931"
---
# <a name="quality-associations"></a>Associazioni di controllo qualità

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come utilizzare le associazioni di controllo qualità in Microsoft Dynamics 365 Supply Chain Management per generare automaticamente ordini di controllo qualità relativi ai processi di vendita, acquisto e produzione.

Un'associazione di controllo qualità definisce le seguenti informazioni per un ordine di controllo qualità generato:

- L'evento della transazione
- Il set di test che devono essere eseguiti sugli articoli
- Livello di qualità accettabile (AQL)
- Il piano di campionamento

Occorre definire un'associazione di controllo qualità per ogni variazione in un processo aziendale che richieda la generazione automatica di un ordine di controllo qualità. Ad esempio, è possible generare un ordine di controllo qualità nei processi aziendali per ordini acquisto, ordini di quarantena, ordini cliente e ordini di produzione.

## <a name="working-with-quality-associations"></a>Utilizzo delle associazioni di controllo qualità

Il processo aziendale che utilizza un'associazione di controllo qualità può essere correlato a diversi documenti di origine come ordini acquisto, ordini cliente o ordini di produzione.

Ciascun record di associazione di controllo qualità definisce il set di test, l'AQL e il piano di campionamento da applicare agli ordini di controllo qualità generati. Un record di un'associazione di controllo qualità deve essere definito per ogni variazione in un processo aziendale. Ad esempio, è possibile impostare un'associazione di controllo qualità che generi un ordine di controllo qualità quando si aggiorna l'entrata prodotti di un ordine acquisto. A seconda della configurazione del piano di esecuzione, il processo di attivazione stesso può essere bloccato mentre c'è un ordine di controllo qualità aperto. In alternativa, è possibile bloccare i processi successivi, come la fatturazione degli ordini fornitore.

> [!NOTE]
> Mentre vi sono ordini di controllo qualità aperti, le quantità di inventario sono automaticamente bloccate. A seconda dell'impostazione di **Blocco completo** nella pagina **Campionamenti articoli**, la quantità è la quantità dell'ordine di controllo qualità o la quantità della riga di documento di origine. Per ulteriori informazioni, vedere [Campionamento degli articoli per la gestione della qualità](quality-item-sampling.md).

Per un processo aziendale specificato, il record di un'associazione di controllo qualità identifica l'evento e le condizioni per cui viene generato un ordine di controllo qualità. Le condizioni possono essere specifiche a un sito o a una persona giuridica. Un ordine di controllo qualità che prevede test distruttivi può essere generato solo quando sono disponibili delle scorte per l'evento.

Per lavorare con associazioni di controllo qualità, vai a **Gestione articoli \> Impostazioni \> Controllo qualità \> Associazioni di controllo qualità**. Negli esempi riportati di seguito viene illustrata la modalità di definizione di un record di associazione di controllo qualità per le variazioni in ciascun processo aziendale. Per ciascun esempio, sono riepilogati nella seguente tabella gli eventi e le condizioni definiti da un record di associazione di controllo qualità.

<table>
<thead>
<tr>
<th>Tipo di riferimento</th>
<th>Tipo di evento</th>
<th>Esecuzione</th>
<th>Bloccaggio evento</th>
<th>Riferimento documento</th>
</tr>
</thead>
<tbody>
<tr>
<td>Inventario</td>
<td>Non applicabile</td>
<td>Non applicabile</td>
<td>Nessuno</td>
<td>Tutti</td>
</tr>
<tr>
<td rowspan="7">Vendite</td>
<td rowspan="4">Il processo di prelievo è programmato</td>
<td rowspan="4">Prima</td>
<td>Nessuno</td>
<td rowspan="22">Solo ID specifico, Gruppo o Tutto</td>
</tr>
<tr>
<td>Processo di prelievo</td>
</tr>
<tr>
<td>Documento di trasporto</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="3">Documento di trasporto</td>
<td rowspan="3">Prima</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Documento di trasporto</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="15">Acquisto</td>
<td rowspan="7">Elenco entrate</td>
<td rowspan="4">Prima</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Elenco entrate</td>
</tr>
<tr>
<td>Entrata prodotti</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="3">Dopo</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Entrata prodotti</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="3">Registrazione</td>
<td rowspan="3">Non applicabile</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Entrata prodotti</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="5">Entrata prodotti</td>
<td rowspan="3">Prima</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Entrata prodotti</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="2">Dopo</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="8">Produzione</td>
<td rowspan="3">Registrazione</td>
<td rowspan="3">Non applicabile</td>
<td>Nessuno</td>
<td rowspan="12">Tutti</td>
</tr>
<tr>
<td>Dichiarato finito</td>
</tr>
<tr>
<td>Fine periodo</td>
</tr>
<tr>
<td rowspan="5">Dichiarato finito</td>
<td rowspan="3">Prima</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Dichiarato finito</td>
</tr>
<tr>
<td>Fine periodo</td>
</tr>
<tr>
<td rowspan="2">Dopo</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Fine periodo</td>
</tr>
<tr>
<td rowspan="4">Quarantena</td>
<td rowspan="3">Dichiarato finito</td>
<td rowspan="2">Prima</td>
<td>Dichiarato finito</td>
</tr>
<tr>
<td>Fine periodo</td>
</tr>
<tr>
<td>Dopo</td>
<td>Fine periodo</td>
</tr>
<tr>
<td>Fine periodo</td>
<td>Prima</td>
<td>Fine periodo</td>
</tr>
<tr>
<td rowspan="3">Operazione ciclo di lavorazione</td>
<td rowspan="3">Dichiarazione di finito</td>
<td rowspan="2">Prima di</td>
<td>Nessuna priorità</td>
<td rowspan="3">ID specifico, Gruppo o Tutti e Specifico risorsa, Gruppo o Tutti</td>
</tr>
<tr>
<td>Dichiarazione di finito</td>
</tr>
<tr>
<td>Dopo</td>
<td>Nessuna priorità</td>
</tr>
<tr>
<td rowspan="3">Produzione co-prodotti</td>
<td>Registrazione</td>
<td>Non applicabile</td>
<td rowspan="3">Nessuna priorità</td>
<td rowspan="3">Tutti</td>
</tr>
<tr>
<td rowspan="2">Dichiarazione di finito</td>
<td>Prima di</td>
</tr>
<tr>
<td>Dopo</td>
</tr>
</tbody>
</table>

> [!NOTE]
> La funzionalità *Gestione qualità per i processi di magazzino* aggiunge funzionalità per l'elaborazione degli ordini di controllo qualità per la produzione con **Tipo di evento** impostato su *Dichiarato finito* e **Esecuzione** impostato su *Dopo* e per acquisti con **Tipo di evento** impostato su *Registrazione*. Per ulteriori informazioni, vedere [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md).

Nella tabella seguente vengono fornite ulteriori informazioni sulla modalità di generazione di ordini di controllo qualità per tipi specifici di processo.

<div class="tableSection">
<table>
<thead>
<tr>
<th>Tipo di processo</th>
<th>Quando gli ordini di controllo qualità possono essere generati automaticamente</th>
<th>Quando gli ordini di controllo qualità possono essere generati se il test distruttivo è obbligatorio</th>
<th>Informazioni sulle condizioni</th>
<th>Informazioni sulla generazione manuale</th>
</tr>
</thead>
<tbody>
<tr>
<td>Ordine fornitore</td>
<td>Prima o dopo la registrazione di un elenco di entrate o un'entrata prodotti per il materiale ricevuta</td>
<td>Dopo che l'entrata prodotti per il materiale ricevuto viene registrata, poiché il materiale deve essere disponibile per il test distruttivo</td>
<td>La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un fornitore specifico o una combinazione di questi.</td>
<td>Un ordine di controllo qualità generato manualmente che si riferisce a un ordine fornitore può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</td>
</tr>
<tr>
<td>Ordine di quarantena</td>
<td>Prima o dopo che l'ordine di quarantena viene dichiarato finito o completato</td>
<td>Gli ordini di controllo qualità che richiedono i test distruttivi non possono essere generati. Si presume che la funzionalità di ordine di quarantena gestisca lo smaltimento del materiale distrutto.</td>
<td>La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un fornitore specifico o una combinazione di questi.</td>
<td>Un ordine di controllo qualità generato manualmente che si riferisce a un ordine di quarantena può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</td>
</tr>
<tr>
<td>Ordine cliente</td>
<td>Prima di un processo di prelievo o un aggiornamento del documento di trasporto per gli articoli in spedizione</td>
<td>In qualsiasi fase</td>
<td>La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un cliente specifico o una combinazione di questi.</td>
<td>Un ordine di controllo qualità generato manualmente che si riferisce a un ordine cliente può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</td>
</tr>
<tr>
<td>Ordine di produzione</td>
<td>Prima o dopo la registrazione della quantità finita per l'ordine di produzione</td>
<td>Dopo la registrazione della quantità finita per l'ordine di produzione</td>
<td>La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo specifico o una combinazione di questi.</td>
<td>Un ordine di controllo qualità generato manualmente che si riferisce a un ordine di produzione può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</td>
</tr>
<tr>
<td>Ordine di produzione che ha un'operazione del ciclo di lavorazione</td>
<td>Prima o dopo che il report venga completato per un'operazione</td>
<td>Dopo la dichiarazione della fine dell'ultima operazione di produzione</td>
<td>La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o una risorsa operativa specifica o una combinazione di questi elementi.</td>
<td>Un ordine di controllo qualità generato manualmente che si riferisce a un'operazione del ciclo di lavorazione può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</td>
</tr>
<tr>
<td>Scorte</td>
<td>Un ordine di controllo qualità non può essere generato automaticamente per una transazione in un giornale di registrazione magazzino o per le transazioni degli ordini di trasferimento.</td>
<td></td>
<td></td>
<td>Un ordine di controllo qualità deve essere creato manualmente per la quantità in magazzino di un articolo. Scorte fisiche disponibili è un campo obbligatorio.</td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Esempi di generazione automatica di ordini di controllo qualità

### <a name="purchasing"></a>Acquisto

Se durante l'acquisto, si imposta il campo **Tipo di evento** su *Entrata prodotti* e il campo **Esecuzione** su *Dopo* nella pagina **Associazioni di controllo qualità**, saranno disponibili i seguenti risultati:

- Se l'opzione **Per quantità aggiornata** è impostata su *Sì*, viene generato un ordine di controllo qualità per ogni entrata dell'ordine fornitore, in base alla quantità ricevuta e alle impostazioni nel campionamento articoli. Ogni volta che una quantità viene ricevuta per l'ordine fornitore, nuovi ordini di controllo qualità vengono generati in base alla quantità ricevuta.
- Se l'opzione **Per quantità aggiornata** è impostata su *No*, viene generato un ordine di controllo qualità per la prima entrata dell'ordine fornitore, in base alla quantità ricevuta. Inoltre, uno o più ordini di controllo qualità vengono creati in base alla quantità rimanente e alle dimensioni di tracciabilità. Gli ordini di controllo qualità non vengono generati per le entrate successive dell'ordine fornitore.

### <a name="production"></a>Produzione

Se durante la produzione, si imposta il campo **Tipo di evento** su *Dichiarato finito* e il campo **Esecuzione** su *Dopo* nella pagina **Associazioni di controllo qualità**, saranno disponibili i seguenti risultati:

- Se l'opzione **Per quantità aggiornata** è impostata su *Sì*, viene generato un ordine di controllo qualità in base a ogni quantità finita e alle impostazioni nel campionamento articoli. Ogni volta che una quantità viene dichiarata come finita per l'ordine di produzione, nuovi ordini di controllo qualità vengono generati in base alla quantità finita. La logica di generazione è coerente con l'acquisto.
- Se l'opzione **Per quantità aggiornata** è impostata su *No*, viene generato un ordine di controllo qualità la prima volta che una quantità viene dichiarata come finita, in base alla quantità finita. Inoltre, uno o più ordini di controllo qualità vengono creati in base alla quantità rimanente e alle dimensioni di tracciabilità del campionamento articoli. Gli ordini di controllo qualità non vengono generati per le successive quantità finite.

<table>
<thead>
<tr>
<th>Specifica qualità</th>
<th>Per quantità aggiornata</th>
<th>Per dimensione di tracciabilità</th>
<th>Risultato</th>
</tr>
</thead>
<tbody>
<tr>
<td>Percentuale: 10%</td>
<td>Sì</td>
<td>
<p>Numero batch: No</p>
<p>Numero di serie: No</p>
</td>
<td>
<p>Quantità ordine: 100</p>
<ol>
<li>Dichiarazione di finito per 30
<ul>
<li>Ordine di controllo qualità 1 per 3 (10% di 30)</li>
</ul>
</li>
<li>Dichiarazione di finito per 70
<ul>
<li>Ordine di controllo qualità 2 per 7 (10% della quantità rimanente dell'ordine, che equivale a 70 in questo caso)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Quantità fissa: 1</td>
<td>Nessuno</td>
<td>
<p>Numero batch: No</p>
<p>Numero di serie: No</p>
</td>
<td>Quantità ordine: 100
<ol>
<li>Dichiarazione di finito per 30
<ul>
<li>L'ordine di controllo qualità 1 per 1 (per la prima quantità dichiarata finita, con un valore fisso di 1)</li>
<li>L'ordine di controllo qualità 2 per 1 (per la quantità rimanente che ha ancora un valore fisso di 1)</li>
</ul>
</li>
<li>Dichiarazione di finito per 10
<ul>
<li>Nessun ordine di controllo qualità viene creato.</li>
</ul>
</li>
<li>Dichiarazione di finito per 60
<ul>
<li>Nessun ordine di controllo qualità viene creato.</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Quantità fissa: 1</td>
<td>Sì</td>
<td>
<p>Numero batch: Sì</p>
<p>Numero di serie: Sì</p>
</td>
<td>
<p>Quantità ordine: 10</p>
<ol>
<li>Dichiara come finito per 3: 1 per il numero di lotto b1, numero di serie s1; 1 per numero di lotto b2, numero di serie s2; e 1 per il numero di lotto b3, numero di serie s3
<ul>
<li>Ordine di controllo qualità 1 per 1 del numero di lotto b1, numero di serie s1</li>
<li>Ordine di controllo qualità 2 per 1 del numero di lotto b2, numero di serie s2</li>
<li>Ordine di controllo qualità 3 per 1 del numero di lotto b3, numero di serie s3</li>
</ul>
</li>
<li>Dichiara come finito per 2: 1 per il numero di lotto b4, numero di serie s4; e 1 per il numero di lotto b5, numero di serie s5
<ul>
<li>Ordine di controllo qualità 4 per 1 del numero di lotto b4, numero di serie s4</li>
<li>Ordine di controllo qualità 5 per 1 del numero di lotto b5, numero di serie s5</li>
</ul>
</li>
</ol>
<p><strong>Nota:</strong> il batch può essere riutilizzato.</p>
</td>
</tr>
<tr>
<td>Quantità fissa: 2</td>
<td>Nessuno</td>
<td>
<p>Numero batch: Sì</p>
<p>Numero di serie: Sì</p>
</td>
<td>
<p>Quantità ordine: 10</p>
<ol>
<li>Dichiara come finito per 4: 1 per il numero di lotto b1, numero di serie s1; 1 per numero di lotto b2, numero di serie s2; 1 per il numero di lotto b3, numero di serie s3: e 1 per il numero di lotto b4, numero di serie s4
<ul>
<li>Ordine di controllo qualità 1 per 1 del numero di lotto b1, numero di serie s1</li>
<li>Ordine di controllo qualità 2 per 1 del numero di lotto b2, numero di serie s2</li>
<li>Ordine di controllo qualità 3 per 1 del numero di lotto b3, numero di serie s3</li>
<li>Ordine di controllo qualità 4 per 1 del numero di lotto b4, numero di serie s4</li>
</ul>
<ul>
<li>Ordine di controllo qualità 5 per 2, senza riferimento a un numero di lotto o un numero di serie</li>
</ul>
</li>
<li>Dichiara come finito per 6: 1 per il numero di lotto b5, numero di serie s5; 1 per numero di lotto b6, numero di serie s6; 1 per il numero di lotto b7, numero di serie s7; 1 per il numero di lotto b8, numero di serie s8; 1 per il numero di lotto b9, numero di serie s9: e 1 per il numero di lotto b10, numero di serie s10
<ul>
<li>Nessun ordine di controllo qualità viene creato.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Risorse aggiuntive

- [Processi di gestione qualità](quality-management-processes.md)
- [Abilitare la gestione della qualità e della non conformità](enable-quality-management.md)
- [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
