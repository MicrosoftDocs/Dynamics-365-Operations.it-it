---
title: Cosa c'è di nuovo o cambiato in Dynamics 365 Human Resources 9 agosto 2021
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 9 agosto 2021.
author: marcelbf
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-08-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 58926e5a6c1476db84fa41945dc92196eb24f4bf
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068456"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-9-2021"></a>Cosa c'è di nuovo o cambiato in Dynamics 365 Human Resources 9 agosto 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive le funzionalità nuove, modificate o future di Microsoft Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle relative date di disponibilità generale previste, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4393.

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potremmo aggiornare questo articolo per includere le correzioni di bug che sono state inserite nella build dopo che questo articolo è stato inizialmente pubblicato.

| Numero problema | Problema | Description |
| --- | --- | --- |
| 558385 | Il destinatario predefinito non viene selezionato quando l'opzione **Selezione automatica dei destinatari** è attivata per i destinatari predefiniti. | Questo problema è ora risolto. Più destinatari predefiniti vengono selezionati automaticamente nei piani idonei quando l'opzione **Seleziona automaticamente i destinatari** nella pagina dei **parametri condivisi delle Risorse umane** è attivata. |
| 589617 | Nella pagina **Permesso** , i saldi **Disponibili per l'acquisto** e **Disponibili per la vendita** sono vuoti quando l'accesso è limitato a una specifica azienda. | Questo problema è ora risolto. La pagina **Permesso** mostra i saldi corretti di **Disponibili per l'acquisto** e **Disponibili per la vendita** quando l'utente è limitato a una specifica azienda. |

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
| Platform Update 10.0.21 (45) | Il roll-out dell'aggiornamento 10.0.21 della piattaforma è previsto per iniziare con il rilascio del servizio il 4 ottobre 2021. Per ulteriori informazioni, vedere [Aggiornamenti della piattaforma per la versione 10.0.21 delle app per la finanza e le operazioni (ottobre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

