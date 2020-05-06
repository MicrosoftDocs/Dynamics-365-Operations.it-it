---
title: Risoluzione dei problemi di sincronizzazione in tempo reale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla sincronizzazione in tempo reale.
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
ms.openlocfilehash: d45b19c1e88e6a27bde4335d4a356f2173bdfcd3
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275419"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="9cb2c-103">Risoluzione dei problemi di sincronizzazione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="9cb2c-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="9cb2c-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="9cb2c-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cb2c-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9cb2c-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="9cb2c-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="9cb2c-108">La sincronizzazione in tempo reale genera un errore 403 Accesso negato quando si crea un record in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9cb2c-108">Live synchronization throws a 403 Forbidden error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="9cb2c-109">È possibile che venga visualizzato il seguente messaggio di errore quando si crea un record in un'app Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="9cb2c-109">You might receive the following error message when you create a record in a Finance and Operations app:</span></span>

<span data-ttu-id="9cb2c-110">*\[{\\"errore\\":{\\"codice\\":\\"0x80072560\\",\\"messaggio\\":\\"L'utente non è un membro dell'organizzazione.\\"}}\], Il server remoto ha restituito un errore: (403) Accesso negato."}}".*</span><span class="sxs-lookup"><span data-stu-id="9cb2c-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="9cb2c-111">Per risolvere il problema, seguire i passaggi in [Requisiti e prerequisiti di sistema](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="9cb2c-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="9cb2c-112">Per completare questi passaggi, gli utenti dell'applicazione di doppia scrittura che vengono creati in Common Data Service devono avere il ruolo di amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-112">To complete those steps, the dual-write application users who are created in Common Data Service must have the system admin role.</span></span> <span data-ttu-id="9cb2c-113">Anche il team proprietario predefinito deve avere il ruolo di amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="9cb2c-114">La sincronizzazione in tempo reale per un'entità genera coerentemente un errore simile quando si crea un record in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9cb2c-114">Live synchronization for any entity consistently throws a similar error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="9cb2c-115">**Ruolo richiesto per risolvere il problema:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="9cb2c-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="9cb2c-116">È possibile che venga visualizzato un messaggio di errore simile al seguente ogni volta che si tenta di salvare i dati dell'entità in un'app Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="9cb2c-116">You might receive an error message like the following every time that you try to save entity data in a Finance and Operations app:</span></span>

<span data-ttu-id="9cb2c-117">*Impossibile salvare le modifiche nel database. L'unità di lavoro non può eseguire il commit della transazione. Impossibile scrivere i dati nell'entità unità di misura. Scrittura su UnitOfMeasureEntity non riuscita con messaggio di errore Impossibile sincronizzare con l'entità unità di misura.*</span><span class="sxs-lookup"><span data-stu-id="9cb2c-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="9cb2c-118">Per risolvere il problema, è necessario assicurarsi che i dati di riferimento dei prerequisiti esistano nell'app Finance and Operations e in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Common Data Service.</span></span> <span data-ttu-id="9cb2c-119">Ad esempio, se il cliente dell'app Finance and Operations appartiene a un gruppo di clienti specifico, assicurarsi che il gruppo di clienti esista in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Common Data Service.</span></span>

<span data-ttu-id="9cb2c-120">Se i dati esistono su entrambi i lati e si conferma che il problema non è relativo ai dati, procedere nel seguente modo.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="9cb2c-121">Arrestare l'entità correlata.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-121">Stop the related entity.</span></span>
2. <span data-ttu-id="9cb2c-122">Accedere all'app Finance and Operations e assicurarsi che siano presenti record per l'entità in errore nelle tabelle DualWriteProjectConfiguration e DualWriteProjectFieldConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-122">Sign in to the Finance and Operations app, and make sure that records for the failing entity exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="9cb2c-123">Ad esempio, ecco come appare la query se l'entità **Clienti** non riesce.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-123">For example, here is what the query looks like if the **Customers** entity is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="9cb2c-124">Se sono presenti record per l'entità in errore anche dopo aver interrotto la mappatura dell'entità, eliminare i record correlati all'entità in errore.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-124">If there are records for the failing entity even after you stop the entity mapping, delete the records that are related to the failing entity.</span></span> <span data-ttu-id="9cb2c-125">Prendere nota della colonna **projectname** nella tabella DualWriteProjectConfiguration e recuperare il record nella tabella DualWriteProjectFieldConfiguration utilizzando il nome del progetto per eliminare il record.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the record in the DualWriteProjectFieldConfiguration table by using the project name to delete the record.</span></span>
4. <span data-ttu-id="9cb2c-126">Avviare la mappatura dell'entità.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-126">Start the entity mapping.</span></span> <span data-ttu-id="9cb2c-127">Convalidare se i dati vengono sincronizzati senza problemi.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="9cb2c-128">Gestire gli errori dei privilegi di lettura o scrittura quando si creano i dati in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9cb2c-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="9cb2c-129">È possibile che venga visualizzato un messaggio di errore "Richiesta non valida" simile al seguente esempio quando si creano dati in un'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Esempio del messaggio di errore Richiesta non valida](media/error_record_id_source.png)

