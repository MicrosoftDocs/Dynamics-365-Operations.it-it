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
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410083"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="9780e-103">Risoluzione dei problemi durante la sincronizzazione iniziale</span><span class="sxs-lookup"><span data-stu-id="9780e-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9780e-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9780e-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="9780e-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="9780e-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9780e-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9780e-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="9780e-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="9780e-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="9780e-108">Verificare la presenza di errori di sincronizzazione iniziale in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9780e-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="9780e-109">Dopo aver abilitato i modelli di mapping, lo stato delle mappe deve essere **In esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="9780e-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="9780e-110">Se lo stato è **Non in esecuzione**, si sono verificati errori durante la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="9780e-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="9780e-111">Per visualizzare gli errori, selezionare la scheda **Dettagli sulla sincronizzazione iniziale** nella pagina **Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="9780e-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Scheda dei dettagli della sincronizzazione iniziale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="9780e-113">Impossibile completare la sincronizzazione iniziale: 400 Richiesta non valida</span><span class="sxs-lookup"><span data-stu-id="9780e-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="9780e-114">**Ruolo richiesto per risolvere il problema:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="9780e-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="9780e-115">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di eseguire il mapping e la sincronizzazione iniziale:</span><span class="sxs-lookup"><span data-stu-id="9780e-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="9780e-116">*Il server remoto ha restituito un errore: (400) Richiesta non valida. Si è verificato un errore nell'esportazione AX*</span><span class="sxs-lookup"><span data-stu-id="9780e-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="9780e-117">Di seguito è riportato un esempio del messaggio di errore completo.</span><span class="sxs-lookup"><span data-stu-id="9780e-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="9780e-118">Se questo errore si verifica in modo coerente e non è possibile completare la sincronizzazione iniziale, attenersi alla seguente procedura per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="9780e-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="9780e-119">Accedere alla macchina virtuale (VM) per l'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9780e-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="9780e-120">Aprire la console di gestione Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9780e-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="9780e-121">Nel riquadro **Servizi**, assicurarsi che il servizio framework di importazione esportazione dati di Microsoft Dynamics 365 sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9780e-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="9780e-122">Riavviarlo se è stato arrestato, poiché la sincronizzazione iniziale lo richiede.</span><span class="sxs-lookup"><span data-stu-id="9780e-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="9780e-123">Errore di sincronizzazione iniziale: 403 Accesso negato</span><span class="sxs-lookup"><span data-stu-id="9780e-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="9780e-124">È possibile che venga visualizzato il seguente messaggio di errore durante la sincronizzazione iniziale:</span><span class="sxs-lookup"><span data-stu-id="9780e-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="9780e-125">*(\[Accesso negato\]. Il server remoto ha restituito un errore: (403) Accesso negato). Si è verificato un errore nell'esportazione AX*</span><span class="sxs-lookup"><span data-stu-id="9780e-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="9780e-126">Per risolvere il problema, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="9780e-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="9780e-127">Accedere all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9780e-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="9780e-128">Nella pagina **Applicazioni Azure Active Directory**, eliminare il client **DtAppID**, quindi aggiungerlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="9780e-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Elenco di applicazioni Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="9780e-130">Errori di riferimento automatico o di riferimento circolare durante la sincronizzazione iniziale</span><span class="sxs-lookup"><span data-stu-id="9780e-130">Self-reference or circular-reference failures during initial synchronization</span></span>

<span data-ttu-id="9780e-131">È possibile ricevere un messaggio di errore se uno dei mapping include riferimenti automatici o circulari.</span><span class="sxs-lookup"><span data-stu-id="9780e-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="9780e-132">Gli errori rientrano in queste categorie:</span><span class="sxs-lookup"><span data-stu-id="9780e-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="9780e-133">Mapping dell'entità Fornitori V2 all'entità msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="9780e-133">Vendors V2 to msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="9780e-134">Mapping dell'entità Clienti V3 all'entità Account</span><span class="sxs-lookup"><span data-stu-id="9780e-134">Customers V3 to Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="9780e-135">Risolvere un errore nel mapping dell'entità Fornitori V2 all'entità msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="9780e-135">Resolve an error in Vendors V2 to msdyn_vendors entity mapping</span></span>

