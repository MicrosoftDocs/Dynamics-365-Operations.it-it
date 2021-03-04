---
title: Piani di retribuzione
description: I responsabili di benefit e retribuzione possono utilizzare la gestione della retribuzione per gestire ed elaborare i piani di retribuzione fissa e variabile per i dipendenti dell'organizzazione.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b6dd163b0e956624eb57fa031b918a94609f9cfa
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419156"
---
# <a name="compensation-plans"></a>Piani di retribuzione

I responsabili di benefit e retribuzione possono utilizzare la gestione della retribuzione per gestire ed elaborare i piani di retribuzione fissa e variabile per i dipendenti dell'organizzazione.

### <a name="introduction"></a>Introduzione

La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base. La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa. È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile. 

I dipendenti possono essere iscritti a uno o più piani di entrambi i tipi. Un dipendente deve soddisfare i seguenti requisiti per poter essere iscritto a un piano di retribuzione:
-   L'assegnazione di posizione del dipendente deve essere attiva.
-   Il dipendente deve soddisfare i criteri definiti dai criteri di idoneità per un determinato piano di retribuzione.

## <a name="compensation-setup"></a>Configurazione della retribuzione
La seguente tabella elenca le componenti del processo di retribuzione che possono essere chiamate in causa durante la configurazione dei piani di retribuzione aziendali.

