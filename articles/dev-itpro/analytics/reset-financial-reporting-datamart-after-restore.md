---
title: Reimpostare il data mart dei report finanziari dopo il ripristino di un database
description: In questo argomento viene descritto come reimpostare il data mart dei report finanziari dopo il ripristino di un database di Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6e3f78fb2f6528449d2a411225cd0e14ca33443e
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="a5f5d-103">Reimpostare il data mart dei report finanziari dopo il ripristino di un database</span><span class="sxs-lookup"><span data-stu-id="a5f5d-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a5f5d-104">In questo argomento viene descritto come reimpostare il data mart dei report finanziari dopo il ripristino di un database di Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="a5f5d-105">Se si ripristina il database di Finance and Operations da un backup o si copia il database da un altro ambiente, è necessario completare i passaggi in questo argomento per assicurarsi che il data mart dei report finanziari stia utilizzando correttamente il database di Finance and Operations ripristinato.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
> [!Note] 
> <span data-ttu-id="a5f5d-106">I passaggi di questo processo sono supportati per la versione di maggio 2016 di Dynamics 365 for Operation (build di app 7.0.1265.23014 e build di report finanziari 7.0.10000.4) e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="a5f5d-107">Se si dispone di una versione precedente di Finance and Operations, contattare il team del supporto per assistenza.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="a5f5d-108">Esportare definizioni di report</span><span class="sxs-lookup"><span data-stu-id="a5f5d-108">Export report definitions</span></span>
<span data-ttu-id="a5f5d-109">Innanzitutto, esportare le progettazioni di report disponibili in Progettazione report, utilizzando i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="a5f5d-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="a5f5d-110">In Progettazione report, passare a **Società** &gt; **Gruppi di blocchi predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="a5f5d-111">Selezionare il gruppo di blocchi predefiniti da esportare, quindi fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-111">Select the building block group to export, and click **Export**.</span></span> 

    > [!Note] 
    > <span data-ttu-id="a5f5d-112">Per Finance and Operations, è supportato un solo gruppo di blocchi predefiniti, **Predefinito**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="a5f5d-113">Selezionare le definizioni di report da esportare:</span><span class="sxs-lookup"><span data-stu-id="a5f5d-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="a5f5d-114">Per esportare tutte le definizioni di report e i blocchi predefiniti associati, fare clic su **Seleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="a5f5d-115">Per esportare specifici report, righe, colonne, alberi o set di dimensioni, fare clic sulla scheda appropriata e selezionare gli elementi da esportare.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="a5f5d-116">Per selezionare più elementi in una scheda, tenere premuto CTRL. Quando si selezionano i report da esportare, vengono selezionate le righe, le colonne, gli alberi e i set di dimensioni associati.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-116">Press and hold the Ctrl key to select multiple items in a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="a5f5d-117">Fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-117">Click **Export**.</span></span>
5.  <span data-ttu-id="a5f5d-118">Immettere un nome di file e selezionare un percorso protetto in cui si desidera salvare le definizioni di report esportate.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-118">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="a5f5d-119">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-119">Click **Save**.</span></span>

