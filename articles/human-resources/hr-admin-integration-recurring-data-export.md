---
title: Creare un'app di esportazione dati ricorrente
description: In questo articolo viene illustrato come creare un'app di logica Microsoft Azure che esporta dati da Microsoft Dynamics 365 Human Resources in modo ricorrente.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a4a963bcfe5932f5642b43751ccd96c472fec0d9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055006"
---
# <a name="create-a-recurring-data-export-app"></a><span data-ttu-id="8dc89-103">Creare un'app di esportazione dati ricorrente</span><span class="sxs-lookup"><span data-stu-id="8dc89-103">Create a recurring data export app</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8dc89-104">In questo articolo viene illustrato come creare un'app di logica Microsoft Azure che esporta dati da Microsoft Dynamics 365 Human Resources in modo ricorrente.</span><span class="sxs-lookup"><span data-stu-id="8dc89-104">This article shows how to create a Microsoft Azure logic app that exports data from Microsoft Dynamics 365 Human Resources on a recurring schedule.</span></span> <span data-ttu-id="8dc89-105">Il tutorial utilizza l'API REST del pacchetto DMF di Human Resources per esportare i dati.</span><span class="sxs-lookup"><span data-stu-id="8dc89-105">The tutorial takes advantage of Human Resources' DMF package REST application programming interface (API) to export the data.</span></span> <span data-ttu-id="8dc89-106">Dopo che i dati sono stati esportati, l'app di logica salva il pacchetto dati esportato in una cartella di Microsoft OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="8dc89-106">After the data has been exported, the logic app saves the exported data package to a Microsoft OneDrive for Business folder.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="8dc89-107">Scenario aziendale</span><span class="sxs-lookup"><span data-stu-id="8dc89-107">Business scenario</span></span>

<span data-ttu-id="8dc89-108">In uno scenario aziendale tipico per le integrazioni di Microsoft Dynamics 365, i dati devono essere esportati in un sistema downstream secondo una programmazione ricorrente.</span><span class="sxs-lookup"><span data-stu-id="8dc89-108">In one typical business scenario for Microsoft Dynamics 365 integrations, data must be exported to a downstream system on a recurring schedule.</span></span> <span data-ttu-id="8dc89-109">Questa esercitazione mostra come esportare tutti i record dei lavoratori da Microsoft Dynamics 365 Human Resources e salva l'elenco dei lavoratori in una cartella di OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="8dc89-109">This tutorial shows how to export all worker records from Microsoft Dynamics 365 Human Resources and save the list of workers in a OneDrive for Business folder.</span></span>

> [!TIP]
> <span data-ttu-id="8dc89-110">I dati specifici esportati in questa esercitazione e la destinazione dei dati esportati sono solo esempi.</span><span class="sxs-lookup"><span data-stu-id="8dc89-110">The specific data that is exported in this tutorial and the destination of the exported data are only examples.</span></span> <span data-ttu-id="8dc89-111">È possibile modificarli facilmente in base alle proprie esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="8dc89-111">You can easily change them to meet your business needs.</span></span>

## <a name="technologies-used"></a><span data-ttu-id="8dc89-112">Tecnologie utilizzate</span><span class="sxs-lookup"><span data-stu-id="8dc89-112">Technologies used</span></span>

<span data-ttu-id="8dc89-113">Questo tutorial utilizza le seguenti tecnologie:</span><span class="sxs-lookup"><span data-stu-id="8dc89-113">This tutorial uses the following technologies:</span></span>

