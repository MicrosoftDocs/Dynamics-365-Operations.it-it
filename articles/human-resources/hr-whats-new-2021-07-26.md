---
title: Novità e modifiche in Dynamics 365 Human Resources 26 luglio 2021
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 26 luglio 2021.
author: marcelbf
ms.date: 07/12/2021
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
ms.search.validFrom: 2021-07-26
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 810511c42cd690579d8c8b6ebcc17b0cf7fcb9eb2b999822dc2226fabd127cc6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771517"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-26-2021"></a>Novità e modifiche in Dynamics 365 Human Resources 26 luglio 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle relative date di disponibilità generale previste, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4384.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Update 10.0.20 della piattaforma | -- | [Aggiornamento della piattaforma per la versione 10.0.20 delle app Finance and Operations (agosto 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20) |

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. È possibile aggiornare questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Problema |  descrizione |
| --- | --- | --- |
| 600422 | La convalida dell'indirizzo retribuzione non riesce per Pronto per il pagamento. | La convalida è stata aggiornata per richiedere un solo indirizzo di tipo "Luogo di residenza retribuzioni" e un solo indirizzo di tipo "Luogo di lavoro retribuzioni". |
| 601226 | Problema di integrazione dei dati: Esportazione integrazione delle retribuzioni non presenta l'opzione per un push completo | L'integrazione delle retribuzioni in Ceridian DayForce generava un push incrementale anziché un push completo. Ceridian richiede sempre un aggiornamento completo. Questo problema è stato risolto; le entità nel progetto di esportazione dei dati non passeranno più al push incrementale. |
| 602272 | I riquadri aggiunti all'area di lavoro Dipendente self-service risultano mancanti e non è più possibile aggiungervi riquadri | Abbiamo risolto il problema di personalizzazione per Dipendenti self-service. È possibile aggiungere nuovi riquadri alla visualizzazione e qualsiasi personalizzazione esistente sarà visibile agli utenti |
| 600711 | Il campo di selezione Definizione metà giornata è abilitato per le richieste di congedo di un'intera giornata | Questo problema è ora risolto e il campo Definizione metà giornata sarà abilitato solo quando i dipendenti selezionano un tipo di congedo con il campo Definizione metà giornata abilitato e mezza giornata come valore di importo selezionato |
| 602208 | Il coefficiente di accumulo è espresso in ore anziché giorni | Questo problema è ora risolto. Il modulo **Tempo libero** mostrerà l'unità corretta (ore o giorni) nella colonna **Coefficiente di accumulo**. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Abilitare l'integrazione delle retribuzioni semplificata (API di integrazione delle retribuzioni) | [Abilitare l'integrazionei semplificata con i fornitori retribuzioni](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)|
|  Consentire a un responsabile dei congedi di gestire le ferie | [Consentire a un responsabile dei congedi di gestire le ferie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | In questa versione, stiamo aggiornando la visualizzazione Area di lavoro del responsabile dei congedi. Per ulteriori informazioni, vedi [Configura il ruolo del responsabile dei congedi](https://go.microsoft.com/fwlink/?linkid=2168107).|
|  Configurare il requisito per l'allegato per tipo di congedo | [Configurare il requisito per l'allegato per tipo di congedo](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurare i tipi di congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Configurare le unità di congedo per tipo di congedo | [Configurare le unità di congedo per tipo di congedo](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurare i tipi di congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati | [Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Pronto per il pagamento](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Presto disponibile

Per un elenco completo delle funzionalità pianificate e dei relativi rilasci programmati, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
