---
title: Reimpostare il data mart dei report finanziari
description: Questo argomento descrive come reimpostare il data mart dei report finanziari.
author: aolson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 5b956dcc5a4a93033396ae0ffcf8b7aeba2cf3f2
ms.openlocfilehash: a07e8b5bae2c4f71e9212cd2f8080d2481769818
ms.contentlocale: it-it
ms.lasthandoff: 12/14/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a><span data-ttu-id="6ec2f-103">Reimpostare il data mart dei report finanziari</span><span class="sxs-lookup"><span data-stu-id="6ec2f-103">Reset the Financial reporting data mart</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6ec2f-104">In questo argomento viene descritto come reimpostare il data mart dei report finanziari per le versioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ec2f-104">This topic explains how to reset the Financial reporting data mart for the following versions:</span></span>

- <span data-ttu-id="6ec2f-105">Creazione di report finanziari di Microsoft Dynamics 365 for Finance and Operations versione 7.2.6.0 e successiva</span><span class="sxs-lookup"><span data-stu-id="6ec2f-105">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>
- <span data-ttu-id="6ec2f-106">Creazione di report finanziari di Microsoft Dynamics 365 for Finance and Operations versione 7.0.10000.4 e successiva</span><span class="sxs-lookup"><span data-stu-id="6ec2f-106">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>
- <span data-ttu-id="6ec2f-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (locale)</span><span class="sxs-lookup"><span data-stu-id="6ec2f-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (on-premises)</span></span>

<span data-ttu-id="6ec2f-108">Per ottenere Creazione di report finanziari di Finance and Operations versione 7.2.6.0, è possibile scaricare KB 4052514 da <https://fix.lcs.dynamics.com/Issue/Resolved?kb=4052514>.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-108">To get Finance and Operations Financial reporting release 7.2.6.0, you can download KB 4052514 from <https://fix.lcs.dynamics.com/Issue/Resolved?kb=4052514>.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a><span data-ttu-id="6ec2f-109">Reimpostare il data mart di report finanziari per Creazione report finanziari di Finance and Operations versione 7.2.6.0 e successiva</span><span class="sxs-lookup"><span data-stu-id="6ec2f-109">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a><span data-ttu-id="6ec2f-110">Reimpostare il data mart di report finanziari da Progettazione report</span><span class="sxs-lookup"><span data-stu-id="6ec2f-110">Reset the Financial reporting data mart from Report designer</span></span>

> [!NOTE]
> <span data-ttu-id="6ec2f-111">I passaggi in questo processo sono supportati per Creazione report finanziari di Finance and Operations versione 7.2.6.0 e successive.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-111">The steps in this process are supported for Finance and Operations Financial reporting release 7.2.6.0 and later.</span></span> <span data-ttu-id="6ec2f-112">Se si dispone di una versione precedente, contattare il team di Supporto per assistenza.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-112">If you have an earlier release, contact the Support team for assistance.</span></span>

<span data-ttu-id="6ec2f-113">In scenari specifici, potrebbe essere necessario reimpostare il data mart per i report finanziari.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-113">In specific scenarios, you might have to reset the data mart for Financial reporting.</span></span> <span data-ttu-id="6ec2f-114">È possibile completare questa attività nel client di Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-114">You can complete this task in the Report designer client.</span></span> <span data-ttu-id="6ec2f-115">Di seguito sono descritti alcuni scenari in cui potrebbe essere necessario reimpostare il data mart:</span><span class="sxs-lookup"><span data-stu-id="6ec2f-115">Here are some scenarios where you might have to reset the data mart:</span></span>

- <span data-ttu-id="6ec2f-116">Il database di Finance and Operations è stato ripristinato, ma non è stato ripristinato il database data mart.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-116">The Finance and Operations database was restored, but the data mart database wasn't restored.</span></span>
- <span data-ttu-id="6ec2f-117">Si vedono dati errati per un periodo.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-117">You see incorrect data for a period.</span></span>
- <span data-ttu-id="6ec2f-118">Il Supporto consiglia di reimpostare il data mart come parte di un passaggio della risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-118">Support instructs you to reset the data mart as part of a troubleshooting step.</span></span>

