---
title: Progettare le configurazioni per generare report in formato di Office con immagini incorporate
description: Questo argomento descrive come progettare configurazioni che generano documenti elettronici nei formati Excel e Word contenenti le immagini incorporate.
author: NickSelin
manager: AnnBe
ms.date: 01/23/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b60ed6b07851c44ceb4b8f313bc65f04b802e646
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093672"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="69722-103">Progettare le configurazioni per generare report in formato di Office con immagini incorporate</span><span class="sxs-lookup"><span data-stu-id="69722-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="69722-104">Per completare i passaggi in questa procedura, prima completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="69722-104">To complete the steps in this procedure, first complete the procedure, "ER Create a configuration provider and mark it as active."</span></span> <span data-ttu-id="69722-105">In questa procedura viene illustrato come progettare le configurazioni ER per generare un documento di Microsoft Excel o Word contenente le immagini incorporate.</span><span class="sxs-lookup"><span data-stu-id="69722-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="69722-106">In questa procedura, verranno create le configurazioni ER necessarie per la società di esempio, Litware, Inc. Questi passaggi possono essere completati mediante il set di dati USMF.</span><span class="sxs-lookup"><span data-stu-id="69722-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="69722-107">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="69722-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="69722-108">Prima di iniziare, scaricare e salvare i file elencati nell'argomento della Guida: [Incorporare immagini e forme nei documenti generati utilizzando ER](../electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="69722-108">Before you begin, download and save the files listed in the Help topic, [Embed images and shapes in documents that you generate by using ER](../electronic-reporting-embed-images-shapes.md).</span></span> <span data-ttu-id="69722-109">I file sono: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png e Cheque template Word.docx.</span><span class="sxs-lookup"><span data-stu-id="69722-109">The files are: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png, and Cheque template Word.docx.</span></span>

