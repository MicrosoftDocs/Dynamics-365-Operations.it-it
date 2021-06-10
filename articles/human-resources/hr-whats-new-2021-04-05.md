---
title: Novità o modifiche in Dynamics 365 Human Resources (5 aprile 2021)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 5 aprile 2021.
author: marcelbf
ms.date: 04/05/2021
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
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 879a500c187e7b0a11d367c4a12618a9c60c98b7
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056470"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-5-2021"></a>Novità o modifiche in Dynamics 365 Human Resources (5 aprile 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4074.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Impedire ai dipendenti di modificare i dettagli di contatto aziendali | [Impedire ai dipendenti di modificare i dettagli di contatto aziendali](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Limitare la modifica delle informazioni personali](./hr-employee-self-service-restrict-editing.md)|

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. È possibile aggiornare questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Uscita |  descrizione |
| --- | --- | --- |
| 550852 | Il pulsante **Approvazione** non funziona con i campi obbligatori impostati nel modulo **Rivedi**. | Quando si imposta un campo nel modulo **Rivedi** come obbligatorio e si pubblicano le modifiche per il ruolo di responsabile, il modulo non viene convalidato come previsto. |
| 559564 | Le azioni storiche dei lavoratori per la modifica della retribuzione fissa generano errori per gli utenti con rapporto di lavoro concluso. | L'azione lavoratore relativa alla retribuzione di un dipendente con rapporto di lavoro concluso genera un errore. Dopo che un dipendente conclude il rapporto di lavoro, l'azione lavoratore di promozione prima della conclusione del rapporto di lavoro genera un errore. |
| 560074 | Il menu a discesa della categoria di impiego non viene filtrato in **Tipo di lavoratore** e mostra le categorie per dipendenti e terzisti. | Nel modulo **Dipendente**, il menu a discesa **Categoria impiego** deve mostrare le categorie di dipendenti o terzisti, in base al tipo di lavoratore del dipendente. |
| 567388 | Alcune delle informazioni per i dipendenti appena creati non vengono sincronizzate immediatamente con la tabella **cdm_worker** in Dataverse. | Quando si crea un nuovo record di dipendente, il nuovo record viene sincronizzato con la tabella **cdm_worker** in Dataverse, ma non tutte le proprietà vengono incluse nel record Dataverse. |
| 563837 | Visualizzazione di funzionalità non disponibili in Human Resources. | Varie funzionalità che non si applicano a Human Resources sono visualizzate in Gestione funzionalità. Queste funzionalità non sono più incluse nell'elenco delle funzionalità disponibili da abilitare in Human Resources. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |

## <a name="coming-soon"></a>Presto disponibili

| Funzionalità | Dettagli |
| --- | --- |
| Le competenze immesse da un manager per i propri dipendenti possono essere approvate automaticamente da un flusso di lavoro | Presto disponibili. |
| Platform Update 10.0.17 (41) | L'implementazione dell'aggiornamento della piattaforma 10.0.17 inizierà con la prossima versione il 19 aprile 2021. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.17 delle app Finance and Operations (aprile 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md). |

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedi [Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]