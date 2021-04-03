---
title: Inviare una richiesta di congedo a flusso di lavoro
description: In Microsoft Dynamics 365 Human Resources, è possibile utilizzare l'API MyLeaveRequests submit() per inviare una richiesta di congedo al flusso di lavoro.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: aeb3d66ad24f96efea1b0ea9828a537f8853c94b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465488"
---
# <a name="submit-a-leave-request-to-workflow"></a><span data-ttu-id="d4cc2-103">Inviare una richiesta di congedo a flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d4cc2-103">Submit a leave request to workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d4cc2-104">In Microsoft Dynamics 365 Human Resources, è possibile utilizzare l'API MyLeaveRequests submit() per inviare una richiesta di congedo al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-104">In Microsoft Dynamics 365 Human Resources, you can use the MyLeaveRequests submit() application programming interface (API) to submit a leave request to workflow.</span></span> <span data-ttu-id="d4cc2-105">Questa API è esposta come azione nell'entità OData MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-105">This API is exposed as an action on the MyLeaveRequests OData entity.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d4cc2-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d4cc2-106">Prerequisites</span></span>

<span data-ttu-id="d4cc2-107">La richiesta di congedo deve essere salvata nel database e deve essere recuperabile tramite l'entità MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-107">The leave request must be saved in the database and must be retrievable through the MyLeaveRequests entity.</span></span>

## <a name="permissions"></a><span data-ttu-id="d4cc2-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d4cc2-108">Permissions</span></span>

