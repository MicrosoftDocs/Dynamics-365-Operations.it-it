---
title: Corsi di formazione di impostazione
description: "Gli amministratori e gli amministratori delle Risorse umane possono utilizzare le funzionalità dei corsi per gestire le informazioni sulla formazione offerta ai lavoratori."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6f4429202efd0506378d681188035c5cc69f56a1
ms.openlocfilehash: aa97950a22572fb4c934687b550c13dcc8acce0d
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-training-courses"></a>Corsi di formazione di impostazione

Gli amministratori e gli amministratori delle Risorse umane possono utilizzare le funzionalità dei corsi per gestire le informazioni sulla formazione offerta ai lavoratori.

 <a name="set-up-prerequisites"></a> Prerequisiti per l'impostazione
---------------------

Le seguenti informazioni sono obbligatorie e devono essere impostate prima di creare i corsi.
-   **Tipi di corso**

Le seguenti informazioni necessarie da specificare per i corsi sono facoltative. Se queste informazioni verranno fornite per i corsi, è necessario impostarle prima di creare i record del corso.
-   **Gruppi di classi**
-   **Gruppi del corso**
-   **Sedi del corso**
-   **Classi**
-   **Istruttori**

## <a name="course-types"></a>Tipi di corso
È possibile utilizzare i tipi di corso per classificare i corsi in base alla struttura o al contenuto del corso. È possibile creare i tipi di corso nella pagina **Tipi di corso**. È necessario selezionare un tipo di corso quando si crea un record del corso.

## <a name="course-setup-type"></a>Tipo di impostazione del corso
Vengono di seguito elencati i tre tipi di impostazione per i corsi. I tipi di installazione determinano la struttura del corso.

<table>
<thead>
<tr class="header">
<th>Tipo di impostazione</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Standard</strong></td>
<td>Selezionare questo tipo per i corsi che non avranno un ordine del giorno giornaliero. Quando si crea un nuovo corso sarà il tipo di impostazione predefinito.</td>
</tr>
<tr class="even">
<td><strong>Agenda</strong></td>
<td>Selezionare qesto tipo per pianificare i dettagli di ogni giorno di un corso di più giorni.</td>
</tr>
<tr class="odd">
<td><strong>Agenda + sessione</strong></td>
<td>Selezionare il tipo per i corsi più complessi. Ad esempio, è possibile suddividere l'ordine del giorno per il corso in tracce e sessioni.
<ul>
<li><strong>Traccia</strong>: le tracce sono argomenti specifici per un corso.</li>
<li><strong>Sessioni</strong>: le sessioni vengono divise in tracce e possono trattare processi o tecniche specifici attinenti a ciascuna traccia.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a>Attività del corso
Per ogni corso, è possibile effettuare le seguenti attività.
-   Registrare i partecipanti
-   Specificare una scadenza per la registrazione
-   Definire il numero minimo e massimo di partecipanti
-   Assegnare una sede del corso e una classe
-   Hotel consigliati per i partecipanti al corso
-   Creare una descrizione del corso che potrà essere pubblicizzata su Dipendente self-service

  >** Nota ** è possibile eliminare un corso solo se nessuna registrate. 
    
## <a name="course-statuses"></a>Stati del corso
Nella seguente tabella sono elencati gli stati possibili del corso e le azioni che è possibile completare quando il corso ha uno stato specifico.

<table>
<thead>
<tr class="header">
<th>Stato</th>
<th>Azioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Creato</strong></td>
<td><ul>
<li>Immettere e modificare le informazioni sul corso.</li>
<li>Modificare lo stato del corso in <strong>Aperto</strong> in modo da poter registrare i lavoratori per il corso.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Aperto</strong></td>
<td><ul>
<li>Registrare i partecipanti per il corso.</li>
<li>Rimuovere i partecipanti dal corso.</li>
<li>Confermare i partecipanti per il corso.</li>
<li>Modificare lo stato del corso su<strong> Chiuso</strong> o <strong>Annullato</strong>.</li>
<li>Pianificare i questionari per i partecipanti a cui è assegnato lo stato <strong>Confermato</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Chiuso</strong></td>
<td>È possibile riaprire il corso.</td>
</tr>
<tr class="even">
<td><strong>Annullato</strong></td>
<td>È possibile riaprire il corso.</td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a>Partecipanti al corso
I partecipanti a un corso sono i dipendenti, i candidati o i contatti che prendono parte a un evento o a un corso di formazione. È possibile registrare solo i partecipanti ai corsi aperti. Il numero minimo e massimo di partecipanti che è possibile registrare per un corso viene definito nella scheda dettaglio **Generale** sulla pagina **Corsi**.

<a name="workflow"></a>Flusso di lavoro
--------

I dipendenti registrati per un corso ** tramite Self Service dipendenti ** la pagina possono disporre dei instradati registrazione tramite il flusso di lavoro per l'approvazione.  Può essere assegnato a un corso ** dettagli relativi all'identificazione ** clic ** ** corsi nella pagina.



