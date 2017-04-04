---
title: Impostazione dei componenti del processo
description: "In questo argomento sono descritti gli elementi riportati di un processo può includere e vengono forniti alcuni esempi di utilizzo gli elementi dell&quot;organizzazione."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: d96b1f01a5cb4370436888deae8fd4835a0dbb80
ms.openlocfilehash: b8143db5b133337603a7f2f46028d91bb81cd947
ms.lasthandoff: 03/31/2017


---

# <a name="setting-up-the-components-of-a-job"></a>Impostazione dei componenti del processo

In questo argomento sono descritti gli elementi riportati di un processo può includere e vengono forniti alcuni esempi di utilizzo gli elementi dell'organizzazione. 

Per poter creare posizioni lavorative, è necessario impostare alcune informazioni di riferimento. È possibile creare una posizione lavorativa con un solo conto. Tuttavia, includendo informazioni aggiuntive, ad esempio una qualifica, vengono immessi valori predefiniti per le posizioni assegnate al processo. Inoltre, alcune informazioni immesse possono essere utilizzate per filtrare i piani retribuzione per posizioni lavorative specifiche. Se si desidera impostare idoneità in cui è possibile filtrare i piani di retribuzione a un processo specifico, è necessario impostare le funzioni lavorative e i tipi di posizione lavorativa prima di impostare le posizioni lavorative. Avendo questi valori predefiniti disponibili, salverete l'ora in cui è possibile aggiungere le posizioni al processo. 

Alcuni dettagli di processo, ad esempio la qualifica, il tipo e funzione di validità, sono valide. Se si crea una posizione lavorativa attualmente ma non aggiungere i dettagli fino a successivamente quindi pubblicate manualmente il processo a partire dalla data di creazione, i dettagli non verrà visualizzata. Di conseguenza, è necessario creare alcune informazioni di riferimento la prima che si. Tale modo, è possibile aggiungere informazioni ai nuovi processi quando vengono create.

## <a name="job-titles"></a>Qualifiche
Prima di creare posizioni lavorative, è necessario impostare titoli per tali posizioni. Le posizioni ereditano i titoli dalle mansioni a cui sono associate. 

Gestire le qualifiche utilizzando ** titoli ** della pagina, che può essere aperto tramite la funzione di ricerca. ** Titoli ** nella pagina, immettere i titoli che si prevede di utilizzare per i processi.

## <a name="job-types"></a>Tipi di posizione lavorativa
I tipi di processo per raggruppare posizioni lavorative simili in categorie. I tipi di posizione lavorativa non sono obbligatori. Tuttavia, se si prevede di utilizzare i tipi di posizione lavorativa per impostare le regole di idoneità per la gestione della retribuzione, è consigliabile impostare i tipi di posizione lavorativa prima di impostare le posizioni lavorative. Alcuni esempi di tipi di processo a tempo pieno e a tempo parziale, o lo stipendio e retribuzione oraria. Vengono gestite mediante i tipi di processo mediante ** tipi di posizione lavorativa ** la pagina. ** Il processo in ** nella pagina, immettere un nome e una breve descrizione del tipo di processo. In ** stato di esenzione ** sistemi, selezionare una delle opzioni seguenti per indicare lo stato di esenzione di (FLSA) consente di base predefinito di lavoro dei processi con questo tipo:

-   ** ** - I processi non sono esenti dallo straordinario in base all'FLSA.
-   ** ** i processi Non esenti non sono esenti dallo straordinario in base all'FLSA.
-   ** Non applicabile ** la copertura FLSA non è applicabile.

## <a name="job-functions"></a>Funzioni lavorative
Le giunzioni dei processi vengono descritte le categorie funzionali a livello principale e alle funzioni di livello superiore. Le funzioni lavorative non sono obbligatorie. È possibile utilizzare le funzioni lavorative, insieme ai tipi di processo, per filtrare i piani retribuzione per posizioni lavorative specifiche. È possibile associare le funzioni lavorative e i tipi di processo ai piani di retribuzione impostando regole di idoneità ** regole di idoneità ** nella pagina. È quindi possibile collegare un insieme di livelli a un piano di retribuzione applicabili alla specifica combinazione di tipo e di funzione lavorativa definita mediante una regola di idoneità. (Queste funzionalità si applicano sia ai piani di retribuzione fissa per i piani di retribuzione variabile). Tuttavia, se si prevede di utilizzare le funzioni lavorative per impostare le regole di idoneità per la gestione della retribuzione, è consigliabile impostare le funzioni lavorative prima di impostare le posizioni lavorative. Nella seguente tabella sono riportati alcuni esempi di funzioni lavorative.

| Mansione           | Funzione lavorativa      |
|---------------|-------------------|
| Manager vendite | Gestore livello medio |
| Ragioniere    | Professionisti     |

Vengono gestite mediante le funzioni lavorative utilizzando ** funzioni lavorative ** la pagina. ** Funzioni lavorative ** nella pagina, immettere un codice di identificazione e una breve descrizione della funzione lavorativa.

## <a name="job-tasks"></a>Mansioni di lavoro
Le mansioni di lavoro vengono descritte le attività di base che un lavoratore in un'ubicazione per un processo deve completare. La stessa attività di processo può essere aggiunti a più posizioni e alle ubicazioni per le posizioni lavorative che utilizzano tali attività di processo. Nella seguente tabella sono riportati alcuni esempi di attività di processo.

<table>
<thead>
<tr class="header">
<th>Mansione</th>
<th>Mansione di lavoro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Manager vendite</td>
<td><ul>
<li><strong>Perforazione- revisione</strong> - Consente di visualizzare il rendimento di lavoro per ogni venditore.</li>
<li><strong>ABS- revisione</strong> Consente di approvare o rifiutare richieste o le registrazioni delle assenze applicate da ciascun fornitore.</li>
</ul></td>
</tr>
<tr class="even">
<td>Ragioniere</td>
<td><strong>Aletta-report</strong> - Report finanziari settimanali inviare al responsabile finanziario.</td>
</tr>
</tbody>
</table>

Vengono gestite mediante le attività di processo mediante ** mansioni di lavoro ** la pagina. ** Mansioni di lavoro ** nella pagina, immettere un nome e una descrizione per la mansione di lavoro. In ** nota ** sistemi, è possibile scegliere di immettere le informazioni aggiuntive. Le note possono essere aggiornate per uno specifico processo senza modificare le note immesse in questo campo.

## <a name="areas-of-responsibility"></a>Aree di responsabilità
È possibile utilizzare le aree di responsabilità per indicare i ruoli di lavoro, i processi e i prodotti che un lavoratore in un'ubicazione per un processo è responsabile del sistema. Ad esempio, per un processo denominato "," contabile un'area di responsabilità può essere "report finanziari per il prodotto A". Vengono gestite mediante le aree di responsabilità utilizzando ** aree di responsabilità ** la pagina, che è possibile trovare utilizzando la funzione di ricerca. ** Aree di responsabilità ** nella pagina, immettere un nome e una descrizione della responsabilità. In ** nota ** sistemi, è possibile scegliere di immettere le informazioni aggiuntive. Le note possono essere aggiornate per uno specifico processo senza modificare le note immesse in questo campo.


