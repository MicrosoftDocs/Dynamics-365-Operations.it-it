---
title: Importare una configurazione da Lifecycle Services
description: Questo argomento descrive come importare una nuova versione di una configurazione di creazione di report elettronici (ER) da Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 09/14/2020
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
ms.openlocfilehash: 674d0dc02b4a53e455a15a06fdb7f24ca3036ba3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752366"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="3867e-103">Importare una configurazione da Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="3867e-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3867e-104">In questo argomento viene illustrato come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per l'importazione di una [configurazione per la creazione di report elettronici (ER)](../general-electronic-reporting.md#Configuration) dalla [raccolta di cespiti a livello di progetto](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="3867e-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="3867e-105">In questo esempio si dovrà selezionare la versione desiderata della configurazione ER e importarla per una società di esempio denominata Litware, Inc. Queste operazioni possono essere completate in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="3867e-105">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="3867e-106">Per completare questi passaggi, è necessario completare i passaggi della procedura [Caricare una configurazione ER in Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="3867e-106">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="3867e-107">È richiesto anche l'accesso a LCS.</span><span class="sxs-lookup"><span data-stu-id="3867e-107">Access to LCS is also required.</span></span>

1. <span data-ttu-id="3867e-108">Accedere all'applicazione utilizzando uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="3867e-108">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="3867e-109">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="3867e-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="3867e-110">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="3867e-110">System administrator</span></span>

2. <span data-ttu-id="3867e-111">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="3867e-111">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="3867e-112">Selezionare **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="3867e-112">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="3867e-113">Assicurarsi che l'utente Dynamics 365 Finance corrente sia membro del progetto LCS che contiene la raccolta cespiti a cui l'utente vuole [accedere](../../lifecycle-services/asset-library.md#asset-library-support) per importare le configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="3867e-113">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="3867e-114">Non è possibile accedere a un progetto LCS da un archivio ER che rappresenta un dominio diverso dal dominio utilizzato in Finance.</span><span class="sxs-lookup"><span data-stu-id="3867e-114">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="3867e-115">Se si tenta, verrà visualizzato un elenco vuoto di progetti LCS e non è possibile importare le configurazioni ER dalla raccolta di cespiti a livello di progetto in LCS.</span><span class="sxs-lookup"><span data-stu-id="3867e-115">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="3867e-116">Per accedere alle raccolte di cespiti a livello di progetto da un archivio ER utilizzato per importare le configurazioni ER, accedere a Finance utilizzando le credenziali di un utente che appartiene al tenant (dominio) per cui è stata fornita l'istanza di Finance corrente.</span><span class="sxs-lookup"><span data-stu-id="3867e-116">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="3867e-117">Eliminare una versione condivisa di una configurazione del modello dati</span><span class="sxs-lookup"><span data-stu-id="3867e-117">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="3867e-118">Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Configurazione del modello di esempio**.</span><span class="sxs-lookup"><span data-stu-id="3867e-118">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="3867e-119">La prima versione di una configurazione del modello dati di esempio è stata creata e pubblicata in LCS quando è stata completata la procedura in [Caricare una configurazione in Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="3867e-119">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="3867e-120">In questa procedura verrà eliminata questa versione della configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="3867e-120">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="3867e-121">Quindi quella versione verrà importata da LCS più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3867e-121">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="3867e-122">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="3867e-122">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="3867e-123">Per questo esempio, selezionare la versione della configurazione con stato **Condiviso**.</span><span class="sxs-lookup"><span data-stu-id="3867e-123">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="3867e-124">Questo stato indica che la configurazione è stata pubblicata in LCS.</span><span class="sxs-lookup"><span data-stu-id="3867e-124">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="3867e-125">Selezionare **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="3867e-125">Select **Change status**.</span></span>
4. <span data-ttu-id="3867e-126">Selezionare **Interrotto**.</span><span class="sxs-lookup"><span data-stu-id="3867e-126">Select **Discontinue**.</span></span>

    <span data-ttu-id="3867e-127">Modificando lo stato della versione selezionata da **Condiviso** a **Interrotto** si rende la versione disponibile per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="3867e-127">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="3867e-128">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3867e-128">Select **OK**.</span></span>
6. <span data-ttu-id="3867e-129">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="3867e-129">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="3867e-130">Per questo esempio, selezionare la versione della configurazione con stato **Interrotto**.</span><span class="sxs-lookup"><span data-stu-id="3867e-130">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="3867e-131">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3867e-131">Select **Delete**.</span></span>
8. <span data-ttu-id="3867e-132">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3867e-132">Select **Yes**.</span></span>

    <span data-ttu-id="3867e-133">Notare che solo la versione bozza 2 della configurazione selezionata del modello dati è ora disponibile.</span><span class="sxs-lookup"><span data-stu-id="3867e-133">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="3867e-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3867e-134">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="3867e-135">Importare una versione condivisa di una configurazione del modello dati da LCS</span><span class="sxs-lookup"><span data-stu-id="3867e-135">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="3867e-136">Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="3867e-136">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="3867e-137">Nella sezione **Provider di configurazione** selezionare il riquadro **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="3867e-137">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="3867e-138">Nel riquadro **Litware, Inc.** selezionare **Archivi**.</span><span class="sxs-lookup"><span data-stu-id="3867e-138">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="3867e-139">Ora è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="3867e-139">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="3867e-140">Selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3867e-140">Select **Open**.</span></span>

    <span data-ttu-id="3867e-141">Per questo esempio, selezionare il record dell'archivio **LCS** e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="3867e-141">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="3867e-142">È necessario disporre dell'[accesso](#accessconditions) al progetto LCS e alla raccolta di cespiti a cui si accede dal repository ER selezionato.</span><span class="sxs-lookup"><span data-stu-id="3867e-142">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="3867e-143">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3867e-143">In the list, mark the selected row.</span></span>

    <span data-ttu-id="3867e-144">Per questo esempio, selezionare la prima versione della **Configurazione del modello di esempio** nell'elenco delle versioni.</span><span class="sxs-lookup"><span data-stu-id="3867e-144">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="3867e-145">Selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="3867e-145">Select **Import**.</span></span>
7. <span data-ttu-id="3867e-146">Selezionare **Sì** per confermare l'importazione della versione selezionata da LCS.</span><span class="sxs-lookup"><span data-stu-id="3867e-146">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="3867e-147">Un messaggio informativo conferma che la versione selezionata è stata importata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3867e-147">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="3867e-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3867e-148">Close the page.</span></span>
9. <span data-ttu-id="3867e-149">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3867e-149">Close the page.</span></span>
10. <span data-ttu-id="3867e-150">Selezionare **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="3867e-150">Select **Configurations**.</span></span>
11. <span data-ttu-id="3867e-151">Nella struttura ad albero selezionare **Configurazione del modello di esempio**.</span><span class="sxs-lookup"><span data-stu-id="3867e-151">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="3867e-152">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="3867e-152">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="3867e-153">Per questo esempio, selezionare la versione della configurazione con stato **Condiviso**.</span><span class="sxs-lookup"><span data-stu-id="3867e-153">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="3867e-154">Notare che anche la versione condivisa 1 della configurazione selezionata del modello dati è ora disponibile.</span><span class="sxs-lookup"><span data-stu-id="3867e-154">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]