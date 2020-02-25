---
title: Configurare l'integrazione di Common Data Service
description: È possibile attivare o disattivare l'integrazione tra Common Data Service e un'istanza di Microsoft Dynamics 365 Human Resources. È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo un'entità per risolvere problemi relativi ai dati tra i due ambienti.
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
ms.openlocfilehash: 042daf3fdf7a906086af726472da050467d217e3
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009516"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="70991-104">Configurare l'integrazione di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="70991-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="70991-105">È possibile attivare o disattivare l'integrazione tra Common Data Service e un'istanza di Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="70991-105">You can turn integration between Common Data Service and an instance of Microsoft Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="70991-106">È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo un'entità per risolvere problemi relativi ai dati tra i due ambienti.</span><span class="sxs-lookup"><span data-stu-id="70991-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="70991-107">Quando si disattiva l'integrazione, gli utenti possono effettuare modifiche in Human Resources o Common Data Service, ma tali modifiche non sono sincronizzate tra i due ambienti.</span><span class="sxs-lookup"><span data-stu-id="70991-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="70991-108">Per impostazione predefinita, l'integrazione tra Human Resources e Common Data Service è disattivata o attivata, a seconda della presenza di dati dimostrativi negli ambienti:</span><span class="sxs-lookup"><span data-stu-id="70991-108">By default, integration between Human Resources and Common Data Service is turned either off or on, depending on the presence of demo data in the environments:</span></span>

- <span data-ttu-id="70991-109">**Disattivata** per nuovi ambienti che non includono dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="70991-109">**Off** for new environments that don't include demo data</span></span>
- <span data-ttu-id="70991-110">**Attivata** per nuovi ambienti che includono dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="70991-110">**On** for new environments that include demo data</span></span>

<span data-ttu-id="70991-111">I nuovi ambienti che includono dati dimostrativi inizieranno a sincronizzare i dati quando viene eseguito il provisioning degli stessi.</span><span class="sxs-lookup"><span data-stu-id="70991-111">New environments that include demo data will start to sync data when they are provisioned.</span></span>

