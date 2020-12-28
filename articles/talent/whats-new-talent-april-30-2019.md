---
title: Novità o modifiche in Dynamics 365 Talent (30 aprile 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2539baba84bffeb21d351cc307191eea3e940515
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528197"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-30-2019"></a>Novità o modifiche in Dynamics 365 Talent (30 aprile 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2270. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="provide-feedback"></a>Fornire commenti e suggerimenti

L'opzione per fornire un feedback si trova nel menu **Guida** (**?**) di Talent. Questo menu consente di accedere alle risorse seguenti:

- Commenti e suggerimenti
- ?
- Per iniziare
- Supporto
- Idee
- Informazioni su

### <a name="improvements-to-the-user-interface-for-duplicate-employee-detection"></a>Miglioramenti all'interfaccia utente per il rilevamento di dipendenti duplicati

Grazie a questa modifica, i duplicati vengono ora rilevati quando si impostano i campi dei nomi e un indicatore di stato mostra il numero di duplicati che sono stati rilevati. Un collegamento fornito apre una pagina in cui è possibile valutare se utilizzare uno dei duplicati. Per evitare di interrompere l'immissione di dati, la pagina Duplicati non viene aperta automaticamente. È necessario selezionare il collegamento per aprire la pagina.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Support dell'entità Common Data Service per i campi personalizzati

Nella versione di questa settimana, le seguenti entità supportano ora i campi personalizzati: Impiego, Tipo di benefit e Ciclo retributivo.

### <a name="an-error-occurs-when-an-off-boarding-checklist-is-assigned-299877"></a>Si verifica un errore quando viene assegnata un elenco di controllo di offboarding (299877)

Questa modifica corregge un messaggio di errore che appare quando si assegna un elenco di controllo di offboarding a un dipendente al di fuori del processo di fine rapporto.

### <a name="the-exited-workers-link-opens-the-wrong-worker-309939"></a>Il collegamento dei lavoratori che hanno lasciato la società apre il lavoratore sbagliato (309939)

Questa modifica corregge un problema che si verifica quando si sta riassumendo un dipendente da un'altra persona giuridica e si prova a passare al dipendente dall'elenco dei lavoratori che hanno lasciato la società.

### <a name="the-employee-self-service-compensation-card-doesnt-show-summary-values-when-advanced-security-is-turned-on-315231"></a>La scheda retributiva self-service dei dipendenti non mostra valori di riepilogo quando la sicurezza avanzata è attivata (315231)

Questa modifica corregge un problema che si verifica quando si utilizza la sicurezza avanzata della retribuzione. Quando viene abilitata la sicurezza avanzata, il self-service dei dipendenti ora mostra gli importi di retribuzione di riepilogo per i dipendenti e i manager. Prima di questa modifica, i valori riepilogativi apparivano con valore 0 (zero).

### <a name="if-a-position-without-a-title-is-created-in-common-data-service-no-position-is-created-in-talent-314562"></a>Se una posizione senza un titolo viene creata in Common Data Service, non viene creata alcuna posizione in Talent (314562)

Le modifiche di questa settimana correggono un problema che si verifica quando si creano posizioni in Common Data Service ma non si fornisce un titolo.

### <a name="error-message-in-performance-journal-entries-in-employee-self-service-314134"></a>Messaggio di errore nelle delle voci del giornale di registrazione delle prestazioni nel self-service dei dipendenti (314134)

Questa modifica corregge un problema che si verifica quando si collegano gli obiettivi prestazione giornale di registrazione delle prestazioni nel self-service dei dipendenti.

## <a name="in-preview"></a>In anteprima

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Consentire la specifica dei codici motivo nei tipi di congedo

Le organizzazioni potrebbero richiedere informazioni aggiuntive per le richieste di permesso. Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Richiedere codici motivo per tipi di congedo specifici nelle richieste di permesso

Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso. Questo requisito potrebbe esistere a causa di criteri aziendali o requisiti normativi. Ora è possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fornire un elenco di transazioni assenze e congedo per le Risorse umane

La possibilità di tracciare il tempo libero dei dipendenti e analizzare come tale tempo viene calcolato non solo consente alle Risorse umane di rispondere alle domande dei dipendenti, ma anche di garantire premi appropriati per i dipendenti. Ora le Risorse umane hanno una nuova visibilità sulle transazioni (concessioni, accumuli, rettifiche e richieste) in modo da poter determinare i motivi dei saldi.

## <a name="coming-soon"></a>Presto disponibili

### <a name="email-support-for-alerts"></a>Supporto di messaggi di posta elettronica per avvisi

Nell'aggiornamento 26 della piattaforma per Finance and Operations, gli utenti possono creare regole di avviso che inviano automaticamente notifiche di posta elettronica ai contatti quando le notifiche sono attivate da un evento.
