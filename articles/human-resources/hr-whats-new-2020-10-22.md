---
title: Novità o modifiche in Dynamics 365 Human Resources 22 ottobre 2020
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 22 ottobre 2020.
author: jcart1106
ms.date: 10/22/2020
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
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 27c34c36b0bf33c28f33f7ecd838a76c5e241cbb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802265"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-22-2020"></a>Novità o modifiche in Dynamics 365 Human Resources 22 ottobre 2020

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources. Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.3680.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Aggiornamento della piattaforma 10.0.14(38) | -- | [Aggiornamento della piattaforma per la versione 10.0.14 delle app Finance and Operations (novembre 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-14) |
| Miglioramenti all'esperienza dei flussi di lavoro dell'organizzazione e della gestione del personale | [Miglioramenti all'esperienza del flusso di lavoro dell'organizzazione e della gestione del personale](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opzione di configurazione per posizionare l'elenco elementi di lavoro assegnati all'utente](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |


### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. È possibile aggiornare questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema| Uscita  | Descrizione|
| --- | --- | --- |
| 437922 | L'importazione delle ore FMLA utilizzando l'entità DMF genera un errore di sola lettura. | L'utilizzo dell'entità ore FMLA per importare le ore associate a un caso FMLA non è riuscito. È stata aggiunta una logica per garantire che le ore importate non superino le ore rimanenti per il caso. |
| 512019 | Importo **Ultimo riporto in avanti** non corretto. | Nella pagina **Permesso**, cambiando **In data** sul primo giorno del periodo fiscale successivo visualizza un importo **Ultimo riporto in avanti** non corretto per il tipo **Congedo annuale**. Ora visualizza l'importo corretto. |
| 458639 | L'entità **Contatti lavoratore** non supporta la modalità di rilevamento delle modifiche. | L'entità **Contatti lavoratore** è stata aggiornata in modo da poterla utilizzare in scenari BYOD.|
| 505347 | I responsabili della formazione potevano inviare una richiesta di congedo per un dipendente quando la funzione Lavoratore semplificato era abilitata. | I ruoli diversi dall'assistente delle risorse umane e dal responsabile delle risorse umane non sono autorizzati a inviare richieste di ferie per i dipendenti. |
| 513490 | Registrazione della gestione dei benefit: aggiungere la registrazione per i piani senza opzioni di copertura. | Abbiamo abilitato la registrazione dei risultati per il **piano senza opzioni di copertura**. Ora vengono visualizzati nella tabella **Risultati del processo** e sono ordinati correttamente per essere visualizzati all'inizio. |
| 517021 | Non è possibile selezionare più piani con lo stesso codice **Tipo di piano** se **Tipo di piano** ha un'iscrizione per tipo. | Abbiamo modificato le restrizioni per la selezione di piani in cui è consentita una sola iscrizione. Le restrizioni sono ora a livello di **Codice tipo di piano** invece di **Tipo di piano**. Questa modifica consente piani come HSA e FSA, che sono entrambi dello stesso tipo, ma è possibile assegnare loro un **Codice tipo di piano** separato. In questo modo, è possibile selezionarli entrambi per lo stesso periodo di iscrizione. |
| 444791 | Non è possibile visualizzare la retribuzione in Self-service dipendenti quando **Accesso limitato** è attivato nel piano di retribuzione. | Nella scheda **Retribuzione** del Self-service dipendenti l'importo della retribuzione corrente e la percentuale di aumento visualizzava "0" se il dipendente era iscritto a un piano con **Accesso limitato** attivato e assegnato a ruoli specifici. Abbiamo risolto questo problema in modo che il dipendente e il responsabile possano sempre vedere i dettagli della retribuzione per se e per i loro diretti subalterni. |
| 457542 | L'aggiornamento dei dettagli del corso dopo la chiusura del corso non aggiorna anche le stesse informazioni per il dipendente che ha seguito il corso. | Le informazioni del dipendente ora vengono aggiornate correttamente quando si modificano i dettagli del corso dopo la chiusura e la riapertura di un corso. |
| 515342 | Non è possibile inserire dati tramite **CDSLeaveRequestDetailEntity**. La società non è stata trovata o non esiste. | Ora è possibile usare **CDSLeaveRequestDetailEntity** per inserire dati. |
| 514743 | Errore nel modulo **Parametro e-mail** quando si utilizza Microsoft Exchange. | Il messaggio "Impossibile caricare file o assembly..." viene visualizzato nella pagina **Parametri e-mail** quando il provider di posta elettronica è impostato su **Exchange**. Questa correzione consente anche il caricamento e il salvataggio della pagina **Parametri e-mail** come previsto. |


## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| App Human Resources in Microsoft Teams | [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [App Human Resources in Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Gestire le richieste di congedo in Teams](hr-teams-leave-app.md) |
| Richieste e approvazioni del flusso di lavoro migliorate | [Miglioramenti all'esperienza del flusso di lavoro dell'organizzazione e della gestione del personale](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opzione di configurazione per posizionare l'elenco Elementi di lavoro assegnati all'utente](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Entità virtuali in Dataverse per Human Resources | [Espandere i dati di base Dynamics 365 Human Resources in Dataverse](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Configurare le entità virtuali di Dataverse](hr-admin-integration-common-data-service-virtual-entities.md) |
| Integrazione con LinkedIn Talent Hub | [Integrazione con LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integrazione con LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
| Collegamenti personalizzati in Responsabile self-service | [Collegamenti personalizzati in Self-service responsabile](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Collegamenti personalizzati in Self-service responsabile](https://aka.ms/MSSCustomLinks) |

## <a name="coming-soon"></a>Presto disponibili

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedere [Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]