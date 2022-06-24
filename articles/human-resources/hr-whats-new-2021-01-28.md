---
title: Novità o modifiche in Dynamics 365 Human Resources 28 gennaio 2021
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 28 gennaio 2021.
author: marcelbf
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 46bbda21c3eb2b32030b93afc2a40785c22b124e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909761"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-28-2021"></a>Novità o modifiche in Dynamics 365 Human Resources 28 gennaio 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive le funzionalità nuove, modificate o future di Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.3906.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Integra i codici motivo Benefit nell'area di lavoro **Gestione personale** | -- | [Imposta i codici causale](hr-benefits-setup-reason-codes.md) |

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potremmo aggiornare questo articolo per includere le correzioni di bug che sono state inserite nella build dopo che questo articolo è stato inizialmente pubblicato.


| Numero problema | Problema |  Description |
| --- | --- | --- |
| 539456 | Il calendario mostra il tipo di congedo nel testo al passaggio del mouse quando il parametro **Mostra assenza senza dettagli** è abilitato. | Quando l'opzione **Mostra assenza senza dettagli** è abilitata, la data della richiesta ora viene visualizzata al passaggio del mouse. |
| 528907 | La concessione dell'accesso a una persona giuridica nel ruolo di dipendente fa sì che i manager non siano in grado di vedere l'attività del saldo delle ferie per i dipendenti nell'area **Team personale** del self-service dei dipendenti. |L'impostazione di questa opzione ora consente ai manager di continuare a vedere l'attività del saldo delle ferie. |
| 526280 | Errore di autorizzazioni su HcmWorkerEntity, HcmEmployeeEntity e HcmContractorEntity. | Gli utenti con un ruolo di amministratore non di sistema non sono stati in grado di esportare le entità elencate a causa di un errore di autorizzazione nel campo NationalityCountryRegion. Gli utenti continueranno ad avere bisogno dei seguenti privilegi per esportare queste informazioni: HcmWorkerEntityMaintain, HcmWorkerEntityView, HcmEmployeeEntityMaintain, HcmEmployeeEntityMaintain, HcmEmployeeEntityView, HcmContractorEntityMaintain e HCMContractorEntityView. |
| 542147 | I campi **Numero conto bancario** e **Numero di registrazione** sono obbligatori quando si aggiunge un conto bancario tramite il self-service dei dipendenti. | Abbiamo corretto l'errore in cui i dipendenti dovevano inserire i campi **Numero conto bancario** e **Numero di registrazione** durante l'aggiunta dei dettagli del conto bancario. Questi campi non sono più obbligatori durante il salvataggio dei nuovi dati del conto bancario. |
| 543641 | Il codice postale non viene compilato nella creazione dei report elettronici. | Risolto un bug per il quale il codice postale non veniva compilato nel rapporto ACA per i codici di copertura da L a Q. |
| 545402 | Aggiungi la modifica del routing per il file UserBranding.js per rimuovere gli errori 404. | L'utente non dovrebbe più vedere gli errori 404 nella console. |

## <a name="in-preview"></a>In anteprima   

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| App Human Resources in Microsoft Teams | [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [App Human Resources in Teams](./hr-admin-teams-leave-app.md)<br>[Gestire le richieste di congedo in Teams](hr-teams-leave-app.md) |
| Visualizzazione interaziendale del congedo per responsabili | [Visualizzazione interaziendale del congedo dei dipendenti per responsabili](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurare i parametri di congedo e assenza](./hr-leave-and-absence-parameters.md) |

## <a name="coming-soon"></a>Presto disponibili

| Funzionalità | Dettagli |
| --- | --- |
| Conferma tramite e-mail per le iscrizioni dei benefit | Questa funzione fornirà un'opzione per inviare un e-mail di conferma ai dipendenti quando effettuano il check-out dalle esperienze di registrazione dei vantaggi in self-service dei dipendenti. Questa funzione sarà disponibile il 1° febbraio. Per ulteriori informazioni, vedi [Configurare i parametri di gestione dei benefit per azienda](hr-benefits-setup-parameters-per-company.md). |
| Le competenze immesse da un manager per i propri dipendenti possono essere approvate automaticamente da un flusso di lavoro | Presto disponibili. |

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedi [Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Aggiornamenti terminologici per Microsoft Dataverse

A partire da novembre 2020, Common Data Service è stato rinominato in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Vedi l'[ annuncio ufficiale](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) sul blog Power Apps per saperne di più. Insieme a questo cambio di nome, è stata aggiornata un po 'di terminologia in Dataverse. Ad esempio, *entità* è ora *tabella* e *campo* è ora *colonna*. Per ulteriori informazioni, vedere [Aggiornamenti della terminologia](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

In questa versione, la terminologia relativa all'integrazione Dynamics 365 Human Resources con Dataverse è stata aggiornata in tutta l'applicazione per riflettere questi cambiamenti. Ad esempio, il modulo **Integrazione Common Data Service** è ora **Integrazione Microsoft Dataverse**.

Per saperne di più sull'integrazione di Dynamics 365 Human Resources con Microsoft Dataverse, vedi [Configura integrazione Microsoft Dataverse](./hr-admin-integration-common-data-service.md) e [Configura tabelle virtuali di Microsoft Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]