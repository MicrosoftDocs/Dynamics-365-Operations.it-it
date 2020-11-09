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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 4d0ca1fb4b7a4964194516544686b6bb7d26e76c
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997328"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="6d4f9-103">Risoluzione dei problemi durante la sincronizzazione iniziale</span><span class="sxs-lookup"><span data-stu-id="6d4f9-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6d4f9-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="6d4f9-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d4f9-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="6d4f9-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="6d4f9-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="6d4f9-108">Verificare la presenza di errori di sincronizzazione iniziale in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6d4f9-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="6d4f9-109">Dopo aver abilitato i modelli di mapping, lo stato delle mappe deve essere **In esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="6d4f9-110">Se lo stato è **Non in esecuzione** , si sono verificati errori durante la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-110">If the status is **Not running** , errors occurred during initial synchronization.</span></span> <span data-ttu-id="6d4f9-111">Per visualizzare gli errori, selezionare la scheda **Dettagli sulla sincronizzazione iniziale** nella pagina **Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Errore nella scheda dei dettagli della sincronizzazione iniziale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="6d4f9-113">Impossibile completare la sincronizzazione iniziale: 400 Richiesta non valida</span><span class="sxs-lookup"><span data-stu-id="6d4f9-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="6d4f9-114">**Ruolo richiesto per risolvere il problema:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="6d4f9-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="6d4f9-115">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di eseguire il mapping e la sincronizzazione iniziale:</span><span class="sxs-lookup"><span data-stu-id="6d4f9-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="6d4f9-116">*(\[Richiesta non valida\]. Il server remoto ha restituito un errore: (400) Richiesta non valida). Si è verificato un errore nell'esportazione AX*</span><span class="sxs-lookup"><span data-stu-id="6d4f9-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="6d4f9-117">Di seguito è riportato un esempio del messaggio di errore completo.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="6d4f9-118">Se questo errore si verifica in modo coerente e non è possibile completare la sincronizzazione iniziale, attenersi alla seguente procedura per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="6d4f9-119">Accedere alla macchina virtuale (VM) per l'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="6d4f9-120">Aprire la console di gestione Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="6d4f9-121">Nel riquadro **Servizi** , assicurarsi che il servizio framework di importazione esportazione dati di Microsoft Dynamics 365 sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="6d4f9-122">Riavviarlo se è stato arrestato, poiché la sincronizzazione iniziale lo richiede.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="6d4f9-123">Errore di sincronizzazione iniziale: 403 Accesso negato</span><span class="sxs-lookup"><span data-stu-id="6d4f9-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="6d4f9-124">È possibile che venga visualizzato il seguente messaggio di errore durante la sincronizzazione iniziale:</span><span class="sxs-lookup"><span data-stu-id="6d4f9-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="6d4f9-125">*(\[Accesso negato\]. Il server remoto ha restituito un errore: (403) Accesso negato). Si è verificato un errore nell'esportazione AX*</span><span class="sxs-lookup"><span data-stu-id="6d4f9-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="6d4f9-126">Per risolvere il problema, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="6d4f9-127">Accedere all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="6d4f9-128">Nella pagina **Applicazioni Azure Active Directory** , eliminare il client **DtAppID** , quindi aggiungerlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Client DtAppID nell'elenco di applicazioni Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="6d4f9-130">Errori di riferimento automatico o di riferimento circolare durante la sincronizzazione iniziale</span><span class="sxs-lookup"><span data-stu-id="6d4f9-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="6d4f9-131">È possibile ricevere un messaggio di errore se uno dei mapping include riferimenti automatici o circulari.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="6d4f9-132">Gli errori rientrano in queste categorie:</span><span class="sxs-lookup"><span data-stu-id="6d4f9-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="6d4f9-133">Errori nel mapping dell'entità Fornitori V2 per msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="6d4f9-133">Errors in the Vendors V2–to–msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="6d4f9-134">Errori nel mapping dell'entità Clienti V3 per Account</span><span class="sxs-lookup"><span data-stu-id="6d4f9-134">Errors in the Customers V3–to–Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="6d4f9-135">Risolvere gli errori nel mapping dell'entità Fornitori V2 per msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="6d4f9-135">Resolve errors in the Vendors V2–to–msdyn_vendors entity mapping</span></span>

