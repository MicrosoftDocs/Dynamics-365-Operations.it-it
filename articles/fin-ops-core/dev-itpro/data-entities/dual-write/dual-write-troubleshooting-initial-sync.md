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
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="510a5-103">Risoluzione dei problemi durante la sincronizzazione iniziale</span><span class="sxs-lookup"><span data-stu-id="510a5-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="510a5-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="510a5-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="510a5-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="510a5-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="510a5-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="510a5-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="510a5-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="510a5-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="510a5-108">Verificare la presenza di errori di sincronizzazione iniziale in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="510a5-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="510a5-109">Dopo aver abilitato i modelli di mapping, lo stato delle mappe deve essere **In esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="510a5-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="510a5-110">Se lo stato è **Non in esecuzione**, si sono verificati errori durante la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="510a5-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="510a5-111">Per visualizzare gli errori, selezionare la scheda **Dettagli sulla sincronizzazione iniziale** nella pagina **Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="510a5-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Scheda dei dettagli della sincronizzazione iniziale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="510a5-113">Impossibile completare la sincronizzazione iniziale: 400 Richiesta non valida</span><span class="sxs-lookup"><span data-stu-id="510a5-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="510a5-114">**Ruolo richiesto per risolvere il problema:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="510a5-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="510a5-115">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di eseguire il mapping e la sincronizzazione iniziale:</span><span class="sxs-lookup"><span data-stu-id="510a5-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="510a5-116">*Il server remoto ha restituito un errore: (400) Richiesta non valida. Si è verificato un errore nell'esportazione AX*</span><span class="sxs-lookup"><span data-stu-id="510a5-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="510a5-117">Di seguito è riportato un esempio del messaggio di errore completo.</span><span class="sxs-lookup"><span data-stu-id="510a5-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="510a5-118">Se questo errore si verifica in modo coerente e non è possibile completare la sincronizzazione iniziale, attenersi alla seguente procedura per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="510a5-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="510a5-119">Accedere alla macchina virtuale (VM) per l'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="510a5-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="510a5-120">Aprire la console di gestione Microsoft.</span><span class="sxs-lookup"><span data-stu-id="510a5-120">Open Microsoft Management Console.</span></span> 
3. <span data-ttu-id="510a5-121">Nel riquadro **Servizi**, assicurarsi che il servizio framework di importazione esportazione dati di Microsoft Dynamics 365 sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="510a5-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="510a5-122">Riavviarlo se è stato arrestato, poiché la sincronizzazione iniziale lo richiede.</span><span class="sxs-lookup"><span data-stu-id="510a5-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="510a5-123">Errore di sincronizzazione iniziale: 403 Accesso negato</span><span class="sxs-lookup"><span data-stu-id="510a5-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="510a5-124">È possibile che venga visualizzato il seguente messaggio di errore durante la sincronizzazione iniziale:</span><span class="sxs-lookup"><span data-stu-id="510a5-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="510a5-125">*(\[Accesso negato\]. Il server remoto ha restituito un errore: (403) Accesso negato). Si è verificato un errore nell'esportazione AX*</span><span class="sxs-lookup"><span data-stu-id="510a5-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="510a5-126">Per risolvere il problema, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="510a5-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="510a5-127">Accedere all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="510a5-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="510a5-128">Nella pagina **Applicazioni Azure Active Directory**, eliminare il client **DtAppID**, quindi aggiungerlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="510a5-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Elenco di applicazioni Azure AD](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a><span data-ttu-id="510a5-130">Errori di riferimenti automatici durante la sincronizzazione iniziale</span><span class="sxs-lookup"><span data-stu-id="510a5-130">Self-reference failures during initial synchronization</span></span>

<span data-ttu-id="510a5-131">È possibile ricevere un messaggio di errore simile al seguente esempio se uno dei mapping include riferimenti automatici:</span><span class="sxs-lookup"><span data-stu-id="510a5-131">You might receive an error message that resembles the following example if any of your mappings have self-references:</span></span>

<span data-ttu-id="510a5-132">*Su Vendors V2, il seguente errore: ID record: nuovo record, ErrorMessage: impossibile risolvere il guid per il campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Il valore di ricerca non è stato trovato: CN-001. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq "CN-001"*</span><span class="sxs-lookup"><span data-stu-id="510a5-132">*On the Vendors V2, the following error: Record Id: new record, ErrorMessage: Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup value was not found: CN-001. Try this URL(s) to check if the reference data exists: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span></span>

<span data-ttu-id="510a5-133">Questo tipo di errore si verifica durante la sincronizzazione iniziale dei mapping con riferimenti automatici.</span><span class="sxs-lookup"><span data-stu-id="510a5-133">This type of error occurs during initial synchronization of mappings that have self-references.</span></span> <span data-ttu-id="510a5-134">Nell'esempio precedente, il campo del conto fattura fa riferimento all'entità fornitore.</span><span class="sxs-lookup"><span data-stu-id="510a5-134">In the preceding example, the field invoice account references the vendor entity.</span></span>

<span data-ttu-id="510a5-135">Per risolvere il problema, potrebbe essere necessario eseguire il mapping due volte prima che la sincronizzazione iniziale abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="510a5-135">To fix the issue, you might have to run the mapping two times before the initial synchronization is successful.</span></span>

