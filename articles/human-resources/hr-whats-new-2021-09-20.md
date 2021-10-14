---
title: Novità o modifiche in Dynamics 365 Human Resources 20 settembre 2021
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 20 settembre 2021.
author: marcelbf
ms.date: 09/20/2021
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
ms.search.validFrom: 2021-09-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3f4fc4768f8c96678b216709f78af6d3ddfd4132
ms.sourcegitcommit: ba8ca42e43e1a5251cbbd6ddb292566164d735dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2021
ms.locfileid: "7556935"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-20-2021"></a>Novità o modifiche in Dynamics 365 Human Resources 20 settembre 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le caratteristiche che sono nuove, cambiate o in arrivo in Microsoft Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle relative date di disponibilità generale previste, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4464.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
|---|---|---|
| Abilitare l'integrazione delle retribuzioni semplificata (API di integrazione delle retribuzioni) | [Abilitare l'integrazionei semplificata con i fornitori retribuzioni](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md) |
| Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati | [Consentire ai dipendenti di essere contrassegnati come pronti per essere pagati](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Pronto per il pagamento](/dynamics365/human-resources/hr-compensation-payroll) |

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potremmo aggiornare questo argomento per includere le correzioni di bug che sono state inserite nella build dopo che questo argomento è stato inizialmente pubblicato.

| Numero problema | Problema | Descrizione |
|---|---|---|
| 619774 | La modifica della descrizione dell'indirizzo non viene sincronizzata in Dataverse in tempo reale. | Quando si modifica la descrizione per l'indirizzo di un lavoratore, la descrizione aggiornata non viene sincronizzata in tempo reale in Dataverse. La sottoscrizione nella tabella **Posizione logistica** è stata aggiornata per l'invio di un aggiornamento. |
| 614603| Errore nella pagina **Lavoratore** quando il parametro **Azioni personale lavoratori** non è selezionato. | Quando si assume un nuovo lavoratore o si passa alla pagina **Lavoratore**, viene visualizzato il seguente errore: "Il campo **Tipo di azione personale** deve essere compilato", anche se le **Azioni personale** sono disattivate. |
| 615367 | La scheda **Permesso approvato** mostra un avviso e viene visualizzato in modo errato. | Se l'unità di congedo è impostata su **Giorni** prima di abilitare la funzione **Configurare le unità di congedo per tipo di congedo**, la scheda **Permesso approvato** mostra un avviso non valido e colonne errate. |


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
| La pagina **Parametri report** in **Self-service dipendenti** per il rendiconto benefit non è corretta. | Durante la navigazione verso **Rendiconto benefit** in **Self-service dipendenti**, la pagina **Parametri report** mostra le Schede dettaglio **Record da includere** ed **Esegui in background**.  Queste devono essere rimosse. |
| I periodi chiusi e futuri sono visualizzati nella pagina **Parametro report** per il rendiconto benefit. | Durante la navigazione verso la pagina di destinazione **Report rendiconto benefit**, l'utente è in grado di selezionare periodi dei piani di benefit chiusi o con data futura, che produce una pagina vuota. Nell'elenco dovrebbe essere visualizzato solo il periodo del piano di benefit corrente. |
|Errore durante l'invio del report tramite posta elettronica utilizzando la destinazione di report GER. | Il rendiconto benefit può essere impostato in modo da utilizzare i parametri di posta elettronica all'interno della pagina **Destinazioni report GER**. Quando si completa la configurazione e si stampa il report, l'utente riceverà un errore di formattazione e il report benefit non verrà inviato.|


## <a name="coming-soon"></a>Presto disponibile

Per un elenco completo delle funzionalità pianificate e dei relativi rilasci programmati, vedi [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funzionalità | Dettagli |
|---|---|
| Platform Update 10.0.21 (45) | Il roll-out dell'aggiornamento 10.0.21 della piattaforma è previsto per iniziare con il rilascio del servizio il 4 ottobre 2021. Per maggiori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.21 di Finance and Operations apps (ottobre 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
|Visualizzazione report estesi di giornali di registrazione delle prestazioni | Questa funzionalità verrà abilitata per impostazione predefinita nella prossima implementazione. |


## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
