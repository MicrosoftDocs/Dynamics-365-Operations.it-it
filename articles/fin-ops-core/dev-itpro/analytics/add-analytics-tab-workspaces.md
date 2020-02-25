---
title: Aggiungere analisi alle aree di lavoro tramite Power BI Embedded
description: In questo argomento viene illustrato come importare un report di Power BI nella scheda Analisi di un'area di lavoro.
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: de85bf52d8e3415549db64501b2435ebd7377fef
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025856"
---
# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a><span data-ttu-id="8ab41-103">Aggiungere analisi alle aree di lavoro tramite Power BI Embedded</span><span class="sxs-lookup"><span data-stu-id="8ab41-103">Add analytics to workspaces by using Power BI Embedded</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="8ab41-104">Questa funzionalità è supportata in Finance and Operations (versione 7.2 e successiva).</span><span class="sxs-lookup"><span data-stu-id="8ab41-104">This feature is supported in Finance and Operations (version 7.2 and later).</span></span>

## <a name="introduction"></a><span data-ttu-id="8ab41-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="8ab41-105">Introduction</span></span>
<span data-ttu-id="8ab41-106">In questo argomento viene illustrato come importare un report di Microsoft Power BI nella scheda **Analisi** di un'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8ab41-106">This topic shows how to embed a Microsoft Power BI report on the **Analytics** tab of a workspace.</span></span> <span data-ttu-id="8ab41-107">Per l'esempio fornito qui, verrà estesa l'area di lavoro **Gestione prenotazione** nell'applicazione di gestione flotta per includere un'area di lavoro di analisi in una scheda **Analisi**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-107">For the example that is given here, we will extend the **Reservation management** workspace in the Fleet Management application to embed an analytical workspace on an **Analytics** tab.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ab41-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8ab41-108">Prerequisites</span></span>
+ <span data-ttu-id="8ab41-109">Accedere a un ambiente di sviluppo in cui è in esecuzione l'aggiornamento 8 della piattaforma o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="8ab41-109">Access to a developer environment that runs Platform update 8 or later.</span></span>
+ <span data-ttu-id="8ab41-110">Un report analitico (file .pbix) creato utilizzando Microsoft Power BI Desktop e con un modello dati che ha origine dal database dell'archivio dell'entità.</span><span class="sxs-lookup"><span data-stu-id="8ab41-110">An analytical report (.pbix file) that was created by using Microsoft Power BI Desktop, and that has a data model that is sourced from the Entity store database.</span></span>

## <a name="overview"></a><span data-ttu-id="8ab41-111">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8ab41-111">Overview</span></span>
<span data-ttu-id="8ab41-112">Se si estende un'area di lavoro dell'applicazione esistente o si introduce una nuova area di lavoro propria, è possibile utilizzare le visualizzazioni analitiche importate per offrire visualizzazioni perspicaci e interattive dei dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="8ab41-112">Whether you extend an existing application workspace or introduce a new workspace of your own, you can use embedded analytical views to deliver insightful and interactive views of your business data.</span></span> <span data-ttu-id="8ab41-113">Il processo per l'aggiunta di una scheda analitica dell'area di lavoro è costituito da quattro passaggi.</span><span class="sxs-lookup"><span data-stu-id="8ab41-113">The process for adding an analytical workspace tab has four steps.</span></span>

1. <span data-ttu-id="8ab41-114">Aggiungere un file .pbix come risorsa Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="8ab41-114">Add a .pbix file as a Dynamics 365 resource.</span></span>
2. <span data-ttu-id="8ab41-115">Definire una scheda analitica dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8ab41-115">Define an analytical workspace tab.</span></span>
3. <span data-ttu-id="8ab41-116">Importare la risorsa .pbix nella scheda dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8ab41-116">Embed the .pbix resource on the workspace tab.</span></span>
4. <span data-ttu-id="8ab41-117">Facoltativo: aggiungere le estensioni per personalizzare la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="8ab41-117">Optional: Add extensions to customize the view.</span></span>

