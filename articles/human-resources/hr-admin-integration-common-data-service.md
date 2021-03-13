---
title: Configurare l'integrazione di Dataverse
description: È possibile attivare o disattivare l'integrazione tra Microsoft Dataverse e Dynamics 365 Human Resources. È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo una tabella per risolvere problemi relativi ai dati tra i due ambienti.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
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
ms.openlocfilehash: 38c42469e62bf5457d0281540325a6c56a5f930f
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113158"
---
# <a name="configure-dataverse-integration"></a><span data-ttu-id="64670-104">Configurare l'integrazione di Dataverse</span><span class="sxs-lookup"><span data-stu-id="64670-104">Configure Dataverse integration</span></span>

<span data-ttu-id="64670-105">È possibile attivare o disattivare l'integrazione tra Microsoft Dataverse e Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="64670-105">You can turn integration between Microsoft Dataverse and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="64670-106">È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo una tabella per risolvere problemi relativi ai dati tra i due ambienti.</span><span class="sxs-lookup"><span data-stu-id="64670-106">You can also view the synchronization details, clear tracking data, and resync a table to help troubleshoot data issues between the two environments.</span></span>

> [!NOTE]
> <span data-ttu-id="64670-107">Per ulteriori informazioni su Dataverse (in precedenza Common Data Service) e aggiornamenti terminologici, vedi [ Cosa è Microsoft Dataverse ?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="64670-107">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="64670-108">Quando si disattiva l'integrazione, gli utenti possono effettuare modifiche in Human Resources o Dataverse, ma tali modifiche non sono sincronizzate tra i due ambienti.</span><span class="sxs-lookup"><span data-stu-id="64670-108">When you turn off integration, users can make changes in Human Resources or Dataverse, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="64670-109">Per impostazione predefinita, l'integrazione di dati tra Human Resources e Dataverse è disattivata.</span><span class="sxs-lookup"><span data-stu-id="64670-109">By default, integration between Human Resources and Dataverse is turned off.</span></span>

<span data-ttu-id="64670-110">In tali casi è possibile che si voglia disattivare l'integrazione:</span><span class="sxs-lookup"><span data-stu-id="64670-110">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="64670-111">Si specificano dati tramite Data Management Framework ed è necessario importarli più volte per riportarli a uno stato corretto.</span><span class="sxs-lookup"><span data-stu-id="64670-111">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="64670-112">Esistono problemi con i dati in Human Resources o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="64670-112">There are issues with data in either Human Resources or Dataverse.</span></span> <span data-ttu-id="64670-113">Se si disattiva l'integrazione, è possibile eliminare un record in un ambiente senza eliminarlo nell'altro.</span><span class="sxs-lookup"><span data-stu-id="64670-113">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="64670-114">Quando si riattiva l'integrazione, il record nell'ambiente in cui non è stato eliminato viene sincronizzato con l'ambiente in cui è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="64670-114">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="64670-115">La sincronizzazione inizia alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione di Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="64670-115">Synchronization begins the next time the **Dataverse integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="64670-116">Quando si disattiva l'integrazione dei dati, assicurarsi di non modificare lo stesso record in entrambi gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="64670-116">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="64670-117">Quando si riattiva l'integrazione, l'ultimo record modificato verrà sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="64670-117">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="64670-118">Pertanto, se non si apportano le stesse modifiche al record in entrambi gli ambienti, può verificarsi una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="64670-118">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-dataverse-integration-page"></a><span data-ttu-id="64670-119">Accedere alla pagina Integrazione di Dataverse</span><span class="sxs-lookup"><span data-stu-id="64670-119">Access the Dataverse integration page</span></span>

1. <span data-ttu-id="64670-120">Nell'istanza di Human Resources in cui si desidera visualizzare o configurare le impostazioni per l'integrazione con Dataverse, selezionare il riquadro **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="64670-120">In the Human Resources instance where you want to view or configure settings for the integration with Dataverse, select the **System administration** tile.</span></span>

    <span data-ttu-id="64670-121">[![Riquadro Amministrazione sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="64670-121">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="64670-122">Selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="64670-122">Select the **Links** tab.</span></span>

    <span data-ttu-id="64670-123">[![Scheda Collegamenti](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="64670-123">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="64670-124">Sotto **Integrazioni**, selezionare **Configurazione di Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="64670-124">Under **Integrations**, select **Dataverse configuration**.</span></span>

    <span data-ttu-id="64670-125">[![Collegamento Configurazione di Dataverse](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span><span class="sxs-lookup"><span data-stu-id="64670-125">[![Dataverse configuration link](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a><span data-ttu-id="64670-126">Attivare o disattivare l'integrazione di dati tra Human Resources e Dataverse</span><span class="sxs-lookup"><span data-stu-id="64670-126">Turn data integration between Human Resources and Dataverse on or off</span></span>

- <span data-ttu-id="64670-127">Per attivare l'integrazione, impostare l'opzione **Abilita integrazione Dataverse** su **Sì** nella pagina **Integrazione di Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="64670-127">To turn on integration, set the **Enable Dataverse integration** option to **Yes** on the **Microsoft Dataverse integration** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="64670-128">Quando si attiva l'integrazione, i dati verranno sincronizzati alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione con Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="64670-128">When you turn on integration, data will be synced the next time that the **Dataverse integration missed request sync** batch job runs.</span></span> <span data-ttu-id="64670-129">Tutti i dati dovrebbero essere disponibili dopo il completamento del processo batch.</span><span class="sxs-lookup"><span data-stu-id="64670-129">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="64670-130">Per disattivare l'integrazione, impostare l'opzione su **No**.</span><span class="sxs-lookup"><span data-stu-id="64670-130">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="64670-131">[![Attivare o disattivare l'integrazione con Dataverse](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span><span class="sxs-lookup"><span data-stu-id="64670-131">[![Turning the Dataverse integration on or off](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span></span>

> [!WARNING]
> <span data-ttu-id="64670-132">Si consiglia vivamente di disattivare l'integrazione Dataverse durante l'esecuzione di attività di migrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="64670-132">We strongly recommend turning off Dataverse integration while performing data migration tasks.</span></span> <span data-ttu-id="64670-133">Caricamenti di dati di grandi dimensioni possono influire in modo significativo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64670-133">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="64670-134">Ad esempio, il caricamento di 2000 lavoratori può richiedere diverse ore quando l'integrazione è abilitata e meno di un'ora quando è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="64670-134">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="64670-135">I numeri forniti in questo esempio sono a puro scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="64670-135">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="64670-136">Il tempo esatto necessario per importare i record può variare notevolmente in base a molti fattori.</span><span class="sxs-lookup"><span data-stu-id="64670-136">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="64670-137">Visualizzare i dettagli dell'integrazione dei dati</span><span class="sxs-lookup"><span data-stu-id="64670-137">View data integration details</span></span>

<span data-ttu-id="64670-138">Nella Scheda dettaglio **Amministrazione** della pagina **Integrazione di Microsoft Dataverse**, puoi vedere come le righe sono collegate tra Human Resources e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="64670-138">On the **Administration** FastTab of the **Microsoft Dataverse integration** page, you can see how rows are linked together between Human Resources and Dataverse.</span></span>

- <span data-ttu-id="64670-139">Per visualizzare le righe di una tabella, seleziona la tabella nel campo **Tabella Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="64670-139">To view the rows for a table, select the table in the **Dataverse table** field.</span></span> <span data-ttu-id="64670-140">La griglia mostra tutte le righe collegate alla tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="64670-140">The grid shows all the rows that are linked to the selected table.</span></span>

> [!NOTE]
> <span data-ttu-id="64670-141">Non tutte le tabelle di Dataverse sono attualmente elencate.</span><span class="sxs-lookup"><span data-stu-id="64670-141">Not all Dataverse tables are currently listed.</span></span> <span data-ttu-id="64670-142">Nella griglia vengono visualizzate solo le tabelle che supportano l'uso di campi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="64670-142">Only tables that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="64670-143">Le nuove tabelle diventano disponibili attraverso il rilascio continuo di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="64670-143">New tables become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="64670-144">La griglia include i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="64670-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="64670-145">**Tabella Dataverse**: il nome della tabella in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="64670-145">**Dataverse table** – The name of the table in Dataverse.</span></span>
- <span data-ttu-id="64670-146">**Riferimento tabella Dataverse**: l'identificatore utilizzato da Dataverse per identificare un record.</span><span class="sxs-lookup"><span data-stu-id="64670-146">**Dataverse table reference** – The identifier that Dataverse uses to identify a record.</span></span> <span data-ttu-id="64670-147">Questo valore equivale al valore **RecId** di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="64670-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="64670-148">Puoi trovare l'identificatore quando si apre la tabella di Dataverse in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="64670-148">You can find the identifier when you open the Dataverse table in Microsoft Excel.</span></span>
- <span data-ttu-id="64670-149">**Nome entità Human Resources**: l'entità Human Resources che ha eseguito l'ultima sincronizzazione dei dati con Dataverse.</span><span class="sxs-lookup"><span data-stu-id="64670-149">**Human Resources entity name** – The Human Resources entity that last synced data to Dataverse.</span></span> <span data-ttu-id="64670-150">L'entità può avere il prefisso Dataverse o un altro prefisso.</span><span class="sxs-lookup"><span data-stu-id="64670-150">The entity can have either the Dataverse prefix or another prefix.</span></span>
- <span data-ttu-id="64670-151">**Riferimento Human Resources** - Il valore **RecId** associato al record in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="64670-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="64670-152">**Eliminato da Dataverse**: un valore che indica se la riga è stata eliminata da Dataverse.</span><span class="sxs-lookup"><span data-stu-id="64670-152">**Deleted from Dataverse** – A value that indicates whether the row was deleted from Dataverse.</span></span>

> [!NOTE]
> <span data-ttu-id="64670-153">I record in Human Resources corrispondono alle righe in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="64670-153">Records in Human Resources correspond to rows in Dataverse.</span></span>

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a><span data-ttu-id="64670-154">Rimuovere l'associazione di un record in Human Resources da una riga Dataverse</span><span class="sxs-lookup"><span data-stu-id="64670-154">Remove the association of a Human Resources record from a Dataverse row</span></span>

<span data-ttu-id="64670-155">In caso di problemi durante la sincronizzazione di dati tra Human Resources e Dataverse, questi potrebbero essere risolti annullando la tracciabilità e consentendo una nuova sincronizzazione della tabella di tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="64670-155">If you experience issues during data synchronization between Human Resources and Dataverse, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="64670-156">Se si rimuove l'associazione e si modifica o si elimina una riga in Dataverse, le modifiche non verranno sincronizzate con Human Resources.</span><span class="sxs-lookup"><span data-stu-id="64670-156">If you remove the association, and then change or delete a row in Dataverse, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="64670-157">Se si apportano modifiche in Human Resources, viene creato un nuovo record di tracciabilità e la riga viene aggiornata in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="64670-157">If you make changes in Human Resources, a new tracking record is created, and the row is updated in Dataverse.</span></span>

- <span data-ttu-id="64670-158">Per rimuovere l'associazione di un record tra Human Resources e una riga Dataverse, seleziona la tabella nel campo **Tabella Dataverse**, quindi seleziona **Cancella informazioni di tracciabilità**.</span><span class="sxs-lookup"><span data-stu-id="64670-158">To remove the association of a Human Resources record and a Dataverse row, select the table in the **Dataverse table** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="64670-159">[![Annullare le informazioni di tracciabilità](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="64670-159">[![Clearing tracking information](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span></span>

<span data-ttu-id="64670-160">Per eseguire una sincronizzazione completa sulla tabella dopo aver annullato la tracciabilità, vedere la procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="64670-160">To run a full synchronization on the table after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-a-table-between-human-resources-and-dataverse"></a><span data-ttu-id="64670-161">Sincronizzare una tabella tra Human Resources e Dataverse</span><span class="sxs-lookup"><span data-stu-id="64670-161">Sync a table between Human Resources and Dataverse</span></span>

<span data-ttu-id="64670-162">Utilizzare questa procedura quando:</span><span class="sxs-lookup"><span data-stu-id="64670-162">Use this procedure when:</span></span>

- <span data-ttu-id="64670-163">Le modifiche da Dataverse impiegano troppo tempo ad apparire in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="64670-163">Changes from Dataverse take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="64670-164">È necessario aggiornare la tabella di monitoraggio dopo aver cancellato il rilevamento.</span><span class="sxs-lookup"><span data-stu-id="64670-164">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="64670-165">Per eseguire una sincronizzazione completa su una tabella tra Human Resources e Dataverse:</span><span class="sxs-lookup"><span data-stu-id="64670-165">To run a full synchronization on a table between Human Resources and Dataverse:</span></span>

1. <span data-ttu-id="64670-166">Selezionare la tabella nel campo **Tabella Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="64670-166">Select the table in the **Dataverse table** field.</span></span>

2. <span data-ttu-id="64670-167">Selezionare **Sincronizza ora**.</span><span class="sxs-lookup"><span data-stu-id="64670-167">Select **Sync now**.</span></span>

<span data-ttu-id="64670-168">[![Eseguire una sincronizzazione completa](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="64670-168">[![Running a full synchronization](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="64670-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64670-169">See also</span></span>

[<span data-ttu-id="64670-170">Tabelle Dataverse</span><span class="sxs-lookup"><span data-stu-id="64670-170">Dataverse tables</span></span>](hr-developer-entities.md)<br>
[<span data-ttu-id="64670-171">Configurare tabelle virtuali in Dataverse</span><span class="sxs-lookup"><span data-stu-id="64670-171">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="64670-172">Domande frequenti sulle tabelle virtuali in Human Resources</span><span class="sxs-lookup"><span data-stu-id="64670-172">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="64670-173">Che cos'è Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="64670-173">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="64670-174">Aggiornamenti terminologici</span><span class="sxs-lookup"><span data-stu-id="64670-174">Terminology updates</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)
