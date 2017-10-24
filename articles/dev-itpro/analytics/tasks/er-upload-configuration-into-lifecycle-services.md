--- 
title: Caricare una configurazione in Lifecycle Services per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) e caricarla in Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d24679a380ec824fe08c56aacb4bc348ff40440a
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="upload-a-configuration-into-lifecycle-services-for-electronic-reporting-er"></a><span data-ttu-id="8b4c0-103">Caricare una configurazione in Lifecycle Services per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="8b4c0-103">Upload a configuration into Lifecycle Services for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8b4c0-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) e caricarla in Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8b4c0-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration and upload it into Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="8b4c0-105">In questo esempio verrà creata una configurazione che sarà caricata in LCS per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-105">In this example, you will create a configuration and upload it to LCS for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="8b4c0-106">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="8b4c0-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="8b4c0-107">L'accesso a LCS è necessario anche per il completamento delle operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="8b4c0-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="8b4c0-109">Selezionare "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="8b4c0-109">Select ‘Litware, Inc.’</span></span> <span data-ttu-id="8b4c0-110">e impostarlo come attivo.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-110">and set it as active.</span></span>
3. <span data-ttu-id="8b4c0-111">Fare clic Configurazioni:</span><span class="sxs-lookup"><span data-stu-id="8b4c0-111">Click Configurations.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="8b4c0-112">Crea una nuova configurazione di modello dati</span><span class="sxs-lookup"><span data-stu-id="8b4c0-112">Create a new data model configuration</span></span>
1. <span data-ttu-id="8b4c0-113">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="8b4c0-113">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="8b4c0-114">Verrà creata una configurazione che contiene un modello dati di esempio per i documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-114">You will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="8b4c0-115">Questa configurazione del modello dati verrà caricata successivamente in LCS.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-115">This data model configuration will be uploaded into LCS later.</span></span>  
2. <span data-ttu-id="8b4c0-116">Nel campo Nome digitare "Configurazione del modello di esempio".</span><span class="sxs-lookup"><span data-stu-id="8b4c0-116">In the Name field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="8b4c0-117">Configurazione del modello di esempio</span><span class="sxs-lookup"><span data-stu-id="8b4c0-117">Sample model configuration</span></span>  
3. <span data-ttu-id="8b4c0-118">Nel campo Descrizione digitare "Configurazione del modello di esempio".</span><span class="sxs-lookup"><span data-stu-id="8b4c0-118">In the Description field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="8b4c0-119">Configurazione del modello di esempio</span><span class="sxs-lookup"><span data-stu-id="8b4c0-119">Sample model configuration</span></span>  
4. <span data-ttu-id="8b4c0-120">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-120">Click Create configuration.</span></span>
5. <span data-ttu-id="8b4c0-121">Fare clic su Progettazione modello.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-121">Click Model designer.</span></span>
6. <span data-ttu-id="8b4c0-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-122">Click New.</span></span>
7. <span data-ttu-id="8b4c0-123">Nel campo Nome digitare "Punto di ingresso".</span><span class="sxs-lookup"><span data-stu-id="8b4c0-123">In the Name field, type 'Entry point'.</span></span>
    * <span data-ttu-id="8b4c0-124">Punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="8b4c0-124">Entry point</span></span>  
8. <span data-ttu-id="8b4c0-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-125">Click Add.</span></span>
9. <span data-ttu-id="8b4c0-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-126">Click Save.</span></span>
10. <span data-ttu-id="8b4c0-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-127">Close the page.</span></span>
11. <span data-ttu-id="8b4c0-128">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-128">Click Change status.</span></span>
12. <span data-ttu-id="8b4c0-129">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-129">Click Complete.</span></span>
13. <span data-ttu-id="8b4c0-130">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-130">Click OK.</span></span>

## <a name="register-a-new--repository"></a><span data-ttu-id="8b4c0-131">Registrare un nuovo archivio</span><span class="sxs-lookup"><span data-stu-id="8b4c0-131">Register a new  repository</span></span>
1. <span data-ttu-id="8b4c0-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-132">Close the page.</span></span>
2. <span data-ttu-id="8b4c0-133">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-133">Click Repositories.</span></span>
    * <span data-ttu-id="8b4c0-134">In questo modo è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-134">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
3. <span data-ttu-id="8b4c0-135">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-135">Click Add to open the drop dialog.</span></span>
    * <span data-ttu-id="8b4c0-136">Ciò consente di aggiungere un nuovo archivio.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-136">This allows you to add a new repository.</span></span>  
4. <span data-ttu-id="8b4c0-137">Nel campo Tipo di archivio di configurazioni selezionare LCS.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-137">In the Configuration repository type field, select LCS.</span></span>
5. <span data-ttu-id="8b4c0-138">Fare clic su Crea archivio.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-138">Click Create repository.</span></span>
6. <span data-ttu-id="8b4c0-139">Nel campo Progetto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-139">In the Project field, enter or select a value.</span></span>
    * <span data-ttu-id="8b4c0-140">Selezionare il progetto LCS desiderato.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-140">Select the desired LCS project.</span></span> <span data-ttu-id="8b4c0-141">È necessario disporre dell'accesso al progetto.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-141">You must have access to the project.</span></span>  
