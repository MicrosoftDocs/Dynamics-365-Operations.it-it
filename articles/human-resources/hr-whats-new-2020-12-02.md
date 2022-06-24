---
title: Novità o modifiche in Dynamics 365 Human Resources 2 dicembre 2020
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 2 dicembre 2020.
author: marcelbf
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cecef6d2e73b42126b1be100dca52ebd8d9270fc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848109"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-december-2-2020"></a>Novità o modifiche in Dynamics 365 Human Resources 2 dicembre 2020

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive le funzionalità nuove, modificate o future di Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.3788.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| I responsabili sono in grado di inviare richieste di selezione per le posizioni | [I responsabili possono inviare una richiesta di selezione per le posizioni aperte](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Aggiungere una richiesta di selezione](./hr-personnel-recruit.md#add-a-recruiting-request) |
| Profilo candidato migliorato in Gestione personale | [Profilo candidato migliorato in Gestione personale](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Aggiungere o modificare un profilo candidato](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| Abilitare le integrazioni semplificate con i selezionatori | [Abilitare le integrazioni semplificate con i selezionatori](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Selezionare i candidati a una posizione](./hr-personnel-recruit.md) |
| Collegamenti personalizzati in Responsabile self-service | [Collegamenti personalizzati in Self-service responsabile](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Collegamenti personalizzati in Self-service responsabile](./hr-employee-manager-self-service-custom-links.md) |


### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potremmo aggiornare questo articolo per includere le correzioni di bug che sono state inserite nella build dopo che questo articolo è stato inizialmente pubblicato.

| Numero problema | Problema | Description |
| --- | --- | --- |
| 514087 | BenefitEligibilityProcessResult deve includere il datetime utilizzato nell'elaborazione. | Il risultato dell'elaborazione di BenefitEligibity ora include il datetimestamp dell'ultima elaborazione che mancava in precedenza. |
| 526903 | La registrazione ai benefit non riesce per i piani con dipendenti quando **Seleziona automaticamente i beneficiari designati** è attivato in **Parametri condivisi delle risorse umane**. | Risolto il problema a causa del quale la registrazione ai benefit non riusciva per i dipendenti quando l'opzione **Seleziona automaticamente i beneficiari designati** è attivata per i beneficiari predefiniti. |
| 521922 | Il parametro **Mostra assenza senza dettagli** mostra i dettagli delle richieste di permesso nel calendario delle assenze del team. | Il tipo di congedo, il colore del tipo di congedo e i dettagli del giorno venivano mostrati nel calendario delle assenze del team quando **Mostra assenza senza dettagli** era impostato su **Sì** in **Parametri di congedi e assenze**. Questo problema è stato risolto e ora il tipo di congedo non viene visualizzato e il colore predefinito del tipo di congedo (blu scuro) viene utilizzato per tutti i tipi di congedo nel calendario delle assenze del team. |
| 527316 | Le modifiche al titolo per le notifiche di lavoro, posizione e lavoratore non vengono sincronizzate. | Una relazione Titolo è stata precedentemente aggiunta alle entità Lavoro, Posizione e Lavoratore. La sincronizzazione per questa relazione funziona per la sincronizzazione da Human Resources a Dataverse, ma non per le notifiche di Dataverse. Questo problema è stato risolto. |
| 512275 | Rimuovere le opzioni di colore da **Parametri di congedo e assenza**. | Ora che i colori sono definiti nel tipo di congedo, le opzioni dei colori non sono più necessarie in **Parametri di congedo e assenza**, quindi sono stati rimossi. |
| 437112 | Testo del messaggio di errore fuorviante durante l'assegnazione della posizione del dipendente. | Aggiornato il messaggio di errore durante l'assunzione di un lavoratore e il tentativo di assegnarlo a una posizione non attiva. Messaggio aggiornato **La posizione specificata non è attiva alla data di inizio del rapporto di lavoro. Controllare la durata di questa posizione.** |
| 527816 | Problemi di prestazioni con la pagina **Permesso**. | Le prestazioni sono state migliorate per la pagina **Permesso**. |
| 523158 | BenefitPeriodMigrationUpgrade e BenefitPlanMigrationUpgrade non in esecuzione. | Risolti i problemi con i processi di migrazione dei benefit relativi a **Periodo** e **Piano** non eseguiti correttamente. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| App Human Resources in Microsoft Teams | [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [App Human Resources in Teams](./hr-admin-teams-leave-app.md)<br>[Gestire le richieste di congedo in Teams](hr-teams-leave-app.md) |
| Richieste e approvazioni del flusso di lavoro migliorate | [Miglioramenti all'esperienza del flusso di lavoro dell'organizzazione e della gestione del personale](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opzione di configurazione per posizionare l'elenco Elementi di lavoro assegnati all'utente](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Integrazione con LinkedIn Talent Hub | [Integrazione con LinkedIn Talent Hub](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integrazione con LinkedIn Talent Hub](./hr-admin-integration-linkedin.md) |
|Visualizzazione interaziendale del congedo per responsabili | [Visualizzazione interaziendale del congedo dei dipendenti per responsabili](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurare i parametri di congedo e assenza](./hr-leave-and-absence-parameters.md) |
|Fornire ulteriori informazioni dettagliate sui saldi dei congedi| [Fornire ulteriori informazioni dettagliate sui saldi dei congedi](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Gestire il congedo dei dipendenti](./hr-leave-and-absence-manage-employee-leave.md) |
| I responsabili sono in grado di inviare richieste di selezione per le posizioni | [I responsabili possono inviare una richiesta di selezione per le posizioni aperte](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Aggiungere una richiesta di selezione](./hr-personnel-recruit.md#add-a-recruiting-request) |
| Profilo candidato migliorato in Gestione personale | [Profilo candidato migliorato in Gestione personale](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Aggiungere o modificare un profilo candidato](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| Abilitare le integrazioni semplificate con i selezionatori | [Abilitare le integrazioni semplificate con i selezionatori](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Selezionare i candidati a una posizione](./hr-personnel-recruit.md) |

## <a name="coming-soon"></a>Presto disponibili

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedere [Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del secondo ciclo di rilascio del 2020 di Dynamics 365 Human Resources](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]