<span data-ttu-id="9780e-136">È possibile che si verifichino i seguenti errori di sincronizzazione iniziale nel mapping dell'entità **Fornitori V2** all'entità **msdyn_vendors** se le entità hanno record esistenti con valori nei campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="9780e-136">You might run into the following initial sync errors on the **Vendors V2** to **msdyn_vendors** mapping if the entities have existing records with values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="9780e-137">Questo perché **InvoiceVendorAccountNumber** è un campo di riferimento automatico e **PrimaryContactPersonId** è un riferimento circolare nel mapping del fornitore.</span><span class="sxs-lookup"><span data-stu-id="9780e-137">This because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="9780e-138">*Impossibile risolvere il guid per il campo: <field>. La ricerca non è stata trovata: <value>. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="9780e-138">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

<span data-ttu-id="9780e-139">Qui di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="9780e-139">Here are a couple of examples:</span></span>

- <span data-ttu-id="9780e-140">*Impossibile risolvere il guid per il campo: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="9780e-140">*Couldn't resolve the guid for the field: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="9780e-141">*Impossibile risolvere il guid per il campo: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. La ricerca non è stata trovata: V24-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span><span class="sxs-lookup"><span data-stu-id="9780e-141">*Couldn't resolve the guid for the field: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span></span>

<span data-ttu-id="9780e-142">Se si hanno record con valori in questi campi nell'entità fornitore, seguire i passaggi nella sezione seguente per completare correttamente la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="9780e-142">If you have records with values in these fields in the vendor entity follow the steps in the below section to complete initial sync successfully.</span></span>

1. <span data-ttu-id="9780e-143">Nell'app Finance and Operations, eliminare i campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** dal mapping e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="9780e-143">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping and save the changes.</span></span>

    1. <span data-ttu-id="9780e-144">Passare alla pagina del mapping in doppia scrittura per **Fornitori V2 (msdyn_vendors)** e selezionare la scheda **Mapping entità**. Nel filtro a sinistra, selezionare **App Finance and Operations.Fornitori V2**.</span><span class="sxs-lookup"><span data-stu-id="9780e-144">Navigate to the dual-write mapping page for **Vendors V2 (msdyn_vendors)**, and select the **Entity mappings** tab. In the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="9780e-145">Nel filtro di destra, selezionare **Vendite.Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="9780e-145">In the right filter, select **Sales.Vendor**.</span></span>

    2. <span data-ttu-id="9780e-146">Cercare **primarycontactperson** per trovare il campo sorgente **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="9780e-146">Search for **primarycontactperson** to find the source field **PrimaryContactPersonId**.</span></span>
    
    3. <span data-ttu-id="9780e-147">Fare clic sul pulsante **Azioni**, quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9780e-147">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![Riferimento automatico o circolare 3](media/vend_selfref3.png)
    
    4. <span data-ttu-id="9780e-149">Ripetere l'operazione per eliminare il campo **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="9780e-149">Repeat to delete the **InvoiceVendorAccountNumber** field.</span></span>
    
        ![Riferimento automatico o circolare 4](media/vend-selfref4.png)
    
    5. <span data-ttu-id="9780e-151">Salvare le modifiche al mapping.</span><span class="sxs-lookup"><span data-stu-id="9780e-151">Save the mapping changes.</span></span>

2. <span data-ttu-id="9780e-152">Disabilitare il rilevamento delle modifiche per l'entità **Fornitori V2**.</span><span class="sxs-lookup"><span data-stu-id="9780e-152">Disable the change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="9780e-153">Accedere a **Gestione dati \> Entità dati**.</span><span class="sxs-lookup"><span data-stu-id="9780e-153">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="9780e-154">Selezionare l'entità **Fornitori V2**.</span><span class="sxs-lookup"><span data-stu-id="9780e-154">Select the **Vendors V2** entity.</span></span>
    
    3. <span data-ttu-id="9780e-155">Fare clic su **Opzioni** nella barra dei menu, quindi selezionare **Rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="9780e-155">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![Riferimento automatico o circolare 5](media/selfref_options.png)
    
    4. <span data-ttu-id="9780e-157">Fare clic su **Disabilita rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="9780e-157">Click **Disable Change Tracking**.</span></span>
    
        ![Riferimento automatico o circolare 6](media/selfref_tracking.png)

