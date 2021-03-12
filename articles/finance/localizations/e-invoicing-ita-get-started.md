---
title: Introduzione al componente aggiuntivo per la fatturazione elettronica per l'Italia
description: Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica per l'Italia in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 08d41244d3ec785127db8f69e37dd522a463c388
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988542"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-italy"></a><span data-ttu-id="8139f-103">Introduzione al componente aggiuntivo per la fatturazione elettronica per l'Italia</span><span class="sxs-lookup"><span data-stu-id="8139f-103">Get started with the Electronic invoicing add-on for Italy</span></span>

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> <span data-ttu-id="8139f-104">Il componente aggiuntivo per la fatturazione elettronica per l'Italia potrebbe attualmente non supportare tutte le funzioni disponibili per le fatture elettroniche in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8139f-104">The Electronic invoicing add-on for Italy might not currently support all the functions that are available for electronic invoices in Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> 

<span data-ttu-id="8139f-105">Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica per il l'Italia.</span><span class="sxs-lookup"><span data-stu-id="8139f-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Italy.</span></span> <span data-ttu-id="8139f-106">Ti guida attraverso i passaggi di configurazione che dipendono dal paese in Regulatory Configuration Services (RCS) e Finance.</span><span class="sxs-lookup"><span data-stu-id="8139f-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="8139f-107">Inoltre, guida l'utente attraverso il processo di invio delle fatture elettroniche generate nel formato **FatturaPA** specifico per l'Italia tramite il servizio e spiega come rivedere i risultati dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="8139f-107">It also guides you through the process for submitting electronic invoices that are generated in the Italy-specific **FatturaPA** format through the service, and it explains how to review the results of processing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8139f-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8139f-108">Prerequisites</span></span>

