---
title: Configurare l'integrazione di Common Data Service
description: È possibile attivare o disattivare l'integrazione tra Common Data Service e Dynamics 365 Human Resources. È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo un'entità per risolvere problemi relativi ai dati tra i due ambienti.
author: andreabichsel
manager: AnnBe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d9ee4715526e18b33ae4b7e90b081ed5868bb19c
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527928"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="30783-104">Configurare l'integrazione di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="30783-104">Configure Common Data Service integration</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="30783-105">È possibile attivare o disattivare l'integrazione tra Common Data Service e Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="30783-105">You can turn integration between Common Data Service and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="30783-106">È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo un'entità per risolvere problemi relativi ai dati tra i due ambienti.</span><span class="sxs-lookup"><span data-stu-id="30783-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="30783-107">Quando si disattiva l'integrazione, gli utenti possono effettuare modifiche in Human Resources o Common Data Service, ma tali modifiche non sono sincronizzate tra i due ambienti.</span><span class="sxs-lookup"><span data-stu-id="30783-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="30783-108">Per impostazione predefinita, l'integrazione di dati tra Human Resources e Common Data Service è disattivata.</span><span class="sxs-lookup"><span data-stu-id="30783-108">By default, integration between Human Resources and Common Data Service is turned off.</span></span>

<span data-ttu-id="30783-109">In tali casi è possibile che si voglia disattivare l'integrazione:</span><span class="sxs-lookup"><span data-stu-id="30783-109">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="30783-110">Si specificano dati tramite Data Management Framework ed è necessario importarli più volte per riportarli a uno stato corretto.</span><span class="sxs-lookup"><span data-stu-id="30783-110">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="30783-111">Esistono problemi con i dati in Human Resources o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="30783-111">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="30783-112">Se si disattiva l'integrazione, è possibile eliminare un record in un ambiente senza eliminarlo nell'altro.</span><span class="sxs-lookup"><span data-stu-id="30783-112">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="30783-113">Quando si riattiva l'integrazione, il record nell'ambiente in cui non è stato eliminato viene sincronizzato con l'ambiente in cui è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="30783-113">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="30783-114">La sincronizzazione inizia alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione di Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="30783-114">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="30783-115">Quando si disattiva l'integrazione dei dati, assicurarsi di non modificare lo stesso record in entrambi gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="30783-115">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="30783-116">Quando si riattiva l'integrazione, l'ultimo record modificato verrà sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="30783-116">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="30783-117">Pertanto, se non si apportano le stesse modifiche al record in entrambi gli ambienti, può verificarsi una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="30783-117">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="30783-118">Accedere alla pagina Integrazione di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="30783-118">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="30783-119">Nell'istanza di Human Resources in cui si desidera visualizzare o configurare le impostazioni per l'integrazione con Common Data Service, selezionare il riquadro **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="30783-119">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="30783-120">[![Riquadro Amministrazione sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="30783-120">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="30783-121">Selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="30783-121">Select the **Links** tab.</span></span>

    <span data-ttu-id="30783-122">[![Scheda Collegamenti](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="30783-122">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="30783-123">Sotto **Integrazioni**, selezionare **Configurazione di Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="30783-123">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="30783-124">[![Collegamento Configurazione di Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="30783-124">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="30783-125">Attivare o disattivare l'integrazione di dati tra Human Resources e Common Data Service</span><span class="sxs-lookup"><span data-stu-id="30783-125">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="30783-126">Per attivare l'integrazione, impostare l'opzione **Abilita l'integrazione con Common Data Service** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="30783-126">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30783-127">Quando si attiva l'integrazione, i dati verranno sincronizzati alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione con Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="30783-127">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="30783-128">Tutti i dati dovrebbero essere disponibili dopo il completamento del processo batch.</span><span class="sxs-lookup"><span data-stu-id="30783-128">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="30783-129">Per disattivare l'integrazione, impostare l'opzione su **No**.</span><span class="sxs-lookup"><span data-stu-id="30783-129">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="30783-130">[![Attivare o disattivare l'integrazione con Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="30783-130">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

> [!WARNING]
> <span data-ttu-id="30783-131">Si consiglia vivamente di disattivare l'integrazione Common Data Service durante l'esecuzione di attività di migrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="30783-131">We strongly recommend turning off Common Data Service integration while performing data migration tasks.</span></span> <span data-ttu-id="30783-132">Caricamenti di dati di grandi dimensioni possono influire in modo significativo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="30783-132">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="30783-133">Ad esempio, il caricamento di 2000 lavoratori può richiedere diverse ore quando l'integrazione è abilitata e meno di un'ora quando è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="30783-133">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="30783-134">I numeri forniti in questo esempio sono a puro scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="30783-134">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="30783-135">Il tempo esatto necessario per importare i record può variare notevolmente in base a molti fattori.</span><span class="sxs-lookup"><span data-stu-id="30783-135">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="30783-136">Visualizzare i dettagli dell'integrazione dei dati</span><span class="sxs-lookup"><span data-stu-id="30783-136">View data integration details</span></span>

<span data-ttu-id="30783-137">Nella Scheda dettaglio **Amministrazione** della pagina **Integrazione con Common Data Service**, è possibile vedere come i record sono collegati tra Human Resources e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="30783-137">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="30783-138">Per visualizzare i record per un'entità, selezionare l'entità nel campo **Nome entità CDS**.</span><span class="sxs-lookup"><span data-stu-id="30783-138">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="30783-139">La griglia mostra tutti i record collegati all'entità selezionata.</span><span class="sxs-lookup"><span data-stu-id="30783-139">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="30783-140">[![Visualizzare i record per un'entità](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="30783-140">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="30783-141">Non tutte le entità di Common Data Service sono attualmente elencate.</span><span class="sxs-lookup"><span data-stu-id="30783-141">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="30783-142">Nella griglia vengono visualizzate solo le entità che supportano l'uso di campi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="30783-142">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="30783-143">Le nuove entità diventano disponibili attraverso il rilascio continuo di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="30783-143">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="30783-144">La griglia include i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="30783-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="30783-145">**Nome entità CDS** - Il nome dell'entità in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="30783-145">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="30783-146">**Riferimento entità CDS** - L'identificatore che Common Data Service utilizza per identificare un record.</span><span class="sxs-lookup"><span data-stu-id="30783-146">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="30783-147">Questo valore equivale al valore **RecId** di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="30783-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="30783-148">È possibile trovare l'identificatore quando si apre l'entità di Common Data Service in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="30783-148">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="30783-149">**Nome entità Human Resources** - L'entità che ha eseguito l'ultima sincronizzazione dei dati con Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="30783-149">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="30783-150">L'entità può avere il prefisso Common Data Service o un altro prefisso.</span><span class="sxs-lookup"><span data-stu-id="30783-150">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="30783-151">**Riferimento Human Resources** - Il valore **RecId** associato al record in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="30783-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="30783-152">**È stato eliminato da CDS** - Un valore che indica se il record è stato eliminato da Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="30783-152">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="30783-153">Rimuovere l'associazione di un record in Human Resources da Common Data Service</span><span class="sxs-lookup"><span data-stu-id="30783-153">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="30783-154">In caso di problemi durante la sincronizzazione di dati tra Human Resources e Common Data Service, questi potrebbero essere risolti annullando la tracciabilità e consentendo una nuova sincronizzazione della tabella di tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="30783-154">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="30783-155">Se si rimuove l'associazione e si modifica o si elimina un record in Common Data Service, le modifiche non verranno sincronizzate con Human Resources.</span><span class="sxs-lookup"><span data-stu-id="30783-155">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="30783-156">Se si apportano modifiche in Human Resources, viene creato un nuovo record di tracciabilità e il record viene aggiornato in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="30783-156">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="30783-157">Per rimuovere l'associazione di un record tra Human Resources e Common Data Service, selezionare l'entità nel campo **Nome entità CDS**, quindi selezionare **Cancella informazioni di tracciabilità**.</span><span class="sxs-lookup"><span data-stu-id="30783-157">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="30783-158">[![Annullare le informazioni di tracciabilità](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="30783-158">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="30783-159">Per eseguire una sincronizzazione completa sull'entità dopo aver annullato la tracciabilità, vedere la procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="30783-159">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="30783-160">Sincronizzare un'entità tra Human Resources e Common Data Service</span><span class="sxs-lookup"><span data-stu-id="30783-160">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="30783-161">Utilizzare questa procedura quando:</span><span class="sxs-lookup"><span data-stu-id="30783-161">Use this procedure when:</span></span>

- <span data-ttu-id="30783-162">Le modifiche da Common Data Service impiegano troppo tempo ad apparire in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="30783-162">Changes from Common Data Service take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="30783-163">È necessario aggiornare la tabella di monitoraggio dopo aver cancellato il rilevamento.</span><span class="sxs-lookup"><span data-stu-id="30783-163">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="30783-164">Per eseguire una sincronizzazione completa su un'entità tra Human Resources e Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="30783-164">To run a full synchronization on an entity between Human Resources and Common Data Service:</span></span>

1. <span data-ttu-id="30783-165">Selezionare l'entità nel campo **Nome entità CDS**.</span><span class="sxs-lookup"><span data-stu-id="30783-165">Select the entity in the **CDS entity name** field.</span></span>

2. <span data-ttu-id="30783-166">Selezionare **Sincronizza ora**.</span><span class="sxs-lookup"><span data-stu-id="30783-166">Select **Sync now**.</span></span>

<span data-ttu-id="30783-167">[![Eseguire una sincronizzazione completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="30783-167">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


