---
title: ER carica una configurazione in Lifecycle Services
description: I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) e caricarla in Microsoft Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19ae8820e5d4a798a5789e9632edb431fe9fede4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551115"
---
# <a name="er-upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="295fa-103">ER carica una configurazione in Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="295fa-103">ER Upload a configuration into Lifecycle Services</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="295fa-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) e caricarla in Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="295fa-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration and upload it into Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="295fa-105">In questo esempio verrà creata una configurazione che sarà caricata in LCS per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="295fa-105">In this example, you will create a configuration and upload it to LCS for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="295fa-106">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="295fa-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="295fa-107">L'accesso a LCS è necessario anche per il completamento delle operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="295fa-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="295fa-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="295fa-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="295fa-109">Selezionare "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="295fa-109">Select ‘Litware, Inc.’</span></span> <span data-ttu-id="295fa-110">e impostarlo come attivo.</span><span class="sxs-lookup"><span data-stu-id="295fa-110">and set it as active.</span></span>
3. <span data-ttu-id="295fa-111">Fare clic Configurazioni:</span><span class="sxs-lookup"><span data-stu-id="295fa-111">Click Configurations.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="295fa-112">Crea una nuova configurazione di modello dati</span><span class="sxs-lookup"><span data-stu-id="295fa-112">Create a new data model configuration</span></span>
1. <span data-ttu-id="295fa-113">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="295fa-113">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="295fa-114">Verrà creata una configurazione che contiene un modello dati di esempio per i documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="295fa-114">You will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="295fa-115">Questa configurazione del modello dati verrà caricata successivamente in LCS.</span><span class="sxs-lookup"><span data-stu-id="295fa-115">This data model configuration will be uploaded into LCS later.</span></span>  
2. <span data-ttu-id="295fa-116">Nel campo Nome digitare "Configurazione del modello di esempio".</span><span class="sxs-lookup"><span data-stu-id="295fa-116">In the Name field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="295fa-117">Configurazione del modello di esempio</span><span class="sxs-lookup"><span data-stu-id="295fa-117">Sample model configuration</span></span>  
3. <span data-ttu-id="295fa-118">Nel campo Descrizione digitare "Configurazione del modello di esempio".</span><span class="sxs-lookup"><span data-stu-id="295fa-118">In the Description field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="295fa-119">Configurazione del modello di esempio</span><span class="sxs-lookup"><span data-stu-id="295fa-119">Sample model configuration</span></span>  
4. <span data-ttu-id="295fa-120">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="295fa-120">Click Create configuration.</span></span>
5. <span data-ttu-id="295fa-121">Fare clic su Progettazione modello.</span><span class="sxs-lookup"><span data-stu-id="295fa-121">Click Model designer.</span></span>
6. <span data-ttu-id="295fa-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="295fa-122">Click New.</span></span>
7. <span data-ttu-id="295fa-123">Nel campo Nome digitare "Punto di ingresso".</span><span class="sxs-lookup"><span data-stu-id="295fa-123">In the Name field, type 'Entry point'.</span></span>
    * <span data-ttu-id="295fa-124">Punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="295fa-124">Entry point</span></span>  
8. <span data-ttu-id="295fa-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="295fa-125">Click Add.</span></span>
9. <span data-ttu-id="295fa-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="295fa-126">Click Save.</span></span>
10. <span data-ttu-id="295fa-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="295fa-127">Close the page.</span></span>
11. <span data-ttu-id="295fa-128">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="295fa-128">Click Change status.</span></span>
12. <span data-ttu-id="295fa-129">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="295fa-129">Click Complete.</span></span>
13. <span data-ttu-id="295fa-130">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="295fa-130">Click OK.</span></span>

## <a name="register-a-new--repository"></a><span data-ttu-id="295fa-131">Registrare un nuovo archivio</span><span class="sxs-lookup"><span data-stu-id="295fa-131">Register a new  repository</span></span>
1. <span data-ttu-id="295fa-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="295fa-132">Close the page.</span></span>
2. <span data-ttu-id="295fa-133">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="295fa-133">Click Repositories.</span></span>
    * <span data-ttu-id="295fa-134">In questo modo è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="295fa-134">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
3. <span data-ttu-id="295fa-135">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="295fa-135">Click Add to open the drop dialog.</span></span>
    * <span data-ttu-id="295fa-136">Ciò consente di aggiungere un nuovo archivio.</span><span class="sxs-lookup"><span data-stu-id="295fa-136">This allows you to add a new repository.</span></span>  
4. <span data-ttu-id="295fa-137">Nel campo Tipo di archivio di configurazioni selezionare LCS.</span><span class="sxs-lookup"><span data-stu-id="295fa-137">In the Configuration repository type field, select LCS.</span></span>
5. <span data-ttu-id="295fa-138">Fare clic su Crea archivio.</span><span class="sxs-lookup"><span data-stu-id="295fa-138">Click Create repository.</span></span>
6. <span data-ttu-id="295fa-139">Nel campo Progetto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="295fa-139">In the Project field, enter or select a value.</span></span>
    * <span data-ttu-id="295fa-140">Selezionare il progetto LCS desiderato.</span><span class="sxs-lookup"><span data-stu-id="295fa-140">Select the desired LCS project.</span></span> <span data-ttu-id="295fa-141">È necessario disporre dell'accesso al progetto.</span><span class="sxs-lookup"><span data-stu-id="295fa-141">You must have access to the project.</span></span>  
7. <span data-ttu-id="295fa-142">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="295fa-142">Click OK.</span></span>
    * <span data-ttu-id="295fa-143">Completare una nuova voce di archivio.</span><span class="sxs-lookup"><span data-stu-id="295fa-143">Complete a new repository entry.</span></span>  
