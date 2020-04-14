---
title: Risoluzione dei problemi durante la sincronizzazione iniziale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172716"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Risoluzione dei problemi durante la sincronizzazione iniziale

[!include [banner](../../includes/banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale. 

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Verificare la presenza di errori di sincronizzazione iniziale in un'app Finance and Operations

Dopo aver abilitato i modelli di mapping, lo stato delle mappe deve essere **In esecuzione**. Se lo stato è **Non in esecuzione**, si sono verificati errori durante la sincronizzazione iniziale. Per visualizzare gli errori, selezionare la scheda **Dettagli sulla sincronizzazione iniziale** nella pagina **Doppia scrittura**.

![Scheda dei dettagli della sincronizzazione iniziale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Impossibile completare la sincronizzazione iniziale: 400 Richiesta non valida

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di eseguire il mapping e la sincronizzazione iniziale:

*Il server remoto ha restituito un errore: (400) Richiesta non valida. Si è verificato un errore nell'esportazione AX*

Di seguito è riportato un esempio del messaggio di errore completo.

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

Se questo errore si verifica in modo coerente e non è possibile completare la sincronizzazione iniziale, attenersi alla seguente procedura per risolvere il problema.

1. Accedere alla macchina virtuale (VM) per l'app Finance and Operations.
2. Aprire la console di gestione Microsoft. 
3. Nel riquadro **Servizi**, assicurarsi che il servizio framework di importazione esportazione dati di Microsoft Dynamics 365 sia in esecuzione. Riavviarlo se è stato arrestato, poiché la sincronizzazione iniziale lo richiede.

## <a name="initial-synchronization-error-403-forbidden"></a>Errore di sincronizzazione iniziale: 403 Accesso negato

È possibile che venga visualizzato il seguente messaggio di errore durante la sincronizzazione iniziale:

*(\[Accesso negato\]. Il server remoto ha restituito un errore: (403) Accesso negato). Si è verificato un errore nell'esportazione AX*

Per risolvere il problema, procedere come segue.

1. Accedere all'app Finance and Operations.
2. Nella pagina **Applicazioni Azure Active Directory**, eliminare il client **DtAppID**, quindi aggiungerlo di nuovo.

![Elenco di applicazioni Azure AD](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a>Errori di riferimenti automatici durante la sincronizzazione iniziale

È possibile ricevere un messaggio di errore simile al seguente esempio se uno dei mapping include riferimenti automatici:

*Su Vendors V2, il seguente errore: ID record: nuovo record, ErrorMessage: impossibile risolvere il guid per il campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Il valore di ricerca non è stato trovato: CN-001. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq "CN-001"*

Questo tipo di errore si verifica durante la sincronizzazione iniziale dei mapping con riferimenti automatici. Nell'esempio precedente, il campo del conto fattura fa riferimento all'entità fornitore.

Per risolvere il problema, potrebbe essere necessario eseguire il mapping due volte prima che la sincronizzazione iniziale abbia esito positivo.