- <span data-ttu-id="8dc89-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**- L'origine dati master per i lavoratori che verranno esportati.</span><span class="sxs-lookup"><span data-stu-id="8dc89-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – The master data source for workers that will be exported.</span></span>
- <span data-ttu-id="8dc89-115">**[App per la logica di Azure](https://azure.microsoft.com/services/logic-apps/)** - La tecnologia che fornisce l'orchestrazione e la pianificazione dell'esportazione ricorrente.</span><span class="sxs-lookup"><span data-stu-id="8dc89-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – The technology that provides orchestration and scheduling of the recurring export.</span></span>

    - <span data-ttu-id="8dc89-116">**[Connettori](/azure/connectors/apis-list)** - La tecnologia utilizzata per connettere l'app per la logica agli endpoint richiesti.</span><span class="sxs-lookup"><span data-stu-id="8dc89-116">**[Connectors](/azure/connectors/apis-list)** – The technology that is used to connect the logic app to the required endpoints.</span></span>

        - <span data-ttu-id="8dc89-117">Connettore [HTTP con Azure AD](/connectors/webcontents/)</span><span class="sxs-lookup"><span data-stu-id="8dc89-117">[HTTP with Azure AD](/connectors/webcontents/) connector</span></span>
        - <span data-ttu-id="8dc89-118">Connettore [OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness)</span><span class="sxs-lookup"><span data-stu-id="8dc89-118">[OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness) connector</span></span>

- <span data-ttu-id="8dc89-119">**[API REST del pacchetto DMF](../fin-ops-core/dev-itpro/data-entities/data-management-api.md)** - La tecnologia utilizzata per attivare l'esportazione e monitorarne l'avanzamento.</span><span class="sxs-lookup"><span data-stu-id="8dc89-119">**[DMF package REST API](../fin-ops-core/dev-itpro/data-entities/data-management-api.md)** – The technology that is used to trigger the export and monitor its progress.</span></span>
- <span data-ttu-id="8dc89-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** - La destinazione per i lavoratori esportati.</span><span class="sxs-lookup"><span data-stu-id="8dc89-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** – The destination for the exported workers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8dc89-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8dc89-121">Prerequisites</span></span>

<span data-ttu-id="8dc89-122">Prima di iniziare questa esercitazione, è necessario disporre dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="8dc89-122">Before you begin the exercise in this tutorial, you must have the following items:</span></span>

- <span data-ttu-id="8dc89-123">Un ambiente di Human Resources con autorizzazioni a livello di amministratore nell'ambiente</span><span class="sxs-lookup"><span data-stu-id="8dc89-123">A Human Resources environment that has admin-level permissions in the environment</span></span>
- <span data-ttu-id="8dc89-124">Una [sottoscrizione di Azure ](https://azure.microsoft.com/free/) per ospitare l'app per la logica</span><span class="sxs-lookup"><span data-stu-id="8dc89-124">An [Azure subscription](https://azure.microsoft.com/free/) to host the logic app</span></span>

## <a name="the-exercise"></a><span data-ttu-id="8dc89-125">Esercitazione</span><span class="sxs-lookup"><span data-stu-id="8dc89-125">The exercise</span></span>

<span data-ttu-id="8dc89-126">Alla fine di questa esercitazione, si disporrà di un'app per la logica connessa all'ambiente di Human Resources e all'account OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="8dc89-126">At the end of this exercise, you will have a logic app that is connected to your Human Resources environment and your OneDrive for Business account.</span></span> <span data-ttu-id="8dc89-127">L'app per la logica esporterà un pacchetto di dati da Human Resources, attenderà il completamento dell'esportazione, scaricherà il pacchetto di dati esportato e salverà il pacchetto di dati nella cartella di OneDrive for Business specificata.</span><span class="sxs-lookup"><span data-stu-id="8dc89-127">The logic app will export a data package from Human Resources, wait for the export to be completed, download the exported data package, and save the data package in the OneDrive for Business folder that you specified.</span></span>

<span data-ttu-id="8dc89-128">L'app per la logica completata sarà simile alla seguente illustrazione.</span><span class="sxs-lookup"><span data-stu-id="8dc89-128">The completed logic app will resemble the following illustration.</span></span>

![Panoramica dell'app per la logica](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a><span data-ttu-id="8dc89-130">Passaggio 1: creare un progetto di esportazione di dati in Human Resources</span><span class="sxs-lookup"><span data-stu-id="8dc89-130">Step 1: Create a data export project in Human Resources</span></span>

<span data-ttu-id="8dc89-131">In Human Resources, creare un progetto di esportazione di dati che esporta i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="8dc89-131">In Human Resources, create a data export project that exports workers.</span></span> <span data-ttu-id="8dc89-132">Assegnare al progetto il nome **Esportazione lavoratori** e assicurarsi che l'opzione **Genera pacchetto dati** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8dc89-132">Name the project **Export Workers**, and make sure that the **Generate data package** option is set to **Yes**.</span></span> <span data-ttu-id="8dc89-133">Aggiungere una singola entità (**Lavoratore**) al progetto e selezionare il formato in cui esportare</span><span class="sxs-lookup"><span data-stu-id="8dc89-133">Add a single entity (**Worker**) to the project, and select the format to export in.</span></span> <span data-ttu-id="8dc89-134">(in questa esercitazione viene utilizzato il formato Microsoft Excel).</span><span class="sxs-lookup"><span data-stu-id="8dc89-134">(Microsoft Excel format is used in this tutorial.)</span></span>

![Progetto dati Esportazione lavoratori](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> <span data-ttu-id="8dc89-136">Prendere nota del nome del progetto di esportazione di dati.</span><span class="sxs-lookup"><span data-stu-id="8dc89-136">Remember the name of the data export project.</span></span> <span data-ttu-id="8dc89-137">Dovrà essere utilizzato quando si crea l'app per la logica nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8dc89-137">You will need it when you create the logic app in the next step.</span></span>

### <a name="step-2-create-the-logic-app"></a><span data-ttu-id="8dc89-138">Passaggio 2: creare l'app per la logica</span><span class="sxs-lookup"><span data-stu-id="8dc89-138">Step 2: Create the logic app</span></span>

<span data-ttu-id="8dc89-139">La maggior parte dell'esercitazione prevede la creazione dell'app per la logica.</span><span class="sxs-lookup"><span data-stu-id="8dc89-139">The bulk of the exercise involves creating the logic app.</span></span>

1. <span data-ttu-id="8dc89-140">Nel portale di Azure, creare un'app per la logica.</span><span class="sxs-lookup"><span data-stu-id="8dc89-140">In the Azure portal, create a logic app.</span></span>

    ![Pagina di creazione dell'app per la logica](media/integration-logic-app-creation-1.png)

2. <span data-ttu-id="8dc89-142">Nella finestra di progettazione di app per la logica, iniziare con un'app per la logica vuota.</span><span class="sxs-lookup"><span data-stu-id="8dc89-142">In the Logic Apps Designer, start with a blank logic app.</span></span>
3. <span data-ttu-id="8dc89-143">Aggiungere un [trigger di programmazione della ricorrenza ](/azure/connectors/connectors-native-recurrence) per eseguire l'app per la logica ogni 24 ore (o in base alla programmazione scelta).</span><span class="sxs-lookup"><span data-stu-id="8dc89-143">Add a [Recurrence Schedule trigger](/azure/connectors/connectors-native-recurrence) to run the logic app every 24 hours (or according to a schedule of your choice).</span></span>

    ![Finestra di dialogo Ricorrenza](media/integration-logic-app-recurrence-step.png)

4. <span data-ttu-id="8dc89-145">Chiamare l'API REST DMF [ExportToPackage ](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#exporttopackage) per pianificare l'esportazione del pacchetto di dati.</span><span class="sxs-lookup"><span data-stu-id="8dc89-145">Call the [ExportToPackage](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API to schedule the export of your data package.</span></span>

    1. <span data-ttu-id="8dc89-146">Utilizzare l'azione **Richiama richiesta HTTP** dal connettore HTTP con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8dc89-146">Use the **Invoke an HTTP request** action from the HTTP with Azure AD connector.</span></span>

        - <span data-ttu-id="8dc89-147">**URL risorsa di base:** l'URL dell'ambiente di Human Resources (non includere l'informazione path/namespace).</span><span class="sxs-lookup"><span data-stu-id="8dc89-147">**Base Resource URL:** The URL of your Human Resources environment (Don't include path/namespace information.)</span></span>
        - <span data-ttu-id="8dc89-148">**URI risorsa Azure AD:** `http://hr.talent.dynamics.com`</span><span class="sxs-lookup"><span data-stu-id="8dc89-148">**Azure AD Resource URI:** `http://hr.talent.dynamics.com`</span></span>

        > [!NOTE]
        > <span data-ttu-id="8dc89-149">Il servizio Human Resources non fornisce ancora un connettore che espone tutte le API che compongono l'API REST del pacchetto DMF, come **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="8dc89-149">The Human Resources service doesn't yet provide a connector that exposes all the APIs that make up the DMF package REST API, such as **ExportToPackage**.</span></span> <span data-ttu-id="8dc89-150">È invece necessario chiamare le API utilizzando le richieste HTTPS non elaborate tramite il connettore HTTP con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8dc89-150">Instead, you must call the APIs by using raw HTTPS requests through the HTTP with Azure AD connector.</span></span> <span data-ttu-id="8dc89-151">Questo connettore utilizza Azure Active Directory (Azure AD) per l'autenticazione e l'autorizzazione a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8dc89-151">This connector uses Azure Active Directory (Azure AD) for authentication and authorization to Human Resources.</span></span>

        ![Connettore HTTP con Azure AD](media/integration-logic-app-http-aad-connector-step.png)

    2. <span data-ttu-id="8dc89-153">Accedere all'ambiente di Human Resources tramite il connettore HTTP con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8dc89-153">Sign in to your Human Resources environment through the HTTP with Azure AD connector.</span></span>
    3. <span data-ttu-id="8dc89-154">Impostare una richiesta **POST** HTTP per chiamare l'API REST DMF **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="8dc89-154">Set up an HTTP **POST** request to call the **ExportToPackage** DMF REST API.</span></span>

        - <span data-ttu-id="8dc89-155">**Metodo:** POST</span><span class="sxs-lookup"><span data-stu-id="8dc89-155">**Method:** POST</span></span>
        - <span data-ttu-id="8dc89-156">**URL della richiesta:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span><span class="sxs-lookup"><span data-stu-id="8dc89-156">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span></span>
        - <span data-ttu-id="8dc89-157">**Corpo della richiesta:**</span><span class="sxs-lookup"><span data-stu-id="8dc89-157">**Body of the request:**</span></span>

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Azione Richiama richiesta HTTP](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > <span data-ttu-id="8dc89-159">È possibile che si intenda rinominare ogni passaggio di modo che risulti più descrittivo del nome predefinito, **Richiamare una richiesta HTTP**.</span><span class="sxs-lookup"><span data-stu-id="8dc89-159">You might want to rename each step so that it's more meaningful than the default name, **Invoke an HTTP request**.</span></span> <span data-ttu-id="8dc89-160">Ad esempio, è possibile rinominare questo passaggio **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="8dc89-160">For example, you can rename this step **ExportToPackage**.</span></span>

5. <span data-ttu-id="8dc89-161">[Inizializzare una variabile](/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) per memorizzare lo stato di esecuzione della richiesta **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="8dc89-161">[Initialize a variable](/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) to store the execution status of the **ExportToPackage** request.</span></span>

    ![Azione Inizializza variabile](media/integration-logic-app-initialize-variable-step.png)

6. <span data-ttu-id="8dc89-163">Attendere fino a quando lo stato di esecuzione dell'esportazione dei dati è **Operazione completata**.</span><span class="sxs-lookup"><span data-stu-id="8dc89-163">Wait until the execution status of the data export is **Succeeded**.</span></span>

    1. <span data-ttu-id="8dc89-164">Aggiungere un [ciclo Until](/azure/logic-apps/logic-apps-control-flow-loops#until-loop) che si ripete fino a che il valore della variabile **ExecutionStatus** non è **Operazione completata**.</span><span class="sxs-lookup"><span data-stu-id="8dc89-164">Add an [Until loop](/azure/logic-apps/logic-apps-control-flow-loops#until-loop) that repeats until the value of the **ExecutionStatus** variable is **Succeeded**.</span></span>
    2. <span data-ttu-id="8dc89-165">Aggiungere un'azione **Ritarda** che attende cinque secondi prima di eseguire il polling dello stato di esecuzione corrente dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="8dc89-165">Add a **Delay** action that waits five seconds before it polls for the current execution status of the export.</span></span>

        ![Contenitore del ciclo Until](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > <span data-ttu-id="8dc89-167">Impostare il valore del limite su **15** per attendere un massimo di 75 secondi (15 iterazioni × 5 secondi) per il completamento dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="8dc89-167">Set the limit count to **15** to wait a maximum of 75 seconds (15 iterations × 5 seconds) for the export to be completed.</span></span> <span data-ttu-id="8dc89-168">Se l'esportazione richiede più tempo, regolare il valore del limite in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8dc89-168">If your export takes more time, adjust the limit count as appropriate.</span></span>        

    3. <span data-ttu-id="8dc89-169">Aggiungere un'azione **Richiama richiesta HTTP** per chiamare l'API REST DMF [GetExecutionSummaryStatus](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) e impostare la variabile **ExecutionStatus** sul risultato della risposta **GetExecutionSummaryStatus**.</span><span class="sxs-lookup"><span data-stu-id="8dc89-169">Add an **Invoke HTTP request** action to call the [GetExecutionSummaryStatus](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API, and set the **ExecutionStatus** variable to the result of the **GetExecutionSummaryStatus** response.</span></span>

        > <span data-ttu-id="8dc89-170">Questo esempio non esegue il controllo degli errori.</span><span class="sxs-lookup"><span data-stu-id="8dc89-170">This sample doesn't do error checking.</span></span> <span data-ttu-id="8dc89-171">L'API **GetExecutionSummaryStatus** può restituire stati terminali non riusciti (ovvero stati diversi da **Operazione completata**).</span><span class="sxs-lookup"><span data-stu-id="8dc89-171">The **GetExecutionSummaryStatus** API can return non-successful terminal states (that is, states other than **Succeeded**).</span></span> <span data-ttu-id="8dc89-172">Per ulteriori informazioni, vedere la [documentazione API](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span><span class="sxs-lookup"><span data-stu-id="8dc89-172">For more information, see the [API documentation](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span></span>

        - <span data-ttu-id="8dc89-173">**Metodo:** POST</span><span class="sxs-lookup"><span data-stu-id="8dc89-173">**Method:** POST</span></span>
        - <span data-ttu-id="8dc89-174">**URL della richiesta:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span><span class="sxs-lookup"><span data-stu-id="8dc89-174">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span></span>
        - <span data-ttu-id="8dc89-175">**Corpo della richiesta:** corpo('Invoke\_an\_HTTP\_request')?['value']</span><span class="sxs-lookup"><span data-stu-id="8dc89-175">**Body of the request:** body('Invoke\_an\_HTTP\_request')?['value']</span></span>

            > [!NOTE]
            > <span data-ttu-id="8dc89-176">Potrebbe essere necessario inserire il valore **Corpo della richiesta** nella visualizzazione codice o nell'editor di funzioni nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8dc89-176">You might have to enter the **Body of the request** value either in code view or in the function editor in the designer.</span></span>

        ![Azione Richiama richiesta HTTP 2](media/integration-logic-app-get-execution-status-step.png)

        ![Azione Imposta variabile](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > <span data-ttu-id="8dc89-179">Il valore dell'azione **Imposta variabile** (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) differirà dal valore del corpo della richiesta **Richiama richiesta HTTP 2** anche se la finestra di progettazione mostrerà i valori allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="8dc89-179">The value for the **Set variable** action (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) will differ from the value for the **Invoke an HTTP request 2** body value, even though the designer will show the values in the same way.</span></span>

7. <span data-ttu-id="8dc89-180">Ottenere l'URL di download del pacchetto esportato.</span><span class="sxs-lookup"><span data-stu-id="8dc89-180">Get the download URL of the exported package.</span></span>

    - <span data-ttu-id="8dc89-181">Aggiungere un'azione **Richiama richiesta HTTP** per chiamare l'API REST DMF [GetExportedPackageUrl](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexportedpackageurl).</span><span class="sxs-lookup"><span data-stu-id="8dc89-181">Add an **Invoke HTTP request** action to call the [GetExportedPackageUrl](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API.</span></span>

        - <span data-ttu-id="8dc89-182">**Metodo:** POST</span><span class="sxs-lookup"><span data-stu-id="8dc89-182">**Method:** POST</span></span>
        - <span data-ttu-id="8dc89-183">**URL della richiesta:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span><span class="sxs-lookup"><span data-stu-id="8dc89-183">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span></span>
        - <span data-ttu-id="8dc89-184">**Corpo della richiesta:** {"executionId": body('GetExportedPackageURL')?['value']}</span><span class="sxs-lookup"><span data-stu-id="8dc89-184">**Body of the request:** {"executionId": body('GetExportedPackageURL')?['value']}</span></span>

        ![Azione GetExportedPackageURL](media/integration-logic-app-get-exported-package-step.png)

8. <span data-ttu-id="8dc89-186">Scaricare il pacchetto esportato.</span><span class="sxs-lookup"><span data-stu-id="8dc89-186">Download the exported package.</span></span>

    - <span data-ttu-id="8dc89-187">Aggiungere una richiesta **GET** HTTP (un'[azione del connettore HTTP](/azure/connectors/connectors-native-http)) integrata per scaricare il pacchetto dall'URL restituito nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="8dc89-187">Add an HTTP **GET** request (a built-in [HTTP connector action](/azure/connectors/connectors-native-http)) to download the package from the URL that was returned in the previous step.</span></span>

        - <span data-ttu-id="8dc89-188">**Metodo:** GET</span><span class="sxs-lookup"><span data-stu-id="8dc89-188">**Method:** GET</span></span>
        - <span data-ttu-id="8dc89-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span><span class="sxs-lookup"><span data-stu-id="8dc89-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span></span>

            > [!NOTE]
            > <span data-ttu-id="8dc89-190">Potrebbe essere necessario immettere il valore **URI** nella visualizzazione codice o nell'editor di funzioni nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8dc89-190">You might have to enter the **URI** value either in code view or in the function editor in the designer.</span></span>

        ![Azione GET HTTP](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > <span data-ttu-id="8dc89-192">Questa richiesta non richiede alcuna autenticazione aggiuntiva, in quanto l'URL che l'API **GetExportedPackageUrl** restituisce include un token di firme di accesso condiviso che concede l'accesso per scaricare il file.</span><span class="sxs-lookup"><span data-stu-id="8dc89-192">This request doesn't require any additional authentication, because the URL that the **GetExportedPackageUrl** API returns includes a shared access signatures token that grants access to download the file.</span></span>

9. <span data-ttu-id="8dc89-193">Salvare il pacchetto scaricato utilizzando il connettore [OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness).</span><span class="sxs-lookup"><span data-stu-id="8dc89-193">Save the downloaded package by using the [OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness) connector.</span></span>

    - <span data-ttu-id="8dc89-194">Aggiungere l'azione [Crea file](/connectors/onedriveforbusinessconnector/#create-file) di OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="8dc89-194">Add a OneDrive for Business [Create File](/connectors/onedriveforbusinessconnector/#create-file) action.</span></span>
    - <span data-ttu-id="8dc89-195">Connettersi all'account OneDrive for Business, come necessario.</span><span class="sxs-lookup"><span data-stu-id="8dc89-195">Connect to your OneDrive for Business account, as required.</span></span>

        - <span data-ttu-id="8dc89-196">**Percorso cartella:** una cartella qualsiasi</span><span class="sxs-lookup"><span data-stu-id="8dc89-196">**Folder Path:** A folder of your choice</span></span>
        - <span data-ttu-id="8dc89-197">**Nome file:** worker\_package.zip</span><span class="sxs-lookup"><span data-stu-id="8dc89-197">**File Name:** worker\_package.zip</span></span>
        - <span data-ttu-id="8dc89-198">**Contenuto file:** il corpo del passaggio precedente (contenuto dinamico)</span><span class="sxs-lookup"><span data-stu-id="8dc89-198">**File Content:** The body from the previous step (dynamic content)</span></span>

        ![Azione Crea file](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a><span data-ttu-id="8dc89-200">Passaggio 3: testare l'app per la logica</span><span class="sxs-lookup"><span data-stu-id="8dc89-200">Step 3: Test the logic app</span></span>

<span data-ttu-id="8dc89-201">Per testare l'app per la logica, selezionare il pulsante **Esegui** nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8dc89-201">To test your logic app, select the **Run** button in the designer.</span></span> <span data-ttu-id="8dc89-202">Vengono eseguiti i passaggi per l'esecuzione dell'app per la logica.</span><span class="sxs-lookup"><span data-stu-id="8dc89-202">You will see that the steps of the logic app start to run.</span></span> <span data-ttu-id="8dc89-203">L'esecuzione dell'app per la logica dovrebbe terminare dopo 30-40 secondi e la cartella di OneDrive for Business dovrebbe includere un nuovo file di pacchetto contenente i lavoratori esportati.</span><span class="sxs-lookup"><span data-stu-id="8dc89-203">After 30 to 40 seconds, the logic app should finish running, and your OneDrive for Business folder should include a new package file that contains the exported workers.</span></span>

<span data-ttu-id="8dc89-204">Se viene segnalato un errore per un qualsiasi passaggio, selezionare quel passaggio nella finestra di progettazione ed esaminarne i campi **Input** e **Output**.</span><span class="sxs-lookup"><span data-stu-id="8dc89-204">If a failure is reported for any step, select the failed step in the designer, and examine the **Inputs** and **Outputs** fields for it.</span></span> <span data-ttu-id="8dc89-205">Eseguire il debug e rettificare il passaggio come necessario per correggere gli errori.</span><span class="sxs-lookup"><span data-stu-id="8dc89-205">Debug and adjust the step as required to correct the errors.</span></span>

<span data-ttu-id="8dc89-206">L'illustrazione seguente mostra l'aspetto della finestra di progettazione di app per la logica quando tutti i passaggi dell'app per la logica vengono eseguiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="8dc89-206">The following illustration shows what the Logic Apps Designer looks like when all the steps of the logic app run successfully.</span></span>

![Esecuzione senza errori dell'app per la logica](media/integration-logic-app-successful-run.png)

## <a name="summary"></a><span data-ttu-id="8dc89-208">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="8dc89-208">Summary</span></span>

<span data-ttu-id="8dc89-209">In questa esercitazione, si è imparato a utilizzare un'app per la logica per esportare dati da Human Resources e a salvare i dati esportati in una cartella OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="8dc89-209">In this tutorial, you learned how to use a logic app to export data from Human Resources and save the exported data to a OneDrive for Business folder.</span></span> <span data-ttu-id="8dc89-210">È possibile modificare i passaggi di questa esercitazione come necessario in base alle proprie esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="8dc89-210">You can modify the steps of this tutorial as required to suit your business needs.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]