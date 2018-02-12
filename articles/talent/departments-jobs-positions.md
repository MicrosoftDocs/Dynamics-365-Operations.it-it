---
title: Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni
description: Reparti, mansioni e posizioni sono elementi organizzativi che vengono gestiti in Risorse umane. Questo argomento descrive le nozioni relative a questi elementi.
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent, Retail
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c61814fa4bc30cb6f6e5da74a13e5ab973706d5d
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="organize-your-workforce-using-departments-jobs-and-positions"></a>Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni

[!include[banner](includes/banner.md)]

[!include[retail name](includes/retail-name.md)]


Reparti, mansioni e posizioni sono elementi organizzativi che vengono gestiti in Risorse umane. Questo argomento descrive le nozioni relative a questi elementi. 

Il seguente esempio viene utilizzato per illustrare i concetti descritti in questo argomento.

|**Reparto**|**Posizione**|**Mansione**|
|---|---|---|
|**Vendite**|Manager vendite (Est)|Manager vendite|
|**Vendite**|Manager vendite (Ovest)|Manager vendite|
|**Vendite**|Manager vendite (Centro)|Manager vendite|
|**Contabilità**|Supervisore contabile|Direttore amministrativo|
|**Contabilità**|Contabilità A|Ragioniere|
|**Risorse umane**|Responsabile risorse umane (Est)|Responsabile risorse Umane|
|**Risorse umane**|Responsabile risorse umane (Ovest)|Responsabile risorse Umane|
|**Risorse umane**|Responsabile risorse umane (Centro)|Responsabile risorse Umane|

 
 <a name="departments"></a>Reparti
------------

Un reparto è un'unità operativa che rappresenta una categoria o un'area funzionale di un'organizzazione, responsabile di un'area specifica dell'organizzazione, ad esempio vendita o contabilità. Un reparto viene utilizzato per i report sulle aree funzionali e può avere responsabilità di profitti e perdite. Inoltre, un reparto può includere un gruppo di centri di costo. Le vendite, la contabilità e le risorse umane sono alcuni esempi di reparti in un'organizzazione.

## <a name="jobs-and-positions"></a>Mansioni e posizioni
Una mansione è una raccolta di attività e responsabilità proprie della persona assegnata alla mansione. Una posizione è una singola istanza di un processo. Le aree di responsabilità, le attività associate alla mansione, le funzioni lavorative, le competenze, le informazioni di formazione e i certificati necessari per una mansione vengono inoltre richiesti per le posizioni associate a una mansione.
### <a name="job-tasks"></a>Mansioni di lavoro

È possibile creare attività per una mansione che descrivono le attività di base che un lavoratore in una posizione per tale mansione deve completare. La stessa attività associata a una mansione può essere aggiunta a più mansioni e le posizioni di tali mansioni erediteranno tali attività. Esempi di attività di mansioni sono elencati nella seguente tabella.

<table>
<thead>
<tr class="header">
<th>Processo</th>
<th>Mansione di lavoro</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Manager vendite</td>
<td><ul>
<li><span class="input">Verifica-prestazioni</span>: verificare le prestazioni di ciascun venditore.</li>
<li><span class="input">Verifica-assenze</span>: approvare o rifiutare le richieste o le registrazioni di assenza di ciascun venditore.</li>
</ul></td>
</tr>
<tr class="even">
<td>Ragioniere</td>
<td><span class="input">Report-finanziario</span>: presentare report finanziari settimanali al responsabile finanziario.</td>
</tr>
</tbody>
</table>

### <a name="job-functions"></a>Funzioni lavorative

Le funzioni lavorative sono simili alle attività associate alle mansioni. Una funzione lavorativa descrive una o più attività, compiti o responsabilità assegnati a una mansione. Le funzioni lavorative possono essere assegnate alle mansioni e utilizzate per impostare e implementare le regole di idoneità per i piani di retribuzione. Esempi di funzioni di mansioni sono elencati nella seguente tabella.

| Processo           | Funzione lavorativa                                                |
|---------------|-------------------------------------------------------------|
| Manager vendite | Gestione-persone: gestire le persone di cui si è superiori.               |
| Ragioniere    | Revisione-finanziaria: gestire i dati finanziari per un insieme di conti. |

### <a name="job-types"></a>Tipi di processo

Utilizzare i tipi di mansione per classificare mansioni simili in categorie. I tipi di mansione, proprio come le funzioni lavorative, possono essere assegnati alle mansioni e utilizzati per impostare e implementare le regole di idoneità per i piani di retribuzione. Nel seguente elenco sono inclusi alcuni esempi di tipi di mansione:
-   A tempo pieno
-   A tempo parziale
-   Stipendio
-   Retribuzione oraria

### <a name="areas-of-responsibility"></a>Aree di responsabilità

Utilizzare le aree di responsabilità per indicare i ruoli di lavoro, i processi e i prodotti di cui un lavoratore in una posizione di tale mansione è responsabile. Un esempio di un'area di responsabilità per una mansione denominata "Ragioniere" potrebbe essere "Reporting finanziario per il prodotto A".

<a name="positions"></a>Posizioni
----------

