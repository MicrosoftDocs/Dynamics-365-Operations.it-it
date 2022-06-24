---
title: Novità o modifiche in Dynamics 365 Human Resources 5 ottobre 2021
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 5 ottobre 2021.
author: marcelbf
ms.date: 10/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cc8cd8616f1b82258fccbb2b41d5e72a90aaed63
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845114"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-5-2021"></a>Novità o modifiche in Dynamics 365 Human Resources 5 ottobre 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive le funzionalità nuove, modificate o future di Microsoft Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle relative date di disponibilità generale previste, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4485.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
|---|---|---|
| Platform Update 10.0.21 (45) | -- | [Aggiornamenti della piattaforma per la versione 10.0.21 delle app per la finanza e le operazioni (ottobre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21) |


### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potremmo aggiornare questo articolo per includere le correzioni di bug che sono state inserite nella build dopo che questo articolo è stato inizialmente pubblicato.

| Numero problema | Problema | Description |
|---|---|---|
| 598896 | L'importo del dipendente non viene visualizzato fino a quando il dipendente non ha completato l'iscrizione | Nella pagina **Self-service dipendenti**, l'importo del dipendente per il benefit non è stato visualizzato. L'importo del dipendente viene ora visualizzato nella pagina **Self-service benefit**.  |
| 613440 | Impossibile esportare i dati da **Gestione dati** | Quando si esportano i dati per un progetto in **Gestione dati**, l'esportazione non riesce in modo imprevisto. |
| 618327 | I periodi chiusi e futuri sono visualizzati nella pagina **Parametri report** per il rendiconto benefit | Durante la navigazione verso **Rendiconto benefit** in **Self-service dipendenti**, la pagina **Parametri report** mostra le Schede dettaglio **Record da includere** ed **Esegui in background**. Queste sezioni sono state rimosse.|
| 618326 | La pagina **Parametri report** visualizzata per **Self-service dipendenti** per il rendiconto benefit non è corretta| Durante la navigazione verso la pagina di destinazione **Report rendiconto benefit**, l'utente era in grado di selezionare periodi dei piani di benefit chiusi o con data futura, che produce una pagina vuota. Nell'elenco dovrebbe essere visualizzato solo il periodo del piano di benefit corrente. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per maggiori informazioni su come attivare o disattivare le funzioni, vedi [Gestione delle funzioni](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
|---|---|---|
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Campi personalizzati in Idoneità |[Supporto per campi personalizzati per l'elaborazione dell'idoneità](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Utilizzo di campi personalizzati nell'elaborazione dell'idoneità](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |
| Rendiconto benefit |[Rendiconto benefit](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) | [Rendiconto benefit](hr-benefits-statement.md) |

### <a name="benefits-statement-known-issues"></a>Problemi noti di Rendiconto benefit

| Problema | Descrizione |
|---|---|
|Errore durante l'invio del report tramite posta elettronica utilizzando la **destinazione di report GER** | Il rendiconto benefit può essere impostato in modo da utilizzare i parametri di posta elettronica nella pagina **Destinazioni di report GER**. Quando si completa la configurazione e si stampa il report, l'utente riceverà un errore di formattazione e il report benefit non verrà inviato.|

## <a name="feature-management-changes"></a>Modifiche della gestione funzionalità

| Funzionalità | Descrizione |
|---|---|
|Visualizzazione report estesi di giornali di registrazione delle prestazioni | Questa funzionalità verrà abilitata per impostazione predefinita in questa versione. |

## <a name="coming-soon"></a>Presto disponibile

Per un elenco completo delle funzionalità pianificate e dei relativi rilasci programmati, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funzionalità | Dettagli |
|---|---|
| Platform Update 10.0.22 (46) | Il roll-out dell'aggiornamento 10.0.22 della piattaforma è previsto per iniziare con il rilascio del servizio il 1 novembre 2021. Per ulteriori informazioni, vedere [Aggiornamenti della piattaforma per la versione 10.0.22 delle app per la finanza e le operazioni (novembre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22). |



## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