3. <span data-ttu-id="9780e-159">Eseguire la sincronizzazione iniziale del mapping **Fornitori V2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="9780e-159">Run the initial sync of **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="9780e-160">La sincronizzazione iniziale deve essere eseguita correttamente senza errori.</span><span class="sxs-lookup"><span data-stu-id="9780e-160">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="9780e-161">Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**.</span><span class="sxs-lookup"><span data-stu-id="9780e-161">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="9780e-162">È necessario sincronizzare questo mapping se si desidera sincronizzare il campo di contatto primario nell'entità fornitori poiché anche i record di contatti devono essere sincronizzati inizialmente.</span><span class="sxs-lookup"><span data-stu-id="9780e-162">You must sync this mapping if you want to sync primary contact field on vendors entity as the contacts records also need to be initial synced.</span></span>

5. <span data-ttu-id="9780e-163">Aggiungere di nuovo i campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** al mapping **Fornitori V2 (msdyn_vendors)** e salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="9780e-163">Add the fields **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** back to the **Vendors V2 (msdyn_vendors)** mapping and save the mapping.</span></span>

6. <span data-ttu-id="9780e-164">Eseguire di nuovo la sincronizzazione iniziale per il mapping **Fornitori V2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="9780e-164">Run the initial sync again for the **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="9780e-165">Tutti i record verranno sincronizzati poiché il rilevamento delle modifiche è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="9780e-165">All the records will be synced, because change tracking is disabled.</span></span>

7. <span data-ttu-id="9780e-166">Abilitare il rilevamento delle modifiche per l'entità **Fornitori V2**.</span><span class="sxs-lookup"><span data-stu-id="9780e-166">Enable change tracking for the **Vendors V2** entity.</span></span>

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="9780e-167">Risolvere un errore nel mapping dell'entità Clienti V3 all'entità Account</span><span class="sxs-lookup"><span data-stu-id="9780e-167">Resolve an error in Customers V3 to Accounts entity mapping</span></span>

<span data-ttu-id="9780e-168">È possibile che si verifichino i seguenti errori di sincronizzazione iniziali nel mapping di **Clienti V3** a **Account** se le entità hanno record esistenti con valori nei campi **ContactPersonID** e **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="9780e-168">You might run into the following initial sync errors on the **Customers V3** to **Accounts** mapping if the entities have existing records with values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="9780e-169">Questo perché **InvoiceAccount** è un campo di riferimento automatico e **ContactPersonID** è un riferimento circolare nel mapping del fornitore.</span><span class="sxs-lookup"><span data-stu-id="9780e-169">This because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="9780e-170">*Impossibile risolvere il guid per il campo: <field>. La ricerca non è stata trovata: <value>. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="9780e-170">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

- <span data-ttu-id="9780e-171">*Impossibile risolvere il guid per il campo: primarycontactid.msdyn_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="9780e-171">*Couldn't resolve the guid for the field: primarycontactid.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="9780e-172">*Impossibile risolvere il guid per il campo: msdyn_billingaccount.accountnumber. La ricerca non è stata trovata: 1206-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span><span class="sxs-lookup"><span data-stu-id="9780e-172">*Couldn't resolve the guid for the field: msdyn_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span></span>

<span data-ttu-id="9780e-173">Se si hanno record con valori in questi campi nell'entità cliente, seguire i passaggi nella sezione seguente per completare correttamente la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="9780e-173">If you have records with values in these fields in the customer entity follow the steps in the below section to complete initial sync successfully.</span></span> <span data-ttu-id="9780e-174">È possibile utilizzare questo approccio per tutte le entità predefinite come Account e Contatti.</span><span class="sxs-lookup"><span data-stu-id="9780e-174">You can use this approach for any out-of-the-box entities such Accounts and Contacts.</span></span>

