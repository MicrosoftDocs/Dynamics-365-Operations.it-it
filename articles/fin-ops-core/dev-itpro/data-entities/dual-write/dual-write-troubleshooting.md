---
title: Risoluzione dei problemi generali
description: In questo argomento vengono fornite informazioni sulla risoluzione dei problemi generali di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.
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
ms.openlocfilehash: f7ee0b5aa4e72614205e129acd986376b33efc70
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172693"
---
# <a name="general-troubleshooting"></a><span data-ttu-id="30371-103">Risoluzione dei problemi generali</span><span class="sxs-lookup"><span data-stu-id="30371-103">General troubleshooting</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="30371-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi generali di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="30371-104">This topic provides general troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30371-105">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="30371-105">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="30371-106">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="30371-106">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a><span data-ttu-id="30371-107">Quando si tenta di installare il pacchetto di doppia scrittura utilizzando lo strumento di distribuzione pacchetti, non vengono visualizzate le soluzioni disponibili</span><span class="sxs-lookup"><span data-stu-id="30371-107">When you try to install the dual-write package by using the package deployer tool, no available solutions are shown</span></span>

<span data-ttu-id="30371-108">Alcune versioni dello strumento di distribuzione dei pacchetti non sono compatibili con il pacchetto della soluzione di doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="30371-108">Some versions of the package deployer tool are incompatible with the dual-write solution package.</span></span> <span data-ttu-id="30371-109">Per installare correttamente il pacchetto, assicurarsi di utilizzare la [versione 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) o successive dello strumento di distribuzione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="30371-109">To successfully install the package, be sure to use [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) or later of the package deployer tool.</span></span>

<span data-ttu-id="30371-110">Dopo aver installato lo strumento di distribuzione pacchetti, installare il pacchetto della soluzione seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="30371-110">After you install the package deployer tool, install the solution package by following these steps.</span></span>

1. <span data-ttu-id="30371-111">Scaricare l'ultimo file del pacchetto della soluzione da Yammer.com.</span><span class="sxs-lookup"><span data-stu-id="30371-111">Download the latest solution package file from Yammer.com.</span></span> <span data-ttu-id="30371-112">Dopo aver scaricato il file zip del pacchetto, fare clic con il tasto destro del mouse e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="30371-112">After the package zip file is downloaded, right-click it, and select **Properties**.</span></span> <span data-ttu-id="30371-113">Selezionare la casella di controllo **Sblocca**, quindi selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="30371-113">Select the **Unblock** check box, and then select **Apply**.</span></span> <span data-ttu-id="30371-114">Se la casella di controllo **Sblocca** non è visibile, il file zip è già sbloccato ed è possibile saltare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="30371-114">If you don't see the **Unblock** check box, the zip file is already unblocked, and you can skip this step.</span></span>

    ![Finestra di dialogo Proprietà](media/unblock_option.png)

2. <span data-ttu-id="30371-116">Estrarre il file zip del pacchetto e copiare tutti i file nella cartella **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438**.</span><span class="sxs-lookup"><span data-stu-id="30371-116">Extract the package zip file, and copy all the files in the **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** folder.</span></span>

    ![Contenuto della cartella Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438](media/extract_package.png)

