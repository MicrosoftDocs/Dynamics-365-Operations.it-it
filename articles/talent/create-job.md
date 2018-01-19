---
title: Impostazione dei componenti di una mansione
description: "In questo argomento sono descritti gli elementi concettuali che una mansione può includere e vengono forniti alcuni esempi di modalità di utilizzo di tali elementi nell'organizzazione."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.author: rschloma
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent, Retail
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 962b3084c5340813d1697cab680621350510d4b9
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="setting-up-the-components-of-a-job"></a>Impostazione dei componenti di una mansione

[!include[banner](includes/banner.md)]

[!include[retail name](includes/retail-name.md)]


In questo argomento sono descritti gli elementi concettuali che una mansione può includere e vengono forniti alcuni esempi di modalità di utilizzo di tali elementi nell'organizzazione. 

Per creare mansioni, è necessario impostare alcune informazioni sui riferimenti. È possibile creare una mansione con un solo nome. Tuttavia, includendo informazioni aggiuntive, ad esempio una qualifica, vengono forniti valori predefiniti per le posizioni assegnate alla mansione. Inoltre, alcune informazioni immesse possono essere utilizzate per filtrare i piani di retribuzione per mansioni specifiche. Se si desidera impostare l'idoneità da poter utilizzare per filtrare i piani di retribuzione per una mansione specifica, è necessario impostare i tipi di mansione e le funzioni lavorative prima delle mansioni. Se si dispone di questi valori predefiniti, l'aggiunta di posizioni alla mansione sarà più rapida. 

Alcuni dettagli della mansione, ad esempio la qualifica, il tipo e la funzione, dispongono di una data di validità. Se si crea una mansione ma questi dettagli vengono aggiunti in un secondo momento e si visualizza la mansione in base alla data di creazione, tali dettagli non saranno visibili. Di conseguenza, è opportuno creare alcune di queste informazioni di riferimento prima che siano necessarie. In tal modo, è possibile aggiungere le informazioni alle nuove mansioni quando vengono create.

## <a name="job-titles"></a>Qualifiche
Prima di creare posizioni lavorative, è necessario impostare titoli per tali posizioni. Le posizioni ereditano i titoli dalle mansioni a cui sono associate. 

Gestire le qualifiche utilizzando la pagina **Titoli**, che può essere aperta tramite la funzione di ricerca. Nella pagina **Titoli**, immettere i titoli che si prevede di utilizzare per le mansioni.

## <a name="job-types"></a>Tipi di posizione lavorativa
I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie. I tipi di mansione non sono obbligatori. Tuttavia, se si prevede di utilizzare i tipi di posizione lavorativa per impostare le regole di idoneità per la gestione della retribuzione, è consigliabile impostare i tipi di posizione lavorativa prima di impostare le posizioni lavorative. Alcuni esempi di tipi di mansione a tempo pieno e a tempo parziale o stipendio e retribuzione oraria. I tipi di mansione vengono gestiti mediante la pagina **Tipi di mansione**. Nella pagina **Tipi di mansione**, immettere un nome per una breve descrizione del tipo di mansione. Nel campo **Stato di esenzione**, selezionare una delle opzioni seguenti per indicare lo stato di esenzione FLSA (Fair Labor Standards Act) di mansioni che dispongono di questo tipo di mansione:

-   **Esente** - Le mansioni sono esenti dallo straordinario in base all'FLSA.
-   **Non esente** - Le mansioni non sono esenti dallo straordinario in base all'FLSA.
-   **Non applicabile** - La copertura FLSA non è applicabile.

## <a name="job-functions"></a>Funzioni lavorative
Le funzioni lavorative descrivono categorie funzionali di alto livello e correlano compiti di alto livello. Le funzioni lavorative non sono obbligatorie. È possibile utilizzare le funzioni lavorative, insieme ai tipi di mansione, per filtrare i piani di retribuzione in base a mansioni specifiche. Per associare tipi di mansione e funzioni lavorative ai piani di retribuzione, impostare le regole di idoneità nella pagina **Regole di idoneità**. È quindi possibile collegare un insieme di livelli a un piano di retribuzione applicabili alla specifica combinazione di un tipo di mansione e funzione lavorativa definita mediante una regola di idoneità. (Queste funzionalità si applicano ai piani di retribuzione sia fissa sia variabile). Tuttavia, se si prevede di utilizzare le funzioni lavorative per impostare le regole di idoneità per la gestione della retribuzione, è opportuno impostarle prima di impostare le mansioni. Nella tabella seguente sono riportati alcuni esempi di funzioni lavorative.

| Mansione           | Funzione lavorativa         |
|---------------|----------------------|
| Manager vendite | Responsabile di livello medio    |
| Ragioniere    | Professionisti        |

Le funzione lavorative vengono gestite mediante la pagina **Funzioni lavorative**. Nella pagina **Funzioni lavorative**, immettere un codice di identificazione e una breve descrizione della funzione lavorativa.

## <a name="job-tasks"></a>Mansioni di lavoro
Le mansioni di lavoro descrivono le attività di base che un lavoratore che ricopre una posizione per una mansione deve completare. La stessa mansione di lavoro può essere aggiunta a più mansioni e alle posizioni per le mansioni che utilizzano tali mansioni di lavoro. Nella tabella seguente sono riportati alcuni esempi di mansioni di lavoro.

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
<li><strong>Verifica-prestazioni</strong>: verificare le prestazioni di ciascun venditore.</li>
<li><strong>Verifica-assenze</strong>: approvare o rifiutare le richieste o le registrazioni di assenza di ciascun venditore.</li>
</ul></td>
</tr>
<tr class="even">
<td>Ragioniere</td>
<td><strong>Report-finanziario</strong>: presentare report finanziari settimanali al responsabile finanziario.</td>
</tr>
</tbody>
</table>

Le mansioni di lavoro vengono gestite mediante la pagina **Mansioni di lavoro**. Nella pagina **Mansioni di lavoro**, immettere un nome per una breve descrizione della mansione di lavoro. Nel campo **Nota** è possibile immettere informazioni aggiuntive. Le note possono essere aggiornate per una mansione specifica senza modificare le note immesse in questo campo.

## <a name="areas-of-responsibility"></a>Aree di responsabilità
Le aree di responsabilità vengono utilizzate per indicare i ruoli di lavoro, i processi e i prodotti di cui un lavoratore in una posizione per una mansione è responsabile. Ad esempio, per una mansione denominata "Ragioniere", un'area di responsabilità potrebbe essere "Reporting finanziario per il prodotto A". Le aree di responsabilità vengono gestite mediante la pagina **Aree di responsabilità**, individuabile tramite la funzione di ricerca. Nella pagina **Aree di responsabilità**, immettere un nome e una descrizione della responsabilità. Nel campo **Nota** è possibile immettere informazioni aggiuntive. Le note possono essere aggiornate per una mansione specifica senza modificare le note immesse in questo campo.




