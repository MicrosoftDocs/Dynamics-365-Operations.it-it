---
title: Novità o modifiche in Dynamics 365 Human Resources 26 settembre 2020
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 26 settembre 2020.
author: jcart1106
ms.date: 09/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cc730bca25293e7dbc78d72834dc8abf9b2a1ec4
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892683"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-26-2020"></a>Novità o modifiche in Dynamics 365 Human Resources 26 settembre 2020

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources. Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.3589-hf.3.

### <a name="new-features"></a>Nuove funzionalità

La seguente funzione è generalmente disponibile con questa versione:

- **L'aggiornamento della piattaforma 10.0.13 è ora disponibile**: Per ulteriori informazioni sull'aggiornamento, vedere [Aggiornamenti della piattaforma per la versione 10.0.13 delle app Finance and Operations (ottobre 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-13.md).

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potrebbero esserci aggiornamenti a questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Uscita | Descrizione |
| --- | --- | --- |
| 469495 | Aggiornare la griglia e la finestra di dialogo delle dimensioni finanziarie predefinite | La griglia e la finestra di dialogo delle dimensioni finanziarie sono state aggiornate in Human Resources. |
| 474887 | L'elemento di lavoro della richiesta di congedo apre un collegamento errato in una decisione manuale | Quando una configurazione del flusso di lavoro contiene una decisione manuale, passare alla richiesta di congedo da **Elementi di lavoro assegnati all'utente** apre il collegamento sbagliato, mostrando un modulo vuoto o una richiesta di congedo creata dall'utente corrente invece di quella assegnatagli per la decisione manuale. |
| 474962 | L'entità dei parametri di congedo e assenza ha campi con etichette ambigue | Le etichette delle entità dei parametri di congedi e assenze sono state aggiornate per essere più chiare. |
| 481401 | L'elaborazione dell'accumulo si blocca quando la base della data di accumulo è successiva alla data di inizio dell'accumulo e alla fine del mese | L'elaborazione dell'accumulo viene aggiornato in modo da non avere ritardi quando la base della data di accumulo è successiva alla data di inizio dell'accumulo e alla fine del mese. |
| 447167 | Gli elenchi di record in scadenza includono i lavoratori inattivi | Nella scheda **Record in scadenza** in **Gestione personale** sono inclusi i lavoratori inattivi. Ora include solo i lavoratori attivi. |
| 486840 | La richiesta di congedo errata si apre da **Elementi di lavoro assegnati all'utente** | La selezione di una richiesta di congedo da **Elementi di lavoro assegnati all'utente** non apre più la richiesta di congedo più recente assegnata all'utente corrente. |
| 506868 | Il campo **Titolo** di Dataverse non è impostato per l'entità **Posizione lavorativa** | Il campo **Titolo** nelle entità **Lavoro** e **Posizione lavorativa** viene visualizzato come non specificato. Il campo **Titolo** ora viene visualizzato. |
| 430359 | Non è possibile accedere alle attività dell'elenco di controllo dell'offboarding con ruoli di responsabile e dipendente assegnati | I lavoratori con una data di fine rapporto futura non potevano accedere alle loro attività dell'elenco di controllo se avevano solo un ruolo di dipendente o responsabile. Ora gli utenti con un ruolo di dipendente o responsabile possono accedere alle attività di offboarding con una data di fine rapporto futura. |
| 458102 | Il nuovo dipendente non appare nell'entità **Informazioni retribuzione lavoratore** al momento della creazione | I nuovi dipendenti vengono inclusi nell'entità delle informazioni sulla retribuzione dei lavoratori senza dover aprire le informazioni sulla retribuzione per il dipendente prima di esportare l'entità. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| App Human Resources in Microsoft Teams | [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [App Human Resources in Teams](./hr-admin-teams-leave-app.md)<br>[Gestire le richieste di congedo in Teams](hr-teams-leave-app.md) |
| Richieste e approvazioni del flusso di lavoro migliorate | [Miglioramenti all'esperienza del flusso di lavoro dell'organizzazione e della gestione del personale](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opzione di configurazione per posizionare l'elenco Elementi di lavoro assegnati all'utente](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |

## <a name="coming-soon"></a>Presto disponibili

La seguente nuova funzionalità è prevista per una versione futura:

- [Collegamenti personalizzati in Self-service responsabile](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedere [Panoramica del secondo ciclo di rilascio del 2019 di Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Risorse aggiuntive

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)
[Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)
[Processo di aggiornamento](hr-admin-setup-update-process.md)
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]