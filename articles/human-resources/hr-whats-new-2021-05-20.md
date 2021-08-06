---
title: Novità o modifiche in Dynamics 365 Human Resources (20 maggio 2021)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 20 maggio 2021.
author: marcelbf
ms.date: 05/20/2021
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
ms.search.validFrom: 2021-05-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c7b7f71cf084a05bb0278f5df4ddb022ef3d640f
ms.sourcegitcommit: baad2723291774f610324a8054fc14abf3287fe1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "6560052"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-20-2021"></a>Novità o modifiche in Dynamics 365 Human Resources (20 maggio 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4189.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Platform Update 10.0.18 (42) | -- | [Aggiornamento della piattaforma per la versione 10.0.18 delle app Finance and Operations (maggio 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18) |
| L'app Human Resources per Microsoft Teams ora supporta le definizioni di metà giornata e la funzionalità per suddividere il giorno | -- | [Gestire le richieste di congedo in Teams](/dynamics365/human-resources/hr-teams-leave-app#create-a-new-request) |

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. È possibile aggiornare questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Problema |  descrizione |
| --- | --- | --- |
| 583776 | Le iscrizioni di massa dei dipendenti ai piani di ferie stanno causando un errore di registrazione duplicato | Questo bug è stato risolto con l'ultima versione e le iscrizioni al piano di ferie di massa dovrebbero essere elaborate correttamente. |
| 582263 | Impossibile eseguire l'elaborazione degli eventi della vita per tutti i lavoratori contemporaneamente | Quando il campo **Lavoratore** viene lasciato vuoto per l'elaborazione degli eventi della vita, tutti i lavoratori verranno elaborati. |
| 558383 | Beneficiario principale non contrassegnato come 100% se il designato predefinito non è selezionato | Il bug è stato risolto in modo che l'utente debba solo selezionare l'interruttore del beneficiario principale.|
| 509404 | L'analisi dell'organico del reparto non prende in considerazione il movimento dei dipendenti tra i reparti |Le analisi sono state aggiornate per includere i trasferimenti di dipendenti tra i reparti|
| 579420 | La funzione di congelamento delle colonne nelle griglie non dovrebbe essere ancora disponibile | La funzionalità **Congelamento delle colonne nelle griglie**, che non è disponibile in Human Resources, era elencata come disponibile in Gestione funzionalità. La funzionalità è stata rimossa dall'elenco delle funzionalità da abilitare. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Supporto per campi personalizzati nelle regole di idoneità di Gestione benefit | [Supporto per campi personalizzati per l'elaborazione dell'idoneità](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Configurazione delle regole di idoneità](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Miglioramenti dell'esperienza del flusso di lavoro congedo e assenza | [Miglioramenti dell'esperienza del flusso di lavoro congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2147528) | [Richiedere un permesso](hr-employee-self-service-request-time-off.md)|
| Abilitare l'integrazione delle retribuzioni semplificata (API di integrazione delle retribuzioni) | [Abilitare l'integrazionei semplificata con i fornitori retribuzioni](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)|
| Controllo transazione accumulo per congedo | - | [Controllo transazione accumulo per congedo](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Presto disponibile

| Funzionalità | Dettagli |
| --- | --- |
|  Consentire a un responsabile dei congedi di gestire le ferie | [Consentire a un responsabile dei congedi di gestire le ferie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedi [Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