8. <span data-ttu-id="295fa-144">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="295fa-144">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="295fa-145">Selezionare il record Archivio LCS.</span><span class="sxs-lookup"><span data-stu-id="295fa-145">Select the LCS repository record.</span></span>  
    * <span data-ttu-id="295fa-146">Un archivio registrato è contrassegnato dal fornitore corrente, pertanto le sole configurazioni di proprietà dal fornitore possono essere posizionate nell'archivio e, di conseguenza, essere caricate nel progetto LCS selezionato.</span><span class="sxs-lookup"><span data-stu-id="295fa-146">Note that a registered repository is marked by the current provider meaning that the only configurations owned by that provider can be placed to this repository and, consequently, uploaded into the selected LCS project.</span></span>  
9. <span data-ttu-id="295fa-147">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="295fa-147">Click Open.</span></span>
    * <span data-ttu-id="295fa-148">Aprire l'archivio per visualizzare l'elenco delle configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="295fa-148">Open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="295fa-149">Sarà vuoto se questo progetto non è stato ancora utilizzato per condividere configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="295fa-149">It will be empty if this project has not yet been used for ER configurations sharing.</span></span>  
10. <span data-ttu-id="295fa-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="295fa-150">Close the page.</span></span>
11. <span data-ttu-id="295fa-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="295fa-151">Close the page.</span></span>

## <a name="upload-configuration-into-lcs"></a><span data-ttu-id="295fa-152">Caricare la configurazione in LCS</span><span class="sxs-lookup"><span data-stu-id="295fa-152">Upload configuration into LCS</span></span>
1. <span data-ttu-id="295fa-153">Fare clic Configurazioni:</span><span class="sxs-lookup"><span data-stu-id="295fa-153">Click Configurations.</span></span>
2. <span data-ttu-id="295fa-154">Nella struttura selezionare "Configurazione del modello di esempio".</span><span class="sxs-lookup"><span data-stu-id="295fa-154">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="295fa-155">Selezionare una configurazione creata che è già stata completata.</span><span class="sxs-lookup"><span data-stu-id="295fa-155">Select a created configuration that has been already completed.</span></span>  
3. <span data-ttu-id="295fa-156">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="295fa-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="295fa-157">Selezionare la versione della configurazione selezionata con stato "Completato".</span><span class="sxs-lookup"><span data-stu-id="295fa-157">Select the version of the selected configuration with the status of ‘Completed’.</span></span>  
4. <span data-ttu-id="295fa-158">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="295fa-158">Click Change status.</span></span>
5. <span data-ttu-id="295fa-159">Fare clic su Condividi.</span><span class="sxs-lookup"><span data-stu-id="295fa-159">Click Share.</span></span>
    * <span data-ttu-id="295fa-160">Lo stato della configurazione verrà cambiato da "Completato “a "Condiviso" quando verrà pubblicato in LCS.</span><span class="sxs-lookup"><span data-stu-id="295fa-160">The configuration status will change from ‘Completed’ to ‘Shared’ when it is published in LCS.</span></span>  
6. <span data-ttu-id="295fa-161">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="295fa-161">Click OK.</span></span>
7. <span data-ttu-id="295fa-162">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="295fa-162">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="295fa-163">Selezionare la versione di configurazione con stato "Condiviso".</span><span class="sxs-lookup"><span data-stu-id="295fa-163">Select the configuration version with the status of 'Shared'.</span></span>  
    * <span data-ttu-id="295fa-164">Lo stato della versione selezionata è cambiato da "Completato" a "Condiviso".</span><span class="sxs-lookup"><span data-stu-id="295fa-164">Note that the status of the selected version has changed from ‘Completed’ to ‘Shared’.</span></span>  
8. <span data-ttu-id="295fa-165">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="295fa-165">Close the page.</span></span>
9. <span data-ttu-id="295fa-166">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="295fa-166">Click Repositories.</span></span>
    * <span data-ttu-id="295fa-167">In questo modo è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="295fa-167">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
10. <span data-ttu-id="295fa-168">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="295fa-168">Click Open.</span></span>
    * <span data-ttu-id="295fa-169">Selezionare l'archivio LCS e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="295fa-169">Select the LCS repository and open it.</span></span>  
    * <span data-ttu-id="295fa-170">La configurazione selezionata viene visualizzata come cespite del progetto LCS selezionato.</span><span class="sxs-lookup"><span data-stu-id="295fa-170">Note that the selected configuration is shown as an asset of the selected LCS project.</span></span>  
    * <span data-ttu-id="295fa-171">Aprire LCS usando https://lcs.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="295fa-171">Open LCS using https://lcs.dynamics.com.</span></span> <span data-ttu-id="295fa-172">Aprire un progetto utilizzato in precedenza per la registrazione di archivio, quindi aprire "Raccolta di risorse" di questo progetto ed espandere il contenuto del tipo di risorsa "Configurazione GER": la configurazione ER caricata sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="295fa-172">Open a project that was used earlier for repository registration, open the ‘Asset library’ of this project, and expand the content of the ‘GER configuration’ asset type – the uploaded ER configuration will be available.</span></span> <span data-ttu-id="295fa-173">La configurazione LCS caricata può essere inclusa in un'altra istanza di Microsoft Dynamics 365 for Finance and Operations, edizione Enterprise, se i fornitori hanno accesso a questo progetto LCS.</span><span class="sxs-lookup"><span data-stu-id="295fa-173">Note that the uploaded LCS configuration can be imported to another Microsoft Dynamics 365 for Finance and Operations, Enterprise edition instance if providers have access to this LCS project.</span></span>  