<span data-ttu-id="70991-112">In tali casi è possibile che si voglia disattivare l'integrazione:</span><span class="sxs-lookup"><span data-stu-id="70991-112">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="70991-113">Si specificano dati tramite Data Management Framework ed è necessario importarli più volte per riportarli a uno stato corretto.</span><span class="sxs-lookup"><span data-stu-id="70991-113">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="70991-114">Esistono problemi con i dati in Human Resources o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="70991-114">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="70991-115">Se si disattiva l'integrazione, è possibile eliminare un record in un ambiente senza eliminarlo nell'altro.</span><span class="sxs-lookup"><span data-stu-id="70991-115">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="70991-116">Quando si riattiva l'integrazione, il record nell'ambiente in cui non è stato eliminato verrà sincronizzato di nuovo con l'ambiente in cui è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="70991-116">When you turn integration back on, the record in the environment where it wasn't deleted will be synced back to the environment where it was deleted.</span></span> <span data-ttu-id="70991-117">La sincronizzazione inizia alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione di Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="70991-117">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="70991-118">Quando si disattiva l'integrazione dei dati, assicurarsi di non modificare lo stesso record in entrambi gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="70991-118">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="70991-119">Quando si riattiva l'integrazione, l'ultimo record modificato verrà sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="70991-119">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="70991-120">Pertanto, se non si apportano le stesse modifiche al record in entrambi gli ambienti, può verificarsi una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="70991-120">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="70991-121">Accedere alla pagina Integrazione di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="70991-121">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="70991-122">Nell'istanza di Human Resources in cui si desidera visualizzare o configurare le impostazioni per l'integrazione con Common Data Service, selezionare il riquadro **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="70991-122">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="70991-123">[![Riquadro Amministrazione sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="70991-123">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="70991-124">Selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="70991-124">Select the **Links** tab.</span></span>

    <span data-ttu-id="70991-125">[![Scheda Collegamenti](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="70991-125">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="70991-126">Sotto **Integrazioni**, selezionare **Configurazione di Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="70991-126">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="70991-127">[![Collegamento Configurazione di Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="70991-127">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="70991-128">Attivare o disattivare l'integrazione di dati tra Human Resources e Common Data Service</span><span class="sxs-lookup"><span data-stu-id="70991-128">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="70991-129">Per attivare l'integrazione, impostare l'opzione **Abilita l'integrazione con Common Data Service** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="70991-129">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70991-130">Quando si attiva l'integrazione, i dati verranno sincronizzati alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione con Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="70991-130">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="70991-131">Tutti i dati dovrebbero essere disponibili dopo il completamento del processo batch.</span><span class="sxs-lookup"><span data-stu-id="70991-131">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="70991-132">Per disattivare l'integrazione, impostare l'opzione su **No**.</span><span class="sxs-lookup"><span data-stu-id="70991-132">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="70991-133">[![Attivare o disattivare l'integrazione con Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="70991-133">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="70991-134">Visualizzare i dettagli dell'integrazione dei dati</span><span class="sxs-lookup"><span data-stu-id="70991-134">View data integration details</span></span>

<span data-ttu-id="70991-135">Nella Scheda dettaglio **Amministrazione** della pagina **Integrazione con Common Data Service**, è possibile vedere come i record sono collegati tra Human Resources e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="70991-135">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="70991-136">Per visualizzare i record per un'entità, selezionare l'entità nel campo **Nome entità CDS**.</span><span class="sxs-lookup"><span data-stu-id="70991-136">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="70991-137">La griglia mostra tutti i record collegati all'entità selezionata.</span><span class="sxs-lookup"><span data-stu-id="70991-137">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="70991-138">[![Visualizzare i record per un'entità](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="70991-138">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="70991-139">Non tutte le entità di Common Data Service sono attualmente elencate.</span><span class="sxs-lookup"><span data-stu-id="70991-139">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="70991-140">Nella griglia vengono visualizzate solo le entità che supportano l'uso di campi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="70991-140">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="70991-141">Le nuove entità diventano disponibili attraverso il rilascio continuo di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="70991-141">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="70991-142">La griglia include i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="70991-142">The grid includes the following fields:</span></span>

- <span data-ttu-id="70991-143">**Nome entità CDS** - Il nome dell'entità in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="70991-143">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="70991-144">**Riferimento entità CDS** - L'identificatore che Common Data Service utilizza per identificare un record.</span><span class="sxs-lookup"><span data-stu-id="70991-144">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="70991-145">Questo valore equivale al valore **RecId** di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="70991-145">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="70991-146">È possibile trovare l'identificatore quando si apre l'entità di Common Data Service in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="70991-146">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="70991-147">**Nome entità Human Resources** - L'entità che ha eseguito l'ultima sincronizzazione dei dati con Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="70991-147">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="70991-148">L'entità può avere il prefisso Common Data Service o un altro prefisso.</span><span class="sxs-lookup"><span data-stu-id="70991-148">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="70991-149">**Riferimento Human Resources** - Il valore **RecId** associato al record in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="70991-149">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="70991-150">**È stato eliminato da CDS** - Un valore che indica se il record è stato eliminato da Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="70991-150">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="70991-151">Rimuovere l'associazione di un record in Human Resources da Common Data Service</span><span class="sxs-lookup"><span data-stu-id="70991-151">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="70991-152">In caso di problemi durante la sincronizzazione di dati tra Human Resources e Common Data Service, questi potrebbero essere risolti annullando la tracciabilità e consentendo una nuova sincronizzazione della tabella di tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="70991-152">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="70991-153">Se si rimuove l'associazione e si modifica o si elimina un record in Common Data Service, le modifiche non verranno sincronizzate con Human Resources.</span><span class="sxs-lookup"><span data-stu-id="70991-153">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="70991-154">Se si apportano modifiche in Human Resources, viene creato un nuovo record di tracciabilità e il record viene aggiornato in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="70991-154">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="70991-155">Per rimuovere l'associazione di un record tra Human Resources e Common Data Service, selezionare l'entità nel campo **Nome entità CDS**, quindi selezionare **Cancella informazioni di tracciabilità**.</span><span class="sxs-lookup"><span data-stu-id="70991-155">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="70991-156">[![Annullare le informazioni di tracciabilità](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="70991-156">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="70991-157">Per eseguire una sincronizzazione completa sull'entità dopo aver annullato la tracciabilità, vedere la procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="70991-157">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="70991-158">Sincronizzare un'entità tra Human Resources e Common Data Service</span><span class="sxs-lookup"><span data-stu-id="70991-158">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="70991-159">Utilizzare questa procedura se la visualizzazione in Human Resources delle modifiche effettuate in Common Data Service richiede troppo tempo o se è necessario aggiornare la tabella di tracciabilità dopo aver annullato la tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="70991-159">Use this procedure if changes from Common Data Service are taking too long to appear in Human Resources, or if you must refresh the tracking table after you clear the tracking.</span></span>

- <span data-ttu-id="70991-160">Per eseguire una sincronizzazione completa su un'entità tra Human Resources e Common Data Service, selezionare l'entità nel campo **Nome entità CDS**, quindi selezionare **Sincronizza ora**.</span><span class="sxs-lookup"><span data-stu-id="70991-160">To run a full synchronization on an entity between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Sync now**.</span></span>

<span data-ttu-id="70991-161">[![Eseguire una sincronizzazione completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="70991-161">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


