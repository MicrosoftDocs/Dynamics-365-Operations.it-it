---
title: Inviare una richiesta di congedo a flusso di lavoro
description: In Microsoft Dynamics 365 Human Resources, è possibile utilizzare l'API MyLeaveRequests submit() per inviare una richiesta di congedo al flusso di lavoro.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7552a4c921dc4a88034b5d2c87d5a9b47d699ae3
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092016"
---
# <a name="submit-a-leave-request-to-workflow"></a>Inviare una richiesta di congedo a flusso di lavoro

In Microsoft Dynamics 365 Human Resources, è possibile utilizzare l'API MyLeaveRequests submit() per inviare una richiesta di congedo al flusso di lavoro. Questa API è esposta come azione nell'entità OData MyLeaveRequests.

## <a name="prerequisites"></a>Prerequisiti

La richiesta di congedo deve essere salvata nel database e deve essere recuperabile tramite l'entità MyLeaveRequests.

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessario disporre di una delle seguenti autorizzazioni. Per ulteriori informazioni sulle autorizzazioni e su come selezionarle, vedere [Autenticazione](hr-developer-api-authentication.md).

| Tipo di autorizzazione                    | Autorizzazioni (dalla meno privilegiata alla più privilegiata) |
|------------------------------------|--------------------------------------------------------|
| Delegata (account di lavoro o dell'istituto di istruzione) | user\_impersonation                                    |

## <a name="https-request"></a>Richiesta HTTPS

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

La richiesta è conforme agli standard OData. I parametri {requestId}, {leaveType}, {leaveDate} e {dataArea} si riferiscono ai campi che compongono la chiave naturale composita dell'entità MyLeaveRequests.

> [!NOTE]
> Sebbene i campi per l'entità MyLeaveRequests fanno riferimento a una singola riga nella richiesta di congedo, la chiamata dell'API di invio invia l'intera richiesta di congedo (tutte le righe) al flusso di lavoro.

### <a name="request-headers"></a>Intestazioni richieste

| Intestazione         | Value                     |
|----------------|---------------------------|
| Autorizzazione  | Portatore {token} (necessaria) |
| Content-Type   | application/json          |

### <a name="request-body"></a>Corpo della richiesta

Non fornire il corpo della richiesta per questo metodo.

### <a name="response"></a>Risposta

Una risposta positiva è sempre una risposta **204 Nessun contenuto**.

I chiamanti non autorizzati riceveranno una risposta **401 Non autorizzato** o a **403 Accesso negato**.

Se l'invio non ha esito positivo (ad esempio a causa della convalida), la risposta sarà **500 Errore del server** e il corpo della risposta includerà un oggetto JSON con ulteriori dettagli.

## <a name="example"></a>Esempio

```http
POST https://aos-rts-sf-550e5c091f6-prod-westus2.hr.talent.dynamics.com/namespaces/b2eb8003-334f-4a84-ab63-edbe23569090/data/MyLeaveRequests(RequestId='USMF-000065', LeaveType='Vacation', LeaveDate=2019-10-04T12:00:00Z, dataAreaId='USMF')/Microsoft.Dynamics.DataEntities.submit
```

```json
{
  "error": {
    "code": "",
    "message": "An error has occurred.",
    "innererror": {
      "message": "Exception occurred while executing action submit on Entity MyLeaveRequest: The request would put the 'Vacation' balance below the allowed minimum balance on 9/10/2019.",
      "type": "System.InvalidOperationException",
      "stacktrace": "   at Microsoft.Dynamics.Platform.Integration.Services.OData.Action.ActionInvokable.Invoke()   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.ActionInvocation(ChangeOperationContext context, ActionInvokable action)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass13_0.<ScheduleInvokable>b__0(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActions(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataDelegatingHandler.<SaveChangesAsync>d__3.MoveNext()"
    }
  }
}
```

## <a name="validation-and-error-messages"></a>Convalida e messaggi d'errore

Come parte della chiamata all'API di invio, Human Resources esegue la convalida della logica aziendale prima dell'invio e ciò garantisce che la richiesta di congedo sia in uno stato valido per l'invio. I messaggi di errore che si potrebbero ricevere nella risposta se le convalide non riescono sono:

 - La richieste comporterebbe l'inserimento del saldo '{LeaveTypeId}' sotto al saldo minimo consentito in {date}.
 - Impossibile inviare la richiesta di permesso con stato Completata.
 - Impossibile inviare o salvare la richiesta poiché non sono state apportate modifiche. Aggiungere o aggiornare l'importo o il tipo di congedo e riprovare.
 - La richiesta di sospensione immessa contiene uno o più giorni con la stessa data e il tipo di congedo come richiesta in sospeso esistente. Richiamare la richiesta esistente per apportare le modifiche.
 - Il codice motivo '{ReasonCodeId}' non si applica ad alcun tipo di congedo nella richiesta.
 - Il tipo di congedo "{LeaveTypeId}" richiede un codice motivo. Selezionare il tipo e il codice motivo appropriati.
 - Il permesso non è stato inviato correttamente. Il permesso è stato salvato come una richiesta di bozza.

## <a name="see-also"></a>Vedere anche

- [Panoramica di MyLeaveRequests](hr-developer-api-myleaverequests-overview.md)
- [Autenticazione](hr-developer-api-authentication.md)