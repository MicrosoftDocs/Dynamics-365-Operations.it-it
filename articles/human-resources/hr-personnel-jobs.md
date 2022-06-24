---
title: Impostare i componenti di una mansione
description: In questo articolo sono descritti gli elementi concettuali che una mansione può includere e vengono forniti alcuni esempi di modalità di utilizzo di tali elementi nell'organizzazione.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle, HcmPersonnelManagementWorkspace, HCMJobFamily
audience: Application User
ms.author: twheeloc
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: afe100879a4f83e4ef16048bc4b1acace19b679b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877716"
---
# <a name="set-up-the-components-of-a-job"></a>Impostare i componenti di una mansione


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

In questo articolo sono descritti gli elementi concettuali che una mansione può includere e vengono forniti alcuni esempi di modalità di utilizzo di tali elementi nell'organizzazione. 

Per creare mansioni, è necessario impostare alcune informazioni sui riferimenti. È possibile creare una mansione con un solo nome. Tuttavia, includendo informazioni aggiuntive, ad esempio una qualifica, vengono forniti valori predefiniti per le posizioni assegnate alla mansione. Inoltre, alcune informazioni immesse possono essere utilizzate per filtrare i piani di retribuzione per mansioni specifiche. Se si desidera impostare l'idoneità da poter utilizzare per filtrare i piani di retribuzione per una mansione specifica, è necessario impostare i tipi di mansione e le funzioni lavorative prima delle mansioni. Se si dispone di questi valori predefiniti, l'aggiunta di posizioni alla mansione sarà più rapida. 

Alcuni dettagli della mansione, ad esempio la qualifica, il tipo e la funzione, dispongono di una data di validità. Se si crea una mansione ma questi dettagli vengono aggiunti in un secondo momento e si visualizza la mansione in base alla data di creazione, tali dettagli non saranno visibili. Di conseguenza, è opportuno creare alcune di queste informazioni di riferimento prima che siano necessarie. In tal modo, è possibile aggiungere le informazioni alle nuove mansioni quando vengono create.

## <a name="job-titles"></a>Qualifiche
Prima di creare posizioni lavorative, è necessario impostare titoli per tali posizioni. Le posizioni ereditano i titoli dalle mansioni a cui sono associate. 

Gestire le qualifiche utilizzando la pagina **Titoli**, che può essere aperta tramite la funzione di ricerca. Nella pagina **Titoli** immettere i titoli che si intende utilizzare per le mansioni.

## <a name="job-types"></a>Tipi di lavoro
I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie. I tipi di mansione non sono obbligatori. Tuttavia, se si prevede di utilizzare i tipi di posizione lavorativa per impostare le regole di idoneità per la gestione della retribuzione, è consigliabile impostare i tipi di posizione lavorativa prima di impostare le posizioni lavorative. Alcuni esempi di tipi di mansione a tempo pieno e a tempo parziale o stipendio e retribuzione oraria. I tipi di mansione vengono gestiti mediante la pagina **Tipi di mansione**. Nella pagina **Tipi di mansione**, immettere un nome per una breve descrizione del tipo di mansione. Nel campo **Stato di esenzione**, selezionare una delle opzioni seguenti per indicare lo stato di esenzione FLSA (Fair Labor Standards Act) di mansioni che dispongono di questo tipo di mansione:

-   **Esente** - Le mansioni sono esenti dallo straordinario in base all'FLSA.
-   **Non esente** - Le mansioni non sono esenti dallo straordinario in base all'FLSA.
-   **Non applicabile** - La copertura FLSA non è applicabile.

## <a name="job-family"></a>Famiglia di processo
Una famiglia di mansioni è un gruppo di mansioni che implicano lavori, formazione, competenze, conoscenze ed esperienze simili. Una famiglia di mansioni può essere collegata a una mansione nella Scheda dettaglio **Classificazione mansione** della pagina **Mansioni** e nella Scheda dettaglio **Generale** della pagina **Tutte le posizioni**. Le famiglie di mansioni possono essere ampie o specifiche a seconda dei requisiti aziendali e di creazione report. Alcuni esempi di famiglie di mansioni ampie sono **Manodopera specializzata** e **Manodopera non specializzata**. Alcuni esempi di famiglie di mansioni specifiche sono **Contabilità**,**Produzione** e **Vendite**.

Gestire le famiglie di mansioni utilizzando la pagina **Famiglia di mansioni**, che è possibile aprire utilizzando la funzione di ricerca. Nella pagina **Famiglia di mansioni** immettere un nome univoco per la famiglia, quindi immettere una descrizione dettagliata che si intende utilizzare per le proprie mansioni.

