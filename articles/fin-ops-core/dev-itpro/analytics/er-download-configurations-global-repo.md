---
title: Scaricare configurazioni ER dall'archivio globale del servizio di configurazione
description: In questo argomento viene descritto come scaricare le configurazioni per la creazione di report elettronici (ER) dall'archivio globale del servizio di configurazione.
author: NickSelin
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ed31cdee74c9db26ba76ed263b5e0578cd04bc3d
ms.sourcegitcommit: 7816902b59aa61d9183d54b50a86e282661e3971
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "3421704"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a><span data-ttu-id="d073a-103">Scaricare configurazioni ER dall'archivio globale del servizio di configurazione</span><span class="sxs-lookup"><span data-stu-id="d073a-103">Download ER configurations from the Global repository of Configuration service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d073a-104">In questo argomento viene descritto come scaricare le [configurazioni per la creazione di report elettronici (ER)](general-electronic-reporting.md#Configuration) dall'archivio globale del servizio di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d073a-104">This topic explains how to download [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the Global repository of configuration service.</span></span> <span data-ttu-id="d073a-105">Per ulteriori informazioni, vedere [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, Servizio di configurazione](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="d073a-105">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="open-configurations-repository"></a><span data-ttu-id="d073a-106">Aprire l'archivio delle configurazioni</span><span class="sxs-lookup"><span data-stu-id="d073a-106">Open configurations repository</span></span>

1. <span data-ttu-id="d073a-107">Accedere all'applicazione Dynamics 365 Finance utilizzando uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="d073a-107">Sign in to the Dynamics 365 Finance application using one of the following roles:</span></span>

    - <span data-ttu-id="d073a-108">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="d073a-108">Electronic reporting developer</span></span>
    - <span data-ttu-id="d073a-109">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="d073a-109">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="d073a-110">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="d073a-110">System administrator</span></span>

2. <span data-ttu-id="d073a-111">Andare ad **Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="d073a-111">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="d073a-112">Nella sezione **Provider di configurazione** selezionare il riquadro **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d073a-112">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
3. <span data-ttu-id="d073a-113">Nel riquadro **Microsoft** selezionare **Archivi**.</span><span class="sxs-lookup"><span data-stu-id="d073a-113">On the **Microsoft** tile, select **Repositories**.</span></span>

    ![Area di lavoro Creazione di report elettronici](./media/er-download-configurations-global-repo-er-workspace.png)

4. <span data-ttu-id="d073a-115">Nella pagina **Archivi di configurazioni** selezionare nella griglia l'archivio esistente di tipo **Globale**.</span><span class="sxs-lookup"><span data-stu-id="d073a-115">On the **Configuration repositories** page, in the grid, select the existing repository of the **Global** type.</span></span> <span data-ttu-id="d073a-116">Se questo archivio non viene visualizzato nella griglia, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="d073a-116">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="d073a-117">Selezionare **Aggiungi** per aggiungere un nuovo archivio.</span><span class="sxs-lookup"><span data-stu-id="d073a-117">Select **Add** to add a new repository.</span></span>
    2. <span data-ttu-id="d073a-118">Selezionare **Globale** come tipo di archivio, quindi selezionare **Crea archivio**.</span><span class="sxs-lookup"><span data-stu-id="d073a-118">Select **Global** as the repository type, and then select **Create repository**.</span></span>
    3. <span data-ttu-id="d073a-119">Se richiesto, seguire le istruzioni di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="d073a-119">If prompted, follow the authorization instructions.</span></span>
    4. <span data-ttu-id="d073a-120">Immettere un nome e una descrizione per l'archivio e quindi selezionare **OK** per confermare il nuovo archivio.</span><span class="sxs-lookup"><span data-stu-id="d073a-120">Enter a name and description for the repository and then select **OK** to confirm the new repository entry.</span></span>
    5. <span data-ttu-id="d073a-121">Nella griglia, selezionare il nuovo archivio di tipo **Globale**.</span><span class="sxs-lookup"><span data-stu-id="d073a-121">In the grid, select the new repository of the **Global** type.</span></span>

5. <span data-ttu-id="d073a-122">Selezionare **Apri** per visualizzare l'elenco delle configurazioni ER per l'archivio selezionato.</span><span class="sxs-lookup"><span data-stu-id="d073a-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    ![Pagina Archivi di configurazione](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a><span data-ttu-id="d073a-124">Importare un'unica configurazione</span><span class="sxs-lookup"><span data-stu-id="d073a-124">Import a single configuration</span></span>

