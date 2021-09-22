---
title: Cosa c'è di nuovo o cambiato in Dynamics 365 Human Resources 23 agosto 2021
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 23 agosto 2021.
author: marcelbf
ms.date: 08/23/2021
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
ms.search.validFrom: 2021-08-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 21c9ee0206bd77a8a2ec42501d64e83077baef09
ms.sourcegitcommit: 696796ca5635863850ae9ef16fc1fb0fc46ce8f0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2021
ms.locfileid: "7441677"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-23-2021"></a>Cosa c'è di nuovo o cambiato in Dynamics 365 Human Resources 23 agosto 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le caratteristiche che sono nuove, cambiate o in arrivo in Microsoft Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle relative date di disponibilità generale previste, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4419.

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potremmo aggiornare questo argomento per includere le correzioni di bug che sono state inserite nella build dopo che questo argomento è stato inizialmente pubblicato.

| Numero problema | Problema | descrizione |
| --- | --- | --- |
| 594066 | Impossibile eliminare le informazioni di contatto | Quando si sceglie di eliminare un record di informazioni di contatto per un dipendente, viene invece eliminato un record di informazioni di contatto diverso dal record selezionato. |
| 611339 | L'aggiunta di una personalizzazione fa sì che il conto bancario ignori il filtro e recuperi il primo record | L'aggiunta di una personalizzazione fa sì che l'elenco dei conti bancari esegua una query di personalizzazione dopo l'esecuzione della query dell'origine dati, con il risultato che la query recupera il record principale indipendentemente dal lavoratore per il quale vengono visualizzati i dettagli. |
| 591806 | Le attività relative alla data di scadenza di onboarding sono calcolate in modo errato | Le date di scadenza vengono calcolate in modo errato quando esistono le seguenti condizioni: gli elenchi di controllo creati utilizzano un calendario che utilizza un intervallo di tempo esteso (ad esempio dal 2005 al 2050) e le preferenze dell'utente utilizzano un fuso orario diverso dall'Ora solare fuso centrale. |   
| 592749 | Il saldo di congedo è errato su **Self-service dipendenti** | Se il dipendente ha un impiego presso più di una persona giuridica e la visualizzazione del congedo interaziendale è abilitata, il saldo di congedo potrebbe essere errato. |
| 603133 | Avviso imprevisto durante la richiesta di permesso | Al momento della richiesta di permesso, la compilazione del campo **Mezza giornata** prima del campo **Quantità** causerà un avviso imprevisto. |
| 606546 | Campo Seleziona non visibile in Permesso approvato | La casella di controllo per selezionare più richieste di congedo approvate non era visibile. |
| 597059 | Operaio non visibile in **Calendario aziendale di congedi e assenze** | Un lavoratore non è visibile nel **Calendario aziendale di congedi e assenze** se l'intervallo di date applicato include qualsiasi giorno per il quale al lavoratore è stata negata una richiesta di congedo. |


## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per maggiori informazioni su come attivare o disattivare le funzioni, vedi [Gestione delle funzioni](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Abilitare l'integrazione delle retribuzioni semplificata (API di integrazione delle retribuzioni) | [Abilitare l'integrazionei semplificata con i fornitori retribuzioni](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)|
| Consentire a un responsabile dei congedi di gestire le ferie | [Consentire a un responsabile dei congedi di gestire le ferie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | In questa release, stiamo aggiornando la vista dello spazio di lavoro del gestore delle assenze. Per ulteriori informazioni, vedi [Configura il ruolo del responsabile dei congedi](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Configurare il requisito per l'allegato per tipo di congedo | [Configurare il requisito per l'allegato per tipo di congedo](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurare i tipi di congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2168108)|
| Configurare le unità di congedo per tipo di congedo | [Configurare le unità di congedo per tipo di congedo](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurare i tipi di congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati | [Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Pronto per il pagamento](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Presto disponibile

Per un elenco completo delle funzionalità pianificate e dei relativi rilasci programmati, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funzionalità | Dettagli |
| --- | --- |
| Platform Update 10.0.21 (45) | Il roll-out dell'aggiornamento 10.0.21 della piattaforma è previsto per iniziare con il rilascio del servizio il 4 ottobre 2021. Per maggiori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.21 di Finance and Operations apps (ottobre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