<span data-ttu-id="8139f-109">Prima di completare i passaggi in questo argomento, è necessario completare i passaggi in [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="8139f-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="8139f-110">Impostazioni RCS</span><span class="sxs-lookup"><span data-stu-id="8139f-110">RCS setup</span></span>

<span data-ttu-id="8139f-111">Durante la configurazione RCS, completerai queste attività:</span><span class="sxs-lookup"><span data-stu-id="8139f-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="8139f-112">Importa la funzionalità di fatturazione elettronica per l'esportazione delle fatture elettroniche dei clienti nel formato **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="8139f-112">Import the e-Invoicing feature for the export of customer electronic invoices in the **FatturaPA** format.</span></span>
2. <span data-ttu-id="8139f-113">Esamina le configurazioni di formato necessarie per generare, inviare e ricevere risposte sulle fatture elettroniche.</span><span class="sxs-lookup"><span data-stu-id="8139f-113">Review the format configurations that are required to generate, submit, and receive responses about electronic invoices.</span></span>
3. <span data-ttu-id="8139f-114">Configura gli eventi che supportano gli scenari di invio delle fatture elettroniche.</span><span class="sxs-lookup"><span data-stu-id="8139f-114">Configure the events that support the electronic invoice submission scenarios.</span></span>
4. <span data-ttu-id="8139f-115">Pubblica la funzionalità per la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="8139f-115">Publish the e-Invoicing feature.</span></span>

> [!NOTE]
> <span data-ttu-id="8139f-116">"La funzionalità per la fatturazione elettronica" è il nome generico della risorsa configurata e pubblicata per utilizzare il server del componente aggiuntivo per la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="8139f-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="8139f-117">In questo caso, l'esportazione delle fatture elettroniche dei clienti rappresenta la funzionalità di fatturazione elettronica che configurerai.</span><span class="sxs-lookup"><span data-stu-id="8139f-117">In this case, the export of customer electronic invoices is the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="8139f-118">Importare la funzionalità per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8139f-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="8139f-119">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="8139f-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="8139f-120">Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="8139f-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="8139f-121">Nella pagina **Funzionalità di fatturazione elettronica**, seleziona **Importa** per importare la funzionalità di fatturazione elettronica dal repository globale.</span><span class="sxs-lookup"><span data-stu-id="8139f-121">On the **e-Invoicing Features** page, select **Import** to import the e-Invoicing feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8139f-122">Se non vedi l'elenco delle funzionalità disponibili, seleziona **Sincronizza**.</span><span class="sxs-lookup"><span data-stu-id="8139f-122">If you don't see the list of available features, select **Synchronize**.</span></span> 

4. <span data-ttu-id="8139f-123">Seleziona la funzionalità **Esportazione fatture elettroniche (IT)**, quindi seleziona **Importa**.</span><span class="sxs-lookup"><span data-stu-id="8139f-123">Select the **e-Invoices Export (IT)** feature, and then select **Import**.</span></span>

![Importazione della funzionalità di esportazione delle fatture elettroniche (IT)](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

<span data-ttu-id="8139f-125">Quando importi la funzionalità **Esportazione fatture elettroniche (IT)** dal repository globale, vengono importate anche tutte le impostazioni descritte nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="8139f-125">When you import the **e-Invoices Export (IT)** feature from the Global repository, all the settings that are described in the next sections are also imported.</span></span>

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a><span data-ttu-id="8139f-126">Creare una nuova versione della funzionalità di esportazioni delle fatture elettroniche (IT)</span><span class="sxs-lookup"><span data-stu-id="8139f-126">Create a new version of the e-Invoices Export (IT) feature</span></span>

1. <span data-ttu-id="8139f-127">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8139f-127">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span> 

    ![Aggiunta di una nuova versione della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    <span data-ttu-id="8139f-129">Successivamente, configurerai i formati di creazione di reporting elettronici (ER) associati alla funzionalità di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="8139f-129">Next, you will configure the Electronic reporting (ER) formats that are associated with the e-Invoicing feature.</span></span>

2. <span data-ttu-id="8139f-130">Nella scheda **Configurazioni**, seleziona **Aggiungi** per gestire le versioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8139f-130">On the **Configurations** tab, select **Add** to manage the configuration versions.</span></span>

    ![Gestione delle versioni di configurazione della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    <span data-ttu-id="8139f-132">In questo passaggio, stai aggiungendo e configurando i formati ER di diversi file utilizzati per esportare le fatture elettroniche italiane.</span><span class="sxs-lookup"><span data-stu-id="8139f-132">In this step, you're adding and configuring the ER formats of different files that are used to export Italian e-invoices.</span></span> <span data-ttu-id="8139f-133">Per le fatture elettroniche FatturaPA italiane, utilizza le seguenti configurazioni standard o le configurazioni personalizzate effettive utilizzate per la fatturazione elettronica:</span><span class="sxs-lookup"><span data-stu-id="8139f-133">For Italian FatturaPA e-invoices, use either the following standard configurations or the actual customized configurations that you use for e-invoicing:</span></span>

    - <span data-ttu-id="8139f-134">Fattura di vendita (IT)</span><span class="sxs-lookup"><span data-stu-id="8139f-134">Sales invoice (IT)</span></span>
    - <span data-ttu-id="8139f-135">Fattura di progetto (IT)</span><span class="sxs-lookup"><span data-stu-id="8139f-135">Project invoice (IT)</span></span>

    <span data-ttu-id="8139f-136">Quando crei una funzionalità di fatturazione elettronica derivata da un'altra funzionalità di fatturazione elettronica, tutti i formati ER vengono ereditati dalla funzionalità originale.</span><span class="sxs-lookup"><span data-stu-id="8139f-136">When you create an e-Invoicing feature that is derived from another e-Invoicing feature, all ER formats are inherited from the original feature.</span></span>

3. <span data-ttu-id="8139f-137">Seleziona una configurazione di file in formato ER specifica.</span><span class="sxs-lookup"><span data-stu-id="8139f-137">Select a specific ER format file configuration.</span></span>
4. <span data-ttu-id="8139f-138">Seleziona **Modifica** o **Visualizza** per aprire la pagina **Progettazione formati**.</span><span class="sxs-lookup"><span data-stu-id="8139f-138">Select **Edit** or **View** to open the **Format designer** page.</span></span>

    ![Apertura della pagina Progettazione formati](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. <span data-ttu-id="8139f-140">Utilizza la pagina **Progettazione formati** per modificare e visualizzare le configurazioni dei file in formato ER.</span><span class="sxs-lookup"><span data-stu-id="8139f-140">Use the **Format designer** page to edit and view the ER format file configurations.</span></span>

    ![Pagina Progettazione formati](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="8139f-142">Gestire le configurazioni della funzionalità di fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8139f-142">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="8139f-143">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Configurazioni**, seleziona **Aggiungi**, **Elimina** o **Modifica** per gestire le configurazioni della funzionalità di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="8139f-143">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Gestione delle configurazioni della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

<span data-ttu-id="8139f-145">In questo passaggio si configurano gli eventi applicabili alle fatture elettroniche, inclusa la generazione dei file di output XML in formato **FatturaPA** e firma digitale (se richiesta).</span><span class="sxs-lookup"><span data-stu-id="8139f-145">In this step, you configure the events that are applicable to electronic invoices, including generation of the XML output files in **FatturaPA** format and digital signing (if required).</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="8139f-146">Configurare l'impostazione della funzionalità Fattura di vendita</span><span class="sxs-lookup"><span data-stu-id="8139f-146">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="8139f-147">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Configurazioni**, nella colonna **Configurazione funzionalità**, seleziona **Fattura di vendita**.</span><span class="sxs-lookup"><span data-stu-id="8139f-147">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="8139f-148">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8139f-148">Select **Edit**.</span></span>
3. <span data-ttu-id="8139f-149">Nella pagina **Configurazione versioni funzionalità**, seleziona la scheda **Azioni** per gestire l'elenco delle azioni.</span><span class="sxs-lookup"><span data-stu-id="8139f-149">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="8139f-150">Le azioni definiscono un elenco di operazioni che devono essere eseguite in ordine sequenziale per completare l'intera esecuzione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8139f-150">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Scheda Azioni](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | <span data-ttu-id="8139f-152">ID azione</span><span class="sxs-lookup"><span data-stu-id="8139f-152">Action ID</span></span> | <span data-ttu-id="8139f-153">Nome azione</span><span class="sxs-lookup"><span data-stu-id="8139f-153">Action name</span></span>        | <span data-ttu-id="8139f-154">Descrizione azione</span><span class="sxs-lookup"><span data-stu-id="8139f-154">Action description</span></span>                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | <span data-ttu-id="8139f-155">1</span><span class="sxs-lookup"><span data-stu-id="8139f-155">1</span></span>         | <span data-ttu-id="8139f-156">Trasforma documento</span><span class="sxs-lookup"><span data-stu-id="8139f-156">Transform document</span></span> | <span data-ttu-id="8139f-157">Crea il file XML della fattura elettronica in formato **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="8139f-157">Create the e-invoice XML file in **FatturaPA** format.</span></span> |
    | <span data-ttu-id="8139f-158">2</span><span class="sxs-lookup"><span data-stu-id="8139f-158">2</span></span>         | <span data-ttu-id="8139f-159">Firma documento</span><span class="sxs-lookup"><span data-stu-id="8139f-159">Sign document</span></span>      | <span data-ttu-id="8139f-160">Applica una firma digitale al file XML.</span><span class="sxs-lookup"><span data-stu-id="8139f-160">Apply a digital signature to the XML file.</span></span>             |

4. <span data-ttu-id="8139f-161">Seleziona la scheda **Regole di applicabilità** per visualizzare e gestire le regole di applicabilità.</span><span class="sxs-lookup"><span data-stu-id="8139f-161">Select the **Applicability rules** tab to view and maintain the applicability rules.</span></span> <span data-ttu-id="8139f-162">Le regole di applicabilità definiscono il contesto in cui verrà eseguita l'azione.</span><span class="sxs-lookup"><span data-stu-id="8139f-162">Applicability rules define the context where the action will be run.</span></span>

    ![Scheda Regole di applicabilità](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. <span data-ttu-id="8139f-164">Seleziona la scheda **Variabili** per visualizzare e gestire le variabili.</span><span class="sxs-lookup"><span data-stu-id="8139f-164">Select the **Variables** tab to view and maintain the variables.</span></span>

    ![Scheda Variabili](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. <span data-ttu-id="8139f-166">Definisci le variabili pubbliche necessarie per eseguire le azioni.</span><span class="sxs-lookup"><span data-stu-id="8139f-166">Define the public variables that are required to run the actions.</span></span>

### <a name="configure-the-project-invoice-feature-setup"></a><span data-ttu-id="8139f-167">Configurare l'impostazione della funzionalità Fattura di progetto</span><span class="sxs-lookup"><span data-stu-id="8139f-167">Configure the Project invoice feature setup</span></span> 

<span data-ttu-id="8139f-168">I passaggi e le impostazioni necessari per configurare la funzionalità **Fattura di progetto** sono molto simili ai passaggi e alle impostazioni per configurare la funzionalità **Fattura di vendita**.</span><span class="sxs-lookup"><span data-stu-id="8139f-168">The steps and settings that are required to configure the **Project invoice** feature setup are very similar to the steps and settings for the **Sales invoice** feature setup.</span></span> <span data-ttu-id="8139f-169">Quando si lavora con le fatture di progetto, vedi le procedure per le fatture di vendita.</span><span class="sxs-lookup"><span data-stu-id="8139f-169">When you work with project invoices, see the procedures for sales invoices.</span></span>

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a><span data-ttu-id="8139f-170">Assegnare la funzionalità di fatturazione elettronica all'ambiente</span><span class="sxs-lookup"><span data-stu-id="8139f-170">Assign the e-Invoicing feature to the environment</span></span>

1. <span data-ttu-id="8139f-171">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Ambienti**, seleziona **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="8139f-171">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="8139f-172">Nel campo **Ambiente**, seleziona l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8139f-172">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="8139f-173">Nel campo **Valido da**, seleziona la data in cui il nuovo ambiente dovrebbe diventare effettivo.</span><span class="sxs-lookup"><span data-stu-id="8139f-173">In the **Effective from** field, select the date when the environment should become effective.</span></span>
4. <span data-ttu-id="8139f-174">Seleziona **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="8139f-174">Select **Enable**.</span></span> 

![Abilitazione dell'ambiente di fatturazione elettronica](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="8139f-176">Pubblicare la funzionalità per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8139f-176">Publish the e-invoicing feature</span></span>

<span data-ttu-id="8139f-177">È possibile pubblicare la funzione di fatturazione elettronica modificando lo stato della versione in **Completato** o **Pubblicato**.</span><span class="sxs-lookup"><span data-stu-id="8139f-177">You can publish the e-Invoicing feature by changing the version status to **Completed** or **Published**.</span></span>

### <a name="change-the-version-status-to-completed"></a><span data-ttu-id="8139f-178">Modificare lo stato della versione in Completato</span><span class="sxs-lookup"><span data-stu-id="8139f-178">Change the version status to Completed</span></span>

1. <span data-ttu-id="8139f-179">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona la versione della funzionalità di fatturazione elettronica con stato **Bozza**.</span><span class="sxs-lookup"><span data-stu-id="8139f-179">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="8139f-180">Selezionare **Cambia stato \> Completa**.</span><span class="sxs-lookup"><span data-stu-id="8139f-180">Select **Change status \> Complete**.</span></span> 

### <a name="change-the-version-status-to-published"></a><span data-ttu-id="8139f-181">Modificare lo stato della versione in Pubblicato</span><span class="sxs-lookup"><span data-stu-id="8139f-181">Change the version status to Published</span></span> 

1. <span data-ttu-id="8139f-182">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona la versione della funzionalità di fatturazione elettronica con stato **Completato**.</span><span class="sxs-lookup"><span data-stu-id="8139f-182">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Completed**.</span></span>
2. <span data-ttu-id="8139f-183">Seleziona **Cambia stato \> Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="8139f-183">Select **Change status \> Publish**.</span></span>

![Modifica dello stato della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance"></a><span data-ttu-id="8139f-185">Configurare l'integrazione del componente aggiuntivo per la fatturazione elettronica in Finance</span><span class="sxs-lookup"><span data-stu-id="8139f-185">Set up the Electronic invoicing add-on integration in Finance</span></span>

<span data-ttu-id="8139f-186">Durante la configurazione di Finance, completerai queste attività:</span><span class="sxs-lookup"><span data-stu-id="8139f-186">During the setup of Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="8139f-187">Importa il modello di dati ER, il mapping del modello di dati ER e le configurazioni del contesto per le fatture elettroniche FatturaPA.</span><span class="sxs-lookup"><span data-stu-id="8139f-187">Import the ER data model, the ER data model mapping, and the context configurations for FatturaPA e-invoices.</span></span>
2. <span data-ttu-id="8139f-188">Configura il certificato necessario per la firma digitale delle fatture elettroniche italiane.</span><span class="sxs-lookup"><span data-stu-id="8139f-188">Configure the certificate that is required to digitally sign Italian e-invoices.</span></span>

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a><span data-ttu-id="8139f-189">Importa il modello di dati ER, il mapping del modello di dati e i formati</span><span class="sxs-lookup"><span data-stu-id="8139f-189">Import the ER data model, data model mapping, and formats</span></span>

1. <span data-ttu-id="8139f-190">Nell'area di lavoro **Creazione di report elettronici**, verificare che il provider di configurazione **Servizio documenti aziendali** sia impostato su **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="8139f-190">In the **Electronic reporting** workspace, verify that the **Business Document Service** configuration provider is set to **Active**.</span></span>
2. <span data-ttu-id="8139f-191">Selezionare **Archivi**.</span><span class="sxs-lookup"><span data-stu-id="8139f-191">Select **Repositories**.</span></span>
3. <span data-ttu-id="8139f-192">Seleziona **Risorsa globale \> Apri**.</span><span class="sxs-lookup"><span data-stu-id="8139f-192">Select **Global resource \> Open**.</span></span>
4. <span data-ttu-id="8139f-193">Importa **Modello di fattura**, **Mapping modello di fattura** e **Modello di contesto della fattura cliente**.</span><span class="sxs-lookup"><span data-stu-id="8139f-193">Import **Invoice model**, **Invoice model mapping**, and **Customer invoice context model**.</span></span>

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a><span data-ttu-id="8139f-194">Attivare la funzionalità per esportare le fatture elettroniche dei clienti per l'Italia</span><span class="sxs-lookup"><span data-stu-id="8139f-194">Turn on the feature for exporting customer electronic invoices for Italy</span></span>

1. <span data-ttu-id="8139f-195">Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="8139f-195">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="8139f-196">Nella scheda **Funzionalità**, seleziona la casella di controllo **Abilitata** nella riga per il riferimento di funzionalità **IT00036**.</span><span class="sxs-lookup"><span data-stu-id="8139f-196">On the **Features** tab, select the **Enabled** check box in the row for feature reference **IT00036**.</span></span>

![Attivazione della funzionalità FatturaPA](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a><span data-ttu-id="8139f-198">Configurare documenti elettronici</span><span class="sxs-lookup"><span data-stu-id="8139f-198">Configure electronic documents</span></span>

1. <span data-ttu-id="8139f-199">Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="8139f-199">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="8139f-200">Nella scheda **Documento elettronico**, seleziona **Aggiungi** e inserisci le tabelle necessarie per generare le fatture elettroniche italiane:</span><span class="sxs-lookup"><span data-stu-id="8139f-200">On the **Electronic document** tab, select **Add**, and enter the tables that are required to generate Italian e-invoices:</span></span>

    - <span data-ttu-id="8139f-201">**Nome tabella:** giornale di registrazione fatture cliente</span><span class="sxs-lookup"><span data-stu-id="8139f-201">**Table name:** Customer invoice journal</span></span>
    - <span data-ttu-id="8139f-202">**Nome tabella:** fattura di progetto</span><span class="sxs-lookup"><span data-stu-id="8139f-202">**Table name:** Project invoice</span></span>

3. <span data-ttu-id="8139f-203">Per ogni tabella, definisci un contesto di documento correlato:</span><span class="sxs-lookup"><span data-stu-id="8139f-203">For each table, define a related document context:</span></span>

    - <span data-ttu-id="8139f-204">Per **Giornale di registrazione fatture cliente**, seleziona **Contesto della fattura cliente**.</span><span class="sxs-lookup"><span data-stu-id="8139f-204">For **Customer invoice journal**, select **Customer invoice context**.</span></span>
    - <span data-ttu-id="8139f-205">Per **Fattura di progetto**, seleziona **Contesto della fattura di progetto**.</span><span class="sxs-lookup"><span data-stu-id="8139f-205">For **Project invoice**, select **Project invoice context**.</span></span>

![Configurazione dei tipi di risposta](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a><span data-ttu-id="8139f-207">Elaborazione fattura elettronica</span><span class="sxs-lookup"><span data-stu-id="8139f-207">Electronic invoice processing</span></span>

<span data-ttu-id="8139f-208">Durante l'elaborazione in Finance, completerai queste attività:</span><span class="sxs-lookup"><span data-stu-id="8139f-208">During processing in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="8139f-209">Generare fatture elettroniche italiane tramite il componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8139f-209">Generate Italian e-invoices through the Electronic invoicing add-on</span></span>
2. <span data-ttu-id="8139f-210">Visualizzare i log di esecuzione e rivedere i risultati dell'elaborazione</span><span class="sxs-lookup"><span data-stu-id="8139f-210">View the execution logs and review the results of processing</span></span>

### <a name="generate-electronic-invoices"></a><span data-ttu-id="8139f-211">Generare fatture elettroniche</span><span class="sxs-lookup"><span data-stu-id="8139f-211">Generate electronic invoices</span></span>

<span data-ttu-id="8139f-212">Dopo aver attivato la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile** e la funzionalità **IT00036**, il vecchio processo di Finance per la generazione di fatture elettroniche italiane non può più essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="8139f-212">After you turn on the **Configurable Electronic invoicing add-on integration** feature and activate the **IT00036** feature, the old Finance process for generating Italian e-invoices can no longer be used.</span></span> <span data-ttu-id="8139f-213">È sostituito da un nuovo processo denominato **Invia documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="8139f-213">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

<span data-ttu-id="8139f-214">È possibile inviare i documenti manualmente, in base alla richiesta di documenti di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="8139f-214">You can submit the documents manually, based on your demand for e-invoice documents.</span></span>

> [!NOTE]
> <span data-ttu-id="8139f-215">Prima di continuare, verifica che la configurazione obbligatoria per le fatture elettroniche italiane sia stata completata.</span><span class="sxs-lookup"><span data-stu-id="8139f-215">Before you continue, verify that the setup that is required for Italian e-invoices was completed.</span></span> <span data-ttu-id="8139f-216">Per ulteriori informazioni, vedi [Fatture elettroniche dei clienti](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span><span class="sxs-lookup"><span data-stu-id="8139f-216">For more information, see [Customer electronic invoices](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span></span> <span data-ttu-id="8139f-217">Tieni presente che alcuni dei passaggi di configurazione descritti in tale argomento potrebbero non essere disponibili a causa dell'attivazione del componente aggiuntivo per la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="8139f-217">Be aware that some of the setup steps that are described in that topic might be unavailable because of Electronic invoicing add-on activation.</span></span>

1. <span data-ttu-id="8139f-218">Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Invia documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="8139f-218">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="8139f-219">Per il primo invio di qualsiasi documento, imposta l'opzione **Invia di nuovo i documenti** su **No**.</span><span class="sxs-lookup"><span data-stu-id="8139f-219">For the first submission of any document, set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="8139f-220">Se devi inviare nuovamente un documento tramite il servizio, imposta questa opzione su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8139f-220">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="8139f-221">Nella Scheda dettaglio **Record da includere**, seleziona **Filtra** per aprire la finestra di dialogo **Richiesta** in cui è possibile creare una query per selezionare i documenti da inviare.</span><span class="sxs-lookup"><span data-stu-id="8139f-221">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Finestra di dialogo Invia documenti elettronici](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a><span data-ttu-id="8139f-223">Query filtri</span><span class="sxs-lookup"><span data-stu-id="8139f-223">Filter query</span></span>

1. <span data-ttu-id="8139f-224">Nella finestra di dialogo **Richiesta**, configura le condizioni di filtro sia per le fatture di vendita che per le fatture di progetto oppure lascia vuote le condizioni per includere tutte le fatture non inviate.</span><span class="sxs-lookup"><span data-stu-id="8139f-224">In the **Inquiry** dialog box, configure the filtering conditions for both sales invoices and project invoices, or leave the conditions blank to include all unsubmitted invoices.</span></span>

    ![Configurazione dei criteri del filtro di invio](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. <span data-ttu-id="8139f-226">Seleziona **OK** per chiudere la finestra di dialogo **Richiesta**.</span><span class="sxs-lookup"><span data-stu-id="8139f-226">Select **OK** to close the **Inquiry** dialog box.</span></span>
3. <span data-ttu-id="8139f-227">Seleziona **OK** per inviare i documenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="8139f-227">Select **OK** submit the selected documents.</span></span>

> <span data-ttu-id="8139f-228">![NOTE] Durante il tuo primo tentativo di inviare un documento tramite il servizio, ti verrà chiesto di confermare la connessione con il componente aggiuntivo per la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="8139f-228">![NOTE] During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="8139f-229">Seleziona **Fai clic qui per connetterti al servizio di invio documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="8139f-229">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

#### <a name="view-submission-logs"></a><span data-ttu-id="8139f-230">Visualizzare i registri di invio</span><span class="sxs-lookup"><span data-stu-id="8139f-230">View submission logs</span></span>

<span data-ttu-id="8139f-231">È possibile visualizzare i registri di invio per tutti i documenti inviati.</span><span class="sxs-lookup"><span data-stu-id="8139f-231">You can view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="8139f-232">Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="8139f-232">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="8139f-233">Nel campo **Tipo di documento**, seleziona **Giornale di registrazione fatture cliente** o **Fattura di progetto** per filtrare i documenti elettronici obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8139f-233">In the **Document type** field, select **Customer invoice journal** or **Project invoice** to filter for the required electronic documents.</span></span>

    ![Selezione di un tipo di documento per visualizzare i registri di invio](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    <span data-ttu-id="8139f-235">Il valore mostrato nella colonna **Stato invio** rappresenta lo stato del processo di invio.</span><span class="sxs-lookup"><span data-stu-id="8139f-235">The value that is shown in the **Submission status** column represents the status of the submission process.</span></span> <span data-ttu-id="8139f-236">Indica se il processo è stato eseguito come configurato e se è necessaria un'azione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="8139f-236">It indicates whether the process ran as configured and whether additional action is required.</span></span>

3. <span data-ttu-id="8139f-237">Nel riquadro azioni seleziona **Richieste \> Dettagli invio** per visualizzare i dettagli dei log di esecuzione dell'invio.</span><span class="sxs-lookup"><span data-stu-id="8139f-237">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Visualizzazione dei dettagli del registro di invio](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. <span data-ttu-id="8139f-239">Nella Scheda dettaglio **Azioni di elaborazione** puoi visualizzare il registro di esecuzione delle azioni configurate nella versione della funzionalità configurata in RCS.</span><span class="sxs-lookup"><span data-stu-id="8139f-239">On the **Processing actions** FastTab, you can view the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="8139f-240">La colonna **Stato** mostra se l'azione è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="8139f-240">The **Status** column shows whether the action was successfully run.</span></span>
5. <span data-ttu-id="8139f-241">Nella Scheda dettaglio **File di azione** puoi visualizzare i file intermedi che sono stati generati durante l'esecuzione delle azioni.</span><span class="sxs-lookup"><span data-stu-id="8139f-241">On the **Action files** FastTab, you can view the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="8139f-242">Puoi selezionare **Visualizza** per scaricare il file XML di output in formato **FatturaPA** e visualizzarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="8139f-242">You can select **View** to download the output XML file in **FatturaPA** format and view its content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8139f-243">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8139f-243">Related topics</span></span>

- [<span data-ttu-id="8139f-244">Panoramica del componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8139f-244">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="8139f-245">Introduzione al componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8139f-245">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="8139f-246">Configurare il componente aggiuntivo per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="8139f-246">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)
