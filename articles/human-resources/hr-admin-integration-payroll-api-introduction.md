---
title: Introduzione all'API di integrazione retribuzioni
description: Questo argomento descrive l'API di integrazione retribuzioni di Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6d8a1cb9619a863184460a74e472af3f06934b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058562"
---
# <a name="payroll-integration-api-introduction"></a>Introduzione all'API di integrazione retribuzioni

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo documento descrive l'API di integrazione retribuzioni di Dynamics 365 Human Resources. L'API consente integrazioni end-to-end ottimizzate tra Human Resources e i sistemi di gestione delle retribuzioni dei partner. L'esperienza integrata inizia in Human Resources con il profilo del dipendente, lo stipendio e le detrazioni e le informazioni sui contributi. Quando si assume un dipendente e si immettono il profilo richiesto e le informazioni sulla retribuzione in Human Resources, il sistema delle retribuzioni estrae queste informazioni per utilizzarle durante l'elaborazione delle retribuzioni. Anche gli eventuali aggiornamenti alle informazioni sul dipendente o sulle retribuzioni vengono estratti per essere utilizzati nei cicli di pagamenti successivi.

![Flusso di integrazione delle retribuzioni](media/hr-admin-integration-payroll-api-introduction-flow.png)

Per abilitare l'integrazione, Human Resources include i seguenti componenti:

- Funzionalità per contrassegnare un dipendente come Pronto per il pagamento
- Un'API di integrazione che apre le nuove funzionalità alle applicazioni di integrazione

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Questa API è creata su Microsoft Dataverse (in precedenza Common Data Service). Tutta l'interazione RESTful con questa API viene eseguita tramite l'API Web Microsoft Dataverse, che utilizza OData. Questa API è un sottoinsieme di API Web Dataverse. L'API Web Dataverse definisce caratteristiche quali autenticazione, SLA, batch, controllo della concorrenza e gestione degli errori.

Per ulteriori informazioni generali sull'API Web Microsoft Dataverse, vedi:

- [Che cos'è Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)
- [Usa l'API Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)
- [Guida per gli sviluppatori Microsoft Dataverse](/powerapps/developer/data-platform)

Questa documentazione include dettagli e indicazioni per sviluppatori per l'utilizzo dell'API web di Dataverse, inclusi i seguenti argomenti:

- [Autenticare in Microsoft Dataverse con l'API Web](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [Eseguire operazioni utilizzando l'API Web](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [Usare Postman con l'API Web](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [Utilizzare il rilevamento delle modifiche per sincronizzare i dati con sistemi esterni](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Tabelle virtuali per Human Resources in Dataverse

Gli endpoint per l'API di integrazione retribuzioni utilizzano le funzionalità della piattaforma di tabelle virtuali di Microsoft Dataverse. Per impostazione predefinita, le tabelle virtuali e gli endpoint API associati non vengono distribuiti per gli ambienti Human Resources, consentendo alle organizzazioni di determinare quali endpoint OData saranno esposti per l'ambiente. Per utilizzare l'API, le tabelle virtuali per le entità Human Resources devono essere generate per l'ambiente.

Per informazioni sulla generazione delle tabelle virtuali per l'API, vedi [Configura tabelle virtuali Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="data-model"></a>Modello dati

Nel diagramma riportato di seguito vengono illustrate le relazioni all'interno dell'API. Diversi tipi hanno chiavi esterne per altre entità preesistenti in Human Resources che non sono illustrate qui. Questo documento fornisce informazioni sulle entità specifiche per gli scenari di integrazione delle retribuzioni. Tuttavia, ci sono molte altre entità nell'API Web di Dataverse per Human Resources potrebbe anche essere rilevante per la tua integrazione. Alcune di queste entità sono referenziate in relazioni di chiavi esterne o proprietà di navigazione.

![Modello di dati dell'API di integrazione retribuzioni](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a>Dipendente retribuzioni e entità correlate

Entità:

- [Dipendente retribuzioni](hr-admin-integration-payroll-api-payroll-employee.md)
- [Indirizzo lavoratore retribuzioni](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [Piano di retribuzione fissa retribuzioni](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Mansione posizione di retribuzione](hr-admin-integration-payroll-api-payroll-position-job.md)
- [Posizione di retribuzione](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a>Vedere anche

[Generare ed esaminare le entità retribuzioni](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[Configurare i parametri di Human Resources](hr-setup-parameters.md)<br>
[Configurare i parametri condivisi di Human Resources](hr-setup-shared-parameters.md)<br>
[Che cos'è Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Usa l'API Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]