7. <span data-ttu-id="8b4c0-142">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-142">Click OK.</span></span>
    * <span data-ttu-id="8b4c0-143">Completare una nuova voce di archivio.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-143">Complete a new repository entry.</span></span>  
8. <span data-ttu-id="8b4c0-144">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-144">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8b4c0-145">Selezionare il record Archivio LCS.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-145">Select the LCS repository record.</span></span>  
    * <span data-ttu-id="8b4c0-146">Un archivio registrato è contrassegnato dal fornitore corrente, pertanto le sole configurazioni di proprietà dal fornitore possono essere posizionate nell'archivio e, di conseguenza, essere caricate nel progetto LCS selezionato.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-146">Note that a registered repository is marked by the current provider meaning that the only configurations owned by that provider can be placed to this repository and, consequently, uploaded into the selected LCS project.</span></span>  
9. <span data-ttu-id="8b4c0-147">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-147">Click Open.</span></span>
    * <span data-ttu-id="8b4c0-148">Aprire l'archivio per visualizzare l'elenco delle configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-148">Open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="8b4c0-149">Sarà vuoto se questo progetto non è stato ancora utilizzato per condividere configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-149">It will be empty if this project has not yet been used for ER configurations sharing.</span></span>  
10. <span data-ttu-id="8b4c0-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-150">Close the page.</span></span>
11. <span data-ttu-id="8b4c0-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-151">Close the page.</span></span>

## <a name="upload-configuration-into-lcs"></a><span data-ttu-id="8b4c0-152">Caricare la configurazione in LCS</span><span class="sxs-lookup"><span data-stu-id="8b4c0-152">Upload configuration into LCS</span></span>
1. <span data-ttu-id="8b4c0-153">Fare clic Configurazioni:</span><span class="sxs-lookup"><span data-stu-id="8b4c0-153">Click Configurations.</span></span>
2. <span data-ttu-id="8b4c0-154">Nella struttura selezionare "Configurazione del modello di esempio".</span><span class="sxs-lookup"><span data-stu-id="8b4c0-154">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="8b4c0-155">Selezionare una configurazione creata che è già stata completata.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-155">Select a created configuration that has been already completed.</span></span>  
3. <span data-ttu-id="8b4c0-156">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8b4c0-157">Selezionare la versione della configurazione selezionata con stato "Completato".</span><span class="sxs-lookup"><span data-stu-id="8b4c0-157">Select the version of the selected configuration with the status of ‘Completed’.</span></span>  
4. <span data-ttu-id="8b4c0-158">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-158">Click Change status.</span></span>
5. <span data-ttu-id="8b4c0-159">Fare clic su Condividi.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-159">Click Share.</span></span>
    * <span data-ttu-id="8b4c0-160">Lo stato della configurazione verrà cambiato da "Completato “a "Condiviso" quando verrà pubblicato in LCS.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-160">The configuration status will change from ‘Completed’ to ‘Shared’ when it is published in LCS.</span></span>  
6. <span data-ttu-id="8b4c0-161">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-161">Click OK.</span></span>
7. <span data-ttu-id="8b4c0-162">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-162">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8b4c0-163">Selezionare la versione di configurazione con stato "Condiviso".</span><span class="sxs-lookup"><span data-stu-id="8b4c0-163">Select the configuration version with the status of 'Shared'.</span></span>  
    * <span data-ttu-id="8b4c0-164">Lo stato della versione selezionata è cambiato da "Completato" a "Condiviso".</span><span class="sxs-lookup"><span data-stu-id="8b4c0-164">Note that the status of the selected version has changed from ‘Completed’ to ‘Shared’.</span></span>  
8. <span data-ttu-id="8b4c0-165">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-165">Close the page.</span></span>
9. <span data-ttu-id="8b4c0-166">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-166">Click Repositories.</span></span>
    * <span data-ttu-id="8b4c0-167">In questo modo è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-167">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
10. <span data-ttu-id="8b4c0-168">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-168">Click Open.</span></span>
    * <span data-ttu-id="8b4c0-169">Selezionare l'archivio LCS e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-169">Select the LCS repository and open it.</span></span>  
    * <span data-ttu-id="8b4c0-170">La configurazione selezionata viene visualizzata come cespite del progetto LCS selezionato.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-170">Note that the selected configuration is shown as an asset of the selected LCS project.</span></span>  
    * <span data-ttu-id="8b4c0-171">Aprire LCS tramite https://lcs.dynamics.com. Aprire un progetto utilizzato in precedenza per la registrazione di archivio, quindi aprire "Raccolta di risorse" di questo progetto ed espandere il contenuto del tipo di risorsa "Configurazione GER": la configurazione ER caricata sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-171">Open LCS using https://lcs.dynamics.com. Open a project that was used earlier for repository registration, open the ‘Asset library’ of this project, and expand the content of the ‘GER configuration’ asset type – the uploaded ER configuration will be available.</span></span> <span data-ttu-id="8b4c0-172">La configurazione LCS caricata può essere inclusa in un'altra istanza di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition se i fornitori hanno accesso a questo progetto LCS.</span><span class="sxs-lookup"><span data-stu-id="8b4c0-172">Note that the uploaded LCS configuration can be imported to another Microsoft Dynamics 365 for Finance and Operations, Enterprise edition instance if providers have access to this LCS project.</span></span>  


