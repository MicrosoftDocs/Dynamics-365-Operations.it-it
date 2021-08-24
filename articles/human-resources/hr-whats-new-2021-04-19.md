---
title: Novità o modifiche in Dynamics 365 Human Resources (19 aprile 2021)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 19 aprile 2021.
author: marcelbf
ms.date: 04/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadad34be31f6522654bc3af47a4f71695dcc5fea7f0b3e760ff26d79d88eb4c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722513"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-19-2021"></a>Novità o modifiche in Dynamics 365 Human Resources (19 aprile 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4113.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Platform Update 10.0.17 (41) | -- | [Aggiornamenti della piattaforma per la versione 10.0.17 delle app Finance and Operations (aprile 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md) |
| Supporto per campi personalizzati nei moduli Gestione benefit | [Supporto per campi personalizzati nei moduli Gestione benefit](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management)| [Panoramica di gestione dei benefit](hr-benefits-management-overview.md)|

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. È possibile aggiornare questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Uscita |  descrizione |
| --- | --- | --- |
| 552164 | **Visualizzazione salvata** in **Self-service dipendenti > Apri corsi** non funziona per i corsi che contengono un'agenda | Se una visualizzazione salvata viene utilizzata in corsi aperti (ESS) e uno dei corsi ha un'agenda allegata, la visualizzazione non mostrerà più righe multiple per quel corso |
| 560614 | **Benefit > Opzioni di eventi reali** mostra discrepanze nella documentazione della descrizione comando e nel comportamento del codice. | Descrizioni comando aggiornate in **Opzioni di eventi reali** per mostrare il comportamento corretto. |
| 560616 | **Benefit > Opzioni di eventi reali** sono modificabili nel piano di benefit per i lavoratori, ma le modifiche non vengono interessate. | Il comportamento aggiornato dell'opzione di evento reale passa da abilitare o disabilitare, in base alle opzioni della persona a carico, in base alla documentazione della descrizione comando. |
| 565054 | Impossibile visualizzare il contenuto dell'elenco **Lavoratori senza impiego** quando **Accesso avanzato** è attivato. | Questa versione risolve il problema dove, quando **Accesso avanzato** è stato attivato, solo gli amministratori di sistema possono visualizzare i contenuti dell'elenco **Lavoratori senza impiego**. Poiché questa correzione è una modifica della sicurezza, sarà necessario acconsentire esplicitamente in Gestione funzionalità. Una volta attivata la funzionalità, i ruoli che hanno accesso al modulo vedranno il contenuto, anche se l'accesso avanzato è attivo. Per ulteriori informazioni, vedere [Lavoratori senza impiego](hr-personnel-workers-without-employment.md). |
| 570586 | La convalida della richiesta di ferie non riesce quando l'impiego termina prima dell'ultima transazione per quel lavoratore in tutti i piani di ferie. | Al termine di un rapporto di impiego, la convalida della richiesta di ferie non fallisce in base alle transazioni di ferie del dipendente.|
| 570783 | Abilitare e disabilitare il congedo interaziendale nei parametri condivisi Risorse umane cambia ciò che i dipendenti impiegati in una singola azienda vedono nelle richieste di ferie. | I dipendenti impiegati in una singola azienda non vedono cambiamenti nella richiesta di ferie se il parametro è abilitato o disabilitato. |
| 572343 | Il codice motivo richiesto non viene visualizzato quando la funzionalità di visualizzazione congedo interaziendale è abilitata. | Quando la funzionalità di visualizzazione congedo interaziendale è abilitata, Il codice motivo ora viene visualizzato come previsto. |
| 573676 | Impossibile aggiungere **Periodo** a **Gestione benefit > Collegamenti > Piani di benefit**. | Bug corretti dove **Periodo** non poteva essere aggiunto o aggiornato sul modulo **Piano di benefit** esistente. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Miglioramenti dell'esperienza del flusso di lavoro congedo e assenza | [Miglioramenti dell'esperienza del flusso di lavoro congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2147528) | [Richiedere un permesso](hr-employee-self-service-request-time-off.md)|
| Abilitare l'integrazione delle retribuzioni semplificata (API di integrazione delle retribuzioni) | [Abilitare l'integrazionei semplificata con i fornitori retribuzioni](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)|

## <a name="coming-soon"></a>Presto disponibili

| Funzionalità | Dettagli |
| --- | --- |
| Le competenze immesse da un manager per i propri dipendenti possono essere approvate automaticamente da un flusso di lavoro | Presto disponibili. |
| Platform Update 10.0.18 (42) | L'implementazione dell'aggiornamento della piattaforma 10.0.18 inizierà con la versione di servizio il 17 maggio 2021. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.18 delle app Finance and Operations (maggio 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Supporto per campi personalizzati nelle regole di idoneità di Gestione benefit  | [Supporto per campi personalizzati per l'elaborazione dell'idoneità](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedi [Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
