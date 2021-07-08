---
title: Caricare una configurazione in Lifecycle Services
description: Questo argomento illustra come creare una nuova configurazione per la creazione di report elettronici e caricarla in Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41a8fcf2592bde4901aba703e0cd124b1155dac6
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270561"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="21f7f-103">Caricare una configurazione in Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="21f7f-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="21f7f-104">In questo argomento viene illustrato come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova [configurazione per la creazione di report elettronici (ER)](../general-electronic-reporting.md#Configuration) e caricarla nella [raccolta di cespiti a livello di progetto](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="21f7f-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21f7f-105">L'utilizzo di LCS come repository di archiviazione per le configurazioni ER è stato [deprecato](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="21f7f-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="21f7f-106">Per ulteriori informazioni vedi [Regulatory Configuration Service (RCS) – Deprecazione dell'archiviazione di Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md)</span><span class="sxs-lookup"><span data-stu-id="21f7f-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="21f7f-107">In questo esempio verrà creata una configurazione che sarà caricata in LCS per la società di esempio denominata Litware, Inc. Queste operazioni possono essere completate in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="21f7f-107">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="21f7f-108">Per completare questi passaggi, è necessario dapprima completare i passaggi in [Creare provider di configurazione e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="21f7f-108">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="21f7f-109">È richiesto anche l'accesso a LCS.</span><span class="sxs-lookup"><span data-stu-id="21f7f-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="21f7f-110">Accedere all'applicazione utilizzando uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="21f7f-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="21f7f-111">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="21f7f-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="21f7f-112">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="21f7f-112">System administrator</span></span>

2. <span data-ttu-id="21f7f-113">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="21f7f-114">Selezionare **Litware, Inc.** e impostarlo come **attivo**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-114">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="21f7f-115">Selezionare **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-115">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="21f7f-116">Assicurarsi che l'utente Dynamics 365 Finance corrente sia membro del progetto LCS che contiene la [raccolta cespiti](../../lifecycle-services/asset-library.md#asset-library-support) che viene utilizzata per importare le configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="21f7f-116">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="21f7f-117">Non è possibile accedere a un progetto LCS da un archivio ER che rappresenta un dominio diverso dal dominio utilizzato in Finance.</span><span class="sxs-lookup"><span data-stu-id="21f7f-117">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="21f7f-118">Se si tenta, verrà visualizzato un elenco vuoto di progetti LCS e non è possibile importare le configurazioni ER dalla raccolta di cespiti a livello di progetto in LCS.</span><span class="sxs-lookup"><span data-stu-id="21f7f-118">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="21f7f-119">Per accedere alle raccolte di cespiti a livello di progetto da un archivio ER utilizzato per importare le configurazioni ER, accedere a Finance utilizzando le credenziali di un utente che appartiene al tenant (dominio) per cui è stata fornita l'istanza di Finance corrente.</span><span class="sxs-lookup"><span data-stu-id="21f7f-119">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="21f7f-120">Creare una nuova configurazione del modello di dati</span><span class="sxs-lookup"><span data-stu-id="21f7f-120">Create a new data model configuration</span></span>

1. <span data-ttu-id="21f7f-121">Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-121">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="21f7f-122">Nella pagina **Configurazioni** selezionare **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="21f7f-122">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="21f7f-123">In questo esempio verrà creata una configurazione che contiene un modello dati di esempio per i documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="21f7f-123">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="21f7f-124">Questa configurazione del modello dati verrà caricata successivamente in LCS.</span><span class="sxs-lookup"><span data-stu-id="21f7f-124">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="21f7f-125">Nel campo **Nome** digitare **Configurazione del modello di esempio**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-125">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="21f7f-126">Nel campo **Descrizione** digitare **Configurazione del modello di esempio**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-126">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="21f7f-127">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-127">Select **Create configuration**.</span></span>
6. <span data-ttu-id="21f7f-128">Selezionare **Progettazione modello**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-128">Select **Model designer**.</span></span>
7. <span data-ttu-id="21f7f-129">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-129">Select **New**.</span></span>
8. <span data-ttu-id="21f7f-130">Nel campo **Nome**, immettere **Punto di ingresso**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-130">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="21f7f-131">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-131">Select **Add**.</span></span>
10. <span data-ttu-id="21f7f-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-132">Select **Save**.</span></span>
11. <span data-ttu-id="21f7f-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="21f7f-133">Close the page.</span></span>
12. <span data-ttu-id="21f7f-134">Selezionare **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-134">Select **Change status**.</span></span>
13. <span data-ttu-id="21f7f-135">Selezionare **Completa**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-135">Select **Complete**.</span></span>
14. <span data-ttu-id="21f7f-136">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-136">Select **OK**.</span></span>
15. <span data-ttu-id="21f7f-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="21f7f-137">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="21f7f-138">Registrare un nuovo archivio</span><span class="sxs-lookup"><span data-stu-id="21f7f-138">Register a new repository</span></span>

1. <span data-ttu-id="21f7f-139">Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-139">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="21f7f-140">Nella sezione **Provider di configurazione** selezionare il riquadro **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-140">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="21f7f-141">Nel riquadro **Litware, Inc.** selezionare **Archivi**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-141">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="21f7f-142">Ora è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="21f7f-142">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="21f7f-143">Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="21f7f-143">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="21f7f-144">Ora è possibile aggiungere un nuovo archivio.</span><span class="sxs-lookup"><span data-stu-id="21f7f-144">You can now add a new repository.</span></span>

5. <span data-ttu-id="21f7f-145">Nel campo dell'**archivio di configurazioni** selezionare **LCS**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-145">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="21f7f-146">Selezionare **Crea archivio**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-146">Select **Create repository**.</span></span>
7. <span data-ttu-id="21f7f-147">Nel campo **Progetto** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="21f7f-147">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="21f7f-148">Per questo esempio, selezionare il progetto LCS desiderato.</span><span class="sxs-lookup"><span data-stu-id="21f7f-148">For this example, select the desired LCS project.</span></span> <span data-ttu-id="21f7f-149">È necessario disporre dell'[accesso](#accessconditions) al progetto.</span><span class="sxs-lookup"><span data-stu-id="21f7f-149">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="21f7f-150">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-150">Select **OK**.</span></span>

    <span data-ttu-id="21f7f-151">Completare una nuova voce di archivio.</span><span class="sxs-lookup"><span data-stu-id="21f7f-151">Complete a new repository entry.</span></span>

9. <span data-ttu-id="21f7f-152">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="21f7f-152">In the list, mark the selected row.</span></span>

    <span data-ttu-id="21f7f-153">Per questo esempio, selezionare il record dell'archivio **LCS**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-153">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="21f7f-154">Notare che un archivio registrato è contrassegnato dal provider corrente.</span><span class="sxs-lookup"><span data-stu-id="21f7f-154">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="21f7f-155">In altre parole, solo le configurazioni di proprietà di quel provider possono essere inserite in questo archivio e quindi caricate nel progetto LCS selezionato.</span><span class="sxs-lookup"><span data-stu-id="21f7f-155">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="21f7f-156">Selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-156">Select **Open**.</span></span>

    <span data-ttu-id="21f7f-157">Aprire l'archivio per visualizzare l'elenco delle configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="21f7f-157">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="21f7f-158">Se il progetto selezionato non è stato ancora utilizzato per condividere configurazioni ER, l'elenco sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="21f7f-158">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="21f7f-159">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="21f7f-159">Close the page.</span></span>
12. <span data-ttu-id="21f7f-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="21f7f-160">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="21f7f-161">Caricare una configurazione in LCS</span><span class="sxs-lookup"><span data-stu-id="21f7f-161">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="21f7f-162">Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-162">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="21f7f-163">Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Configurazione del modello di esempio**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-163">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="21f7f-164">È necessario selezionare una configurazione creata che è già stata completata.</span><span class="sxs-lookup"><span data-stu-id="21f7f-164">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="21f7f-165">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="21f7f-165">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="21f7f-166">Per questo esempio, selezionare la versione della configurazione selezionata con stato **Completato**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-166">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="21f7f-167">Selezionare **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-167">Select **Change status**.</span></span>
5. <span data-ttu-id="21f7f-168">Selezionare **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-168">Select **Share**.</span></span>

    <span data-ttu-id="21f7f-169">Lo stato della configurazione viene modificato da **Completato** in **Condiviso** quando la configurazione viene pubblicata in LCS.</span><span class="sxs-lookup"><span data-stu-id="21f7f-169">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="21f7f-170">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-170">Select **OK**.</span></span>
7. <span data-ttu-id="21f7f-171">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="21f7f-171">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="21f7f-172">Per questo esempio, selezionare la versione della configurazione con stato **Condiviso**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-172">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="21f7f-173">Lo stato della versione selezionata è cambiato da **Completato** a **Condiviso**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-173">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="21f7f-174">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="21f7f-174">Close the page.</span></span>
9. <span data-ttu-id="21f7f-175">Selezionare **Archivi**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-175">Select **Repositories**.</span></span>

    <span data-ttu-id="21f7f-176">Ora è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="21f7f-176">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="21f7f-177">Selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-177">Select **Open**.</span></span>

    <span data-ttu-id="21f7f-178">Per questo esempio, selezionare il record dell'archivio **LCS** e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="21f7f-178">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="21f7f-179">Notare che la configurazione selezionata viene visualizzata come cespite del progetto LCS selezionato.</span><span class="sxs-lookup"><span data-stu-id="21f7f-179">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="21f7f-180">Aprire LCS andando in <https://lcs.dynamics.com>.</span><span class="sxs-lookup"><span data-stu-id="21f7f-180">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="21f7f-181">Aprire un progetto che è stato utilizzato in precedenza per la registrazione del repository.</span><span class="sxs-lookup"><span data-stu-id="21f7f-181">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="21f7f-182">Aprire la raccolta di cespiti del progetto.</span><span class="sxs-lookup"><span data-stu-id="21f7f-182">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="21f7f-183">Selezionare il tipo di cespite **Configurazione ER**.</span><span class="sxs-lookup"><span data-stu-id="21f7f-183">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="21f7f-184">La configurazione ER che hai caricato dovrebbe essere elencata.</span><span class="sxs-lookup"><span data-stu-id="21f7f-184">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="21f7f-185">La configurazione LCS caricata può essere inclusa in un'altra istanza se i fornitori hanno accesso a questo progetto LCS.</span><span class="sxs-lookup"><span data-stu-id="21f7f-185">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
