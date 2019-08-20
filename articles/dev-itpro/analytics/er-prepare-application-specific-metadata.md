---
title: Preparare metadati specifici dell'applicazione per RCS e ER
description: In questo argomento viene descritto come preparare metadati specifici dell'applicazione per Regulatory Configuration Service (RCS) e la creazione di report elettronici (ER).
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3a540676ba11bc3c0fb7855a2fdaff998819dfbe
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849687"
---
# <a name="prepare-application-specific-metadata-for-rcs"></a><span data-ttu-id="93579-103">Preparare metadati specifici dell'applicazione per RCS</span><span class="sxs-lookup"><span data-stu-id="93579-103">Prepare application-specific metadata for RCS</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="93579-104">In questo argomento vengono illustrati esempi delle seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="93579-104">This topic walks you through examples of the following tasks:</span></span>

- [<span data-ttu-id="93579-105">Preparare i metadati dell'applicazione da utilizzare in RCS</span><span class="sxs-lookup"><span data-stu-id="93579-105">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)
- [<span data-ttu-id="93579-106">Accedere ai metadati dell'applicazione utilizzando una configurazione ER</span><span class="sxs-lookup"><span data-stu-id="93579-106">Access application metadata by using an ER configuration</span></span>](#access-application-metadata-by-using-an-er-configuration)
- [<span data-ttu-id="93579-107">Accedere ai metadati dell'applicazione utilizzando applicazioni connesse</span><span class="sxs-lookup"><span data-stu-id="93579-107">Access application metadata by using connected applications</span></span>](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a><span data-ttu-id="93579-108">Preparare i metadati dell'applicazione da utilizzare in RCS</span><span class="sxs-lookup"><span data-stu-id="93579-108">Prepare application metadata that can be used in RCS</span></span>

<span data-ttu-id="93579-109">La procedura seguente illustra come un utente di Finance and Operations con ruolo di **amministratore di sistema** o di **sviluppatore per la creazione di report elettronici** può creare una configurazione per la creazione di report elettronici (ER) che contiene metadati per l'applicazione Microsoft Dynamics 365 for Finance and Operations e che viene utilizzata per la progettazione di configurazioni del mapping di modello ER in Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="93579-109">The following procedure shows how a user of Finance and Operations who has the **System Administrator** or **Electronic Reporting Developer** role can create an Electronic reporting (ER) configuration that contains metadata for the Microsoft Dynamics 365 for Finance and Operations application, and that is used to design ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="93579-110">La configurazione del mapping di modello ER di esempio creata in questo esempio verrà utilizzata per accedere alle transazioni del commercio estero.</span><span class="sxs-lookup"><span data-stu-id="93579-110">The sample ER model mapping configuration that is created in this example will be used to access foreign trade transactions.</span></span>

<span data-ttu-id="93579-111">Per questo esempio, si desidera utilizzare RCS per progettare una soluzione ER per Finance and Operations che verrà utilizzata per generare documenti elettronici contenenti informazioni del dominio aziendale per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="93579-111">For this example, you want to use RCS to design an ER solution for Finance and Operations that will be used to generate electronic documents that contain information from the foreign trade business domain.</span></span> <span data-ttu-id="93579-112">Per specificare il mapping tra il modello di dati ER e le origini dei dati necessari, accedere ai metadati dell'applicazione per Finance and Operations in RCS.</span><span class="sxs-lookup"><span data-stu-id="93579-112">To specify the mapping between the ER data model and the sources of required data, you must have access to application metadata for Finance and Operations in RCS.</span></span> <span data-ttu-id="93579-113">Di conseguenza, nell'ambito del processo di progettazione della soluzione ER è necessario configurare una nuova configurazione dei metadati ER contenente tutti i metadati attualmente necessari per generare report ER per il dominio aziendale selezionato.</span><span class="sxs-lookup"><span data-stu-id="93579-113">Therefore, as part of the process of designing the ER solution, you must configure a new ER metadata configuration that contains all the metadata that is currently required in order to generate ER reports for the selected business domain.</span></span>

> [!NOTE]
> <span data-ttu-id="93579-114">In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="93579-114">In this example, you will create a configuration for the sample company, Litware, Inc. These steps can be performed in any company.</span></span>

1. <span data-ttu-id="93579-115">Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="93579-115">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="93579-116">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**.</span><span class="sxs-lookup"><span data-stu-id="93579-116">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="93579-117">Se il provider di configurazione non è visualizzato, completare i passaggi della procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="93579-117">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="93579-118">Selezionare **Configurazioni dei metadati**.</span><span class="sxs-lookup"><span data-stu-id="93579-118">Select **Metadata configurations**.</span></span>
4. <span data-ttu-id="93579-119">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-119">Select **Create configuration**.</span></span>
5. <span data-ttu-id="93579-120">Nella finestra di dialogo a discesa, nel campo **Nome**, immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="93579-120">In the drop-down dialog box, in the **Name** field, enter a name.</span></span> <span data-ttu-id="93579-121">Per questo esempio, immettere **Metadati del commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="93579-121">For this example, enter **Foreign trade metadata**.</span></span>
6. <span data-ttu-id="93579-122">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-122">Select **Create configuration**.</span></span>
7. <span data-ttu-id="93579-123">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-123">Select **Designer**.</span></span>
8. <span data-ttu-id="93579-124">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="93579-124">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93579-125">È possibile selezionare tutti i metadati per l'intera applicazione o per i modelli o moduli selezionati.</span><span class="sxs-lookup"><span data-stu-id="93579-125">You can select all metadata either for the whole application, or for selected models or modules.</span></span> <span data-ttu-id="93579-126">In entrambi i casi, tenere presente che i seguenti metadati verranno aggiunti automaticamente: tabelle di record, enumerazioni e tipi di dati estesi.</span><span class="sxs-lookup"><span data-stu-id="93579-126">In both cases, be aware that the following metadata will be automatically added: tables of records, enumerations, and extended data types (EDTs).</span></span> <span data-ttu-id="93579-127">Se sono necessari ulteriori tipi di metadati, devono essere aggiunti manualmente.</span><span class="sxs-lookup"><span data-stu-id="93579-127">When additional types of metadata are required, they must be manually added.</span></span>

<span data-ttu-id="93579-128">È necessario aggiungere alcuni metadati correlati alle transazioni del commercio estero e selezionare manualmente elementi di metadati.</span><span class="sxs-lookup"><span data-stu-id="93579-128">You must add some metadata that is related to foreign trade transactions and manually select metadata items.</span></span>

9. <span data-ttu-id="93579-129">Selezionare **Aggiungi origine dati \> Record di tabella**.</span><span class="sxs-lookup"><span data-stu-id="93579-129">Select **Add data source \> Table records**.</span></span>
10. <span data-ttu-id="93579-130">Filtrare in base al valore **Intrastat** nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="93579-130">Filter on a value of **Intrastat** in the **Name** field.</span></span>
11. <span data-ttu-id="93579-131">Selezionare il record di tabella **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="93579-131">Select the **Intrastat** table record.</span></span>
12. <span data-ttu-id="93579-132">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="93579-132">Select **OK**.</span></span>

<span data-ttu-id="93579-133">È necessario aggiungere informazioni sui metadati relative alla tabella di record Intrastat.</span><span class="sxs-lookup"><span data-stu-id="93579-133">You must add metadata information about the Intrastat table of records.</span></span>

13. <span data-ttu-id="93579-134">Nella struttura, selezionare **Record di tabella Intrastat \> \>Relazioni \> IntrastatCommodity (Record tabella EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="93579-134">In the tree, select **Table records Intrastat \> \>Relations \> IntrastatCommodity (Table records EcoResCategory)**.</span></span>
14. <span data-ttu-id="93579-135">Selezionare **Aggiungi metadati**.</span><span class="sxs-lookup"><span data-stu-id="93579-135">Select **Add metadata**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93579-136">I metadati relativi alle relazioni necessarie per la tabella di record selezionata devono essere aggiunti manualmente.</span><span class="sxs-lookup"><span data-stu-id="93579-136">Metadata about required relations for the selected table of records must be added manually.</span></span>

15. <span data-ttu-id="93579-137">Selezionare **Aggiungi origine dati**.</span><span class="sxs-lookup"><span data-stu-id="93579-137">Select **Add data source**.</span></span>
16. <span data-ttu-id="93579-138">Selezionare **Enumerazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-138">Select **Enumeration**.</span></span>
17. <span data-ttu-id="93579-139">Filtrare in base al valore **IntrastatDirection** nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="93579-139">Filter on a value of **IntrastatDirection** in the **Name** field.</span></span>
18. <span data-ttu-id="93579-140">Selezionare il record di enumerazione **IntrastatDirection**.</span><span class="sxs-lookup"><span data-stu-id="93579-140">Select the **IntrastatDirection** enumeration record.</span></span>
19. <span data-ttu-id="93579-141">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="93579-141">Select **OK**.</span></span>
20. <span data-ttu-id="93579-142">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="93579-142">Select **Save**.</span></span>
21. <span data-ttu-id="93579-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="93579-143">Close the page.</span></span>
22. <span data-ttu-id="93579-144">Completare la versione bozza della configurazione dei metadati:</span><span class="sxs-lookup"><span data-stu-id="93579-144">Complete the draft version of the metadata configuration:</span></span>

    1. <span data-ttu-id="93579-145">Selezionare **Cambia stato \> Completa**.</span><span class="sxs-lookup"><span data-stu-id="93579-145">Select **Change status \> Complete**.</span></span>
    2. <span data-ttu-id="93579-146">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="93579-146">Select **OK**.</span></span>
    3. <span data-ttu-id="93579-147">Selezionare la versione completata 1.</span><span class="sxs-lookup"><span data-stu-id="93579-147">Select the completed version 1.</span></span>

23. <span data-ttu-id="93579-148">Esportare la versione completata della configurazione dei metadati dall'applicazione come file XML:</span><span class="sxs-lookup"><span data-stu-id="93579-148">Export the completed version of the metadata configuration from the application as an XML file:</span></span>

    1. <span data-ttu-id="93579-149">Selezionare **Scambia \> Esporta come file XML**.</span><span class="sxs-lookup"><span data-stu-id="93579-149">Select **Exchange \> Export as XML file**.</span></span>
    2. <span data-ttu-id="93579-150">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="93579-150">Select **OK**.</span></span>

<span data-ttu-id="93579-151">La configurazione dei metadati ER creata viene salvata come file **Metadati del commercio estero.xml**.</span><span class="sxs-lookup"><span data-stu-id="93579-151">The ER metadata configuration that you created is saved as the **Foreign trade metadata.xml** file.</span></span> <span data-ttu-id="93579-152">È ora possibile importarla in RCS, di modo che possa essere utilizzata come origine dei metadati del dominio aziendale per il commercio estero in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93579-152">You can now import it into RCS, so that it can be used as the source of metadata for the foreign trade business domain in Finance and Operations.</span></span> <span data-ttu-id="93579-153">In base a queste informazioni, è possibile specificare il mapping tra i metadati dell'applicazione e il modello di dati ER.</span><span class="sxs-lookup"><span data-stu-id="93579-153">Based on this information, you can specify the mapping between application metadata and the ER data model.</span></span>

## <a name="access-application-metadata-by-using-an-er-configuration"></a><span data-ttu-id="93579-154">Accedere ai metadati dell'applicazione utilizzando una configurazione ER</span><span class="sxs-lookup"><span data-stu-id="93579-154">Access application metadata by using an ER configuration</span></span>

<span data-ttu-id="93579-155">La seguente procedura illustra come un utente RCS con ruolo **Amministratore di sistema** o **Sviluppatore per la creazione di report elettronici** può progettare un nuovo mapping di modello ER utilizzando i metadati dell'applicazione Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93579-155">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata from the Finance and Operations application.</span></span> <span data-ttu-id="93579-156">Sarà possibile accedere ai metadati dell'applicazione utilizzando la configurazione dei metadati ER contenente un set di metadati di esempio per accedere alle transazioni del commercio estero.</span><span class="sxs-lookup"><span data-stu-id="93579-156">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span>

<span data-ttu-id="93579-157">Prima di poter completare questa procedura, è necessario dapprima svolgere le seguenti procedure:</span><span class="sxs-lookup"><span data-stu-id="93579-157">Before you can complete this procedure, you must first complete the following procedures:</span></span>

- [<span data-ttu-id="93579-158">Creare un provider di configurazione e contrassegnarlo come attivo</span><span class="sxs-lookup"><span data-stu-id="93579-158">Create a configuration provider and mark it as active</span></span>](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [<span data-ttu-id="93579-159">Preparare i metadati dell'applicazione da utilizzare in RCS</span><span class="sxs-lookup"><span data-stu-id="93579-159">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)

1. <span data-ttu-id="93579-160">Andare a **Tutte le aree di lavoro \> Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="93579-160">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="93579-161">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**.</span><span class="sxs-lookup"><span data-stu-id="93579-161">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="93579-162">Se il provider di configurazione non è visualizzato, completare i passaggi della procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="93579-162">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="93579-163">Importare la configurazione dei metadati ER che contiene i metadati per l'applicazione Finance and Operations e che è configurata per generare documenti elettronici per il dominio aziendale per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="93579-163">Import the ER metadata configuration that contains metadata for the Finance and Operations application, and that is configured to generate electronic documents for the foreign trade business domain.</span></span> <span data-ttu-id="93579-164">Questa configurazione dei metadati ER è stata creata ed esportata come file XML nella procedura [Preparare i metadati dell'applicazione da utilizzare in RCS](#prepare-application-metadata-that-can-be-used-in-rcs) vista in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="93579-164">You created this ER metadata configuration and exported it as an XML file in the [Prepare application metadata that can be used in RCS](#prepare-application-metadata-that-can-be-used-in-rcs) procedure earlier in this topic.</span></span>

    1. <span data-ttu-id="93579-165">Selezionare **Configurazioni dei metadati**.</span><span class="sxs-lookup"><span data-stu-id="93579-165">Select **Metadata configurations**.</span></span>
    2. <span data-ttu-id="93579-166">Selezionare **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="93579-166">Select **Exchange**.</span></span>
    3. <span data-ttu-id="93579-167">Selezionare **Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="93579-167">Select **Load from XML file**.</span></span>
    4. <span data-ttu-id="93579-168">Selezionare il file **Metadati del commercio estero.xml**.</span><span class="sxs-lookup"><span data-stu-id="93579-168">Browse to select the **Foreign trade metadata.xml** file.</span></span>
    5. <span data-ttu-id="93579-169">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="93579-169">Select **OK**.</span></span>
    6. <span data-ttu-id="93579-170">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="93579-170">Close the page.</span></span>

4. <span data-ttu-id="93579-171">Creare una configurazione del modello di dati:</span><span class="sxs-lookup"><span data-stu-id="93579-171">Create a data model configuration:</span></span>

    1. <span data-ttu-id="93579-172">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="93579-172">Select **Reporting configurations**.</span></span>
    2. <span data-ttu-id="93579-173">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-173">Select **Create configuration**.</span></span>
    3. <span data-ttu-id="93579-174">Nella finestra di dialogo a discesa, nel campo **Nome**, immettere **Modello del commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="93579-174">In the drop-down dialog box, in the **Name** field, enter **Foreign trade model**.</span></span>
    4. <span data-ttu-id="93579-175">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-175">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="93579-176">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-176">Select **Designer**.</span></span>
    6. <span data-ttu-id="93579-177">Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="93579-177">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="93579-178">Nel campo **Nome**, digitare **Radice**.</span><span class="sxs-lookup"><span data-stu-id="93579-178">In the **Name** field, type **Root**.</span></span>
        2. <span data-ttu-id="93579-179">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="93579-179">Select **Add**.</span></span>
    
    7. <span data-ttu-id="93579-180">Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="93579-180">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="93579-181">Nel campo **Nome** digitare **Transazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-181">In the **Name** field, type **Transaction**.</span></span>
        2. <span data-ttu-id="93579-182">Nel campo **Tipo di articolo** selezionare **Elenco di record**.</span><span class="sxs-lookup"><span data-stu-id="93579-182">In the **Item type** field, select **Record list**.</span></span>
        3. <span data-ttu-id="93579-183">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="93579-183">Select **Add**.</span></span>
 
    8. <span data-ttu-id="93579-184">Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="93579-184">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="93579-185">Nel campo **Nome** digitare **Codice voce doganale**.</span><span class="sxs-lookup"><span data-stu-id="93579-185">In the **Name** field, type **Commodity code**.</span></span>
        2. <span data-ttu-id="93579-186">Nel campo **Tipo di articolo** selezionare **Stringa**.</span><span class="sxs-lookup"><span data-stu-id="93579-186">In the **Item type** field, select **String**.</span></span>
        3. <span data-ttu-id="93579-187">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="93579-187">Select **Add**.</span></span>

    9. <span data-ttu-id="93579-188">Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="93579-188">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="93579-189">Nel campo Nome digitare **Importo fatturato**.</span><span class="sxs-lookup"><span data-stu-id="93579-189">In the Name field, type **Invoiced amount**.</span></span>
        2. <span data-ttu-id="93579-190">Nel campo **Tipo di articolo** selezionare **Reale**.</span><span class="sxs-lookup"><span data-stu-id="93579-190">In the **Item type** field, select **Real**.</span></span>
        3. <span data-ttu-id="93579-191">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="93579-191">Select **Add**.</span></span>

    10. <span data-ttu-id="93579-192">Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="93579-192">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="93579-193">Digitare **Data** nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="93579-193">In the **Name** field, type **Date**.</span></span>
        2. <span data-ttu-id="93579-194">Nel campo **Tipo di articolo** selezionare **Data**.</span><span class="sxs-lookup"><span data-stu-id="93579-194">In the **Item type** field, select **Date**.</span></span>
        3. <span data-ttu-id="93579-195">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="93579-195">Select **Add**.</span></span>
 
    11. <span data-ttu-id="93579-196">Selezionare **Aggiungi \> Riferimento radice**.</span><span class="sxs-lookup"><span data-stu-id="93579-196">Select **Add \> Root reference**.</span></span>
    12. <span data-ttu-id="93579-197">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="93579-197">Select **OK**.</span></span>
    13. <span data-ttu-id="93579-198">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="93579-198">Select **Save**.</span></span>
    14. <span data-ttu-id="93579-199">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="93579-199">Close the page.</span></span>
    15. <span data-ttu-id="93579-200">Selezionare **Cambia stato \> Completa**.</span><span class="sxs-lookup"><span data-stu-id="93579-200">Select **Change status \> Complete**.</span></span>
    16. <span data-ttu-id="93579-201">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="93579-201">Select **OK**.</span></span>

5. <span data-ttu-id="93579-202">Creare una configurazione del mapping di modello</span><span class="sxs-lookup"><span data-stu-id="93579-202">Create a model mapping configuration:</span></span>

    1. <span data-ttu-id="93579-203">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-203">Select **Create configuration**.</span></span>
    2. <span data-ttu-id="93579-204">Nella finestra di dialogo a discesa, nel campo **Nuovo** immettere **Mapping di modello basato sul modello di dati Modello del commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="93579-204">In the drop-down dialog box, in the **New** field, enter **Model Mapping based on data model Foreign trade model**.</span></span>
    3. <span data-ttu-id="93579-205">Nel campo **Nome**, immettere **Mapping del commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="93579-205">In the **Name** field, enter **Foreign trade mapping**.</span></span>
    4. <span data-ttu-id="93579-206">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-206">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="93579-207">Nella scheda dettaglio **Prerequisiti**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="93579-207">On the **Prerequisites** FastTab, select **Edit**.</span></span>
    6. <span data-ttu-id="93579-208">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="93579-208">Select **New**.</span></span>
    7. <span data-ttu-id="93579-209">Nel campo **Tipo di componente prerequisito**, selezionare **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-209">In the **Prerequisite component type** field, select **Configuration**.</span></span>
    8. <span data-ttu-id="93579-210">Selezionare la configurazione **Metadati del commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="93579-210">Select the **Foreign trade metadata** configuration.</span></span>
    9. <span data-ttu-id="93579-211">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="93579-211">Select **Save**.</span></span> <span data-ttu-id="93579-212">Da notare che il riferimento viene aggiunto alla versione 1 della configurazione **Metadati del commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="93579-212">Notice that the reference is added to version 1 of the **Foreign trade metadata** configuration.</span></span> <span data-ttu-id="93579-213">I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione del mapping di modello.</span><span class="sxs-lookup"><span data-stu-id="93579-213">Application metadata from this configuration will be offered while the model mapping is designed.</span></span>
    10. <span data-ttu-id="93579-214">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="93579-214">Close the page.</span></span>
    11. <span data-ttu-id="93579-215">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-215">Select **Designer**.</span></span>
    12. <span data-ttu-id="93579-216">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-216">Select **Designer**.</span></span>
    13. <span data-ttu-id="93579-217">Nella struttura selezionare **Dynamics 365 for Operations \> Record di tabella**.</span><span class="sxs-lookup"><span data-stu-id="93579-217">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
    14. <span data-ttu-id="93579-218">Selezionare **Aggiungi radice**.</span><span class="sxs-lookup"><span data-stu-id="93579-218">Select **Add root**.</span></span>
    15. <span data-ttu-id="93579-219">Nel campo **Nome** immettere **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="93579-219">In the **Name** field, enter **Intrastat**.</span></span>
    16. <span data-ttu-id="93579-220">Selezionare i record di tabella **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="93579-220">Select **Intrastat** table records.</span></span>
    17. <span data-ttu-id="93579-221">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="93579-221">Select **OK**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="93579-222">Solo 2 tabelle sono disponibili poiché solo 2 tabelle sono state aggiunte al set di metadati attualmente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="93579-222">Only two tables are offered, because only two tables were added to the set of metadata that is currently used.</span></span>

    18. <span data-ttu-id="93579-223">Selezionare **Associa**.</span><span class="sxs-lookup"><span data-stu-id="93579-223">Select **Bind**.</span></span>
    19. <span data-ttu-id="93579-224">Nella struttura selezionare **Intrastat \> AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="93579-224">In the tree, select **Intrastat \> AmountMST**.</span></span>
    20. <span data-ttu-id="93579-225">Nella struttura selezionare **Transazione = Intrastat \> Importo fatturato**.</span><span class="sxs-lookup"><span data-stu-id="93579-225">In the tree, select **Transaction = Intrastat \> Invoiced amount**.</span></span>
    21. <span data-ttu-id="93579-226">Selezionare **Associa**.</span><span class="sxs-lookup"><span data-stu-id="93579-226">Select **Bind**.</span></span>
    22. <span data-ttu-id="93579-227">Nella struttura selezionare **Intrastat \> TransDate**.</span><span class="sxs-lookup"><span data-stu-id="93579-227">In the tree, select **Intrastat \> TransDate**.</span></span>
    23. <span data-ttu-id="93579-228">Nella struttura selezionare **Transazione = Intrastat \> Data**.</span><span class="sxs-lookup"><span data-stu-id="93579-228">In the tree, select **Transaction = Intrastat \> Date**.</span></span>
    24. <span data-ttu-id="93579-229">Selezionare **Associa**.</span><span class="sxs-lookup"><span data-stu-id="93579-229">Select **Bind**.</span></span>
    25. <span data-ttu-id="93579-230">Nella struttura selezionare **Intrastat \> \>Relazioni \> IntrastatCommodity \> Codice**.</span><span class="sxs-lookup"><span data-stu-id="93579-230">In the tree, select **Intrastat \> \>Relations \> IntrastatCommodity \> Code**.</span></span>
    26. <span data-ttu-id="93579-231">Nella struttura selezionare **Transazione = Intrastat \> Codice voce doganale**.</span><span class="sxs-lookup"><span data-stu-id="93579-231">In the tree, select **Transaction = Intrastat \> Commodity code**.</span></span>
    27. <span data-ttu-id="93579-232">Selezionare **Associa**.</span><span class="sxs-lookup"><span data-stu-id="93579-232">Select **Bind**.</span></span>
    28. <span data-ttu-id="93579-233">Selezionare **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="93579-233">Select **Validate**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="93579-234">Dopo la convalida, gli elementi del modello di dati risulteranno associati agli articoli delle origini dati descritte utilizzando i dettagli dei metadati dell'applicazione nella configurazione dei metadati ER.</span><span class="sxs-lookup"><span data-stu-id="93579-234">After validation is completed, you've successfully bound elements of the data model to items of the data sources that are described by using details of the application metadata from the referenced ER metadata configuration.</span></span>

    29. <span data-ttu-id="93579-235">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="93579-235">Select **Save**.</span></span>

<span data-ttu-id="93579-236">Quando necessario, è possibile estendere il set di metadati esistente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93579-236">As you require, you can extend the existing set of metadata in Finance and Operations.</span></span> <span data-ttu-id="93579-237">È quindi possibile esportare la nuova versione completata della configurazione dei metadati ER da Finance and Operations, importarla in RCS e aggiornare i prerequisiti della configurazione del mapping di modello configurata per fare riferimento a una nuova versione della configurazione dei metadati importata.</span><span class="sxs-lookup"><span data-stu-id="93579-237">You can then export the new completed version of the ER metadata configuration from Finance and Operations, import it into RCS, and update the prerequisites of the configured model mapping configuration to refer to a new version of the imported metadata configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="93579-238">Questo metodo per ottenere informazioni sui metadati dell'applicazione è l'unico disponibile per le applicazioni distribuite localmente (ovvero, quando un modello di distribuzione di dati aziendali locali \[LBD\] o on-premises è utilizzato per Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="93579-238">This method for getting information about application metadata is the only available method for applications that are locally deployed (that is, when a local business data \[LBD\], or on-premises, deployment model is used for Finance and Operations).</span></span>

## <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="93579-239">Accedere ai metadati dell'applicazione utilizzando applicazioni connesse</span><span class="sxs-lookup"><span data-stu-id="93579-239">Access application metadata by using connected applications</span></span>

<span data-ttu-id="93579-240">La seguente procedura illustra come un utente RCS con ruolo **Amministratore di sistema** o **Sviluppatore per la creazione di report elettronici** può progettare un nuovo mapping di modello ER utilizzando i metadati dell'applicazione Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93579-240">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata of the Finance and Operations application.</span></span> <span data-ttu-id="93579-241">Per accedere ai metadati dell'applicazione online si utilizzerà l'applicazione connessa RCS.</span><span class="sxs-lookup"><span data-stu-id="93579-241">Application metadata will be accessed online by using RCS connected application.</span></span> <span data-ttu-id="93579-242">Un mapping di modello ER di esempio verrà configurato per accedere alle transazioni del commercio estero.</span><span class="sxs-lookup"><span data-stu-id="93579-242">A sample ER model mapping will be configured to access foreign trade transactions.</span></span>

<span data-ttu-id="93579-243">Per completare questa procedura, completare dapprima la procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md) in RCS.</span><span class="sxs-lookup"><span data-stu-id="93579-243">To complete this procedure, you must first complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure in RCS.</span></span> <span data-ttu-id="93579-244">Se i passaggi nella procedura [Accedere ai metadati dell'applicazione utilizzando una configurazione ER](#access-application-metadata-by-using-an-er-configuration) vista precedentemente in questo argomento non sono stati ancora completati, accedere alla pagina [Guide attività per la creazione di report elettronici per Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) per scaricare i seguenti file di configurazioni ER e salvarli localmente: **Metadati del commercio estero.xml**, **Modello del commercio estero.xml** e **Mapping del commercio estero.xml**.</span><span class="sxs-lookup"><span data-stu-id="93579-244">If you haven't yet completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, go to [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page to download the following ER configuration files in advance and save them locally: **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml**.</span></span>


### <a name="get-required-er-configurations"></a><span data-ttu-id="93579-245">Ottenere le configurazioni ER necessarie</span><span class="sxs-lookup"><span data-stu-id="93579-245">Get required ER configurations</span></span>

<span data-ttu-id="93579-246">Se i passaggi nella procedura [Accedere ai metadati dell'applicazione utilizzando una configurazione ER](#access-application-metadata-by-using-an-er-configuration) vista precedentemente in questo argomento sono stati completati, si dispone già di tutte le configurazioni ER necessarie (configurazioni di metadati, modello e mapping del commercio estero) nell'istanza di RCS corrente.</span><span class="sxs-lookup"><span data-stu-id="93579-246">If you've already completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, you already have all the required ER configurations (the foreign trade metadata, model, and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="93579-247">In tal caso, è possibile ignorare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="93579-247">In that case, you can skip this procedure.</span></span>

1. <span data-ttu-id="93579-248">Andare a **Tutte le aree di lavoro \> Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="93579-248">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="93579-249">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="93579-249">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="93579-250">Caricare i file di configurazione **Metadati del commercio estero.xml**, **Modello del commercio estero.xml** e **Mapping del commercio estero.xml** ripetendo li seguenti passaggi per ognuno:</span><span class="sxs-lookup"><span data-stu-id="93579-250">Load the **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml** configuration files repeating the following chain of steps for each of them:</span></span>

    1. <span data-ttu-id="93579-251">Selezionare **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="93579-251">Select **Exchange**.</span></span>
    2. <span data-ttu-id="93579-252">Selezionare **Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="93579-252">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="93579-253">Selezionare **Sfoglia** e selezionare un file.</span><span class="sxs-lookup"><span data-stu-id="93579-253">Select **Browse**, and select a file.</span></span>
    4. <span data-ttu-id="93579-254">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="93579-254">Select **OK**.</span></span>

### <a name="register-the-connection-with-finance-and-operations"></a><span data-ttu-id="93579-255">Registrare la connessione a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93579-255">Register the connection with Finance and Operations</span></span>

1. <span data-ttu-id="93579-256">Andare a **Tutte le aree di lavoro \> Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="93579-256">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="93579-257">Selezionare **Applicazioni connesse**.</span><span class="sxs-lookup"><span data-stu-id="93579-257">Select **Connected applications**.</span></span>
3. <span data-ttu-id="93579-258">Assicurarsi che l'applicazione configurata sia basata su Microsoft Azure e che sia accessibile agli utenti RCS.</span><span class="sxs-lookup"><span data-stu-id="93579-258">Make sure that the configured application is based on Microsoft Azure, and that it is accessible in general to RCS users.</span></span> <span data-ttu-id="93579-259">L'utente RCS corrente deve avere accesso all'applicazione configurata ed essere registrato come utente di questa applicazione con un ruolo che fornisce privilegi di accesso ai metadati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="93579-259">The current RCS user must have access to the configured application being registered as a user of this application in a role that gives him or her privileges to access the application's metadata.</span></span>
4. <span data-ttu-id="93579-260">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="93579-260">Select **New**.</span></span>
5. <span data-ttu-id="93579-261">Nel campo **Nome**, immettere **MiaAppConnessa** come nome dell'applicazione connessa.</span><span class="sxs-lookup"><span data-stu-id="93579-261">In the **Name** field, enter **MyConnectedApp** as the name of the connected application.</span></span>
6. <span data-ttu-id="93579-262">Nel campo **Applicazione**, specificare l'URL dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="93579-262">In the **Application** field, specify the URL of the application.</span></span>
7. <span data-ttu-id="93579-263">Nel campo **Tenant**, specificare il provider dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="93579-263">In the **Tenant** field, specify the provider of the application.</span></span>
8. <span data-ttu-id="93579-264">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="93579-264">Select **Save**.</span></span> 
9. <span data-ttu-id="93579-265">Quando si verifica la connessione all'applicazione configurata, nella pagina **Connettersi all'applicazione remota**, selezionare il collegamento **Fare clic qui per la connessione all'applicazione remota selezionata**.</span><span class="sxs-lookup"><span data-stu-id="93579-265">When you check the connection to the configured application, on the **Connect to remote application** page, select the **Select here to connect to selected remote application** link.</span></span> 
10. <span data-ttu-id="93579-266">Selezionare **Verifica connessione** per convalidare l'accesso all'applicazione configurata.</span><span class="sxs-lookup"><span data-stu-id="93579-266">Select **Check connection** to validate access to the configured application.</span></span>
11. <span data-ttu-id="93579-267">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="93579-267">Select **Close**.</span></span>

<span data-ttu-id="93579-268">Dopo il completamento di questa procedura e la convalida della connessione, i dettagli relativi a tenant e versione per l'applicazione configurata verranno aggiornati nella griglia corrente.</span><span class="sxs-lookup"><span data-stu-id="93579-268">After you complete this procedure and validation of the connection succeeds, the version and tenant details for the configured application will be updated in the current grid.</span></span>

### <a name="review-the-existing-model-mapping-configuration"></a><span data-ttu-id="93579-269">Esaminare la configurazione del mapping di modello esistente</span><span class="sxs-lookup"><span data-stu-id="93579-269">Review the existing model mapping configuration</span></span>

1. <span data-ttu-id="93579-270">Andare a **Tutte le aree di lavoro \> Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="93579-270">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="93579-271">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="93579-271">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="93579-272">Nella struttura, selezionare **Modello del commercio estero \> Mapping del commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="93579-272">In the tree, select **Foreign trade model \> Foreign trade mapping**.</span></span>
4. <span data-ttu-id="93579-273">Selezionare la scheda dettaglio **Prerequisiti**.</span><span class="sxs-lookup"><span data-stu-id="93579-273">Select the **Prerequisites** FasTab.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93579-274">Attualmente, questo mapping fa riferimento alla configurazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="93579-274">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="93579-275">I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione di questo mapping di modello.</span><span class="sxs-lookup"><span data-stu-id="93579-275">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

4. <span data-ttu-id="93579-276">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-276">Select **Designer**.</span></span>
5. <span data-ttu-id="93579-277">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-277">Select **Designer**.</span></span>
6. <span data-ttu-id="93579-278">Nella struttura selezionare **Dynamics 365 for Operations \> Record di tabella**.</span><span class="sxs-lookup"><span data-stu-id="93579-278">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
7. <span data-ttu-id="93579-279">Selezionare **Aggiungi radice**.</span><span class="sxs-lookup"><span data-stu-id="93579-279">Select **Add root**.</span></span>
8. <span data-ttu-id="93579-280">Nel campo **Tabella** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="93579-280">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93579-281">Attualmente, questo mapping fa riferimento alla configurazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="93579-281">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="93579-282">I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione di questo mapping di modello.</span><span class="sxs-lookup"><span data-stu-id="93579-282">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

9. <span data-ttu-id="93579-283">Selezionare **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="93579-283">Select **Cancel**.</span></span>

### <a name="assign-the-connected-application-to-a-model-mapping"></a><span data-ttu-id="93579-284">Assegnare l'applicazione connessa a un mapping di modello</span><span class="sxs-lookup"><span data-stu-id="93579-284">Assign the connected application to a model mapping</span></span>

1. <span data-ttu-id="93579-285">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="93579-285">Select **Edit**.</span></span>
2. <span data-ttu-id="93579-286">Nel campo **Applicazione connessa**, selezionare l'applicazione **MiaAppConnessa**.</span><span class="sxs-lookup"><span data-stu-id="93579-286">In the **Connected application field**, select the **MyConnectedApp** application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93579-287">Questo mapping fa riferimento ai metadati dell'applicazione connessa selezionata.</span><span class="sxs-lookup"><span data-stu-id="93579-287">This mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="93579-288">Se un mapping fa riferimento contemporaneamente alla configurazione dei metadati e all'applicazione connessa, verranno utilizzati i metadati dell'applicazione connessa.</span><span class="sxs-lookup"><span data-stu-id="93579-288">If a mapping refers to the metadata configuration and the connected application at the same time, the metadata of the connected application will be used.</span></span>

3. <span data-ttu-id="93579-289">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-289">Select **Designer**.</span></span>
4. <span data-ttu-id="93579-290">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="93579-290">Select **Designer**.</span></span>
5. <span data-ttu-id="93579-291">Nella struttura selezionare **Dynamics 365 for Operations \> Record di tabella**.</span><span class="sxs-lookup"><span data-stu-id="93579-291">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
6. <span data-ttu-id="93579-292">Selezionare **Aggiungi radice**.</span><span class="sxs-lookup"><span data-stu-id="93579-292">Select **Add root**.</span></span>
7. <span data-ttu-id="93579-293">Nel campo **Tabella** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="93579-293">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93579-294">A questo punto, sono disponibili più di due tabelle dell'applicazione in quanto questo mapping utilizza tutti i metadati dell'applicazione connessa che è stata assegnata agli stessi.</span><span class="sxs-lookup"><span data-stu-id="93579-294">At this point, more than two application tables are offered, because this mapping uses all the metadata of the connected application that has been assigned to it.</span></span>

8. <span data-ttu-id="93579-295">Selezionare **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="93579-295">Select **Cancel**.</span></span>
9. <span data-ttu-id="93579-296">Selezionare **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="93579-296">Select **Validate**.</span></span>

<span data-ttu-id="93579-297">A questo punto sono stati associati gli elementi del modello di dati agli articoli delle origini dati descritte utilizzando i dettagli dei metadati dell'applicazione connessa che è stata assegnata a questo mapping.</span><span class="sxs-lookup"><span data-stu-id="93579-297">You've now bound elements of the data model to items of the data sources that are described by using details of the metadata of the connected application that has been assigned to this mapping.</span></span>

<span data-ttu-id="93579-298">Quando è necessario valutare questo mapping di modello utilizzando i metadati di un'altra versione dell'applicazione, registrare un'altra applicazione connessa, assegnarla a questo mapping di modello e convalidarla in base ai nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="93579-298">When you must evaluate this model mapping by using the metadata of a different version of the application, register another connected application, assign it to this model mapping, and validate it against the new metadata.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93579-299">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="93579-299">Additional resources</span></span>

<span data-ttu-id="93579-300">In alternativa, è possibile riprodurre la guida attività **Preparare i metadati dell'applicazione da utilizzare in RCS** in Finance and Operations nonché le guide attività **Accedere ai metadati dell'applicazione utilizzando una configurazione ER** e **Accedere ai metadati dell'applicazione utilizzando applicazioni connesse** in RCS.</span><span class="sxs-lookup"><span data-stu-id="93579-300">Alternatively, you can play the **Prepare application metadata that can be used in RCS** task guide in Finance and Operationsas as well as the **Access application metadata by using an ER configuration** and **Access application metadata by using connected applications** task guides in RCS.</span></span> <span data-ttu-id="93579-301">Queste guide attività possono essere scaricate dalla pagina [Guide attività per la creazione di report elettronici per Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739).</span><span class="sxs-lookup"><span data-stu-id="93579-301">These task guides can be downloaded from the [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page.</span></span>