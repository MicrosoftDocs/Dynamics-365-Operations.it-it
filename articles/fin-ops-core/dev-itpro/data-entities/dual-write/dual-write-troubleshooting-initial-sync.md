---
title: Risoluzione dei problemi durante la sincronizzazione iniziale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8aa7d156d0f0dad921b5c0aceec941295950b308
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566839"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="02a13-103">Risoluzione dei problemi durante la sincronizzazione iniziale</span><span class="sxs-lookup"><span data-stu-id="02a13-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="02a13-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="02a13-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="02a13-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="02a13-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02a13-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="02a13-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="02a13-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="02a13-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="02a13-108">Verificare la presenza di errori di sincronizzazione iniziale in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="02a13-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="02a13-109">Dopo aver abilitato i modelli di mapping, lo stato delle mappe deve essere **In esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="02a13-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="02a13-110">Se lo stato è **Non in esecuzione**, si sono verificati errori durante la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="02a13-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="02a13-111">Per visualizzare gli errori, selezionare la scheda **Dettagli sulla sincronizzazione iniziale** nella pagina **Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="02a13-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Errore nella scheda dei dettagli della sincronizzazione iniziale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="02a13-113">Impossibile completare la sincronizzazione iniziale: 400 Richiesta non valida</span><span class="sxs-lookup"><span data-stu-id="02a13-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="02a13-114">**Ruolo richiesto per risolvere il problema:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="02a13-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="02a13-115">È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di eseguire il mapping e la sincronizzazione iniziale:</span><span class="sxs-lookup"><span data-stu-id="02a13-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="02a13-116">*(\[Richiesta non valida\]. Il server remoto ha restituito un errore: (400) Richiesta non valida). Si è verificato un errore nell'esportazione AX*</span><span class="sxs-lookup"><span data-stu-id="02a13-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="02a13-117">Di seguito è riportato un esempio del messaggio di errore completo.</span><span class="sxs-lookup"><span data-stu-id="02a13-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="02a13-118">Se questo errore si verifica in modo coerente e non è possibile completare la sincronizzazione iniziale, attenersi alla seguente procedura per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="02a13-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="02a13-119">Accedere alla macchina virtuale (VM) per l'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="02a13-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="02a13-120">Aprire la console di gestione Microsoft.</span><span class="sxs-lookup"><span data-stu-id="02a13-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="02a13-121">Nel riquadro **Servizi**, assicurarsi che il servizio framework di importazione esportazione dati di Microsoft Dynamics 365 sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="02a13-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="02a13-122">Riavviarlo se è stato arrestato, poiché la sincronizzazione iniziale lo richiede.</span><span class="sxs-lookup"><span data-stu-id="02a13-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="02a13-123">Errore di sincronizzazione iniziale: 403 Accesso negato</span><span class="sxs-lookup"><span data-stu-id="02a13-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="02a13-124">È possibile che venga visualizzato il seguente messaggio di errore durante la sincronizzazione iniziale:</span><span class="sxs-lookup"><span data-stu-id="02a13-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="02a13-125">*(\[Accesso negato\]. Il server remoto ha restituito un errore: (403) Accesso negato). Si è verificato un errore nell'esportazione AX*</span><span class="sxs-lookup"><span data-stu-id="02a13-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="02a13-126">Per risolvere il problema, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="02a13-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="02a13-127">Accedere all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="02a13-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="02a13-128">Nella pagina **Applicazioni Azure Active Directory**, eliminare il client **DtAppID**, quindi aggiungerlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="02a13-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Client DtAppID nell'elenco di applicazioni Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="02a13-130">Errori di riferimento automatico o di riferimento circolare durante la sincronizzazione iniziale</span><span class="sxs-lookup"><span data-stu-id="02a13-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="02a13-131">È possibile ricevere un messaggio di errore se uno dei mapping include riferimenti automatici o circulari.</span><span class="sxs-lookup"><span data-stu-id="02a13-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="02a13-132">Gli errori rientrano in queste categorie:</span><span class="sxs-lookup"><span data-stu-id="02a13-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="02a13-133">Errori nel mapping della tabella Fornitori V2 per msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="02a13-133">Errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="02a13-134">Errori nel mapping della tabella Clienti V3 per Account</span><span class="sxs-lookup"><span data-stu-id="02a13-134">Errors in the Customers V3–to–Accounts table mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="02a13-135">Risolvere gli errori nel mapping della tabella Fornitori V2 per msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="02a13-135">Resolve errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>