<span data-ttu-id="d4cc2-109">Per chiamare questa API è necessario disporre di una delle seguenti autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-109">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d4cc2-110">Per ulteriori informazioni sulle autorizzazioni e su come selezionarle, vedere [Autenticazione](hr-developer-api-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d4cc2-110">For more information about permissions and how to select them, see [Authentication](hr-developer-api-authentication.md).</span></span>

| <span data-ttu-id="d4cc2-111">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d4cc2-111">Permission type</span></span>                    | <span data-ttu-id="d4cc2-112">Autorizzazioni (dalla meno privilegiata alla più privilegiata)</span><span class="sxs-lookup"><span data-stu-id="d4cc2-112">Permissions (from least privileged to most privileged)</span></span> |
|------------------------------------|--------------------------------------------------------|
| <span data-ttu-id="d4cc2-113">Delegata (account di lavoro o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="d4cc2-113">Delegated (work or school account)</span></span> | <span data-ttu-id="d4cc2-114">user\_impersonation</span><span class="sxs-lookup"><span data-stu-id="d4cc2-114">user\_impersonation</span></span>                                    |

## <a name="https-request"></a><span data-ttu-id="d4cc2-115">Richiesta HTTPS</span><span class="sxs-lookup"><span data-stu-id="d4cc2-115">HTTPS request</span></span>

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

<span data-ttu-id="d4cc2-116">La richiesta è conforme agli standard OData.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-116">The request conforms to OData standards.</span></span> <span data-ttu-id="d4cc2-117">I parametri {requestId}, {leaveType}, {leaveDate} e {dataArea} si riferiscono ai campi che compongono la chiave naturale composita dell'entità MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-117">The {requestId}, {leaveType}, {leaveDate}, and {dataArea} parameters refer to the fields that make up the composite natural key for the MyLeaveRequests entity.</span></span>

> [!NOTE]
> <span data-ttu-id="d4cc2-118">Sebbene i campi per l'entità MyLeaveRequests fanno riferimento a una singola riga nella richiesta di congedo, la chiamata dell'API di invio invia l'intera richiesta di congedo (tutte le righe) al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-118">While the fields for the MyLeaveRequests entity refer to an individual line in the leave request, calling the submit API will submit the entire leave request (all lines) to workflow.</span></span>

### <a name="request-headers"></a><span data-ttu-id="d4cc2-119">Intestazioni richieste</span><span class="sxs-lookup"><span data-stu-id="d4cc2-119">Request headers</span></span>

| <span data-ttu-id="d4cc2-120">Intestazione</span><span class="sxs-lookup"><span data-stu-id="d4cc2-120">Header</span></span>         | <span data-ttu-id="d4cc2-121">Value</span><span class="sxs-lookup"><span data-stu-id="d4cc2-121">Value</span></span>                     |
|----------------|---------------------------|
| <span data-ttu-id="d4cc2-122">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d4cc2-122">Authorization</span></span>  | <span data-ttu-id="d4cc2-123">Portatore {token} (necessaria)</span><span class="sxs-lookup"><span data-stu-id="d4cc2-123">Bearer {token} (required)</span></span> |
| <span data-ttu-id="d4cc2-124">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d4cc2-124">Content-Type</span></span>   | <span data-ttu-id="d4cc2-125">application/json</span><span class="sxs-lookup"><span data-stu-id="d4cc2-125">application/json</span></span>          |

### <a name="request-body"></a><span data-ttu-id="d4cc2-126">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="d4cc2-126">Request body</span></span>

<span data-ttu-id="d4cc2-127">Non fornire il corpo della richiesta per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-127">Don't supply a request body for this method.</span></span>

### <a name="response"></a><span data-ttu-id="d4cc2-128">Risposta</span><span class="sxs-lookup"><span data-stu-id="d4cc2-128">Response</span></span>

<span data-ttu-id="d4cc2-129">Una risposta positiva è sempre una risposta **204 Nessun contenuto**.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-129">A successful response is always a **204 No Content** response.</span></span>

<span data-ttu-id="d4cc2-130">I chiamanti non autorizzati riceveranno una risposta **401 Non autorizzato** o a **403 Accesso negato**.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-130">Unauthorized callers will receive a **401 Unauthorized** or a **403 Forbidden** response.</span></span>

<span data-ttu-id="d4cc2-131">Se l'invio non ha esito positivo (ad esempio a causa della convalida), la risposta sarà **500 Errore del server** e il corpo della risposta includerà un oggetto JSON con ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-131">If submission is unsuccessful (because of validation, for example), the response will be a **500 Server Error**, and the response body will include a JSON object with further details.</span></span>

## <a name="example"></a><span data-ttu-id="d4cc2-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4cc2-132">Example</span></span>

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

## <a name="validation-and-error-messages"></a><span data-ttu-id="d4cc2-133">Convalida e messaggi d'errore</span><span class="sxs-lookup"><span data-stu-id="d4cc2-133">Validation and error messages</span></span>

<span data-ttu-id="d4cc2-134">Come parte della chiamata all'API di invio, Human Resources esegue la convalida della logica aziendale prima dell'invio e ciò garantisce che la richiesta di congedo sia in uno stato valido per l'invio.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-134">As part of the call to the submit API, Human Resources performs business logic validation before submission, which ensures the leave request is in a valid state for submission.</span></span> <span data-ttu-id="d4cc2-135">I messaggi di errore che si potrebbero ricevere nella risposta se le convalide non riescono sono:</span><span class="sxs-lookup"><span data-stu-id="d4cc2-135">The possible error messages you may receive in the response if validations fail are:</span></span>

 - <span data-ttu-id="d4cc2-136">La richieste comporterebbe l'inserimento del saldo '{LeaveTypeId}' sotto al saldo minimo consentito in {date}.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-136">The request would put the '{LeaveTypeId}' balance below the allowed minimum balance on {date}.</span></span>
 - <span data-ttu-id="d4cc2-137">Impossibile inviare la richiesta di permesso con stato Completata.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-137">Time off request in Completed state cannot be submitted.</span></span>
 - <span data-ttu-id="d4cc2-138">Impossibile inviare o salvare la richiesta poiché non sono state apportate modifiche.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-138">Unable to submit or save request as no changes have been made.</span></span> <span data-ttu-id="d4cc2-139">Aggiungere o aggiornare l'importo o il tipo di congedo e riprovare.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-139">Add or update the amount or the leave type and try again.</span></span>
 - <span data-ttu-id="d4cc2-140">La richiesta di sospensione immessa contiene uno o più giorni con la stessa data e il tipo di congedo come richiesta in sospeso esistente.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-140">The time off request entered contains one or more days with the same date and leave type as an existing pending request.</span></span> <span data-ttu-id="d4cc2-141">Richiamare la richiesta esistente per apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-141">Please recall the existing request to make changes.</span></span>
 - <span data-ttu-id="d4cc2-142">Il codice motivo '{ReasonCodeId}' non si applica ad alcun tipo di congedo nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-142">Reason code '{ReasonCodeId}' doesn't apply to any of the leave types in the request.</span></span>
 - <span data-ttu-id="d4cc2-143">Il tipo di congedo "{LeaveTypeId}" richiede un codice motivo.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-143">Leave type '{LeaveTypeId}' requires a reason code.</span></span> <span data-ttu-id="d4cc2-144">Selezionare il tipo e il codice motivo appropriati.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-144">Select the appropriate type and reason code.</span></span>
 - <span data-ttu-id="d4cc2-145">Il permesso non è stato inviato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-145">The time off was not submitted successfully.</span></span> <span data-ttu-id="d4cc2-146">Il permesso è stato salvato come una richiesta di bozza.</span><span class="sxs-lookup"><span data-stu-id="d4cc2-146">The time off has been saved as a draft request.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4cc2-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4cc2-147">See also</span></span>

- [<span data-ttu-id="d4cc2-148">Panoramica di MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="d4cc2-148">MyLeaveRequests overview</span></span>](hr-developer-api-myleaverequests-overview.md)
- [<span data-ttu-id="d4cc2-149">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="d4cc2-149">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]