<table>
<thead>
<tr class="header">
<th>Componente</th>
<th>Ulteriori informazioni...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Azioni retribuzione fissa</td>
<td>Le azioni di retribuzione fissa hanno due scopi:
<ul>
<li>Le azioni possono specificare il tipo di informazioni che deve essere registrato quando una retribuzione dipendente cambia. Ad esempio, è possibile richiedere che il motivo una modifica, ad esempio una promozione o una retrocessione, venga registrato.</li>
<li>Le azioni possono assicurare che un calcolo venga applicato durante l'elaborazione dei piani di retribuzione fissa.  Ad esempio, le azioni di tipo capitale netto confrontano la retribuzione dei dipendenti con il punto di riferimento minimo per il livello del dipendente e garantiscono al dipendente almeno la retribuzione minima.</li>
</ul></td>
</tr>
<tr class="even">
<td>Livelli</td>
<td>I livelli sono associati alle mansioni e a qualsiasi posizione correlata a una mansione. È possibile creare livelli distinti per i tre tipi di piani di retribuzione: Grado, Fascia e Passaggio.</td>
</tr>
<tr class="odd">
<td>Matrice utilizzo range retributivo</td>
<td>Le matrici utilizzo range retributivo consentono di trasferire i dipendenti nel punto di controllo per le rispettive mansioni. Si può ricorrere all'utilizzo del range retributivo anche per verificare l'omogeneità delle tariffe all'interno della società, indipendentemente dal rendimento di un singolo dipendente o dalle prestazioni complessive della società. Ad esempio, i dipendenti che ricevono basse retribuzioni nell'ambito del proprio range retributivo potrebbero ottenere aumenti percentuali maggiori rispetto ai dipendenti che ricevono retribuzioni più elevate nell'ambito del range retributivo stesso. In questo modo, è possibile compensare sistematicamente le differenze. L'utilizzo del range retributivo viene calcolato nel modo seguente: (frequenza di retribuzione fissa - range retributivo minimo) ÷ (range retributivo massimo - range retributivo minimo).</td>
</tr>
<tr class="even">
<td>Impostazioni punti di riferimento</td>
<td>La configurazione dei punti di riferimento comprende un insieme di punti di riferimento che rappresentano i range retributivi all'interno di una matrice. Ciascun range retributivo può essere associato a una tariffa retributiva. Ad esempio, i piani del grado avranno spesso punti di riferimento di minimo, punto intermedio e massimo.</td>
</tr>
<tr class="odd">
<td>Matrice di retribuzione</td>
<td>Una matrice di retribuzione è un insieme di punti di riferimento e di livelli utilizzato per creare una struttura retributiva.</td>
</tr>
<tr class="even">
<td>Struttura retributiva</td>
<td>Una struttura retributiva è una matrice di incremento retributivo che presenta range retributivi associati alle tariffe retributive.</td>
</tr>
<tr class="odd">
<td>Regole di idoneità</td>
<td>Le regole di idoneità vengono utilizzate per identificare i dipendenti nell'ambito di specifici processi, funzioni lavorative, tipi di processo, reparti, sindacati o Paesi di retribuzione coperte da piani di retribuzione specifici. È necessario creare le regole di idoneità sia per la variabile che i piani di retribuzione fissa per iscrivere i dipendenti al piano. Dopo avere specificato le regole di idoneità per un piano di retribuzione, sarà possibile definire i livelli del piano che dovranno essere applicati alle mansioni coperte dal piano.</td>
</tr>
<tr class="even">
<td>Frequenze retribuzione</td>
<td>Le frequenze di retribuzione vengono utilizzate per definire il periodo per il quale è specificata la retribuzione.  Ad esempio, la frequenza di retribuzione aiuta a comprendere se l'importo della retribuzione viene specificato come retribuzione annuale anziché come tariffa di retribuzione oraria. Le frequenze di retribuzione sono inoltre utilizzate per impostare i fattori di conversione che consentono di convertire gli importi retributivi da frequenze di retribuzione mensile, settimanale, bisettimanale e oraria in una frequenza di retribuzione annua.</td>
</tr>
<tr class="odd">
<td>Paesi di retribuzione</td>
<td>I Paesi di retribuzione vengono utilizzati per specificare la retribuzione dipendente in base all'ubicazione del luogo di lavoro.</td>
</tr>
<tr class="even">
<td>Punto di controllo</td>
<td>Il punto di controllo definisce ciò che si considera essere la tariffa ideale per tutti i dipendenti inclusi in un livello retributivo. Nelle strutture retributive scalari, i punti di controllo corrispondono in genere al punto medio dei singoli range. Le strutture "a fascia" utilizzano raramente i punti di controllo. È possibile specificare il punto di controllo di un piano di retribuzione fissa nel modulo Piani di retribuzione fissa.</td>
</tr>
<tr class="odd">
<td>Funzioni lavorative</td>
<td>Le funzioni lavorative vengono utilizzate per classificare e filtrare i piani di retribuzione nei processi specifici.</td>
</tr>
<tr class="even">
<td>Tipi di processo</td>
<td>I tipi di processo vengono utilizzati per classificare e filtrare i piani di retribuzione nei processi specifici.</td>
</tr>
<tr class="odd">
<td>Tipi di retribuzione variabile</td>
<td>I tipi di retribuzione variabile, ad esempio un premio in azioni o una gratifica in contanti, vengono impostati nei piani di retribuzione variabile.</td>
</tr>
<tr class="even">
<td>Griglie retributive</td>
<td>Le griglie retributive contengono la struttura retributiva.  Le griglie retributive possono essere utilizzate da uno o più piani di retribuzione.</td>
</tr>
<tr class="odd">
<td>Piani prestazioni</td>
<td>I piani prestazioni sono utilizzati per associare le prestazioni a una matrice di allocazione, in modo tale da poter utilizzare il piano in una strategia di retribuzione basata sulla produttività.</td>
</tr>
<tr class="even">
<td>Valutazioni delle prestazioni</td>
<td>Le valutazioni delle prestazioni sono utilizzate nei piani prestazioni per stabilire l'importo di un premio di merito o di un premio produttività.</td>
</tr>
</tbody>
</table>

## <a name="process-events"></a>Eventi processo
Gli eventi processo consentono di calcolare le informazioni sulle retribuzioni in un periodo specifico per tutti i dipendenti iscritti a uno o più piani di retribuzione fissa o variabile. È possibile eseguire ripetutamente un evento processo per effettuare il test o l'aggiornamento dei risultati retributivi calcolati.

<a name="compensation-events"></a>Eventi retributivi
-------------------

Ogni volta che viene eseguito un evento processo, viene creato un evento retribuzione.  Gli eventi retribuzione contengono i risultati del processo retributivo per ciascun dipendente incluso nell'evento processo.  Quando i calcoli sono corretti, è possibile caricare l'evento retribuzione per aggiornare le voci relative alla retribuzione per i dipendenti interessati dall'evento processo.

## <a name="recommendations"></a>Suggerimenti
Dopo aver eseguito un evento processo, è possibile suggerire correzioni dell'aumento per merito o dell'importo del premio di un dipendente, in base alle linee guida calcolate per l'evento processo. Per proporre suggerimenti relativi ai dipendenti, è necessario abilitare i suggerimenti quando si impostano i piani di retribuzione o l'evento processo.





[!INCLUDE[footer-include](../includes/footer-banner.md)]