<span data-ttu-id="6d4f9-136">È possibile che si verifichino errori di sincronizzazione iniziale per il mapping dell'entità **Fornitori V2** all'entità **msdyn\_vendors** se le entità hanno record esistenti con valori nei campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the entities have existing records where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="6d4f9-137">Questi errori si verificano perché **InvoiceVendorAccountNumber** è un campo di riferimento automatico e **PrimaryContactPersonId** è un riferimento circolare nel mapping del fornitore.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="6d4f9-138">I messaggi di errore che si ricevono avranno il seguente formato.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="6d4f9-139">*Impossibile risolvere il guid per il campo: \<field\>. La ricerca non è stata trovata: \<value\>. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="6d4f9-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="6d4f9-140">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-140">Here are some examples:</span></span>

- <span data-ttu-id="6d4f9-141">*Impossibile risolvere il guid per il campo: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="6d4f9-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="6d4f9-142">*Impossibile risolvere il guid per il campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. La ricerca non è stata trovata: V24-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="6d4f9-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="6d4f9-143">Se i record nell'entità fornitore hanno valori nei campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** , seguire questi passaggi per completare la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-143">If any records in the vendor entity have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="6d4f9-144">Nell'app Finance and Operations, eliminare i campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** dal mapping e salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="6d4f9-145">Nella pagina del mapping in doppia scrittura per **Fornitori V2 (msdyn\_vendors)** e selezionare la scheda **Mapping entità**. Nel filtro a sinistra, selezionare **Finance and Operations apps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)** , on the **Entity mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="6d4f9-146">Nel filtro di destra, selezionare **Vendite.Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="6d4f9-147">Cercare **primarycontactperson** per trovare il campo di origine **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source field.</span></span>
    3. <span data-ttu-id="6d4f9-148">Selezionare **Azioni** , quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-148">Select **Actions** , and then select **Delete**.</span></span>

        ![Eliminazione del campo PrimaryContactPersonId](media/vend_selfref3.png)

    4. <span data-ttu-id="6d4f9-150">Ripetere questi passaggi per eliminare il campo **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** field.</span></span>

        ![Eliminazione del campo InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. <span data-ttu-id="6d4f9-152">Salvare le modifiche nel mapping.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="6d4f9-153">Disattivare il rilevamento delle modifiche per l'entità **Fornitori V2**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-153">Turn off change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="6d4f9-154">Nell'area di lavoro **Gestione dati** selezionare la scheda **Entità di dati**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-154">In the **Data management** workspace, select the **Data entities** tile.</span></span>
    2. <span data-ttu-id="6d4f9-155">Selezionare l'entità **Fornitori V2**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-155">Select the **Vendors V2** entity.</span></span>
    3. <span data-ttu-id="6d4f9-156">Nel riquadro azioni selezionare **Opzioni** , quindi selezionare **Rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-156">On the Action Pane, select **Options** , and then select **Change tracking**.</span></span>

        ![Selezione dell'opzione Rilevamento modifiche](media/selfref_options.png)

    4. <span data-ttu-id="6d4f9-158">Selezionare **Disabilita rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-158">Select **Disable Change Tracking**.</span></span>

        ![Selezione di Disabilita rilevamento modifiche](media/selfref_tracking.png)

3. <span data-ttu-id="6d4f9-160">Eseguire la sincronizzazione iniziale per il mapping **Fornitori V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="6d4f9-161">La sincronizzazione iniziale deve essere eseguita correttamente senza errori.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="6d4f9-162">Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="6d4f9-163">È necessario sincronizzare questo mapping se si desidera sincronizzare il campo di contatto primario nell'entità fornitori perché la sincronizzazione deve essere eseguita anche per i record di contatti.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-163">You must sync this mapping if you want to sync the primary contact field on the vendors entity, because initial synchronization must also be done for the contact records.</span></span>
5. <span data-ttu-id="6d4f9-164">Aggiungere di nuovo i campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** al mapping **Fornitori V2 (msdyn\_vendors)** e salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="6d4f9-165">Eseguire di nuovo la sincronizzazione iniziale per il mapping **Fornitori V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="6d4f9-166">Tutti i record verranno sincronizzati perché il rilevamento delle modifiche è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-166">Because change tracking is turned off, all the records will be synced.</span></span>
7. <span data-ttu-id="6d4f9-167">Attivare di nuovo il rilevamento delle modifiche per l'entità **Fornitori V2**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-167">Turn change tracking back on for the **Vendors V2** entity.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="6d4f9-168">Risolvere gli errori nel mapping dell'entità Clienti V3 all'entità Account</span><span class="sxs-lookup"><span data-stu-id="6d4f9-168">Resolve errors in the Customers V3–to–Accounts entity mapping</span></span>

<span data-ttu-id="6d4f9-169">È possibile che si verifichino errori di sincronizzazione iniziale per il mapping dell'entità **Clienti V3** all'entità **Account** se le entità hanno record esistenti con valori nei campi **ContactPersonID** e **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the entities have existing records where there are values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="6d4f9-170">Questi errori si verificano perché **InvoiceAccount** è un campo di riferimento automatico e **ContactPersonID** è un riferimento circolare nel mapping del fornitore.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-170">These errors occur because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="6d4f9-171">I messaggi di errore che si ricevono avranno il seguente formato.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="6d4f9-172">*Impossibile risolvere il guid per il campo: \<field\>. La ricerca non è stata trovata: \<value\>. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="6d4f9-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="6d4f9-173">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-173">Here are some examples:</span></span>

- <span data-ttu-id="6d4f9-174">*Impossibile risolvere il guid per il campo: primarycontactid.msdyn\_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="6d4f9-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="6d4f9-175">*Impossibile risolvere il guid per il campo: msdyn\_billingaccount.accountnumber. La ricerca non è stata trovata: 1206-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="6d4f9-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="6d4f9-176">Se i record nell'entità cliente hanno valori nei campi **ContactPersonID** e **InvoiceAccount** , seguire questi passaggi per completare la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-176">If any records in the customer entity have values in the **ContactPersonID** and **InvoiceAccount** fields, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="6d4f9-177">È possibile utilizzare questo approccio per tutte le entità predefinite come **Account** e **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-177">You can use this approach for any out-of-box entities, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="6d4f9-178">Nell'app Finance and Operations, eliminare i campi **ContactPersonID** e **InvoiceAccount** dal mapping **Clienti V3 (account)** e quindi salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** fields from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="6d4f9-179">Nella pagina del mapping in doppia scrittura per **Clienti V3 (account)** , selezionare la scheda **Mapping entità** e nel filtro a sinistra, selezionare **App Finance and Operations.Clienti V3**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-179">On the dual-write mapping page for **Customers V3 (accounts)** , on the **Entity mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="6d4f9-180">Nel filtro a destra, selezionare **Common Data Service.Account**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-180">In the right filter, select **Common Data Service.Account**.</span></span>
    2. <span data-ttu-id="6d4f9-181">Cercare **contactperson** per trovare il campo di origine **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-181">Search for **contactperson** to find the **ContactPersonID** source field.</span></span>
    3. <span data-ttu-id="6d4f9-182">Selezionare **Azioni** , quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-182">Select **Actions** , and then select **Delete**.</span></span>

        ![Eliminazione del campo ContactPersonID](media/cust_selfref3.png)

    4. <span data-ttu-id="6d4f9-184">Ripetere questi passaggi per eliminare il campo **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-184">Repeat these steps to delete the **InvoiceAccount** field.</span></span>

        ![Eliminazione del campo InvoiceAccount](media/cust_selfref4.png)

    5. <span data-ttu-id="6d4f9-186">Salvare le modifiche nel mapping.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="6d4f9-187">Disattivare il rilevamento delle modifiche per l'entità **Clienti V3**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-187">Turn off change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="6d4f9-188">Nell'area di lavoro **Gestione dati** selezionare la scheda **Entità di dati**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-188">In the **Data management** workspace, select the **Data entities** tile.</span></span>
    2. <span data-ttu-id="6d4f9-189">Selezionare l'entità **Clienti V3**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-189">Select the **Customers V3** entity.</span></span>
    3. <span data-ttu-id="6d4f9-190">Nel riquadro azioni selezionare **Opzioni** , quindi selezionare **Rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-190">On the Action Pane, select **Options** , and then select **Change tracking**.</span></span>

        ![Selezione dell'opzione Rilevamento modifiche](media/selfref_options.png)

    4. <span data-ttu-id="6d4f9-192">Selezionare **Disabilita rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-192">Select **Disable Change Tracking**.</span></span>

        ![Selezione di Disabilita rilevamento modifiche](media/selfref_tracking.png)

3. <span data-ttu-id="6d4f9-194">Eseguire la sincronizzazione iniziale per il mapping **Clienti V3 (account)**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="6d4f9-195">La sincronizzazione iniziale deve essere eseguita correttamente senza errori.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="6d4f9-196">Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6d4f9-197">Sono presenti due mappe con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-197">There are two maps that have the same name.</span></span> <span data-ttu-id="6d4f9-198">Assicurarsi di selezionare la mappa con la descrizione **Modello in doppia scrittura per la sincronizzazione tra Contatti fornitore FO.CDS V2 e CDS.Contatti. Necessita un nuovo pacchetto \[Dynamics365SupplyChainExtended\] nella scheda** **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="6d4f9-199">Aggiungere di nuovo i campi **ContactPersonID** e **InvoiceAccount** al mapping **Clienti V3 (account)** e quindi salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-199">Add the **InvoiceAccount** and **ContactPersonId** fields back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="6d4f9-200">I campi **InvoiceAccount** e **ContactPersonId** fanno di nuovo parte della modalità di sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-200">Both the **InvoiceAccount** field and the **ContactPersonId** field are now part of live synchronization mode again.</span></span> <span data-ttu-id="6d4f9-201">Nel passaggio successivo, eseguire la sincronizzazione iniziale per questi campi.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-201">In the next step, you will do the initial synchronization for these fields.</span></span>
6. <span data-ttu-id="6d4f9-202">Eseguire di nuovo la sincronizzazione iniziale per il mapping **Clienti V3 (account)**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="6d4f9-203">Poiché il rilevamento delle modifiche è disattivato, i dati per **InvoiceAccount** e **ContactPersonId** vengono sincronizzati dall'app Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Common Data Service.</span></span>
7. <span data-ttu-id="6d4f9-204">Per sincronizzare i dati per **InvoiceAccount** e **ContactPersonId** da Common Data Service all'app Finance and Operations, è necessario utilizzare un progetto di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="6d4f9-205">In Power Apps, creare un progetto di integrazione dei dati tra le entità **Vendite.Account** e **Finance and Operations apps.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="6d4f9-206">La direzione dei dati deve essere da Common Data Service all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-206">The data direction must be from Common Data Service to the Finance and Operations app.</span></span> <span data-ttu-id="6d4f9-207">Poiché **InvoiceAccount** è un nuovo attributo in doppia scrittura, è possibile che si voglia ignorare la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="6d4f9-208">Per ulteriori informazioni, vedere [Integrare dati in Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="6d4f9-208">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="6d4f9-209">La figura seguente mostra un progetto che aggiorna **CustomerAccount** e **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Progetto di integrazione dei dati per aggiornare CustomerAccount e ContactPersonId](media/cust_selfref6.png)

    2. <span data-ttu-id="6d4f9-211">Aggiungere i criteri dell'azienda nel filtro sul lato Common Data Service in modo che solo i record che soddisfano i criteri di filtro verranno aggiornati nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-211">Add the company criteria in the filter on the Common Data Service side, so that only records that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="6d4f9-212">Per aggiungere un filtro, selezionare il pulsante del filtro.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="6d4f9-213">Nella finestra di dialogo **Modifica query** , è possibile aggiungere una query filtro come **\_msdyn\_company\_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="6d4f9-214">[NOTA] Se il pulsante del filtro non è presente, creare un ticket di supporto per chiedere al team di integrazione dei dati di abilitare la funzionalità sul tenant.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="6d4f9-215">Se non si immette una query filtro per **\_msdyn\_company\_value** , tutti i record vengono sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-215">If you don't enter a filter query for **\_msdyn\_company\_value** , all the records will be synced.</span></span>

        ![Aggiunta di una query filtro](media/cust_selfref7.png)

    <span data-ttu-id="6d4f9-217">La sincronizzazione iniziale dei record è ora completata.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-217">The initial synchronization of the records is now completed.</span></span>

8. <span data-ttu-id="6d4f9-218">Abilitare di nuovo il rilevamento delle modifiche nell'app Finance and Operations per l'entità **Clienti V3**.</span><span class="sxs-lookup"><span data-stu-id="6d4f9-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** entity.</span></span>
