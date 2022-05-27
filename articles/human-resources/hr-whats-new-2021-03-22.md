---
title: Novità o modifiche in Dynamics 365 Human Resources (22 marzo 2021)
description: In questo argomento vengono descritte le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources all'22 marzo 2021.
author: marcelbf
ms.date: 03/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 13520ca55c98fb1acb6185af393550b12fbc2072
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693530"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-22-2021"></a>Novità o modifiche in Dynamics 365 Human Resources (22 marzo 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4049.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Opzione per forzare l'annullamento e il ripristino dei lavori batch bloccati (560976) | NA | [Reimpostare i processi batch bloccati](./hr-admin-troubleshooting-batch-execution.md) |
| Aggiornamenti minori dell'esperienza utente per la creazione di un nuovo piano di benefit (419941) | NA | [Creare un piano di benefit](hr-benefits-plans-setup.md) |

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. È possibile aggiornare questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Uscita |  descrizione |
| --- | --- | --- |
| 554239 | Miglioramenti delle prestazioni per entità correlate alla tabella **BusinessProcessTaskAssignment** | Miglioramento delle prestazioni delle entità correlate alla tabella **BusinessProcessTaskAssignment** aggiungendo gli indici suggeriti alla tabella. |
| 566061 | Rimozione del codice di fallback dell'entità V2 dalla sincronizzazione notturna | Rimozione del codice di fallback V2 per la sincronizzazione notturna di Dataverse. Il fallback non è più necessario e impedisce alla sincronizzazione filtrata di funzionare come previsto. La modifica migliora la coerenza della sincronizzazione dei dati Dataverse. |
| 538024 | Piani di benefit per i lavoratori > Errore generato alla rimozione del checkout | È stato risolto un errore durante la rimozione del checkout per l'opzione Piano di benefit nel modulo Benefit lavoratori. |
| 557965 | Area di lavoro **Benefit**: il collegamento **Eventi reali attivi** deve essere sempre visibile nella sezione **Collegamenti** | Risolto il problema per cui il collegamento **Eventi reali attivi** era visibile nella sezione **Collegamenti**, ma generava un errore durante il tentativo di spostarsi se la funzionalità **(Anteprima) Area di lavoro per la gestione dei benefit** non è abilitata. Per ulteriori informazioni sull'abilitazione dell'area di lavoro, vedi [Area di lavoro per la gestione dei benefit](hr-benefits-management-workspace.md). |
| 556672 | Impossibile elaborare i ratei per un dipendente licenziato quando **Inserimento dipendenti semplificato** è abilitato nella gestione delle funzionalità | È stata aggiunta l'opzione per accumulare piani di ferie e assenze ad **Altre opzioni** sotto **Storico lavoro** per i dipendenti quando **Inserimento dipendenti semplificato** è abilitato nella gestione delle funzionalità. |
| 562656 | La voce di menu **SysRecordChangeLogValidTimeState** deve essere inclusa in un privilegio di sicurezza e un'estensione del diritto di sicurezza **SystemExternalBasicMaintain** | Ai ruoli di amministratore non di sistema mancava il pulsante **Visualizza modifiche** sui moduli del gestione della data. |
| 505989 | Elaborazione degli eventi reali: modifica dell'idoneità non elaborata correttamente a causa della data utilizzata | Risolto il problema per cui la modifica nell'elaborazione dell'idoneità dipendeva dalla data di inizio della posizione e non solo dalla posizione corrente. |
| 562286 | Il lavoratore licenziato invia più aggiornamenti a Dataverse | Quando un lavoratore viene licenziato, viene inviata più di un'operazione di aggiornamento a Dataverse, risultando in due notifiche di aggiornamento per la stessa modifica. Ciò può causare più attivazioni se un flusso Power Automate è configurato per attivarsi all'azione. |
| 527340 | L'errore "Data e ora non rappresentabile" viene visualizzato quando si aprono le iscrizioni per ferie e assenze | Quando si seleziona un'iscrizione di congedo e assenza, l'errore non viene più visualizzato. |
| 561663 | Aumento dell'intervallo di tempo di attesa per il provisioning del cluster | Migliorata la stabilità dell'infrastruttura e la coerenza del provisioning con gli aggiornamenti al provisioning del cluster. |
| 486129 | Non è possibile modificare i campi personalizzati in **Ubicazioni > Gestisci modifiche** | Risolto un problema per cui i campi personalizzati non potevano essere modificati nella scheda **Gestisci modifiche** per **Ubicazioni**. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Impedire ai dipendenti di modificare i dettagli di contatto aziendali | [Impedire ai dipendenti di modificare i dettagli di contatto aziendali](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Impedire la modifica delle informazioni personali](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Presto disponibili

| Funzionalità | Dettagli |
| --- | --- |
| Le competenze immesse da un manager per i propri dipendenti possono essere approvate automaticamente da un flusso di lavoro | Presto disponibili. |

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedi [Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]