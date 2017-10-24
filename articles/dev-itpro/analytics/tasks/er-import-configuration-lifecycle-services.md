--- 
title: Importare una configurazione da Lifecycle Services per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può importare una nuova configurazione per la creazione di report elettronici (ER) da Microsoft Lifecycle Services (LCS)."
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
ms.openlocfilehash: 9eb4f54897c84b98828c927f0f93613583fd4599
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="import-a-configuration-from-lifecycle-services-for-electronic-reporting-er"></a><span data-ttu-id="6b730-103">Importare una configurazione da Lifecycle Services per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="6b730-103">Import a configuration from Lifecycle Services for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6b730-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può importare una nuova configurazione per la creazione di report elettronici (ER) da Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="6b730-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="6b730-105">In questo esempio si dovrà selezionare la versione desiderata della configurazione ER e importarla per la società di esempio, Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="6b730-105">In this example, you will select the desired version of the ER configuration and import it for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="6b730-106">Per completare questi passaggi, è necessario completare i passaggi della procedura "Caricare una configurazione ER in Lifecycle Services".</span><span class="sxs-lookup"><span data-stu-id="6b730-106">To complete these steps, you must first complete the steps in the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="6b730-107">L'accesso a LCS è necessario anche per il completamento delle operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="6b730-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="6b730-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="6b730-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="6b730-109">Fare clic Configurazioni:</span><span class="sxs-lookup"><span data-stu-id="6b730-109">Click Configurations.</span></span>

## <a name="delete-a-shared-version-of-data-model-configuration"></a><span data-ttu-id="6b730-110">Eliminare una versione condivisa della configurazione del modello dati</span><span class="sxs-lookup"><span data-stu-id="6b730-110">Delete a shared version of data model configuration</span></span>
1. <span data-ttu-id="6b730-111">Nella struttura selezionare "Configurazione del modello di esempio".</span><span class="sxs-lookup"><span data-stu-id="6b730-111">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="6b730-112">La prima versione di una configurazione del modello dati di esempio è stata creata e pubblicata in LCS durante la procedura "Caricare una configurazione ER in Lifecycle Services".</span><span class="sxs-lookup"><span data-stu-id="6b730-112">The first version of a sample data model configuration has been created and published to LCS during the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="6b730-113">In questa procedura verrà eliminata questa versione della configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="6b730-113">In this procedure, you will delete this version of the ER configuration.</span></span> <span data-ttu-id="6b730-114">Questa versione di una configurazione del modello dati di esempio verrà importata più avanti da LCS.</span><span class="sxs-lookup"><span data-stu-id="6b730-114">This version of a sample data model configuration will be imported later from LCS.</span></span>  
2. <span data-ttu-id="6b730-115">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="6b730-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="6b730-116">Selezionare la versione di questa configurazione con stato "Condiviso".</span><span class="sxs-lookup"><span data-stu-id="6b730-116">Select the version of this configuration that is in the ‘Shared’ status.</span></span> <span data-ttu-id="6b730-117">Questo stato indica che la configurazione è stata pubblicata in LCS.</span><span class="sxs-lookup"><span data-stu-id="6b730-117">This status indicates that the configuration has been published to LCS.</span></span>  
3. <span data-ttu-id="6b730-118">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="6b730-118">Click Change status.</span></span>
4. <span data-ttu-id="6b730-119">Fare clic su Sospendi.</span><span class="sxs-lookup"><span data-stu-id="6b730-119">Click Discontinue.</span></span>
    * <span data-ttu-id="6b730-120">Modificare lo stato della versione selezionata da "Condiviso" a “Interrotto" per renderla disponibile per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="6b730-120">Change the status of the selected version from ‘Shared’ to ‘Discontinued’ to make it available for deletion.</span></span>  