## <a name="job-functions"></a>Funzioni di lavoro
Le funzioni lavorative descrivono categorie funzionali di alto livello e correlano compiti di alto livello. Le funzioni lavorative non sono obbligatorie. È possibile utilizzare le funzioni lavorative, insieme ai tipi di mansione, per filtrare i piani di retribuzione in base a mansioni specifiche. Per associare tipi di mansione e funzioni lavorative ai piani di retribuzione, impostare le regole di idoneità nella pagina **Regole di idoneità**. È quindi possibile collegare un insieme di livelli a un piano di retribuzione applicabili alla specifica combinazione di un tipo di mansione e funzione lavorativa definita mediante una regola di idoneità. (Queste funzionalità si applicano ai piani di retribuzione sia fissa sia variabile). Tuttavia, se si prevede di utilizzare le funzioni lavorative per impostare le regole di idoneità per la gestione della retribuzione, è opportuno impostarle prima di impostare le mansioni. Nella tabella seguente sono riportati alcuni esempi di funzioni lavorative.

| Mansione           | Funzione lavorativa         |
|---------------|----------------------|
| Manager vendite | Responsabile di livello medio    |
| Ragioniere    | Professionisti        |

Le funzione lavorative vengono gestite mediante la pagina **Funzioni lavorative**. Nella pagina **Funzioni lavorative**, immettere un codice di identificazione e una breve descrizione della funzione lavorativa.

## <a name="compensation"></a>Retribuzione
Per assegnare un piano di retribuzione fissa a un dipendente con una determinata posizione, è necessario impostare livelli di retribuzione. Il **livello di retribuzione** viene utilizzato quando gli importi minimo, medio e massimo sono impostati in una struttura retributiva (griglia retributiva). Quando viene creato un piano di retribuzione fisso, viene selezionata la struttura retributiva. La struttura retributiva comprende anche il livello retributivo. Quando si seleziona un piano di retribuzione fissa per un dipendente, i livelli di retribuzione disponibili per la selezione dipendono dalla mansione a cui è associata la posizione del dipendente. Per ulteriori informazioni sull'impostazione della retribuzione, vedere [Piani di retribuzione](hr-compensation-overview.md).

## <a name="job-skills"></a>Competenze mansione
Le competenze mansione descrivono le abilità necessarie per svolgere un lavoro. Un livello di competenza deve essere associato a ogni abilità della mansione. I livelli di competenze sono definiti dall'utente. Indicano il livello di conoscenza o competenza richiesto. Ad esempio, le aziende potrebbero impostare livelli numerici, ad esempio da 1 a 5, dove **1** indica un principiante e **5** indica un esperto. In alternativa, le aziende potrebbero impostare livelli etichettati **Principiante**, **Intermedio** o **Esperto**. Dopo aver impostato il livello di competenza, è anche possibile impostare l'importanza della competenza. Ad esempio, se a un contabile è richiesta una conoscenza approfondita di Microsoft Excel, è possibile creare una competenza di nome **Conoscenza di Excel**. Il livello di competenza può quindi essere impostato su **Intermedio** e l'importanza può essere impostata su **Maggiore**.

Le competenze di una mansione possono essere utilizzate nel mapping delle competenze. Il mapping delle competenze può confrontare il set di competenze richiesto per una mansione e le competenze associate a un lavoratore. Può quindi determinare una corrispondenza percentuale, in base alle competenze sovrapposte. Per informazioni sul mapping delle competenze, vedere [Configurare le competenze](hr-develop-skills.md). 

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
<td>Contabile</td>
<td><strong>Report-finanziario</strong>: presentare report finanziari settimanali al responsabile finanziario.</td>
</tr>
</tbody>
</table>

Le mansioni di lavoro vengono gestite mediante la pagina **Mansioni di lavoro**. Nella pagina **Mansioni di lavoro**, immettere un nome per una breve descrizione della mansione di lavoro. Nel campo **Nota** è possibile immettere informazioni aggiuntive. Le note possono essere aggiornate per una mansione specifica senza modificare le note immesse in questo campo.

## <a name="areas-of-responsibility"></a>Aree di responsabilità
Le aree di responsabilità vengono utilizzate per indicare i ruoli di lavoro, i processi e i prodotti di cui un lavoratore in una posizione per una mansione è responsabile. Ad esempio, per una mansione denominata "Ragioniere", un'area di responsabilità potrebbe essere "Reporting finanziario per il prodotto A". Le aree di responsabilità vengono gestite mediante la pagina **Aree di responsabilità**, individuabile tramite la funzione di ricerca. Nella pagina **Aree di responsabilità**, immettere un nome e una descrizione della responsabilità. Nel campo **Nota** è possibile immettere informazioni aggiuntive. Le note possono essere aggiornate per una mansione specifica senza modificare le note immesse in questo campo.

## <a name="steps-for-creating-a-job"></a>Passaggi per creare un processo
Fare riferimento all'articolo [Definire nuovi processi](./hr-personnel-define-jobs.md) per la procedura dettagliata relativa alla creazione di un nuovo processo. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
