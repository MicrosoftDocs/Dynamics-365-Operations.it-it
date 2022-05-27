---
title: Novità o modifiche in Dynamics 365 Human Resources 6 settembre 2021
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 6 settembre 2021.
author: marcelbf
ms.date: 09/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 314d836db9b7560c2ed95ad1b9d2eba753e39d2b
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690584"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-6-2021"></a>Novità o modifiche in Dynamics 365 Human Resources 6 settembre 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le caratteristiche che sono nuove, cambiate o in arrivo in Microsoft Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle relative date di disponibilità generale previste, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4443.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
|---|---|---|
| Consentire a un responsabile dei congedi di gestire le ferie | [Consentire a un responsabile dei congedi di gestire le ferie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | In questa release, stiamo aggiornando la vista dello spazio di lavoro del gestore delle assenze. Per ulteriori informazioni, vedi [Configura il ruolo del responsabile dei congedi](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Configurare il requisito per l'allegato per tipo di congedo | [Configurare il requisito per l'allegato per tipo di congedo](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) | [Configurare i tipi di congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2168108) |
| Configurare le unità di congedo per tipo di congedo | [Configurare le unità di congedo per tipo di congedo](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) | [Configurare i tipi di congedo e assenza](https://go.microsoft.com/fwlink/?linkid=2168215) |

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potremmo aggiornare questo argomento per includere le correzioni di bug che sono state inserite nella build dopo che questo argomento è stato inizialmente pubblicato.

| Numero problema | Problema | descrizione |
|---|---|---|
| 610128 | Errore relativo alla pubblicazione dei dati quando si utilizza HcmDiscussionOverallCommentEntity | Quando i dati vengono pubblicati da una cartella di lavoro di Excel nell'entità HcmDiscussionOverralCommentEntity, si verifica il seguente errore: "Impossibile individuare il record di origine dati di tipo HcmTopicOverrall". |
| 589073 | Il report EEO-1 conteggia i valori "non specificati" e vuoti per il campo **Genere** come valore "Femmina". | Se **Maschio** non è specificato per il campo **Genere**, il report EEO-1 genera un valore predefinito di **Femmina**. |
| 589617 | Il saldo della scheda Permessi e i saldi dei campi Disponibili per l'acquisto e Disponibili per la vendita non vengono visualizzati quando i ruoli utente sono limitati a una persona giuridica specifica. | Se l'utente (ruolo dipendente) è limitato a una specifica persona giuridica, i saldi non vengono visualizzati correttamente nella scheda **Saldi permessi**, e nei campi **Disponibile per l'acquisto** e **Disponibile per la vendita**. |
| 604310 | La scheda responsabile dei congedi deve essere nascosta quando all'utente non è stata assegnata una gerarchia dei congedi. | Per una data entità giuridica, la scheda **Responsabile dei congedi** deve essere nascosta nel portale self-service a meno che il parametro interaziendale non sia abilitato e all'utente sia associata almeno una gerarchia di congedi. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per maggiori informazioni su come attivare o disattivare le funzioni, vedi [Gestione delle funzioni](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
|---|---|---|
| Abilitare l'integrazione delle retribuzioni semplificata (API di integrazione delle retribuzioni) | [Abilitare l'integrazionei semplificata con i fornitori retribuzioni](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md) |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati | [Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Pronto per il pagamento](/dynamics365/human-resources/hr-compensation-payroll) |
| Campi personalizzati in Idoneità |[Supporto per campi personalizzati per l'elaborazione dell'idoneità](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Utilizzo di campi personalizzati nell'elaborazione dell'idoneità](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |

## <a name="coming-soon"></a>Presto disponibile

Per un elenco completo delle funzionalità pianificate e dei relativi rilasci programmati, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funzionalità | Dettagli |
|---|---|
| Platform Update 10.0.21 (45) | Il roll-out dell'aggiornamento 10.0.21 della piattaforma è previsto per iniziare con il rilascio del servizio il 4 ottobre 2021. Per ulteriori informazioni, vedere [Aggiornamenti della piattaforma per la versione 10.0.21 delle app per la finanza e le operazioni (ottobre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
| Rendiconto benefit | Rendiconto dei benefit per la visualizzazione delle attuali idoneità dei benefit di un dipendente. Per ulteriori informazioni, vedi [Rendiconto benefit](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) nel documento del ciclo di rilascio. |

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