## <a name="verify-prerequisites"></a><span data-ttu-id="69722-110">Verificare i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="69722-110">Verify prerequisites</span></span>  
 1. <span data-ttu-id="69722-111">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="69722-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="69722-112">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="69722-112">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="69722-113">Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="69722-113">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>   
 3. <span data-ttu-id="69722-114">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="69722-114">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="69722-115">Aggiungere una nuova configurazione del modello ER</span><span class="sxs-lookup"><span data-stu-id="69722-115">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="69722-116">Anziché creare un nuovo modello, è possibile caricare il file di configurazione del modello ER (Model for cheques.xml) salvato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="69722-116">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="69722-117">Questo file contiene il modello dati di esempio per gli assegni di pagamento e il mapping del modello dati ai dati componenti dell'applicazione Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="69722-117">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="69722-118">Nella scheda dettaglio Versioni fare clic su Scambia.</span><span class="sxs-lookup"><span data-stu-id="69722-118">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="69722-119">Fare clic su Carica da file XML.</span><span class="sxs-lookup"><span data-stu-id="69722-119">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="69722-120">Fare clic su Sfoglia quindi selezionare Model for cheques.xml.</span><span class="sxs-lookup"><span data-stu-id="69722-120">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="69722-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="69722-121">Click OK.</span></span>  
 6. <span data-ttu-id="69722-122">Il modello caricato verrà utilizzato come origine dati delle informazioni per generare i documenti contenenti le immagini in Excel e Word.</span><span class="sxs-lookup"><span data-stu-id="69722-122">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="69722-123">Aggiungere una nuova configurazione di formato ER</span><span class="sxs-lookup"><span data-stu-id="69722-123">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="69722-124">Anziché creare un nuovo formato, è possibile caricare il file di configurazione del formato ER (Cheques printing format.xml) salvato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="69722-124">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="69722-125">Questo file contiene il layout di esempio del formato per stampare gli assegni utilizzando il modulo prestampato e il mapping di questo formato al modello di dati per assegni.</span><span class="sxs-lookup"><span data-stu-id="69722-125">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the 'Model for cheques' data model.</span></span>   
 2. <span data-ttu-id="69722-126">Fare clic su Scambia.</span><span class="sxs-lookup"><span data-stu-id="69722-126">Click Exchange.</span></span>  
 3. <span data-ttu-id="69722-127">Fare clic su Carica da file XML.</span><span class="sxs-lookup"><span data-stu-id="69722-127">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="69722-128">Fare clic su Sfoglia e selezionare il file Cheques printing format.xml.</span><span class="sxs-lookup"><span data-stu-id="69722-128">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="69722-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="69722-129">Click OK.</span></span>  
 6. <span data-ttu-id="69722-130">Nella struttura espandere "Model for cheques".</span><span class="sxs-lookup"><span data-stu-id="69722-130">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="69722-131">Nella struttura selezionare "Model for cheques\Cheques printing format".</span><span class="sxs-lookup"><span data-stu-id="69722-131">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="69722-132">Il formato caricato verrà utilizzato per generare i documenti contenenti le immagini in Excel e Word.</span><span class="sxs-lookup"><span data-stu-id="69722-132">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="69722-133">Configurare i parametri utente ER</span><span class="sxs-lookup"><span data-stu-id="69722-133">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="69722-134">Nel riquadro azioni, fare clic su Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="69722-134">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="69722-135">Fare clic su Parametri utente.</span><span class="sxs-lookup"><span data-stu-id="69722-135">Click User parameters.</span></span>  
 3. <span data-ttu-id="69722-136">Selezionare Sì nel campo Esegui impostazioni.</span><span class="sxs-lookup"><span data-stu-id="69722-136">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="69722-137">Attivare il flag "Esegui bozza" per avviare la versione bozza del formato selezionato anziché di quello completato.</span><span class="sxs-lookup"><span data-stu-id="69722-137">Turn on the 'Run draft' flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="69722-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="69722-138">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="69722-139">Configurare i Parametri di gestione cassa e banche</span><span class="sxs-lookup"><span data-stu-id="69722-139">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="69722-140">Andare a Gestione cassa e banche > Conti bancari > Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="69722-140">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="69722-141">Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="69722-141">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="69722-142">Nel riquadro azioni, fare clic su Imposta.</span><span class="sxs-lookup"><span data-stu-id="69722-142">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="69722-143">Fare clic su Verifica.</span><span class="sxs-lookup"><span data-stu-id="69722-143">Click Check.</span></span>  
 5. <span data-ttu-id="69722-144">Espandere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="69722-144">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="69722-145">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="69722-145">Click Edit.</span></span>  
 7. <span data-ttu-id="69722-146">Selezionare Sì nel campo Logo società.</span><span class="sxs-lookup"><span data-stu-id="69722-146">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="69722-147">Fare clic su il logo della società.</span><span class="sxs-lookup"><span data-stu-id="69722-147">Click Company logo.</span></span>  
 9. <span data-ttu-id="69722-148">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="69722-148">Click Change.</span></span>  
 10. <span data-ttu-id="69722-149">Fare clic su Sfoglia e selezionare il file scaricato in precedenza, Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="69722-149">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="69722-150">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="69722-150">Click Save.</span></span>  
 12. <span data-ttu-id="69722-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="69722-151">Close the page.</span></span>  
 13. <span data-ttu-id="69722-152">Espandere la sezione Firma.</span><span class="sxs-lookup"><span data-stu-id="69722-152">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="69722-153">Selezionare Sì nel campo Stampa prima firma.</span><span class="sxs-lookup"><span data-stu-id="69722-153">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="69722-154">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="69722-154">Click Change.</span></span>  
 16. <span data-ttu-id="69722-155">Fare clic su Sfoglia e selezionare il file scaricato in precedenza, Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="69722-155">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="69722-156">Espandere la sezione Copie.</span><span class="sxs-lookup"><span data-stu-id="69722-156">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="69722-157">Nel campo Filigrana selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="69722-157">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="69722-158">Selezionare Sì nel campo Formato esportazione elettronica generica.</span><span class="sxs-lookup"><span data-stu-id="69722-158">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="69722-159">Selezionare la configurazione 'Cheques printing format'.</span><span class="sxs-lookup"><span data-stu-id="69722-159">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="69722-160">Ora il formato ER selezionato verrà utilizzato per la stampa degli assegni.</span><span class="sxs-lookup"><span data-stu-id="69722-160">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="69722-161">Fare clic su Allega.</span><span class="sxs-lookup"><span data-stu-id="69722-161">Click Attach.</span></span>  
 23. <span data-ttu-id="69722-162">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="69722-162">Click New.</span></span>  
 24. <span data-ttu-id="69722-163">Fare clic su File.</span><span class="sxs-lookup"><span data-stu-id="69722-163">Click File.</span></span>  
 25. <span data-ttu-id="69722-164">Fare clic su Sfoglia e selezionare il file scaricato in precedenza, Signature image 2.png.</span><span class="sxs-lookup"><span data-stu-id="69722-164">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="69722-165">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="69722-165">Close the page.</span></span>  
 27. <span data-ttu-id="69722-166">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="69722-166">Close the page.</span></span>  
 28. <span data-ttu-id="69722-167">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="69722-167">Close the page.</span></span>  
 29. <span data-ttu-id="69722-168">Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.</span><span class="sxs-lookup"><span data-stu-id="69722-168">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="69722-169">Selezionare Sì nel campo Consenti creazione notifica anticipata su conti bancari inattivi.</span><span class="sxs-lookup"><span data-stu-id="69722-169">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="69722-170">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="69722-170">Click Save.</span></span>  
 32. <span data-ttu-id="69722-171">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="69722-171">Close the page.</span></span>  