> [!NOTE]
> <span data-ttu-id="8ab41-118">Per ulteriori informazioni su come creare report analitici, vedere [Introduzione a Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="8ab41-118">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span></span> <span data-ttu-id="8ab41-119">Questa pagina offre notevoli approfondimenti che consentono di creare soluzioni efficaci per la creazione di report analitici.</span><span class="sxs-lookup"><span data-stu-id="8ab41-119">This page is a great source for insights that can help you create compelling analytical reporting solutions.</span></span>

## <a name="add-a-pbix-file-as-a-resource"></a><span data-ttu-id="8ab41-120">Aggiungere un file .pbix come risorsa</span><span class="sxs-lookup"><span data-stu-id="8ab41-120">Add a .pbix file as a resource</span></span>
<span data-ttu-id="8ab41-121">Prima di iniziare è necessario creare o visualizzare il report di Power BI che verrà importato nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8ab41-121">Before you begin, you must create or obtain the Power BI report that you will embed in the workspace.</span></span> <span data-ttu-id="8ab41-122">Per ulteriori informazioni su come creare report analitici, vedere [Introduzione a Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="8ab41-122">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span></span>

<span data-ttu-id="8ab41-123">Seguire questi passaggi per aggiungere un file .pbix come elemento del progetto di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8ab41-123">Follow these steps to add a .pbix file as a Visual Studio project artifact.</span></span>

1. <span data-ttu-id="8ab41-124">Creare un nuovo progetto nel modello appropriato.</span><span class="sxs-lookup"><span data-stu-id="8ab41-124">Create a new project in the appropriate model.</span></span>
2. <span data-ttu-id="8ab41-125">In Esplora soluzioni selezionare il progetto, fare clic con il pulsante destro del mouse e quindi selezionare **Aggiungi** \> **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-125">In Solution Explorer, select the project, right-click, and then select **Add** \> **New Item**.</span></span>
3. <span data-ttu-id="8ab41-126">Nella finestra di dialogo **Aggiungi nuovo articolo**, in **Elementi operazioni**, selezionare il modello **Risorsa**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-126">In the **Add New Item** dialog box, under **Operations Artifacts**, select the **Resource** template.</span></span>
4. <span data-ttu-id="8ab41-127">Immettere un nome che verrà utilizzato per fare riferimento al report nei metadati X++, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-127">Enter a name that will be used to reference the report in X++ metadata, and then click **Add**.</span></span>

    ![Finestra di dialogo Aggiungi nuovo articolo](media/analytical-workspace-add.png)

5. <span data-ttu-id="8ab41-129">Individuare il file .pbix contenente la definizione di report analitico, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-129">Find the .pbix file that contains the definition of the analytical report, and then click **Open**.</span></span>

    ![Selezionare una finestra di dialogo del file di risorse](media/analytical-workspace-select-resource.png)

<span data-ttu-id="8ab41-131">Dopo aver aggiunto un file .pbix come risorsa Dynamics 365, è possibile importare i report nelle aree di lavoro e aggiungere collegamenti diretti utilizzando le voci di menu.</span><span class="sxs-lookup"><span data-stu-id="8ab41-131">Now that you've added the .pbix file as a Dynamics 365 resource, you can embed the reports in workspaces and add direct links by using menu items.</span></span>

## <a name="add-a-tab-control-to-an-application-workspace"></a><span data-ttu-id="8ab41-132">Aggiungere un controllo della scheda a un'area di lavoro dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8ab41-132">Add a tab control to an application workspace</span></span>
<span data-ttu-id="8ab41-133">In questo esempio verrà estesa l'area di lavoro **Gestione prenotazione** del modello di gestione flotta aggiungendo la scheda **Analisi** alla definizione del modulo **FMClerkWorkspace**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-133">In this example, we will extend the **Reservation management** workspace in the Fleet Management model by adding the **Analytics** tab to the definition of the **FMClerkWorkspace** form.</span></span>

<span data-ttu-id="8ab41-134">Nella figura che segue viene mostrato l'aspetto del modulo **FMClerkWorkspace** nello strumento di progettazione in Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8ab41-134">The following illustration shows what the **FMClerkWorkspace** form looks like in the designer in Microsoft Visual Studio.</span></span>

![Il modulo FMClerkWorkspace prima delle modifiche](media/analytical-workspace-definition-before.png)

<span data-ttu-id="8ab41-136">Seguire questi passaggi per estendere la definizione di modulo per l'area di lavoro **Gestione prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-136">Follow these steps to extend the form definition for the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="8ab41-137">Aprire lo strumento di progettazione del modulo per estendere la definizione di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8ab41-137">Open the form designer to extend the design definition.</span></span>
2. <span data-ttu-id="8ab41-138">Nella definizione di progettazione selezionare l'elemento principale che è contrassegnato come **Progettazione | Modello: Area di lavoro operativa**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-138">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
3. <span data-ttu-id="8ab41-139">Fare clic con il pulsante destro del mouse e selezionare **Nuovo** \> **Scheda** per aggiungere un controllo nuovo denominato **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-139">Right-click, and then select **New** \> **Tab** to add a new control that is named **FormTabControl1**.</span></span>
4. <span data-ttu-id="8ab41-140">Nello strumento di progettazione del modulo selezionare **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-140">In the form designer, select **FormTabControl1**.</span></span>
5. <span data-ttu-id="8ab41-141">Fare clic con il pulsante destro del mouse e scegliere **Nuova scheda** per aggiungere una nuova scheda.</span><span class="sxs-lookup"><span data-stu-id="8ab41-141">Right-click, and then select **New Tab Page** to add a new tab page.</span></span>
6. <span data-ttu-id="8ab41-142">Assegnare alla scheda un nome significativo, ad esempio **Area di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-142">Rename the tab page to something meaningful, such as **Workspace**.</span></span>
7. <span data-ttu-id="8ab41-143">Nello strumento di progettazione del modulo selezionare **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-143">In the form designer, select **FormTabControl1**.</span></span>
8. <span data-ttu-id="8ab41-144">Fare clic con il pulsante destro del mouse e scegliere **Nuova scheda**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-144">Right-click, and then select **New Tab Page**.</span></span>
9. <span data-ttu-id="8ab41-145">Assegnare alla scheda un nome significativo, ad esempio **Analisi**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-145">Rename the tab page to something meaningful, such as **Analytics**.</span></span>
10. <span data-ttu-id="8ab41-146">Nello strumento di progettazione del modulo selezionare **Analisi (scheda)**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-146">In the form designer, select **Analytics (Tab Page)**.</span></span>
11. <span data-ttu-id="8ab41-147">Impostare la proprietà **Titolo** su **Analisi**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-147">Set the **Caption** property to **Analytics**.</span></span>
12. <span data-ttu-id="8ab41-148">Fare clic con il pulsante destro del mouse sul controllo e quindi selezionare **Nuovo** \> **Gruppo** per aggiungere un nuovo controllo gruppo di moduli.</span><span class="sxs-lookup"><span data-stu-id="8ab41-148">Right-click the control, and then select **New** \> **Group** to add a new form group control.</span></span>
13. <span data-ttu-id="8ab41-149">Assegnare al gruppo di moduli un nome significativo, ad esempio **powerBIReportGroup**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-149">Rename the form group to something meaningful, such as **powerBIReportGroup**.</span></span>
14. <span data-ttu-id="8ab41-150">Nello strumento di progettazione del modulo selezionare **PanoramaBody (scheda)**, quindi trascinare il controllo sulla scheda **Area di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-150">In the form designer, select **PanoramaBody (Tab)**, and then drag the control onto the **Workspace** tab.</span></span>
15. <span data-ttu-id="8ab41-151">Nella definizione di progettazione selezionare l'elemento principale che è contrassegnato come **Progettazione | Modello: Area di lavoro operativa**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-151">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
16. <span data-ttu-id="8ab41-152">Fare clic con il pulsante destro del mouse e scegliere **Rimuovi criterio**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-152">Right-click, and then select **Remove pattern**.</span></span>
17. <span data-ttu-id="8ab41-153">Fare di nuovo clic con il pulsante destro del mouse e quindi selezionare **Aggiungi modello** \> **Area di lavoro a schede**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-153">Right-click again, and then select **Add pattern** \> **Workspace Tabbed**.</span></span>
18. <span data-ttu-id="8ab41-154">Eseguire una build per verificare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8ab41-154">Perform a build to verify your changes.</span></span>

<span data-ttu-id="8ab41-155">Nell'illustrazione riportata di seguito viene mostrato l'aspetto della progettazione dopo l'applicazione di tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="8ab41-155">The following illustration shows what the design looks like after these changes are applied.</span></span>

![FMClerkWorkspace dopo le modifiche](media/analytical-workspace-definition-after.png)

<span data-ttu-id="8ab41-157">Dopo aver aggiunto i controlli del modulo che verranno utilizzati per includere il report dell'area di lavoro, è necessario definire la dimensione del controllo padre in modo che si adatti al layout.</span><span class="sxs-lookup"><span data-stu-id="8ab41-157">Now that you've added the form controls that will be used to embed the workspace report, you must define the size of the parent control so that it accommodates the layout.</span></span> <span data-ttu-id="8ab41-158">Per impostazione predefinita, sia la pagina **Riquadro filtri** che la pagina **Scheda** saranno visibili nel report.</span><span class="sxs-lookup"><span data-stu-id="8ab41-158">By default, both the **Filters Pane** page and the **Tab** page will be visible on the report.</span></span> <span data-ttu-id="8ab41-159">Tuttavia, è possibile modificare la visibilità di questi controlli a seconda del cliente di destinazione del report.</span><span class="sxs-lookup"><span data-stu-id="8ab41-159">However, you can change the visibility of these controls as appropriate for the target consumer of the report.</span></span>

> [!NOTE]
> <span data-ttu-id="8ab41-160">Per le aree di lavoro incluse, si consiglia di utilizzare le estensioni per nascondere sia la pagina **Scheda** che la pagina **Riquadro filtri**, per coerenza.</span><span class="sxs-lookup"><span data-stu-id="8ab41-160">For embedded workspaces, we recommend that you use extensions to hide both the **Filters Pane** and **Tab** pages, for consistency.</span></span>

<span data-ttu-id="8ab41-161">L'attività di estensione della definizione di modulo dell'applicazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8ab41-161">You've now completed the task of extending the application form definition.</span></span> <span data-ttu-id="8ab41-162">Per ulteriori informazioni su come utilizzare le estensioni per effettuare personalizzazioni, vedere [Personalizzare tramite estensioni e overlayering](../extensibility/customization-overlayering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="8ab41-162">For more information about how to use extensions to do customizations, see [Customize through extension and overlayering](../extensibility/customization-overlayering-extensions.md).</span></span>

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a><span data-ttu-id="8ab41-163">Aggiungere la regola business X++ per importare un controllo del visualizzatore</span><span class="sxs-lookup"><span data-stu-id="8ab41-163">Add X++ business logic to embed a viewer control</span></span>
<span data-ttu-id="8ab41-164">Seguire questi passaggi per aggiungere la regola business che inizializza il controllo del visualizzatore di report incluso nell'area di lavoro **Gestione prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="8ab41-164">Follow these steps to add business logic that initializes the report viewer control that is embedded in the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="8ab41-165">Aprire lo strumento di progettazione del modulo **FMClerkWorkspace** per estendere la definizione di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8ab41-165">Open the **FMClerkWorkspace** form designer to extend the design definition.</span></span>
2. <span data-ttu-id="8ab41-166">Premere F7 per accedere al codice che sta dietro la definizione del codice.</span><span class="sxs-lookup"><span data-stu-id="8ab41-166">Press F7 to access the code behind the code definition.</span></span>
3. <span data-ttu-id="8ab41-167">Aggiungere il seguente codice X++.</span><span class="sxs-lookup"><span data-stu-id="8ab41-167">Add the following X++ code.</span></span>

    ```xpp
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                // initialize the PBI report control using shared helper
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
        }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. <span data-ttu-id="8ab41-168">Eseguire una build per verificare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8ab41-168">Perform a build to verify your changes.</span></span>

<span data-ttu-id="8ab41-169">L'attività di aggiunta della regola business per inizializzare il controllo del visualizzatore di report incluso è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8ab41-169">You've now completed the task of adding business logic to initialize the embedded report viewer control.</span></span> <span data-ttu-id="8ab41-170">Nell'illustrazione riportata di seguito viene mostrato l'aspetto dell'area di lavoro dopo l'applicazione di tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="8ab41-170">The following illustration shows what the workspace looks like after these changes are applied.</span></span>

![Report incluso nell'area di lavoro](media/analytical-workspace-final.png)

> [!NOTE]
> <span data-ttu-id="8ab41-172">È possibile accedere alla visualizzazione operativa esistente utilizzando le schede dell'area di lavoro sotto il titolo della pagina.</span><span class="sxs-lookup"><span data-stu-id="8ab41-172">You can access the existing operational view by using the workspace tabs below the page title.</span></span>

## <a name="reference"></a><span data-ttu-id="8ab41-173">Riferimento</span><span class="sxs-lookup"><span data-stu-id="8ab41-173">Reference</span></span>

### <a name="pbireporthelperinitializereportcontrol-method"></a><span data-ttu-id="8ab41-174">Metodo PBIReportHelper.initializeReportControl</span><span class="sxs-lookup"><span data-stu-id="8ab41-174">PBIReportHelper.initializeReportControl method</span></span>
<span data-ttu-id="8ab41-175">In questa sezione vengono fornite informazioni sulla classe degli helper utilizzata per importare un report di Power BI (risorsa .pbix) in un controllo del gruppo di moduli.</span><span class="sxs-lookup"><span data-stu-id="8ab41-175">This section provides information about the helper class that is used to embed a Power BI report (.pbix resource) in a form group control.</span></span>

#### <a name="syntax"></a><span data-ttu-id="8ab41-176">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ab41-176">Syntax</span></span>
```xpp
public static void initializeReportControl(
    str                 _resourceName,
    FormGroupControl    _formGroupControl,
    str                 _defaultPageName = '',
    boolean             _showFilterPane = false,
    boolean             _showNavPane = false,
    List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a><span data-ttu-id="8ab41-177">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ab41-177">Parameters</span></span>

| <span data-ttu-id="8ab41-178">Nome</span><span class="sxs-lookup"><span data-stu-id="8ab41-178">Name</span></span>             | <span data-ttu-id="8ab41-179">descrizione</span><span class="sxs-lookup"><span data-stu-id="8ab41-179">Description</span></span>                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8ab41-180">resourceName</span><span class="sxs-lookup"><span data-stu-id="8ab41-180">resourceName</span></span>     | <span data-ttu-id="8ab41-181">Nome della risorsa .pbix.</span><span class="sxs-lookup"><span data-stu-id="8ab41-181">The name of the .pbix resource.</span></span>                                                                              |
| <span data-ttu-id="8ab41-182">formGroupControl</span><span class="sxs-lookup"><span data-stu-id="8ab41-182">formGroupControl</span></span> | <span data-ttu-id="8ab41-183">Controllo del gruppo di moduli al quale applicare il controllo del report Power BI.</span><span class="sxs-lookup"><span data-stu-id="8ab41-183">The form group control to apply the Power BI report control to.</span></span>                                              |
| <span data-ttu-id="8ab41-184">defaultPageName</span><span class="sxs-lookup"><span data-stu-id="8ab41-184">defaultPageName</span></span>  | <span data-ttu-id="8ab41-185">Nome della pagina predefinita.</span><span class="sxs-lookup"><span data-stu-id="8ab41-185">The default page name.</span></span>                                                                                       |
| <span data-ttu-id="8ab41-186">showFilterPane</span><span class="sxs-lookup"><span data-stu-id="8ab41-186">showFilterPane</span></span>   | <span data-ttu-id="8ab41-187">Valore booleano che indica se il riquadro filtri deve essere visualizzato (**True**) o nascosto (**False**).</span><span class="sxs-lookup"><span data-stu-id="8ab41-187">A Boolean value that indicates whether the filter pane should be shown (**true**) or hidden (**false**).</span></span>     |
| <span data-ttu-id="8ab41-188">showNavPane</span><span class="sxs-lookup"><span data-stu-id="8ab41-188">showNavPane</span></span>      | <span data-ttu-id="8ab41-189">Valore booleano che indica se il riquadro di spostamento deve essere visualizzato (**True**) o nascosto (**False**).</span><span class="sxs-lookup"><span data-stu-id="8ab41-189">A Boolean value that indicates whether the navigation pane should be shown (**true**) or hidden (**false**).</span></span> |
| <span data-ttu-id="8ab41-190">defaultFilters</span><span class="sxs-lookup"><span data-stu-id="8ab41-190">defaultFilters</span></span>   | <span data-ttu-id="8ab41-191">Filtri di base per il report Power BI.</span><span class="sxs-lookup"><span data-stu-id="8ab41-191">The default filters for the Power BI report.</span></span>                                                                 |
