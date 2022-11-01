---
title: Panoramica dei corsi
description: Questo articoli spiega come gli amministratori e i responsabili di risorse umane possono utilizzare le funzionalità dei corsi per gestire le informazioni sui corsi disponibili per i lavoratori.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a1fd00fb9feea9ab426f67095770389696452215
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2022
ms.locfileid: "9716337"
---
# <a name="courses-overview"></a>Panoramica dei corsi

Microsoft Dynamics 365 Human Resources fornisce una soluzione per le esigenze di apprendimento della tua organizzazione. Questa soluzione offre due percorsi di apprendimento: *virtuale* e *guidato da istruttore*.

*Apprendimento virtuale* è un'esperienza di apprendimento che viene migliorata attraverso risorse online. In *training con docente*, un istruttore facilita una sessione di formazione per un gruppo di lavoratori o studenti.

Nel nostro modulo di apprendimento, i professionisti delle risorse umane, gli amministratori, i responsabili della formazione e i manager possono creare e assegnare entrambi i percorsi di apprendimento ai lavoratori.

> [!NOTE]
> Per utilizzare i corsi virtuali, è necessario abilitare la funzionalità **Miglioramenti al corso** in Gestione funzionalità.

## <a name="set-up-virtual-courses"></a>Configurare i corsi virtuali

Per configurare i corsi virtuali, è necessario abilitare la funzionalità **Miglioramenti al corso** in Gestione funzionalità. Vai a **Corsi \> Nuovo** e imposta l'opzione **Virtuale** su **Sì**. Dopo aver abilitato la funzionalità, è necessario un collegamento al corso. Il campo **Stato corso** verrà impostato su **Aperto**. L'opzione **Consenti al dipendente di autoregistrarsi** sarà impostata su **Sì** ma può essere impostata su **No**.

Dopo aver abilitato la funzionalità **Miglioramenti del corso** in Gestione funzionalità, si verificano le seguenti modifiche:

- È necessario definire una data di scadenza per l'assegnazione del corso.
- È necessario un collegamento al corso.
- **Dipendente self-servicei** mostrerà una panoramica dei dipendenti in **Corsi**. L'utente può visualizzare i corsi scaduti, in scadenza e assegnati.
- I lavoratori possono completare corsi virtuali e autocertificarli.

## <a name="set-up-instructor-led-courses"></a>Configurare corsi guidati da istruttore

I corsi guidati dall'istruttore non devono essere configurati prima di essere utilizzati.

Le seguenti informazioni sono facoltative e possono essere specificate per i corsi. Se queste informazioni verranno inserite per i corsi, dovrebbero essere configurate prima della creazione dei record del corso:

- Tipo di corso
- Gruppi di classi
- Gruppi del corso
- Sedi del corso
- Classi
- Istruttori
- Tipi di corso

È possibile utilizzare i *tipi di corso* per classificare i corsi in base alla loro struttura o al contenuto. È possibile creare i tipi di corso nella pagina  **Tipi di corso** .

Il numero minimo e massimo di partecipanti che è possibile registrare per un corso viene definito nella scheda dettaglio  **Generale**  sulla pagina  **Corsi** .

### <a name="course-setup-type"></a>Tipo di impostazione del corso 

I *tipi di configurazione* determinano la struttura del corso. Esistono tre tipi di configurazione per i corsi.

| Tipo di configurazione | Description |
|------|--------|
| Standard | I corsi di questo tipo di configurazione non hanno un'agenda giornaliera. Quando si crea un nuovo corso sarà il tipo di impostazione predefinito. |
| Agenda | Selezionare qesto tipo di configurazione per pianificare i dettagli di ogni giorno di un corso di più giorni. |
| Agenda + sessione | <p>Seleziona questo tipo di configurazione per i corsi più complessi. Ad esempio, è possibile suddividere l'ordine del giorno per il corso in *tracce* e *sessioni*.</p><ul><li>Le *tracce* sono argomenti specifici per un corso.</li><li>*Sessioni*: vengono divise in tracce e possono trattare processi o tecniche specifici attinenti a ciascuna traccia.</li></ul> |

### <a name="course-tasks"></a>Attività del corso

Per ogni corso, completa le seguenti attività:

- Registra i partecipanti.
- Specifica una scadenza per la registrazione.
- Definisci il numero minimo e massimo di partecipanti.
- Assegna una sede del corso e una classe.
- Hotel consigliati per i partecipanti al corso.
- Crea una descrizione del corso che potrà essere pubblicata su  **Self-service dipendenti**.

> [!NOTE]
> È possibile eliminare un corso solo se nessuno vi si è registrato.

### <a name="course-statuses"></a>Stati del corso

La tabella seguente elenca gli stati del corso e le azioni completate per ciascuno.

| Status | Azioni |
|------|--------|
| Creata | <ul><li>Immettere e modificare le informazioni sul corso.</li><li>Modificare lo stato del corso in  **Aperto** in modo da poter registrare i lavoratori per il corso.</li></ul> | 
| Apri | <ul><li>Registrare i partecipanti per il corso.</li><li>Rimuovere i partecipanti dal corso.</li><li>Confermare i partecipanti per il corso.</li><li>Modifica lo stato del corso in  **Chiuso**  o  **Annullato** per i partecipanti il cui stato è  **Confermato**.</li></ul>|
| Chiuso | È possibile riaprire il corso. |
| Annullata | È possibile riaprire il corso. |

### <a name="course-participants"></a>Partecipanti al corso

I *partecipanti a un corso* sono i dipendenti che prendono parte a un evento o a un corso di formazione. È possibile registrare solo i partecipanti ai corsi aperti.

### <a name="workflow"></a>Flusso di lavoro

I dipendenti registrati per un corso tramite la pagina  **Dipendente self-service**  possono avere la registrazione instradata tramite il flusso di lavoro per l'approvazione. Un flusso di lavoro può essere assegnato a un corso nella Scheda dettaglio  **Generale**  della pagina  **Corsi** .