<span data-ttu-id="9cb2c-131">Per risolvere il problema, è necessario assegnare il ruolo di sicurezza corretto al team della Business Unit Dynamics 365 Sales o Dynamics 365 Customer Service mappata per abilitare il privilegio mancante.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="9cb2c-132">Nell'app Finance and Operations, trovare la Business Unit mappata nel set di connessioni Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Mapping dell'organizzazione](media/mapped_business_unit.png)

2. <span data-ttu-id="9cb2c-134">Accedere all'ambiente nell'app basata su modello in Dynamics 365, andare a **Impostazione \> Sicurezza** e trovare il team della Business Unit mappata.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Team della Business Unit mappata](media/setting_security_page.png)

3. <span data-ttu-id="9cb2c-136">Aprire la pagina del team per la modifica, quindi selezionare **Gestisci ruoli** per aprire la finestra di dialogo **Gestisci ruoli del team**.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Pulsante Gestisci ruoli](media/manage_team_roles.png)

4. <span data-ttu-id="9cb2c-138">Assegnare il ruolo con il privilegio di lettura/scrittura per le entità pertinenti, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-138">Assign the role that has the read/write privilege for the relevant entities, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a><span data-ttu-id="9cb2c-139">Risoluzione dei problemi di sincronizzazione in un ambiente in cui è stato recentemente modificato Common Data Service</span><span class="sxs-lookup"><span data-stu-id="9cb2c-139">Fix synchronization issues in an environment that has a recently changed Common Data Service environment</span></span>

<span data-ttu-id="9cb2c-140">**Ruolo richiesto per risolvere il problema:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="9cb2c-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="9cb2c-141">È possibile che venga visualizzato il seguente messaggio di errore quando si creano dati in un'app Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="9cb2c-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="9cb2c-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Impossibile generare il payload per l'entità CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Creazione del payload non riuscita con errore URI non valido: L'URI è vuoto."}\],"isErrorCountUpdated":true}*</span><span class="sxs-lookup"><span data-stu-id="9cb2c-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="9cb2c-143">Ecco come si presenta l'errore nell'app basata su modello in Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="9cb2c-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="9cb2c-144">*Si è verificato un errore imprevisto del codice ISV. (ErrorType = ClientError) Eccezione imprevista dal plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: impossibile elaborare l'account dell'entità - Tentativo di connessione non riuscito perché la parte connessa non ha risposto correttamente dopo un periodo di tempo o connessione stabilita non riuscita perché l'host connesso non ha risposto*</span><span class="sxs-lookup"><span data-stu-id="9cb2c-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="9cb2c-145">Questo errore si verifica quando l'ambiente Common Data Service viene reimpostato in modo errato mentre si tenta di creare dati nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-145">This error occurs when the Common Data Service environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="9cb2c-146">Per risolvere il problema, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="9cb2c-147">Accedere alla macchina virtuale (VM) Finance and Operations, aprire SQL Server Management Studio (SSMS) e cercare i record nella tabella DUALWRITEPROJECTCONFIGURATIONENTITY dove **internalentityname** equivale a **Clienti V3** e **externalentityname** equivale a **conti**.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for records in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="9cb2c-148">Ecco come appare la query.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="9cb2c-149">Utilizzare il nome del progetto dai risultati della query precedente per eseguire la query seguente.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="9cb2c-150">Assicurarsi che la colonna **externalenvironmentURL** abbia l'URL corretto di Common Data Service o dell'app.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-150">Make sure that the **externalenvironmentURL** column has the correct Common Data Service or app URL.</span></span> <span data-ttu-id="9cb2c-151">Eliminare tutti i record duplicati che puntano all'URL Common Data Service errato.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-151">Delete any duplicate records that point to the wrong Common Data Service URL.</span></span> <span data-ttu-id="9cb2c-152">Eliminare i record corrispondenti nelle tabelle DUALWRITEPROJECTFIELDCONFIGURATION e DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="9cb2c-152">Delete the corresponding records in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="9cb2c-153">Arrestare il mapping dell'entità e quindi riavviarlo</span><span class="sxs-lookup"><span data-stu-id="9cb2c-153">Stop the entity mapping, and then restart it</span></span>