<span data-ttu-id="6ec2f-119">La reimpostazione del data mart deve essere eseguita solo nei periodi in cui la quantità di elaborazione è ridotta.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-119">The data mart reset should be done only during times when the amount of processing on the database is small.</span></span> <span data-ttu-id="6ec2f-120">La funzionalità di creazione di report finanziari non è disponibile durante il processo di reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-120">Financial reporting will be unavailable during the reset process.</span></span>

#### <a name="reset-the-data-mart"></a><span data-ttu-id="6ec2f-121">Reimpostare il data mart</span><span class="sxs-lookup"><span data-stu-id="6ec2f-121">Reset the data mart</span></span>

<span data-ttu-id="6ec2f-122">Per reimpostare il data mart, in Progettazione report, nel menu **Strumenti** selezionare **Reimposta data mart**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-122">To reset the data mart, in Report designer, on the **Tools** menu, select **Reset Data Mart**.</span></span> <span data-ttu-id="6ec2f-123">La finestra di dialogo che viene visualizzata contiene due sezioni: **Statistiche** e **Reimpostazione**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-123">The dialog box that appears has two sections: **Statistics** and **Reset**.</span></span>

<span data-ttu-id="6ec2f-124">[![Reimpostare la finestra di dialogo Data mart](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span><span class="sxs-lookup"><span data-stu-id="6ec2f-124">[![Reset Data Mart dialog box](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span></span>

##### <a name="integration-attempts"></a><span data-ttu-id="6ec2f-125">Tentativi di integrazione</span><span class="sxs-lookup"><span data-stu-id="6ec2f-125">Integration attempts</span></span>

<span data-ttu-id="6ec2f-126">La griglia **Tentativi di integrazione** visualizza il numero di volte che il sistema è tentato di integrare le transazioni.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-126">The **Integration attempts** grid shows how many times the system has tried to integrate transactions.</span></span> <span data-ttu-id="6ec2f-127">Il sistema continua a provare a integrare dati nell'arco di giorni se i primissimi tentativi non hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-127">The system continues to try to integrate data over a period of days if the first few attempts aren't successful.</span></span> <span data-ttu-id="6ec2f-128">Il data mart deve essere reimpostato se il numero di tentativo è pari a 8 o superiore e se vi sono molte combinazioni di dimensioni o record di transazioni.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-128">You will know that the data mart must be reset is if the number of attempts is 8 or more, and if there are many Dimension combination or Transaction records.</span></span> <span data-ttu-id="6ec2f-129">In questo caso, i dati non vengono inseriti nel report.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-129">In this situation, the data won't be reported on.</span></span>

##### <a name="data-status"></a><span data-ttu-id="6ec2f-130">Stato dati</span><span class="sxs-lookup"><span data-stu-id="6ec2f-130">Data status</span></span>

<span data-ttu-id="6ec2f-131">La griglia **Stato dati** include uno snapshot delle transazioni, i tassi di cambio e valori di dimensione nel data mart.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-131">The **Data status** grid provides a snapshot of the transactions, exchange rates, and dimension values in the data mart.</span></span> <span data-ttu-id="6ec2f-132">La presenza di un numero elevato di record non aggiornati indica che sono stati eseguiti numerosi aggiornamenti ai record.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-132">A large number of stale records indicates that numerous updates to the records have occurred.</span></span> <span data-ttu-id="6ec2f-133">Questa situazione può allungare i tempi di generazione dei report.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-133">This situation might cause slower report generation times.</span></span>

##### <a name="misaligned-main-account-categories"></a><span data-ttu-id="6ec2f-134">Categorie di conti principali non allineate</span><span class="sxs-lookup"><span data-stu-id="6ec2f-134">Misaligned main account categories</span></span>

<span data-ttu-id="6ec2f-135">Se si utilizza una versione precedente a Creazione report finanziari di Microsoft Dynamics 365 for Finance and Operations versione 7.2.1, potrebbe essere necessario reimpostare il data mart se si rinominano i conti e li si sposta tra categorie di conti.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-135">If you're using a release that is earlier than Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.1, you might have to reset the data mart if you rename accounts and move accounts between account categories.</span></span> <span data-ttu-id="6ec2f-136">Queste azioni possono determinare il disallineamento delle categorie di conti principali.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-136">These actions can cause main account categories to become misaligned.</span></span> <span data-ttu-id="6ec2f-137">Il campo **Categorie di conti principali non allineate** mostra se è presente questo problema.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-137">The **Misaligned main account categories** field shows whether you're experiencing that issue.</span></span>

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a><span data-ttu-id="6ec2f-138">Reimpostare il data mart in Creazione report finanziari di Finance and Operations versione 7.2.6.0</span><span class="sxs-lookup"><span data-stu-id="6ec2f-138">Reset the data mart in Finance and Operations Financial reporting release 7.2.6.0</span></span>

<span data-ttu-id="6ec2f-139">Per reimpostare il data mart in Creazione report finanziari di Finance and Operations versione 7.2.6.0 e versioni precedenti, nella finestra di dialogo **Reimposta data mart** selezionare la casella di controllo **Reimposta data mart** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-139">To reset the data mart in Finance and Operations Financial reporting release 7.2.6.0 and earlier, in the **Reset Data Mart** dialog box, select the **Reset data mart** check box, and then select **OK**.</span></span> <span data-ttu-id="6ec2f-140">È consigliabile reimpostare il data mart solo durante il periodo di inattività programmata.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-140">You should reset the data mart only during scheduled downtime.</span></span>

<span data-ttu-id="6ec2f-141">[![Casella di controllo Reimposta data mart](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span><span class="sxs-lookup"><span data-stu-id="6ec2f-141">[![Reset data mart check box](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span></span>

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a><span data-ttu-id="6ec2f-142">Reimpostare il data mart e selezionare un motivo in Creazione report finanziari di Microsoft Dynamics 365 for Finance and Operations versione 7.3.0</span><span class="sxs-lookup"><span data-stu-id="6ec2f-142">Reset the data mart and select a reason in Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.3.0</span></span>

<span data-ttu-id="6ec2f-143">Se si determina che è necessario reimpostare il data mart, selezionare la casella di controllo **Reimposta data mart** e quindi selezionare un motivo nel campo **Motivo**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-143">If you determine that a data mart reset is required, select the **Reset data mart** check box, and then select a reason in the **Reason** field.</span></span> <span data-ttu-id="6ec2f-144">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ec2f-144">The following options are available:</span></span>

- <span data-ttu-id="6ec2f-145">**Dati mancanti o non corretti** - In base alle statistiche è stato determinato che potrebbero mancare dei dati.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-145">**Missing or incorrect data** – Based on the statistics, you've determined that data might be missing.</span></span> <span data-ttu-id="6ec2f-146">Prima di continuare, si consiglia di collaborare con il Supporto per determinare la causa radice.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-146">Before you continue, we recommend that you work with Support to determine the root cause.</span></span>
- <span data-ttu-id="6ec2f-147">**Ripristina database** - Il database di Finance and Operations è stato ripristinato, ma non è stato ripristinato il database data mart.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-147">**Restore database** – The Finance and Operations database was restored, but the database for the Financial reporting data mart wasn't restored.</span></span>
- <span data-ttu-id="6ec2f-148">**Altro** - Si reimposta il data mart per un altro motivo.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-148">**Other** – You're resetting the data mart for another reason.</span></span> <span data-ttu-id="6ec2f-149">Se si teme che vi sia un problema, contattare il Supporto per identificarlo.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-149">If you're concerned that there is an issue, contact Support to identify it.</span></span>

<span data-ttu-id="6ec2f-150">[![Reimposta data mart](./media/Integration.png)](./media/Integration.png)</span><span class="sxs-lookup"><span data-stu-id="6ec2f-150">[![Reset data mart](./media/Integration.png)](./media/Integration.png)</span></span>

> [!NOTE]
> <span data-ttu-id="6ec2f-151">Verificare che tutte le attività di reimpostazione data mart abbiano completato un caricamento iniziale prima di iniziare una reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-151">Verify that all data mart reset tasks have completed an initial load before you begin a reset.</span></span> <span data-ttu-id="6ec2f-152">È possibile verificare questo cercando un valore nella colonna Ultimo runtime selezionando **Strumenti** &gt;. **Stato integrazione**</span><span class="sxs-lookup"><span data-stu-id="6ec2f-152">You can confirm this by looking for a value in the Last Runtime column by selecting **Tools** &gt; **Integration status**.</span></span>

#### <a name="clear-users-and-companies"></a><span data-ttu-id="6ec2f-153">Cancella utenti e società</span><span class="sxs-lookup"><span data-stu-id="6ec2f-153">Clear users and companies</span></span>

<span data-ttu-id="6ec2f-154">Selezionare la casella di controllo **Cancella utenti e società** se è stato ripristinato il database, ma successivamente sono state apportate modifiche agli utenti o alle società.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-154">Select the **Clear users and companies** check box if you restored your database, but you then made changes to users or companies.</span></span> <span data-ttu-id="6ec2f-155">Raramente si dovrebbe selezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-155">You should rarely have to select this check box.</span></span>

<span data-ttu-id="6ec2f-156">Quando si è pronti per avviare il processo di reimpostazione, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-156">When you're ready to start the reset process, select **OK**.</span></span> <span data-ttu-id="6ec2f-157">Verrà richiesto di confermare che si è pronti ad avviare il processo.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-157">You're prompted to confirm that you're ready to start the process.</span></span> <span data-ttu-id="6ec2f-158">Tenere presente che Creazione report finanziari non sarà disponibile durante la reimpostazione e l'integrazione dei dati iniziali che avviene in un momento successivo.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-158">Note that Financial reporting won't be available during the reset and the initial data integration that occurs afterward.</span></span>

<span data-ttu-id="6ec2f-159">Se si desidera esaminare lo stato dell'integrazione, selezionare **Strumenti** &gt; **Stato integrazione** per vedere l'ultima volta che è stata eseguita l'integrazione e lo stato.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-159">If you want to review the status of the integration, select **Tools** &gt; **Integration status** to see the last time that the integration was run and the status.</span></span>

<span data-ttu-id="6ec2f-160">[![Visualizzare lo stato dell'integrazione](./media/New-integration.PNG)](./media/New-integration.PNG)</span><span class="sxs-lookup"><span data-stu-id="6ec2f-160">[![View the status of the integration](./media/New-integration.PNG)](./media/New-integration.PNG)</span></span>

> [!NOTE]
> <span data-ttu-id="6ec2f-161">La reimpostazione è finita quando tutti i mapping mostrano che lo stato di RanToCompletion e della finestra dello stato di integrazione è "Integrazione completata" nell'angolo in basso a sinistra.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-161">The reset is finished when all mappings show the status of RanToCompletion and the Integration Status window says “Integration complete” in the bottom-left corner.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a><span data-ttu-id="6ec2f-162">Reimpostare il data mart di report finanziari per Creazione report finanziari di Finance and Operations versione 7.0.10000.4 e successiva</span><span class="sxs-lookup"><span data-stu-id="6ec2f-162">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>

<span data-ttu-id="6ec2f-163">Se si ripristina il database di Finance and Operations da un backup o si copia il database da un altro ambiente, è necessario completare i passaggi in questa sezione per assicurarsi che il data mart dei report finanziari utilizzi correttamente il database di Finance and Operations ripristinato.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-163">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this section to help guarantee that the Financial reporting data mart correctly uses the restored Finance and Operations database.</span></span>

> [!NOTE]
> <span data-ttu-id="6ec2f-164">I passaggi in questo processo sono supportati per l'applicazione Microsoft Dynamics AX versione 7.0.1 (maggio 2016) (build applicazione 7.0.1265.23014 e build Creazione report finanziari 7.0.10000.4) e successive.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-164">The steps in this process are supported for Microsoft Dynamics AX application version 7.0.1 (May 2016) (application build 7.0.1265.23014 and Financial reporting build 7.0.10000.4) and later.</span></span> <span data-ttu-id="6ec2f-165">Se si dispone di una versione precedente di Finance and Operations, contattare il team del Supporto per assistenza.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-165">If you have an earlier version of Finance and Operations, contact Support for assistance.</span></span>

### <a name="export-report-definitions"></a><span data-ttu-id="6ec2f-166">Esportare definizioni di report</span><span class="sxs-lookup"><span data-stu-id="6ec2f-166">Export report definitions</span></span>

<span data-ttu-id="6ec2f-167">Innanzitutto, attenersi alla procedura seguente per esportare i progetti di report da Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-167">First, follow these steps to export the report designs from Report designer.</span></span>

1. <span data-ttu-id="6ec2f-168">In Progettazione report, selezionare **Società** &gt; **Gruppi di blocchi predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-168">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="6ec2f-169">Selezionare il gruppo di blocchi predefiniti da esportare, quindi selezionare **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-169">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ec2f-170">Per Finance and Operations, è supportato un solo gruppo di blocchi predefiniti, **Predefinito**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-170">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="6ec2f-171">Selezionare le definizioni di report da esportare:</span><span class="sxs-lookup"><span data-stu-id="6ec2f-171">Select the report definitions to export:</span></span>

    - <span data-ttu-id="6ec2f-172">Per esportare tutte le definizioni di report e i blocchi predefiniti associati, selezionare **Seleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-172">To export all your report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="6ec2f-173">Per esportare specifici report, righe, colonne, alberi o set di dimensioni, selezionare la scheda appropriata e selezionare gli elementi da esportare.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-173">To export specific reports, rows, columns, trees, or dimension sets, select the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="6ec2f-174">Per selezionare più elementi in una scheda, tenere premuto CTRL. Quando si selezionano i report da esportare, vengono selezionate le righe, le colonne, gli alberi e i set di dimensioni associati.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-174">Press and hold the Ctrl key to select multiple items on a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4. <span data-ttu-id="6ec2f-175">Selezionare **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-175">Select **Export**.</span></span>
5. <span data-ttu-id="6ec2f-176">Immettere un nome di file e selezionare un percorso protetto in cui si desidera salvare le definizioni di report esportate.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-176">Enter a file name, and select a secure location where you want to save the exported report definitions.</span></span>
6. <span data-ttu-id="6ec2f-177">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-177">Select **Save**.</span></span>

<span data-ttu-id="6ec2f-178">È possibile copiare o caricare il file in un percorso protetto.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-178">You can copy or upload the file to a secure location.</span></span> <span data-ttu-id="6ec2f-179">In questo modo, il file può essere importato in un ambiente diverso in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-179">In this way, the file can be imported into a different environment later.</span></span> <span data-ttu-id="6ec2f-180">Per informazioni su come utilizzare un account di archiviazione di Microsoft Azure, vedere [Trasferire dati con l'utilità della riga di comando AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="6ec2f-180">For information about how to use a Microsoft Azure storage account, see [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span>

> [!NOTE]
> <span data-ttu-id="6ec2f-181">Microsoft non fornisce un account di archiviazione nel contratto di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-181">Microsoft doesn't provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="6ec2f-182">È necessario richiedere un account di archiviazione o impostarne uno da una sottoscrizione Azure separata.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-182">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span>

> [!WARNING]
> <span data-ttu-id="6ec2f-183">Tenere presente il comportamento dell'unità D nelle macchine virtuali di Azure.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-183">Be aware of the behavior of drive D on Azure virtual machines (VMs).</span></span> <span data-ttu-id="6ec2f-184">Non archiviare in modo permanente i gruppi esportati di blocchi predefiniti nell'unità D. Per ulteriori informazioni sulle unità temporanee, vedere [Comprensione dell'unità temporanea in Macchine virtuali di Microsoft Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="6ec2f-184">Don't permanently store your exported building block groups on drive D. For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

### <a name="stop-services"></a><span data-ttu-id="6ec2f-185">Interrompere i servizi</span><span class="sxs-lookup"><span data-stu-id="6ec2f-185">Stop services</span></span>

<span data-ttu-id="6ec2f-186">I seguenti servizi di Microsoft Windows hanno connessioni aperte al database di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-186">The following Microsoft Windows services will have open connections to the Finance and Operations database.</span></span> <span data-ttu-id="6ec2f-187">È pertanto necessario utilizzare Desktop remoto per collegarsi a tutti i computer nell'ambiente e quindi utilizzare services.msc per arrestare questi servizi.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-187">Therefore, you must use Microsoft Remote Desktop to connect to all the computers in the environment and then use services.msc to stop these services.</span></span>

- <span data-ttu-id="6ec2f-188">Servizio di pubblicazione World Wide Web (in tutti i computer Application Object Servers [AOS])</span><span class="sxs-lookup"><span data-stu-id="6ec2f-188">World wide web publishing service (on all Application Object Servers [AOS] computers)</span></span>
- <span data-ttu-id="6ec2f-189">Servizio di gestione dei batch di Microsoft Dynamics 365 for Finance and Operations (solo in computer AOS non privati)</span><span class="sxs-lookup"><span data-stu-id="6ec2f-189">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="6ec2f-190">Servizio del processo Management Reporter 2012 (solo nei computer Business intelligence [BI])</span><span class="sxs-lookup"><span data-stu-id="6ec2f-190">Management Reporter 2012 Process Service (on Business intelligence [BI] computers only)</span></span>

### <a name="reset"></a><span data-ttu-id="6ec2f-191">Reimpostazione</span><span class="sxs-lookup"><span data-stu-id="6ec2f-191">Reset</span></span>

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="6ec2f-192">Scaricare il pacchetto MinorVersionDataUpgrade.zip più recente</span><span class="sxs-lookup"><span data-stu-id="6ec2f-192">Download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="6ec2f-193">Scaricare il pacchetto MinorVersionDataUpgrade.zip più recente.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-193">Download the latest MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="6ec2f-194">Per istruzioni su come trovare e scaricare la versione corretta del pacchetto di aggiornamento dei dati, vedere [Scaricare il pacchetto distribuibile di aggiornamento dei dati più recente](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package).</span><span class="sxs-lookup"><span data-stu-id="6ec2f-194">For instructions about how to find and download the correct version of the data upgrade package, see the[Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package).</span></span> 

<span data-ttu-id="6ec2f-195">Non è necessario eseguire un aggiornamento per scaricare il pacchetto MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-195">An upgrade isn't required in order to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="6ec2f-196">Di conseguenza, è sufficiente seguire i passaggi descritti nella sezione "Scaricare il pacchetto distribuibile di aggiornamento dei dati più recente" di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-196">Therefore, you just have follow the steps in the "Download the latest data upgrade deployable package" section of that topic.</span></span> <span data-ttu-id="6ec2f-197">È possibile ignorare tutti gli altri passaggi descritti nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-197">You can skip all the other steps in the topic.</span></span>

#### <a name="run-scripts-against-the-finance-and-operations-database"></a><span data-ttu-id="6ec2f-198">Eseguire gli script sul database di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6ec2f-198">Run scripts against the Finance and Operations database</span></span>

<span data-ttu-id="6ec2f-199">Eseguire i seguenti script sul database di Finance and Operations (non sul database dei report finanziari):</span><span class="sxs-lookup"><span data-stu-id="6ec2f-199">Run the following scripts against the Finance and Operations database (not against the Financial reporting database):</span></span>

- <span data-ttu-id="6ec2f-200">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="6ec2f-200">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
- <span data-ttu-id="6ec2f-201">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="6ec2f-201">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="6ec2f-202">Questi script garantiscono la correttezza degli utenti, dei ruoli e delle impostazioni di rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-202">These scripts help guarantee that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a><span data-ttu-id="6ec2f-203">Eseguire un comando di Windows PowerShell per ripristinare il database</span><span class="sxs-lookup"><span data-stu-id="6ec2f-203">Run a Windows PowerShell command to reset the database</span></span>

<span data-ttu-id="6ec2f-204">Nel computer AOS, avviare Microsoft Windows PowerShell come amministratore ed eseguire i comandi seguenti per reimpostare l'integrazione tra Finance and Operations e Creazione report finanziari.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-204">On the AOS computer, start Microsoft Windows PowerShell as an administrator, and run the following commands to reset the integration between Finance and Operations and Financial reporting.</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

<span data-ttu-id="6ec2f-205">Ecco la descrizione dei parametri del comando **Reset-DatamartIntegration**:</span><span class="sxs-lookup"><span data-stu-id="6ec2f-205">Here is an explanation of the parameters in the **Reset-DatamartIntegration** command:</span></span>

- <span data-ttu-id="6ec2f-206">I valori validi per **-Reason** sono **SERVICING**, **BADDATA** e **OTHER**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-206">The valid values for **-Reason** are **SERVICING**, **BADDATA**, and **OTHER**.</span></span>
- <span data-ttu-id="6ec2f-207">Il parametro **-ReasonDetail** è testo libero.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-207">The **-ReasonDetail** parameter is free text.</span></span>
- <span data-ttu-id="6ec2f-208">Il motivo e il dettaglio del motivo vengono registrati nel monitoraggio dell'ambiente/telemetria.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-208">The reason and reason detail will be recorded in telemetry/environment monitoring.</span></span>

> [!NOTE]
> <span data-ttu-id="6ec2f-209">Dopo avere eseguito i comandi, viene chiesto di immettere **S** per confermare che si desidera reimpostare il database.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-209">After you run the commands, you will be asked to enter **Y** to confirm that you want to reset the database.</span></span>

#### <a name="restart-services"></a><span data-ttu-id="6ec2f-210">Avviare i servizi</span><span class="sxs-lookup"><span data-stu-id="6ec2f-210">Restart services</span></span>

<span data-ttu-id="6ec2f-211">Utilizzare services.msc per riavviare i servizi interrotti in precedenza:</span><span class="sxs-lookup"><span data-stu-id="6ec2f-211">Use services.msc to restart the services that you stopped earlier:</span></span>

- <span data-ttu-id="6ec2f-212">Servizio di pubblicazione World Wide Web (in tutti i computer AOS)</span><span class="sxs-lookup"><span data-stu-id="6ec2f-212">World wide web publishing service (on all AOS computers)</span></span>
- <span data-ttu-id="6ec2f-213">Servizio di gestione dei batch di Microsoft Dynamics 365 for Finance and Operations (solo in computer AOS non privati)</span><span class="sxs-lookup"><span data-stu-id="6ec2f-213">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="6ec2f-214">Servizio dei processi dello strumento di creazione report di gestione 2012 (solo in computer BI)</span><span class="sxs-lookup"><span data-stu-id="6ec2f-214">Management Reporter 2012 Process Service (on BI computers only)</span></span>

#### <a name="import-report-definitions"></a><span data-ttu-id="6ec2f-215">Importare definizioni di report</span><span class="sxs-lookup"><span data-stu-id="6ec2f-215">Import report definitions</span></span>

<span data-ttu-id="6ec2f-216">Importare i progetti di report da Progettazione report utilizzando il file creato durante l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-216">Import your report designs from Report designer by using the file that was created during the export.</span></span>

1. <span data-ttu-id="6ec2f-217">In Progettazione report, selezionare **Società** &gt; **Gruppi di blocchi predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-217">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="6ec2f-218">Selezionare il gruppo di blocchi predefiniti da esportare, quindi selezionare **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-218">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ec2f-219">Per Finance and Operations, è supportato un solo gruppo di blocchi predefiniti, **Predefinito**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-219">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="6ec2f-220">Selezionare il blocco **Predefinito** e selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-220">Select the **Default** building block, and then select **Import**.</span></span>
4. <span data-ttu-id="6ec2f-221">Selezionare il file che contiene le definizioni di report esportate e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-221">Select the file that contains the exported report definitions, and then select **Open**.</span></span>
5. <span data-ttu-id="6ec2f-222">Nella finestra di dialogo **Importa** selezionare le definizioni di report da importare:</span><span class="sxs-lookup"><span data-stu-id="6ec2f-222">In the **Import** dialog box, select the report definitions to import:</span></span>

    - <span data-ttu-id="6ec2f-223">Per importare tutte le definizioni di report e i blocchi predefiniti associati, selezionare **Seleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-223">To import all the report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="6ec2f-224">Per importare report, righe, colonne, alberi o set di dimensioni specifici, selezionare gli elementi da importare.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-224">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6. <span data-ttu-id="6ec2f-225">Selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-225">Select **Import**.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a><span data-ttu-id="6ec2f-226">Reimpostare il data mart di Creazione report finanziari per Finance and Operations (locale)</span><span class="sxs-lookup"><span data-stu-id="6ec2f-226">Reset the Financial reporting data mart for Finance and Operations (on-premises)</span></span>

1. <span data-ttu-id="6ec2f-227">Chiedere a tutti gli utenti di uscire da Progettazione report e dall'area Creazione report finanziari di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-227">Instruct all users to exit Report designer and the Financial reporting area of Finance and Operations.</span></span>
2. <span data-ttu-id="6ec2f-228">Eseguire lo script seguente sul database dei report finanziari (MRDB).</span><span class="sxs-lookup"><span data-stu-id="6ec2f-228">Run the following script against the Financial reporting database (MRDB).</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. <span data-ttu-id="6ec2f-229">Troncare o eliminare tutti i record dalla tabella FINANCIALREPORTS nel database di Finance and Operations (AXDB).</span><span class="sxs-lookup"><span data-stu-id="6ec2f-229">Truncate or delete all records from the FINANCIALREPORTS table in the Finance and Operations database (AXDB).</span></span>
4. <span data-ttu-id="6ec2f-230">Troncare o eliminare tutti i record dalla tabella FINANCIALREPORTVERSION, se questa tabella è presente nel database di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-230">Truncate or delete all records from the FINANCIALREPORTVERSION table, if this table exists in the Finance and Operations database.</span></span> <span data-ttu-id="6ec2f-231">Se la tabella non è presente nel database di Finance and Operations, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-231">If the table doesn't exist in the Finance and Operations database, skip this step.</span></span>
5. <span data-ttu-id="6ec2f-232">Eseguire lo script **ResetDatamart.sql** sul database dei report finanziari.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-232">Run the **ResetDatamart.sql** script against the Financial reporting database.</span></span> <span data-ttu-id="6ec2f-233">Questo script disattiva l'integrazione del data mart, elimina tutti i dati del data mart e quindi riattiva l'integrazione del data mart.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-233">This script disables the data mart integration, deletes all the data mart data, and then reenables the data mart integration.</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. <span data-ttu-id="6ec2f-234">Dopo la reimpostazione, è possibile verificare manualmente il ricaricamento dei dati eseguendo la query seguente sul database dei report finanziari.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-234">After the reset, you can manually verify the data reload by running the following query against the Financial reporting database.</span></span>

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    <span data-ttu-id="6ec2f-235">Verificare che tutte le righe abbiano un valore **LastRunTime** e che **StateType** sia impostato su **5**.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-235">Confirm that all rows have a **LastRunTime** value, and that **StateType** is set to **5**.</span></span> <span data-ttu-id="6ec2f-236">**StateType** impostato su **5** indica il corretto ricaricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-236">A **StateType** value of **5** indicates that the data was successfully reloaded.</span></span> <span data-ttu-id="6ec2f-237">Il valore **7** indica uno stato di errore.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-237">A value of **7** indicates a faulted state.</span></span> <span data-ttu-id="6ec2f-238">Talvolta, la mappa della gerarchia organizzativa ha questo stato la prima volta che viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-238">Sometimes, the Organization Hierarchy map has this state the first time that it runs.</span></span> <span data-ttu-id="6ec2f-239">Tuttavia, lo stato di errore dovrebbe essere risolto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6ec2f-239">However, the faulted state but should be automatically resolved.</span></span>