Le posizioni sono un elemento importante del livello inferiore di una gerarchia organizzativa. Una posizione è una singola istanza di un processo. Ad esempio, la posizione "Manager vendite (Est") è solo una delle posizioni associate alla mansione "Manager vendite". Le posizioni esistono in un reparto e vengono assegnate ai lavoratori.
### <a name="position-creation-and-maintenance"></a>Creazione e gestione di posizioni

-   È possibile visualizzare lo storico delle modifiche al sistema relative alle posizioni in una pagina elenco di semplice accesso.
-   È possibile creare codici motivo che gli utenti possono selezionare quando creano o modificano posizioni.
-   È possibile creare tipi di azione dipendente e assegnare una sequenza numerica alle azioni dipendente.
-   È possibile impostare il flusso di lavoro in modo da poter richiedere l'approvazione per le aggiunte e le modifiche alle posizioni.

### <a name="position-duration"></a>Durata posizione

Ogni posizione è valida per un periodo di tempo. Tale periodo di tempo viene definito durata. Ad esempio, le posizioni estive possono avere una durata compresa tra il 1° maggio 2015 e il 31 agosto 2015.

### <a name="worker-assignments"></a>Assegnazioni lavoratori

Quando si assegna un lavoratore a una posizione, tale posizione viene coperta. È possibile assegnare i lavoratori a più posizioni, ma solo un lavoratore può essere assegnato a una posizione contemporaneamente.

### <a name="reporting-relationships"></a>Relazioni gerarchiche

Le posizioni sono elementi importanti del livello inferiore di una gerarchia organizzativa. Nel modulo Posizione è possibile specificare la posizione gerarchicamente superiore a una posizione. Quando si assegna un lavoratore a una posizione che ha una posizione superiore, viene creata una relazione gerarchica tra i lavoratori assegnati alle due posizioni. Ad esempio, la posizione “Ragioniere-A" risponde alla posizione superiore "Supervisore contabile". Kim Akers viene assegnata alla posizione “Supervisore contabile" e Sanjay Patel alla posizione “Ragioniere-A”. Ciò significa che Kim Akers è il superiore gerarchico di Sanjay Patel. 

Se l'organizzazione utilizza una gerarchia a matrice o un'altra gerarchia personalizzata, è possibile impostare i tipi di gerarchia delle posizioni e aggiungere le relazioni gerarchiche alle posizioni per ogni tipo di gerarchia impostata. Ad esempio, Lori Penor è una responsabile generale in Adventure Works e viene assegnata alla posizione "Responsabile generale". Lori gestisce lo sviluppo di un prodotto che viene utilizzato per eseguire la pulitura dei congegni meccanici. Lori ha bisogno dell'assistenza di un ragioniere per gli aspetti finanziari dello sviluppo del prodotto. Di conseguenza, ha assunto Sanjay Patel come proprio ragioniere. Sanjay risponde direttamente a Kim Akers, ma lavora anche con Lori Penor relativamente agli aspetti finanziari dello sviluppo del prodotto per la pulitura dei congegni. 

Per l'esempio precedente, vanno completate le seguenti attività per impostare la relazione di lavoro tra Sanjay Patel e Lori Penor:
1.  Creare un tipo di gerarchia di posizioni personalizzato, denominato "Congegni", per creare una gerarchia che include le posizioni responsabili per le attività sul prodotto per la pulitura dei congegni.
2.  Assegnare la posizione Responsabile generale come posizione superiore della posizione Ragioniere-A nella gerarchia Congegni.

Utilizzare la gerarchia di posizioni per visualizzare la struttura gerarchica delle posizioni. Se sono presenti più gerarchie di posizioni, è possibile visualizzare la gerarchia di ogni tipo nella gerarchia di posizioni. Inoltre, è possibile cercare una posizione in base all'ID posizione o al nome del lavoratore assegnato alla posizione. La gerarchia di posizioni è una gerarchia organizzativa.

## <a name="date-effective-records"></a>Record con date valide
Per alcuni record, è possibile specificare le modifiche future al record. Le seguenti informazioni sono correlate a una data di validità.

<table>
<thead>
<tr class="header">
<th>Record</th>
<th>Informazioni correlate a una data di validità</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Processi</td>
<td><ul>
<li>Alcune informazioni dettagliate sulla mansione</li>
<li>Informazioni sulla classificazione della mansione</li>
<li>Informazioni sulla retribuzione</li>
</ul></td>
</tr>
<tr class="even">
<td>Posizioni</td>
<td><ul>
<li>Alcune informazioni dettagliate sulla posizione</li>
<li>Assegnazioni dei lavoratori</li>
<li>Durate posizione</li>
<li>Gerarchie posizioni</li>
</ul></td>
</tr>
</tbody>
</table>

È possibile modificare le informazioni citate nella tabella precedente per una posizione o una mansione e specificare una data in cui le modifiche alla posizione o alla mansione devono essere rese effettive. Ad esempio, una posizione può essere assegnata solo a un lavoratore, ma Sanjay Patel, assegnato alla posizione Ragioniere-A, lascerà la società tra due settimane. Joe Healy sostituirà Sanjay Patel. Anche se Sanjay è ancora assegnato alla posizione, è possibile assegnare Joe Healy alla stessa posizione in modo che l'assegnazione sia valida solo dopo l'ultimo giorno di Sanjay.