1. <span data-ttu-id="9780e-175">Nell'app Finance and Operations, eliminare i campi **ContactPersonID** e **InvoiceAccount** dal mapping **Clienti V3 (account)** e salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="9780e-175">In the Finance and Operations app, delete the fields **ContactPersonID** and **InvoiceAccount** from the **Customers V3 (accounts)** mapping and save the mapping.</span></span>

    1. <span data-ttu-id="9780e-176">Passare alla pagina del mapping in doppia scrittura per **Clienti V3 (account)** e selezionare la scheda **Mapping entità**. Nel filtro a sinistra, selezionare **App Finance and Operations.Clienti V3**.</span><span class="sxs-lookup"><span data-stu-id="9780e-176">Navigate to the dual-write mapping page for **Customers V3 (accounts)**, select the **Entity mappings** tab. In the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="9780e-177">Nel filtro a destra, selezionare **Common Data Service.Account**.</span><span class="sxs-lookup"><span data-stu-id="9780e-177">In the right filter, select **Common Data Service.Account**.</span></span>

    2. <span data-ttu-id="9780e-178">Cercare **contactperson** per trovare il campo sorgente **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="9780e-178">Search for **contactperson** to find the source field **ContactPersonID**.</span></span>
    
    3. <span data-ttu-id="9780e-179">Fare clic sul pulsante **Azioni**, quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9780e-179">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![Riferimento automatico o circolare 3](media/cust_selfref3.png)
    
    4. <span data-ttu-id="9780e-181">Ripetere l'operazione per eliminare il campo **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="9780e-181">Repeat to delete the **InvoiceAccount** field.</span></span>
    
        ![Riferimento automatico o circolare](media/cust_selfref4.png)
    
    5. <span data-ttu-id="9780e-183">Salvare le modifiche al mapping.</span><span class="sxs-lookup"><span data-stu-id="9780e-183">Save the mapping changes.</span></span>

2. <span data-ttu-id="9780e-184">Disabilitare il rilevamento delle modifiche per l'entità **Clienti V3**.</span><span class="sxs-lookup"><span data-stu-id="9780e-184">Disable the change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="9780e-185">Accedere a **Gestione dati \> Entità dati**.</span><span class="sxs-lookup"><span data-stu-id="9780e-185">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="9780e-186">Selezionare l'entità **Clienti V3**.</span><span class="sxs-lookup"><span data-stu-id="9780e-186">Select the **Customers V3** entity.</span></span>
    
    3. <span data-ttu-id="9780e-187">Fare clic su **Opzioni** nella barra dei menu, quindi selezionare **Rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="9780e-187">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![Riferimento automatico o circolare 5](media/selfref_options.png)
    
    4. <span data-ttu-id="9780e-189">Fare clic su **Disabilita rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="9780e-189">Click **Disable Change Tracking**.</span></span>
    
        ![Riferimento automatico o circolare 6](media/selfref_tracking.png)

3. <span data-ttu-id="9780e-191">Eseguire la sincronizzazione iniziale per il mapping **Clienti V3 (account)**.</span><span class="sxs-lookup"><span data-stu-id="9780e-191">Run the initial sync for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="9780e-192">La sincronizzazione iniziale deve essere eseguita correttamente senza errori.</span><span class="sxs-lookup"><span data-stu-id="9780e-192">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="9780e-193">Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**.</span><span class="sxs-lookup"><span data-stu-id="9780e-193">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="9780e-194">Ci sono 2 mappe con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="9780e-194">There are 2 maps with the same name.</span></span> <span data-ttu-id="9780e-195">Selezionare quella con la descrizione **Modello in doppia scrittura per la sincronizzazione tra Contatti fornitore FO.CDS V2 e CDS.Contatti. Necessita un nuovo pacchetto \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="9780e-195">Select the one with the description **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span> <span data-ttu-id="9780e-196">nella scheda **Dettagli** della mappa.</span><span class="sxs-lookup"><span data-stu-id="9780e-196">on the **Details** tab of the map.</span></span>

5. <span data-ttu-id="9780e-197">Aggiungere di nuovo i campi **ContactPersonID** e **InvoiceAccount** al mapping **Clienti V3 (account)** e salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="9780e-197">Add the fields **InvoiceAccount** and **ContactPersonId** back to the **Customers V3 (Accounts)** mapping and save the mapping.</span></span> <span data-ttu-id="9780e-198">Adesso i campi **InvoiceAccount** e **ContactPersonId** fanno di nuovo parte della modalità di sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="9780e-198">Now, both the **InvoiceAccount** field and the **ContactPersonId** field are again part of live sync mode.</span></span> <span data-ttu-id="9780e-199">Nel passaggio successivo, completare la sincronizzazione iniziale per questi campi.</span><span class="sxs-lookup"><span data-stu-id="9780e-199">In the next step, you complete the initial sync for these fields.</span></span>