<span data-ttu-id="a5f5d-120">Il file può essere copiato o caricato in un percorso protetto, in modo da consentirne l'importazione in un ambiente diverso in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-120">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="a5f5d-121">Le informazioni sull'utilizzo di un account di archiviazione di Microsoft Azure sono disponibili in [Trasferire dati con l'utilità riga di comando di AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="a5f5d-121">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="a5f5d-122">Microsoft non fornisce un account di archiviazione incluso nel contratto Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-122">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="a5f5d-123">È necessario richiedere un account di archiviazione o impostarne uno da una sottoscrizione Azure separata.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-123">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="a5f5d-124">Tenere presente il comportamento dell'unità D sulle macchine virtuali Azure.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-124">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="a5f5d-125">Non conservare i gruppi di blocchi predefiniti esportati in questa posizione in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-125">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="a5f5d-126">Per ulteriori informazioni sulle unità temporanee, vedere [Informazioni sull'unità temporanea sulle macchine virtuali Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="a5f5d-126">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="a5f5d-127">Interrompere i servizi</span><span class="sxs-lookup"><span data-stu-id="a5f5d-127">Stop services</span></span>
<span data-ttu-id="a5f5d-128">Utilizzare Desktop remoto per collegarsi a tutti i computer nell'ambiente e interrompere i seguenti servizi Windows utilizzando services.msc:</span><span class="sxs-lookup"><span data-stu-id="a5f5d-128">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="a5f5d-129">Servizio di pubblicazione World Wide Web (in tutti i computer AOS)</span><span class="sxs-lookup"><span data-stu-id="a5f5d-129">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="a5f5d-130">Servizio di gestione dei batch di Microsoft Dynamics 365 for Finance and Operations (solo in computer AOS non privati)</span><span class="sxs-lookup"><span data-stu-id="a5f5d-130">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="a5f5d-131">Servizio dei processi dello strumento di creazione report di gestione 2012 (solo in computer BI)</span><span class="sxs-lookup"><span data-stu-id="a5f5d-131">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="a5f5d-132">Questi servizi avranno connessioni aperte al database di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-132">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="a5f5d-133">Reimpostazione</span><span class="sxs-lookup"><span data-stu-id="a5f5d-133">Reset</span></span>
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="a5f5d-134">Individuare e scaricare il pacchetto MinorVersionDataUpgrade.zip più recente</span><span class="sxs-lookup"><span data-stu-id="a5f5d-134">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="a5f5d-135">Individuare il pacchetto MinorVersionDataUpgrade.zip più recente utilizzando le istruzioni disponibili in [Scaricare il pacchetto distribuibile di aggiornamento dei dati più recente](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="a5f5d-135">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="a5f5d-136">Le istruzioni illustrano come individuare e scaricare la versione corretta del pacchetto di aggiornamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-136">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="a5f5d-137">Un aggiornamento non è necessario per scaricare il pacchetto MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-137">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="a5f5d-138">È sufficiente completare i passaggi nella sezione "Scaricare il pacchetto distribuibile di aggiornamento dei dati più recente" senza eseguire le altre operazioni dell'articolo per recuperare una copia del pacchetto MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-138">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="a5f5d-139">Eseguire gli script sul database di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a5f5d-139">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="a5f5d-140">Eseguire i seguenti script sul database di Finance and Operations (non sul database dei report finanziari).</span><span class="sxs-lookup"><span data-stu-id="a5f5d-140">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="a5f5d-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="a5f5d-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="a5f5d-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="a5f5d-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="a5f5d-143">Questi script garantiscono che gli utenti, i ruoli e le impostazioni di rilevamento delle modifiche siano corretti.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-143">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="a5f5d-144">Eseguire il comando PowerShell per reimpostare il database</span><span class="sxs-lookup"><span data-stu-id="a5f5d-144">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="a5f5d-145">Nel computer AOS, eseguire i comandi seguenti in PowerShell come amministratore per reimpostare l'integrazione tra Finance and Operations e i report finanziari:</span><span class="sxs-lookup"><span data-stu-id="a5f5d-145">On the AOS computer, execute the following commands in PowerShell as an Administrator to reset the integration between Finance and Operations and financial reporting:</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> <span data-ttu-id="a5f5d-146">Dopo l'esecuzione dei comandi, Verrà richiesto di immettere "Y" per confermare.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-146">After executing the commands, you will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="a5f5d-147">Descrizione dei parametri:</span><span class="sxs-lookup"><span data-stu-id="a5f5d-147">Explanation of parameters:</span></span>

-   <span data-ttu-id="a5f5d-148">I valori validi per -Reason sono: SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-148">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="a5f5d-149">Il parametro -ReasonDetail è a testo libero.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-149">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="a5f5d-150">Il motivo e il parametro reasonDetail verranno registrati in telemetria/monitoraggio dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-150">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="a5f5d-151">Avviare i servizi</span><span class="sxs-lookup"><span data-stu-id="a5f5d-151">Start services</span></span>
<span data-ttu-id="a5f5d-152">Utilizzare services.msc per riavviare i servizi interrotti in precedenza:</span><span class="sxs-lookup"><span data-stu-id="a5f5d-152">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="a5f5d-153">Servizio di pubblicazione World Wide Web (in tutti i computer AOS)</span><span class="sxs-lookup"><span data-stu-id="a5f5d-153">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="a5f5d-154">Servizio di gestione dei batch di Microsoft Dynamics 365 for Finance and Operations (solo in computer AOS non privati)</span><span class="sxs-lookup"><span data-stu-id="a5f5d-154">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="a5f5d-155">Servizio dei processi dello strumento di creazione report di gestione 2012 (solo in computer BI)</span><span class="sxs-lookup"><span data-stu-id="a5f5d-155">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="a5f5d-156">Importare definizioni di report</span><span class="sxs-lookup"><span data-stu-id="a5f5d-156">Import report definitions</span></span>
<span data-ttu-id="a5f5d-157">Importare le progettazioni di report da Progettazione report, utilizzando il file creato durante l'esportazione:</span><span class="sxs-lookup"><span data-stu-id="a5f5d-157">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="a5f5d-158">In Progettazione report, passare a **Società** &gt; **Gruppi di blocchi predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-158">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="a5f5d-159">Selezionare il gruppo di blocchi predefiniti da esportare, quindi fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-159">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="a5f5d-160">Per Finance and Operations, è supportato un solo gruppo di blocchi predefiniti, **Predefinito**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-160">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="a5f5d-161">Selezionare il blocco predefinito **Predefinito** e fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-161">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="a5f5d-162">Selezionare il file contenente le definizioni di report esportate e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-162">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="a5f5d-163">Nella finestra di dialogo Importa, selezionare le definizioni di report da importare:</span><span class="sxs-lookup"><span data-stu-id="a5f5d-163">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="a5f5d-164">Per importare tutte le definizioni di report e i blocchi predefiniti di supporto, fare clic su **Seleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-164">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="a5f5d-165">Per importare specifici report, righe, colonne, alberi o set di dimensioni, selezionare i report, le righe, le colonne, gli alberi o i set di dimensioni da importare.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-165">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="a5f5d-166">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="a5f5d-166">Click **Import**.</span></span>





