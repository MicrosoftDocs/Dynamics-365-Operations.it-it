---
title: Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services
description: Questo argomento illustra come scaricare le configurazioni per la creazione di report elettronici da Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 14f0f2b1a4d63101d432b1361379c61a70ac9345
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271185"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="16f7c-103">Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="16f7c-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16f7c-104">Questo argomento spiega come scaricare la versione più recente di [Configurazioni per la creazione di report elettronici](general-electronic-reporting.md#Configuration) dalla [libreria di risorse condivise](../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="16f7c-104">This topic explains how to download the newest version of [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the [Shared asset library](../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16f7c-105">L'utilizzo di LCS come repository di archiviazione per le configurazioni ER è stato [deprecato](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="16f7c-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="16f7c-106">Per ulteriori informazioni vedi [Regulatory Configuration Service (RCS) – Deprecazione dell'archiviazione di Lifecycle Services (LCS)](../../../finance/localizations/rcs-lcs-repo-dep-faq.md)</span><span class="sxs-lookup"><span data-stu-id="16f7c-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

1. <span data-ttu-id="16f7c-107">Accedere all'applicazione utilizzando uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="16f7c-107">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="16f7c-108">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="16f7c-108">Electronic reporting developer</span></span>
    - <span data-ttu-id="16f7c-109">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="16f7c-109">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="16f7c-110">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="16f7c-110">System administrator</span></span>

2. <span data-ttu-id="16f7c-111">Andare a **Amministrazione organizzazione** &gt; **Aree di lavoro** &gt; **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="16f7c-111">Go to **Organization administration** &gt; **Workspaces** &gt; **Electronic reporting**.</span></span>
3. <span data-ttu-id="16f7c-112">Nella sezione **Provider di configurazione** selezionare il riquadro **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="16f7c-112">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4. <span data-ttu-id="16f7c-113">Nel riquadro **Microsoft** selezionare **Archivi**.</span><span class="sxs-lookup"><span data-stu-id="16f7c-113">On the **Microsoft** tile, select **Repositories**.</span></span>

    <span data-ttu-id="16f7c-114">[![Riquadro Microsoft nella pagina delle configurazioni di localizzazione](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="16f7c-114">[![Microsoft tile on the Localization configurations page](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>

5. <span data-ttu-id="16f7c-115">Nella pagina **Archivi di configurazioni** selezionare nella griglia l'archivio esistente di tipo **LCS**.</span><span class="sxs-lookup"><span data-stu-id="16f7c-115">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="16f7c-116">Se questo archivio non viene visualizzato nella griglia, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="16f7c-116">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="16f7c-117">Selezionare **Aggiungi** per aggiungere un archivio.</span><span class="sxs-lookup"><span data-stu-id="16f7c-117">Select **Add** to add a repository.</span></span>
    2. <span data-ttu-id="16f7c-118">Selezionare **LCS** come tipo di archivio.</span><span class="sxs-lookup"><span data-stu-id="16f7c-118">Select **LCS** as the repository type.</span></span>
    3. <span data-ttu-id="16f7c-119">Selezionare **Crea archivio**.</span><span class="sxs-lookup"><span data-stu-id="16f7c-119">Select **Create repository**.</span></span>
    4. <span data-ttu-id="16f7c-120">Se viene richiesta l'autorizzazione, seguire le istruzioni sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="16f7c-120">If you're prompted about authorization, follow the on-screen instructions.</span></span>
    5. <span data-ttu-id="16f7c-121">Immettere un nome e una descrizione per l'archivio.</span><span class="sxs-lookup"><span data-stu-id="16f7c-121">Enter a name and description for the repository.</span></span>
    6. <span data-ttu-id="16f7c-122">Selezionare **OK** per confermare la nuova voce di archivio.</span><span class="sxs-lookup"><span data-stu-id="16f7c-122">Select **OK** to confirm the new repository entry.</span></span>
    7. <span data-ttu-id="16f7c-123">Nella griglia, selezionare il nuovo archivio di tipo **LCS**.</span><span class="sxs-lookup"><span data-stu-id="16f7c-123">In the grid, select the new repository of the **LCS** type.</span></span>

6. <span data-ttu-id="16f7c-124">Selezionare **Apri** per visualizzare l'elenco delle configurazioni ER per l'archivio selezionato.</span><span class="sxs-lookup"><span data-stu-id="16f7c-124">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    <span data-ttu-id="16f7c-125">[![Pagina Archivi di configurazione](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="16f7c-125">[![Configuration repositories page](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>

    > [!TIP]
    > <span data-ttu-id="16f7c-126">Se si verificano problemi con l'accesso all'archivio LCS per scaricare le configurazioni dalla libreria di risorse condivise in LCS, è possibile scaricare le configurazioni dal [repository globale](er-download-configurations-global-repo.md).</span><span class="sxs-lookup"><span data-stu-id="16f7c-126">If you have trouble accessing the LCS repository to download configurations from the Shared asset library in LCS, you can download configurations from the [Global repository](er-download-configurations-global-repo.md) instead.</span></span>

7. <span data-ttu-id="16f7c-127">Nella struttura di configurazioni nel riquadro sinistro, selezionare la configurazione per la creazione di report elettronici desiderata.</span><span class="sxs-lookup"><span data-stu-id="16f7c-127">In the configurations tree in the left pane, select the required ER configuration.</span></span>
8. <span data-ttu-id="16f7c-128">Nella scheda dettaglio **Versioni** selezionare la versione richiesta della configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="16f7c-128">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9. <span data-ttu-id="16f7c-129">Selezionare **Importa** per scaricare la versione selezionata da LCS nell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="16f7c-129">Select **Import** to download the selected version from LCS to the current instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="16f7c-130">Il pulsante **Importa** non è disponibile per le versioni di configurazione di creazione di report elettronici già presenti nell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="16f7c-130">The **Import** button is unavailable for ER configuration versions that are already present in the current instance.</span></span>

    <span data-ttu-id="16f7c-131">[![Configurazione della pagina dell'archivio](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="16f7c-131">[![Configuration repository page](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

> [!NOTE]
> <span data-ttu-id="16f7c-132">A seconda delle impostazioni ER, le configurazioni vengono convalidate dopo l'importazione.</span><span class="sxs-lookup"><span data-stu-id="16f7c-132">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="16f7c-133">È possibile ricevere una notifica per tutti i problemi di incoerenza rilevati.</span><span class="sxs-lookup"><span data-stu-id="16f7c-133">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="16f7c-134">Risolvere i problemi prima di utilizzare la versione di configurazione importata.</span><span class="sxs-lookup"><span data-stu-id="16f7c-134">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="16f7c-135">Per ulteriori informazioni, vedere l'elenco di argomenti correlati per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="16f7c-135">For more information, see the list of related topics for this topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="16f7c-136">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="16f7c-136">Additional resources</span></span>

[<span data-ttu-id="16f7c-137">Panoramica dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="16f7c-137">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="16f7c-138">Scaricare configurazioni ER dall'archivio globale del servizio di configurazione</span><span class="sxs-lookup"><span data-stu-id="16f7c-138">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
