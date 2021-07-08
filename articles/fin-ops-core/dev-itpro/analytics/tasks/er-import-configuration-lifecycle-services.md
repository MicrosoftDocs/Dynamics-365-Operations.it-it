---
title: Importare una configurazione da Lifecycle Services
description: Questo argomento descrive come importare una nuova versione di una configurazione di creazione di report elettronici (ER) da Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b58ecb8a7d6f52631dbca7642a4acbcf6ff895a3
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270839"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="c2568-103">Importare una configurazione da Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="c2568-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c2568-104">In questo argomento viene illustrato come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per l'importazione di una [configurazione per la creazione di report elettronici (ER)](../general-electronic-reporting.md#Configuration) dalla [raccolta di cespiti a livello di progetto](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c2568-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2568-105">L'utilizzo di LCS come repository di archiviazione per le configurazioni ER è stato [deprecato](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="c2568-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="c2568-106">Per ulteriori informazioni vedi [Regulatory Configuration Service (RCS) – Deprecazione dell'archiviazione di Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md)</span><span class="sxs-lookup"><span data-stu-id="c2568-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="c2568-107">In questo esempio si dovrà selezionare la versione desiderata della configurazione ER e importarla per una società di esempio denominata Litware, Inc. Queste operazioni possono essere completate in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="c2568-107">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="c2568-108">Per completare questi passaggi, è necessario completare i passaggi della procedura [Caricare una configurazione ER in Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="c2568-108">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="c2568-109">È richiesto anche l'accesso a LCS.</span><span class="sxs-lookup"><span data-stu-id="c2568-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="c2568-110">Accedere all'applicazione utilizzando uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="c2568-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="c2568-111">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="c2568-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="c2568-112">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="c2568-112">System administrator</span></span>

2. <span data-ttu-id="c2568-113">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="c2568-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="c2568-114">Selezionare **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="c2568-114">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="c2568-115">Assicurarsi che l'utente Dynamics 365 Finance corrente sia membro del progetto LCS che contiene la raccolta cespiti a cui l'utente vuole [accedere](../../lifecycle-services/asset-library.md#asset-library-support) per importare le configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="c2568-115">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="c2568-116">Non è possibile accedere a un progetto LCS da un archivio ER che rappresenta un dominio diverso dal dominio utilizzato in Finance.</span><span class="sxs-lookup"><span data-stu-id="c2568-116">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="c2568-117">Se si tenta, verrà visualizzato un elenco vuoto di progetti LCS e non è possibile importare le configurazioni ER dalla raccolta di cespiti a livello di progetto in LCS.</span><span class="sxs-lookup"><span data-stu-id="c2568-117">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="c2568-118">Per accedere alle raccolte di cespiti a livello di progetto da un archivio ER utilizzato per importare le configurazioni ER, accedere a Finance utilizzando le credenziali di un utente che appartiene al tenant (dominio) per cui è stata fornita l'istanza di Finance corrente.</span><span class="sxs-lookup"><span data-stu-id="c2568-118">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="c2568-119">Eliminare una versione condivisa di una configurazione del modello dati</span><span class="sxs-lookup"><span data-stu-id="c2568-119">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="c2568-120">Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Configurazione del modello di esempio**.</span><span class="sxs-lookup"><span data-stu-id="c2568-120">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="c2568-121">La prima versione di una configurazione del modello dati di esempio è stata creata e pubblicata in LCS quando è stata completata la procedura in [Caricare una configurazione in Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="c2568-121">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="c2568-122">In questa procedura verrà eliminata questa versione della configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="c2568-122">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="c2568-123">Quindi quella versione verrà importata da LCS più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c2568-123">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="c2568-124">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c2568-124">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c2568-125">Per questo esempio, selezionare la versione della configurazione con stato **Condiviso**.</span><span class="sxs-lookup"><span data-stu-id="c2568-125">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="c2568-126">Questo stato indica che la configurazione è stata pubblicata in LCS.</span><span class="sxs-lookup"><span data-stu-id="c2568-126">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="c2568-127">Selezionare **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="c2568-127">Select **Change status**.</span></span>
4. <span data-ttu-id="c2568-128">Selezionare **Interrotto**.</span><span class="sxs-lookup"><span data-stu-id="c2568-128">Select **Discontinue**.</span></span>

    <span data-ttu-id="c2568-129">Modificando lo stato della versione selezionata da **Condiviso** a **Interrotto** si rende la versione disponibile per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="c2568-129">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="c2568-130">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2568-130">Select **OK**.</span></span>
6. <span data-ttu-id="c2568-131">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c2568-131">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c2568-132">Per questo esempio, selezionare la versione della configurazione con stato **Interrotto**.</span><span class="sxs-lookup"><span data-stu-id="c2568-132">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="c2568-133">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="c2568-133">Select **Delete**.</span></span>
8. <span data-ttu-id="c2568-134">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c2568-134">Select **Yes**.</span></span>

    <span data-ttu-id="c2568-135">Notare che solo la versione bozza 2 della configurazione selezionata del modello dati è ora disponibile.</span><span class="sxs-lookup"><span data-stu-id="c2568-135">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="c2568-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c2568-136">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="c2568-137">Importare una versione condivisa di una configurazione del modello dati da LCS</span><span class="sxs-lookup"><span data-stu-id="c2568-137">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="c2568-138">Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="c2568-138">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="c2568-139">Nella sezione **Provider di configurazione** selezionare il riquadro **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="c2568-139">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="c2568-140">Nel riquadro **Litware, Inc.** selezionare **Archivi**.</span><span class="sxs-lookup"><span data-stu-id="c2568-140">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="c2568-141">Ora è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c2568-141">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="c2568-142">Selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="c2568-142">Select **Open**.</span></span>

    <span data-ttu-id="c2568-143">Per questo esempio, selezionare il record dell'archivio **LCS** e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="c2568-143">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="c2568-144">È necessario disporre dell'[accesso](#accessconditions) al progetto LCS e alla raccolta di cespiti a cui si accede dal repository ER selezionato.</span><span class="sxs-lookup"><span data-stu-id="c2568-144">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="c2568-145">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c2568-145">In the list, mark the selected row.</span></span>

    <span data-ttu-id="c2568-146">Per questo esempio, selezionare la prima versione della **Configurazione del modello di esempio** nell'elenco delle versioni.</span><span class="sxs-lookup"><span data-stu-id="c2568-146">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="c2568-147">Selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="c2568-147">Select **Import**.</span></span>
7. <span data-ttu-id="c2568-148">Selezionare **Sì** per confermare l'importazione della versione selezionata da LCS.</span><span class="sxs-lookup"><span data-stu-id="c2568-148">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="c2568-149">Un messaggio informativo conferma che la versione selezionata è stata importata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c2568-149">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="c2568-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c2568-150">Close the page.</span></span>
9. <span data-ttu-id="c2568-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c2568-151">Close the page.</span></span>
10. <span data-ttu-id="c2568-152">Selezionare **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="c2568-152">Select **Configurations**.</span></span>
11. <span data-ttu-id="c2568-153">Nella struttura ad albero selezionare **Configurazione del modello di esempio**.</span><span class="sxs-lookup"><span data-stu-id="c2568-153">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="c2568-154">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c2568-154">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c2568-155">Per questo esempio, selezionare la versione della configurazione con stato **Condiviso**.</span><span class="sxs-lookup"><span data-stu-id="c2568-155">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="c2568-156">Notare che anche la versione condivisa 1 della configurazione selezionata del modello dati è ora disponibile.</span><span class="sxs-lookup"><span data-stu-id="c2568-156">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