<span data-ttu-id="02a13-136">È possibile che si verifichino errori di sincronizzazione iniziale per il mapping di **Fornitori V2** all'entità **msdyn\_vendors** se le tabelle hanno righe esistenti con valori nelle colonne **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="02a13-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the tables have existing rows where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns.</span></span> <span data-ttu-id="02a13-137">Questi errori si verificano perché **InvoiceVendorAccountNumber** è una colonna di riferimento automatico e **PrimaryContactPersonId** è un riferimento circolare nel mapping del fornitore.</span><span class="sxs-lookup"><span data-stu-id="02a13-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing column, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="02a13-138">I messaggi di errore che si ricevono avranno il seguente formato.</span><span class="sxs-lookup"><span data-stu-id="02a13-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="02a13-139">*Impossibile risolvere il guid per il campo: \<field\>. La ricerca non è stata trovata: \<value\>. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="02a13-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="02a13-140">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="02a13-140">Here are some examples:</span></span>

- <span data-ttu-id="02a13-141">*Impossibile risolvere il guid per il campo: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="02a13-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="02a13-142">*Impossibile risolvere il guid per il campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. La ricerca non è stata trovata: V24-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="02a13-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="02a13-143">Se le righe nella tabella fornitore hanno valori nelle colonne **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**, seguire questi passaggi per completare la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="02a13-143">If any rows in the vendor table have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="02a13-144">Nell'app Finance and Operations, eliminare le colonne **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** dal mapping e salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="02a13-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="02a13-145">Nella pagina del mapping in doppia scrittura per **Fornitori V2 (msdyn\_vendors)**, nella scheda **Mapping della tabella**, nel filtro a sinistra, selezionare **Finance and Operationsapps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="02a13-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="02a13-146">Nel filtro di destra, selezionare **Vendite.Fornitore**.</span><span class="sxs-lookup"><span data-stu-id="02a13-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="02a13-147">Cercare **primarycontactperson** per trovare la colonna di origine **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="02a13-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source column.</span></span>
    3. <span data-ttu-id="02a13-148">Selezionare **Azioni**, quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="02a13-148">Select **Actions**, and then select **Delete**.</span></span>

        ![Eliminazione della colonna PrimaryContactPersonId](media/vend_selfref3.png)

    4. <span data-ttu-id="02a13-150">Ripetere questi passaggi per eliminare la colonna **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="02a13-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** column.</span></span>

        ![Eliminazione della colonna InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. <span data-ttu-id="02a13-152">Salvare le modifiche nel mapping.</span><span class="sxs-lookup"><span data-stu-id="02a13-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="02a13-153">Disattivare il rilevamento delle modifiche per la tabella **Fornitori V2**.</span><span class="sxs-lookup"><span data-stu-id="02a13-153">Turn off change tracking for the **Vendors V2** table.</span></span>

    1. <span data-ttu-id="02a13-154">Nell'area di lavoro **Gestione dati** selezionare la scheda **Tabelle dati**.</span><span class="sxs-lookup"><span data-stu-id="02a13-154">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="02a13-155">Selezionare la tabella **Fornitori V2**.</span><span class="sxs-lookup"><span data-stu-id="02a13-155">Select the **Vendors V2** table.</span></span>
    3. <span data-ttu-id="02a13-156">Nel riquadro azioni selezionare **Opzioni**, quindi selezionare **Rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="02a13-156">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Selezione dell'opzione Rilevamento modifiche](media/selfref_options.png)

    4. <span data-ttu-id="02a13-158">Selezionare **Disabilita rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="02a13-158">Select **Disable Change Tracking**.</span></span>

        ![Selezione di Disabilita rilevamento modifiche](media/selfref_tracking.png)

3. <span data-ttu-id="02a13-160">Eseguire la sincronizzazione iniziale per il mapping **Fornitori V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="02a13-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="02a13-161">La sincronizzazione iniziale deve essere eseguita correttamente senza errori.</span><span class="sxs-lookup"><span data-stu-id="02a13-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="02a13-162">Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**.</span><span class="sxs-lookup"><span data-stu-id="02a13-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="02a13-163">È necessario sincronizzare questo mapping se si desidera sincronizzare la colonna di contatto primario nella tabella fornitori perché la sincronizzazione deve essere eseguita anche per le righe di contatti.</span><span class="sxs-lookup"><span data-stu-id="02a13-163">You must sync this mapping if you want to sync the primary contact column on the vendors table, because initial synchronization must also be done for the contact rows.</span></span>
5. <span data-ttu-id="02a13-164">Aggiungere di nuovo le colonne **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** al mapping **Fornitori V2 (msdyn\_vendors)** e salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="02a13-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="02a13-165">Eseguire di nuovo la sincronizzazione iniziale per il mapping **Fornitori V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="02a13-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="02a13-166">Tutte le righe verranno sincronizzate perché il rilevamento delle modifiche è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="02a13-166">Because change tracking is turned off, all the rows will be synced.</span></span>
7. <span data-ttu-id="02a13-167">Attivare di nuovo il rilevamento delle modifiche per la tabella **Fornitori V2**.</span><span class="sxs-lookup"><span data-stu-id="02a13-167">Turn change tracking back on for the **Vendors V2** table.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="02a13-168">Risolvere gli errori nel mapping della tabella Clienti V3 per Account</span><span class="sxs-lookup"><span data-stu-id="02a13-168">Resolve errors in the Customers V3–to–Accounts table mapping</span></span>

<span data-ttu-id="02a13-169">È possibile che si verifichino errori di sincronizzazione iniziale per il mapping dell'entità **Clienti V3** all'entità **Account** se le tabelle hanno righe esistenti con valori nelle colonne **ContactPersonID** e **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="02a13-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the tables have existing rows where there are values in the **ContactPersonID** and **InvoiceAccount** columns.</span></span> <span data-ttu-id="02a13-170">Questi errori si verificano perché **InvoiceAccount** è una colonna di riferimento automatico e **ContactPersonID** è un riferimento circolare nel mapping del fornitore.</span><span class="sxs-lookup"><span data-stu-id="02a13-170">These errors occur because **InvoiceAccount** is a self-referencing column, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="02a13-171">I messaggi di errore che si ricevono avranno il seguente formato.</span><span class="sxs-lookup"><span data-stu-id="02a13-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="02a13-172">*Impossibile risolvere il guid per il campo: \<field\>. La ricerca non è stata trovata: \<value\>. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="02a13-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="02a13-173">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="02a13-173">Here are some examples:</span></span>

- <span data-ttu-id="02a13-174">*Impossibile risolvere il guid per il campo: primarycontactid.msdyn\_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="02a13-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="02a13-175">*Impossibile risolvere il guid per il campo: msdyn\_billingaccount.accountnumber. La ricerca non è stata trovata: 1206-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="02a13-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="02a13-176">Se le righe nella tabella cliente hanno valori nelle colonne **ContactPersonID** e **InvoiceAccount**, seguire questi passaggi per completare la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="02a13-176">If any rows in the customer table have values in the **ContactPersonID** and **InvoiceAccount** columns, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="02a13-177">È possibile utilizzare questo approccio per tutte le tabelle predefinite come **Account** e **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="02a13-177">You can use this approach for any out-of-box tables, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="02a13-178">Nell'app Finance and Operations, eliminare le colonne **ContactPersonID** e **InvoiceAccount** dal mapping **Clienti V3 (account)** e quindi salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="02a13-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** columns from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="02a13-179">Nella pagina del mapping in doppia scrittura per **Clienti V3 (account)**, nella scheda **Mapping della tabella**, nel filtro a sinistra, selezionare **Finance and Operations app.Customer V3**.</span><span class="sxs-lookup"><span data-stu-id="02a13-179">On the dual-write mapping page for **Customers V3 (accounts)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="02a13-180">Nel filtro a destra, selezionare **Dataverse.Account**.</span><span class="sxs-lookup"><span data-stu-id="02a13-180">In the right filter, select **Dataverse.Account**.</span></span>
    2. <span data-ttu-id="02a13-181">Cercare **contactperson** per trovare la colonna di origine **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="02a13-181">Search for **contactperson** to find the **ContactPersonID** source column.</span></span>
    3. <span data-ttu-id="02a13-182">Selezionare **Azioni**, quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="02a13-182">Select **Actions**, and then select **Delete**.</span></span>

        ![Eliminazione della colonna ContactPersonID](media/cust_selfref3.png)

    4. <span data-ttu-id="02a13-184">Ripetere questi passaggi per eliminare la colonna **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="02a13-184">Repeat these steps to delete the **InvoiceAccount** column.</span></span>

        ![Eliminazione della colonna InvoiceAccount](media/cust_selfref4.png)

    5. <span data-ttu-id="02a13-186">Salvare le modifiche nel mapping.</span><span class="sxs-lookup"><span data-stu-id="02a13-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="02a13-187">Disattivare il rilevamento delle modifiche per la tabella **Clienti V3**.</span><span class="sxs-lookup"><span data-stu-id="02a13-187">Turn off change tracking for the **Customers V3** table.</span></span>

    1. <span data-ttu-id="02a13-188">Nell'area di lavoro **Gestione dati** selezionare la scheda **Tabelle dati**.</span><span class="sxs-lookup"><span data-stu-id="02a13-188">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="02a13-189">Selezionare la tabella **Cliente V3**.</span><span class="sxs-lookup"><span data-stu-id="02a13-189">Select the **Customers V3** table.</span></span>
    3. <span data-ttu-id="02a13-190">Nel riquadro azioni selezionare **Opzioni**, quindi selezionare **Rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="02a13-190">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Selezione dell'opzione Rilevamento modifiche](media/selfref_options.png)

    4. <span data-ttu-id="02a13-192">Selezionare **Disabilita rilevamento modifiche**.</span><span class="sxs-lookup"><span data-stu-id="02a13-192">Select **Disable Change Tracking**.</span></span>

        ![Selezione di Disabilita rilevamento modifiche](media/selfref_tracking.png)

3. <span data-ttu-id="02a13-194">Eseguire la sincronizzazione iniziale per il mapping **Clienti V3 (account)**.</span><span class="sxs-lookup"><span data-stu-id="02a13-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="02a13-195">La sincronizzazione iniziale deve essere eseguita correttamente senza errori.</span><span class="sxs-lookup"><span data-stu-id="02a13-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="02a13-196">Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**.</span><span class="sxs-lookup"><span data-stu-id="02a13-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02a13-197">Sono presenti due mappe con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="02a13-197">There are two maps that have the same name.</span></span> <span data-ttu-id="02a13-198">Assicurarsi di selezionare la mappa con la descrizione **Modello in doppia scrittura per la sincronizzazione tra Contatti fornitore FO.CDS V2 e CDS.Contatti. Necessita un nuovo pacchetto \[Dynamics365SupplyChainExtended\] nella scheda** **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="02a13-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="02a13-199">Aggiungere di nuovo le colonne **ContactPersonID** e **InvoiceAccount** al mapping **Clienti V3 (account)** e quindi salvare il mapping.</span><span class="sxs-lookup"><span data-stu-id="02a13-199">Add the **InvoiceAccount** and **ContactPersonId** columns back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="02a13-200">Le colonne **InvoiceAccount** e **ContactPersonId** fanno di nuovo parte della modalità di sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="02a13-200">Both the **InvoiceAccount** column and the **ContactPersonId** column are now part of live synchronization mode again.</span></span> <span data-ttu-id="02a13-201">Nel passaggio successivo, eseguire la sincronizzazione iniziale per queste colonne.</span><span class="sxs-lookup"><span data-stu-id="02a13-201">In the next step, you will do the initial synchronization for these columns.</span></span>
6. <span data-ttu-id="02a13-202">Eseguire di nuovo la sincronizzazione iniziale per il mapping **Clienti V3 (account)**.</span><span class="sxs-lookup"><span data-stu-id="02a13-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="02a13-203">Poiché il rilevamento delle modifiche è disattivato, i dati per **InvoiceAccount** e **ContactPersonId** vengono sincronizzati dall'app Finance and Operations a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="02a13-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Dataverse.</span></span>
7. <span data-ttu-id="02a13-204">Per sincronizzare i dati per **InvoiceAccount** e **ContactPersonId** da Dataverse all'app Finance and Operations, è necessario utilizzare un progetto di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="02a13-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Dataverse to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="02a13-205">In Power Apps, creare un progetto di integrazione dei dati tra le tabelle **Sales.Account** e **Finance and Operations apps.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="02a13-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** tables.</span></span> <span data-ttu-id="02a13-206">La direzione dei dati deve essere da Dataverse all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="02a13-206">The data direction must be from Dataverse to the Finance and Operations app.</span></span> <span data-ttu-id="02a13-207">Poiché **InvoiceAccount** è un nuovo attributo in doppia scrittura, è possibile che si voglia ignorare la sincronizzazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="02a13-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="02a13-208">Per ulteriori informazioni, vedere [Integrare dati in Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="02a13-208">For more information, see [Integrate data into Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="02a13-209">La figura seguente mostra un progetto che aggiorna **CustomerAccount** e **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="02a13-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Progetto di integrazione dei dati per aggiornare CustomerAccount e ContactPersonId](media/cust_selfref6.png)

    2. <span data-ttu-id="02a13-211">Aggiungere i criteri dell'azienda nel filtro sul lato Dataverse in modo che solo le righe che soddisfano i criteri di filtro verranno aggiornati nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="02a13-211">Add the company criteria in the filter on the Dataverse side, so that only rows that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="02a13-212">Per aggiungere un filtro, selezionare il pulsante del filtro.</span><span class="sxs-lookup"><span data-stu-id="02a13-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="02a13-213">Nella finestra di dialogo **Modifica query**, è possibile aggiungere una query filtro come **\_msdyn\_company\_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="02a13-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="02a13-214">[NOTA] Se il pulsante del filtro non è presente, creare un ticket di supporto per chiedere al team di integrazione dei dati di abilitare la funzionalità sul tenant.</span><span class="sxs-lookup"><span data-stu-id="02a13-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="02a13-215">Se non si immette una query filtro per **\_msdyn\_company\_value**, tutte le righe vengono sincronizzate.</span><span class="sxs-lookup"><span data-stu-id="02a13-215">If you don't enter a filter query for **\_msdyn\_company\_value**, all the rows will be synced.</span></span>

        ![Aggiunta di una query filtro](media/cust_selfref7.png)

    <span data-ttu-id="02a13-217">La sincronizzazione iniziale delle righe è ora completata.</span><span class="sxs-lookup"><span data-stu-id="02a13-217">The initial synchronization of the rows is now completed.</span></span>

8. <span data-ttu-id="02a13-218">Abilitare di nuovo il rilevamento delle modifiche nell'app Finance and Operations per la tabella **Clienti V3**.</span><span class="sxs-lookup"><span data-stu-id="02a13-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** table.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]