5. <span data-ttu-id="6b730-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6b730-121">Click OK.</span></span>
6. <span data-ttu-id="6b730-122">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="6b730-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="6b730-123">Selezionare la versione di questa configurazione con stato "Interrotto".</span><span class="sxs-lookup"><span data-stu-id="6b730-123">Select the version of this configuration that has a status of ‘Discontinued’.</span></span>  
7. <span data-ttu-id="6b730-124">Fare clic su Elimina.</span><span class="sxs-lookup"><span data-stu-id="6b730-124">Click Delete.</span></span>
8. <span data-ttu-id="6b730-125">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="6b730-125">Click Yes.</span></span>
    * <span data-ttu-id="6b730-126">Solo la versione bozza 2 della configurazione selezionata del modello dati è disponibile.</span><span class="sxs-lookup"><span data-stu-id="6b730-126">Note that the only draft version 2 of the selected data model configuration is available.</span></span>  
9. <span data-ttu-id="6b730-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6b730-127">Close the page.</span></span>

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a><span data-ttu-id="6b730-128">Importare una versione condivisa della configurazione del modello dati da LCS</span><span class="sxs-lookup"><span data-stu-id="6b730-128">Import a shared version of data model configuration from LCS</span></span>
1. <span data-ttu-id="6b730-129">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6b730-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6b730-130">Aprire l'elenco degli archivi per il provider di configurazione per</span><span class="sxs-lookup"><span data-stu-id="6b730-130">Open the list of repositories for the ‘Litware, Inc.’</span></span> <span data-ttu-id="6b730-131">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="6b730-131">configuration provider.</span></span>  
2. <span data-ttu-id="6b730-132">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="6b730-132">Click Repositories.</span></span>
3. <span data-ttu-id="6b730-133">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="6b730-133">Click Open.</span></span>
    * <span data-ttu-id="6b730-134">Selezionare l'archivio LCS e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="6b730-134">Select the LCS repository and open it.</span></span>  
4. <span data-ttu-id="6b730-135">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6b730-135">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6b730-136">Selezionare la prima versione della "Configurazione del modello di esempio" nell'elenco delle versioni.</span><span class="sxs-lookup"><span data-stu-id="6b730-136">Select the first version of the 'Sample model configuration' in the versions list.</span></span>  
5. <span data-ttu-id="6b730-137">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="6b730-137">Click Import.</span></span>
6. <span data-ttu-id="6b730-138">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="6b730-138">Click Yes.</span></span>
    * <span data-ttu-id="6b730-139">Confermare l'importazione della versione selezionata dal LCS.</span><span class="sxs-lookup"><span data-stu-id="6b730-139">Confirm the import of the selected version from LCS .</span></span>  
    * <span data-ttu-id="6b730-140">Il messaggio informativo (sopra il modulo) conferma il completamento dell'importazione della versione selezionata.</span><span class="sxs-lookup"><span data-stu-id="6b730-140">Note that the information message (above the form) confirms the successful completion of the import of the selected version.</span></span>  
7. <span data-ttu-id="6b730-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6b730-141">Close the page.</span></span>
8. <span data-ttu-id="6b730-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6b730-142">Close the page.</span></span>
9. <span data-ttu-id="6b730-143">Fare clic Configurazioni:</span><span class="sxs-lookup"><span data-stu-id="6b730-143">Click Configurations.</span></span>
10. <span data-ttu-id="6b730-144">Nella struttura selezionare "Configurazione del modello di esempio".</span><span class="sxs-lookup"><span data-stu-id="6b730-144">In the tree, select 'Sample model configuration'.</span></span>
11. <span data-ttu-id="6b730-145">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="6b730-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="6b730-146">Selezionare la versione di questa configurazione con stato "Condiviso".</span><span class="sxs-lookup"><span data-stu-id="6b730-146">Select the version of this configuration that has a status of ‘Shared’.</span></span>  
    * <span data-ttu-id="6b730-147">Anche la versione condivisa 1 della configurazione selezionata del modello dati è ora disponibile.</span><span class="sxs-lookup"><span data-stu-id="6b730-147">Note that the shared version 1 of the selected data model configuration is available now as well.</span></span>  