6. <span data-ttu-id="9780e-200">Eseguire di nuovo la sincronizzazione iniziale per il mapping **Clienti V3 (account)**.</span><span class="sxs-lookup"><span data-stu-id="9780e-200">Run the initial sync again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="9780e-201">Poiché il rilevamento delle modifiche è disabilitato, l'esecuzione della sincronizzazione sincronizzerà i dati per **InvoiceAccount** e **ContactPersonId** dall'app Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9780e-201">Because change tracking is disabled, running the sync will sync the data for **InvoiceAccount** and **ContactPersonId** from the Finance and Operations app to Common Data Service.</span></span>

7. <span data-ttu-id="9780e-202">Per sincronizzare i dati per **InvoiceAccount** e **ContactPersonId** da Common Data Service a Finance and Operations, si utilizza un progetto di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="9780e-202">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations, you use a data integration project.</span></span>

    1. <span data-ttu-id="9780e-203">In Power Apps, creare un progetto di integrazione dei dati tra le entità **Vendite.Account** e **App Finance and Operations.Clienti V3**.</span><span class="sxs-lookup"><span data-stu-id="9780e-203">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="9780e-204">La direzione dei dati deve essere da Common Data Service all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9780e-204">The data direction must be from Common Data Service to the Finance and Operations app.</span></span>  <span data-ttu-id="9780e-205">Poiché **InvoiceAccount** è un nuovo attributo in doppia scrittura, è possibile che si voglia ignorare la sincronizzazione iniziale per questo attributo.</span><span class="sxs-lookup"><span data-stu-id="9780e-205">Because **InvoiceAccount** is a new attribute in dual-write, you may want to skip initial sync for this attribute.</span></span> <span data-ttu-id="9780e-206">Per ulteriori informazioni, vedere [Integrare dati in Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="9780e-206">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="9780e-207">L'immagine seguente mostra un progetto che aggiorna **CustomerAccount** e **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="9780e-207">The following image shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Riferimento automatico o circolare](media/cust_selfref6.png)

    2. <span data-ttu-id="9780e-209">Aggiungere i criteri dell'azienda nel filtro sul lato Common Data Service, poiché solo i record che soddisfano i criteri di filtro verranno aggiornati nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9780e-209">Add the company criteria in the filter on Common Data Service side, because only the records that match filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="9780e-210">Per aggiungere un filtro, fare clic sull'icona filtro.</span><span class="sxs-lookup"><span data-stu-id="9780e-210">To add a filter, click the filter icon.</span></span> <span data-ttu-id="9780e-211">Nella finestra di dialogo **Modifica query**, è possibile aggiungere una query filtro come **_msdyn_company_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="9780e-211">In the **Edit query** dialog, you can add a filter query like **_msdyn_company_value eq '\<guid\>'**.</span></span> <span data-ttu-id="9780e-212">Se l'icona filtro non è presente, creare un ticket di supporto per chiedere al team di integrazione dei dati di abilitare la funzionalità sul tenant.</span><span class="sxs-lookup"><span data-stu-id="9780e-212">If the filter icon is not present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span> <span data-ttu-id="9780e-213">Se non si immette una query filtro per **_msdyn_company_value**, tutti i record vengono sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="9780e-213">If you do not enter a filter query for **_msdyn_company_value**, then all the records are synced.</span></span>

        ![Riferimento automatico o circolare](media/cust_selfref7.png)

        <span data-ttu-id="9780e-215">La sincronizzazione iniziale dei record risulta completata.</span><span class="sxs-lookup"><span data-stu-id="9780e-215">This completes the initial sync of the records.</span></span>

8. <span data-ttu-id="9780e-216">Abilitare il rilevamento delle modifiche per l'entità **Clienti V3** nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9780e-216">Enable change tracking for the **Customers V3** entity in the Finance and Operations app.</span></span>