1. <span data-ttu-id="d073a-125">Nella pagina **Archivi di configurazioni**, nella struttura delle configurazioni, selezionare la configurazione ER desiderata.</span><span class="sxs-lookup"><span data-stu-id="d073a-125">On the **Configuration repositories** page, in the configurations tree, select the ER configuration that you want.</span></span>
2. <span data-ttu-id="d073a-126">Nella scheda dettaglio **Versioni** selezionare la versione richiesta della configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="d073a-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
3. <span data-ttu-id="d073a-127">Selezionare **Importa** per scaricare la versione selezionata dall'archivio Globale nell'istanza corrente di Finance.</span><span class="sxs-lookup"><span data-stu-id="d073a-127">Select **Import** to download the selected version from Global repository to the current Finance instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d073a-128">Il pulsante **Importa** non è disponibile per le versioni di configurazione ER già presenti nell'istanza corrente di Finance.</span><span class="sxs-lookup"><span data-stu-id="d073a-128">The **Import** button is unavailable for ER configuration versions that are already present in the current Finance instance.</span></span>

    ![Configurazione della pagina dell'archivio](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a><span data-ttu-id="d073a-130">Importare configurazioni filtrate</span><span class="sxs-lookup"><span data-stu-id="d073a-130">Import filtered configurations</span></span>

1. <span data-ttu-id="d073a-131">Nella pagina **Archivi di configurazione**, nella struttura delle configurazioni, espandere la Scheda dettaglio **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="d073a-131">On the **Configuration repositories** page, in the configurations tree, expand the **Filter** FastTab.</span></span>
2. <span data-ttu-id="d073a-132">Nella griglia **Tag**, aggiungere eventuali tag necessari.</span><span class="sxs-lookup"><span data-stu-id="d073a-132">In the **Tags** grid, add any tags that are needed.</span></span>
3. <span data-ttu-id="d073a-133">Nel campo **Applicabilità paese**, selezionare i codici paese appropriati, quindi selezionare **Applica filtro**.</span><span class="sxs-lookup"><span data-stu-id="d073a-133">In the **Country/region applicability** field, select the appropriate country/region codes, and then select  **Apply filter**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d073a-134">La Scheda dettaglio **Configurazioni** mostra tutte le configurazioni che soddisfano le condizioni di selezione specificate.</span><span class="sxs-lookup"><span data-stu-id="d073a-134">The **Configurations** FastTab shows all the configurations that satisfy the specified selection conditions.</span></span>

4. <span data-ttu-id="d073a-135">Nella Scheda dettaglio **Configurazioni**, selezionare **Importa** per scaricare le configurazioni filtrate dall'archivio globale nell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="d073a-135">On the **Configurations** FastTab, select **Import** to download the filtered configurations from the Global repository to the current instance.</span></span>
5. <span data-ttu-id="d073a-136">Nella Scheda dettaglio **Configurazioni**, selezionare **Reimposta filtro** per ripulire le condizioni di selezione specificate.</span><span class="sxs-lookup"><span data-stu-id="d073a-136">On the **Configurations** FastTab, select **Reset filter** to clean up the specified selection conditions.</span></span>

    ![Configurazione della pagina dell'archivio](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> <span data-ttu-id="d073a-138">A seconda delle impostazioni ER, le configurazioni vengono convalidate dopo l'importazione.</span><span class="sxs-lookup"><span data-stu-id="d073a-138">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="d073a-139">È possibile ricevere una notifica per tutti i problemi di incoerenza rilevati.</span><span class="sxs-lookup"><span data-stu-id="d073a-139">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="d073a-140">Prima di utilizzare la versione di configurazione importata, è necessario risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="d073a-140">Before you can use the imported configuration version, you must resolve the issues.</span></span> <span data-ttu-id="d073a-141">Per ulteriori informazioni, vedere l'elenco delle risorse correlate per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d073a-141">For more information, see the list of related resources for this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="d073a-142">Le configurazioni ER possono essere configurate come dipendenti da altre configurazioni.</span><span class="sxs-lookup"><span data-stu-id="d073a-142">ER configurations can be configured as being dependent on other configurations.</span></span> <span data-ttu-id="d073a-143">Pertanto, insieme a una configurazione selezionata, altre configurazioni potrebbero essere importate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d073a-143">Therefore, along with a selected configuration, other configurations might be automatically imported.</span></span> <span data-ttu-id="d073a-144">Per ulteriori informazioni sulle dipendenze delle configurazioni, vedere [Definire la dipendenza delle configurazioni ER in altri componenti](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span><span class="sxs-lookup"><span data-stu-id="d073a-144">For more about configuration dependencies, see [Define the dependency of ER configurations on other components](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d073a-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d073a-145">Additional resources</span></span>

[<span data-ttu-id="d073a-146">Panoramica dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="d073a-146">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)