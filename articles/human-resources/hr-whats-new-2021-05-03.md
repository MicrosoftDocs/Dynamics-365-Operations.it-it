---
title: Novità o modifiche in Dynamics 365 Human Resources (3 maggio 2021)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 3 maggio 2021.
author: marcelbf
ms.date: 05/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-05-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 944d5794bb535faa18b4f2de8b5382ebfb9bc2ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022065"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-3-2021"></a>Novità o modifiche in Dynamics 365 Human Resources (3 maggio 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4140.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Aggiunta della barra delle informazioni quando vengono creati eventi reali. | - | Quando crei un evento reale, la barra delle informazioni visualizza un messaggio indicante il tipo di evento reale creato.

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. È possibile aggiornare questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Uscita |  descrizione |
| --- | --- | --- |
| 559312 |  Il livello non viene mostrato quando si crea un piano di retribuzione fissa per un dipendente. |  Quando si verifica una mancata corrispondenza tra il fuso orario dell'utente e il fuso orario dell'azienda, non è possibile leggere il livello di retribuzione sul lavoro. La query è stata aggiornata per essere recuperata in base all'ora UTC. |
| 573676  | Impossibile aggiungere un nuovo periodo nel modulo **Piano benefit**. | Aggiornato il modulo di modo che il pulsante **Nuovo** sia abilitato sotto la Scheda dettaglio **Periodo** in **Piani benefit**. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Miglioramenti dell'esperienza del flusso di lavoro congedo e assenza | [Miglioramenti dell'esperienza del flusso di lavoro congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2147528) | [Richiedere un permesso](hr-employee-self-service-request-time-off.md)|
| Abilitare l'integrazione delle retribuzioni semplificata (API di integrazione delle retribuzioni) | [Abilitare l'integrazionei semplificata con i fornitori retribuzioni](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)|
| Controllo transazione accumulo per congedo | - | [Controllo transazione accumulo per congedo](hr-leave-and-absence-accrue.md#preview-leave-accrual-transaction-auditing)|

## <a name="coming-soon"></a>Presto disponibile

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