3. <span data-ttu-id="30371-118">Incollare tutti i file copiati nella cartella **Strumenti** dello strumento di distribuzione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="30371-118">Paste all the copied files into the **Tools** folder of the package deployer tool.</span></span> 
4. <span data-ttu-id="30371-119">Eseguire **PackageDeployer.exe** per selezionare l'ambiente Common Data Service e installare le soluzioni.</span><span class="sxs-lookup"><span data-stu-id="30371-119">Run **PackageDeployer.exe** to select the Common Data Service environment and install the solutions.</span></span>

    ![Contenuto della cartella Strumenti](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details"></a><span data-ttu-id="30371-121">Abilitare e visualizzare il log di traccia del plug-in Common Data Service per visualizzare i dettagli dell'errore</span><span class="sxs-lookup"><span data-stu-id="30371-121">Enable and view the plug-in trace log in Common Data Service to view error details</span></span>

<span data-ttu-id="30371-122">**Ruolo richiesto per attivare il log di traccia e visualizzare gli errori:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="30371-122">**Required role to turn on the trace log and view errors:** System admin</span></span>

<span data-ttu-id="30371-123">Per attivare il log di traccia, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="30371-123">To turn on the trace log, follow these steps.</span></span>

1. <span data-ttu-id="30371-124">Accedere all'app Finance and Operations, aprire la pagina **Impostazioni** e quindi sotto **Sistema**, selezionare **Amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="30371-124">Sign in to the Finance and Operations app, open the **Settings** page, and then, under **System**, select **Administration**.</span></span>
2. <span data-ttu-id="30371-125">Nella pagina **Amministrazione** selezionare **Impostazioni di sistema**.</span><span class="sxs-lookup"><span data-stu-id="30371-125">On the **Administration** page, select **System Settings**.</span></span>
3. <span data-ttu-id="30371-126">Nella scheda **Personalizzazione**, nel campo **Analisi attività plug-in e flusso di lavoro personalizzato**, selezionare **Tutto** per abilitare il log di traccia del plug-in.</span><span class="sxs-lookup"><span data-stu-id="30371-126">On the **Customization** tab, in the **Plug-in and custom workflow activity tracing** field, select **All** to enable the plug-in trace log.</span></span> <span data-ttu-id="30371-127">Se si desidera registrare i log di traccia solo quando si verificano eccezioni, è possibile selezionare **Eccezione**.</span><span class="sxs-lookup"><span data-stu-id="30371-127">If you want to log trace logs only when exceptions occur, you can select **Exception** instead.</span></span>


<span data-ttu-id="30371-128">Per visualizzare il log di traccia, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="30371-128">To view the trace log, follow these steps.</span></span>

1. <span data-ttu-id="30371-129">Accedere all'app Finance and Operations, aprire la pagina **Impostazioni** e quindi sotto **Personalizzazione**, selezionare **Registro di traccia plug-in**.</span><span class="sxs-lookup"><span data-stu-id="30371-129">Sign in to the Finance and Operations app, open the **Settings** page, and then, under **Customization**, select **Plug-in Trace Log**.</span></span>
2. <span data-ttu-id="30371-130">Trovare i log di traccia dove il campo **Nome tipo** è impostato su **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.</span><span class="sxs-lookup"><span data-stu-id="30371-130">Find the trace logs where the **Type Name** field is set to **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.</span></span>
3. <span data-ttu-id="30371-131">Fare doppio clic su un elemento per visualizzare il registro completo, quindi nella scheda dettaglio **Esecuzione**, esaminare il testo **Blocco messaggio**.</span><span class="sxs-lookup"><span data-stu-id="30371-131">Double-click an item to view the full log, and then, on the **Execution** FastTab, review the **Message Block** text.</span></span>

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a><span data-ttu-id="30371-132">Abilitare la modalità debug per risolvere i problemi di sincronizzazione in tempo reale nelle app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="30371-132">Enable debug mode to troubleshoot live synchronization issues in Finance and Operations apps</span></span>

<span data-ttu-id="30371-133">**Ruolo richiesto per visualizzare gli errori:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="30371-133">**Required role to view the errors:** System admin</span></span>

<span data-ttu-id="30371-134">Gli errori di doppia scrittura che hanno origine in Common Data Service possono apparire nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="30371-134">Dual-write errors that originate in Common Data Service can appear in the Finance and Operations app.</span></span> <span data-ttu-id="30371-135">In alcuni casi, il testo completo del messaggio di errore non è disponibile perché il messaggio è troppo lungo o contiene informazioni di identificazione personale (PII).</span><span class="sxs-lookup"><span data-stu-id="30371-135">In some cases, the full text of the error message isn't available because the message is too long or contains personally identifying information (PII).</span></span> <span data-ttu-id="30371-136">È possibile attivare la registrazione dettagliata degli errori seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="30371-136">You can turn on verbose logging for errors by following these steps.</span></span>

1. <span data-ttu-id="30371-137">Tutte le configurazioni del progetto nelle app Finance and Operations hanno una proprietà **IsDebugMode** nell'entità **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="30371-137">All project configurations in Finance and Operations apps have an **IsDebugMode** property in the **DualWriteProjectConfiguration** entity.</span></span> <span data-ttu-id="30371-138">Aprire l'entità **DualWriteProjectConfiguration** utilizzando il componente aggiuntivo di Excel.</span><span class="sxs-lookup"><span data-stu-id="30371-138">Open the **DualWriteProjectConfiguration** entity by using the Excel add-in.</span></span>

    > [!TIP]
    > <span data-ttu-id="30371-139">Un modo semplice per aprire l'entità è attivare la modalità **Progettazione** nel componente aggiuntivo di Excel e quindi aggiungere **DualWriteProjectConfigurationEntity** al foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="30371-139">An easy way to open the entity is to turn on **Design** mode in the Excel add-in and then add **DualWriteProjectConfigurationEntity** to the worksheet.</span></span> <span data-ttu-id="30371-140">Per ulteriori informazioni, vedere [Aprire i dati dell'entità in Excel e aggiornarli tramite il componente aggiuntivo di Excel](../../office-integration/use-excel-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="30371-140">For more information, see [Open entity data in Excel and update it by using the Excel add-in](../../office-integration/use-excel-add-in.md).</span></span>

2. <span data-ttu-id="30371-141">Impostare la proprietà **IsDebugMode** su **Sì** per il progetto.</span><span class="sxs-lookup"><span data-stu-id="30371-141">Set the **IsDebugMode** property to **Yes** for the project.</span></span>
3. <span data-ttu-id="30371-142">Esegui lo scenario che genera errori.</span><span class="sxs-lookup"><span data-stu-id="30371-142">Run the scenario that is generating errors.</span></span>
4. <span data-ttu-id="30371-143">I log dettagliati sono disponibili nella tabella DualWriteErrorLog.</span><span class="sxs-lookup"><span data-stu-id="30371-143">The verbose logs are available in the DualWriteErrorLog table.</span></span> <span data-ttu-id="30371-144">Per cercare i dati nel browser delle tabelle, utilizzare il seguente URL (sostituire **XXX** come appropriato):</span><span class="sxs-lookup"><span data-stu-id="30371-144">To look up data in the table browser, use the following URL (replace **XXX** as appropriate):</span></span>

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=>DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a><span data-ttu-id="30371-145">Controllare gli errori di sincronizzazione sulla macchina virtuale per l'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="30371-145">Check synchronization errors on the virtual machine for the Finance and Operations app</span></span>

<span data-ttu-id="30371-146">**Ruolo richiesto per visualizzare gli errori:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="30371-146">**Required role to view the errors:** System admin</span></span>

1. <span data-ttu-id="30371-147">Accedere a Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="30371-147">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="30371-148">Aprire il progetto LCS per cui si è scelto di eseguire il test di doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="30371-148">Open the LCS project that you chose to do the dual-write testing for.</span></span>
3. <span data-ttu-id="30371-149">Selezionare il riquadro **Distribuzione ambienti ospitati nel cloud**.</span><span class="sxs-lookup"><span data-stu-id="30371-149">Select the **Cloud-hosted environments** tile.</span></span>
4. <span data-ttu-id="30371-150">Usare Remote Desktop per accedere alla macchina virtuale (VM) per l'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="30371-150">Use Remote Desktop to sign in to the virtual machine (VM) for the Finance and Operations app.</span></span> <span data-ttu-id="30371-151">Utilizzare l'account locale mostrato in LCS.</span><span class="sxs-lookup"><span data-stu-id="30371-151">Use the local account that is shown in LCS.</span></span>
5. <span data-ttu-id="30371-152">Aprire il visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="30371-152">Open Event viewer.</span></span>
6. <span data-ttu-id="30371-153">Selezionare **Registri applicazioni e servizi \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operativo**.</span><span class="sxs-lookup"><span data-stu-id="30371-153">Select **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span>
7. <span data-ttu-id="30371-154">Rivedere l'elenco degli errori recenti.</span><span class="sxs-lookup"><span data-stu-id="30371-154">Review the list of recent errors.</span></span>

## <a name="unlink-and-link-another-common-data-service-environment-from-a-finance-and-operations-app"></a><span data-ttu-id="30371-155">Scollegare e collegare un altro ambiente Common Data Service da un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="30371-155">Unlink and link another Common Data Service environment from a Finance and Operations app</span></span>

<span data-ttu-id="30371-156">**Credenziali richieste per scollegare l'ambiente:** amministratore del tenant Azure AD</span><span class="sxs-lookup"><span data-stu-id="30371-156">**Required credentials to unlink the environment:** Azure AD tenant admin</span></span>

1. <span data-ttu-id="30371-157">Accedere all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="30371-157">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="30371-158">Andare a **Aree di lavoro \>Gestione dei dati** e selezionare il riquadro **Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="30371-158">Go to **Workspaces \> Data management**, and select the **Dual Write** tile.</span></span>
3. <span data-ttu-id="30371-159">Selezionare tutti i mapping in esecuzione e scegliere **Interrompi**.</span><span class="sxs-lookup"><span data-stu-id="30371-159">Select all running mappings, and then select **Stop**.</span></span>
4. <span data-ttu-id="30371-160">Selezionare **Scollega ambiente**.</span><span class="sxs-lookup"><span data-stu-id="30371-160">Select **Unlink environment**.</span></span>
5. <span data-ttu-id="30371-161">Selezionare **Sì** per confermare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="30371-161">Select **Yes** to confirm the operation.</span></span>

<span data-ttu-id="30371-162">Ora è possibile collegare un nuovo ambiente.</span><span class="sxs-lookup"><span data-stu-id="30371-162">You can now link a new environment.</span></span>
